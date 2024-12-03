
include $(TOPDIR)/rules.mk

PKG_NAME:=rk-vendor-storage
PKG_VERSION:=2019-11-26
PKG_RELEASE:=1

PKG_SOURCE_VERSION:=99773aeac38b1a4928bb92e11b90350f351352ac
PKG_HASH:=d179368fe1b1801477177023e2dcd0983c66b212819a793a237ca1eb7589a1cb
PKG_SOURCE_URL_FILE:=$(PKG_SOURCE_VERSION).tar.gz
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/jjm2473/rk_vendor_storage/archive/

# PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

TAR_OPTIONS+= --strip-components 1
TAR_CMD=$(HOST_TAR) -C $(1) $(TAR_OPTIONS)

define Package/rk-vendor-storage
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Rockchip Vendor Storage Util
endef

define Build/Configure
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR) \
		CC="$(TARGET_CC)" \
		CFLAGS="$(TARGET_CFLAGS) -Wall" \
		LDFLAGS="$(TARGET_LDFLAGS)"
endef

define Package/rk-vendor-storage/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/rk_vendor_storage $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,rk-vendor-storage))
