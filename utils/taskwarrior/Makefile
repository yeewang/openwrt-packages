#
# Copyright (C) 2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=taskwarrior
PKG_VERSION:=2.3.0
PKG_RELEASE:=1

PKG_SOURCE:=task-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://www.taskwarrior.org/download/
PKG_MD5SUM:=2c1d2c64311855f3519ad038ebd372ac

PKG_INSTALL:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/task-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/taskwarrior
  TITLE:=taskwarrior
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:=+libncurses +libstdcpp +liblua +libuuid +libreadline +libgnutls
  URL:=http://taskwarrior.org/projects/show/taskwarrior
  MAINTAINER:=Xiangfu Liu <xiangfu@sharism.cc>
endef

TARGET_LDFLAGS += -ldl

define Package/taskwarrior/description
 taskwarrior is a command-line todo list manager
endef

define Package/taskwarrior/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/task $(1)/usr/bin/
endef

$(eval $(call BuildPackage,taskwarrior))
