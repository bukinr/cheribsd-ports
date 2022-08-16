PORTNAME=	kwallet
DISTVERSION=	${KDE_FRAMEWORKS_VERSION}
PORTREVISION=	2
CATEGORIES=	sysutils kde kde-frameworks

MAINTAINER=	kde@FreeBSD.org
COMMENT=	KF5 secure and unified container for user passwords

LIB_DEPENDS=	libassuan.so:security/libassuan

USES=		cmake compiler:c++11-lib gettext kde:5 qca qt:5 tar:xz xorg
USE_KDE=	auth codecs config configwidgets coreaddons dbusaddons \
		i18n iconthemes notifications service \
		widgetsaddons windowsystem \
		ecm:build
USE_QT=		core dbus gui testlib widgets xml \
		buildtools:build qmake:build
USE_XORG=	x11

OPTIONS_DEFINE=		PINENTRY
OPTIONS_DEFAULT=	PINENTRY

PINENTRY_DESC=	Include pinentry-qt, for wallet passwords
PINENTRY_RUN_DEPENDS=	pinentry-qt5:security/pinentry-qt5

OPTIONS_DEFINE=		DOCBOOK
OPTIONS_DEFAULT=	DOCBOOK
OPTIONS_SUB=		yes
DOCBOOK_DESC=		Doctools build

OPTIONS_EXCLUDE_aarch64c=	DOCBOOK
OPTIONS_EXCLUDE_riscv64c=	DOCBOOK

.include <bsd.port.pre.mk>

.if ${ARCH} != aarch64c && ${ARCH} != riscv64c
LIB_DEPENDS+=	libgcrypt.so:security/libgcrypt \
		libgpg-error.so:security/libgpg-error \
		libgpgme.so:security/gpgme \
		libqgpgme.so:security/gpgme-qt5 \
		libgpgmepp.so:security/gpgme-cpp
.endif

.if ${PORT_OPTIONS:MDOCBOOK}
USE_KDE+=	doctools:build
.endif

.include <bsd.port.post.mk>
