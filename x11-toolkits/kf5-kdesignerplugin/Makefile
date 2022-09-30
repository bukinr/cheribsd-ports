PORTNAME=	kdesignerplugin
DISTVERSION=	${KDE_FRAMEWORKS_VERSION}
CATEGORIES=	x11-toolkits kde kde-frameworks

MAINTAINER=	kde@FreeBSD.org
COMMENT=	KF5 integration of Frameworks widgets in Qt Designer/Creator

USES=		cmake compiler:c++11-lib gettext kde:5 qt:5 tar:xz
USE_KDE=	auth bookmarks codecs completion config configwidgets \
		coreaddons i18n iconthemes itemviews \
		jobwidgets kio plotting service solid sonnet \
		textwidgets widgetsaddons xmlgui \
		ecm:build
USE_QT=		concurrent core dbus designer gui linguisttools \
		network widgets xml \
		buildtools:build qmake:build

OPTIONS_DEFINE=		DOCBOOK
OPTIONS_DEFAULT=	DOCBOOK
OPTIONS_SUB=		yes
DOCBOOK_DESC=		Doctools build

OPTIONS_EXCLUDE_purecap=	DOCBOOK

.include <bsd.port.options.mk>

.if ${ARCH} != aarch64c && ${ARCH} != riscv64c
USE_KDE+=	kdewebkit
USE_QT+=	webkit
.endif

.if ${PORT_OPTIONS:MDOCBOOK}
USE_KDE+=	doctools:build
.endif

.include <bsd.port.mk>
