# Created by: Li-Wen Hsu <lwhsu@FreeBSD.org>
# $FreeBSD$

PORTNAME=	sphinx
PORTVERSION=	1.3.1
PORTREVISION=	2
CATEGORIES=	textproc python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
DISTNAME=	Sphinx-${PORTVERSION}
DIST_SUBDIR=	python

MAINTAINER=	kmoore@FreeBSD.org
COMMENT=	Python documentation generator

LICENSE=	BSD2CLAUSE

BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}Jinja2>=2.3:${PORTSDIR}/devel/py-Jinja2 \
		${PYTHON_PKGNAMEPREFIX}docutils>=0.11:${PORTSDIR}/textproc/py-docutils \
		${PYTHON_PKGNAMEPREFIX}six>=1.4:${PORTSDIR}/devel/py-six
RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}Babel>=1.3:${PORTSDIR}/devel/py-babel\
		${PYTHON_PKGNAMEPREFIX}Jinja2>=2.3:${PORTSDIR}/devel/py-Jinja2 \
		${PYTHON_PKGNAMEPREFIX}docutils>=0.11:${PORTSDIR}/textproc/py-docutils \
		${PYTHON_PKGNAMEPREFIX}pygments>=2.0:${PORTSDIR}/textproc/py-pygments \
		${PYTHON_PKGNAMEPREFIX}Babel>=1.3:${PORTSDIR}/devel/py-babel \
		${PYTHON_PKGNAMEPREFIX}sphinx_rtd_theme>=0.1:${PORTSDIR}/textproc/py-sphinx_rtd_theme \
		${PYTHON_PKGNAMEPREFIX}alabaster>=0.7:${PORTSDIR}/textproc/py-alabaster \
		${PYTHON_PKGNAMEPREFIX}snowballstemmer>=1.1:${PORTSDIR}/textproc/py-snowballstemmer \
		${PYTHON_PKGNAMEPREFIX}six>=1.4:${PORTSDIR}/devel/py-six

USES=		python
USE_PYTHON=	autoplist distutils

post-build:
	cd ${WRKSRC}/build/lib && \
	${SETENV} PYTHONPATH=${WRKSRC}/build/lib:${PYTHONPREFIX_SITELIBDIR} \
	${PYTHON_CMD} -m sphinx.pycode.pgen2.driver -c 'import load_grammar'

post-install:
	${INSTALL_DATA} ${WRKSRC}/build/lib/sphinx/pycode/Grammar-py${PYTHON_VER:R}-${PORTNAME}${PORTVERSION:R}.pickle \
	${STAGEDIR}/${PYTHONPREFIX_SITELIBDIR}/sphinx/pycode/

	@${ECHO_CMD} ${PYTHON_SITELIBDIR:S;${PYTHONBASE}/;;}/sphinx/pycode/Grammar-py${PYTHON_VER:R}-${PORTNAME}${PORTVERSION:R}.pickle >> ${TMPPLIST}

.include <bsd.port.mk>
