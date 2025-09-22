SPK_NAME = tvheadend
SPK_SHORT_VERS = 4.3
SPK_GIT_HASH = d6902132
SPK_GIT_DATE = 20250821
SPK_VERS = $(SPK_SHORT_VERS).$(SPK_GIT_DATE)
TVH_VERS = $(SPK_SHORT_VERS)~$(SPK_GIT_HASH)
SPK_REV = 44
SPK_ICON = src/tvheadend.png
DSM_UI_DIR = app

export TVH_VERS

FFMPEG_PACKAGE = ffmpeg7
PYTHON_PACKAGE = python312
SPK_DEPENDS = 'python312:$(FFMPEG_PACKAGE)'

UNSUPPORTED_ARCHS = $(OLD_PPC_ARCHS)
UNSUPPORTED_ARCHS += $(ARMv5_ARCHS)

WHEELS_PURE_PYTHON_PACKAGING_ENABLE = 1
WHEELS += src/requirements-pure.txt

DEPENDS = cross/tvheadend
DEPENDS += cross/dtv-scan-tables
DEPENDS += cross/docker-tvheadend
DEPENDS += cross/zap2epg

MAINTAINER = th0ma7
DESCRIPTION = Tvheadend is a TV streaming server and recorder for Linux, FreeBSD and Android supporting DVB-S, DVB-S2, DVB-C, DVB-T, ATSC, ISDB-T, IPTV, SAT IP and HDHomeRun as input sources. Tvheadend offers HTTP, HTSP and SAT IP streaming.
DESCRIPTION_FRE = Tvheadend est un serveur de streaming et enregistreur TV pour Linux, FreeBSD et Android prenant en charge DVB-S, DVB-S2, DVB-C, DVB-T, ATSC, ISDB-T, IPTV, SAT IP et HDHomeRun comme sources d\'entrée. Tvheadend offre le streaming HTTP, HTSP et SAT IP.
DISPLAY_NAME = Tvheadend 中文版
STARTABLE = yes
CHANGELOG = "1. Update to latest git version d6902132 as of August 21st 2025 \(Includes season and episode number to filename formatting, Add scene markers to recordings, Add age ratings on XMLTV\)<br/>2. Update zap2epg to version 4.1<br/>3. Include new gracenote2epg grabber v1.5.1<br/>4. 内置简体中文界面"
HOMEPAGE = https://tvheadend.org/
LICENSE = GPL v3

CONF_DIR = src/conf/
SERVICE_USER = auto
SERVICE_SETUP = src/service-setup.sh
SERVICE_PORT = 9981
SERVICE_PORT_TITLE = Tvheadend (HTTP)
ADMIN_PORT = ${SERVICE_PORT}

# ---- 中文文件复制 ----
tvheadend_post_install:
	cp files/tvh.zh-Hans.js.gz \
		$(INSTALL_DIR)/share/tvheadend/src/webui/static/intl/tvh.zh-Hans.js.gz

include ../../mk/spksrc.python.mk
CONFIGURE_ARGS += -DCMAKE_DISABLE_FIND_PACKAGE_ZLIB=ON
