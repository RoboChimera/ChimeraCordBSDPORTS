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
	cp -rvf ChimeraCord/chimeracord /usr/local/share/chimeracord
	cp -vf ChimeraCord/chimeracord.in /usr/local/bin/chimeracord
	chmod +x /usr/local/bin/chimeracord
	cp ChimeraCord/chimeracord.desktop.in /usr/local/share/applications/chimeracord.desktop
	ln -sFf /usr/local/lib/node_modules /usr/local/share/chimeracord/node_modules

.include <bsd.port.mk>
