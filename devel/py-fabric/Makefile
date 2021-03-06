# Created by: Yi-Jheng Lin <yzlin@cs.nctu.edu.tw>
# $FreeBSD$

PORTNAME=	fabric
PORTVERSION=	1.14.1
PORTEPOCH=	1
CATEGORIES=	devel python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
DISTNAME=	Fabric-${DISTVERSION}

MAINTAINER=	koobs@FreeBSD.org
COMMENT=	Simple, Pythonic remote execution and deployment

LICENSE=	BSD2CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}paramiko>=1.10:security/py-paramiko@${PY_FLAVOR} # <3.0
TEST_DEPENDS=	${PYTHON_PKGNAMEPREFIX}nose>0:devel/py-nose@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}fudge>0:devel/py-fudge@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}Jinja2>0:devel/py-Jinja2@${PY_FLAVOR}

USES=		python:2.7
USE_PYTHON=	distutils concurrent autoplist

NO_ARCH=	yes

do-test:
	@cd ${WRKSRC} && ${PYTHON_CMD} -m nose -v \
		--exclude=test_nested_execution_with_explicit_ports

.include <bsd.port.mk>
