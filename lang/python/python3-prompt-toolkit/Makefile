include $(TOPDIR)/rules.mk

PKG_NAME:=python3-prompt-toolkit
PKG_VERSION:=3.0.36
PKG_RELEASE:=1

PKG_SOURCE:=prompt_toolkit-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/fb/93/180be2342f89f16543ec4eb3f25083b5b84eba5378f68efff05409fb39a9/
PKG_HASH:=3e163f254bef5a03b146397d7c1963bd3e2812f0964bb9a24e6ec761fd28db63

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-prompt-toolkit-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-prompt-toolkit/Default
  SECTION:=lang-python
  CATEGORY:=Languages
  SUBMENU:=Python
  https://github.com/prompt-toolkit/python-prompt-toolkit
endef

define Package/python3-prompt-toolkit
$(call Package/python-prompt-toolkit/Default)
  TITLE:=python3-prompt-toolkit
  DEPENDS:=+PACKAGE_python3-prompt-toolkit:python3
  VARIANT:=python3
endef

define Package/python-prompt-toolkit/description
Library for powerful interactive command line applications in Python.
endef

define Package/python3-prompt-toolkit/description
$(call Package/python-prompt-toolkit/description)
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

