################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include Startup/subdir.mk
-include Libraries/XMCLib/src/subdir.mk
-include Libraries/Newlib/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
SECONDARY_FLASH += \
helloworld.hex \

SECONDARY_LIST += \
helloworld.lst \

SECONDARY_SIZE += \
helloworld.siz \


LIST_FILES = $(addsuffix .o.lst, $(basename $(OBJS))) 
MAP_FILE = "helloworld.map"

TOOLCHAIN_ROOT=C:/Users/wiegelep/Downloads/DAVE_4-4-2_32bit_2018-02-23/DAVE_4-4-2_32bit_2018-02-23/DAVE-IDE-4.4.2-32Bit/DAVE-IDE-4.4.2-32Bit/eclipse/ARM-GCC-49
PROJECT_LOC=C:/Users/wiegelep/Downloads/ws/helloworld

# All Target
all: helloworld.elf secondary-outputs

# Tool invocations
helloworld.elf: $(OBJS) ../linker_script.ld $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: ARM-GCC C Linker'
	$(file >objects.rsp,$(OBJS))
	"$(TOOLCHAIN_ROOT)/bin/arm-none-eabi-gcc" -T"../linker_script.ld" -nostartfiles -Xlinker --gc-sections -specs=nano.specs -specs=nosys.specs -Wl,-Map,$(MAP_FILE) -mcpu=cortex-m0 -mthumb -g -gdwarf-2 -o "helloworld.elf" "@objects.rsp" $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo.
helloworld.hex: helloworld.elf
	@echo 'Invoking: ARM-GCC Create Flash Image'
	"$(TOOLCHAIN_ROOT)/bin/arm-none-eabi-objcopy" -O ihex "helloworld.elf" "helloworld.hex"
	@echo 'Finished building: $@'
	@echo.
helloworld.lst: helloworld.elf
	@echo 'Invoking: ARM-GCC Create Listing'
	"$(TOOLCHAIN_ROOT)/bin/arm-none-eabi-objdump" -h -S "helloworld.elf" > "helloworld.lst"
	@echo 'Finished building: $@'
	@echo.
helloworld.siz: helloworld.elf
	@echo 'Invoking: ARM-GCC Print Size'
	"$(TOOLCHAIN_ROOT)/bin/arm-none-eabi-size" --format=berkeley "helloworld.elf"
	@echo 'Finished building: $@'
	@echo.
# Other Targets
clean:
	-$(RM) $(OBJS)$(SECONDARY_FLASH)$(SECONDARY_LIST)$(SECONDARY_SIZE)$(ARM_GCC_FOR_XMC_LINKER_OUTPUT_TYPE_OUTPUTS)$(S_DEPS)$(S_UPPER_DEPS)$(C_DEPS) helloworld.elf $(LIST_FILES) $(MAP_FILE) objects.rsp
	-@echo.
secondary-outputs: $(SECONDARY_FLASH) $(SECONDARY_LIST) $(SECONDARY_SIZE)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
