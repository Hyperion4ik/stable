# $FreeBSD: releng/11.1/usr.sbin/bsnmpd/gensnmptree/Makefile 319119 2017-05-29 10:15:41Z ngie $
#
# Author: Harti Brandt <harti@freebsd.org>

CONTRIB=${SRCTOP}/contrib/bsnmp
.PATH: ${CONTRIB}/gensnmptree

PROG=	gensnmptree
CFLAGS+= -I${CONTRIB}/lib
CFLAGS+= -DQUADFMT='"llu"' -DQUADXFMT='"llx"' -DHAVE_STDINT_H
CFLAGS+= -DHAVE_INTTYPES_H

WARNS?=	5

.include <bsd.prog.mk>
