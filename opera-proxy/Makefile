include $(TOPDIR)/rules.mk

PKG_NAME:=opera-proxy
PKG_VERSION:=1.14.0
PKG_RELEASE:=1
PKG_LICENSE:=MIT
PKG_MAINTAINER:=Snawoot <vladislav-ex-gh@vm-0.com>

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Opera Proxy client
  URL:=https://github.com/Snawoot/opera-proxy
endef

# Эти блоки должны быть пустыми, так как мы подкладываем готовый бинарник
define Build/Prepare
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/$(PKG_NAME)/install
	# Установка скрипта инициализации
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) $(CURDIR)/files/etc/init.d/opera-proxy $(1)/etc/init.d/opera-proxy

	# Установка самого бинарника
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(CURDIR)/files/usr/bin/opera-proxy $(1)/usr/bin/opera-proxy

	# Установка конфига
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_CONF) $(CURDIR)/files/etc/config/opera-proxy $(1)/etc/config/opera-proxy
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
