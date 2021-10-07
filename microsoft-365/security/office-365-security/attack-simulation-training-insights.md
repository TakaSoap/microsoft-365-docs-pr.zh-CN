---
title: 通过攻击模拟培训获得见解
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以了解企业门户中的攻击Microsoft 365 Defender培训如何影响员工，并可以从模拟和培训结果中获得见解。
ms.technology: mdo
ms.openlocfilehash: 9376ef78ef6349bbd595ec0c48fccd394e0cd869
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154349"
---
# <a name="gain-insights-through-attack-simulation-training"></a>通过攻击模拟培训获得见解

**适用于 Microsoft** [Defender for Office 365计划 2](defender-for-office-365.md)

在攻击模拟培训中，Microsoft 根据员工经过的模拟和培训结果提供见解。 这些见解将有助于你随时了解员工的威胁准备进度，并推荐下一步，让员工和环境更好地做好应对攻击的准备。

我们正在不断扩展可供你获取的见解。 行为影响和推荐操作目前可用。 To start， head to [Attack simulation training in the Microsoft 365 Defender portal](https://security.microsoft.com/attacksimulator?viewid=overview).

## <a name="behavior-impact-on-compromise-rate"></a>行为对泄露率的影响

在攻击 **模拟** 培训的概述选项卡上，你将发现行为对入侵 **率卡** 的影响。 此卡显示员工如何处理你与预测的泄露率相反 **的模拟**。 通过针对同一个员工组运行多个模拟，你可以使用这些见解跟踪员工威胁准备情况的进度。

在图中，你可以看到：

- **预测的泄露率**，反映了使用攻击模拟培训的其他 Microsoft 365 租户中使用相同负载的模拟的平均入侵率。
- **实际泄露** 率反映了为模拟而牺牲的员工百分比。

此外，还反映了受攻击危害的实际员工数与预测的入侵率 `<number> less susceptible to phishing` 之间的差值。 此员工数量不太可能在将来受到类似攻击的攻击，同时指示员工的整体行为与预测的泄露率 `<percent%> better than predicted rate` 的对比。

> [!div class="mx-imgBorder"]
> ![攻击模拟培训概述中的行为影响卡片。](../../media/attack-sim-preview-behavior-impact-card.png)

若要查看更详细的报告，请单击查看 **模拟和培训的报表**。 此报告提供了来自模拟本身的其他上下文的相同信息 (例如，模拟技术和目标用户总数) 。

## <a name="recommended-actions"></a>建议的操作

在 [**"模拟"** 选项卡](https://security.microsoft.com/attacksimulator?viewid=simulations)上，选择模拟将你查看模拟详细信息，你将在这里找到推荐 **操作** 部分。

建议的操作部分详细介绍了 Microsoft 安全分数 [中提供的建议](../defender/microsoft-secure-score.md)。 这些建议基于模拟中使用的有效负载，有助于保护员工和环境。 单击每个改进操作将让你了解其详细信息。

> [!div class="mx-imgBorder"]
> ![攻击模拟培训的建议操作部分。](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>相关链接

[开始使用攻击模拟培训](attack-simulation-training-get-started.md)

[创建网络钓鱼攻击模拟](attack-simulation-training.md)

[创建用于培训人员的有效负载](attack-simulation-training-payloads.md)
