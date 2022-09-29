PORTNAME=	kio
DISTVERSION=	${KDE_FRAMEWORKS_VERSION}
PORTREVISION=	1
CATEGORIES=	devel kde kde-frameworks

MAINTAINER=	kde@FreeBSD.org
COMMENT=	KF5 resource and network access abstraction

USES=		cmake compiler:c++11-lib \
		gettext kde:5 cpe qt:5 ssl tar:xz xorg
USE_GNOME=	libxml2 libxslt
USE_KDE=	archive auth bookmarks codecs completion config \
		configwidgets coreaddons crash dbusaddons guiaddons \
		i18n iconthemes itemviews jobwidgets kded \
		notifications service solid sonnet textwidgets wallet \
		widgetsaddons windowsystem xmlgui \
		ecm:build
USE_QT=		concurrent core dbus declarative gui network \
		widgets x11extras xml \
		buildtools:build qmake:build testlib:build
USE_XORG=	x11

OPTIONS_DEFINE=		DOCBOOK
OPTIONS_DEFAULT=	DOCBOOK
OPTIONS_SUB=		yes
DOCBOOK_DESC=		Doctools build

OPTIONS_EXCLUDE_aarch64c=	DOCBOOK
OPTIONS_EXCLUDE_riscv64c=	DOCBOOK

.include <bsd.port.pre.mk>

.if ${ARCH} != aarch64c && ${ARCH} != riscv64c
USES+=		desktop-file-utils gnome
USE_QT+=	script
.endif

.if ${PORT_OPTIONS:MDOCBOOK}
USE_KDE+=	doctools:build
.endif

.include <bsd.port.post.mk>
