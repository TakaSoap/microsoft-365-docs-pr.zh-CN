---
title: 了解客户端分析器 HTML 报告
description: 了解如何分析 Microsoft Defender for Endpoint Client Analyzer HTML 报告
keywords: client analyzer report， html report， client analyzer
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6b345eb898b84de9f15772e11fdc92e1af5dde6a
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167006"
---
# <a name="understand-the-client-analyzer-html-report"></a>了解客户端分析器 HTML 报告

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

客户端分析器生成 HTML 格式的报告。 了解如何查看报告以确定潜在的传感器问题，以便排除它们。

使用下面的示例可了解报告。

 在载入到过期组织 ID 且无法到达所需的 Microsoft Defender 终结点 URL 之一的计算机上，分析器的输出示例：

![客户端分析器结果的图像。](images/147cbcf0f7b6f0ff65d200bf3e4674cb.png)

- 顶部列出了脚本版本和脚本运行时，仅供参考
- " **设备信息** "部分提供用于唯一标识运行分析器的设备的基本操作系统和设备标识符。
- 终结点 **安全详细信息** 提供有关与终结点相关的进程的 Microsoft Defender 的常规信息，Microsoft Defender 防病毒和传感器进程。 如果重要进程未如预期联机，则颜色将更改为红色。

  ![客户端分析器详细结果的图像](images/85f56004dc6bd1679c3d2c063e36cb80.png)

-   终结点 **安全详细信息** 提供有关与终结点相关的进程的 Microsoft Defender 的常规信息，Microsoft Defender 防病毒和传感器进程。 如果重要进程未如预期联机，则颜色将更改为红色。

  ![客户端分析器详细结果的图像。](images/85f56004dc6bd1679c3d2c063e36cb80.png)

-   On **Check Results Summary** you'll have an aggregated count for error， warning， or informational events detected by the analyzer.

-   On **Detailed Results** you'll see a list (sorted by severity) with the results and the guidance based on the observations made by the analyzer.

## <a name="open-a-support-ticket-to-microsoft-and-include-the-analyzer-results"></a>向 Microsoft 打开支持票证并包括分析工具结果

若要在打开支持 [票证时](contact-support.md#open-a-service-request)包含分析器结果文件，请确保使用"附件 **"部分并** 包括 `MDEClientAnalyzerResult.zip` 文件：

![附件提示的图像。](images/508c189656c3deb3b239daf811e33741.png)

> [!NOTE]
> 如果文件大小大于 25 MB，分配给您的案例的支持工程师将提供一个专用安全工作区来上载大文件进行分析。
