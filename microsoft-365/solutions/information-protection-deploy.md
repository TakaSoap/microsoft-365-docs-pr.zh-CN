---
title: 为 Microsoft 365 中的数据隐私法规部署信息保护
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: ''
description: 配置安全和服务基础结构，以保护您的信息并遵守数据隐私法规。
ms.openlocfilehash: 9af0a113d9b0eb2cbca07fdf457cd8bb7db3e094
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842292"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>为 Microsoft 365 中的数据隐私法规部署信息保护

您的组织可能受区域数据隐私法规的约束，这些法规要求您保护、管理和提供对存储在 IT 基础结构中的个人信息（包括内部部署和云中的个人信息）的权限和控制。 数据隐私法规的最佳示例是欧盟的一般数据保护法规 (GDPR) 。 如果不遵守数据隐私法规，可能会导致巨额罚款。

Microsoft 365 中的数据类型示例包括 Microsoft 团队中的聊天会话、Exchange 中的电子邮件以及 SharePoint 和 OneDrive 中的文件。 此解决方案提供了有关如何评估风险和标识信息、保护、管理和响应 Microsoft 365 服务中存储的适用于数据隐私法规的个人数据的数据隐私事件的指南。

![什么是针对数据隐私法规的信息保护](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png)

此外，还提供了针对你的数据隐私需求使用 Microsoft 365 标识、设备和威胁防护控制的其他信息。 

若要符合保护信息以实现与数据隐私法规遵从性的标准，请使用以下 Microsoft 365 功能和功能。

| 功能或特性 | 说明 | 许可 |
|:-------|:-----|:-------|
| 合规性管理器 | 管理法规遵从性活动，获取当前合规性配置的整体分数，并在 Microsoft 365 合规性中心中查找基于工作流的风险评估工具改进的建议。 | Microsoft 365 E3 和 E5 |
| Microsoft Defender for Office 365 | 保护你的 Microsoft 365 应用和数据（例如电子邮件、Office 文档和协作工具）免受攻击。 | Microsoft 365 E3 和 E5 | 
| 敏感度标签 | 通过在电子邮件、文件或站点上放置具有不同保护级别的标签，可以在不影响用户工作效率和协作能力的情况下对组织的数据进行分类和保护。 | Microsoft 365 E3 和 E5 |
| 数据丢失防护 (DLP) | 在内部和外部检测、警告和阻止有风险的、无意或不适当的共享，例如包含个人信息的数据共享。 | Microsoft 365 E3 和 E5 | 
| 数据保留标签和策略 | 实施信息治理控制，例如将数据保留多长时间以及对客户个人数据存储的要求，以符合组织的政策或数据法规。 | Microsoft 365 E3 和 E5 |
| 电子邮件加密 | 在组织内部和外部的人员之间发送和接收加密的电子邮件，其中包含受监管的数据，例如客户的个人数据。 | Microsoft 365 E3 和 E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>本解决方案中指南的组织结构

为了帮助您了解可用于识别、管理、控制和监视个人数据受一种或多种与隐私相关的法规约束的 Microsoft 365 工具，本指南分为几节。
 
![对数据隐私法规实施信息保护的步骤](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

这两个部分分别对应于本解决方案中的一篇文章。

>[!Note]
>如果您已熟悉您的数据隐私义务并正针对现有计划执行，您可能希望将重点放在阻止、保护、保留和调查指南中。

>[!Important]
>遵循本指南并不一定会使您符合任何数据隐私法规，尤其要考虑功能上下文之外所需的步骤数。 您有责任确保您的合规性并咨询您的法律和合规性团队，或者从第三方（具体符合合规性）中寻求指导和建议。
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>Plan：评估数据隐私风险并确定敏感项目

评估您的组织所依赖的数据隐私法规和风险是开始实施改进（包括通过 Microsoft 365 配置实现的）之前需要执行的重要第一步。 这可能包括您的组织需要遵守的管理法规控制和在 Microsoft 365 环境中出现的特定敏感信息类型的总体准备情况评估或标识。

有关详细信息，请参阅 [评估数据隐私风险和标识敏感项目](information-protection-deploy-assess.md)。

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a>跟踪：运行风险评估并检查合规性分数

合规性管理器（可在 Microsoft 365 合规性中心中提供）为您提供了一个内置的功能，用于跟踪和管理整体改进操作以及与适用于您的多个数据隐私法规相关的问题。

利用特定于每个法规的内置评估模板，您可以在其中跟踪选定的每个评估模板的操作项，并查看特定的规章控件，并将它们与特定操作相关联。

有关详细信息，请参阅 [Use 合规性管理器管理改进操作](information-protection-deploy-compliance.md)。

## <a name="prevent-protect-personal-data"></a>阻止：保护个人数据

Microsoft 365 提供了大量标识、设备和威胁防护功能，可用于帮助遵守数据隐私法规遵从性。 

有关详细信息，请参阅 [对数据隐私法规使用标识、设备和威胁防护](information-protection-deploy-identity-device-threat.md)。

本文简要介绍了在这些领域中通常要调用的数据隐私法规，并提供了相关 Microsoft 365 解决方案的列表，并提供了可帮助您满足任何实现要求的详细信息的链接。 

## <a name="protect-information-subject-to-data-privacy-regulation"></a>保护受数据隐私法规制约的信息

数据隐私规章规定了许多可在您的环境中使用的个人信息保护控件，其中包括40个在 GDPR 的示例集（加利福尼亚州消费者防护法案 (CCPA) 、HIPAA-高科技 (美国卫生保健隐私法案) 以及巴西数据保护法案 (LGPD) 中的四个数据隐私规章中保护信息控制。

有关详细信息，请参阅 [保护受组织中数据隐私法规制约的信息](information-protection-deploy-protect-information.md)。

本文介绍了可用于为组织中的数据隐私提供寻址信息保护需求的主要控件方案。

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>保留：管理受数据隐私法规约束的信息

数据隐私管理法规要求在您的环境中可采用的个人信息治理控制措施，包括 GDPR、CCPA、HIPAA-高科技和 LGPD 的示例集中四个数据隐私法规的四个以上的控制措施。

有关详细信息，请参阅 [管理组织中的数据隐私法规所依据的信息](information-protection-deploy-govern.md)。

尽管在故意保留、删除和存档等信息管理方面，数据保密法规可能不 &mdash; 明确，但 &mdash; 本文还介绍了主要控件方案，您可以对组织中的数据隐私使用地址信息治理需求。

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a>调查：监控、调查和响应数据隐私事件

有 Microsoft 365 功能可帮助您在您的组织中监视、调查数据隐私事件并在 operationalize 相关功能时对其做出响应。 

对于每个以上的过程、过程和其他文档来说，向管理法规遵守合规性可能非常重要。

有关详细信息，请参阅 [监视和响应组织中的数据隐私事件](information-protection-deploy-monitor-respond.md)。
