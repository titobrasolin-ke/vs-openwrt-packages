include $(TOPDIR)/rules.mk

PKG_NAME:=python3-dill
PKG_VERSION:=0.3.6
PKG_RELEASE:=$(AUTORELEASE)

PYPI_NAME:=dill
PKG_HASH:=e5db55f3687856d8fbdab002ed78544e1c4559a130302693d839dfe8f93f2373

include $(TOPDIR)/feeds/packages/lang/python/pypi.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

define Package/python3-dill
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=serialize all of python
  URL:=https://github.com/uqfoundation/dill
  DEPENDS:=+python3-light
endef

define Package/python3-dill/description
serialize all of python
endef

$(eval $(call Py3Package,$(PKG_NAME)))
$(eval $(call BuildPackage,$(PKG_NAME)))
$(eval $(call BuildPackage,$(PKG_NAME)-src))
