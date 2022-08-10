PORTNAME=	ChimeraCord
DISTVERSION=	0.1.0
CATEGORIES=	www

MAINTAINER=	fernvent@protonmail.com
COMMENT=	A native unofficial discord client for FreeBSD!

LICENSE=	BSD2CLAUSE

NO_ARCH=	yes
NO_BUILD=	yes

BUILD_DEPENDS=	electron19>=19:devel/electron19 \
		npm>=8:www/npm \
		node16>=16:www/node16 

do-install:
	git clone https://github.com/RoboChimera/ChimeraCord
	npm install -gf electron-context-menu --savedev
	cp -rvf ChimeraCord/chimeracord ${STAGEDIR}${PREFIX}/share/chimeracord
	cp -vf ChimeraCord/chimeracord.in ${STAGEDIR}${PREFIX}/bin/chimeracord
	chmod +x ${STAGEDIR}${PREFIX}/bin/chimeracord
	cp ChimeraCord/chimeracord.desktop.in ${STAGEDIR}${PREFIX}/share/applications/chimeracord.desktop
	mkdir ${STAGEDIR}${PREFIX}/share/chimeracord/node_modules
	mv /usr/local/lib/node_modules/electron-context-menu ${STAGEDIR}${PREFIX}/share/chimeracord/node_modules/electron-context-menu

.include <bsd.port.mk>
