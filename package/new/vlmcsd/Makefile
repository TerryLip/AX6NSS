include $(TOPDIR)/rules.mk

PKG_NAME:=vlmcsd
PKG_RELEASE:=6

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/Wind4/vlmcsd.git
PKG_SOURCE_DATE:=2020-03-30
PKG_SOURCE_VERSION:=e599080486478e219cd065e141d6de050a450c27
PKG_MIRROR_HASH:=0daa66c27aa917db13b26d444f04d73ea16925ef021405f5dd6e11ff9f9d034f

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=fuyumi <280604399@qq.com>

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/vlmcsd
  SECTION:=net
  CATEGORY:=Network
  TITLE:=vlmcsd for OpenWRT
  DEPENDS:=+libpthread
endef

define Package/vlmcsd/description
  vlmcsd is a KMS Emulator in C.
endef

define Build/Prepare
	$(call Build/Prepare/Default)
	rm $(PKG_BUILD_DIR)/GNUmakefile
endef

define Package/vlmcsd/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/vlmcsd $(1)/usr/bin/vlmcsd
	$(INSTALL_DIR) $(1)/etc/vlmcsd
	$(INSTALL_BIN) ./files/vlmcsd.ini $(1)/etc/vlmcsd/vlmcsd.ini
endef

$(eval $(call BuildPackage,vlmcsd))
