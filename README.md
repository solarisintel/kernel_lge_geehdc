
## mako(Nexus4) -> geehdc(L01E/LGL21) defconfig memo

1) architecture 
CONFIG_MACH_APQ8064_MAKO=y 
-> 
CONFIG_MACH_APQ8064_MAKO=y 
+CONFIG_MACH_APQ8064_J1D=y 
  
2) display  
CONFIG_FB_MSM_MIPI_DSI_LGIT=y 
CONFIG_FB_MSM_MIPI_LGIT_VIDEO_WXGA_PT=y 
CONFIG_FB_MSM_MIPI_LGIT_VIDEO_WXGA_PT_PANEL 
-> 
+# CONFIG_FB_MSM_MIPI_DSI_LGIT=y 
+# CONFIG_FB_MSM_MIPI_LGIT_VIDEO_WXGA_PT=y 
+# CONFIG_FB_MSM_MIPI_LGIT_VIDEO_WXGA_PT_PANEL 
+CONFIG_FB_MSM_MIPI_DSI_HITACHI=y 
+CONFIG_FB_MSM_MIPI_HITACHI_VIDEO_HD_PT=y 
+CONFIG_FB_MSM_MIPI_HITACHI_VIDEO_HD_PT_PANEL=y 
 
3) display touch sensor 
CONFIG_TOUCHSCREEN_LGE_SYNAPTICS=y 
CONFIG_TOUCH_REG_MAP_TM2000=y 
# CONFIG_TOUCHSCREEN_SYNAPTICS_I2C_RMI4 is not set 
-> 
CONFIG_TOUCHSCREEN_LGE_SYNAPTICS=y 
+CONFIG_TOUCHSCREEN_SYNAPTICS_I2C_RMI4=y 
CONFIG_TOUCH_REG_MAP_TM2000=y 
+CONFIG_TOUCH_REG_MAP_TM2372=y 
 
4) lcd backlight sensor 
CONFIG_BACKLIGHT_LM3530=y 
-> 
+# CONFIG_BACKLIGHT_LM3530 is not set 
+CONFIG_BACKLIGHT_LM3533=y 
 
5) camera sensor 
CONFIG_IMX111=y 
CONFIG_IMX119=y 
CONFIG_SEKONIX_LENS_ACT=y 
-> 
+# CONFIG_IMX111 is not set 
+# CONFIG_IMX111_ACT is not set 
+# CONFIG_SEKONIX_LENS_ACT is not set 
+CONFIG_IMX091=y 
+CONFIG_IMX091_ACT=y 
+CONFIG_IMX119=y 
+CONFIG_IMX091_EEPROM=y 
 
6) exetrnal sdcard support 
# CONFIG_MMC_MSM_SDC2_SUPPORT is not set
-# CONFIG_MMC_MSM_SDC3_SUPPORT is not set 
-> 
# CONFIG_MMC_MSM_SDC2_SUPPORT is not set 
+CONFIG_MMC_MSM_SDC3_SUPPORT=y 
 
7) sound codec 
CONFIG_WCD9304_CODEC=y 
CONFIG_WCD9310_CODEC=y 
-> 
CONFIG_WCD9304_CODEC=y 
CONFIG_WCD9310_CODEC=y 
+CONFIG_SOUND_CONTROL_HAX_GPL=y 
+CONFIG_SOUND_CONTROL_HAX_3_GPL=y 
 
8) display 
CONFIG_UPDATE_LCDC_LUT=y 
CONFIG_LCD_KCAL=y 
-> 
CONFIG_UPDATE_LCDC_LUT=y 
+# CONFIG_LCD_KCAL is not set 
 
9) no support NFC, MHL 
CONFIG_SLIMPORT_ANX7808=y 
CONFIG_BCM2079X=y 
-> 
+# CONFIG_SLIMPORT_ANX7808 is not set 
+# CONFIG_BCM2079X is not set 
 
10) no support HDMI 
CONFIG_FB_MSM_HDMI_MSM_PANEL=y 
CONFIG_FB_MSM_EXT_INTERFACE_COMMON=y 
CONFIG_FB_MSM_HDMI_COMMON=y 
CONFIG_FB_MSM_HDMI_3D=y 
-> 
+# CONFIG_FB_MSM_HDMI_MSM_PANEL is not set 
+# CONFIG_FB_MSM_EXT_INTERFACE_COMMON is not set 
+# CONFIG_FB_MSM_HDMI_COMMON is not set 
+# CONFIG_FB_MSM_HDMI_3D is not set 
 
11) no support wireless charger 
# CONFIG_WIRELESS_CHARGER is not set 

 modifed source 
<arch> 
include/mach/board_lge.h 
lge/mako/Kconfig 
lge/mako/board-mako-camera.c 
lge/mako/board-mako-display.c 
lge/mako/board-mako-gpiomux.c 
lge/mako/board-mako-input.c 
lge/mako/board-mako-misc.c 
lge/mako/board-mako-nfc.c 
lge/mako/board-mako-pmic.c 
lge/mako/board-mako-regulator.c 
lge/mako/board-mako-sound.c 
lge/mako/board-mako.c 
lge/mako/board-mako.h 
 
<touchscreen> 
input/touchscreen/Kconfig 
input/touchscreen/Makefile 
input/touchscreen/SynaImage.h 
input/touchscreen/cyttsp_core.c 
input/touchscreen/eeti_ts.c 
input/touchscreen/lge_touch_core.c 
input/touchscreen/touch_synaptics.c 
input/touchscreen/touch_synaptics_ds4_fw_upgrade.c 
input/touchscreen/tsc40.c 
input/touchscreen/usbtouchscreen.c 
linux/input/lge_touch_core.h 
linux/input/touch_synaptics.h 
 
<display> 
drivers/video/Kconfig 
drivers/video/Makefile 
video/msm/Kconfig 
video/msm/Makefile 
video/msm/external_common.c 
video/msm/msm_fb.c 
video/backlight/lm3533.c 
 
<sound>
include/linux/wcd9xxx/core.h 
drivers/mfd/wcd9xxx-core.c 
soc/codecs/Kconfig 
soc/codecs/Makefile 
soc/codecs/wcd9310.c 
soc/codecs/sound_control_gpl.c 
soc/codecs/sound_control_3_gpl.c 


