# $NetBSD: Makefile,v 1.8 2013/10/24 09:49:22 jperkin Exp $

DISTNAME=	dhcpd-pools-2.16
PKGREVISION=	3
CATEGORIES=	net
MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=dhcpd-pools/}

MAINTAINER=	adam@NetBSD.org
HOMEPAGE=	http://dhcpd-pools.sourceforge.net/
COMMENT=	ISC dhcpd lease analysis and reporting
LICENSE=	gnu-gpl-v3

USE_LANGUAGES=		c
USE_LIBTOOL=		yes
GNU_CONFIGURE=		yes
CONFIGURE_ARGS+=	--with-dhcpd-leases=${VARBASE}/db/dhcpd.leases

BUILD_DEFS+=		VARBASE
REPLACE_PERL=		contrib/snmptest.pl
USE_TOOLS+=		perl:run

SUBST_CLASSES+=		fix-name
SUBST_STAGE.fix-name=	pre-configure
SUBST_MESSAGE.fix-name=	Removing program_invocation_short_name.
SUBST_FILES.fix-name=	src/dhcpd-pools.c src/other.c src/sort.c
SUBST_SED.fix-name=	-e 's,program_invocation_short_name,"dhcpd-pools",g'

LDFLAGS.SunOS+=	-lnsl

.include "../../mk/bsd.pkg.mk"
