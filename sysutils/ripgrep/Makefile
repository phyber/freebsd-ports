# $freeBSD$

PORTNAME=		ripgrep
PORTVERSION=	0.5.0
PORTEPOCH=		1
CATEGORIES?=	sysutils

MAINTAINER=		dor.bsd@xm0.uk
COMMENT=		ripgrep combines the usability of The Silver Searcher with the raw speed of grep.
LICENSE=		MIT
LICENSE_FILE=	${WRKSRC}/LICENSE-MIT

BUILD_DEPENDS=	cargo:devel/cargo

USE_GITHUB=		yes
GH_ACCOUNT=		BurntSushi
GH_PROJECT=		${PORTNAME}

MAKE_ENV=		CARGO_HOME=${BUILD_WRKSRC}

do-build:
	cd ${BUILD_WRKSRC} && ${SETENV} ${MAKE_ENV} cargo build --release --verbose

do-install:
	${INSTALL_PROGRAM} ${BUILD_WRKSRC}/target/release/rg ${STAGEDIR}${PREFIX}/bin/rg
	${INSTALL_MAN} ${BUILD_WRKSRC}/doc/rg.1 ${STAGEDIR}${PREFIX}/man/man1/rg.1

.include <bsd.port.mk>
