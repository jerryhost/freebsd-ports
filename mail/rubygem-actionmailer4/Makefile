# Created by: Johannes Meixner <xmj@chaot.net>
# $FreeBSD$

PORTNAME=	actionmailer
PORTVERSION=	4.2.3
CATEGORIES=	mail rubygems
MASTER_SITES=	RG
PKGNAMESUFFIX=	4

MAINTAINER=	ruby@FreeBSD.org
COMMENT=	Easy email delivery and testing for Ruby

LICENSE=	MIT

RUN_DEPENDS=	rubygem-actionpack4>=${PORTVERSION}:${PORTSDIR}/www/rubygem-actionpack4 \
		rubygem-actionview>=${PORTVERSION}:${PORTSDIR}/devel/rubygem-actionview \
		rubygem-activejob>=${PORTVERSION}:${PORTSDIR}/devel/rubygem-activejob \
		rubygem-mail>=2.6.1:${PORTSDIR}/mail/rubygem-mail \
		rubygem-rails-dom-testing>=1.0:${PORTSDIR}/textproc/rubygem-rails-dom-testing

NO_ARCH=	yes
USE_RUBY=	yes
USE_RUBYGEMS=	yes
RUBYGEM_AUTOPLIST=	yes

.include <bsd.port.mk>
