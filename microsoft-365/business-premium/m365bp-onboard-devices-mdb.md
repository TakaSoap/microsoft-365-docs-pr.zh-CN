---
title: 将组织的设备载入 Microsoft Defender for Business
description: 将组织的设备载入 Microsoft Defender for Business
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/08/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 4e6d689a040963453bd3beac32593220e04f94dc
ms.sourcegitcommit: a9266e4e7470e8c1e8afd31fef8d266f7849d781
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2022
ms.locfileid: "63406506"
---
# <a name="onboard-managed-devices-to-microsoft-defender-for-business"></a>将托管设备载入 Microsoft Defender for Business

将设备载入 Microsoft Defender for Business，以使用下一代保护 (防病毒、反恶意软件和云提供的保护) 、防火墙保护、Web 内容筛选等进行保护。 

若要载入设备，你可以从多个选项中进行选择：

- [对已注册Windows的设备使用自动载入Microsoft Endpoint Manager](#use-automatic-onboarding-for-windows-devices-that-are-already-enrolled-in-microsoft-endpoint-manager)
- [使用本地脚本载入 Windows 和 macOS 设备](#use-a-local-script-to-onboard-windows-and-macos-devices)
- [使用 Endpoint Manager注册](#use-microsoft-endpoint-manager-to-enroll-devices)设备 (Windows、macOS、iOS 和 Android) 然后将 Defender for Business 策略应用于这些设备

本文还包括：

- [如何在设备上运行检测Windows测试](#run-a-detection-test-on-a-windows-device)
- [如何逐步载入设备](#onboard-devices-gradually)
- [在设备被替换](#offboard-a-device) 或某人离开组织时如何离开设备

> [!IMPORTANT]
> 如果出现问题且载入过程失败，请参阅 [Microsoft Defender for Business 疑难解答](../security/defender-business/mdb-troubleshooting.yml)。

## <a name="use-automatic-onboarding-for-windows-devices-that-are-already-enrolled-in-microsoft-endpoint-manager"></a>对已注册Windows的设备使用自动载入Microsoft Endpoint Manager

自动载入选项仅适用于Windows设备。 如果你的组织在你获得 Defender for Business 之前已在 Microsoft Intune 中使用 Microsoft Endpoint Manager、Microsoft Intune 或移动设备管理 (MDM) ，并且你已注册 Windows 设备，则自动载入可用Endpoint Manager。 

如果Windows设备已在 Endpoint Manager 中注册，则 Defender for Business 将在你设置和配置 Defender for Business 的过程中检测这些设备。 系统将会询问你是否要将自动载入用于所有或部分 Windows设备。 你可以一次Windows所有设备，或选择开始使用的特定设备，然后以后添加更多设备。

若要详细了解自动载入，请参阅使用向导设置 [Microsoft Defender for Business 中的](../security/defender-business/mdb-use-wizard.md)步骤 2。

## <a name="use-a-local-script-to-onboard-windows-and-macos-devices"></a>使用本地脚本载入 Windows 和 macOS 设备

可以使用本地脚本载入 Windows macOS 设备。 当你在设备上运行载入脚本时，如果) 不存在该信任，它将创建与 Azure Active Directory (的信任，在 Microsoft Endpoint Manager (中注册设备（如果尚未注册) ）然后将设备载入到 Defender for Business。 

使用此方法，一次可载入最多 10 台设备。

1. 转到 Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) ，然后登录。

2. 在导航窗格中，选择"**设置** > **""Endpoints"**，然后在 **"设备管理**"下选择"**载入"**。

3. 选择操作系统（如 **Windows 10 和 11**，然后在"载入设备"下的"部署方法"部分，选择"**本地脚本"**。 

4. 选择 **下载载入程序包**。 我们建议将载入程序包保存为可移动驱动器。

5. 请按照以下文章中的指导操作：

   - Windows设备：[Windows本地脚本载入设备](../security/defender-endpoint/configure-endpoints-script.md#onboard-windows-devices-using-a-local-script)
   - macOS 设备： [在 macOS 上手动部署 Microsoft Defender for Endpoint](../security/defender-endpoint/mac-install-manually.md#download-installation-and-onboarding-packages)

## <a name="use-microsoft-endpoint-manager-to-enroll-devices"></a>使用Microsoft Endpoint Manager注册设备

如果你已在使用 Endpoint Manager (包括 Microsoft Intune 和移动设备管理) ，那么在你获得 Defender for Business 之前，你可以继续使用 Endpoint Manager 载入你的组织设备。 借助Endpoint Manager，你可以载入计算机、平板电脑和手机，包括 iOS 和 Android 设备。

如果你的组织使用的是 Android 设备，请使用此方法。

请参阅[设备注册Microsoft Intune](/mem/intune/enrollment/device-enrollment)。

需要此处的过程

## <a name="run-a-detection-test-on-a-windows-device"></a>在设备上运行检测Windows测试

将设备载入 Windows Defender for Business 后，可以在 Windows 设备上运行检测测试，以确保一切正常。

1. 在 Windows 设备上，创建一个文件夹：`C:\test-MDATP-test`。

2. 以管理员角色打开命令提示符。

3. 在命令提示符窗口中，运行以下 PowerShell 命令：

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

命令运行后，命令提示符窗口将自动关闭。 如果成功，检测测试将标记为已完成，并且新载入的设备的 Microsoft 365 Defender 门户 ([https://security.microsoft.com](https://security.microsoft.com)) 将在大约 10 分钟内显示新警报。

## <a name="onboard-devices-gradually"></a>逐步载入设备

如果你想要逐步载入设备（我们称之为逐步设备载入） *，* 请按照以下步骤操作： 

1. 标识要载入的一组设备。

2. 转到 Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) ，然后登录。

3. 在导航窗格中，选择"**设置** > **""Endpoints"**，然后在 **"设备管理**"下选择"**载入"**。

4. 选择操作系统 (如 Windows 10 和 **11)**，然后选择载入方法 **(如本地** 脚本) 。 按照为所选方法提供的指南操作。

5. 对要载入的每组设备重复此过程。 

> [!TIP]
> 每次载入设备时，都不必使用相同的载入程序包。 例如，可以使用本地脚本载入某些设备，稍后可以选择另一种方法载入更多设备。

## <a name="offboard-a-device"></a>载出设备

如果你想要将设备载出，请按照以下步骤操作：

1. 转到"Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 并登录。

2. 在导航窗格中 **，选择"** 设置"，然后选择"**终结点"**。

3. 在 **"设备管理"** 下，选择 **"载出"**。

4. 选择操作系统，如 Windows 10 **11**，然后在"载出设备"下的"部署方法"部分，选择"**本地脚本"**。 

5. 在确认屏幕中，查看信息，然后选择" **下载"** 继续。

6. 选择 **下载载出程序包**。 我们建议将载出包保存为可移动驱动器。

7. 在你想要从每台设备上运行脚本。 需要此任务的帮助？ 参阅以下资源：   

   - Windows设备：使用[Windows脚本的载出设备](../security/defender-endpoint/configure-endpoints-script.md#offboard-devices-using-a-local-script)
   - macOS 设备： [在 macOS 上卸载](../security/defender-endpoint/mac-resources.md#uninstalling)

> [!IMPORTANT]
> 将设备载出会导致设备停止向 Defender for Business 发送数据。 但是，在载出之前收到的数据最多保留六 (6) 个月。

## <a name="next-steps"></a>后续步骤

[查看修复方法中的Microsoft 365 商业高级版](m365bp-review-remediation-actions-devices.md)