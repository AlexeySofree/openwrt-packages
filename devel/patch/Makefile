#
# Copyright (C) 2008-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=patch
PKG_VERSION:=2.7.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=@GNU/patch
PKG_MD5SUM:=95dd8d7e41dcbcecdd5cd88ef915378d

include $(INCLUDE_DIR)/package.mk

define Package/patch
  SECTION:=devel
  CATEGORY:=Development
  TITLE:=patch
  URL:=http://www.gnu.org/
  MAINTAINER:=Russell Senior <russell@personaltelco.net>
endef

define Package/patch/description
  The Patch package contains a program for modifying or creating files
  by applying a "patch" file typically created by the diff program.
endef

CONFIGURE_ARGS+= --disable-xattr

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR) \
		DESTDIR="$(PKG_INSTALL_DIR)" \
		all install
endef

define Package/patch/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/patch $(1)/usr/bin/
endef

$(eval $(call BuildPackage,patch))
