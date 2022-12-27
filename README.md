
## mako(Nexus4) -> geehdc(L01E/LGL21) defconfig memo
<br>
1) architecture <br>
CONFIG_MACH_APQ8064_MAKO=y <br>
-\> <br>
CONFIG_MACH_APQ8064_MAKO=y <br>
+CONFIG_MACH_APQ8064_J1D=y <br>
 <br>
2) display <br>
CONFIG_FB_MSM_MIPI_DSI_LGIT=y <br>
CONFIG_FB_MSM_MIPI_LGIT_VIDEO_WXGA_PT=y <br>
CONFIG_FB_MSM_MIPI_LGIT_VIDEO_WXGA_PT_PANEL <br>
-\><br> 
+\# CONFIG_FB_MSM_MIPI_DSI_LGIT=y <br>
+\# CONFIG_FB_MSM_MIPI_LGIT_VIDEO_WXGA_PT=y <br>
+\# CONFIG_FB_MSM_MIPI_LGIT_VIDEO_WXGA_PT_PANEL <br>
+CONFIG_FB_MSM_MIPI_DSI_HITACHI=y <br>
+CONFIG_FB_MSM_MIPI_HITACHI_VIDEO_HD_PT=y <br>
+CONFIG_FB_MSM_MIPI_HITACHI_VIDEO_HD_PT_PANEL=y<br> 
 <br>
3) display touch sensor <br>
CONFIG_TOUCHSCREEN_LGE_SYNAPTICS=y <br>
CONFIG_TOUCH_REG_MAP_TM2000=y <br>
\# CONFIG_TOUCHSCREEN_SYNAPTICS_I2C_RMI4 is not set <br>
-\> <br>
CONFIG_TOUCHSCREEN_LGE_SYNAPTICS=y <br>
+CONFIG_TOUCHSCREEN_SYNAPTICS_I2C_RMI4=y <br> 
CONFIG_TOUCH_REG_MAP_TM2000=y <br>
+CONFIG_TOUCH_REG_MAP_TM2372=y <br>
 <br>
4) lcd backlight sensor <br>
CONFIG_BACKLIGHT_LM3530=y <br>
-\> <br>
+\# CONFIG_BACKLIGHT_LM3530 is not set <br>
+CONFIG_BACKLIGHT_LM3533=y <br>
<br> 
5) camera sensor <br>
CONFIG_IMX111=y <br>
CONFIG_IMX119=y <br>
CONFIG_SEKONIX_LENS_ACT=y <br>
-\> <br>
+\# CONFIG_IMX111 is not set <br>
+\# CONFIG_IMX111_ACT is not set <br>
+\# CONFIG_SEKONIX_LENS_ACT is not set<br> 
+CONFIG_IMX091=y <br>
+CONFIG_IMX091_ACT=y <br>
+CONFIG_IMX119=y <br>
+CONFIG_IMX091_EEPROM=y <br>
 <br>
6) exetrnal sdcard support <br>
\# CONFIG_MMC_MSM_SDC2_SUPPORT is not set<br>
-\# CONFIG_MMC_MSM_SDC3_SUPPORT is not set <br>
-\> <br>
\# CONFIG_MMC_MSM_SDC2_SUPPORT is not set <br>
+CONFIG_MMC_MSM_SDC3_SUPPORT=y <br>
 <br>
7) sound codec <br>
CONFIG_WCD9304_CODEC=y<br> 
CONFIG_WCD9310_CODEC=y <br>
-\> <br>
CONFIG_WCD9304_CODEC=y <br>
CONFIG_WCD9310_CODEC=y <br>
+CONFIG_SOUND_CONTROL_HAX_GPL=y <br>
+CONFIG_SOUND_CONTROL_HAX_3_GPL=y <br>
 <br>
8) display <br>
CONFIG_UPDATE_LCDC_LUT=y <br>
CONFIG_LCD_KCAL=y <br>
-\> <br>
CONFIG_UPDATE_LCDC_LUT=y <br>
+\# CONFIG_LCD_KCAL is not set <br>
 <br>
9) no support NFC, MHL <br>
CONFIG_SLIMPORT_ANX7808=y <br>
CONFIG_BCM2079X=y <br>
-\> <br>
+\# CONFIG_SLIMPORT_ANX7808 is not set <br>
+\# CONFIG_BCM2079X is not set <br>
 <br>
10) no support HDMI <br>
CONFIG_FB_MSM_HDMI_MSM_PANEL=y <br>
CONFIG_FB_MSM_EXT_INTERFACE_COMMON=y <br>
CONFIG_FB_MSM_HDMI_COMMON=y <br>
CONFIG_FB_MSM_HDMI_3D=y <br>
-\> <br>
+\# CONFIG_FB_MSM_HDMI_MSM_PANEL is not set <br>
+\# CONFIG_FB_MSM_EXT_INTERFACE_COMMON is not set<br> 
+\# CONFIG_FB_MSM_HDMI_COMMON is not set <br>
+\# CONFIG_FB_MSM_HDMI_3D is not set <br>
 <br>
11) no support wireless charger <br>
\# CONFIG_WIRELESS_CHARGER is not set<br> 
<br>
 modifed source <br>
[arch] <br>
include/mach/board_lge.h <br>
lge/mako/Kconfig <br>
lge/mako/board-mako-camera.c <br>
lge/mako/board-mako-display.c <br>
lge/mako/board-mako-gpiomux.c <br>
lge/mako/board-mako-input.c <br>
lge/mako/board-mako-misc.c <br>
lge/mako/board-mako-nfc.c <br>
lge/mako/board-mako-pmic.c <br>
lge/mako/board-mako-regulator.c<br> 
lge/mako/board-mako-sound.c <br>
lge/mako/board-mako.c <br>
lge/mako/board-mako.h <br>
 <br>
[touchscreen] <br>
input/touchscreen/Kconfig <br>
input/touchscreen/Makefile <br>
input/touchscreen/SynaImage.h <br>
input/touchscreen/cyttsp_core.c <br>
input/touchscreen/eeti_ts.c <br>
input/touchscreen/lge_touch_core.c <br>
input/touchscreen/touch_synaptics.c <br>
input/touchscreen/touch_synaptics_ds4_fw_upgrade.c <br>
input/touchscreen/tsc40.c <br>
input/touchscreen/usbtouchscreen.c <br>
linux/input/lge_touch_core.h <br>
linux/input/touch_synaptics.h <br>
 <br>
[display] <br>
drivers/video/Kconfig <br>
drivers/video/Makefile <br>
video/msm/Kconfig  <br>
video/msm/Makefile  <br>
video/msm/external_common.c  <br>
video/msm/msm_fb.c  <br>
video/backlight/lm3533.c  <br>
  <br>
[sound] <br>
include/linux/wcd9xxx/core.h  <br>
drivers/mfd/wcd9xxx-core.c  <br>
soc/codecs/Kconfig  <br>
soc/codecs/Makefile  <br>
soc/codecs/wcd9310.c  <br>
soc/codecs/sound_control_gpl.c  <br>
soc/codecs/sound_control_3_gpl.c  <br>


