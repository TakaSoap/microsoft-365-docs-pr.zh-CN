---
title: 载入非持久性虚拟桌面基础结构 (VDI) 设备。
description: 在 VDI (虚拟桌面基础结构上) 包，以便它们可以载入到 Microsoft Defender for Endpoint 服务。
keywords: configure virtual desktop infrastructure (VDI) device， vdi， device management， configure Microsoft Defender for Endpoint， endpoints
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.date: 02/14/2022
ms.technology: mde
ms.openlocfilehash: 3e430d44789a1f3c43ec55a20ee7e06521f2dcaf
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2022
ms.locfileid: "62807628"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-in-microsoft-365-defender"></a>将非永久性虚拟桌面基础结构 (VDI) 设备载入Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- 虚拟桌面基础结构 (VDI) 设备
- Windows 10、Windows 11、Windows Server 2019、Windows Server 2022、Windows Server 2008R2/2012R2/2016

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configvdi-abovefoldlink)。

 > [!NOTE]
  > **永久性 VDI** - [将永久性 VDI 计算机](configure-endpoints.md) 载入 Microsoft Defender for Endpoint 的处理方式与载入物理计算机（如台式机或笔记本电脑）的方式相同。 组策略Microsoft Endpoint Manager和其他方法可用于载入永久计算机。 在 Microsoft 365 Defender门户中， (https://security.microsoft.com)下选择你的首选载入方法，然后按照该类型的说明进行操作。 

## <a name="onboarding-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>在 VDI 设备上载入非永久性 () 基础结构

Defender for Endpoint 支持非永久性 VDI 会话载入。

载入 VDIS 时可能存在相关挑战。 以下是此方案的典型挑战：

- 即时提前载入短期会话，此会话在实际预配之前必须载入到 Defender for Endpoint。
- 设备名称通常重新用于新会话。

VDI 设备可以在 Defender for Endpoint 门户中显示为：

- 每台设备的单个条目。

  > [!NOTE]
  > 在这种情况下，创建会话时必须配置相同的设备名称，例如使用无人参与应答文件。

- 每个设备有多个条目 - 每个会话一个条目。

以下步骤将指导你完成载入 VDI 设备，并重点介绍单项和多条目的步骤。

> [!WARNING]
> 对于资源配置较低的环境，VDI 启动过程可能会减慢 Defender for Endpoint 传感器载入的速度。

### <a name="for-windows-10-or-windows-11-or-windows-server-2019-or-windows-server-2022"></a>对于 Windows 10、Windows 11、Windows Server 2019 或 Windows Server 2022

1.  打开 VDI 配置包.zip文件 (*WindowsDefenderATPOnboardingPackage.zip)* 从服务载入向导下载的内容。 还可以从应用门户获取Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">包</a>：

    1. 在导航窗格中，**选择"设置** > **EndpointsDevice** >  **managementOnboarding** > "。

    1. 选择操作系统。

    1.  在 **"部署方法"** 字段中，选择"非永久性终结点的 **VDI 载入脚本"**。

    1. 单击 **下载程序包** 并保存.zip文件。

2. 将文件从从 .zip 文件中提取的 WindowsDefenderATPOnboardingPackage 文件夹复制到路径 下的黄金/主映像 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`。
    1. 如果要为每台设备实现多个条目（每个会话一个条目），请复制 WindowsDefenderATPOnboardingScript.cmd。
    2. 如果你要针对每台设备实现单个条目，请同时复制 Onboard-NonPersistentMachine.ps1 和 WindowsDefenderATPOnboardingScript.cmd。

    > [!NOTE]
    > 如果看不到该文件夹 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` ，它可能处于隐藏状态。 你需要从文件资源管理器中选择显示隐藏 **文件和** 文件夹选项。

3. 打开本地组策略编辑器窗口并导航 **到计算机**\>配置 **Windows 设置** \> **脚本** \> **启动**。

   > [!NOTE]
   > 域组策略还可用于载入非永久性 VDI 设备。

4. 根据你要实现的方法，请按照相应步骤操作：
    - 对于每台设备的单个条目：

         选择 **"PowerShell 脚本**"选项卡，然后单击"添加 (Windows资源管理器将在你之前复制载入脚本的路径中直接) 。 导航到载入 PowerShell 脚本 `Onboard-NonPersistentMachine.ps1`。 无需指定其他文件，因为它将自动触发。

    - 对于每台设备的多个条目：

         选择"**脚本**"选项卡，**然后单击"添加** (Windows资源管理器将在你之前复制载入脚本的路径中直接) 。 导航到载入 Bash 脚本 `WindowsDefenderATPOnboardingScript.cmd`。

5. 测试解决方案：
   1. 创建具有一台设备的池。
   2. 登录到设备。
   3. 从设备注销。
   4. 使用其他用户登录到设备。
   5. 根据你要实现的方法，请按照相应步骤操作：
      - For single entry for each device： Check only one entry in Microsoft 365 Defender portal.
      - For multiple entries for each device： Check multiple entries in Microsoft 365 Defender portal.

6. 单击 **导航窗格上的** "设备列表"。

7. 通过输入设备名称并选择设备作为搜索类型 **来** 使用搜索函数。

## <a name="for-downlevel-skus-windows-server-2008-r22012-r22016"></a>对于下层 SKUs (Windows Server 2008 R2/2012 R2/2016) 

> [!NOTE]
> 以下注册表仅在目标是实现"每个设备的单个条目"时相关。

1. 将注册表值设置为：

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    或者使用命令行：

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. 按照 [服务器载入过程操作](configure-server-endpoints.md)。 

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>使用 VDI 映像更新 (虚拟) 基础结构

作为最佳实践，我们建议使用脱机维护工具修补黄金/主映像。

例如，可以使用以下命令在映像保持脱机时安装更新：

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing"
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

有关 DISM 命令和脱机服务的详细信息，请参阅以下文章：

- [使用 DISM Windows映像](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [DISM 映像管理Command-Line选项](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [减小脱机映像中组件存储Windows大小](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

如果脱机服务不是非永久性 VDI 环境的可行选项，应执行以下步骤以确保一致性和传感器运行状况：

1. 启动主映像进行联机维护或修补后，运行载出脚本以关闭 Defender for Endpoint 传感器。 有关详细信息，请参阅使用本地 [脚本的载出设备](configure-endpoints-script.md#offboard-devices-using-a-local-script)。

2. 在 CMD 窗口中运行以下命令，确保传感器已停止：

   ```console
   sc query sense
   ```

3. 根据需要为映像提供服务。

4. 使用可下载的 https://download.sysinternals.com/files/PSTools.zip) PsExec.exe (运行以下命令，以清理传感器自启动后可能累积的网络文件夹内容：

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. 像平常一样封装黄金/主图像。

## <a name="related-topics"></a>相关主题
- [使用组策略载入 Windows 设备](configure-endpoints-gp.md)
- [使用 Microsoft Endpoint Configuration Manager 载入 Windows 设备](configure-endpoints-sccm.md)
- [使用移动设备管理工具载入 Windows 设备](configure-endpoints-mdm.md)
- [使用本地脚本载入 Windows 设备](configure-endpoints-script.md)
- [Microsoft Defender 终结点载入问题疑难解答](troubleshoot-onboarding.md)
