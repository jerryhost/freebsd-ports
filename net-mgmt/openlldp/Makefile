# Created by: Roar Pettersen <roar@uib.no>
# $FreeBSD$

PORTNAME=	openlldp
DISTVERSION=	0.4alpha
PORTREVISION=	1
CATEGORIES=	net-mgmt
MASTER_SITES=	SF/${PORTNAME}

MAINTAINER=	roar.pettersen@it.uib.no
COMMENT=	Link Layer Discovery Protocol daemon

GNU_CONFIGURE=	yes

USE_RC_SUBR=	lldpd
PLIST_FILES=	sbin/lldpd bin/lldpneighbors man/man8/lldpd.8.gz

post-patch:
	@${REINPLACE_CMD} -e 's/^CFLAGS =/CFLAGS +=/g' \
		${WRKSRC}/src/Makefile.in

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/src/lldpd ${STAGEDIR}${PREFIX}/sbin
	${INSTALL_PROGRAM} ${WRKSRC}/src/lldpneighbors ${STAGEDIR}${PREFIX}/bin
	${INSTALL_MAN} ${FILESDIR}/lldpd.8 ${STAGEDIR}${MANPREFIX}/man/man8

.include <bsd.port.mk>
