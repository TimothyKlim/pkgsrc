# $NetBSD: Makefile,v 1.8 2013/05/31 12:40:33 wiz Exp $
#

DISTNAME=	MooseX-FollowPBP-0.05
PKGNAME=	p5-${DISTNAME}
PKGREVISION=	2
CATEGORIES=	devel perl5
MASTER_SITES=	${MASTER_SITE_PERL_CPAN:=MooseX/}

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	http://search.cpan.org/dist/MooseX-FollowPBP/
COMMENT=	Name your accessors get_foo() and set_foo()
LICENSE=	artistic-2.0

BUILD_DEPENDS+=	{perl>=5.10.1,p5-Test-Simple>=0.88}:../../devel/p5-Test-Simple
DEPENDS+=	p5-Moose>=0.94:../../devel/p5-Moose

USE_LANGUAGES=	# empty
PERL5_PACKLIST=	auto/MooseX/FollowPBP/.packlist

.include "../../lang/perl5/module.mk"
.include "../../mk/bsd.pkg.mk"
