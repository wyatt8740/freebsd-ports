# $FreeBSD$

PORTNAME=	rpm-build-perl
PORTVERSION=	0.82
PORTREVISION=	1
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:ATOURBIN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	This module is required to build Perl RPM packages

BROKEN=		does not build, op_sibling usage. https://rt.cpan.org/Public/Bug/Display.html?id=117350

TEST_DEPENDS=	p5-Try-Tiny>=0:lang/p5-Try-Tiny

USES=		perl5
USE_PERL5=	configure

post-patch:
	@${REINPLACE_CMD} -e 's| perl.clean||' ${WRKSRC}/Makefile.PL

.include <bsd.port.mk>
