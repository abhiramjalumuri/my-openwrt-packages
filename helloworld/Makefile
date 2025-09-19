include $(TOPDIR)/rules.mk

PKG_NAME:=helloworld
PKG_VERSION:=1.0
PKG_RELEASE:=r1

include $(INCLUDE_DIR)/package.mk

define Package/helloworld
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Hello World Package
  ARCH:=all
endef

define Package/helloworld/description
  Simple Hello World C program
endef

# Copy sources to the build directory
define Build/Prepare
        mkdir -p $(PKG_BUILD_DIR)
        $(CP) ./src/* $(PKG_BUILD_DIR)/
endef

# Compile the source file
define Build/Compile
        $(TARGET_CC) $(PKG_BUILD_DIR)/helloworld.c -o $(PKG_BUILD_DIR)/helloworld
endef

# Install the compiled binary into the package
define Package/helloworld/install
        $(INSTALL_DIR) $(1)/usr/bin
        $(INSTALL_BIN) $(PKG_BUILD_DIR)/helloworld $(1)/usr/bin/
endef

$(eval $(call BuildPackage,helloworld))
