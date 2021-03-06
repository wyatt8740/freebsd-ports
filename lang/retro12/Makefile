# $FreeBSD$

PORTNAME=	retro12
DISTVERSION=	2019.1
CATEGORIES=	lang
MASTER_SITES=	https://forthworks.com/retro/r/
DISTNAME=	${PORTNAME:tu}-${DISTVERSION}

MAINTAINER=	0mp@FreeBSD.org
COMMENT=	Clean, elegant, and pragmatic dialect of Forth

LICENSE=	ISCL
LICENSE_FILE=	${WRKSRC}/LICENSE.md

USES=	ncurses shebangfix

SHEBANG_FILES=	example/Atua*
SHEBANG_LANG=	rre

# Conflicting files: bin/listener bin/repl bin/ri
CONFLICTS_INSTALL=	audio/listener mail/nmh japanese/mh lang/ruby

MAKE_ENV=	DATADIR=${DATADIR} \
		DESTDIR=${DESTDIR} \
		DOCSDIR=${DOCSDIR} \
		EXAMPLESDIR=${EXAMPLESDIR} \
		PREFIX=${PREFIX}
# There are race conditions in the makefile due to missing dependencies for
# targets as upstream tests releases on single core machines.
MAKE_JOBS_UNSAFE=	yes

PLIST_FILES=	bin/retro \
		bin/retro-embedimage \
		bin/retro-extend \
		bin/retro-injectimage-js \
		bin/retro-muri \
		bin/retro-repl \
		bin/retro-ri \
		bin/retro-unu

PORTDATA=	RETRO12.html \
		glossary.forth \
		ngaImage \
		tests \
		words.tsv

PORTDOCS=	doc \
		literate \
		README.md \
		RELEASE_NOTES.md

PORTEXAMPLES=	example

INSTALL_TARGET=	install-strip
TEST_TARGET=	test

OPTIONS_DEFINE=	DOCS EXAMPLES

.include <bsd.port.mk>
