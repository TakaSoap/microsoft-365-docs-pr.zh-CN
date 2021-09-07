---
title: 载入非持久性虚拟桌面基础结构 (VDI) 设备。
description: 在 VDI (虚拟桌面基础结构) 包，以便它们可以载入到 Microsoft Defender for Endpoint 服务。
keywords: configure virtual desktop infrastructure (VDI) device， vdi， device management， configure Microsoft Defender for Endpoint， endpoints
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: 772c032bd44ab8f26e3a6fb6d5e9cd0092bd5826
ms.sourcegitcommit: af575ade7b187af70f94db904b03f0471f56452a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2021
ms.locfileid: "53591147"
---
# <a name="onboarding-non-persistent-virtual-desktop-infrastructure-devices"></a>载入非永久性虚拟桌面基础结构设备


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- 虚拟桌面基础结构 (VDI) 设备
- Windows 10、Windows Server 2019、Windows Server 2008R2/2012R2/2016

>想要体验适用于终结点的 Defender？ [注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)。

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>载入非持久性虚拟桌面基础结构 (VDI) 设备。

Defender for Endpoint 支持非永久性 VDI 会话载入。 

载入 VDIS 时可能存在相关挑战。 以下是此方案的典型挑战：

- 即时提前载入短期会话，此会话在实际预配之前必须载入到 Defender for Endpoint。
- 设备名称通常重新用于新会话。

VDI 设备可以在 Defender for Endpoint 门户中显示为：

- 每台设备的单个条目。

  > [!NOTE]
  > 在这种情况下， *必须在创建会话* 时配置相同的设备名称，例如使用无人参与应答文件。

- 每个设备有多个条目 - 每个会话一个条目。

以下步骤将指导你完成载入 VDI 设备，并重点介绍单项和多条目的步骤。

>[!WARNING]
> 对于资源配置较低的环境，VDI 启动过程可能会减慢 Defender for Endpoint 传感器载入的速度。 


### <a name="for-windows-10-or-windows-server-2019"></a>For Windows 10 or Windows Server 2019

1.  打开 VDI 配置包.zip文件 *(WindowsDefenderATPOnboardingPackage.zip)* 从服务载入向导下载的内容。 还可以从应用门户获取[Microsoft 365 Defender包](https://security.microsoft.com/)：

    1. 在导航窗格中，**选择"设置**  >  **终结点**  >  **设备管理**  >  **载入"。**

    1. 选择Windows 10操作系统。

    1.  在 **"部署方法"** 字段中，选择 **"非永久性终结点的 VDI 载入脚本"。**

    1. 单击 **下载程序包** 并保存.zip文件。

2. 将文件从 windowsDefenderATPOnboardingPackage 文件夹中从 .zip 文件复制到路径 `golden/master` 下的映像 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 中。 

    1. 如果你未针对每台设备实现单个条目，请复制 WindowsDefenderATPOnboardingScript.cmd。

    1. 如果你要针对每台设备实现单个条目，请同时复制 Onboard-NonPersistentMachine.ps1 和 WindowsDefenderATPOnboardingScript.cmd。
    
    > [!NOTE]
    > 如果看不到该文件夹 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` ，它可能处于隐藏状态。 你需要从文件资源管理器中选择显示隐藏 **文件和** 文件夹选项。

3. 打开本地组策略编辑器窗口并导航 **到计算机配置**  >  **Windows 设置**  >  **脚本**  >  **启动**。

   > [!NOTE]
   > 域组策略还可用于载入非永久性 VDI 设备。

4. 根据你要实现的方法，请按照相应步骤操作：

    - 对于每台设备的单个条目：
   
         选择 **"PowerShell 脚本**"选项卡，然后单击"添加 (Windows资源管理器将在你之前复制载入脚本的路径中直接) 。 导航到载入 PowerShell 脚本 `Onboard-NonPersistentMachine.ps1` 。 无需指定其他文件，因为它将自动触发。
   
    - 对于每台设备的多个条目：
   
         选择"**脚本**"选项卡，然后单击 **"添加** (Windows资源管理器将在你之前复制载入脚本的路径中直接) 。 导航到载入 Bash 脚本 `WindowsDefenderATPOnboardingScript.cmd` 。

5. 测试解决方案：

   1. 创建具有一台设备的池。
      
   1. 登录到设备。
      
   1. 从设备注销。

   1. 使用其他用户登录到设备。
      
   1. 根据你要实现的方法，请按照相应步骤操作：

   - 对于每台设备的单个条目： 

     仅检查门户中的Microsoft 365 Defender条目。

   - 对于每台设备的多个条目： 

     在门户中检查Microsoft 365 Defender条目。


6. 单击 **导航窗格上的** "设备列表"。

7. 通过输入设备名称并选择设备作为搜索类型 **来** 使用搜索函数。


## <a name="for-downlevel-skus"></a>对于下层 SKUs

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

2. 按照 [服务器载入过程操作](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)。 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>使用 VDI 映像更新 (虚拟) 基础结构
作为最佳实践，我们建议使用脱机维护工具修补黄金/主映像。<br>
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

4. 使用可下载的 PsExec.exe (运行以下命令，以清理传感器自启动后可能累积的网络 https://download.sysinternals.com/files/PSTools.zip) 文件夹内容：

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. 像平常一样封装黄金/主图像。

## <a name="related-topics"></a>相关主题
- [使用Windows 10载入设备](configure-endpoints-gp.md)
- [使用Windows 10载入Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [使用移动设备管理工具载入 Windows 10 设备](configure-endpoints-mdm.md)
- [使用本地脚本载入 Windows 10 设备](configure-endpoints-script.md)
- [Microsoft Defender 终结点载入问题疑难解答](troubleshoot-onboarding.md)
