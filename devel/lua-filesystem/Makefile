# $NetBSD: Makefile,v 1.6 2013/10/30 06:03:37 dholland Exp $
#

DISTNAME=		luafilesystem-1.6.2
PKGNAME=		${DISTNAME:S/lua/${LUA_PKGPREFIX}-/}
PKGREVISION=		1
CATEGORIES=		devel
MASTER_SITES=		http://github.com/downloads/keplerproject/luafilesystem/

MAINTAINER=		filip@joyent.com
HOMEPAGE=		http://keplerproject.github.com/luafilesystem/
COMMENT=		File system related library for Lua
LICENSE=		mit

USE_TOOLS+=		gmake
BUILD_TARGET=		lib

MAKE_ENV+=		LUA_CDIR=${LUA_CDIR}

.include "../../lang/lua/module.mk"
.include "../../mk/bsd.pkg.mk"
