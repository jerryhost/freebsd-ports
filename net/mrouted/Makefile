# Created by: Bruce M Simpson <bms@FreeBSD.org>
# $FreeBSD$

PORTNAME=	mrouted
PORTVERSION=	3.9.6
PORTREVISION=	1
CATEGORIES=	net
MASTER_SITES=	http://cloud.github.com/downloads/troglobit/mrouted/

MAINTAINER=	hrs@FreeBSD.org
COMMENT=	Multicast routing daemon providing DVMRP for IPv4

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE

USE_RC_SUBR=	mrouted
USES=		gmake tar:bzip2
MAKE_ARGS=	sysconfdir=${PREFIX}/etc \
		mandir=${MAN8PREFIX}/man/man8
PORTDOCS=	README AUTHORS ChangeLog
PLIST_FILES=	sbin/map-mbone sbin/mrouted sbin/mrinfo sbin/mtrace \
		etc/mrouted.conf man/man8/map-mbone.8.gz \
		man/man8/mrinfo.8.gz man/man8/mrouted.8.gz \
		man/man8/mtrace.8.gz
OPTIONS_DEFINE=	DOCS

.include <bsd.port.options.mk>

.if ${PORT_OPTIONS:MDOCS}
MAKE_ARGS+=	datadir=${DOCSDIR} doc=yes
.endif

.include <bsd.port.mk>
