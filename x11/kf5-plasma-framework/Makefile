PORTNAME=	plasma-framework
DISTVERSION=	${KDE_FRAMEWORKS_VERSION}
PORTREVISION=	1
CATEGORIES=	x11 kde kde-frameworks

MAINTAINER=	kde@FreeBSD.org
COMMENT=	KF5 plugin based UI runtime used to write user interfaces

USES=		cmake compiler:c++11-lib gettext gl kde:5 pkgconfig qt:5 tar:xz xorg
USE_GL=		egl gl
USE_KDE=	activities archive auth codecs completion config \
		configwidgets coreaddons dbusaddons globalaccel \
		guiaddons i18n iconthemes jobwidgets kirigami2 kio package \
		notifications service solid wayland windowsystem xmlgui kdeclarative \
		widgetsaddons
USE_QT=		buildtools:build concurrent core dbus declarative gui network qmake:build \
		sql svg widgets x11extras xml
USE_XORG=	ice sm x11 xcb xext xrandr

OPTIONS_DEFINE=		DOCBOOK
OPTIONS_DEFAULT=	DOCBOOK
OPTIONS_SUB=		yes
DOCBOOK_DESC=		Doctools build

OPTIONS_EXCLUDE_aarch64c=	DOCBOOK
OPTIONS_EXCLUDE_riscv64c=	DOCBOOK

.include <bsd.port.pre.mk>

.if ${ARCH} != aarch64c && ${ARCH} != riscv64c
USE_QT+=	script
.endif

.if ${PORT_OPTIONS:MDOCBOOK}
USE_KDE+=	doctools:build
.endif

.include <bsd.port.post.mk>
