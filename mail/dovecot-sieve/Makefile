#
# Copyright (C) 2006-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=dovecot-sieve
PKG_VERSION:=0.1.19
PKG_VERSION_DOVECOT:=1.2
PKG_RELEASE:=1

#PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
#PKG_SOURCE_URL:=http://www.dovecot.org/releases/sieve/

PKG_SOURCE:=dovecot-$(PKG_VERSION_DOVECOT)-sieve-$(PKG_VERSION).tar.gz
PKG_BUILD_DIR:=$(BUILD_DIR)/dovecot-$(PKG_VERSION_DOVECOT)-sieve-$(PKG_VERSION)
PKG_SOURCE_URL:=http://www.rename-it.nl/dovecot/1.2/
PKG_MD5SUM:=-

PKG_FIXUP:=libtool
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/dovecot-sieve
  SECTION:=mail
  CATEGORY:=Mail
  DEPENDS:=+dovecot
  TITLE:=Sieve plugin for Dovecot
  URL:=http://www.dovecot.org/
endef

define Package/dovecot-sieve/description
 Dovecot-sieve is a filter module for Dovecot
endef

TARGET_CFLAGS += $(FPIC)


CONFIGURE_ARGS += \
	--with-notify \
        --with-dovecot=../dovecot-1.2.17

define Build/Configure
	(cd $(PKG_BUILD_DIR); rm -rf config.{cache,status}; \
		autoconf \
	);
	$(call Build/Configure/Default)
endef
		

define Package/dovecot-sieve/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/sievec $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/sieved $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/sieve-test $(1)/usr/bin
	$(INSTALL_DIR) $(1)/usr/lib/dovecot/modules/lda
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/dovecot/modules/lda/* $(1)/usr/lib/dovecot/modules/lda
endef

$(eval $(call BuildPackage,dovecot-sieve))
