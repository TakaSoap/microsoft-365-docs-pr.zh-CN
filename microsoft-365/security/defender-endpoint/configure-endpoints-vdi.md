---
title: 载入非持久性虚拟桌面基础结构 (VDI) 设备。
description: 将配置包部署到 VDI (虚拟桌面) ，以便载入到 Microsoft Defender for Endpoint 服务。
keywords: 配置虚拟桌面基础结构 (VDI) 设备， vdi， 设备管理， 配置 Microsoft Defender for Endpoint， 终结点
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
ms.openlocfilehash: e292c2f1e0d01e51e3962b71a940927078ab95ad
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634704"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-in-microsoft-365-defender"></a>将非永久性虚拟桌面基础结构 (VDI) 设备载入Microsoft 365 Defender

虚拟桌面基础结构 (VDI) 是一个 IT 基础结构概念，它允许最终用户从几乎所有设备 (（如个人计算机、智能手机或平板电脑) ）访问企业虚拟桌面实例，无需组织为用户提供物理计算机。 使用 VDI 设备可降低成本，因为 IT 部门不再负责管理、修复和替换物理终结点。 授权用户可以通过安全的桌面客户端或浏览器从任何批准的设备访问相同的公司服务器、文件、应用和服务。

与 IT 环境中任何其他系统一样，这些系统也应具有终结点检测和响应 (EDR) 防病毒解决方案，以抵御高级威胁和攻击。


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- 虚拟桌面基础结构 (VDI) 设备
- Windows 10、Windows 11、Windows Server 2019、Windows Server 2022、Windows Server 2008R2/2012R2/2016

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configvdi-abovefoldlink)。

 > [!NOTE]
  > **永久性 VDI** - [将永久性 VDI](configure-endpoints.md) 计算机载入Microsoft Defender for Endpoint处理方式与载入物理计算机（如台式机或笔记本电脑）的方式相同。 组策略Microsoft Endpoint Manager和其他方法可用于载入永久计算机。 在 Microsoft 365 Defender门户中， (https://security.microsoft.com)下选择你的首选载入方法，然后按照该类型的说明进行操作。 

## <a name="onboarding-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>在 VDI 设备上载入非永久性虚拟 () 基础结构

Defender for Endpoint 支持非永久性 VDI 会话载入。

载入 VDI 实例时可能存在相关挑战。 以下是此方案的典型挑战：

- 即时提前载入短期会话，此会话在实际预配之前必须载入到 Defender for Endpoint。
- 设备名称通常重新用于新会话。

在 VDI 环境中，VDI 实例的生命周期可能较短。 VDI 设备可以在 Defender for Endpoint 门户中显示为：


- 每个 VDI 实例的单个门户条目。 如果 VDI 实例已载入 Microsoft Defender for Endpoint并且在某些时候已删除，然后使用相同的主机名重新创建，将不会在门户中创建表示此 VDI 实例的新对象。 


  > [!NOTE]
  > 在这种情况下，创建会话时必须配置相同的设备名称，例如使用无人参与应答文件。

- 每个设备有多个条目 - 每个 VDI 实例一个条目。

以下步骤将指导你完成载入 VDI 设备，并重点介绍单项和多条目的步骤。

> [!WARNING]
> 对于资源配置较低的环境，VDI 启动过程可能会减慢 Defender for Endpoint 传感器载入的速度。

### <a name="for-windows-10-or-windows-11-or-windows-server-2012-r2-and-later"></a>For Windows 10， or Windows 11， or Windows Server 2012 R2 and later

> [!NOTE]
> Windows Server 2016 Windows Server 2012 R2，需要先按照[载入 Windows 服务器](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2012-r2-and-windows-server-2016)中的说明应用安装程序包，使此功能正常工作。

1.  打开 VDI 配置包.zip文件 (*WindowsDefenderATPOnboardingPackage.zip)* 从服务载入向导下载的内容。 还可以从应用门户获取<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender包</a>：

    1. 在导航窗格中，**选择"设置** > **EndpointsDevice** >  **managementOnboarding** > "。

    1. 选择操作系统。

    1.  在 **"部署方法"** 字段中，选择"非永久性终结点的 **VDI 载入脚本"**。

    1. 单击 **下载程序包** 并保存.zip文件。

2. 将文件从从 .zip 文件中提取的 WindowsDefenderATPOnboardingPackage 文件夹复制到路径 下的黄金/主映像 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`中。
    1. 如果要为每台设备实现多个条目（每个会话一个条目），请复制 WindowsDefenderATPOnboardingScript.cmd。
    2. 如果你要针对每台设备实现单个条目，请同时复制 Onboard-NonPersistentMachine.ps1 和 WindowsDefenderATPOnboardingScript.cmd。

    > [!NOTE]
    > 如果看不到该文件夹 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` ，它可能处于隐藏状态。 你需要从"显示隐藏文件和文件夹"**选项文件资源管理器。**

3. 打开"本地组策略编辑器"窗口并导航\>到"**计算机**\>配置"Windows 设置 **脚本** \> **启动"**。

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
      - 对于每台设备的多个条目：在门户中检查Microsoft 365 Defender条目。

6. 单击 **导航窗格上的** "设备列表"。

7. 通过输入设备名称并选择设备作为搜索类型 **来** 使用搜索函数。

## <a name="for-downlevel-skus-windows-server-2008-r2"></a>对于下层 SKUS (Windows Server 2008 R2) 

> [!NOTE]
> 如果为需要 MMA 的 Microsoft Defender for Endpoint Windows Server 2016 Windows Server 2012 R2 运行上述 Windows Server 2012，则适用于其他 Windows 服务器版本的这些说明也适用。 有关迁移到新的统一解决方案的说明，请参阅 Microsoft Defender for Endpoint [中的服务器迁移方案](/microsoft-365/security/defender-endpoint/server-migration)。

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
- [载入Microsoft Defender for Endpoint疑难解答](troubleshoot-onboarding.md)
