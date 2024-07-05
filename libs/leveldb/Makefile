include $(TOPDIR)/rules.mk

PKG_NAME:=leveldb
PKG_VERSION:=1.22
PKG_RELEASE:=1
PKG_INSTALL:=1

PKG_SOURCE:=$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/google/leveldb/archive/refs/tags/
PKG_MD5SUM:=e1dbde14dcda1b58b49f0c214464fdd9
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/leveldb/Default
  SUBMENU:=database
  TITLE:=(leveldb)A key/value database library
  URL:=https://code.google.com/p/leveldb/
  MAINTAINER:=code.google.com
endef

define Package/leveldb
  DEPENDS:=+snappy
  SECTION:=libs
  CATEGORY:=Libraries
  SUBMENU:=database
  TITLE:=A fast and lightweight key/value database library
  URL:=https://code.google.com/p/leveldb/
  DEPENDS:=+libstdcpp +libpthread
  DEFAULT:=y
endef

CMAKE_OPTIONS += \
    -DCMAKE_BUILD_TYPE=Release \
    -DBUILD_SHARED_LIBS=ON

TARGET_CFLAGS += \
    -D_GLIBCXX_USE_C99

define Package/leveldb/Default/description
A fast and lightweight key/value database library
endef

define Build/Compile
  $(call Build/Compile/Default)
endef

define Package/leveldb/install
  $(MAKE) $(PKG_JOBS) -C $(PKG_BUILD_DIR) DESTDIR="$(1)" install
endef

$(eval $(call BuildPackage,leveldb))
