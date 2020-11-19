---
title: 通过攻击模拟培训获得见解
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: 了解 Microsoft 365 安全中心中的攻击模拟培训如何影响员工以及如何从模拟和培训结果中获得见解。
ms.openlocfilehash: 6a8ee15f14475a1cebb169ab49bdb0f490c81345
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357347"
---
# <a name="gain-insights-through-attack-simulation-training"></a>通过攻击模拟培训获得见解

在攻击模拟培训中，Microsoft 将根据模拟和员工培训的成果为您提供见解。 这些见解将帮助您了解员工在威胁准备方面的进展情况，并建议后续步骤，以便更好地为你的员工和环境提供攻击的准备。

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

我们不断努力为你提供扩大见解，并提供当前可用的行为影响和建议操作。
若要开始，请转到 [Microsoft 365 安全中心上的 "攻击模拟培训](https://security.microsoft.com/attacksimulator?viewid=overview)"。

## <a name="behavior-impact-on-compromise-rate"></a>对泄露率的行为影响

在 "攻击模拟培训 **概述** " 选项卡上，你将发现对 **安全降低率卡的行为影响** 。 此卡片显示了员工如何处理与 **预测的折衷率** 不同的模拟。 通过对相同的员工组运行多次模拟，可以使用这些见解跟踪员工的威胁就绪情况。

在图中，可以看到：

- **预测的威胁率** ，它反映了使用攻击模拟培训的租户上使用相同类型有效负载进行模拟的平均危害率。
- **实际泄露率** 反映了模拟的员工所占的百分比。

此外，还反映了受 `<number> less susceptible to phishing` 攻击影响的实际员工数与预测的威胁率之间的差异。 这一数量的员工将来会受到类似攻击的可能性降低，同时 `<percent%> better than predicted rate` 指出了员工如何与预测的安全评级进行总体对比。

> [!div class="mx-imgBorder"]
> ![攻击模拟培训中的行为影响卡片概述](../../media/attack-sim-preview-behavior-impact-card.png)

若要查看更详细的报告，请单击 **查看模拟和培训 efficacy 报告** ，该报告提供的信息与模拟本身的其他上下文相同，如模拟技术和目标用户总数。

## <a name="recommended-actions"></a>建议的操作

在 " [**模拟** " 选项卡](https://security.microsoft.com/attacksimulator?viewid=simulations)上，选择任意模拟将转到模拟详细信息。 在这里，你将看到 " **建议的操作** " 部分。

"建议的操作" 部分详细介绍了 [Microsoft 安全分数](../mtp/microsoft-secure-score.md)中提供的建议。 这些建议基于模拟中使用的有效负载，并将帮助您保护员工和环境。 单击每个改进操作将转到其详细信息。

> [!div class="mx-imgBorder"]
> ![攻击模拟培训的 "建议操作" 部分](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>相关链接

**攻击模拟器**[创建网络钓鱼攻击模拟](attack-simulation-training.md)和 [创建有效负载，以培训您的人员](attack-simulation-training-payloads.md)
