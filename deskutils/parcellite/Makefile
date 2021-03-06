# Created by: Joey Mingrone <joey@mingrone.org>
# $FreeBSD$

PORTNAME=	parcellite
PORTVERSION=	1.1.7
PORTREVISION=	1
PORTEPOCH=	1
CATEGORIES=	deskutils
MASTER_SITES=	SF/${PORTNAME}/${PORTNAME}/${PORTNAME}-${PORTVERSION}

MAINTAINER=	koalative@gmail.com
COMMENT=	Lightweight GTK+ clipboard manager

LICENSE=	GPLv3

BUILD_DEPENDS=	p5-XML-Parser>=0:${PORTSDIR}/textproc/p5-XML-Parser

USES=		gettext-tools gmake pkgconfig
GNU_CONFIGURE=	yes
USE_GNOME=	gtk20 intltool

PORTDOCS=	AUTHORS ChangeLog README

LDFLAGS+=	-L${LOCALBASE}/lib
LIBS+=		-lgio-2.0

OPTIONS_DEFINE= DOCS NLS
OPTIONS_SUB=	yes

NLS_CONFIGURE_ENABLE=	nls
NLS_USES=	gettext-runtime
NLS_LIBS=	-lintl

SUB_FILES=	pkg-message

.include <bsd.port.options.mk>

post-patch:
	@${REINPLACE_CMD} -e 's|"/proc/|"/compat/linux/proc/|; \
		s|"/proc"|"/compat/linux/proc"|' \
		${WRKSRC}/src/utils.c
.if ${PORT_OPTIONS:MNLS}
	@${REINPLACE_CMD} -e 's|$$(DATADIRNAME)/locale|share/locale|' \
		${WRKSRC}/po/Makefile.in.in
.endif

post-install:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${PORTDOCS:S|^|${WRKSRC}/|} ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
