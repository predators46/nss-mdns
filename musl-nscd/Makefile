include $(TOPDIR)/rules.mk

PKG_NAME:=musl-nscd
PKG_VERSION:=1.1.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/pikhq/musl-nscd/tar.gz/v$(PKG_VERSION)?
PKG_HASH:=1e25aa28be11b591d46bb20afcbe7c4005a038e8ab150bc69963f0b25e7924f5

PKG_MAINTAINER:=Andy Syam <privasisource@gmail.com>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=COPYRIGHT

PKG_INSTALL:=1
PKG_FIXUP:=autoreconf
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/musl-nscd
  SECTION:=net
  CATEGORY:=Network
  TITLE:=musl-nscd is an implementation of the NSCD protocol
  URL:=https://github.com/pikhq/musl-nscd
endef

define Package/musl-nscd/description
musl-nscd is an implementation of the NSCD protocol. It makes use of NSS
modules, just like with glibc. This permits alternative backends for the user
and group databases for musl libc. The protocol it uses is a subset of that
used by glibc. This project was created with the help of Contauro Ltd.
Configuration of which modules to use should be given in /etc/nsswitch.conf.
The syntax of the file matches glibc.
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/nss.h $(1)/usr/include/
endef

define Package/musl-nscd/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/nscd $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,musl-nscd))
