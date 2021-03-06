# $NetBSD: Makefile,v 1.1 2013/09/12 13:58:24 ryoon Exp $

DISTNAME=	binutils-2.23.2
PKGNAME=	cross-freemint-${DISTNAME}
CATEGORIES=	cross
MASTER_SITES=	${MASTER_SITE_GNU:=binutils/}
EXTRACT_SUFX=	.tar.bz2

MAINTAINER=	ryoon@NetBSD.org
HOMEPAGE=	http://vincent.riviere.free.fr/soft/m68k-atari-mint/
COMMENT=	Cross binutils for FreeMiNT
LICENSE=	gnu-gpl-v2 AND gnu-gpl-v3 AND gnu-lgpl-v2 AND gnu-lgpl-v3

PATCH_SITES=	http://vincent.riviere.free.fr/soft/m68k-atari-mint/archives/
PATCHFILES=	binutils-2.23.2-mint-20130327.patch.bz2
PATCH_DIST_STRIP=	-p1

FREEMINT_PREFIX=	${PREFIX}/cross-freemint

USE_TOOLS+=	gmake makeinfo
GNU_CONFIGURE=	yes

OBJDIR=			../build
CONFIGURE_DIRS=		${OBJDIR}
CONFIGURE_SCRIPT=	${WRKSRC}/configure
GNU_CONFIGURE_PREFIX=	${FREEMINT_PREFIX}

CONFIGURE_ARGS+=	--disable-werror --target=m68k-atari-mint
INFO_FILES=		yes

INSTALLATION_DIRS+=	bin ${FREEMINT_PREFIX}

pre-configure:
	${RUN} cd ${WRKSRC} && ${MKDIR} ${OBJDIR}
	${CP} ${PKGSRCDIR}/mk/gnu-config/config.guess ${WRKSRC}
	${CP} ${PKGSRCDIR}/mk/gnu-config/config.sub ${WRKSRC}


post-install:
	for f in m68k-atari-mint-addr2line	m68k-atari-mint-ar \
		 m68k-atari-mint-as		m68k-atari-mint-c++filt \
		 m68k-atari-mint-gprof		m68k-atari-mint-ld \
		 m68k-atari-mint-nm		m68k-atari-mint-objcopy \
		 m68k-atari-mint-objdump	m68k-atari-mint-ranlib \
		 m68k-atari-mint-readelf	m68k-atari-mint-size \
		 m68k-atari-mint-strings	m68k-atari-mint-strip ; do \
		${LN} -s ${FREEMINT_PREFIX}/bin/"$$f" \
		  ${DESTDIR}${PREFIX}/bin/"$$f" || exit 1; \
	done
# copy libiberty.a under the different name from compiler
# PATH differs between clang and gcc:
	for d in ${MACHINE_ARCH}/libiberty.a libiberty.a; do \
		if [ -f ${DESTDIR}${FREEMINT_PREFIX}/lib/$$d ]; then \
			${MV} ${DESTDIR}${FREEMINT_PREFIX}/lib/$$d \
			      ${DESTDIR}${FREEMINT_PREFIX}/lib/libiberty_binutils.a; \
		break; \
		fi; \
	done

.include "../../mk/bsd.pkg.mk"
