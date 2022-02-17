---
title: '将设备载入 Microsoft Defender for Business (预览) '
description: '了解 Microsoft Defender for Business 预览版中的设备载入 (选项) '
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/16/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 073478300e6b5a9d5a9fc10e634f6e3113897fb3
ms.sourcegitcommit: 007822d16e332522546e948f5c216327254a4d49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2022
ms.locfileid: "62879236"
---
# <a name="onboard-devices-to-microsoft-defender-for-business-preview"></a>将设备载入 Microsoft Defender for Business (预览) 

> [!IMPORTANT]
> Microsoft Defender for Business 现在为预览版，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 我们将于未来几周内载入一组初始客户和合作伙伴，并扩大预览版本，从而一般可用。 请注意，预览将启动 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

Defender for Business 中的设备载入体验是在 Microsoft Defender for Endpoint 中使用的相同设备载入过程上构建的。 观看以下视频，了解其工作方式：<br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

借助 Microsoft Defender for Business (预览) ，你可以从多个选项中进行选择以载入你的组织设备。 本文将引导你完成你的选项，并包括载入工作原理的概述。

> [!TIP]
> 若要查看有关 Defender for Endpoint 中的设备载入的更多详细信息，请参阅载入设备和为 [终结点功能配置 Microsoft Defender](../defender-endpoint/onboard-configure.md)。

## <a name="what-to-do"></a>需执行的操作

1. 查看载入 [设备的选项](#device-onboarding-methods)。

2. 使用下列方法之一载入设备：
    - [自动载入Windows注册的设备Microsoft Endpoint Manager](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)
    - [适用于 Windows macOS 和 Linux 设备的本地脚本](#onboard-devices-using-a-local-script-in-defender-for-business)
    - [Microsoft Endpoint Manager、平板电脑和手机的移动设备](#onboard-devices-using-microsoft-endpoint-manager)
    - [适用于设备Windows策略](#onboard-windows-devices-using-group-policy)
    - [此处未列出的另一种方法](#onboard-devices-using-a-method-not-listed-here)

3. [对新载入的设备](#run-a-detection-test)运行检测Windows测试。

4. [请参阅你的下一步](#next-steps)。 

本文还包括有关将设备 [载出的信息](#offboarding-a-device)。

## <a name="device-onboarding-methods"></a>设备载入方法

下表介绍了将设备载入 Defender for Business 最常用的方法。 

| 载入方法  | 说明  |
|---------|---------|
| **自动载入**<br/> (*已使用 Microsoft Endpoint Manager)* | 自动载入设置 Defender for Business (预览版) 和 Microsoft Endpoint Manager 之间的连接，然后将 Windows 设备载入到 Defender for Business (预览版) 。 设备必须已注册Endpoint Manager。<br/><br/>若要了解更多信息，请参阅在 Windows [中注册的设备使用](#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)自动载入Microsoft Endpoint Manager。 |
| **本地脚本**<br/> (*预览期间推荐使用;可用于* 一次载入几台设备)   | 可以使用在 Windows、macOS 或 Linux 设备上) 下载并运行的脚本将计算机载入 Defender for Business (预览版。 该脚本设置与 Azure Active Directory的信任，并注册设备。<br/><br/>若要使用此方法，请参阅 [使用 Defender for Business 中的本地脚本载入设备](#onboard-devices-using-a-local-script-in-defender-for-business)。 |
| **Microsoft Intune** 或 **Microsoft Endpoint Manager**<br/> (*已使用 Microsoft Intune* 或 Endpoint Manager)  | [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)[移动设备管理是](/mem/intune/enrollment/device-enrollment)移动设备管理的一Endpoint Manager。 如果你在获得 Defender for Business Endpoint Manager 预览版 (之前) ，你可以选择继续使用 Endpoint Manager 载入和管理设备<br/><br/>若要使用此方法，请参阅使用 [Microsoft Endpoint Manager 载入设备](#onboard-devices-using-microsoft-endpoint-manager)。 |
| **组策略** | 如果你的组织已在使用组策略，可以在 Defender for Business (预览版中创建 GPO，) 。<br/><br/>若要详细了解此方法，请参阅使用组[Windows载入设备](#onboard-windows-devices-using-group-policy)。 | 

> [!IMPORTANT]
> 如果出现问题且载入过程失败，请参阅 [Microsoft Defender for Business 疑难解答](mdb-troubleshooting.yml)。

## <a name="automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager"></a>自动载入Windows注册的设备Microsoft Endpoint Manager

自动载入选项仅适用于Windows设备。 如果你的组织在获得 Defender for Business (预览版) 之前已在 Microsoft Intune 中使用的是 Microsoft Endpoint Manager、Microsoft Intune 或移动设备管理 (MDM) ，并且你已注册 Windows 设备，则此选项可用Endpoint Manager。 

如果Windows设备已在 Endpoint Manager 中注册，则 Defender for Business 将在你设置和配置 Defender for Business 的过程中检测这些设备。 系统将会询问你是否要将自动载入用于所有或部分 Windows设备。 

自动载入过程在 Defender for Business 和 Endpoint Manager 之间设置连接，然后将设备载入到 Defender for Business。 你可以选择一次载入所有注册Windows设备，或选择要载入的一Windows设备。

若要了解的详细信息，请参阅使用向导设置 [Microsoft Defender for Business (预览版) ](mdb-use-wizard.md)。

## <a name="onboard-devices-using-a-local-script-in-defender-for-business"></a>在 Defender for Business 中使用本地脚本载入设备

可以使用本地脚本将 Windows macOS 和 Linux 设备载入 Defender for Business。 当你在设备上运行载入脚本时，它将创建与 Azure Active Directory 的信任、在 Microsoft Endpoint Manager 中注册设备，以及将设备载入 Defender for Business。 此方法对于在 Defender for Business 中载入设备和一次载入几台设备非常有用。

1. 转到"Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) ，然后登录。

2. 在导航窗格中，选择"**设置** > **""Endpoints"**，然后在 **"设备管理**"下，选择"**载入"**。

3. 选择操作系统，如 Windows 10 **和 11，然后在"载入****设备**"下的"部署方法"部分，选择"**本地脚本"**。 

4. 选择 **下载载入程序包**。 我们建议将载入程序包保存为可移动驱动器。

5. 请按照以下文章中的指导操作：

   - Windows设备：[Windows本地脚本载入设备](../defender-endpoint/configure-endpoints-script.md#onboard-devices)
   - macOS 设备： [在 macOS 上手动部署 Microsoft Defender for Endpoint](../defender-endpoint/mac-install-manually.md#client-configuration)
   - Linux 设备： [手动在 Linux 上部署 Microsoft Defender for Endpoint](../defender-endpoint/linux-install-manually.md#client-configuration)

> [!IMPORTANT]
> 如果出现问题且载入过程失败，请参阅 [Microsoft Defender for Business (预览版) 疑难解答](mdb-troubleshooting.yml)。

## <a name="onboard-devices-using-microsoft-endpoint-manager"></a>使用移动设备载入Microsoft Endpoint Manager

如果你在获取 Defender for Business Microsoft Intune预览版 (之前) ，你可以继续使用 Microsoft Intune 载入设备。 借助Endpoint Manager，你可以载入计算机、平板电脑和手机。 

请参阅[设备注册Microsoft Intune](/mem/intune/enrollment/device-enrollment)。

## <a name="onboard-windows-devices-using-group-policy"></a>使用组策略载入 Windows 设备

[组策略](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)) 是一种基础结构，可用于通过组策略设置和组策略首选项为用户和计算机指定托管配置。 组策略对象 (GPO) 组策略容器和组策略模板组成的逻辑对象。 

如果你的组织已在使用组策略来管理设备，可以使用组策略将设备载入 Defender for Business。 如果你对组策略很新，我们建议使用另一种方法，Endpoint Manager或本地脚本。 

请参阅[使用Windows载入设备](../defender-endpoint/configure-endpoints-gp.md)。

## <a name="onboard-devices-using-a-method-not-listed-here"></a>使用此处未列出的方法载入设备

如果你想要使用本文未列出的其他方法载入设备，请参阅载入 [和配置工具选项](../defender-endpoint/onboard-configure.md#onboarding-and-configuration-tool-options)。

## <a name="run-a-detection-test"></a>运行检测测试

将 Windows 设备载入 Defender for Business (预览版) 后，可以在 Windows 设备上运行检测测试，以确保一切正常。

1. 在Windows上，创建一个文件夹：`C:\test-MDATP-test`。

2. 以管理员角色打开命令提示符。

3. 在命令提示符窗口中，运行以下 PowerShell 命令：

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

命令运行后，命令提示符窗口将自动关闭。 如果成功，检测测试将标记为已完成，并且新载入的设备的 Microsoft 365 Defender 门户 ([https://security.microsoft.com](https://security.microsoft.com)) 中将在大约 10 分钟内显示新警报。

## <a name="gradual-device-onboarding"></a>逐步设备载入

如果你想要逐步载入组织的设备，请按照以下步骤操作：

1. 标识要载入的一组设备。

2. 转到"Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) ，然后登录。

3. 在导航窗格中，选择"**设置** > **""Endpoints"**，然后在 **"设备管理**"下，选择"**载入"**。

4. 选择操作系统 (如 **Windows 10 和 11)**，然后选择载入方法 **(如本地** 脚本) 。 按照为所选方法提供的指南操作。

5. 对要载入的每组设备重复此过程。 

> [!TIP]
> 每次载入设备时，都不必使用相同的载入程序包。 例如，可以使用本地脚本载入某些设备，稍后可以选择另一种方法载入更多设备。

## <a name="offboarding-a-device"></a>将设备载出

如果你想要将设备载出，请按照以下步骤操作：

1. 转到"Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 并登录。

2. 在导航窗格中 **，选择"** 设置"，然后选择"**终结点"**。

3. 在 **"设备管理"** 下，选择 **"载出"**。

4. 选择操作系统，如 Windows 10 **和 11**，然后在"载出设备"下的"部署方法"部分，选择"**本地脚本"**。 

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