# 
# Copyright (C) 2007-2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=lua-leveldb
PKG_VERSION:=0.5
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/marcopompili/lua-leveldb#0.4
PKG_MIRROR_HASH:=333333333333333333333333333333333333333333333333
PKG_SOURCE_VERSION:=acefd7e2e17cad1a8d9a106d7468d9a6da1d3b1b
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/lua-leveldb
  SUBMENU:=Lua
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=A LUA-library of routines to manage LevelDB
  URL:=https://code.google.com/p/leveldb/
  DEPENDS:=+leveldb
  MAINTAINER:=Obinou <obconseil@gmail.com>
  DEFAULT:=y
endef

define Package/lua-leveldb/Default/description
A fast and lightweight key/value database library
endef

PKG_FIXUP:=autoreconf

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(TAR) -xzf $(DL_DIR)/$(PKG_SOURCE) --strip=1 -C $(PKG_BUILD_DIR)
	/usr/bin/autoreconf -fiv $(PKG_BUILD_DIR)
endef
    
define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR)
	$(MAKE) -C $(PKG_BUILD_DIR) DESTDIR="$(PKG_INSTALL_DIR)" install
endef

define Build/InstallDev
	$(MAKE) -C $(PKG_BUILD_DIR) DESTDIR="$(1)" install
endef

define Package/lua-leveldb/install
	$(INSTALL_DIR)  $(1)/usr/lib/
endef

$(eval $(call BuildPackage,lua-leveldb))
