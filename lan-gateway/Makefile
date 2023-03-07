include $(TOPDIR)/rules.mk

PKG_NAME:=lan-gateway
PKG_VERSION:=1.15
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define Package/lan-gateway
  SUBMENU:=Domotica
  SECTION:=net
  CATEGORY:=Network
  TITLE:=An example server for the Vossloh-Schwabe LAN-Gateway
  DEPENDS:=+python3-vs-lan-gateway-server
  PKGARCH:=all
endef

define Package/lan-gateway/description
OpenWrt package for the Vossloh-Schwabe LAN-Gateway Server Demo.
endef

define Package/lan-gateway/conffiles
/etc/vs_lan_gateway_server/
/etc/config/vs_lan_gateway_server
endef

define Build/Compile
endef

define Package/lan-gateway/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/lan-gateway.init $(1)/etc/init.d/lan-gateway
	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_BIN) ./files/lan-gateway.defaults $(1)/etc/uci-defaults/lan-gateway
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
