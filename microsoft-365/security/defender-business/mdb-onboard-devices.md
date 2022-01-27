---
title: '将设备载入 Microsoft Defender for Business (预览版) '
description: '了解 Microsoft Defender for Business 预览版中的设备载入 (选项) '
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/23/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365initiative-defender-business
ms.openlocfilehash: a9aa664c7b7e6c2093817772f8f0bfaefdff3d9e
ms.sourcegitcommit: aac7e002ec6e10a41baa2d0bd38614b0ed471a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2022
ms.locfileid: "62244567"
---
# <a name="onboard-devices-to-microsoft-defender-for-business-preview"></a>将设备载入 Microsoft Defender for Business (预览版) 

> [!IMPORTANT]
> Microsoft Defender for Business 现在为预览版，将逐步向在此处注册以请求[](https://aka.ms/mdb-preview)它的客户和 IT 合作伙伴推出。 我们将于未来几周内载入一组初始客户和合作伙伴，并扩大预览版本，从而一般可用。 请注意，预览将启动 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

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
| **自动载入**<br/> (*已使用 Microsoft Endpoint Manager)* | 如果你在获取 Defender for Business Microsoft Endpoint Manager预览版之前 (过) ，Defender for Business 将检测到这一点。 系统将会询问你是否要对之前已载入到 Microsoft Endpoint Manager 的设备使用自动载入Microsoft Endpoint Manager。 <br/><br/>自动载入在 Defender for Business (预览版) 和 Microsoft Endpoint Manager 之间设置连接，然后将设备载入 Defender for Business (预览版) 。 此选项使你能够快速高效地将设备载入 Defender for Business (预览) 预览版。 当前Windows注册的所有Microsoft Endpoint Manager将载入 Defender for Business。 <br/><br/>如果选择自动载入，请跳过本文中的过程，然后继续执行步骤 [5： ](mdb-configure-security-settings.md)在 Microsoft Defender for Business 中配置安全设置和策略 (预览) 。  |
| **本地脚本**<br/> (*预览期间推荐使用;可用于* 一次载入几台设备)   | 在预览期间，可以使用在 macOS、Windows 10 或 11 以及 Linux 设备上下载和运行的脚本在 Defender for Business (预览版) 中载入设备。 在设备上运行脚本将创建与 Azure Active Directory (Azure AD) 的信任，并注册设备Microsoft Intune。 此过程与将设备载入 [到 Microsoft Defender for Endpoint 的过程非常相似](../defender-endpoint/onboarding.md)。<br/><br/>若要使用此方法，请继续执行在 Microsoft 365 Defender[中使用本地脚本载入设备](#onboard-a-device-using-a-local-script-in-defender-for-business)。 |
| **Microsoft Intune** <br/> (*已使用 Microsoft Intune)* | 如果你在获取 Defender for Business [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)预览版之前 (过) ，Microsoft Intune设备。 在预览版中，Microsoft Intune将 Windows、iOS、macOS、Linux 和 Android 设备载入 Defender for Business (预览版) 。 <br/><br/>若要使用此方法，请参阅 [Intune 中的设备注册](/mem/intune/enrollment/device-enrollment)。 |

> [!TIP]
> 如果在载入设备时出错，请参阅 Microsoft Defender for Business ([预览) 疑难解答](mdb-troubleshooting.yml)。 

## <a name="onboard-a-device-using-a-local-script-in-defender-for-business"></a>在 Defender for Business 中使用本地脚本载入设备

1. 转到 Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) () ，然后登录。

2. 在导航窗格中，**选择"设置**  >  **终结点"，** 然后在"设备管理"下选择 **"载入"。**

3. 选择操作系统（如 Windows 10 **和 11，然后在"载入****设备**"下的"部署方法"部分，选择"本地 **脚本"。** 

4. 选择 **下载载入程序包**。 我们建议将载入程序包保存为可移动驱动器。

5. 请按照以下文章中的指导操作：

   - Windows设备[：Windows本地脚本载入设备](../defender-endpoint/configure-endpoints-script.md#onboard-devices)
   - macOS 设备：[在 macOS 上手动](../defender-endpoint/mac-install-manually.md#client-configuration)部署 Microsoft Defender for Endpoint
   - Linux 设备： [手动在 Linux 上部署 Microsoft Defender for Endpoint](../defender-endpoint/linux-install-manually.md#client-configuration)

6. 继续[为设备运行检测](#run-a-detection-test)Windows测试。

> [!IMPORTANT]
> 如果出现问题且载入过程失败，请参阅 Microsoft Defender for Business ([预览) 疑难解答](mdb-troubleshooting.yml)。

## <a name="onboard-devices-using-microsoft-intune"></a>使用移动设备载入Microsoft Intune

如果你在获取 Defender for Business Microsoft Intune预览版之前 (过) ，可以使用 Microsoft Intune 载入设备。 若要获取有关此内容的帮助，请参阅设备[注册Microsoft Intune。](/mem/intune/enrollment/device-enrollment)

## <a name="run-a-detection-test"></a>运行检测测试

手动载入 Windows设备后，可以运行检测测试，以确保使用 Defender for Business 预览版 (一) 。

1. 在 Windows设备上，创建一个文件夹 `C:\test-MDATP-test` ：。

2. 以管理员角色打开命令提示符。

3. 在命令提示符窗口中，运行以下 PowerShell 命令：

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

命令运行后，命令提示符窗口将自动关闭。 如果成功，检测测试将标记为已完成，新载入设备的 Microsoft 365 Defender 门户中将在大约 10 分钟内显示新警报。

## <a name="what-if-i-want-to-offboard-a-device"></a>如果我想从设备中注销，该做什么？

如果你想要将设备载出，请按照以下步骤操作：

1. 转到"Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) () 并登录。

2. 在导航窗格中，**选择**"设置"，然后选择"**终结点"。**

3. 在 **"设备管理"** 下，选择 **"载出"。**

4. 选择操作系统，如 Windows 10 **和 11，** 然后在"部署方法"部分中的"载出 **设备**"下，选择"**本地脚本"。** 

5. 在确认屏幕中，查看信息，然后选择" **下载"** 继续。

6. 选择 **下载载出程序包**。 我们建议将载出包保存为可移动驱动器。

7. 在你想要从每台设备上运行脚本。 

   需要此任务的帮助？ 参阅以下资源：   

   - Windows设备：使用[Windows脚本的载出设备](../defender-endpoint/configure-endpoints-script.md#offboard-devices-using-a-local-script)
   - macOS 设备： [在 macOS 上卸载](../defender-endpoint/mac-resources.md#uninstalling)
   - Linux 设备： [在 Linux 上卸载](../defender-endpoint/linux-resources.md#uninstall)

> [!IMPORTANT]
> 将设备载出会导致设备停止向 Defender for Business 发送数据， (预览) 。 但是，在载出之前收到的数据最多保留六 (6) 个月。

## <a name="next-steps"></a>后续步骤

继续：

- [步骤 5：在 Microsoft Defender for Business 预览版中配置 (和) ](mdb-configure-security-settings.md)

- [开始使用 Microsoft Defender for Business (预览) ](mdb-get-started.md) 