#
# Copyright (C) 2023 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=docker-ubus
PKG_VERSION:=0.0.1
PKG_RELEASE:=1

PKG_MAINTAINER:=Sergey Ponomarev <stokito@gmail.com>
PKG_LICENSE:=Apache-2.0

include $(INCLUDE_DIR)/package.mk

define Package/docker-ubus
  SECTION:=utils
  CATEGORY:=Utilities
  SUBMENU:=Containers
  TITLE:=UBUS bridge to Docker
  DEPENDS:=+curl
endef

define Package/docker-ubus/description
  UBUS bridge to Docker
endef

define Package/docker-ubus/conffiles
endef

define Build/Compile
endef

define Build/Install
endef

define Package/docker-ubus/postinst
#!/bin/sh
[ -z "$${IPKG_INSTROOT}" ] && /etc/init.d/rpcd restart
exit 0
endef

define Package/docker-ubus/postrm
#!/bin/sh
[ -z "$${IPKG_INSTROOT}" ] && /etc/init.d/rpcd restart
exit 0
endef

define Package/docker-ubus/install
	$(INSTALL_DIR) $(1)/usr/libexec/rpcd
	$(INSTALL_BIN) ./files/usr/libexec/rpcd/docker $(1)/usr/libexec/rpcd/
endef

$(eval $(call BuildPackage,docker-ubus))
