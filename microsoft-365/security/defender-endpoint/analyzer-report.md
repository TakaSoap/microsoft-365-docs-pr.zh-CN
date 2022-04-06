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
ms.collection: m365-security-compliance
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1f843c62d44ed7c25f07568cc0ee92709fb080a7
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468890"
---
# <a name="understand-the-client-analyzer-html-report"></a>了解客户端分析器 HTML 报告

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

客户端分析器生成 HTML 格式的报告。 了解如何查看报告以确定潜在的传感器问题，以便排除它们。

使用下面的示例可了解报告。

 在载入到过期组织 ID 且无法到达所需的 Microsoft Defender 终结点 URL 之一的计算机上，分析器的输出示例：

:::image type="content" source="images/147cbcf0f7b6f0ff65d200bf3e4674cb.png" alt-text="MDE 客户端分析器结果页" lightbox="images/147cbcf0f7b6f0ff65d200bf3e4674cb.png":::

- 顶部列出了脚本版本和脚本运行时，仅供参考
- " **设备信息** "部分提供用于唯一标识运行分析器的设备的基本操作系统和设备标识符。
- 终结点 **安全详细信息** 提供有关与终结点相关的进程的 Microsoft Defender 的常规信息，Microsoft Defender 防病毒和传感器进程。 如果重要进程未如预期联机，则颜色将更改为红色。
  
-   终结点 **安全详细信息** 提供有关与终结点相关的进程的 Microsoft Defender 的常规信息，Microsoft Defender 防病毒和传感器进程。 如果重要进程未如预期联机，则颜色将更改为红色。

    :::image type="content" source="images/85f56004dc6bd1679c3d2c063e36cb80.png" alt-text="&quot;检查结果摘要&quot;页" lightbox="images/85f56004dc6bd1679c3d2c063e36cb80.png":::

-   在 **"检查结果摘要**"中，您将具有分析器检测到的错误、警告或信息事件的聚合计数。

-   On **Detailed Results**， you'll see a list (sorted by severity) with the results and the guidance based on the observations made by the analyzer.

## <a name="open-a-support-ticket-to-microsoft-and-include-the-analyzer-results"></a>向 Microsoft 打开支持票证并包括分析工具结果

若要在打开支持 [票证时](contact-support.md#open-a-service-request)包含分析器结果文件，请确保使用"附件 **"部分并** 包括 `MDEClientAnalyzerResult.zip` 文件：

:::image type="content" source="images/508c189656c3deb3b239daf811e33741.png" alt-text="附件提示" lightbox="images/508c189656c3deb3b239daf811e33741.png":::

> [!NOTE]
> 如果文件大小大于 25 MB，分配给您的案例的支持工程师将提供一个专用安全工作区来上载大文件进行分析。
