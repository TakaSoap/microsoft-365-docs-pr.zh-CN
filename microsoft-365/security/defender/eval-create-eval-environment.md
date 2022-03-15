---
title: 创建Microsoft 365 Defender评估环境，实现更高的网络安全和 XDR
description: 了解 XDR 中将评估Microsoft 365 Defender，并激活试用许可证Microsoft 365 Defender测试实验室或试验环境。 从这里开始你的 XDR 网络安全之旅，并了解如何将测试进行生产。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/19/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: d81d33a01802ebdf8ef0ea67a9ee74fc69b79384
ms.sourcegitcommit: 8423f47fce3905a48db9daefe69c21c841da43a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504735"
---
# <a name="step-1-create-the-microsoft-365-defender-evaluation-environment-for-greater-cyber-security"></a>步骤 1. 创建Microsoft 365 Defender评估环境，实现更高的网络安全

LYou 可以了解此解决方案，Microsoft Defender XDR通过本系列其余部分分发的步骤构建此解决方案：

- [如何创建环境](eval-create-eval-environment.md)
- 设置或了解此 Microsoft XDR 的每个技术
    - [Microsoft Defender for Identity](eval-defender-identity-overview.md)
    - [Microsoft Defender for Office](eval-defender-office-365-overview.md)
    - [Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)
    - [Microsoft Defender for Cloud Apps](eval-defender-mcas-overview.md)
- [如何使用此 XDR 调查和响应](eval-defender-investigate-respond.md)
- [将试用环境推广到生产环境](eval-defender-promote-to-production.md)
- [返回到概述](eval-overview.md)

本系列中的步骤端到端运行，从了解 Microsoft 365 Defender XDR 背后的概念，到将评估环境投入生产。

在评估中，有两种常见方法可以执行下一步。 本系列假定你已经拥有生产Microsoft 365，并且将激活 E5 试用许可证以Microsoft 365 Defender *当前环境中使用许可证*。 就地评估将让你保留任何安全方法，在评估期后购买许可证。

第二个[操作是Microsoft 365 Defender测试](setup-m365deval.md)实验室环境以进行评估。 请注意，在测试期间，可能没有来自业务的真实信号。

## <a name="you-will-need-to-activate-e5-trial-licenses-to-evaluate-microsoft-365-defender"></a>你将需要激活 E5 试用许可证才能评估Microsoft 365 Defender

1. 登录到现有租户Microsoft 365门户。
2. 从 **导航菜单中选择** "购买服务"。
3. 向下滚动到"Office 365"**部分，然后选择**"许可证"Office 365 E5"详细信息"按钮。

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="The Office 365 section has a Details button to click.":::

4. 选择 **"开始免费试用链接** "。

   :::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="单击&quot;开始免费试用&quot; (费用为 35 美元) 。":::

5. 确认你的请求，然后单击立即 **尝试** 按钮。

   :::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="在&quot;签出，确认订单&quot;面板上有一个&quot;立即试用&quot;按钮 (25 个用户试用一Office 365 E5 25) 。":::

## <a name="go-to-the-next-step"></a>转到下一步

[了解如何启用Microsoft 365标识](eval-defender-identity-overview.md)

或返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)