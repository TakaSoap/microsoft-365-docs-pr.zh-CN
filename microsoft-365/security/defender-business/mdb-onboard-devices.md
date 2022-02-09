---
title: '将设备载入 Microsoft Defender for Business (预览版) '
description: '了解 Microsoft Defender for Business 预览版中的设备载入 (选项) '
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/07/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 709af580211d999e5a2f4117a773686542d37160
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2022
ms.locfileid: "62465283"
---
# <a name="onboard-devices-to-microsoft-defender-for-business-preview"></a>将设备载入 Microsoft Defender for Business (预览版) 

> [!IMPORTANT]
> Microsoft Defender for Business 现在为预览版，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 我们将于未来几周内载入一组初始客户和合作伙伴，并扩大预览版本，从而一般可用。 请注意，预览将启动 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

借助 Microsoft Defender for Business (预览) ，你可以从多个选项中进行选择以载入你的组织设备。 本文将引导你完成你的选项，并包括载入工作原理的概述。

## <a name="what-to-do"></a>需执行的操作

1. [了解载入方法](#types-of-onboarding-methods)，并确定是使用自动载入还是手动载入。

2. 执行下列操作之一：

   - 如果你使用的是自动载入，请继续执行步骤 5：在 [Microsoft Defender for Business ](mdb-configure-security-settings.md)中配置安全设置和策略 (预览) 。
   - 如果你要手动载入设备，请选择载入方法类型中的载入方法，然后按照该方法[](#types-of-onboarding-methods)的说明进行操作。
   - 如果你已在使用 Microsoft Intune，[请继续执行使用](#onboard-devices-using-microsoft-intune) Microsoft Intune。

3. [对新载入的设备](#run-a-detection-test) 运行检测测试。

4. [请参阅下一步](#next-steps)。 

本文还包括有关 [如何从设备载出的信息](#what-if-i-want-to-offboard-a-device)。

## <a name="types-of-onboarding-methods"></a>载入方法的类型

下表介绍了预览版中 Defender for Business 支持的载入方法类型。 
<br/><br/>

| 载入方法  | 说明  |
|---------|---------|
| **自动载入**<br/> (*已使用 Microsoft Endpoint Manager*)  | 如果你在获取 Defender for Business Microsoft Endpoint Manager预览版之前 (已) ，则 Defender for Business 将检测到这一点。 将询问你是否要对之前已载入到 Microsoft Endpoint Manager 的设备使用自动载入Microsoft Endpoint Manager。 <br/><br/>自动载入在 Defender for Business (预览版) 和 Microsoft Endpoint Manager 之间设置连接，然后将设备载入 Defender for Business (预览) 。 此选项使你可以快速、高效地将设备载入 Defender for Business (预览) 预览版。 当前Windows注册的所有Microsoft Endpoint Manager将载入 Defender for Business。 <br/><br/>如果选择自动载入，请跳过本文中的过程，然后继续执行步骤 5：在 [Microsoft Defender for Business ](mdb-configure-security-settings.md)中配置安全设置和策略 (预览) 。  |
| **本地脚本**<br/> (*预览期间推荐使用;可用于* 一次载入几台设备)   | 在预览期间，可以使用在 macOS、Windows 10 或 11 以及 Linux 设备上下载和运行的脚本在 Defender for Business (预览版) 中载入设备。 在设备上运行脚本将创建与 Azure Active Directory (Azure AD) 的信任，并注册设备Microsoft Intune。 此过程类似于将设备载入 [到 Microsoft Defender for Endpoint 的过程](../defender-endpoint/onboarding.md)。<br/><br/>若要使用此方法，请继续执行在设备上[使用](#onboard-a-device-using-a-local-script-in-defender-for-business)本地脚本载入Microsoft 365 Defender。 |
| **Microsoft Intune** <br/> (*已使用 Microsoft Intune)* | 如果你在获取 Defender for Business [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)预览版之前 (已) ，Microsoft Intune设备。 在预览版中，可以使用 Microsoft Intune将 Windows、iOS、macOS、Linux 和 Android 设备载入 Defender for Business (预览版) 。 <br/><br/>若要使用此方法，请参阅 [Intune 中的设备注册](/mem/intune/enrollment/device-enrollment)。 |
| **组策略** | [组策略](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)) 是一种基础结构，可用于通过组策略设置和组策略首选项为用户和计算机指定托管配置。 组策略对象 (GPO) 组策略容器和组策略模板组成的逻辑对象。 如果你的组织已在使用组策略，可以在 Defender for Business (预览版中创建 GPO，) 。<br/><br/>若要了解有关此方法的信息，请参阅使用组[Windows载入设备](../defender-endpoint/configure-endpoints-gp.md)。 | 
| **VDI 载入脚本** | 如果你的组织在 VDI 设备上使用非永久性 (基础结构) ，可以使用可下载的脚本载入这些终结点。 <br/><br/>若要了解有关此方法的信息，请参阅 [载入非永久性 VDI 设备](../defender-endpoint/configure-endpoints-vdi.md)。  |


> [!TIP]
> 如果在载入设备时出错，请参阅 [Microsoft Defender for Business (预览) 疑难解答](mdb-troubleshooting.yml)。 

## <a name="onboard-a-device-using-a-local-script-in-defender-for-business"></a>在 Defender for Business 中使用本地脚本载入设备

1. 转到 Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) ，然后登录。

2. 在导航窗格中，选择"**设置** > **Endpoints"**，然后在 **"设备管理**"下选择"**载入"**。

3. 选择操作系统，如 **Windows 10 11，然后在"载入** 设备"下的"部署方法"部分，选择"**本地脚本"**。 

4. 选择 **下载载入程序包**。 我们建议将载入程序包保存为可移动驱动器。

5. 请按照以下文章中的指导操作：

   - Windows设备：[Windows本地脚本载入设备](../defender-endpoint/configure-endpoints-script.md#onboard-devices)
   - macOS 设备： [在 macOS 上手动部署 Microsoft Defender for Endpoint](../defender-endpoint/mac-install-manually.md#client-configuration)
   - Linux 设备： [手动在 Linux 上部署 Microsoft Defender for Endpoint](../defender-endpoint/linux-install-manually.md#client-configuration)

6. 继续[为设备运行](#run-a-detection-test)检测Windows测试。

> [!IMPORTANT]
> 如果出现问题且载入过程失败，请参阅 [Microsoft Defender for Business (预览) 疑难解答](mdb-troubleshooting.yml)。

## <a name="onboard-devices-using-microsoft-intune"></a>使用移动设备载入Microsoft Intune

如果你在获取 Defender for Business Microsoft Intune预览版之前 (已) ，Microsoft Intune设备。 若要获取有关此内容的帮助，请参阅设备[注册Microsoft Intune](/mem/intune/enrollment/device-enrollment)。

## <a name="run-a-detection-test"></a>运行检测测试

手动载入 Windows 设备后，可以运行检测测试，以确保一切正常使用 Defender for Business (预览版) 。

1. 在Windows上，创建一个文件夹：`C:\test-MDATP-test`。

2. 以管理员角色打开命令提示符。

3. 在命令提示符窗口中，运行以下 PowerShell 命令：

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

命令运行后，命令提示符窗口将自动关闭。 如果成功，检测测试将标记为已完成，并且新载入设备的 Microsoft 365 Defender 门户中将在大约 10 分钟内显示新警报。

## <a name="what-if-i-want-to-onboard-devices-gradually"></a>如果我想逐步载入设备，该做什么？

如果你想要逐步载入组织的设备，请按照以下步骤操作：

1. 标识要载入的一组设备。

2. 转到 Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) ，然后登录。

3. 在导航窗格中，选择"**设置** > **Endpoints"**，然后在 **"设备管理**"下选择"**载入"**。

4. 选择操作系统 (如 Windows 10 和 **11)**，然后选择载入方法 (如本地 **脚本) 。** 按照为所选方法提供的指南操作。

5. 对要载入的每组设备重复此过程。 

> [!TIP]
> 每次载入设备时，都不必使用相同的载入程序包。 例如，可以使用本地脚本载入某些设备，稍后可以选择另一种方法载入更多设备。

## <a name="what-if-i-want-to-offboard-a-device"></a>如果我想从设备中注销，该做什么？

如果你想要将设备载出，请按照以下步骤操作：

1. 转到"Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 并登录。

2. 在导航窗格中 **，选择"** 设置"，然后选择"**终结点"**。

3. 在 **"设备管理"** 下，选择 **"载出"**。

4. 选择操作系统，如 **Windows 10 和 11**，然后在"载出设备"下的"部署方法"部分，选择"**本地脚本"**。 

5. 在确认屏幕中，查看信息，然后选择" **下载"** 继续。

6. 选择 **下载载出程序包**。 我们建议将载出包保存为可移动驱动器。

7. 在你想要从每台设备上运行脚本。 

   需要此任务的帮助？ 参阅以下资源：   

   - Windows设备：Windows[本地脚本的载出设备](../defender-endpoint/configure-endpoints-script.md#offboard-devices-using-a-local-script)
   - macOS 设备： [在 macOS 上卸载](../defender-endpoint/mac-resources.md#uninstalling)
   - Linux 设备： [在 Linux 上卸载](../defender-endpoint/linux-resources.md#uninstall)

> [!IMPORTANT]
> 将设备载出会导致设备停止向 Defender for Business 发送数据， (预览) 。 但是，在载出之前收到的数据最多保留六 (6) 个月。

## <a name="next-steps"></a>后续步骤

继续：

- [步骤 5：在 Microsoft Defender for Business 预览版中配置 (和) ](mdb-configure-security-settings.md)

- [开始使用 Microsoft Defender for Business (预览) ](mdb-get-started.md) 