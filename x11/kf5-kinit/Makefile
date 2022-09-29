PORTNAME=	kinit
DISTVERSION=	${KDE_FRAMEWORKS_VERSION}
PORTREVISION=	1
CATEGORIES=	x11 kde kde-frameworks

MAINTAINER=	kde@FreeBSD.org
COMMENT=	KF5 process launcher to speed up launching KDE applications

USES=		cmake compiler:c++11-lib gettext kde:5 qt:5 tar:xz xorg
USE_KDE=	completion config coreaddons crash dbusaddons i18n \
		jobwidgets kio service solid widgetsaddons windowsystem \
		ecm:build
USE_QT=		concurrent core dbus gui network widgets \
		buildtools:build qmake:build
USE_XORG=	x11 xcb

OPTIONS_DEFINE=		DOCBOOK
OPTIONS_DEFAULT=	DOCBOOK
OPTIONS_SUB=		yes
DOCBOOK_DESC=		Doctools build

OPTIONS_EXCLUDE_aarch64c=	DOCBOOK
OPTIONS_EXCLUDE_riscv64c=	DOCBOOK

.include <bsd.port.options.mk>

.if ${PORT_OPTIONS:MDOCBOOK}
USE_KDE+=	doctools:build
.endif

.include <bsd.port.mk>
