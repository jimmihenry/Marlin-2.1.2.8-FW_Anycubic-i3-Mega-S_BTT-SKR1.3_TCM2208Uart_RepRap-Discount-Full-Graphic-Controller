Changes that were made to the Original Marlin 2.1.2.8 Firmware in order to suit the hardware of the Anycubuc i3 Mega S
in addition to the SKR1.3 BigTreeTech board.

MarlinAnycubicSkr1.3UartRepRapDiscount_2004_2.1.2.8
=============================================================================================================
Config.h
-------------------------------------------------------------------------------------------------------------
// @section info

// Author info of this build printed to the host during boot and M115
#define STRING_CONFIG_H_AUTHOR "(Jimmi Henry Mod)" // Who made the changes.

// Choose the name from boards.h that matches your setup
#define MOTHERBOARD BOARD_BTT_SKR_V1_3
-------------------------------------------------------------------------------------------------------------
// @section serial

#define SERIAL_PORT -1
#define SERIAL_PORT_2 0	
#define BAUDRATE 115200
// Name displayed in the LCD "Ready" message and Info menu
#define CUSTOM_MACHINE_NAME "Analcubic i3"
-------------------------------------------------------------------------------------------------------------
// @section stepper drivers
#define X_DRIVER_TYPE  TMC2208
#define Y_DRIVER_TYPE  TMC2208
#define Z_DRIVER_TYPE  TMC2208
#define Z2_DRIVER_TYPE TMC2208
#define E0_DRIVER_TYPE TMC2208
-------------------------------------------------------------------------------------------------------------
// @section psu control
#define TEMP_SENSOR_0 5
--------------------------------------------------------------------------------------------------------------
// @section hotend temp
#define DEFAULT_KP_LIST {  15.94,  15.94 }
#define DEFAULT_KI_LIST {   1.17,   1.17 }
#define DEFAULT_KD_LIST { 54.19, 54.19 }
#else    
#define DEFAULT_KP  15.94
#define DEFAULT_KI   1.17
#define DEFAULT_KD 54.19
-------------------------------------------------------------------------------------------------------------
// @section bed temp
#define PIDTEMPBED
// Anycubic i3 Mega Ultrabase (0.9Ω @ 22°C)
#define DEFAULT_BED_KP 251.78
#define DEFAULT_BED_KI 49.57
#define DEFAULT_BED_KD 319.73
#define EXTRUDE_MAXLENGTH 600
-------------------------------------------------------------------------------------------------------------
// @section endstops
#define USE_ZMAX_PLUG
#define X_MIN_ENDSTOP_INVERTING true 	    // Set to true to invert the logic of the endstop.
#define Y_MIN_ENDSTOP_INVERTING true 	    // Set to true to invert the logic of the endstop.
#define Z_MIN_ENDSTOP_INVERTING true 	    // Set to true to invert the logic of the endstop.
-------------------------------------------------------------------------------------------------------------
// @section motion
#define DEFAULT_AXIS_STEPS_PER_UNIT   { 80, 80, 400, 384 }
#define DEFAULT_MAX_FEEDRATE          { 300, 300, 5, 60 }
#define DEFAULT_MAX_ACCELERATION      { 1200, 1000, 60, 10000 }
#define DEFAULT_ACCELERATION          1200    // X, Y, Z and E acceleration for printing moves	
#define DEFAULT_TRAVEL_ACCELERATION   1500    // X, Y, Z acceleration for travel (non printing) moves
#define DEFAULT_XJERK 7.0
#define DEFAULT_YJERK 5.0
-------------------------------------------------------------------------------------------------------------
// @section probes
//#define Z_MIN_PROBE_USES_Z_MIN_ENDSTOP_PIN
#define NOZZLE_TO_PROBE_OFFSET { 75, 5, -2 }
-------------------------------------------------------------------------------------------------------------
// @section motion
#define INVERT_X_DIR true
#define INVERT_Y_DIR false
#define INVERT_Z_DIR true
-------------------------------------------------------------------------------------------------------------
// @section extruder	
// For direct drive extruder v9 set to true, for geared extruder set to false.
#define INVERT_E0_DIR false
-------------------------------------------------------------------------------------------------------------
// @section geometry
#define X_BED_SIZE 210
#define Y_BED_SIZE 210
#define X_MIN_POS -10
#define Y_MIN_POS -11
#define Z_MAX_POS 250	
#define FILAMENT_RUNOUT_SENSOR
#define FIL_RUNOUT_STATE     HIGH        // Pin state indicating that filament is NOT present.
-------------------------------------------------------------------------------------------------------------
// @section eeprom
#define EEPROM_SETTINGS     		         // Persistent storage with M500 and M501
-------------------------------------------------------------------------------------------------------------
// @section units
#define PREHEAT_1_TEMP_HOTEND 200
#define PREHEAT_1_TEMP_BED     50
#define PREHEAT_2_TEMP_HOTEND 235
#define PREHEAT_2_TEMP_BED    85
#define NOZZLE_PARK_FEATURE
-------------------------------------------------------------------------------------------------------------
// @section interface
#define DISPLAY_CHARSET_HD44780 WESTERN
#define SDSUPPORT
#define SPEAKER
-------------------------------------------------------------------------------------------------------------
// @section lcd
#define REPRAP_DISCOUNT_SMART_CONTROLLER
-------------------------------------------------------------------------------------------------------------
// @section fans
#define FAN_SOFT_PWM
=============================================================================================================
Config_adv.h
-------------------------------------------------------------------------------------------------------------
// @section fans
#define USE_CONTROLLER_FAN
#define CONTROLLER_FAN_PIN P2_03          // Set a custom pin for the controller fan
#define CONTROLLERFAN_IDLE_TIME        120// (seconds) Extra time to keep the fan running after disabling motors
#define E0_AUTO_FAN_PIN P2_04          	  // steuert exakt den Steckplatz an, der auf dem SKR 1.3 mit HE1 beschriftet ist.
#define EXTRUDER_AUTO_FAN_TEMPERATURE 50
#define EXTRUDER_AUTO_FAN_SPEED       255 // Volle Pulle bei über 50 Grad//
#define E0_AUTO_FAN_PIN -1
#define Z_MULTI_ENDSTOPS          	      // Other Z axes have their own endstops
-------------------------------------------------------------------------------------------------------------
// @section extruder
#define LIN_ADVANCE
#define ADVANCE_K { 0.0 }    // (mm) Compression length per 1mm/s extruder speed, per extruder
#define ADVANCE_K 0.0        // (mm) Compression length applying to all extruders
-------------------------------------------------------------------------------------------------------------
// @section gcode
#define MAX_CMD_SIZE 128
#define BUFSIZE 32
#define TX_BUFFER_SIZE 32
#define RX_BUFFER_SIZE 128
#define EMERGENCY_PARSER
-------------------------------------------------------------------------------------------------------------
// @section advanced pause
#define ADVANCED_PAUSE_FEATURE
#define FILAMENT_CHANGE_UNLOAD_LENGTH      550  // (mm) The length of filament for a complete unload.
#define FILAMENT_CHANGE_FAST_LOAD_LENGTH   540  // (mm) Load length of filament, from extruder gear to nozzle.
#define ADVANCED_PAUSE_PURGE_LENGTH         20  // (mm) Length to extrude after loading.
#define ADVANCED_PAUSE_RESUME_PRIME          2  // (mm) Extra distance to prime nozzle after returning from park.
#define PARK_HEAD_ON_PAUSE                      // Park the nozzle during pause and filament change.
-------------------------------------------------------------------------------------------------------------
// @section tmc_smart
#define X_CURRENT       600                    // (mA) RMS current. Multiply by 1.414 for peak current.
#define Y_CURRENT       600
#define Z_CURRENT       600
#define E0_CURRENT      550
-------------------------------------------------------------------------------------------------------------
// @section tmc/stealthchop
//#define STEALTHCHOP_E
-------------------------------------------------------------------------------------------------------------
// @section host
#define HOST_ACTION_COMMANDS
#define HOST_PROMPT_SUPPORT                   // Initiate host prompts to get user feedback
=============================================================================================================
