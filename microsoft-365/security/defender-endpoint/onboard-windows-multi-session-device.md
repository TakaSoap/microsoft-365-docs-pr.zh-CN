---
title: 在Windows桌面中载入多会话设备
description: 阅读本文中有关在 Azure 虚拟Windows加入多会话设备
keywords: Azure 虚拟桌面， WVD， microsoft defender， 终结点， 载入
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 0681144d09a430d0f4e4a2349f24ba442382cd14
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110567"
---
# <a name="onboard-windows-multi-session-devices-in-azure-virtual-desktop"></a>在Windows桌面中载入多会话设备

6 分钟阅读

应用于：

- Windows Azure 虚拟桌面和 AVD (上运行的多) 

Microsoft Defender for Endpoint 支持监视 VDI 和 Azure 虚拟桌面会话。 根据组织的需求，可能需要实现 VDI 或 Azure 虚拟桌面会话，以帮助员工从非托管设备、远程位置或类似方案访问公司数据和应用。 通过 Microsoft Defender for Endpoint，你可以监视这些虚拟机的异常活动。

## <a name="before-you-begin"></a>开始之前

熟悉非永久性 [VDI 的注意事项](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)。 虽然[Azure 虚拟](/azure/virtual-desktop/overview)桌面不提供非持久性选项，但它确实提供了使用黄金 Windows 映像的方法，可用于预配新主机和重新部署计算机。 这会增加环境中的变化，从而影响在 Microsoft Defender 终结点门户中创建和维护的条目，从而可能降低安全分析师的可见性。

> [!NOTE]
> 根据你选择的载入方法，设备可以在 Microsoft Defender for Endpoint 门户中显示为：
>
> - 每个虚拟桌面的单个条目
> - 每个虚拟桌面的多个条目

Microsoft 建议将 Azure 虚拟桌面作为每个虚拟桌面的单个条目载入。 这可确保 Microsoft Defender for Endpoint 门户中的调查体验基于计算机名称在一台设备的上下文中。 经常删除和重新部署 WVD 主机的组织应强烈建议使用此方法，因为它会阻止在 Microsoft Defender for Endpoint 门户中创建同一台计算机的多个对象。 这可能会导致调查事件时混淆。 对于测试或非可变环境，你可以选择不同的选择。

Microsoft 建议将 Microsoft Defender for Endpoint 载入脚本添加到 WVD 黄金映像。 这样，你可以确保此载入脚本在首次启动时立即运行。 它作为启动脚本在首次启动时在从 WVD 黄金映像预配的所有 WVD 计算机上执行。 但是，如果使用的库图像之一未经修改，将脚本放在共享位置，然后从本地或域组策略调用它。

> [!NOTE]
> WVD 黄金映像上的 VDI 载入启动脚本的位置和配置会将其配置为在 WVD 启动时运行的启动脚本。 不建议 **载入实际的** WVD 黄金映像。 另一个注意事项是用于运行脚本的方法。 它应尽早在启动/预配过程中运行，以减少计算机可用于接收会话和设备载入到服务之间的时间。 下面的方案 1 和 2 考虑到这一点。

### <a name="scenarios"></a>应用场景

有几种方法可以载入 WVD 主机：

- 在黄金映像中运行脚本 (在启动期间从共享) 运行脚本。
- 使用管理工具运行脚本。
- 通过与 [Microsoft Defender for Cloud 集成](azure-server-integration.md)

#### <a name="scenario-1-using-local-group-policy"></a>*方案 1：使用本地组策略*

此方案要求将脚本放置在黄金映像中，并使用本地组策略在启动过程早期运行。

按照在 [VDI 设备上载入非永久性虚拟桌面 (中的) 进行操作](configure-endpoints-vdi.md)。

按照每个设备的单个条目的说明进行操作。

#### <a name="scenario-2-using-domain-group-policy"></a>*方案 2：使用域组策略*

此方案使用位于中央的脚本并使用基于域的组策略运行它。 还可以将脚本放在黄金映像中，并使用相同的方式运行它。

##### <a name="download-the-windowsdefenderatponboardingpackagezip-file-from-the-windows-defender-security-center"></a>从WindowsDefenderATPOnboardingPackage.zip安全中心Windows Defender文件

1. 打开 VDI 配置包.zip文件 (WindowsDefenderATPOnboardingPackage.zip) 

    1. 在"Microsoft 365 Defender门户"导航窗格中，选择"设置管理"下 (终结点载入 \>  \> ) 。 
    1. 选择Windows 10或Windows 11操作系统。
    1. 在 **"部署方法"** 字段中，选择"非永久性终结点的 VDI 载入脚本"。
    1. 单击 **下载程序包** 并保存.zip文件。

2. 将 .zip 文件的内容提取到设备可以访问的共享只读位置。 你应该有一个名为 **OptionalParamsPolicy** 的文件夹以及 **WindowsDefenderATPOnboardingScript.cmd** 和 **Onboard-NonPersistentMachine.ps1**。

##### <a name="use-group-policy-management-console-to-run-the-script-when-the-virtual-machine-starts"></a>当虚拟机启动时，使用组策略管理控制台运行脚本

1. 打开 GPMC (组策略管理) ，右键单击要配置的组策略对象 (GPO) 然后单击 **编辑。**

2. 在组策略管理编辑器中，转到计算机 **配置** \> **首选项** \> **控制面板设置**。

3. 右键单击 **计划任务**，单击 **新建**，**然后单击立即任务** (至少Windows 7) 。

4. 在打开的任务窗口中，转到常规 **选项卡** 。在" **安全选项"** 下 **，单击"更改用户或组"，** 然后键入"系统"。 单击 **"检查名称"，** 然后单击"确定"。 NT AUTHORITY\SYSTEM 显示为任务将运行的用户帐户。

5. Select **Run whether user is logged on or not and** check the Run with highest **privileges** check box.

6. 转到"操作 **"** 选项卡，然后单击"新建 **"。** 确保在 **"操作"** 字段中选择了"启动程序"。 输入以下信息：

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   然后选择" **确定"** 并关闭任何打开的 GPMC 窗口。

#### <a name="scenario-3-onboarding-using-management-tools"></a>*方案 3：使用管理工具载入*

如果你计划使用管理工具管理计算机，可以使用 Microsoft Endpoint Configuration Manager。

有关详细信息，请参阅使用配置[Windows载入设备](configure-endpoints-sccm.md)。

> [!WARNING]
> 如果你计划使用攻击面[](attack-surface-reduction-rules.md)减少规则，请注意，不应使用规则"阻止源自[PSExec](attack-surface-reduction-rules.md#block-process-creations-originating-from-psexec-and-wmi-commands)和 WMI 命令的进程创建"，因为该规则与通过 Microsoft Endpoint Configuration Manager 管理不兼容。 该规则阻止 Configuration Manager 客户端用于正常运行的 WMI 命令。

> [!TIP]
> 载入设备后，你可以选择运行检测测试，以验证设备是否正确载入到服务。 有关详细信息，请参阅对新载入的 [Microsoft Defender for Endpoint](run-detection-test.md)设备运行检测测试。

#### <a name="tagging-your-machines-when-building-your-golden-image"></a>生成黄金映像时标记计算机

作为载入的一部分，你可能要考虑设置计算机标记，以在 Microsoft 安全中心更轻松地区分 WVD 计算机。 有关详细信息，请参阅通过 [设置注册表项值添加设备标记](machine-tags.md#add-device-tags-by-setting-a-registry-key-value)。

#### <a name="other-recommended-configuration-settings"></a>其他建议的配置设置

生成黄金映像时，你可能还想要配置初始保护设置。 有关详细信息，请参阅其他 [推荐的配置设置](configure-endpoints-gp.md#other-recommended-configuration-settings)。

此外，如果您使用的是 FSlogix 用户配置文件，我们建议您从始终打开的保护中排除以下文件：

**排除文件：**

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

**排除进程：**

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a>许可要求

许可注意事项：使用 Windows Enterprise 多会话时，根据你的要求，你可以选择让所有用户通过 Microsoft Defender for Endpoint (许可，每用户) 、Windows Enterprise E5、Microsoft 365 安全或 Microsoft 365 E5，或者通过 Microsoft Defender for Cloud 获得 VM 许可。
可在许可要求中找到适用于终结点的 Microsoft Defender [的许可要求](minimum-requirements.md#licensing-requirements)。

#### <a name="related-links"></a>相关链接

[通过 PowerShell 为 Defender for Endpoint 添加排除项](/azure/architecture/example-scenario/wvd/windows-virtual-desktop-fslogix#add-exclusions-for-microsoft-defender-by-using-powershell)
