#
# Copyright (C) 2006-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=yaddns
PKG_VERSION:=1.1-rc2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://download.gna.org/yaddns/
PKG_MD5SUM:=919a25bd66abf926e049f3afea619e19

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/yaddns
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=IP Addresses and Names
  TITLE:=Yet Another DDNS client
  URL:=http://patatrac.info/yaddns
endef

define Package/yaddns/description
Yaddns is a small ddns client with multiple ddns server supports (dyndns, ...)
and a high flexibility. Yaddns is particularly appropriate for embedded systems.
endef

define Package/yaddns/conffiles
/etc/config/ddns
endef

define Package/yaddns/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/yaddns $(1)/usr/bin/
	$(CP) ./files/* $(1)/
endef

$(eval $(call BuildPackage,yaddns))
