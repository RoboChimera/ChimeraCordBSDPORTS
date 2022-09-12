PORTNAME=	ChimeraCord
DISTVERSION=	0.1.0
CATEGORIES=	www

MAINTAINER=	fernvent@protonmail.com
COMMENT=	A native unofficial discord client for FreeBSD!
LICENSE=	BSD2CLAUSE

USE_GITHUB=	yes
GH_ACCOUNT=	RoboChimera
GH_PROJECT=	ChimeraCord
GH_TAGNAME=	aed4b5e

ONLY_FOR_ARCH=	amd64 i386
NO_BUILD=	yes

RUN_DEPENDS=	electron19>=19:devel/electron19 \
		npm>=8:www/npm \
		node16>=16:www/node16

do-install:
	npm install -gf electron-context-menu electron-store --savedev
	cp -rvf ${WRKSRC}/chimeracord ${STAGEDIR}${PREFIX}/share/chimeracord
	cp -vf ${WRKSRC}/chimeracord.in ${STAGEDIR}${PREFIX}/bin/chimeracord
	chmod +x ${STAGEDIR}${PREFIX}/bin/chimeracord
	cp ${WRKSRC}/chimeracord.desktop.in ${STAGEDIR}${PREFIX}/share/applications/chimeracord.desktop
	mkdir ${STAGEDIR}${PREFIX}/share/chimeracord/node_modules
	mv /usr/local/lib/node_modules/electron-context-menu ${STAGEDIR}${PREFIX}/share/chimeracord/node_modules/electron-context-menu
	mv /usr/local/lib/node_modules/electron-store ${STAGEDIR}${PREFIX}/share/chimeracord/node_modules/electron-store

.include <bsd.port.mk>
