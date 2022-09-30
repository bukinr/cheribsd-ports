PORTNAME=	kde-cli-tools
DISTVERSION=	${KDE_PLASMA_VERSION}
PORTREVISION=	1
CATEGORIES=	sysutils kde kde-plasma

MAINTAINER=	kde@FreeBSD.org
COMMENT=	Plasma5 non-interactive system tools
WWW=		https://www.kde.org/plasma-desktop

USES=		cmake compiler:c++11-lib cpe gettext desktop-file-utils \
		kde:5 qt:5 tar:xz xorg
USE_KDE=	activities auth bookmarks codecs completion config \
		configwidgets coreaddons crash emoticons guiaddons i18n \
		iconthemes init itemmodels itemviews jobwidgets kcmutils \
		kdeclarative kdesu kio notifications parts plasma-workspace \
		pty service solid sonnet textwidgets unitconversion \
		widgetsaddons windowsystem xmlgui \
		ecm:build
USE_QT=		concurrent core dbus declarative gui network printsupport svg \
		widgets x11extras xml \
		buildtools:build qmake:build testlib:build
USE_XORG=	x11
CPE_VENDOR=	kde

OPTIONS_DEFINE=		DOCBOOK
OPTIONS_DEFAULT=	DOCBOOK
OPTIONS_SUB=		yes
DOCBOOK_DESC=		Doctools build

OPTIONS_EXCLUDE_purecap=	DOCBOOK

.include <bsd.port.options.mk>

.if ${PORT_OPTIONS:MDOCBOOK}
USE_KDE+=	doctools:build
.endif

.include <bsd.port.mk>
