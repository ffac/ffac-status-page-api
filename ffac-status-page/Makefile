include $(TOPDIR)/rules.mk

PKG_NAME:=ffac-status-page
PKG_VERSION:=3

include $(TOPDIR)/../package/gluon.mk

define Package/ffac-status-page
  TITLE:=Status page showing information about the node
  DEPENDS:=+gluon-web +gluon-neighbour-info +gluon-respondd +uhttpd +sse-multiplex +libiwinfo +libjson-c +libnl-tiny +libubus-lua
  PROVIDES:=gluon-status-page
endef

define Package/ffac-status-page/install
	$(Gluon/Build/Install)

	$(INSTALL_DIR) $(1)/lib/gluon/status-page/providers
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/stations $(1)/lib/gluon/status-page/providers/

	$(INSTALL_DIR) $(1)/lib/gluon/status-page/view/
	$(LN) /lib/gluon/web/i18n $(1)/lib/gluon/status-page/
	$(LN) /lib/gluon/web/view/error $(1)/lib/gluon/status-page/view/
endef

$(eval $(call BuildPackageGluon,ffac-status-page))
