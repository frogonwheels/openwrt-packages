#
# Copyright (C) 2009-2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libnetfilter_conntrack
PKG_VERSION:=0.9.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:= \
	http://www.netfilter.org/projects/libnetfilter_conntrack/files/ \
	ftp://ftp.netfilter.org/pub/libnetfilter_conntrack/
PKG_MD5SUM:=b7506cbb7580433859809d8eac53a199

PKG_FIXUP:=libtool

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libnetfilter-conntrack
  SECTION:=libs
  CATEGORY:=Libraries
  DEPENDS:=@!LINUX_2_4 +libnfnetlink +kmod-nf-conntrack-netlink
  TITLE:=API to the in-kernel connection tracking state table
  URL:=http://www.netfilter.org/projects/libnetfilter_conntrack/
endef

define Package/libnetfilter-conntrack/description
 libnetfilter_conntrack is a userspace library providing a programming
 interface (API) to the in-kernel connection tracking state table. The
 library libnetfilter_conntrack has been previously known as
 libnfnetlink_conntrack and libctnetlink. This library is currently
 used by conntrack-tools among many other applications.
endef

TARGET_CFLAGS += $(FPIC)

CONFIGURE_ARGS += \
	--enable-static \
	--enable-shared \

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/libnetfilter_conntrack
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/include/libnetfilter_conntrack/*.h \
		$(1)/usr/include/libnetfilter_conntrack/

	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/libnetfilter_conntrack.{so*,a,la} \
		$(1)/usr/lib/

	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/pkgconfig/libnetfilter_conntrack.pc \
		$(1)/usr/lib/pkgconfig/
endef

define Package/libnetfilter-conntrack/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/libnetfilter_conntrack.so.* \
		$(1)/usr/lib/
endef

$(eval $(call BuildPackage,libnetfilter-conntrack))
