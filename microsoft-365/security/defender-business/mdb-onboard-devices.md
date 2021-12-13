---
title: '将设备载入 Microsoft Defender for Business (预览版) '
description: '了解 Microsoft Defender for Business 预览版中的设备载入 (选项) '
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/10/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 330d0ca65916d647ff970468d32ede75f36d63a6
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61423211"
---
# <a name="onboard-devices-to-microsoft-defender-for-business-preview"></a>将设备载入 Microsoft Defender for Business (预览版) 

> [!IMPORTANT]
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 本文包含指向联机内容的链接，这些链接可能介绍 Microsoft Defender for Business 预览版中未包含 (一些) 。

借助 Microsoft Defender for Business (预览) ，你可以从多个选项中进行选择以载入你的公司设备。 本文将引导你完成你的选项，并包括载入工作原理的概述。

## <a name="what-to-do"></a>需执行的操作

1. [了解载入方法](#types-of-onboarding-methods)，并确定是使用自动载入还是手动载入。

2. 执行下列操作之一：

   - 如果你使用的是自动载入，请继续执行步骤 5：在 Microsoft Defender for Business 中配置安全设置和策略 ([预览) 。 ](mdb-configure-security-settings.md)
   - 如果你要手动载入设备，请继续执行使用 Microsoft 365 Defender 中的[本地脚本载入设备](#onboard-a-device-using-a-local-script-in-defender-for-business)。
   - 如果你已在使用 Microsoft Intune，请继续执行使用 Microsoft Intune[载入设备](#onboard-devices-using-microsoft-intune)。

3. [对新载入的设备](#run-a-detection-test) 运行检测测试。

4. [请参阅下一步。](#next-steps) 

本文还包括有关 [如何从设备上离开的信息](#what-if-i-want-to-offboard-a-device)。

## <a name="types-of-onboarding-methods"></a>载入方法的类型

下表介绍了预览版中 Defender for Business 支持的载入方法类型。 
<br/><br/>

| 载入方法  | 说明  |
|---------|---------|
| **自动载入**<br/> (*已使用 Microsoft Endpoint Manager)* | 如果你在获取 Defender for Business Microsoft Endpoint Manager预览版之前 (已) ，则 Defender for Business 将检测到这一点。 系统将会询问你是否要对之前已载入到 Microsoft Endpoint Manager 的设备使用自动载入Microsoft Endpoint Manager。 自动载入在 Defender for Business (预览版) 和 Microsoft Endpoint Manager 之间设置连接，然后将设备载入 Defender for Business (预览版) 。 此选项使你可以快速、高效地将设备载入 Defender for Business (预览) 预览版。<br/><br/>如果你选择自动载入过程，则 *所有在* Microsoft Endpoint Manager注册的设备都将载入到适用于终结点的 Defender。 <br/><br/>如果你想要使用自动载入，请跳过本文中的过程，然后继续执行步骤 [5： ](mdb-configure-security-settings.md)在 Microsoft Defender for Business 中配置安全设置和策略 (预览版) 。  |
| **本地脚本**<br/> (*预览期间推荐使用;可用于* 一次载入几台设备)   | 在预览版中，可以使用本地脚本在 Defender for Business (预览) 载入设备。 Microsoft Defender for Business (预览版) 可下载的脚本，可以在 Windows 10 11 设备上使用。 在设备上运行脚本将创建与 Azure Active Directory (Azure AD) 的信任，并注册设备Microsoft Intune。<br/><br/>如果要使用此方法，请继续执行使用 Microsoft 365 Defender[中的本地脚本载入设备](#onboard-a-device-using-a-local-script-in-defender-for-business)。 |
| **Microsoft Intune** <br/> (*已使用 Microsoft Intune)* | 如果你在获取 Defender for Business Microsoft Intune预览版之前 (过) ，可以使用 Microsoft Intune载入设备。 例如，在预览期间，你可以将 iOS、macOS、Linux 和 Android 设备载入 Defender for Business (预览版) 。 <br/><br/>如果你想要使用此方法，请参阅 [Intune 中的设备注册](/mem/intune/enrollment/device-enrollment)。 |

> [!TIP]
> 如果在载入设备时出错，请参阅 Microsoft Defender for Business ([预览) 疑难解答](mdb-troubleshooting.yml)。 

## <a name="onboard-a-device-using-a-local-script-in-defender-for-business"></a>在 Defender for Business 中使用本地脚本载入设备

1. 转到 Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) () ，然后登录。

2. 在导航窗格中，**选择"设置**  >  **终结点"，** 然后在"设备管理"下选择 **"载入"。**

3. 选择 **Windows 10 11"，** 然后在"载入 **设备**"下的"部署方法"部分，选择"**本地脚本"。** 

4. 选择 **下载载入程序包**。 我们建议将载入程序包保存为可移动驱动器。

5. 在每台设备上，按照以下步骤操作： 

   1. 将 `WindowsDefenderATPOnboardingPackage.zip` 下载的文件复制到设备，并提取其内容。 你可以将内容提取到设备的 **桌面文件夹** 。
   
   2. 以管理员角色打开命令提示符。
   
   3. 在命令提示符窗口中，键入脚本文件的位置。 例如，如果将文件复制到桌面 **文件夹，请** 键入 `%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd` ，然后按 Enter 键。

6. 继续运行 [检测测试](#run-a-detection-test)。

> [!IMPORTANT]
> 如果出现问题且载入过程失败，请参阅 Microsoft Defender for Business ([预览) 疑难解答](mdb-troubleshooting.yml)。

## <a name="onboard-devices-using-microsoft-intune"></a>使用移动设备载入Microsoft Intune

如果你在获取 Defender for Business Microsoft Intune预览版之前 (过) ，可以使用 Microsoft Intune载入设备。 若要获取有关此内容的帮助，请参阅设备[注册Microsoft Intune。](/mem/intune/enrollment/device-enrollment)

## <a name="run-a-detection-test"></a>运行检测测试

手动载入设备后，你可以运行检测测试，以确保一切正常使用 Defender for Business (预览版) 。

1. 在设备上，创建一个文件夹 `C:\test-MDATP-test` ：。

2. 以管理员角色打开命令提示符。

3. 在命令提示符窗口中，运行以下 PowerShell 命令：

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

命令运行后，命令提示符窗口将自动关闭。 如果成功，检测测试将标记为已完成，并且新载入设备的 Microsoft 365 Defender 门户中将在大约 10 分钟内显示新警报。

## <a name="what-if-i-want-to-offboard-a-device"></a>如果我想从设备中注销，该做什么？

如果你想要将设备载出，请按照以下步骤操作：

1. 转到"Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) () 并登录。

2. 在导航窗格中，**选择**"设置"，然后选择"**终结点"。**

3. 在 **"设备管理"** 下，选择 **"载出"。**

4. 选择 **"Windows 10和 11"，** 然后在"从设备载出"下的"部署方法 **"部分，** 选择"**本地脚本"。** 

5. 在确认屏幕中，查看信息，然后选择" **下载"** 继续。

6. 将压缩文件夹保存到一个位置，例如可移动驱动器。

7. 在每台设备上，按照以下步骤操作： 

   1. 将配置包 () 下载到设备，然后 `WindowsDefenderATPOffboardingPackage_valid_until_YYYY-MM-DD` 提取其内容。 你可以将内容提取到设备的 **桌面文件夹** 。  (`YYYY-MM-DD` package.) 

   2. 以管理员角色打开命令提示符。

   3. 在命令提示符窗口中，键入脚本文件的位置。 例如，如果将文件复制到桌面 **文件夹，请** 键入 `%userprofile%\Desktop\WindowsDefenderATPOffboardingPackage_valid_until_YYYY-MM-DD.cmd` ，然后按 Enter 键。

## <a name="next-steps"></a>后续步骤

继续：

- [步骤 5：在 Microsoft Defender for Business 预览版中配置 (和) ](mdb-configure-security-settings.md)

- [开始使用 Microsoft Defender for Business (预览) ](mdb-get-started.md) 