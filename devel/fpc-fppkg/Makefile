# Created by: Alonso Cardenas Marquez <acm@FreeBSD.org>
# $FreeBSD$

PORTREVISION=	1
CATEGORIES=	devel lang
PKGNAMESUFFIX=	-fppkg

MAINTAINER=	freebsd-fpc@FreeBSD.org
COMMENT=	Free Pascal package unit

USE_FPC=	fcl-base fcl-process fcl-web fcl-xml

MASTERDIR=	${.CURDIR}/../../lang/fpc
WRKUNITDIR=	${FPCSRCDIR}/packages/${PKGNAMESUFFIX:S/-//}
EXTRACTUNITDIR=	${WRKUNITDIR}

.include "${MASTERDIR}/Makefile"
