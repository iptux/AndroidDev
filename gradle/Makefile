# simple makefile for ANdroid project that use gradle

GRADLE := gradle

define GRADLE_TARGET
# param: TARGET TASK MODULE
ifeq (,$(strip $(3)))
# project level target
$(1):
	$(GRADLE) $(2)
.PHONY: $(1)
else
# module level target
$(3)-$(1):
	$(GRADLE) :$(3):$(2)
.PHONY: $(3)-$(1)
endif
endef

define GRADLE_ANDROID
# param: MODULE
$(eval $(call GRADLE_TARGET,debug,assembleDebug,$(1)))
$(eval $(call GRADLE_TARGET,release,assembleRelease,$(1)))
$(eval $(call GRADLE_TARGET,clean,clean,$(1)))
$(eval $(call GRADLE_TARGET,install,installDebug,$(1)))
$(eval $(call GRADLE_TARGET,uninstall,uninstallDebug,$(1)))
endef

$(call GRADLE_ANDROID,)
$(call GRADLE_ANDROID,app)