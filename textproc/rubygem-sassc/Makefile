# Created by: Po-Chuan Hsieh <sunpoet@FreeBSD.org>
# $FreeBSD$

PORTNAME=	sassc
PORTVERSION=	2.0.1
PORTREVISION=	1
CATEGORIES=	textproc rubygems
MASTER_SITES=	RG

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Use libsass with Ruby

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

BUILD_DEPENDS=	rubygem-rake>=0:devel/rubygem-rake
RUN_DEPENDS=	rubygem-ffi>=1.9.6:devel/rubygem-ffi \
		rubygem-rake>=0:devel/rubygem-rake
LIB_DEPENDS=	libsass.so:textproc/libsass

USES=		gem gmake
USE_RUBY=	yes

NO_ARCH=	yes

post-patch:
	@${REINPLACE_CMD} -e 's|#{gem_root}/ext/libsass|${LOCALBASE}|g' ${WRKSRC}/lib/sassc/native.rb

.include <bsd.port.mk>
