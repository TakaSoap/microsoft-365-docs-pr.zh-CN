---
title: 通过攻击模拟培训获得见解
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以了解 Microsoft 365 安全中心中的攻击模拟培训如何影响员工，并可以从模拟和培训结果中获得见解。
ms.technology: mdo
ms.openlocfilehash: 43319089f604d32bf295392dd223cf65af8bd4be
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288653"
---
# <a name="gain-insights-through-attack-simulation-training"></a>通过攻击模拟培训获得见解

在攻击模拟培训中，Microsoft 根据员工经历的模拟和培训结果为您提供见解。 这些见解将帮助您及时了解员工的威胁准备进度，并推荐下一步，以更好地让员工和环境做好攻击准备。

我们正在不断扩展可用的见解。 行为影响和推荐操作目前可用。 若要开始，请前往 [Microsoft 365 安全中心进行攻击模拟培训](https://security.microsoft.com/attacksimulator?viewid=overview)。

## <a name="behavior-impact-on-compromise-rate"></a>行为对泄露率的影响

在 **攻击** 模拟培训的"概述"选项卡上，你将发现对泄露 **率卡的行为** 影响。 此卡片显示员工如何处理你与预测的泄露率相反的 **模拟**。 通过针对同一组员工运行多个模拟，可以使用这些见解跟踪员工威胁准备情况的进度。

在图中，你可以看到：

- **预测的泄露** 率，反映使用攻击模拟培训的其他 Microsoft 365 租户中使用相同负载类型的模拟的平均泄露率。
- **实际泄露** 率反映为模拟而下降的员工百分比。

此外，还反映了受攻击威胁的实际员工数与预测的泄露率 `<number> less susceptible to phishing` 之间的差异。 此员工数量不太可能在将来受到类似攻击的攻击，同时指示员工的总体行为与预测的泄露 `<percent%> better than predicted rate` 率相比。

> [!div class="mx-imgBorder"]
> ![攻击模拟培训概述上的行为影响卡片](../../media/attack-sim-preview-behavior-impact-card.png)

若要查看更详细的报告，请单击 **"查看模拟和培训报表"。** 此报告提供来自模拟本身的其他上下文的相同信息 (例如，模拟技术和目标用户总数) 。

## <a name="recommended-actions"></a>建议的操作

在 [**"模拟"** 选项卡](https://security.microsoft.com/attacksimulator?viewid=simulations)上，选择模拟将让你了解模拟详细信息，你将在这里找到"建议的操作 **"** 部分。

建议的操作部分详细介绍了 Microsoft 安全分数 [中提供的建议](../mtp/microsoft-secure-score.md)。 这些建议基于模拟中使用的有效负载，并且将帮助您保护员工和环境。 单击每个改进操作将让你了解其详细信息。

> [!div class="mx-imgBorder"]
> ![攻击模拟培训的建议操作部分](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>相关链接

[开始使用攻击模拟培训](attack-simulation-training-get-started.md)

[创建网络钓鱼攻击模拟](attack-simulation-training.md)

[创建用于培训人员的有效负载](attack-simulation-training-payloads.md)
