Python wrapper for the Deditec RO-Modules (RO-USB and RO-ETH)
#############################################################

Gives a convenient access to the Deditec RO-Series. 

From the defined constants you can estimate the wrappers' 
capabilities... Have fun!

    RO_USB1 =   7 # RO-USB-Serie
    RO_USB  =   7 # RO-USB-Serie
    RO_ETH  =   8 # RO-ETH-Serie

    # Special Function-Codes
    DAPI_SPECIAL_CMD_GET_MODULE_CONFIG  = 0x01
    DAPI_SPECIAL_CMD_TIMEOUT            = 0x02
    DAPI_SPECIAL_CMD_DA                 = 0x06
    DAPI_SPECIAL_CMD_COUNTER            = 0x08
    DAPI_SPECIAL_CMD_AD                 = 0x09
    DAPI_SPECIAL_CMD_CNT48              = 0x0b
    # values for PAR1
    DAPI_SPECIAL_GET_MODULE_CONFIG_PAR_DI               = 1
    DAPI_SPECIAL_GET_MODULE_CONFIG_PAR_DI_FF            = 7
    DAPI_SPECIAL_GET_MODULE_CONFIG_PAR_DI_COUNTER       = 8
    DAPI_SPECIAL_GET_MODULE_CONFIG_PAR_DO               = 2
    DAPI_SPECIAL_GET_MODULE_CONFIG_PAR_DX               = 3
    DAPI_SPECIAL_GET_MODULE_CONFIG_PAR_AD               = 4
    DAPI_SPECIAL_GET_MODULE_CONFIG_PAR_DA               = 5
    DAPI_SPECIAL_GET_MODULE_CONFIG_PAR_TEMP             = 9
    DAPI_SPECIAL_GET_MODULE_CONFIG_PAR_STEPPER          = 6
    DAPI_SPECIAL_GET_MODULE_CONFIG_PAR_CNT48            = 10
    DAPI_SPECIAL_GET_MODULE_CONFIG_PAR_PULSE_GEN        = 11
    DAPI_SPECIAL_GET_MODULE_CONFIG_PAR_PWM_OUT          = 12
    DAPI_SPECIAL_GET_MODULE_CONFIG_PAR_HW_INTERFACE1    = 13
    DAPI_SPECIAL_GET_MODULE_CONFIG_PAR_SW_FEATURE1      = 14
    DAPI_SPECIAL_GET_MODULE_CONFIG_PAR_HW_GROUP         = 15
    DAPI_SPECIAL_GET_MODULE_CONFIG_PAR_SW_CLASS         = 16
    DAPI_SPECIAL_GET_MODULE_CONFIG_PAR_MODULE_ID        = 17
    # values for  A/D and D/A Modes
    DAPI_ADDA_MODE_UNIPOL_10V                           = 0x00
    DAPI_ADDA_MODE_UNIPOL_5V                            = 0x01
    DAPI_ADDA_MODE_UNIPOL_2V5                           = 0x02
        
    DAPI_ADDA_MODE_BIPOL_10V                            = 0x40
    DAPI_ADDA_MODE_BIPOL_5V                             = 0x41
    DAPI_ADDA_MODE_BIPOL_2V5                            = 0x42

    DAPI_ADDA_MODE_BI_CAL_MODE                          = 0xfd
    #DAPI_ADDA_MODE_0_20mA_TESTMODE                     = 0xfe
    DAPI_ADDA_MODE_BIPOL_10V_TESTMODE                   = 0xff
        
    DAPI_ADDA_MODE_DA_DISABLE                           = 0x100
    DAPI_ADDA_MODE_DA_ENABLE                            = 0x200
    # special for AD
    DAPI_SPECIAL_AD_READ_MULTIPLE_AD                    = 1
    DAPI_ADDA_MODE_PREVENT_DAPI_MODE_ERROR              = 0x8000
    # special for D/A timeouts
    DAPI_SPECIAL_TIMEOUT_SET_VALUE_SEC                  = 1
    DAPI_SPECIAL_TIMEOUT_ACTIVATE                       = 2
    DAPI_SPECIAL_TIMEOUT_DEACTIVATE                     = 3
    DAPI_SPECIAL_TIMEOUT_GET_STATUS                     = 4
    # special for D/A
    DAPI_SPECIAL_DA_PAR_DA_LOAD_DEFAULT                 = 1
    DAPI_SPECIAL_DA_PAR_DA_SAVE_EEPROM_CONFIG           = 2
    DAPI_SPECIAL_DA_PAR_DA_LOAD_EEPROM_CONFIG           = 3
        
    # values for A/D and D/A units
    DAPI_ADDA_UNIT_ILLEGAL                              = 0x00
    DAPI_ADDA_UNIT_VOLT                                 = 0x01
    DAPI_ADDA_UNIT_MA                                   = 0x02
    # special for CNT8 units
    DAPI_CNT48_FILTER_20ns                              = 0x0000
    DAPI_CNT48_FILTER_100ns                             = 0x1000
    DAPI_CNT48_FILTER_250ns                             = 0x2000
    DAPI_CNT48_FILTER_500ns                             = 0x3000
    DAPI_CNT48_FILTER_1us                               = 0x4000
    DAPI_CNT48_FILTER_2_5us                             = 0x5000
    DAPI_CNT48_FILTER_5us                               = 0x6000
    DAPI_CNT48_FILTER_10us                              = 0x7000
    DAPI_CNT48_FILTER_25us                              = 0x8000
    DAPI_CNT48_FILTER_50us                              = 0x9000
    DAPI_CNT48_FILTER_100us                             = 0xA000
    DAPI_CNT48_FILTER_250us                             = 0xB000
    DAPI_CNT48_FILTER_500us                             = 0xC000
    DAPI_CNT48_FILTER_1ms                               = 0xD000
    DAPI_CNT48_FILTER_2_5ms                             = 0xE000
    DAPI_CNT48_FILTER_5ms                               = 0xF000
    
    DAPI_CNT48_MODE_COUNT_RISING_EDGE                   = 0x0000
    # DAPI_CNT48_MODE_COUNT_RISING_EDGE_X2              = 0x0001
    # DAPI_CNT48_MODE_COUNT_RISING_EDGE_X4              = 0x0002
    DAPI_CNT48_MODE_T                                   = 0x000D
    DAPI_CNT48_MODE_FREQUENCY                           = 0x000E
    DAPI_CNT48_MODE_PWM                                 = 0x000F
    
    DAPI_CNT48_SUBMODE_NO_RESET                         = 0x0000
    DAPI_CNT48_SUBMODE_RESET_WITH_READ                  = 0x0010
    DAPI_CNT48_SUBMODE_NO_RESET_NO_HW_RESET             = 0x0020
    DAPI_CNT48_SUBMODE_RESET_WITH_READ_NO_HW_RESET      = 0x0030
    DAPI_CNT48_SUBMODE_RESET_ON_CH_7                    = 0x0070
    DAPI_CNT48_SUBMODE_LATCH_COMMON                     = 0x0080
    DAPI_CNT48_SUBMODE_FREQUENCY_TIME_BASE_1ms          = 0x0030
    DAPI_CNT48_SUBMODE_FREQUENCY_TIME_BASE_10ms         = 0x0020
    DAPI_CNT48_SUBMODE_FREQUENCY_TIME_BASE_100ms        = 0x0010
    DAPI_CNT48_SUBMODE_FREQUENCY_TIME_BASE_1sec         = 0x0000
    # specials for cnt8...
    DAPI_SPECIAL_COUNTER_LATCH_ALL                      = 1
    DAPI_SPECIAL_COUNTER_LATCH_ALL_WITH_RESET           = 2
    DAPI_SPECIAL_COUNTER_PRELOAD_SET                    = 3
    DAPI_SPECIAL_COUNTER_PRELOAD_GET                    = 4
    DAPI_SPECIAL_COUNTER_MODE_SET                       = 5
    DAPI_SPECIAL_COUNTER_MODE_GET                       = 6
    DAPI_CPECIAL_COUNTER_GET                            = 7
    
    DAPI_SPECIAL_CNT48_RESET_SINGLE                     = 1
    DAPI_SPECIAL_CNT48_RESET_GROUP8                     = 2
    DAPI_SPECIAL_CNT48_LATCH_GROUP8                     = 3
    DAPI_SPECIAL_CNT48_DI_GET1                          = 4
    
    # specials for DI units
    
    ups! still to do...
    
    
    # defines from delib_error_codes.h
    DAPI_ERR_NONE = 0