PORTNAME=	systemsettings
DISTVERSION=	${KDE_PLASMA_VERSION}
PORTREVISION=	1
CATEGORIES=	sysutils kde kde-plasma

MAINTAINER=	kde@FreeBSD.org
COMMENT=	Plasma5 system settings
WWW=		https://www.kde.org/plasma-desktop

USES=		cmake compiler:c++11-lib gettext kde:5 qt:5 tar:xz xorg
USE_KDE=	activities activities-stats auth codecs completion config \
		configwidgets coreaddons crash dbusaddons guiaddons i18n \
		iconthemes itemmodels itemviews jobwidgets kcmutils \
		kdeclarative kio kirigami2 notifications package parts \
		plasma-framework plasma-workspace runner service solid sonnet \
		textwidgets widgetsaddons windowsystem xmlgui \
		ecm:build
USE_QT=		concurrent core dbus declarative gui network widgets xml \
		buildtools:build qmake:build
USE_XORG=	x11

OPTIONS_DEFINE=		DOCBOOK
OPTIONS_DEFAULT=	DOCBOOK
OPTIONS_SUB=		yes
DOCBOOK_DESC=		Doctools build

OPTIONS_EXCLUDE_purecap=	DOCBOOK

.include <bsd.port.options.mk>

.if ${ARCH} != aarch64c && ${ARCH} != riscv64c
USE_KDE+=	js khtml
.endif

.if ${PORT_OPTIONS:MDOCBOOK}
USE_KDE+=	doctools:build
.endif

.include <bsd.port.mk>
