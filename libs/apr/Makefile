#
# Copyright (C) 2007-2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
# $Id: Makefile 12228 2008-08-06 22:43:15Z nbd $ 

include $(TOPDIR)/rules.mk

PKG_NAME:=apr
PKG_VERSION:=1.4.5
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=http://www.ibiblio.org/pub/mirrors/apache/apr
PKG_MD5SUM:=8b53f5a5669d0597f2da889a2f576eb6

PKG_FIXUP:=autoreconf
PKG_REMOVE_FILES:=aclocal.m4 build/ltmain.sh

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libapr
  SECTION:=libs
  CATEGORY:=Libraries
  DEPENDS:=+libpthread +librt
  TITLE:=Apache Portable Runtime Library
  URL:=http://apr.apache.org/
endef

TARGET_CFLAGS += $(FPIC)
CONFIGURE_ARGS += \
	--with-devrandom=/dev/urandom \
	--enable-ipv6

# XXX: ac_cv_sizeof_struct_iovec=1 is just to trick configure
CONFIGURE_VARS += \
	ac_cv_sizeof_struct_iovec=1 \
	apr_cv_process_shared_works=no \
	apr_cv_mutex_robust_shared=no \
	apr_cv_tcp_nodelay_with_cork=yes \
	ac_cv_struct_rlimit=yes \
	LDFLAGS="$$$$LDFLAGS -lpthread"

ifneq ($(CONFIG_PACKAGE_libapr),)
define Build/Compile/libapr
	echo configuring APR Dynamic
	$(call Build/Configure/Default, \
		--disable-static \
		--enable-layout=GNU \
		--enable-lfs \
		--enable-ipv6 \
	)
	echo Building APR Dynamic
	$(MAKE) -C $(PKG_BUILD_DIR) DESTDIR="$(PKG_INSTALL_DIR)" all install
endef
endif

define Build/Compile
	$(call Build/Compile/libapr)
endef

define Build/Configure
   echo NOT configuring APR
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/bin $(1)/usr/include/apr-1 $(1)/usr/lib $(1)/usr/lib/pkgconfig $(1)/usr/share/build-1 $(1)/usr/include/apache2
	$(CP)   $(PKG_INSTALL_DIR)/usr/bin/apr-1-config*    $(1)/usr/bin || true
	$(CP)   $(PKG_INSTALL_DIR)/usr/include/apr-1/*      $(1)/usr/include/apr-1 || true
	$(CP)   $(PKG_INSTALL_DIR)/usr/include/apache2/*    $(1)/usr/include/apache2 || true
	$(CP)   $(PKG_INSTALL_DIR)/usr/lib/lib{apr-1,apr}.{la,a,so*} $(1)/usr/lib || true
	$(CP)   $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/apr-1.pc $(1)/usr/lib/pkgconfig || true 
	$(CP)   $(PKG_INSTALL_DIR)/usr/share/build-1/*      $(1)/usr/share/build-1 || true
	for i in $(1)/usr/bin/apr-1-config* ; do \
	  $(SED) 's,^datadir=\"/usr/share\",datadir=\"$(STAGING_DIR)/usr/share\",g' $$$$i; \
	  $(SED) 's,^installbuilddir=\"/usr/share/build-1\",installbuilddir=\"$(STAGING_DIR)/usr/share/build-1\",g' $$$$i ; \
	  $(SED) 's,^libdir=\"$$$${exec_prefix}/lib,libdir=\"$(STAGING_DIR)/usr/lib,g' $$$$i ; \
	  $(SED) 's,^includedir=\"$$$${prefix}/include/,includedir=\"$(STAGING_DIR)/usr/include/,g' $$$$i ; \
	  $(SED) 's,-L$$$$libdir,,g' $$$$i ; \
	  $(SED) 's,-R$$$$libdir,,g' $$$$i ; \
	done
	$(SED) 's,/usr/share/build-1,$(STAGING_DIR)/usr/share/build-1,g' $(1)/usr/share/build-1/apr_rules.mk
endef

define Package/libapr/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libapr.so.* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libapr))
