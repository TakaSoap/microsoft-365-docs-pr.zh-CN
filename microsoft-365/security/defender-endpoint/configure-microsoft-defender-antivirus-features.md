---
title: 配置 Microsoft Defender 防病毒软件功能
description: 可以使用 Intune、Microsoft Endpoint Configuration Manager、组策略 和 PowerShell 配置Microsoft Defender 防病毒功能。
keywords: Microsoft Defender 防病毒、反恶意软件、安全性、Defender、配置、配置、配置管理器、Microsoft Endpoint Configuration Manager、SCCM、Intune、MDM、移动设备管理、GP、组策略、PowerShell
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 10/14/2021
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 8a1aa78a153e11f1a36fe9f7dcbd85322e6f258d
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787943"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>配置 Microsoft Defender 防病毒软件功能


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender 防病毒

**平台**
- Windows

可以使用多种工具配置Microsoft Defender 防病毒，例如：

- 包括Microsoft Intune和Microsoft Endpoint Configuration Manager) 的Microsoft Endpoint Manager (
- 组策略
- PowerShell cmdlet
- Windows Management Instrumentation (WMI)
- [租户附加](/mem/configmgr/tenant-attach/)

可以配置以下广泛的功能类别：

- 云提供的保护。 请参阅[云提供的保护和Microsoft Defender 防病毒](cloud-protection-microsoft-defender-antivirus.md)

- 始终实时保护，包括行为、启发式和基于机器学习的保护。 请参阅 [“配置行为”、“启发式”和“实时保护](configure-protection-features-microsoft-defender-antivirus.md)”。

- 最终用户如何在单个终结点上与客户端交互。 参阅以下资源：
  - [阻止用户查看或与Microsoft Defender 防病毒用户界面交互](prevent-end-user-interaction-microsoft-defender-antivirus.md)
  - [阻止或允许用户在本地修改Microsoft Defender 防病毒策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)

> [!TIP]
> 查看 [有关管理和配置工具的参考主题](configuration-management-reference-microsoft-defender-antivirus.md)。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)