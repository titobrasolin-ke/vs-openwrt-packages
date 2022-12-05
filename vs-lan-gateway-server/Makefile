include $(TOPDIR)/rules.mk

PKG_NAME:=python3-vs-lan-gateway-server
PKG_VERSION:=1.13
PKG_RELEASE:=1
PKG_SOURCE:=b2l_gateway_Demo_server_$(PKG_VERSION).zip
PKG_SOURCE_URL:=https://www.vossloh-schwabe.com/fileadmin/perfion/files
PKG_MD5SUM:=29a2b1024610e69262de900971fef3c6

UNPACK_CMD=unzip -q -o -d $(1) -j $(DL_DIR)/$(PKG_SOURCE) install_files/vs_lan_gateway_server-$(PKG_VERSION)-py3-none-any.whl

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

define Package/python3-vs-lan-gateway-server
  SUBMENU:=Domotica
  SECTION:=net
  CATEGORY:=Network
  TITLE:=An example server for the Vossloh-Schwabe LAN-Gateway
  DEPENDS:=+python3-sslpsk2
  PKGARCH:=all
  VARIANT:=python3
endef

define Package/python3-vs-lan-gateway-server/description
An example server for the Vossloh-Schwabe LAN-Gateway
endef

define Build/Prepare
	$(PKG_UNPACK)
	(cd $(PKG_BUILD_DIR) && unzip -q -o vs_lan_gateway_server-$(PKG_VERSION)-py3-none-any.whl)
	$(Build/Patch)
endef

define Build/Configure
endef

define Package/python3-vs-lan-gateway-server/conffiles
/var/vs_lan_gateway_server/config.json
endef

$(eval $(call Py3Package,$(PKG_NAME)))
$(eval $(call BuildPackage,$(PKG_NAME)))
$(eval $(call BuildPackage,$(PKG_NAME)-src))
