---
title: 使用 Power Automate
description: 了解电源自动化Microsoft 365 Defender以及如何使用它们。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 自定义检测， 架构， secops
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: a707de259897080f8e726aed70618ea6505bdea6
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60717406"
---
# <a name="use-power-automate-in-microsoft-365-defender"></a>在Power Automate Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

> 想要体验 Microsoft 365 Defender？你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。
>

SecOps (新式安全) 团队需要自动化才能高效工作。 为了专注于搜寻和调查真实威胁，SecOps 团队Power Automate警报列表进行会审并消除不是威胁的警报。  

## <a name="criteria-for-resolving-alerts"></a>解决警报的条件

- 用户已打开外出消息

- 用户未标记为高风险

如果两者都为 true，则 SecOps 将警报标记为合法旅行并解决。 通知在解决后Microsoft Teams中发布。 

## <a name="connect-power-automate-to-microsoft-cloud-app-security"></a>连接 Power Automate Microsoft Cloud App Security

若要创建自动化，你需要一个 API 令牌，然后才能将Power Automate连接到MICROSOFT CLOUD APP SECURITY (MCAS) 。 

1. 单击 **设置"，** 选择"**安全扩展"，** 然后单击"API令牌"选项卡中的"**添加令牌**"。 

2. 为令牌提供名称，然后单击"生成 **"。** 保存令牌，因为稍后将需要它。

## <a name="create-an-automated-flow"></a>创建自动化流

有关详细的分步过程，请参阅此处 [的视频](https://www.microsoft.com/en-us/videoplayer/embed/RWFIRn)。 

此视频还介绍了如何将电源自动化连接到 MCAS。 

## <a name="related-information"></a>相关信息

- [将Power Automate与Microsoft Cloud App Security](/cloud-app-security/flow-integration)

- [Microsoft Power Automate文档](/power-automate)
