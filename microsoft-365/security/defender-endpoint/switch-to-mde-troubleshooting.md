---
title: 切换到用户时的问题Microsoft Defender for Endpoint
description: 了解如何在切换到 Microsoft Defender for Endpoint 时解决问题。
keywords: 迁移， windows defender， 高级终结点保护， 防病毒， 反恶意软件， 被动模式， 主动模式， 疑难解答
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365solution-scenario
- M365-security-compliance
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 04/01/2022
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 8334ce03bac5b7d4518433f83ab34d5f86e71339
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634154"
---
# <a name="troubleshooting-issues-when-switching-to-microsoft-defender-for-endpoint"></a>切换到用户时的问题Microsoft Defender for Endpoint

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

本文为在从非 Microsoft 终结点保护解决方案切换到安全保护解决方案时遇到问题的安全管理员提供了Microsoft Defender for Endpoint。

## <a name="microsoft-defender-antivirus-is-getting-uninstalled-on-windows-server"></a>Microsoft Defender 防病毒服务器上卸载Windows

当你切换到 Defender for Endpoint 时，你首先在活动模式下使用非 Microsoft 防病毒/反恶意软件保护。 作为设置过程的一部分，在被动Microsoft Defender 防病毒配置策略。 有时，非 Microsoft 防病毒/反恶意软件解决方案可能会阻止 Microsoft Defender 防病毒 Server Windows运行。 事实上，它看起来可能Microsoft Defender 防病毒服务器Windows服务器。

若要解决此问题，请执行以下步骤：

1. [将Microsoft Defender for Endpoint添加到排除列表](#add-microsoft-defender-for-endpoint-to-the-exclusion-list)。
2. [手动Microsoft Defender 防病毒被动模式。](#set-microsoft-defender-antivirus-to-passive-mode-manually)

### <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list"></a>将Microsoft Defender for Endpoint添加到排除列表

Defender for Endpoint 的某些排除项必须在现有的非 Microsoft 终结点保护解决方案中定义。 请确保添加以下排除项：

`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`

`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCM.exe`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-manually"></a>手动Microsoft Defender 防病毒被动模式

在 Windows Server 2019、Windows Server 版本 1803 或更高版本、Windows Server 2016 或 Windows Server 2012 R2 上，您必须手动将 Microsoft Defender 防病毒 设置为被动模式。 此操作有助于防止在服务器上安装多个防病毒产品导致的问题。 可以使用 PowerShell Microsoft Defender 防病毒或注册表项组策略被动模式。

可以通过设置Microsoft Defender 防病毒注册表项来将用户设置为被动模式：

路径： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`

名称：`ForceDefenderPassiveMode`

类型： `REG_DWORD`

值：`1`

> [!NOTE]
> 若要使被动模式在运行 Windows Server 2016 和 Windows Server 2012 R2 的终结点上运行，必须使用载入 Windows 服务器中的[说明载入这些终结点](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)。

有关详细信息，请参阅 Microsoft Defender 防病毒 [Server Windows。](microsoft-defender-antivirus-on-windows-server.md)

## <a name="microsoft-defender-antivirus-seems-to-be-stuck-in-passive-mode"></a>Microsoft Defender 防病毒似乎卡在被动模式下

如果Microsoft Defender 防病毒卡在被动模式下，请手动按照以下步骤将模式设置为活动模式：

1. 在 Windows设备上，以管理员角色打开注册表编辑器。

2. 转到 `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`。

3. 设置或定义名为 **REG_DWORD** `ForceDefenderPassiveMode`项，并设置其值 `0`。

4. 重新启动设备。

> [!IMPORTANT]
> 如果在执行此过程后仍无法将Microsoft Defender 防病毒模式设置为活动模式，请联系[支持人员](../../admin/get-help-support.md)。

## <a name="i-am-having-trouble-re-enabling-microsoft-defender-antivirus-on-windows-server-2016"></a>我在重新启用Microsoft Defender 防病毒时Windows Server 2016

如果您在 Windows Server 2016 使用非 Microsoft 防病毒/反恶意软件解决方案，则现有解决方案可能需要Microsoft Defender 防病毒或卸载此解决方案。 您可以使用恶意软件防护[Command-Line实用工具](command-line-arguments-microsoft-defender-antivirus.md)重新启用Microsoft Defender 防病毒上的Windows Server 2016。

1. 作为服务器的本地管理员，打开命令提示符。

2. 运行以下命令：`MpCmdRun.exe -wdenable`

3. 重启设备。

## <a name="see-also"></a>另请参阅

- [Microsoft Defender 防病毒安全产品的兼容性](microsoft-defender-antivirus-compatibility.md)

- [适用于 Defender for Endpoint 中Windows的载入工具和方法](configure-endpoints.md) 
