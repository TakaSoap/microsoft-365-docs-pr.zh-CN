---
title: Microsoft 合规性分数（预览）计算
f1.keywords:
- NOCSH
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 552f2f85c4659ec24bc717d41c71733764d898ed
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023243"
---
# <a name="compliance-score-preview-calculation"></a>合规性分数（预览）计算

> [!IMPORTANT]
> 合规性分数和合规性管理器中提供的建议不应解释为合规性保证。 根据您的法规环境评估和验证客户控制措施的有效性。 这些服务当前处于预览阶段，并遵循[在线服务条款](https://go.microsoft.com/fwlink/?linkid=2108910)中的条款和条件。 另请参阅[适用于安全性和合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

## <a name="how-compliance-score-works"></a>合规性分数的工作原理

合规性分数仪表板显示分数，用于衡量在控件中完成改进操作的进度。 每项操作对你的分数有不同的影响，具体取决于所涉及的潜在风险。 你的分数可帮助优先考虑要关注的操作，以改进你的总体合规性状况。

为该控件显示的符合性分数值将*全部*应用于通过通过/失败的总分。 该控件已实现并传递后续评估测试，否则不会。 

当控件具有以下条件时，将其添加到符合性分数：

- **实现状态**等于已**实现**或**替代实现**，并且
- **测试结果**等于已**通过**。

控制分数是通过采取改进操作获得的分数总和。 控制分数的总和是评估分数。 **评估分数总和是您的总体合规性分数。**

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>基于 Microsoft 365 数据保护基准的初始分数
  
合规性分数为你提供了基于 Microsoft 365 数据保护基准的初始分数。 此基准是一组控件，包括用于数据保护和常规数据管理的关键法规和标准。 此基线主要从 NIST CSF （美国国家标准和技术协会 Cybersecurity Framework）和 ISO （国际标准化组织）以及 FedRAMP （联邦风险和授权管理计划）和 GDPR （欧盟的常规数据保护法规）中提取元素。

数据保护基准评估（默认情况下为所有组织提供）用于在配置任何其他评估之前计算您的初始分数。 首次访问时，合规性分数已从 Microsoft 365 解决方案中收集信号。 你将快速了解你的组织是如何相对于关键数据保护标准和管理法规执行的，并查看建议采取的改进措施。

由于每个组织都有特定的需求，因此合规性分数取决于您设置和管理您自己的评估以帮助尽可能地减少和缓解风险。

## <a name="how-compliance-score-continuously-assesses-controls"></a>合规性分数如何持续评估控制措施

合规性分数将自动通过 Microsoft 365 环境扫描并检测系统设置，并持续并自动更新你的技术控制状态。 安全分数是执行监控的基础引擎。

你的合规性分数仪表板每24小时更新一次你的控制状态。 一旦您遵循了实现控件的建议，您将看到在下一天更新控件状态。

例如，如果在 Azure AD 门户中打开多重身份验证（MFA），合规性分数将检测设置，并在控制访问解决方案详细信息中反映该设置。 相反，如果未启用 MFA，合规性分数标志为建议采取的操作。

在公共预览过程中，连续评估适用于部分控件，但并非全部。

#### <a name="learn-more"></a>了解详细信息
[阅读有关安全分数及其工作方式的信息](../security/mtp/microsoft-secure-score-new.md)。
  
## <a name="action-types-and-points"></a>操作类型和点

合规性分数跟踪两种类型的操作：您管理的操作以及 Microsoft 管理的操作。 完成后，这两种类型的操作都将计入总得分的点：

1. **你的积分**根据你的组织管理的控件来贡献合规性分数。
2. **Microsoft 托管点**根据 Microsoft 作为云服务提供商管理的操作，为你的合规性分数提供贡献。

根据操作是强制还是自由，以及是否为预防、侦探或纠正措施，为操作分配分数值。

### <a name="mandatory-and-discretionary-actions"></a>强制和自由操作

 - 无法绕过**强制操作**，无论是有意的还是意外的。 例如，集中管理的密码策略，设置密码长度、复杂性和过期的要求。 用户必须遵循以下要求才能访问系统。
  
 - **任意操作**取决于用户了解策略并相应地执行操作。 例如，要求用户在其离开时锁定其计算机的策略是自由控制，因为它依赖于用户。
  
### <a name="preventative-detective-and-corrective-actions"></a>预防性、侦探和纠正措施
  
 - **预防措施**解决特定风险。 例如，使用加密保护静态信息是预防攻击和泄露的预防措施。 分离职责是一种预防措施，用于管理利益冲突并防范欺诈行为。
  
 - **侦探操作**主动监视系统，以确定存在不稳定的条件或行为，以确定风险或可用于检测入侵或泄露的行为。 示例包括系统访问审核和特权管理操作。 法规遵从性审核是用于查找过程问题的侦探操作的一种。
  
- **纠正操作**尝试将安全事件的负面影响降至最低，采取纠正措施以降低即时效果，并在可能的情况下反转损坏。 隐私事件响应是一种纠正措施，用于将损坏和还原系统限制为受到破坏后的操作状态。
  
每个操作在符合性分数中分配的值基于它表示的风险：

|**类型**|**分配分数**|
|:-----|:-----|
| 预防性强制 | 27 |
| 预防自由 | 9  |
| 侦探必备 | 3  |
| 侦探自由 | 1  |
| 强制纠正 | 3  |
| 随机纠正 | 1  |
  
![合规性分数控制点值](../media/compliance-score-controls-scoring.png "合规性分数控制点值")