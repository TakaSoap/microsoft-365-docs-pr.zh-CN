---
title: 规划支持终止的软件和硬件版本
description: 发现并规划不再受支持且不会接收安全更新的软件和硬件版本。
keywords: 危险和漏洞管理， 适用于终结点的 Microsoft Defender 电视安全建议， 网络安全建议， 可操作的安全建议
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 65842d0bd56308b6a5e5476f84c089b63a04987b
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168014"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a>使用产品/服务规划支持终止的危险和漏洞管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)。

软件或软件版本的支持终止 (EOS) （也称为生命周期结束 (EOL) ）意味着它们将不再受支持或获得服务，并且不会接收安全更新。 当你使用具有结束支持的软件或软件版本时，你将使组织面临安全漏洞、法律和财务风险。

安全与 IT 管理员必须协同工作，并确保组织的软件清单配置为获得最佳结果、合规性和正常的网络生态系统。 他们应检查删除或替换已到达停止支持的应用的选项，并更新不再受支持的版本。 最好在支持日期结束之前 **创建** 和实施计划。

> [!NOTE]
> 支持终止功能当前仅适用于Windows产品。

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a>查找不再受支持的软件或软件版本

1. 从"危险和漏洞管理"菜单中，导航到"[**安全建议"。**](tvm-security-recommendation.md)
2. 转到筛选器 **面板** 并查找标记部分。 选择一个或多个 EOS 标记选项。 然后 **应用**。

    ![显示 EOS 软件、EOS 版本和即将推出的 EOS 版本的屏幕截图标记。](images/tvm-eos-tag.png)

3. 你将看到与已结束支持的软件、停止提供支持的软件版本或即将停止提供支持的版本相关的建议列表。 这些标记还显示在软件清单 [页面中](tvm-software-inventory.md) 。

    ![推荐 EOS 标记。](images/tvm-eos-tags-column.png)

## <a name="list-of-versions-and-dates"></a>版本和日期列表

若要查看已终止支持或即将结束或支持的版本列表以及这些日期，请按照以下步骤操作：

1. 对于版本已终止支持或即将停止提供支持的软件，将在安全建议飞出中显示一条消息。

    ![版本分发链接的屏幕截图。](images/eos-upcoming-eos.png)

2. 选择 **版本分发** 链接以转到软件深化页面。 其中，你可以看到经过筛选的版本列表，其中标记将它们标识为支持终止或即将停止提供支持。

    ![包含支持软件终止的软件向下钻取页面的屏幕截图。](images/software-drilldown-eos.png)

3. 选择要打开的表中的某个版本。 例如，版本 10.0.18362.1。 将显示一个显示支持日期结束的飞出图。

    ![支持结束日期的屏幕截图。](images/version-eos-date.png)

在确定哪些软件和硬件版本由于停止支持状态而易受攻击后，您必须决定是更新还是从组织中删除它们。 这样做将降低组织对漏洞和高级永久性威胁的暴露程度。

## <a name="related-topics"></a>相关主题

- [威胁和漏洞管理概述](next-gen-threat-and-vuln-mgt.md)
- [安全性建议](tvm-security-recommendation.md)
- [软件库存](tvm-software-inventory.md)
