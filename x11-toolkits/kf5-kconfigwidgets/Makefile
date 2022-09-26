PORTNAME=	kconfigwidgets
DISTVERSION=	${KDE_FRAMEWORKS_VERSION}
CATEGORIES=	x11-toolkits kde kde-frameworks

MAINTAINER=	kde@FreeBSD.org
COMMENT=	KF5 widgets for configuration dialogs

USES=		cmake compiler:c++11-lib gettext kde:5 qt:5 shebangfix tar:xz
USE_KDE=	auth codecs config coreaddons guiaddons \
		i18n widgetsaddons \
		ecm:build
USE_QT=		core dbus gui widgets xml \
		buildtools:build qmake:build

SHEBANG_FILES=	src/preparetips5

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

.include <bsd.port.post.mk>
