---
title: 使用 PowerShell cmdlet 配置并运行Microsoft Defender 防病毒
description: 在Windows 10和Windows 11中，可以使用 PowerShell cmdlet 运行扫描、更新安全智能以及更改 Microsoft Defender 防病毒。
keywords: 扫描， 命令行， mpcmdrun， defender
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: bfcf100d4935895b66e781c7be0fa2e3c9cb829a
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110687"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a>使用 PowerShell cmdlet 配置和管理Microsoft Defender 防病毒

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

可以使用 PowerShell 在 Windows Defender 中执行各种Windows Defender。 与命令提示符或命令行类似，PowerShell 是基于任务的命令行 shell 和脚本语言，专为系统管理设计。 可以在 MSDN 上的 [PowerShell 中心中阅读有关它的更多信息](/previous-versions/msdn10/mt173057(v=msdn.10))。

有关 cmdlet 及其函数和可用参数的列表，请参阅 Defender for [Cloud cmdlet 主题](/powershell/module/defender) 。

PowerShell cmdlet 在 Windows Server 环境中最有用，这些环境不依赖图形用户界面 (GUI) 配置软件。

> [!NOTE]
> PowerShell cmdlet 不应用作完整网络策略管理基础结构（如[Microsoft Endpoint Configuration Manager、](/configmgr)组策略管理控制台或 Microsoft Defender 防病毒[](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))[组策略 ADMX 模板）的替换](https://www.microsoft.com/download/101445)。

使用 PowerShell 所做的更改将影响部署或进行更改的终结点上的本地设置。 这意味着，使用组策略、Microsoft Endpoint Configuration Manager或Microsoft Intune部署策略可能会覆盖使用 PowerShell 所做的更改。

你可以 [配置哪些设置可以使用本地策略覆盖本地覆盖](configure-local-policy-overrides-microsoft-defender-antivirus.md)。

PowerShell 通常安装在 文件夹 下 `%SystemRoot%\system32\WindowsPowerShell` 。

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a>使用 Microsoft Defender 防病毒 PowerShell cmdlet

1. 在搜索Windows中，键入 **powershell**。
2. Select **Windows PowerShell** from the results to open the interface.
3. 输入 PowerShell 命令和任何参数。

> [!NOTE]
> 您可能需要在管理员模式下打开 PowerShell。 右键单击用户策略中的 **"开始"菜单，** 单击"以管理员角色运行"，在权限提示符下单击"是"。

若要打开任何 cmdlet 的联机帮助，请键入以下内容：

```PowerShell
Get-Help <cmdlet> -Online
```

省略 `-online` 参数可获取本地缓存的帮助。

## <a name="related-topics"></a>相关主题

- [有关管理和配置工具的参考主题](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender 防病毒 Cmdlet](/powershell/module/defender)
