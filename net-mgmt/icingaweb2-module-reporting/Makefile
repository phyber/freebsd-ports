# $FreeBSD$

PORTNAME=	icingaweb2-module-reporting
DISTVERSIONPREFIX=	v
DISTVERSION=	0.9.0
CATEGORIES=	net-mgmt www

MAINTAINER=	lme@FreeBSD.org
COMMENT=	Reporting module for Icinga Web 2

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=	icingaweb2>=2.6.0:net-mgmt/icingaweb2 \
		icingaweb2-module-reactbundle>=0.4:net-mgmt/icingaweb2-module-reactbundle \
		icingaweb2-module-ipl>=0.2.1:net-mgmt/icingaweb2-module-ipl

USE_GITHUB=	yes
GH_ACCOUNT=	icinga

OPTIONS_DEFINE=		PDF
PDF_DESC=		Use Chromium to export PDFs
OPTIONS_DEFAULT=	PDF
PDF_RUN_DEPENDS=	icingaweb2-module-pdfexport>=0.9:net-mgmt/icingaweb2-module-pdfexport

NO_BUILD=	yes
NO_ARCH=	yes

WWWDIR?=	${PREFIX}/www/icingaweb2/modules/${PORTNAME:C/^.*-//}

do-install:
	@${MKDIR} ${STAGEDIR}${WWWDIR}
	(cd ${WRKSRC} && \
		${COPYTREE_SHARE} . ${STAGEDIR}${WWWDIR})

.include <bsd.port.mk>
