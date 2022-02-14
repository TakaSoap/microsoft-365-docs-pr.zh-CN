---
title: 评估 Microsoft Defender 防病毒软件
description: 各种规模的企业都可以使用本指南评估和测试企业在Microsoft Defender 防病毒提供的Windows。
keywords: Microsoft Defender 防病毒， 云保护， 云， 反恶意软件， 安全性， defender， 评估， 测试， 保护， 比较， 实时保护
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
ms.openlocfilehash: 4dd25a599f144a60bfd2ebeb3e9bb8b1876bd3c6
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2022
ms.locfileid: "62807412"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>评估 Microsoft Defender 防病毒软件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

使用本指南可确定Microsoft Defender 防病毒保护您免受病毒、恶意软件和可能不需要的应用程序的侵害。

> [!TIP]
>还可以访问 Microsoft Defender for Endpoint 演示网站，demo.wd.microsoft.com 以确认以下[](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)功能是否正常工作并查看这些功能如何工作：
>
> - 云端保护
> - 快速学习 (包括首次看到时阻止) 
> - 可能不需要的应用程序阻止

> [!NOTE]
> 位于 Demo.wd.microsoft.com 的 Defender for Endpoint 演示网站已弃用，并且将在未来删除。

它介绍了适用于中小型企业的 Microsoft Defender 防病毒 重要下一代保护功能，以及这些功能如何增强整个网络的恶意软件检测和保护。

可以选择单独配置和评估每个设置，也可以一次配置和评估所有设置。 我们已根据典型评估方案对类似的设置进行分组，并包括有关使用 PowerShell 启用这些设置的说明。

本指南以 PDF 格式提供，以便脱机查看：

- [下载 PDF 格式的指南](https://www.microsoft.com/download/details.aspx?id=54795)

还可以下载 PowerShell，以自动启用指南中所述的所有设置。 你可以与上述 PDF 下载一起获取脚本，也可以从 PowerShell 库单独获取：

- [下载 PowerShell 脚本以自动配置设置](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> 本指南目前适用于单台计算机对Microsoft Defender 防病毒。 启用本指南中所有设置可能不适合实际部署。
>
> 有关跨网络实际部署和监视 Microsoft Defender 防病毒的最新建议，请参阅部署[Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)。

## <a name="related-topics"></a>相关主题

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [部署Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)