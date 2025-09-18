# Include OpenWrt build system rules
include $(TOPDIR)/rules.mk

# Package info
PKG_NAME:=helloworld
PKG_VERSION:=1.0
PKG_RELEASE:=1

# Include standard package definitions
include $(INCLUDE_DIR)/package.mk

# Package metadata
define Package/helloworld
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Hello World Program
endef

define Package/helloworld/description
 A simple Hello World program for OpenWrt.
endef

# Compile step
define Build/Compile
	$(TARGET_CC) $(TARGET_CFLAGS) -o $(PKG_BUILD_DIR)/helloworld $(CURDIR)/src/helloworld.c
endef

# Install step
define Package/helloworld/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/helloworld $(1)/usr/bin/
endef

# Evaluate package
$(eval $(call BuildPackage,helloworld))
