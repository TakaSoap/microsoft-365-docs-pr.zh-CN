---
title: 将设备载入Microsoft Defender 商业版
description: 了解 Microsoft Defender 商业版 中的设备载入Microsoft Defender 商业版
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 04/01/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 78a8eaa5a9472a32c9615dfb7c7f5b08afe548ff
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634726"
---
# <a name="onboard-devices-to-microsoft-defender-for-business"></a>将设备载入Microsoft Defender 商业版

> [!IMPORTANT]
> Microsoft Defender 商业版 2022 年 3 [Microsoft 365 商业高级版](../../business-premium/index.md) 1 开始向客户推出。 作为独立订阅的 Defender for Business 在预览版中，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 预览 [包括一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

使用 Microsoft Defender 商业版，你可以从多个选项中进行选择以载入你的公司设备。 本文将引导你完成你的选项，并包括载入工作原理的概述。

>
> **有空吗？**
> 请参加<a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">我们的简短调查，了解Microsoft Defender 商业版</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="what-to-do"></a>需执行的操作

1. [查看载入设备的选项，](#device-onboarding-methods)然后选择方法。 

   - [对已注册Windows的设备使用自动载入Microsoft Endpoint Manager](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)
   - [使用本地脚本载入Windows macOS 设备](#local-script-in-defender-for-business)
   - [使用 Microsoft Endpoint Manager载入Windows macOS 或移动设备](#microsoft-endpoint-manager)

2. [对新载入的设备](#run-a-detection-test)运行检测Windows测试。

3. [请参阅你的下一步](#next-steps)。 

本文还包括有关将设备 [载出的信息](#offboarding-a-device)。

## <a name="device-onboarding-methods"></a>设备载入方法

Defender for Business 为载入设备提供了几种不同的方法，无论你已在使用 Microsoft Endpoint Manager，还是只需要简化的载入体验。 将设备载入 Defender for Business 最常用的方法包括：

- **已注册** Windows的设备自动载入Microsoft Endpoint Manager。 自动载入在 Defender for Business 和 Microsoft Endpoint Manager 之间设置连接，然后将Windows载入到 Defender for Business。 若要使用此选项，你的设备必须已在 Endpoint Manager。 若要了解更多信息，请参阅 [自动载入](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)。

- **手动将** Windows macOS 设备载入 Defender for Business 的本地脚本。 可以使用本地脚本一次载入最多 10 台设备。 若要了解更多信息，请参阅 [Defender for Business 中的本地脚本](#local-script-in-defender-for-business)。

- **Microsoft Intune** 或 **Microsoft Endpoint Manager** 移动设备Windows macOS 和移动设备。 你可以在你的设备上注册Endpoint Manager，然后将你的设备载入 Defender for Business。 [Microsoft 365 商业高级版](../../business-premium/index.md)客户已拥有[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)，Microsoft Intune[和移动](/mem/intune/enrollment/device-enrollment)设备管理现在都属于 Endpoint Manager。 若要使用此方法[，请参阅Microsoft Endpoint Manager](#microsoft-endpoint-manager)。

> [!IMPORTANT]
> 如果出现问题且载入过程失败，请参阅Microsoft Defender 商业版[疑难解答](mdb-troubleshooting.yml)。

## <a name="automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager"></a>自动载入Windows注册的设备Microsoft Endpoint Manager

自动载入选项仅适用于Windows设备。 如果满足以下条件，则自动载入可用：

- 在获得 Defender for Business 之前，你的公司已在 Microsoft Endpoint Manager Microsoft Intune 使用 设备管理 (MDM) Microsoft Intune 或移动版 MDM

- 你已经在Windows注册了Endpoint Manager

如果Windows设备已在 Endpoint Manager 中注册，则 Defender for Business 将在你设置和配置 Defender for Business 的过程中检测这些设备。 系统将会询问你是否要将自动载入用于所有或部分 Windows设备。 你可以一次Windows所有设备，或选择开始使用的特定设备，然后以后添加更多设备。

> [!TIP]
> 我们建议选择"已注册所有设备"选项。 这样，Windows以后在 Endpoint Manager中注册设备时，它们将自动载入 Defender for Business。 此外，如果你一直在管理 Endpoint Manager 中的安全策略和设置，我们建议切换到 Microsoft 365 Defender 门户来管理你的设备、策略和设置。 若要了解更多信息， [请参阅选择在何处管理安全策略和设备](mdb-configure-security-settings.md#choose-where-to-manage-security-policies-and-devices)。

若要详细了解自动载入，请参阅使用向导设置自动载入[Microsoft Defender 商业版](mdb-use-wizard.md)。

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
   | macOS | 1. 在 Mac 计算机上，将安装包另存 `wdav.pkg` 为本地目录。 <br/><br/>2. 将载入程序包另 `WindowsDefenderATPOnboardingPackage.zip` 存为用于安装程序包的同一目录。 <br/><br/>3. 使用 Finder 导航到 `wdav.pkg` 保存的位置，然后打开它。<br/><br/>4. **选择"继续**"，同意许可条款，然后在系统提示时输入您的密码。<br/><br/>5. 系统将提示你允许从 Microsoft 安装驱动程序 ("系统扩展阻止"或"安装已保留"，或同时安装两者。 必须允许安装驱动程序。 若要允许安装，请选择"打开 **安全** 首选项"或"**打开系统** > 首选项""安全 **&隐私**"，然后选择"允许 **"**。<br/><br/>6. 在 Bash 中使用以下 Python 命令运行载入包： `/usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py`。 <br/><br/>7. 若要确认设备与贵公司关联，请使用 Bash 中的以下 Python 命令： `mdatp health --field org_id`。<br/><br/>8. 如果你使用的是 macOS 10.15 (加泰罗尼亚语) 更高版本，请授予 Defender for Business 同意来保护你的设备。 Go to **System PreferencesSecurity** >  **&** **PrivacyPrivacyFull** >  >  **Disk Access**.  选择锁定图标以 (对话框底部的") "，然后选择"Microsoft Defender 商业版 ("或"适用于终结点的 Defender"（如果) ）。 <br/><br/>9. 若要验证设备已载入，请使用 Bash 中的以下命令： `mdatp health --field real_time_protection_enabled`。    |

## <a name="microsoft-endpoint-manager"></a>Microsoft Endpoint Manager

如果你已在使用 Endpoint Manager (包括 Microsoft Intune 和移动版 设备管理) ，在你获得 Defender for Business 之前，你可以继续使用 Endpoint Manager 载入你的公司设备。 借助Endpoint Manager，你可以载入计算机、平板电脑和手机，包括 iOS 和 Android 设备。

请参阅[设备注册Microsoft Intune](/mem/intune/enrollment/device-enrollment)。

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

你可以阶段性地载入你的公司设备。 *我们将此称为逐步设备载入*。 

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
| macOS | 1. 转到 **FinderApplications** > 。 <br/><br/>2. 右键单击Microsoft Defender 商业版，然后选择"**移动到回收站"**。 <br/><br/>--- 或 --- <br/><br/> 使用以下命令： `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`。|

> [!IMPORTANT]
> 将设备载出会导致设备停止向 Defender for Business 发送数据。 但是，在载出之前收到的数据最多保留六 (6) 个月。

## <a name="next-steps"></a>后续步骤

继续：

- [步骤 5：在安全环境中配置Microsoft Defender 商业版](mdb-configure-security-settings.md)

- [开始Microsoft Defender 商业版](mdb-get-started.md) 
