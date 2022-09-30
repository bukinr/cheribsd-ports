PORTNAME=	ktexteditor
DISTVERSION=	${KDE_FRAMEWORKS_VERSION}
PORTREVISION=	1
CATEGORIES=	devel kde kde-frameworks

MAINTAINER=	kde@FreeBSD.org
COMMENT=	KF5 advanced embeddable text editor

USES=		cmake compiler:c++11-lib gettext kde:5 cpe pkgconfig \
		qt:5 tar:xz xorg
USE_KDE=	archive auth codecs completion config configwidgets \
		coreaddons guiaddons i18n iconthemes itemviews \
		jobwidgets kio parts service solid sonnet syntaxhighlighting \
		textwidgets widgetsaddons windowsystem xmlgui \
		ecm:build
USE_QT=		concurrent core dbus declarative gui network printsupport \
		widgets xml xmlpatterns \
		buildtools:build qmake:build
USE_XORG=	x11

OPTIONS_DEFINE=		POLKIT
OPTIONS_DEFAULT=	POLKIT
OPTIONS_SUB=		yes
DOCBOOK_DESC=		Polkit Qt support

OPTIONS_EXCLUDE_aarch64c=	POLKIT
OPTIONS_EXCLUDE_riscv64c=	POLKIT

.include <bsd.port.pre.mk>

.if ${ARCH} != aarch64c && ${ARCH} != riscv64c
USE_QT+=	script
LIB_DEPENDS=	libgit2.so:devel/libgit2 \
		libeditorconfig.so:editors/editorconfig-core-c
.endif

.include <bsd.port.post.mk>
