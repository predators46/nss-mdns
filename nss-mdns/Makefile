include $(TOPDIR)/rules.mk

PKG_NAME:=nss-mdns
PKG_VERSION:=0.15.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/avahi/nss-mdns/tar.gz/v$(PKG_VERSION)?
PKG_HASH:=2d1b8de2e9ed5526f51c8bb627b719c07668465b5315787e7cfeed776ab90b9a

PKG_MAINTAINER:=Andy Syam <privasisource@gmail.com>
PKG_LICENSE:=LGPL-2.1 license
PKG_LICENSE_FILES:=LICENSE

PKG_INSTALL:=1
PKG_FIXUP:=autoreconf
PKG_BUILD_DEPENDS:=musl-nscd
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/nss-mdns
  SECTION:=net
  CATEGORY:=Network
  TITLE:=NSS module for Multicast DNS name resolution
  URL:=https://github.com/avahi/nss-mdns
endef

define Package/nss-mdns/description
nss-mdns is a plugin for the GNU Name Service Switch (NSS)
functionality of the GNU C Library (glibc)
providing host name resolution via Multicast 
DNS (using Zeroconf, aka Apple Bonjour / Apple Rendezvous )
effectively allowing name resolution by common Unix/Linux programs in the ad-hoc mDNS domain .local.
endef

define Package/nss-mdns/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,nss-mdns))
