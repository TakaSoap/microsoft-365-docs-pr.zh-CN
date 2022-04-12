---
title: 评估 Microsoft Defender 防病毒软件
description: 各种规模的企业都可以使用本指南来评估和测试Windows中Microsoft Defender 防病毒提供的保护。
keywords: Microsoft Defender 防病毒、云保护、云、反恶意软件、安全性、Defender、评估、测试、保护、比较、实时保护
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 8c7ced9c85ec7c6075b44970d25e34ba5594404e
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787615"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>评估 Microsoft Defender 防病毒软件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- Microsoft Defender 防病毒
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

**平台**
- Windows

使用本指南可确定Microsoft Defender 防病毒如何保护你免受病毒、恶意软件和可能不需要的应用程序的侵害。

> [!TIP]
>还可以访问 [demo.wd.microsoft.com 的Microsoft Defender for Endpoint](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)演示网站，确认以下功能是否正常工作，并了解其工作原理：
>
> - 云端保护
> - 快速学习 (包括一见钟情) 
> - 可能不需要的应用程序阻止

> [!NOTE]
> 位于 demo.wd.microsoft.com 处的 Defender for Endpoint 演示网站已弃用，并将在未来删除。

它介绍了适用于小型和大型企业的Microsoft Defender 防病毒的重要下一代保护功能，以及它们如何在整个网络中增加恶意软件检测和保护。

可以选择单独配置和评估每个设置，或者一次性进行全部评估。 我们已根据典型评估方案对类似的设置进行分组，并包含有关使用 PowerShell 启用设置的说明。

该指南以 PDF 格式提供，可用于脱机查看：

- [下载 PDF 格式的指南](https://www.microsoft.com/download/details.aspx?id=54795)

还可以下载 PowerShell，该 PowerShell 将自动启用指南中描述的所有设置。 可以与上面的 PDF 下载一起获取脚本，也可以从PowerShell 库单独获取脚本：

- [下载 PowerShell 脚本以自动配置设置](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> 本指南目前用于对Microsoft Defender 防病毒进行单机评估。 在本指南中启用所有设置可能不适合实际部署。
>
> 有关在网络中实际部署和监视Microsoft Defender 防病毒的最新建议，请参阅[“部署Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)。

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

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [部署Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)