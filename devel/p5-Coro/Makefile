# $NetBSD: Makefile,v 1.11 2013/09/02 13:16:26 obache Exp $
#

DISTNAME=	Coro-6.31
PKGNAME=	p5-${DISTNAME}
CATEGORIES=	parallel
MASTER_SITES=	${MASTER_SITE_PERL_CPAN:=Coro/}

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	http://search.cpan.org/dist/Coro/
COMMENT=	Perl 5 module providing cooperative threads
LICENSE=	${PERL5_LICENSE}

REPLACE_PERL=	Coro/jit-amd64-unix.pl Coro/jit-x86-unix.pl

USE_LANGUAGES=	c
PERL5_PACKLIST=	auto/Coro/.packlist

DEPENDS+=	p5-AnyEvent-AIO>=1:../../devel/p5-AnyEvent-AIO
DEPENDS+=	p5-AnyEvent-BDB>=1:../../databases/p5-AnyEvent-BDB
DEPENDS+=	p5-BDB-[0-9]*:../../databases/p5-BDB
DEPENDS+=	p5-IO-AIO>=3.1:../../devel/p5-IO-AIO
DEPENDS+=	p5-AnyEvent>=5:../../devel/p5-AnyEvent
DEPENDS+=	p5-Guard>=0.5:../../devel/p5-Guard
DEPENDS+=	p5-common-sense-[0-9]*:../../devel/p5-common-sense

.include "../../mk/bsd.prefs.mk"

.if ${OPSYS} == "NetBSD"
# Only tested on NetBSD/i386 5.0.2
MAKE_ENV+=	CORO_INTERFACE=p # pthread implementation
.endif

.include "../../devel/p5-Event/buildlink3.mk"
.include "../../devel/p5-EV/buildlink3.mk"
.include "../../lang/perl5/module.mk"
.include "../../mk/bsd.pkg.mk"
