---
title: 使用 WMI 配置 Microsoft Defender 防病毒
description: 了解如何使用 WMI 脚本在 Microsoft Defender for Endpoint 中检索、修改和更新设置来配置和管理 Microsoft Defender 防病毒。
keywords: wmi， 脚本， windows management instrumentation， 配置
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8d24a08ae3b8db710ca1727821690e5c87f056c3
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689970"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a>使用 Windows Management Instrumentation (WMI) 配置和管理 Microsoft Defender 防病毒

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Windows Management Instrumentation (WMI) 是一个脚本界面，可用于检索、修改和更新设置。

有关 WMI 的更多内容，Microsoft 开发人员网络 [System Administration 库](/windows/win32/wmisdk/wmi-start-page)。

Microsoft Defender 防病毒具有许多特定的 WMI 类，可用于执行与组策略和其他管理工具大多数相同的功能。 许多类都类似于 Defender [PowerShell cmdlet。](use-powershell-cmdlets-microsoft-defender-antivirus.md)

[MSDN Windows Defender WMIv2 提供程序](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)参考库列出了 Microsoft Defender 防病毒的可用 WMI 类，并包括示例脚本。

使用 WMI 所做的更改将影响部署或进行更改的终结点上的本地设置。 这意味着使用组策略、Microsoft Endpoint Configuration Manager 或 Microsoft Intune 部署策略可能会覆盖使用 WMI 所做的更改。 

你可以 [配置哪些设置可以使用本地策略覆盖在本地覆盖](configure-local-policy-overrides-microsoft-defender-antivirus.md)。

## <a name="related-topics"></a>相关主题

- [有关管理和配置工具的参考主题](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)