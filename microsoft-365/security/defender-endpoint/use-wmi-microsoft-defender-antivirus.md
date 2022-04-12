---
title: 使用 WMI 配置Microsoft Defender 防病毒
description: 了解如何使用 WMI 脚本在Microsoft Defender for Endpoint中检索、修改和更新设置来配置和管理Microsoft Defender 防病毒。
keywords: wmi、脚本、Windows 管理检测、配置
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: a525deb526f61f8500f42cc918380fdfa9c52861
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787616"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a>使用Windows管理检测 (WMI) 来配置和管理Microsoft Defender 防病毒

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

Windows管理检测 (WMI) 是一个脚本接口，可用于检索、修改和更新设置。

在 [Microsoft 开发人员网络系统管理库](/windows/win32/wmisdk/wmi-start-page)中阅读有关 WMI 的详细信息。

Microsoft Defender 防病毒具有许多特定的 WMI 类，可用于执行与组策略和其他管理工具相同的大多数函数。 许多类类似于 [Defender for Cloud PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)。

[MSDN Windows Defender WMIv2 提供程序参考库](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)列出了可用于Microsoft Defender 防病毒的 WMI 类，并包含示例脚本。

使用 WMI 所做的更改将影响部署或进行更改的终结点上的本地设置。 这意味着，使用组策略、Microsoft Endpoint Configuration Manager或Microsoft Intune部署策略可以覆盖使用 WMI 所做的更改。 

可以 [使用本地策略重写来配置可在本地重写哪些设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="related-topics"></a>相关主题

- [有关管理和配置工具的参考主题](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
