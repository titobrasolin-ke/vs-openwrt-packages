include $(TOPDIR)/rules.mk

PKG_NAME:=python3-prompt-toolkit
PKG_VERSION:=3.0.36
PKG_RELEASE:=$(AUTORELEASE)

PYPI_NAME:=prompt_toolkit
PKG_HASH:=3e163f254bef5a03b146397d7c1963bd3e2812f0964bb9a24e6ec761fd28db63

include $(TOPDIR)/feeds/packages/lang/python/pypi.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

define Package/python3-prompt-toolkit
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=Library for building powerful interactive command line applications
  URL:=https://github.com/prompt-toolkit/python-prompt-toolkit
  DEPENDS:=+python3-wcwidth
endef

define Package/python3-prompt-toolkit/description
Library for building powerful interactive command line applications
endef

$(eval $(call Py3Package,$(PKG_NAME)))
$(eval $(call BuildPackage,$(PKG_NAME)))
$(eval $(call BuildPackage,$(PKG_NAME)-src))
