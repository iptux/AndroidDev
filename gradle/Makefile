# simple makefile for Android project that use gradle
#
# Copyright (c) 2016 Tommy Alex
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
# FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
# DEALINGS IN THE SOFTWARE.

GRADLE := gradle

module-name = $(lastword $(subst :, ,$(1)))

define GRADLE_TARGET
# param: TARGET TASK MODULE
ifeq (,$(strip $(3)))
# project level target
.PHONY: $(1)
$(1):
	$(GRADLE) $(2)
else
# module level target
.PHONY: $(call module-name,$(3))-$(1)
$(call module-name,$(3))-$(1):
	$(GRADLE) :$(3):$(2)
endif
endef

define GRADLE_ANDROID
# param: MODULE
$(eval $(call GRADLE_TARGET,debug,assembleDebug,$(1)))
$(eval $(call GRADLE_TARGET,release,assembleRelease,$(1)))
$(eval $(call GRADLE_TARGET,clean,clean,$(1)))
$(eval $(call GRADLE_TARGET,install,installDebug,$(1)))
$(eval $(call GRADLE_TARGET,installr,installRelease,$(1)))
$(eval $(call GRADLE_TARGET,uninstall,uninstallDebug,$(1)))
$(eval $(call GRADLE_TARGET,uninstallr,uninstallRelease,$(1)))
endef

$(call GRADLE_ANDROID,)
$(call GRADLE_ANDROID,app)
