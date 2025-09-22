SPK_NAME = tvheadend
SPK_VERS = 4.3
SPK_REV = 1
SPK_ICON = src/tvheadend.png

DEPENDS  = cross/tvheadend

MAINTAINER = SynoCommunity
DESCRIPTION = TV streaming server for Linux and UNIX that supports DVB-S, DVB-S2, DVB-C, DVB-T, IPTV, and more.
DESCRIPTION_FRE = Serveur de streaming TV pour Linux et UNIX qui supporte DVB-S, DVB-S2, DVB-C, DVB-T, IPTV, et plus encore.
DISPLAY_NAME = TVHeadend
STARTABLE = yes
BETA = 1

HOMEPAGE = https://tvheadend.org
LICENSE  = GPLv3

SERVICE_USER = auto
SERVICE_SETUP = src/service-setup.sh
SERVICE_PORT = 9981

# ====== 汉化：编译后替换中文文件 ======
POST_INSTALL_TARGET = tvheadend_post_install

tvheadend_post_install:
	@echo ">>> Copy Chinese translation file"
	cp $(WORK_DIR)/files/tvh.zh-Hans.js.gz \
		$(STAGING_DIR)/share/tvheadend/src/webui/static/intl/tvh.zh-Hans.js.gz
