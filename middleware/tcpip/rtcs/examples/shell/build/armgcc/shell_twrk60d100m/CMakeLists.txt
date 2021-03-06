INCLUDE(CMakeForceCompiler)

SET(CMAKE_SYSTEM_NAME Generic)

# this file was generated
CMAKE_MINIMUM_REQUIRED(VERSION 2.6)
PROJECT(shell)



SET(CMAKE_EXECUTABLE_SUFFIX)
# get rid of -rdynamic
SET(CMAKE_SHARED_LIBRARY_LINK_C_FLAGS)


ENABLE_LANGUAGE(ASM)
STRING(TOLOWER "${CMAKE_BUILD_TYPE}" CMAKE_BUILD_TYPE)


# -----------------------------------------------
# common settings
# -----------------------------------------------

# common asm flags
SET(CMAKE_ASM_FLAGS "${CMAKE_ASM_FLAGS} -mcpu=cortex-m4")
SET(CMAKE_ASM_FLAGS "${CMAKE_ASM_FLAGS} -mfloat-abi=soft")
SET(CMAKE_ASM_FLAGS "${CMAKE_ASM_FLAGS} -Xassembler --no-warn")
SET(CMAKE_ASM_FLAGS "${CMAKE_ASM_FLAGS} -std=gnu99")
SET(CMAKE_ASM_FLAGS "${CMAKE_ASM_FLAGS} -Wall")
SET(CMAKE_ASM_FLAGS "${CMAKE_ASM_FLAGS} -mthumb")
SET(CMAKE_ASM_FLAGS "${CMAKE_ASM_FLAGS} -g2")
SET(CMAKE_ASM_FLAGS "${CMAKE_ASM_FLAGS} -gdwarf-2")
SET(CMAKE_ASM_FLAGS "${CMAKE_ASM_FLAGS} -gstrict-dwarf")

# common asm defines
SET(CMAKE_ASM_FLAGS "${CMAKE_ASM_FLAGS} -DCPU_MK60DN512VMD10=1")
SET(CMAKE_ASM_FLAGS "${CMAKE_ASM_FLAGS} -DFSL_RTOS_MQX=1")
SET(CMAKE_ASM_FLAGS "${CMAKE_ASM_FLAGS} -DMQX_USE_IO_OLD=0")
SET(CMAKE_ASM_FLAGS "${CMAKE_ASM_FLAGS} -DPLATFORM_SDK_ENABLED=1")

# common c compiler flags
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -mcpu=cortex-m4")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -mfloat-abi=soft")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -fno-strict-aliasing")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wno-missing-braces")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=gnu99")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -ffunction-sections")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -fdata-sections")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -mthumb")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -g2")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -gdwarf-2")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -gstrict-dwarf")

# common c compiler defines
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -DCPU_MK60DN512VMD10=1")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -DFSL_RTOS_MQX=1")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -DMQX_USE_IO_OLD=0")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -DPLATFORM_SDK_ENABLED=1")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -D_AEABI_LC_CTYPE=C")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -D__STRICT_ANSI__=1")

# linker flags
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -mcpu=cortex-m4")
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -mfloat-abi=soft")
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -std=gnu99")
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -nostartfiles")
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -nodefaultlibs")
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -nostdlib")
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -Xlinker --gc-sections")
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -Xlinker -cref")
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -Xlinker -static")
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -mthumb")
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -g2")
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -gdwarf-2")
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -gstrict-dwarf")
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -Xlinker -z -Xlinker muldefs")
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -u __isr_vector")
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -Xlinker --defsym=__stack_size__=0x400")
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -Xlinker --defsym=__heap_size__=0x200")


IF(CMAKE_BUILD_TYPE MATCHES "int flash debug")
# -----------------------------------------------
# special settings for 'int flash debug'
# -----------------------------------------------

#   asm defines
    SET(CMAKE_ASM_FLAGS "${CMAKE_ASM_FLAGS} -D_DEBUG=1")

#   c compiler flags
    SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -O0")

#   c compiler defines
    SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -D_DEBUG=1")

# linker flags
    SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -Wl,-Map,intflash_debug.map")

    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/config/mcu/MK60D10")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/config/board/twrk60d100m")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/config/common")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../..")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/mqx/source/include")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/mqx/source/bsp")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../examples/twrk60d100m")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/devices/MK60D10/startup")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/devices/MK60D10/include")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/devices")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/CMSIS/Include")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/hal/inc")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/drivers/inc")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/drivers/src/enet")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/drivers/src/mpu")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/drivers/src/uart")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/utilities/inc")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../filesystem/mfs/source/mfs_sdcard/nio_esdhc")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/osa/inc")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/system/inc")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../filesystem/mfs/source/include")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../security/wolfssl/source/wolfssl")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../security/wolfssl/source")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../lib/twrk60d100m.armgcc/debug/rtcs")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../filesystem/mfs/lib/twrk60d100m.armgcc/debug/mfs")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/lib/twrk60d100m.armgcc/debug/nshell")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/lib/twrk60d100m.armgcc/debug/config")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/lib/twrk60d100m.armgcc/debug/mqx")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/lib/twrk60d100m.armgcc/debug/mqx_stdlib")

    SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -T${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/devices/MK60D10/linker/gcc/MK60DN512xxx10_flash.ld")


    SET(EXECUTABLE_OUTPUT_PATH "${CMAKE_CURRENT_SOURCE_DIR}/int flash debug")
ENDIF()

IF(CMAKE_BUILD_TYPE MATCHES "int flash release")
# -----------------------------------------------
# special settings for 'int flash release'
# -----------------------------------------------

#   asm defines
    SET(CMAKE_ASM_FLAGS "${CMAKE_ASM_FLAGS} -DNDEBUG=1")

#   c compiler flags
    SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Os")

#   c compiler defines
    SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -DNDEBUG=1")

# linker flags
    SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -Wl,-Map,intflash_release.map")

    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/config/mcu/MK60D10")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/config/board/twrk60d100m")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/config/common")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../..")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/mqx/source/include")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/mqx/source/bsp")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../examples/twrk60d100m")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/devices/MK60D10/startup")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/devices/MK60D10/include")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/devices")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/CMSIS/Include")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/hal/inc")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/drivers/inc")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/drivers/src/enet")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/drivers/src/mpu")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/drivers/src/uart")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/utilities/inc")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../filesystem/mfs/source/mfs_sdcard/nio_esdhc")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/osa/inc")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/system/inc")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../filesystem/mfs/source/include")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../security/wolfssl/source/wolfssl")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../security/wolfssl/source")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../lib/twrk60d100m.armgcc/release/rtcs")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../filesystem/mfs/lib/twrk60d100m.armgcc/release/mfs")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/lib/twrk60d100m.armgcc/release/nshell")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/lib/twrk60d100m.armgcc/release/config")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/lib/twrk60d100m.armgcc/release/mqx")
    INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/lib/twrk60d100m.armgcc/release/mqx_stdlib")

    SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -T${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../platform/devices/MK60D10/linker/gcc/MK60DN512xxx10_flash.ld")


    SET(EXECUTABLE_OUTPUT_PATH "${CMAKE_CURRENT_SOURCE_DIR}/int flash release")
ENDIF()



ADD_EXECUTABLE(
shell.elf
"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/config/mcu/MK60D10/mqx_sdk_config.h"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/config/board/twrk60d100m/user_config.h"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/config/common/small_ram_config.h"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/config/common/lite_config.h"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/config/common/verif_enabled_config.h"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../app_mqx.c"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../app_mqx.h"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../app_rtos.h"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../demo.c"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../main.h"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../config.h"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../demo_cmd.c"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/mqx/source/include/mqx.h"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/mqx/source/bsp/bsp.h"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../../common/hardware_init.c"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/mqx/source/bsp/bsp_config.h"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/mqx/source/bsp/init_bsp.c"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/mqx/source/bsp/mqx_main.c"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../examples/twrk60d100m/board.h"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../examples/twrk60d100m/board.c"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../examples/twrk60d100m/gpio_pins.h"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../examples/twrk60d100m/gpio_pins.c"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../examples/twrk60d100m/pin_mux.h"
"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../examples/twrk60d100m/pin_mux.c"
)


IF(CMAKE_BUILD_TYPE MATCHES "int flash debug")
    TARGET_LINK_LIBRARIES(shell.elf
        -Wl,--start-group
        -L"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../lib/ksdk_mqx_lib/armgcc/K60D10/debug"
        -lksdk_platform_mqx
        -L"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../lib/twrk60d100m.armgcc/debug/rtcs"
        -l_rtcs
        -L"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../filesystem/mfs/lib/twrk60d100m.armgcc/debug/mfs"
        -l_mfs
        -L"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/lib/twrk60d100m.armgcc/debug/nshell"
        -l_nshell
        -L"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/lib/twrk60d100m.armgcc/debug/mqx"
        -l_mqx
        -L"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/lib/twrk60d100m.armgcc/debug/mqx_stdlib"
        -l_mqx_stdlib
        -lgcc
        -lc
        -lsupc++
        -lm
        -lnosys
        -Wl,--end-group
    )
ENDIF()
IF(CMAKE_BUILD_TYPE MATCHES "int flash release")
    TARGET_LINK_LIBRARIES(shell.elf
        -Wl,--start-group
        -L"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../lib/ksdk_mqx_lib/armgcc/K60D10/release"
        -lksdk_platform_mqx
        -L"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../lib/twrk60d100m.armgcc/release/rtcs"
        -l_rtcs
        -L"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../filesystem/mfs/lib/twrk60d100m.armgcc/release/mfs"
        -l_mfs
        -L"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/lib/twrk60d100m.armgcc/release/nshell"
        -l_nshell
        -L"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/lib/twrk60d100m.armgcc/release/mqx"
        -l_mqx
        -L"${CMAKE_CURRENT_SOURCE_DIR}/../../../../../../../../rtos/mqx/lib/twrk60d100m.armgcc/release/mqx_stdlib"
        -l_mqx_stdlib
        -lgcc
        -lc
        -lsupc++
        -lm
        -lnosys
        -Wl,--end-group
    )
ENDIF()


