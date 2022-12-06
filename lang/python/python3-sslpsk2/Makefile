include $(TOPDIR)/rules.mk

PKG_NAME:=python3-sslpsk2
PKG_VERSION:=1.0.2
PKG_RELEASE:=1

PKG_SOURCE:=sslpsk2-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/dd/12/ea5d04f8a637ae13e64a761cfbfc3091446c1500515b64bfe573c29960b3/
PKG_HASH:=8498d7625389f21fa1d1ab9fa68a5a44860a66b3ef50534e70d19f3ca8a510cd

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-sslpsk2-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-sslpsk2/Default
  SECTION:=lang-python
  CATEGORY:=Languages
  SUBMENU:=Python
  URL:=https://github.com/autinerd/sslpsk2
endef

define Package/python3-sslpsk2
$(call Package/python-sslpsk2/Default)
  TITLE:=python3-sslpsk2
  DEPENDS:=+python3-openssl +PACKAGE_python3-sslpsk2:python3
  VARIANT:=python3
endef

define Package/python-sslpsk2/description
This module adds TLS-PSK support to the Python 2.7 and 3.x ssl package.
endef

define Package/python3-sslpsk2/description
$(call Package/python-sslpsk2/description)
.
(Variant for Python3)
endef

define Py3Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --prefix=/usr --root=$(PKG_INSTALL_DIR),\
		CONFIG_BIG_ENDIAN="$(CONFIG_BIG_ENDIAN)" \
	)
endef

$(eval $(call Py3Package,$(PKG_NAME)))
$(eval $(call BuildPackage,$(PKG_NAME)))
$(eval $(call BuildPackage,$(PKG_NAME)-src))

