---
title: 将设备载入 Microsoft Defender for Business
description: 了解 Microsoft Defender for Business 中的设备载入选项
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/14/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 6b475a1f56f66c6ec9e1ed09b5311515c5eb31c8
ms.sourcegitcommit: 9af389e4787383cd97bc807f7799ef6ecf0664d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2022
ms.locfileid: "63468690"
---
# <a name="onboard-devices-to-microsoft-defender-for-business"></a>将设备载入 Microsoft Defender for Business

> [!IMPORTANT]
> 从 2022 年 3 [月](../../business-premium/index.md) 1 Microsoft 365 商业高级版 Microsoft Defender for Business 将推出给客户。 作为独立订阅的 Defender for Business 在预览版中，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 预览 [包括一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

借助 Microsoft Defender for Business，你可以从多个选项中进行选择，以载入你的组织设备。 本文将引导你完成你的选项，并包括载入工作原理的概述。

## <a name="what-to-do"></a>需执行的操作

1. 查看载入 [设备的选项，](#device-onboarding-methods)然后选择以下方法之一： 

   - [自动载入Windows注册的设备Microsoft Endpoint Manager](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)
   - [适用于 Windows 和 Mac 设备的本地脚本](#local-script-in-defender-for-business)
   - [Microsoft Endpoint Manager (Microsoft Intune) ](#microsoft-endpoint-manager)
   - [Microsoft Defender for Business 安全配置](#microsoft-defender-for-business-security-configuration)

2. [对新载入的设备](#run-a-detection-test)运行检测Windows测试。

3. [请参阅你的下一步](#next-steps)。 

本文还包括有关为设备运行检测Windows[和](#run-a-detection-test)将设备载[出的信息](#offboarding-a-device)。

>
> **有空吗？**
> 请参加有关 <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business 的简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="device-onboarding-methods"></a>设备载入方法

下表介绍了将设备载入 Defender for Business 最常用的方法。 

| 载入方法  | 说明  | 操作系统 |
|---------|---------|---------|
| **自动载入**<br/> (*已使用 Microsoft Endpoint Manager)* | *Microsoft 365 商业高级版已拥有Microsoft Intune，可以使用此选项*。 自动载入在 Defender for Business 和 Microsoft Endpoint Manager 之间设置连接，然后将Windows载入到 Defender for Business。 若要使用此选项，你的设备必须已在 Endpoint Manager。<br/><br/>若要了解更多信息，请参阅 [自动载入](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)。 | Windows |
| **本地脚本** <br/> | 此选项使你能够手动将个别设备载入到 Defender for Business。 可以使用本地脚本一次载入最多 10 台设备。<br/><br/>若要了解更多信息，请参阅 [Defender for Business 中的本地脚本](#local-script-in-defender-for-business)。 | Windows <br/>macOS |
| **Microsoft Intune** 或 **Microsoft Endpoint Manager**<br/> (或Microsoft Intune *客户Endpoint Manager)* | [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)[移动设备管理是](/mem/intune/enrollment/device-enrollment)移动设备管理的一Endpoint Manager。  (Microsoft 365 商业高级版客户已拥有 Microsoft Intune.) <br/><br/>如果你已在使用 Endpoint Manager Defender for Business 之前，你可以选择继续使用 Endpoint Manager载入和管理你的设备。<br/><br/>若要使用此方法[，请参阅Microsoft Endpoint Manager](#microsoft-endpoint-manager)。 | Windows <br/>macOS<br/>iOS<br/>Android OS | 
| **Microsoft Defender for Business 安全配置** <br/> (*使用Microsoft 365 Defender门户*)  | 若要使用此选项，请配置某些设置以促进 Defender for Business 和 Endpoint Manager。 然后，使用在每台设备上下载并运行的Microsoft 365 Defender程序包 () [https://security.microsoft.com](https://security.microsoft.com) 门户中载入设备。 在设备和设备之间建立信任Azure Active Directory (Azure AD) ，Defender for Business 安全策略将推送到设备。<br/><br/>若要了解详细信息，请参阅 [Microsoft Defender for Business 安全配置](#microsoft-defender-for-business-security-configuration)。 | Windows <br/>macOS |

> [!IMPORTANT]
> 如果出现问题且载入过程失败，请参阅 [Microsoft Defender for Business 疑难解答](mdb-troubleshooting.yml)。

## <a name="automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager"></a>自动载入Windows注册的设备Microsoft Endpoint Manager

自动载入选项仅适用于Windows设备。 如果满足以下条件，则自动载入可用：

- 在获得 Defender for Business 之前，你的组织已在 Microsoft Endpoint Manager、Microsoft Intune MDM () mdm Microsoft Intune或移动设备管理
- 你已经在Windows注册了Endpoint Manager

如果Windows设备已在 Endpoint Manager 中注册，则 Defender for Business 将在你设置和配置 Defender for Business 的过程中检测这些设备。 系统将会询问你是否要将自动载入用于所有或部分 Windows设备。 你可以一次Windows所有设备，或选择开始使用的特定设备，然后以后添加更多设备。

> [!TIP]
> 我们建议选择"已注册所有设备"选项。 这样，Windows以后在 Endpoint Manager中注册设备时，它们将自动载入 Defender for Business。

若要详细了解自动载入，请参阅使用向导设置 [Microsoft Defender for Business 中的](mdb-use-wizard.md)步骤 2。

## <a name="local-script-in-defender-for-business"></a>Defender for Business 中的本地脚本

可以使用本地脚本载入 Windows Mac 设备。 当你在设备上运行载入脚本时，它会创建与 Azure Active Directory (的信任（如果该信任不存在) ，在 Microsoft Endpoint Manager (中注册设备（如果尚未注册) ）然后将设备载入到 Defender for Business。 此方法对于在 Defender for Business 中载入设备非常有用。 一次可载入最多 10 台设备。

1. 转到 Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) ，然后登录。

2. 在导航窗格中，选择"**设置** > **""Endpoints"**，然后在 **"设备管理**"下选择"**载入"**。

3. 选择操作系统，如 **Windows 10 11** 或 **macOS**，然后在"部署方法"部分，选择"**本地脚本"**。 

4. 选择 **下载载入程序包**。 我们建议将载入程序包保存为可移动驱动器。  (如果你选择了 **macOS，** 则还要选择下载 **安装** 程序包并将其保存到你的可移动设备。) 

5. 请按照下表中的指导操作：

   | 操作系统 | Procedure |
   |---|---|
   | Windows | 1. Windows设备上，将配置包的内容提取到一个位置，如桌面文件夹。 你应该有一个名为 的文件 `WindowsDefenderATPLocalOnboardingScript.cmd`。 <br/><br/>2. 以管理员角色打开命令提示符。<br/><br/>3. 键入脚本文件的位置。 例如，如果你将文件复制到桌面文件夹，你需要键入： `%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd`，然后按 Enter 键 (**或选择确定**) 。<br/><br/>4. 脚本运行后，继续 [运行检测测试](#run-a-detection-test)。 |
   | macOS | 1. 在 Mac 计算机上，将安装包另存 `wdav.pkg` 为本地目录。 <br/><br/>2. 将载入程序包另 `WindowsDefenderATPOnboardingPackage.zip` 存为用于安装程序包的同一目录。 <br/><br/>3. 使用 Finder 导航到 `wdav.pkg` 保存的位置，然后打开它。<br/><br/>4. **选择"继续**"，同意许可条款，然后在系统提示时输入您的密码。<br/><br/>5. 系统将提示你允许从 Microsoft 安装驱动程序 ("系统扩展阻止"或"安装已保留"，或同时安装两者。 必须允许安装驱动程序。 若要允许安装，请选择"打开 **安全** 首选项"或"**打开系统** > 首选项""安全 **&隐私**"，然后选择"允许 **"**。<br/><br/>6. 在 Bash 中使用以下 Python 命令运行载入包： `/usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py`。 <br/><br/>7. 若要确认设备与您的组织关联，请使用 Bash 中的以下 Python 命令： `mdatp health --field org_id`。<br/><br/>8. 如果你使用的是 macOS 10.15 (加泰罗尼亚语) 更高版本，请授予 Defender for Business 同意来保护你的设备。 Go to **System PreferencesSecurity** >  **&** **PrivacyPrivacyFull** >  >  **Disk Access**.  选择锁定图标以 (对话框底部的) 进行更改，然后选择 Microsoft Defender for Business (或 Defender for Endpoint（如果你看到) ）。 <br/><br/>9. 若要验证设备已载入，请使用 Bash 中的以下命令： `mdatp health --field real_time_protection_enabled`。    |

## <a name="microsoft-endpoint-manager"></a>Microsoft Endpoint Manager

如果你已在使用 Endpoint Manager (包括 Microsoft Intune 和移动设备管理) ，那么在你获得 Defender for Business 之前，你可以继续使用 Endpoint Manager 载入你的组织设备。 借助Endpoint Manager，你可以载入计算机、平板电脑和手机，包括 iOS 和 Android 设备。

请参阅[设备注册Microsoft Intune](/mem/intune/enrollment/device-enrollment)。

## <a name="microsoft-defender-for-business-security-configuration"></a>Microsoft Defender for Business 安全配置

> [!NOTE]
> 如果你已在使用 Endpoint Manager来管理设备和安全策略，请跳过此方法，并改为参阅[Microsoft Endpoint Manager。](#microsoft-endpoint-manager)

Microsoft Defender for Business 安全配置基于称为 Microsoft [Defender for Endpoint ](/mem/intune/protect/mde-security-integration)安全管理功能 (预览版) 。 它使你能够在 Microsoft 365 Defender 门户 () 中将设备载入 Defender for Business [https://security.microsoft.com](https://security.microsoft.com) ，而无需事先要求这些设备Microsoft Endpoint Manager注册。 

此方法使你能够在 Microsoft 365 Defender 门户中载入设备并 () [https://security.microsoft.com](https://security.microsoft.com) 。 以下是所有功能的工作原理：

1. 从应用门户下载载入Microsoft 365 Defender，然后在设备上运行该程序包，将这些设备载入到 Defender for Business。

2. 运行程序包将在每个设备之间建立信任 (如果信任不存在，) Azure Active Directory (Azure AD) 。 

3. 设备使用其Endpoint Manager标识Azure AD通信，Defender for Business 中的安全策略将推送到设备。

4. 可以在管理中心门户和 Microsoft 365 Defender 管理中心Endpoint Manager查看[https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 。

若要使用此选项，必须事先配置某些设置。 若要了解更多信息，包括先决条件和支持的操作系统，请参阅在设备上使用 Microsoft Endpoint Manager 管理 [Microsoft Defender for Endpoint](/mem/intune/protect/mde-security-integration)。

## <a name="run-a-detection-test"></a>运行检测测试

将设备载入 Windows Defender for Business 后，可以在 Windows 设备上运行检测测试，以确保一切正常。

1. 在 Windows 设备上，创建一个文件夹：`C:\test-MDATP-test`。

2. 以管理员角色打开命令提示符。

3. 在命令提示符窗口中，运行以下 PowerShell 命令：

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

命令运行后，命令提示符窗口将自动关闭。 如果成功，检测测试将标记为已完成，并且新载入的设备的 Microsoft 365 Defender 门户 ([https://security.microsoft.com](https://security.microsoft.com)) 将在大约 10 分钟内显示新警报。

## <a name="gradual-device-onboarding"></a>逐步设备载入

你可以阶段性地载入组织的设备。 *我们将此称为逐步设备载入*。 

1. 标识要载入的一组设备。

2. 转到 Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) ，然后登录。

3. 在导航窗格中，选择"**设置** > **""Endpoints"**，然后在 **"设备管理**"下选择"**载入"**。

4. 选择操作系统 (如 Windows 10 和 **11)**，然后选择载入方法 **(如本地** 脚本) 。 按照为所选方法提供的指南操作。

5. 对要载入的每组设备重复此过程。 

> [!TIP]
> 每次载入设备时，都不必使用相同的载入程序包。 例如，可以使用本地脚本载入某些设备，稍后可以选择另一种方法载入更多设备。

## <a name="offboarding-a-device"></a>将设备载出

如果要从设备中注销，请使用以下过程之一：

| 操作系统 | Procedure |
|---|---|
| Windows | 1. 转到 Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 并登录。<br/><br/>2. 在导航窗格中，选择"**设置"，** 然后选择"**终结点"**。<br/><br/>3. 在 **"设备管理"下**，选择 **"载出"**。<br/><br/>4. 选择操作系统（如 Windows 10 **和 11**，然后在"从设备载出"下的"部署方法"部分，选择"**本地脚本"**。 <br/><br/>5. 在确认屏幕中，查看信息，然后选择" **下载** "继续。<br/><br/>6. 选择 **下载载出程序包**。 我们建议将载出包保存为可移动驱动器。<br/><br/>7. 在你想要从每台设备上运行脚本。| 
| macOS | 1. 转到 **FinderApplications** > 。 <br/><br/>2. 右键单击 Microsoft Defender for Business，然后选择" **移动到回收站"**。 <br/><br/>--- 或 --- <br/><br/> 使用以下命令： `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`。|

> [!IMPORTANT]
> 将设备载出会导致设备停止向 Defender for Business 发送数据。 但是，在载出之前收到的数据最多保留六 (6) 个月。

## <a name="next-steps"></a>后续步骤

继续：

- [步骤 5：在 Microsoft Defender for Business 中配置安全设置和策略](mdb-configure-security-settings.md)

- [开始使用 Microsoft Defender for Business](mdb-get-started.md) 
