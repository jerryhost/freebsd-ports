# Created by: Diane Bruce <db@db.net>
# $FreeBSD$

PORTNAME=	ibp
PORTVERSION=	0.21
PORTREVISION=	2
CATEGORIES=	comms hamradio
MASTER_SITES=	http://wwwhome.cs.utwente.nl/~ptdeboer/ham/ \
		LOCAL/db

MAINTAINER=	hamradio@FreeBSD.org
COMMENT=	Little program for monitoring amateur radio beacons

USES=		imake tar:tgz
USE_XORG=	x11

do-install:
	${INSTALL_PROGRAM}	${WRKSRC}/ibp ${STAGEDIR}${PREFIX}/bin/
	${INSTALL_MAN}	${WRKSRC}/ibp.1 ${STAGEDIR}${MANPREFIX}/man/man1/ibp.1

.include <bsd.port.mk>
