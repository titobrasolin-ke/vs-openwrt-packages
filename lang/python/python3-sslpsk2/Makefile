include $(TOPDIR)/rules.mk

PKG_NAME:=python3-sslpsk2
PKG_VERSION:=1.0.2
PKG_RELEASE:=$(AUTORELEASE)

PYPI_NAME:=sslpsk2
PKG_HASH:=8498d7625389f21fa1d1ab9fa68a5a44860a66b3ef50534e70d19f3ca8a510cd

include $(TOPDIR)/feeds/packages/lang/python/pypi.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

define Package/python3-sslpsk2
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=Adds TLS-PSK support to the Python ssl package
  URL:=https://github.com/autinerd/sslpsk2
  DEPENDS:=+libopenssl +python3-light
endef

define Package/python3-sslpsk2/description
Adds TLS-PSK support to the Python ssl package
endef

$(eval $(call Py3Package,$(PKG_NAME)))
$(eval $(call BuildPackage,$(PKG_NAME)))
$(eval $(call BuildPackage,$(PKG_NAME)-src))
