# $NetBSD: Makefile,v 1.2 2012/10/29 05:07:13 asau Exp $
#

DISTNAME=		xkbevd-1.1.3
CATEGORIES=		x11
MASTER_SITES=		${MASTER_SITE_XORG:=app/}
EXTRACT_SUFX=		.tar.bz2

MAINTAINER=		pkgsrc-users@NetBSD.org
HOMEPAGE=		http://xorg.freedesktop.org/
COMMENT=		Possible replacement for xev (work in progress)

GNU_CONFIGURE=		yes
USE_TOOLS+=		pkg-config

.include "../../x11/libxkbfile/buildlink3.mk"
.include "../../x11/libX11/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
