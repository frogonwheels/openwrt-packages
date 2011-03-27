#
# Copyright (C) 2007-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
# $Id: Makefile 12758 2008-09-28 09:20:20Z nbd $ 

include $(TOPDIR)/rules.mk

PKG_NAME:=apache
PKG_VERSION:=2.2.15
PKG_RELEASE:=2
PKG_SOURCE_NAME:=httpd

PKG_SOURCE:=$(PKG_SOURCE_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=http://ftp.uni-erlangen.de/pub/mirrors/apache/httpd/ \
		http://apache.imsam.info/httpd/
PKG_MD5SUM:=016cec97337eccead2aad6a7c27f2e14

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_SOURCE_NAME)-$(PKG_VERSION)

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/apache/Default
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=Web Servers/Proxies
  TITLE:=The Apache Web Server
  URL:=http://httpd.apache.org/
endef

define Package/apache
  $(call Package/apache/Default)
  MENU=1
  DEPENDS:=+libapr +libaprutil +libpcre +libopenssl
endef

define Package/apache/description
	The Apache Web Server is a powerful and flexible HTTP/1.1 compliant
	web server.  Originally designed as a replacement for the NCSA HTTP
	Server, it has grown to be the most popular web server on the Internet.
endef

define Package/apache-server
  $(call Package/apache/Default)
  TITLE:=The Apache Web Server and some tools
  DEPENDS:=+libapr +libaprutil +zlib +libexpat +libpcre +libopenssl +libsqlite3
endef

define Package/apache-mod_actions
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_actions
  DEPENDS:=+apache-server
endef

define Package/apache-mod_alias
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_alias
  DEPENDS:=+apache-server
endef

define Package/apache-mod_asis
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_asis
  DEPENDS:=+apache-server
endef

define Package/apache-mod_auth_basic
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_auth_basic
  DEPENDS:=+apache-server
endef

define Package/apache-mod_auth_digest
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_auth_digest
  DEPENDS:=+apache-server
endef

define Package/apache-mod_authn
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_authn
  DEPENDS:=+apache-server
endef

define Package/apache-mod_authn_db
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_authn_db
  DEPENDS:=+apache-server
endef

define Package/apache-mod_authz
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_authz
  DEPENDS:=+apache-server
endef

define Package/apache-mod_authz_dbm
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_authz_dbm
  DEPENDS:=+apache-server
endef

define Package/apache-mod_autoindex
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_autoindex
  DEPENDS:=+apache-server
endef

define Package/apache-mod_cache
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_cache
  DEPENDS:=+apache-server
endef

define Package/apache-mod_cern_meta
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_cern_meta
  DEPENDS:=+apache-server
endef

define Package/apache-mod_cgi
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_cgi
  DEPENDS:=+apache-server
endef

define Package/apache-mod_dav_fs
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_dav_fs
  DEPENDS:=+apache-server
endef

define Package/apache-mod_dbd
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_dbd
  DEPENDS:=+apache-server
endef

define Package/apache-mod_deflate
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_deflate
  DEPENDS:=+apache-server
endef

define Package/apache-mod_dir
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_dir
  DEPENDS:=+apache-server
endef

define Package/apache-mod_dumpio
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_dumpio
  DEPENDS:=+apache-server
endef

define Package/apache-mod_env
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_env
  DEPENDS:=+apache-server
endef

define Package/apache-mod_expires
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_expires
  DEPENDS:=+apache-server
endef

define Package/apache-mod_ext_filter
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_ext_filter
  DEPENDS:=+apache-server
endef

define Package/apache-mod_file_cache
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_file_cache
  DEPENDS:=+apache-server
endef

define Package/apache-mod_filter
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_filter
  DEPENDS:=+apache-server
endef

define Package/apache-mod_headers
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_headers
  DEPENDS:=+apache-server
endef

define Package/apache-mod_ident
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_ident
  DEPENDS:=+apache-server
endef

define Package/apache-mod_imagemap
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_imagemap
  DEPENDS:=+apache-server
endef

define Package/apache-mod_include
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_include
  DEPENDS:=+apache-server
endef

define Package/apache-mod_info
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_info
  DEPENDS:=+apache-server
endef

define Package/apache-mod_log
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_log
  DEPENDS:=+apache-server
endef

define Package/apache-mod_mem_cache
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_mem_cache
  DEPENDS:=+apache-server
endef

define Package/apache-mod_mime_magic
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_mime_magic
  DEPENDS:=+apache-server
endef

define Package/apache-mod_negotiation
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_negotiation
  DEPENDS:=+apache-server
endef

define Package/apache-mod_proxy
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_proxy
  DEPENDS:=+apache-server
endef

define Package/apache-mod_proxy_balancer
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_proxy_balancer
  DEPENDS:=+apache-server
endef

define Package/apache-mod_proxy_ajp
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_proxy_ajp
  DEPENDS:=+apache-server
endef

define Package/apache-mod_rewrite
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_rewrite
  DEPENDS:=+apache-server
endef

define Package/apache-mod_setenvif
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_setenvif
  DEPENDS:=+apache-server
endef

define Package/apache-mod_speling
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_speling
  DEPENDS:=+apache-server
endef

define Package/apache-mod_ssl
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_ssl
  DEPENDS:=+apache-server
endef

define Package/apache-mod_status
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_status
  DEPENDS:=+apache-server
endef

define Package/apache-mod_unique_id
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_unique_id
  DEPENDS:=+apache-server
endef

define Package/apache-mod_userdir
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_userdir
  DEPENDS:=+apache-server
endef

define Package/apache-mod_usertrack
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_usertrack
  DEPENDS:=+apache-server
endef

define Package/apache-mod_version
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_version
  DEPENDS:=+apache-server
endef

define Package/apache-mod_vhost_alias
  $(call Package/apache/Default)
  Title:= Module for apache server - mod_vhost_alias
  DEPENDS:=+apache-server
endef

define Package/apache-server/description
	Take care that you don't include apache at the moment into your image
	please select it only as module because busybox will override
	/usr/sbin/httpd. It'll be solved soon. If you need to include this
	package in the image anyway, remove httpd from busybox
	(Base system --> Configuration --> Networking Utilities --> httpd).
	Also you should take care for the initscripts, apache's httpd isn't
	compatible with the one from busybox, so if you want to use apache
	for running your webif, you'll need to change the parameters in the
	scripts and configure the rest in /etc/httpd.conf.
endef

define Package/apache-mod_actions/description
	Apache Modules: mod_actions
		mod_actions.so
endef

define Package/apache-mod_alias/description
	Apache Modules: mod_alias
		mod_alias.so
endef

define Package/apache-mod_asis/description
	Apache Modules: mod_asis
		mod_asis.so
endef

define Package/apache-mod_auth_basic/description
	Apache Modules: mod_auth_basic
		mod_auth_basic.so
endef

define Package/apache-mod_auth_digest/description
	Apache Modules: mod_auth_digest
		mod_auth_digest.so
endef

define Package/apache-mod_authn/description
	Apache Modules: mod_authn
		mod_authn_anon.so
		mod_authn_default.so
		mod_authn_file.so
endef

define Package/apache-mod_authn_db/description
	Apache Modules: mod_authn_db*
		mod_authn_dbd.so
		mod_authn_dbm.so
endef

define Package/apache-mod_authz/description
	Apache Modules: mod_authz
		mod_authz_default.so
		mod_authz_groupfile.so
		mod_authz_host.so
		mod_authz_owner.so
		mod_authz_user.so
endef

define Package/apache-mod_authz_dbm/description
	Apache Modules: mod_authz_dbm
		mod_authz_dbm.so
endef

define Package/apache-mod_autoindex/description
	Apache Modules: mod_autoindex
		mod_autoindex.so
endef

define Package/apache-mod_cache/description
	Apache Modules: mod_cache
		mod_cache.so
endef

define Package/apache-mod_cern_meta/description
	Apache Modules: mod_cern_meta
		mod_cern_meta.so
endef

define Package/apache-mod_cgi/description
	Apache Modules: mod_cgi
		mod_cgid.so
endef

define Package/apache-mod_dav_fs/description
	Apache Modules: mod_dav_fs
		mod_dav_fs.so
		mod_dav.so
endef

define Package/apache-mod_dbd/description
	Apache Modules: mod_dbd
		mod_dbd.so
endef

define Package/apache-mod_deflate/description
	Apache Modules: mod_deflate
		mod_deflate.so
endef

define Package/apache-mod_dir/description
	Apache Modules: mod_dir
		mod_dir.so
endef

define Package/apache-mod_dumpio/description
	Apache Modules: mod_dumpio
		mod_dumpio.so
endef

define Package/apache-mod_env/description
	Apache Modules: mod_env
		mod_env.so
endef

define Package/apache-mod_expires/description
	Apache Modules: mod_expires
		mod_expires.so
endef

define Package/apache-mod_ext_filter/description
	Apache Modules: mod_ext_filter
		mod_ext_filter.so
endef

define Package/apache-mod_file_cache/description
	Apache Modules: mod_file_cache
		mod_file_cache.so
endef

define Package/apache-mod_filter/description
	Apache Modules: mod_filter
		mod_filter.so
endef

define Package/apache-mod_headers/description
	Apache Modules: mod_headers
		mod_headers.so
endef

define Package/apache-mod_ident/description
	Apache Modules: mod_ident
		mod_ident.so
endef

define Package/apache-mod_imagemap/description
	Apache Modules: mod_imagemap
		mod_imagemap.so
endef

define Package/apache-mod_include/description
	Apache Modules: mod_include
		mod_include.so
endef

define Package/apache-mod_info/description
	Apache Modules: mod_info
		mod_info.so
endef

define Package/apache-mod_log/description
	Apache Modules: mod_log
		mod_log_config.so
		mod_log_forensic.so
		mod_logio.so
endef

define Package/apache-mod_mem_cache/description
	Apache Modules: mod_mem_cache
		mod_mem_cache.so
endef

define Package/apache-mod_mime_magic/description
	Apache Modules: mod_mime
		mod_mime.so
		mod_mime_magic.so
endef

define Package/apache-mod_negotiation/description
	Apache Modules: mod_negotiation
		mod_negotiation.so
endef

define Package/apache-mod_proxy/description
	Apache Modules: mod_proxy
		mod_proxy_connect.so
		mod_proxy_ftp.so
		mod_proxy_http.so
		mod_proxy.so
endef

define Package/apache-mod_proxy_balancer/description
	Apache Modules: mod_proxy_balancer
		mod_proxy_balancer.so
endef

define Package/apache-mod_proxy_ajp/description
	Apache Modules: mod_proxy_ajp
		mod_proxy_ajp.so
endef

define Package/apache-mod_rewrite/description
	Apache Modules: mod_rewrite
		mod_rewrite.so
endef

define Package/apache-mod_setenvif/description
	Apache Modules: mod_setenvif
		mod_setenvif.so
endef

define Package/apache-mod_speling/description
	Apache Modules: mod_speling
		mod_speling.so
endef

define Package/apache-mod_ssl/description
	Apache Modules: mod_ssl
		mod_ssl.so
endef

define Package/apache-mod_status/description
	Apache Modules: mod_status
		mod_status.so
endef

define Package/apache-mod_unique_id/description
	Apache Modules: mod_unique_id
		mod_unique_id.so
endef

define Package/apache-mod_userdir/description
	Apache Modules: mod_userdir
		mod_userdir.so
endef

define Package/apache-mod_usertrack/description
	Apache Modules: mod_usertrack
		mod_usertrack.so
endef

define Package/apache-mod_version/description
	Apache Modules: mod_version
		mod_version.so
endef

define Package/apache-mod_vhost_alias/description
	Apache Modules: mod_vhost_alias
		mod_vhost_alias.so
endef

#/etc/apache/httpd.conf
define Package/apache-server/conffiles
/etc/apache/extra/httpd-autoindex.conf
/etc/apache/extra/httpd-dav.conf
/etc/apache/extra/httpd-default.conf
/etc/apache/extra/httpd-info.conf
/etc/apache/extra/httpd-languages.conf
/etc/apache/extra/httpd-manual.conf
/etc/apache/extra/httpd-mpm.conf
/etc/apache/extra/httpd-multilang-errordoc.conf
/etc/apache/extra/httpd-ssl.conf
/etc/apache/extra/httpd-userdir.conf
/etc/apache/extra/httpd-vhosts.conf
/etc/apache/magic
/etc/apache/mime.types
endef

define Package/apache-icons
  $(call Package/apache/Default)
  TITLE:=Icons from Apache
#  DEPENDS:=apache
endef

define Package/apache-icons/description
  $(call Package/apache/description)
  This package contains the icons from Apache.
endef

APACHE_MPM=worker

define Build/Compile/apache-server
	#	--with-mpm=$(APACHE_MPM) 
	echo Compiling apache server
	$(MAKE) -C $(PKG_BUILD_DIR) \
		DESTDIR="$(PKG_INSTALL_DIR)" \
		all install
	# if you need docs take a look into the build-dir :)
	rm -rf	$(PKG_INSTALL_DIR)/ser/usr/man/ \
		$(PKG_INSTALL_DIR)/usr/share/manual/
endef

define Build/Compile
	$(call Build/Compile/apache-server)
endef

define Build/Configure
	$(call Build/Configure/Default, \
		--with-apr="$(STAGING_DIR)/usr/bin/apr-1-config" \
		--with-apr-util="$(STAGING_DIR)/usr/bin/apu-1-config" \
		--with-pcre="$(STAGING_DIR)/usr/bin/pcre-config" \
		--enable-http \
		--enable-ssl \
		--enable-proxy \
		--enable-layout=GNU \
		--with-mpm=$(APACHE_MPM) \
		--enable-mods-shared=all \
		--enable-cache \
		--enable-file-cache \
		--disable-disk-cache \
		--enable-mem-cache \
		--enable-deflate \
		--enable-maintainer-mode \
		--enable-mime-magic \
		--without-suexec-bin \
		--sysconfdir=/etc/apache \
		ap_cv_void_ptr_lt_long=no \
		logfiledir="/var/log" \
	)
endef

define Build/InstallDev
	rm -rf	$(PKG_INSTALL_DIR)/usr/man/ \
		$(PKG_INSTALL_DIR)/usr/share/manual/
	# if you need docs take a look into the build-dir :)
	$(INSTALL_DIR) $(1)/etc
	$(CP)   $(PKG_INSTALL_DIR)/etc/* \
		$(1)/etc
	$(INSTALL_DIR) $(1)/usr/include/apache2

	$(CP)	$(PKG_INSTALL_DIR)/usr/include/apache2/* \
		$(1)/usr/include/apache2
	$(INSTALL_DIR) $(1)/usr/lib

	$(CP)   $(PKG_INSTALL_DIR)/usr/lib/httpd.exp \
		$(1)/usr/lib
	$(INSTALL_DIR) $(1)/usr/sbin
	$(CP)   $(PKG_INSTALL_DIR)/usr/sbin/* \
		$(1)/usr/sbin
	$(INSTALL_DIR) $(1)/usr/share
	$(CP)   $(PKG_INSTALL_DIR)/usr/share/* \
		$(1)/usr/share
	$(SED) 's,/usr/share/build,$(STAGING_DIR)/usr/share/build,g' \
		$(1)/usr/sbin/apxs
	$(INSTALL_DIR) $(1)/usr/share/build
	$(CP)   $(PKG_INSTALL_DIR)/usr/share/build/* \
		$(1)/usr/share/build || true
	$(SED) 's!^\([a-z_]\+ = \)/usr!\1$(STAGING_DIR)/usr!' \
		$(1)/usr/share/build/config_vars.mk
	$(SED) 's!^\(AP[RU]_CONFIG = \)/usr!\1$(STAGING_DIR)/usr!' \
		$(1)/usr/share/build/config_vars.mk
endef

define Package/apache-server/preinst
	rm /usr/sbin/httpd
	echo -e "You should take a look in the initscripts, busybox's httpd \n\
	uses some parameters which are maybe unsupported by apache."
endef

define Package/apache-server/install
	$(INSTALL_DIR) $(1)/usr/sbin
	# we don't need apxs on the router, it's just for building apache modules.
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/{ab,apachectl,checkgid,dbmmanage,envvars,envvars-std,htcacheclean,htdbm,htdigest,htpasswd,httpd,httxt2dbm,logresolve,rotatelogs} $(1)/usr/sbin/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP)	$(PKG_INSTALL_DIR)/usr/lib/httpd.exp \
		$(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/share
	$(CP) $(PKG_INSTALL_DIR)/usr/share/{error,htdocs,cgi-bin,build} \
		$(1)/usr/share/
	$(INSTALL_DIR) $(1)/etc/apache
	$(CP) $(PKG_INSTALL_DIR)/etc/apache/{magic,mime.types,extra} \
		$(1)/etc/apache/
endef
#	$(CP) ./files/etc/apache/httpd.conf \ $(1)/etc/apache/

define Package/apache-mod_actions/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_actions.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_alias/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_alias.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_asis/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_asis.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_auth_basic/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_auth_basic.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_auth_digest/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_auth_digest.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_authn/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_authn_anon.so $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_authn_default.so $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_authn_file.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_authn_db/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_authn_dbd.so $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_authn_dbm.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_authz/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_authz_default.so $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_authz_groupfile.so $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_authz_host.so $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_authz_owner.so $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_authz_user.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_authz_dbm/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_authz_dbm.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_autoindex/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_autoindex.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_cache/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_cache.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_cern_meta/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_cern_meta.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_cgi/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_cgi*.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_dav_fs/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_dav_fs.so $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_dav.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_dbd/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_dbd.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_deflate/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_deflate.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_dir/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_dir.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_dumpio/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_dumpio.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_env/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_env.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_expires/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_expires.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_ext_filter/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_ext_filter.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_file_cache/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_file_cache.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_filter/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_filter.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_headers/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_headers.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_ident/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_ident.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_imagemap/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_imagemap.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_include/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_include.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_info/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_info.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_log/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_log_config.so $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_log_forensic.so $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_logio.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_mem_cache/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_mem_cache.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_mime_magic/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_mime_magic.so $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_mime.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_negotiation/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_negotiation.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_proxy/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_proxy_connect.so $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_proxy_ftp.so $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_proxy_http.so $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_proxy.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_proxy_balancer/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_proxy_balancer.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_proxy_ajp/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_proxy_ajp.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_rewrite/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_rewrite.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_setenvif/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_setenvif.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_speling/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_speling.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_ssl/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_ssl.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_status/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_status.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_unique_id/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_unique_id.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_userdir/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_userdir.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_usertrack/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_usertrack.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_version/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_version.so $(1)/usr/share/apache2/
endef

define Package/apache-mod_vhost_alias/install
	$(INSTALL_DIR) $(1)/usr/share/apache2/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/mod_vhost_alias.so $(1)/usr/share/apache2/
endef

define Package/apache-server/postrm
	rm -rf /usr/sbin/httpd
	ln -s /bin/busybox /usr/sbin/httpd
	echo -e "You may need to change your initscripts back for the use \n\
		with busybox's httpd."
endef

define Package/apache-icons/install
	$(INSTALL_DIR) $(1)/usr/share
	$(INSTALL_DIR) $(1)/usr/share/icons
	$(CP) $(PKG_INSTALL_DIR)/usr/share/icons/* $(1)/usr/share/icons
endef

$(eval $(call BuildPackage,apache))
$(eval $(call BuildPackage,apache-server))
$(eval $(call BuildPackage,apache-icons))
$(eval $(call BuildPackage,apache-mod_actions))
$(eval $(call BuildPackage,apache-mod_alias))
$(eval $(call BuildPackage,apache-mod_asis))
$(eval $(call BuildPackage,apache-mod_auth_basic))
$(eval $(call BuildPackage,apache-mod_auth_digest)) 
$(eval $(call BuildPackage,apache-mod_authn)) 
$(eval $(call BuildPackage,apache-mod_authn_db)) 
$(eval $(call BuildPackage,apache-mod_authz)) 
$(eval $(call BuildPackage,apache-mod_authz_dbm)) 
$(eval $(call BuildPackage,apache-mod_autoindex)) 
$(eval $(call BuildPackage,apache-mod_cache)) 
$(eval $(call BuildPackage,apache-mod_cern_meta))
$(eval $(call BuildPackage,apache-mod_cgi))
$(eval $(call BuildPackage,apache-mod_dav_fs))
$(eval $(call BuildPackage,apache-mod_dbd))
$(eval $(call BuildPackage,apache-mod_deflate))
$(eval $(call BuildPackage,apache-mod_dir))
$(eval $(call BuildPackage,apache-mod_dumpio))
$(eval $(call BuildPackage,apache-mod_env))
$(eval $(call BuildPackage,apache-mod_expires))
$(eval $(call BuildPackage,apache-mod_ext_filter))
$(eval $(call BuildPackage,apache-mod_file_cache))
$(eval $(call BuildPackage,apache-mod_filter))
$(eval $(call BuildPackage,apache-mod_headers))
$(eval $(call BuildPackage,apache-mod_ident))
$(eval $(call BuildPackage,apache-mod_imagemap))
$(eval $(call BuildPackage,apache-mod_include))
$(eval $(call BuildPackage,apache-mod_info))
$(eval $(call BuildPackage,apache-mod_log))
$(eval $(call BuildPackage,apache-mod_mem_cache))
$(eval $(call BuildPackage,apache-mod_mime_magic))
$(eval $(call BuildPackage,apache-mod_negotiation))
$(eval $(call BuildPackage,apache-mod_proxy))
$(eval $(call BuildPackage,apache-mod_proxy_balancer))
$(eval $(call BuildPackage,apache-mod_proxy_ajp))
$(eval $(call BuildPackage,apache-mod_rewrite))
$(eval $(call BuildPackage,apache-mod_setenvif))
$(eval $(call BuildPackage,apache-mod_speling))
$(eval $(call BuildPackage,apache-mod_ssl))
$(eval $(call BuildPackage,apache-mod_status))
$(eval $(call BuildPackage,apache-mod_unique_id))
$(eval $(call BuildPackage,apache-mod_userdir))
$(eval $(call BuildPackage,apache-mod_usertrack))
$(eval $(call BuildPackage,apache-mod_version)) 
$(eval $(call BuildPackage,apache-mod_vhost_alias))

