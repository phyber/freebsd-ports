# Created by: Koop Mast <kwm@rainbow-runner.nl>
# $FreeBSD$
#    $MCom: ports/multimedia/py-gstreamer/Makefile,v 1.20 2008/07/26 17:21:38 marcus Exp $

PORTNAME=	gstreamer
PORTVERSION=	0.10.22
PORTREVISION=	5
CATEGORIES=	multimedia python gnome
MASTER_SITES=	http://gstreamer.freedesktop.org/src/gst-python/
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
DISTNAME=	gst-python-${PORTVERSION}

MAINTAINER=	multimedia@FreeBSD.org
COMMENT=	Python bindings for gstreamer

LICENSE=	LGPL21
LICENSE_FILE=	${WRKSRC}/COPYING

BUILD_DEPENDS=	${PYTHON_SITELIBDIR}/libxml2mod.so:textproc/py-libxml2@${PY_FLAVOR}
RUN_DEPENDS=	${PYTHON_SITELIBDIR}/libxml2mod.so:textproc/py-libxml2@${PY_FLAVOR}

PORTSCOUT=	limit:0\.10\..*

USES=		gmake libtool pathfix pkgconfig python:2.7 tar:bzip2
USE_GNOME=	pygobject
USE_GSTREAMER=	yes
USE_PYTHON=	flavors
GNU_CONFIGURE=	yes
INSTALL_TARGET=	install-strip
PLIST_SUB=	VERSION="${GST_VERSION}"
CPPFLAGS+=	-I${LOCALBASE}/include
LDFLAGS+=	-L${LOCALBASE}/lib

post-patch:
	@${REINPLACE_CMD} -e 's|DLFCN|dl|g' ${WRKSRC}/gst/__init__.py
	@${REINPLACE_CMD} -e 's|alsasink|osssink|g' -e 's|alsasrc|osssrc|g' \
		${WRKSRC}/gst/extend/jukebox.py \
		${WRKSRC}/common/m4/gst-default.m4
.for d in audio-controller.py decodebin.py mixer.py vumeter.py
	@${REINPLACE_CMD} -e 's|alsasink|osssink|g' -e 's|alsasrc|osssrc|g' \
		${WRKSRC}/examples/${d}
.endfor

post-install:
	${PYTHON_CMD} -O ${PYTHON_LIBDIR}/compileall.py -d \
		${PYTHONPREFIX_SITELIBDIR} -f ${STAGEDIR}${PYTHONPREFIX_SITELIBDIR}
	${PYTHON_CMD} ${PYTHON_LIBDIR}/compileall.py -d \
		${PYTHONPREFIX_SITELIBDIR} -f ${STAGEDIR}${PYTHONPREFIX_SITELIBDIR}

.include <bsd.port.mk>
