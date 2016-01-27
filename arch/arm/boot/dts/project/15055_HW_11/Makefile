ifeq ($(CONFIG_OF),y)
dtb-$(CONFIG_ARCH_MSM8974) += msm8974pro-ab-pm8941-mtp_15055_HW_11.dtb \
	msm8974pro-ac-pm8941-mtp_15055_HW_11.dtb

DTB_NAMES := $(subst $\",,$(CONFIG_BUILD_ARM_APPENDED_DTB_IMAGE_NAMES))
ifneq ($(DTB_NAMES),)
DTB_LIST := $(addsuffix .dtb,$(DTB_NAMES))
else
DTB_LIST := $(dtb-y)
endif
DTB_OBJS := $(addprefix $(obj)/,$(DTB_LIST))

targets += dtbs
targets += $(addprefix ../, $(DTB_LIST))
endif

# Rule to build device tree blobs
$(obj)/%.dtb: $(src)/dts/project/15055_HW_11/%.dts FORCE
	$(call if_changed_dep,dtc)

$(obj)/dtbs: $(DTB_OBJS)

clean-files := *.dtb
