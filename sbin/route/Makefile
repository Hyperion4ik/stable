#	@(#)Makefile	8.1 (Berkeley) 6/5/93
# $FreeBSD: releng/11.1/sbin/route/Makefile 298107 2016-04-16 07:45:30Z gjb $

.include <src.opts.mk>

PACKAGE=runtime
PROG=	route
MAN=	route.8
SRCS=	route.c keywords.h
WARNS?=	3
CLEANFILES+=keywords.h

CFLAGS+= -DNS
.if ${MK_INET_SUPPORT} != "no"
CFLAGS+= -DINET
.endif
.if ${MK_INET6_SUPPORT} != "no"
CFLAGS+= -DINET6
.endif
CFLAGS+= -I.

keywords.h: keywords
	LC_ALL=C awk '!/^#|^$$/ { \
		printf "#define\tK_%s\t%d\n\t{\"%s\", K_%s},\n", \
		    toupper($$1), ++L, $$1, toupper($$1); \
	}' < ${.CURDIR}/keywords > ${.TARGET} || (rm -f ${.TARGET}; false)

.include <bsd.prog.mk>
