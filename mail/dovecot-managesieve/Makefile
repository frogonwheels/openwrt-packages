#
# Copyright (C) 2006-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=dovecot-managesieve
PKG_VERSION_DOVECOT:=1.2
PKG_VERSION_DOVECOT_FULL:=1.2.17
PKG_VERSION_SIEVE=0.1.19
PKG_VERSION:=0.11.13
PKG_RELEASE:=2

PKG_SOURCE:=dovecot-$(PKG_VERSION_DOVECOT)-managesieve-$(PKG_VERSION).tar.gz
PKG_BUILD_DIR:=$(BUILD_DIR)/dovecot-$(PKG_VERSION_DOVECOT)-managesieve-$(PKG_VERSION)
PKG_SOURCE_URL:=http://www.rename-it.nl/dovecot/1.2/
PKG_MD5SUM:=-

PKG_FIXUP:=libtool
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/dovecot-managesieve
  SECTION:=mail
  CATEGORY:=Mail
  DEPENDS:=+dovecot
  TITLE:=ManageSieve plugin for Dovecot
  URL:=http://www.dovecot.org/
endef

define Package/dovecot-managesieve/description
 Dovecot-managesieve provides 'managesieve' protocol for Dovecot
endef

TARGET_CFLAGS += $(FPIC)


CONFIGURE_ARGS += \
	--with-notify \
        --with-dovecot=../dovecot-$(PKG_VERSION_DOVECOT_FULL) \
        --with-dovecot-sieve=../dovecot-$(PKG_VERSION_DOVECOT)-sieve-$(PKG_VERSION_SIEVE)

define Build/Configure
	(cd $(PKG_BUILD_DIR); rm -rf config.{cache,status}; \
		autoconf \
	);
	$(call Build/Configure/Default)
endef
		

define Package/dovecot-managesieve/install
	$(INSTALL_DIR) $(1)/usr/lib/dovecot/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/dovecot/managesieve $(1)/usr/lib/dovecot/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/dovecot/managesieve-login $(1)/usr/lib/dovecot/
endef

$(eval $(call BuildPackage,dovecot-managesieve))
