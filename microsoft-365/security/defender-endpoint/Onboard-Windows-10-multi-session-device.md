---
title: 在 Windows 虚拟桌面中载入 Windows 10 多会话设备
description: 阅读本文中有关在 Windows 虚拟桌面中载入 Windows 10 多会话设备
keywords: Windows 虚拟桌面， WVD， microsoft defender， 终结点， 载入
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.date: 09/10/2020
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 30e664aed74ed01944c67b139e6268fc3340ada4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054848"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a>在 Windows 虚拟桌面中载入 Windows 10 多会话设备 
6 分钟阅读 

应用于： 
- 在 Windows 虚拟桌面和 WVD (上运行的 Windows 10 多)  
> [!IMPORTANT]
> 欢迎使用 Microsoft Defender for Endpoint，这是 Microsoft Defender for Endpoint 的新名称。 在此处阅读有关此内容和其他更新的详细信息。 我们将在不久的将来更新产品和文档中的名称。

> [!WARNING]
> Microsoft Defender for Endpoint 对 Windows 虚拟桌面多会话方案的支持目前处于预览阶段，每个主机/VM 最多只能有 25 个并发会话。 但是，Windows 虚拟桌面上的单个会话方案完全受支持。

Microsoft Defender for Endpoint 支持监视 VDI 和 Windows 虚拟桌面会话。 根据组织的需求，你可能需要实现 VDI 或 Windows 虚拟桌面会话，以帮助你的员工从非托管设备、远程位置或类似方案访问公司数据和应用。 通过 Microsoft Defender for Endpoint，你可以监视这些虚拟机的异常活动。

 ## <a name="before-you-begin"></a>准备工作
熟悉非永久性 [VDI 的注意事项](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)。 尽管 [Windows 虚拟](https://docs.microsoft.com/azure/virtual-desktop/overview) 桌面不提供非持久性选项，但它确实提供了使用黄金 Windows 映像的方法，该映像可用于预配新主机和重新部署计算机。 这会增加环境中的变化，从而影响在 Microsoft Defender 终结点门户中创建和维护的条目，从而可能降低安全分析师的可见性。

> [!NOTE]
> 根据你选择的载入方法，设备可以在 Microsoft Defender for Endpoint 门户中显示为： 
> - 每个虚拟桌面的单个条目 
> - 每个虚拟桌面的多个条目 

Microsoft 建议将 Windows 虚拟桌面作为每个虚拟桌面的单个条目载入。 这可确保 Microsoft Defender 终结点门户中的调查体验基于计算机名称在一台设备的上下文中。 经常删除和重新部署 WVD 主机的组织应强烈建议使用此方法，因为它会阻止在 Microsoft Defender for Endpoint 门户中创建同一台计算机的多个对象。 这可能会导致调查事件时混淆。 对于测试或非可变环境，你可以选择不同的选择。 

Microsoft 建议将 Microsoft Defender for Endpoint 载入脚本添加到 WVD 黄金映像。 这样，你可以确保此载入脚本在首次启动时立即运行。 它作为启动脚本在首次启动时在从 WVD 黄金映像预配的所有 WVD 计算机上执行。 但是，如果使用的库图像之一未经修改，则将脚本放在共享位置，然后从本地或域组策略调用它。 

> [!NOTE]
> WVD 黄金映像上的 VDI 载入启动脚本的位置和配置会将其配置为在 WVD 启动时运行的启动脚本。 不建议载入实际的 WVD 黄金映像。 另一个注意事项是用于运行脚本的方法。 它应尽早在启动/预配过程中运行，以减少计算机可用于接收会话和设备载入到服务之间的时间。 在方案 1 & 2 中考虑到这一点。

### <a name="scenarios"></a>应用场景
有几种方法可以载入 WVD 主机：

- 在黄金映像中运行脚本 (在启动期间从共享) 运行脚本。
- 使用管理工具运行脚本。

#### <a name="scenario-1-using-local-group-policy"></a>*方案 1：使用本地组策略*
此方案要求将脚本放置在黄金映像中，并使用本地组策略在启动过程早期运行。

按照载入非 [永久性虚拟桌面基础结构 VDI 设备 中的说明操作](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)。

按照每个设备的单个条目的说明进行操作。

#### <a name="scenario-2-using-domain-group-policy"></a>*方案 2：使用域组策略*
此方案使用位于中央的脚本并使用基于域的组策略运行它。 还可以将脚本放在黄金映像中，并使用相同的方式运行它。

**从WindowsDefenderATPOnboardingPackage.zip安全中心Windows Defender文件**
1. 打开 VDI 配置包 .zip 文件 (WindowsDefenderATPOnboardingPackage.zip)   
    - 在 Microsoft Defender 安全中心导航窗格中，**选择设置**  >  **载入**。 
    - 选择 Windows 10 作为操作系统。 
    - 在" **部署方法"** 字段中，选择"非永久性终结点的 VDI 载入脚本"。 
    - 单击 **下载程序包** 并保存 .zip 文件。 
2. 将 .zip 文件的内容提取到设备可以访问的共享只读位置。 你应该有一个名为 **OptionalParamsPolicy** 的文件夹以及 **WindowsDefenderATPOnboardingScript.cmd** 和 **Onboard-NonPersistentMachine.ps1**。

**当虚拟机启动时，使用组策略管理控制台运行脚本**
1. 打开组策略管理控制台 (GPMC) ，右键单击要配置的组策略对象 (GPO) 然后单击 **编辑。**
1. 在组策略管理编辑器中，转到计算机 **配置** \> **首选项** \> **控制面板设置**。 
1. 右键单击 **计划任务**，单击 **新建**， **然后单击即时任务** (Windows 7) 。 
1. 在打开的任务窗口中，转到常规 **选项卡** 。在" **安全选项"** 下 **，单击"更改用户或组"** 并键入 SYSTEM。 单击 **"检查名称"，** 然后单击"确定"。 NT AUTHORITY\SYSTEM 显示为任务将运行的用户帐户。 
1. Select **Run whether user is logged on or not and** check the Run with highest **privileges** check box. 
1. 转到"操作 **"选项卡**，然后单击"新建 **"。** 确保在 **"操作"** 字段中选择了"启动程序"。 输入以下信息： 

> Action = "Start a program" <br>
> Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe <br>
> 添加参数 (可选) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"

单击 **"确定** "并关闭任何打开的 GPMC 窗口。

#### <a name="scenario-3-onboarding-using-management-tools"></a>*方案 3：使用管理工具载入*

如果你计划使用管理工具管理计算机，可以使用 Microsoft Endpoint Configuration Manager 载入设备。

有关详细信息，请参阅：使用 Configuration Manager 载入 [Windows 10 设备](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm) 

> [!WARNING]
> 如果你计划使用攻击面[](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)减少规则，请注意，不应使用规则"阻止源自[PSExec](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction#block-process-creations-originating-from-psexec-and-wmi-commands)和 WMI 命令的进程创建"，因为它与通过 Microsoft Endpoint Configuration Manager 管理不兼容，因为此规则会阻止 Configuration Manager 客户端用于正常运行的 WMI 命令。 

> [!TIP]
> 载入设备后，你可以选择运行检测测试，以验证设备是否正确载入到服务。 有关详细信息，请参阅对新载入的 [Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test)设备运行检测测试。 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a>生成黄金映像时标记计算机 

作为载入的一部分，你可能要考虑设置计算机标记，以便可以在 Microsoft 安全中心更轻松地区分 WVD 计算机。 有关详细信息，请参阅通过 [设置注册表项值添加设备标记](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags#add-device-tags-by-setting-a-registry-key-value)。 

#### <a name="other-recommended-configuration-settings"></a>其他建议的配置设置 

生成黄金映像时，你可能还想要配置初始保护设置。 有关详细信息，请参阅其他 [推荐的配置设置](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp#other-recommended-configuration-settings)。 

此外，如果您使用的是 FSlogix 用户配置文件，我们建议您从始终打开的保护中排除以下文件： 

**排除文件：** 

> %ProgramFiles%\FSLogix\Apps\frxdrv.sys <br>
> %ProgramFiles%\FSLogix\Apps\frxdrvvt.sys <br>
> %ProgramFiles%\FSLogix\Apps\frxccd.sys <br>
> %TEMP% \* 。VHD <br>
> %TEMP% \* 。VHDX <br>
> %Windir%\TEMP \* 。VHD <br>
> %Windir%\TEMP \* 。VHDX <br>
> \\storageaccount.file.core.windows.net\share \* \* 。VHD <br>
> \\storageaccount.file.core.windows.net\share \* \* 。VHDX <br>

**排除进程：**

> %ProgramFiles%\FSLogix\Apps\frxccd.exe <br>
> %ProgramFiles%\FSLogix\Apps\frxccds.exe <br>
> %ProgramFiles%\FSLogix\Apps\frxsvc.exe <br>

#### <a name="licensing-requirements"></a>许可要求 

Windows 10 多会话是客户端操作系统。 有关 Microsoft Defender 终结点的许可要求，可位于： [许可要求](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。
