# $FreeBSD$

.PATH:	${.CURDIR}/../../../dev/drm ${.CURDIR}/../../../dev/drm/ttm
KMOD	= drm
SRCS	= \
	ati_pcigart.c \
	drm_agpsupport.c \
	drm_atomic.c \
	drm_atomic_helper.c \
	drm_auth.c \
	drm_bufs.c \
	drm_bridge.c \
	drm_cache.c \
	drm_context.c \
	drm_crtc.c \
	drm_crtc_helper.c \
	drm_debugfs.c \
	drm_dma.c \
	drm_dp_aux_dev.c \
	drm_dp_dual_mode_helper.c \
	drm_dp_helper.c \
	drm_dp_mst_topology.c \
	drm_drv.c \
	drm_edid.c \
	drm_edid_load.c \
	drm_encoder_slave.c \
	drm_fb_helper.c \
	drm_fb_helper_freebsd.c \
	drm_flip_work.c \
	drm_fops.c \
	drm_gem.c \
	drm_gem_cma_helper.c \
	drm_global.c \
	drm_hashtab.c \
	drm_ioctl.c \
	drm_info.c \
	drm_irq.c \
	drm_kms_helper_common.c \
	drm_lock.c \
	drm_memory.c \
	drm_mipi_dsi.c \
	drm_mm.c \
	drm_modes.c \
	drm_modeset_lock.c \
	drm_os_freebsd.c \
	drm_panel.c \
	drm_pci.c \
	drm_plane_helper.c \
	drm_prime.c \
	drm_probe_helper.c \
	drm_rect.c \
	drm_scatter.c \
	drm_sysfs.c \
	drm_sysctl.c \
	drm_vma_manager.c \
	drm_vm.c \
	linux_fb.c \
	tainted_linux_fb.c \
	linux_hdmi.c \
	ttm_agp_backend.c \
	ttm_lock.c \
	ttm_object.c \
	ttm_tt.c \
	ttm_bo_util.c \
	ttm_bo.c \
	ttm_bo_manager.c \
	ttm_execbuf_util.c \
	ttm_memory.c \
	ttm_module.c \
	ttm_page_alloc.c \
	ttm_page_alloc_dma.c \
	ttm_bo_vm.c \



        # drm_of.c
        # 	
       # drm_platform.c
        # 

#	drm_fb_cma_helper.c \

CFLAGS+= -I${.CURDIR}/../../../compat/linuxkpi/common/include
CFLAGS+= -I${.CURDIR}/../../../compat/linuxkpi/common/include/drm
CFLAGS+= -I${.CURDIR}/../../../compat/linuxkpi/common/include/uapi
CFLAGS+= -I${.CURDIR}/../../../contrib/ck/include
CFLAGS+= '-DKBUILD_MODNAME="${KMOD}"'
CFLAGS+= -include ${.CURDIR}/../../../dev/drm/drm_os_config.h

# until stable
#CFLAGS += -O0
#CFLAGS += -DDRM_DEBUG_LOG_ALL
#CFLAGS += -DPRINT_UNIMPLEMENTED

.if ${MACHINE_CPUARCH} == "amd64" || ${MACHINE_ARCH} == "powerpc64"
SRCS	+= drm_ioc32.c
.endif

SRCS	+=device_if.h vnode_if.h bus_if.h pci_if.h device_if.h iicbus_if.h opt_drm.h \
	opt_vm.h opt_compat.h opt_syscons.h


.if ${MACHINE_CPUARCH} == "powerpc"
CWARNFLAGS+=-Wno-cast-qual
.endif
CWARNFLAGS+= -Wno-pointer-arith -Wno-pointer-sign -Wno-format
CWARNFLAGS+= -Wno-expansion-to-defined

CWARNFLAGS.drm_mipi_dsi.c+=	-Wno-incompatible-pointer-types-discards-qualifiers -Wno-int-conversion
CWARNFLAGS.drm_cache.c+=	-Wno-int-conversion
CWARNFLAGS.drm_info.c+=		-Wno-tautological-compare
CWARNFLAGS.drm_debugfs.c+=	-Wno-format-security
CWARNFLAGS.drm_scatter.c+=	-Wno-int-conversion
.include <bsd.kmod.mk>
