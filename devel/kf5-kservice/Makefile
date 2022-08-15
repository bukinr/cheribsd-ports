PORTNAME=	kservice
DISTVERSION=	${KDE_FRAMEWORKS_VERSION}
CATEGORIES=	devel kde kde-frameworks

MAINTAINER=	kde@FreeBSD.org
COMMENT=	KF5 advanced plugin and service introspection

USES=		bison cmake compiler:c++11-lib gettext kde:5 qt:5 tar:xz
USE_KDE=	archive config coreaddons crash dbusaddons i18n \
		ecm:build
USE_QT=		core dbus gui xml \
		buildtools:build qmake:build

# Make the applications.menu file not conflict with KDE4.
CMAKE_ARGS=	-DAPPLICATIONS_MENU_NAME:STRING="kf5-applications.menu"

OPTIONS_DEFINE=		DOCBOOK
OPTIONS_DEFAULT=	DOCBOOK
OPTIONS_SUB=		yes
DOCBOOK_DESC=		Doctools build

OPTIONS_EXCLUDE_aarch64c=	DOCBOOK
OPTIONS_EXCLUDE_riscv64c=	DOCBOOK

.include <bsd.port.pre.mk>

.if ${PORT_OPTIONS:MDOCBOOK}
USE_KDE+=	doctools:build
.endif

.include <bsd.port.mk>
