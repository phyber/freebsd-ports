# $FreeBSD$

PORTNAME=	bootsnap
PORTVERSION=	1.3.2
PORTREVISION=	1
CATEGORIES=	devel rubygems
MASTER_SITES=	RG

MAINTAINER=	ruby@FreeBSD.org
COMMENT=	Boot large ruby/rails apps faster

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

RUN_DEPENDS=	rubygem-msgpack>=1.0:devel/rubygem-msgpack

USES=		gem shebangfix
USE_RUBY=	yes

SHEBANG_FILES=	bin/*

.include <bsd.port.mk>
