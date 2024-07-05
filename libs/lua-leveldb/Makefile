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

define Build/Compile
  $(call Build/Compile/Default)
endef

define Package/lua-leveldb/install
	$(INSTALL_DIR)  $(1)/usr/lib/
endef

$(eval $(call BuildPackage,lua-leveldb))
