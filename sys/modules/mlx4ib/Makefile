# $FreeBSD$
.PATH:  ${.CURDIR}/../../dev/mlx4/mlx4_ib

KMOD=	mlx4ib
SRCS=	device_if.h bus_if.h vnode_if.h pci_if.h \
	opt_inet.h opt_inet6.h \
	mlx4_ib_alias_GUID.c \
	mlx4_ib_mcg.c \
	mlx4_ib_sysfs.c \
	mlx4_ib_ah.c \
	mlx4_ib_cq.c \
	mlx4_ib_exp.c \
	mlx4_ib_doorbell.c \
	mlx4_ib_mad.c \
	mlx4_ib_main.c \
	mlx4_ib_mr.c \
	mlx4_ib_qp.c \
	mlx4_ib_srq.c \
	mlx4_ib_wc.c \
	mlx4_ib_cm.c

CFLAGS+= -I${.CURDIR}/../../ofed/include
CFLAGS+= -I${.CURDIR}/../../compat/linuxkpi/common/include
CFLAGS+= -I${.CURDIR}/../../contrib/ck/include
CFLAGS+= -DCONFIG_INFINIBAND_USER_MEM
CFLAGS+= -DINET6 -DINET

.include <bsd.kmod.mk>

CFLAGS+= -Wno-cast-qual -Wno-pointer-arith
