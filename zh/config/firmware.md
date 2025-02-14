# 加载固件

_QGroundControl_ **desktop** versions can be used to install PX4 firmware onto [Pixhawk-series](../getting_started/flight_controller_selection.md) flight-controller boards.

:::warning
**Before you start installing Firmware** all USB connections to the vehicle must be _disconnected_ (both direct or through a telemetry radio). The vehicle must _not be_ powered by a battery.
:::

## 安装稳定的PX4版本

Generally you should use the most recent _released_ version of PX4, in order to benefit from bug fixes and get the latest and greatest features.

:::tip
This is the version that is installed by default.
:::

To install PX4:

1. Start _QGroundControl_ and connect the vehicle.
1. Select **"Q" icon > Vehicle Setup > Firmware** (sidebar) to open _Firmware Setup_.

   ![Firmware disconnected](../../assets/qgc/setup/firmware/firmware_disconnected.png)

1. Connect the flight controller directly to your computer via USB.

   :::note
Connect directly to a powered USB port on your machine (do not connect through a USB hub).
:::

1. Select the **PX4 Pro Stable Release vX.x.x** option to install the latest stable version of PX4 _for your flight controller_ (autodetected).

   ![Install PX4 default](../../assets/qgc/setup/firmware/firmware_connected_default_px4.png)

1. 单击 **OK** 按钮开始更新。

   The firmware will then proceed through a number of upgrade steps (downloading new firmware, erasing old firmware etc.). Each step is printed to the screen and overall progress is displayed on a progress bar.

   ![Firmware upgrade complete](../../assets/qgc/setup/firmware/firmware_upgrade_complete.png)

   Once the firmware has completed loading, the device/vehicle will reboot and reconnect.

:::tip
If _QGroundControl_ installs the FMUv2 target (see console during installation) and you have a newer board, you may need to [update the bootloader](#bootloader) in order to access all the memory on your flight controller.
:::

Next you will need to specify the [vehicle airframe](../config/airframe.md) (and then sensors, radio, etc.)

<a id="custom"></a>

## 安装PX4 Main, Beta或自定义固件

To install a different version of PX4:

1. 如上所述连接飞行器，并选择 **PX4 飞行栈 vX.x.x Stagable Release**. ![安装 PX4 版本](../../assets/qgc/setup/firmware/qgc_choose_firmware.png)
1. 检查 **高级设置** 并从下拉列表中选择版本：
   - **标准版本 (稳定):** 默认版本 (即无需使用高级设置来安装！)
   - **Beta 测试(beta)：** 测试/候选版本。 只有当新版本准备完毕时才可用。
   - **Developer Build (master):** PX4/PX4-Autopilot _主分支_ 最新版本。
   - **自定义固件文件...:** 自定义固件文件 (例如你已在本地构建的)。 如果选择 Custom firmware file ，您需要在下一步中从文件系统中选择自定义固件。

Firmware update then continues as before.

<a id="bootloader"></a>

## Bootloader 更新

硬件通常预先安装匹配版本的引导程序。

您可能需要更新的是安装较新的 Pixhawk 板FMUv2 固件 。 If _QGroundControl_ installs the FMUv2 target (see console during installation), and you have a newer board, you may need to update the bootloader in order to access all the memory on your flight controller.

![FMUv2 更新](../../assets/qgc/setup/firmware/bootloader_update.jpg)

您可以按照 [引导加载器更新 > FMUv2 启动加载器更新](../advanced_config/bootloader_update.md#fmuv2-bootloader-update)

## 更多信息

- [QGroundControl 用户指南>固件](https://docs.qgroundcontrol.com/master/en/SetupView/Firmware.html)。
- [PX4 Setup Video](https://youtu.be/91VGmdSlbo4) (Youtube)
