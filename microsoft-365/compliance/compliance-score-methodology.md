---
title: 合规性分数计算
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解 Microsoft 合规性分数如何根据为解决风险而采取的措施计算个性化分数，并提高您的合规性状况。
ms.openlocfilehash: 9fbc2b2beca3a667b09c1a4ba790651a364d1bf0
ms.sourcegitcommit: e872676ec98036a50d3a0cb5071109ea5f5a7ae5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "41515573"
---
# <a name="microsoft-compliance-score-preview-calculation"></a>Microsoft 合规性分数（预览）计算

> [!IMPORTANT]
> 合规性分数不表示对任何特定标准或法规的组织合规性的绝对衡量。 它表示您已采用的控制程度，可降低个人数据和个人隐私的风险。 不应将合规性分数和合规性管理器中的建议解释为合规性保证。 此服务目前处于预览阶段，并受[在线服务条款](https://go.microsoft.com/fwlink/?linkid=2108910)中的条款和条件的制约。

## <a name="overview"></a>概述

合规性分数仪表板显示分数，用于衡量在控件中完成改进操作的进度。 完成操作时，会对点进行累算。

根据 Microsoft 管理的操作和客户管理的操作的完成情况计算分数。 每项操作对你的分数有不同的影响，具体取决于所涉及的潜在风险，因此分数可帮助确定重点关注的操作以改进您的总体合规性状态。

为该控件显示的符合性分数值将*全部*应用于通过通过/失败的总分。 该控件已实现并通过后续评估测试，否则不会执行。 当控件具有以下条件时，为合规性分数添加分配的点：

- **实现状态**等于已**实现**或**替代实施**，以及
- **测试结果**等于已**通过**。

通过采取改进操作达到的分数总和是控制得分。 控制分数的总和是评估分数。 评估分数总和是您的总体合规性分数

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>基于 Microsoft 365 数据保护基准的初始分数
  
合规性分数为您提供了基于 Microsoft 365 数据保护基准的现成分数，这是一组包括用于数据保护和常规数据保护的关键法规和标准的控件。 此基线主要从 NIST CSF （美国国家标准和技术协会 Cybersecurity Framework）和 ISO （国际标准化组织）和 FedRAMP （联邦风险和授权管理）中绘制元素程序）和 GDPR （欧盟的常规数据保护法规）。

## <a name="how-compliance-score-continuously-assesses-controls"></a>合规性分数如何持续评估控制措施

合规性分数将自动通过 Microsoft 365 环境扫描并检测系统设置，并持续并自动更新你的技术控制状态。 合规性分数使用安全分数作为执行监控的基础引擎。 [了解有关安全分数及其工作方式的详细信息](../security/mtp/microsoft-secure-score.md)。

你的合规性分数仪表板每24小时更新一次你的控制状态。 一旦您遵循了实现控件的建议，您将会看到在下一天更新控件状态。

例如，如果在 Azure AD 门户中打开多重身份验证（MFA），合规性分数将检测设置，并在控制访问解决方案详细信息中反映该设置。 相反，如果未启用 MFA，合规性分数标志为建议采取的操作。

在公共预览过程中，连续评估适用于部分控件，但并非全部。
  
## <a name="control-types-and-points"></a>控件类型和点

合规性分数跟踪两种类型的控件： Microsoft 管理的控件和客户管理的控件，其中每个控件都有对整体得分的积分：

1. 根据您的组织管理的控件，**客户管理的积分**将有助于满足您的合规性分数。
2. 根据 Microsoft 作为云服务提供商托管的控件， **Microsoft 管理点**将对您的合规性分数构成贡献。

根据控件是必需的还是任意的，以及是否为预防、侦探或纠正措施（如下所述），会为控件分配一个分数值。

### <a name="mandatory-and-discretionary-controls"></a>强制和任意控件

 - **强制控制**措施是不能有意地或无意中回避的操作。 例如集中管理的密码策略，用于设置密码长度、复杂性和过期的要求。 用户必须遵守这些要求才能访问系统。
  
 - **任意控件**依赖于用户了解策略并相应地执行操作。 例如，要求用户在其离开时锁定其计算机的策略是自由控制，因为它依赖于用户。
  
### <a name="preventative-detective-and-corrective-controls"></a>预防性、侦探和纠正控制措施
  
 - **预防控制措施**解决特定风险。 例如，使用加密保护静态信息是抵御攻击和泄露的预防控制措施。 分离职责是一种预防性控制，用于管理利益冲突并防范欺诈行为。
  
 - **侦探控件**主动监视系统，以找出表示风险或可用于检测入侵情况或确定是否发生了入侵的不规则条件或行为。 系统访问审核和特权管理操作审核是侦探监视控件的类型。 法规遵从性审核是一种用于查找进程问题的侦探控件。
  
- **纠正控制**尝试将安全事件的负面影响降至最低，采取纠正措施以降低即时效果，并在可能的情况下反转损坏。 "隐私事件响应" 是一种纠正控制，用于将损坏和还原系统限制为受到破坏后的操作状态。
  
根据其表示的风险，每个控件都在合规性分数中分配了一个值：

|**类型**|**分配分数**|
|:-----|:-----|
| 预防性强制 | 27 |
| 预防自由 | 9  |
| 侦探必备 | 第三章 |
| 侦探自由 | 1 |
| 强制纠正 | 第三章 |
| 随机纠正 | 1 |
  