---
title: 为数据隐私法规部署信息保护Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: admindeeplinkCOMPLIANCE
description: 针对数据隐私Microsoft 365如 GDPR 和加州消费者隐私法案 (CCPA) （包括 Microsoft Teams、SharePoint 和电子邮件）配置信息保护。
ms.openlocfilehash: 92314529cf6ca3ec318b181eb367bab81b9b81a0
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60786670"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>为数据隐私法规部署信息保护Microsoft 365

你的组织可能受区域数据隐私法规的约束，这些法规要求你保护、管理和控制存储在 IT 基础结构（包括本地和云）中的个人信息。 数据隐私条例的最佳示例是欧盟一般数据保护条例 (GDPR) 。 如果不遵守数据隐私法规，可能会导致大量罚款。

Microsoft 365 中数据类型的示例包括 Microsoft Teams 中的聊天会话、Exchange 中的电子邮件以及 SharePoint 和 OneDrive。 此解决方案提供了有关如何评估风险并采取适当的措施来保护数据中个人数据Microsoft 365。 这包括标识个人信息，以便你可以保护、治理和响应数据隐私事件。

![什么是数据隐私法规的信息保护。](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png#lightbox)

此外，还提供了有关数据隐私Microsoft 365、设备和威胁防护控件的使用的其他信息。

观看此视频以简要了解部署流程。
<br>
<br>
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4NHCQ]

这些Microsoft 365功能可帮助您满足保护信息的条件。

| 功能或特性 | 说明 | 许可 |
|:-------|:-----|:-------|
| 合规性管理器 | 管理法规合规性活动，获取当前合规性配置的整体分数，并查找改进建议。 这是工作流中基于工作流的风险评估Microsoft 365 合规中心。 | Microsoft 365 E3 和 E5 |
| Microsoft Defender for Office 365 | 保护你的 Microsoft 365 应用和数据（例如电子邮件、Office 文档和协作工具）免受攻击。 | Microsoft 365 E3 和 E5 |
| 敏感度标签 | 对组织的数据进行分类和保护，而不会妨碍用户的工作效率及其协作能力。 将具有各种保护级别的标签放在电子邮件、文件或网站上。 | Microsoft 365 E3 和 E5 |
| 数据丢失防护 (DLP) | 检测、警告和阻止在内部和外部共享包含个人信息的数据存在风险、无意或不当共享。 | Microsoft 365 E3 和 E5 |
| 数据保留标签和策略 | 实施信息治理控制。 这些可能包括确定保留数据 (例如与符合组织策略或数据) 的客户相关的个人数据。 | Microsoft 365 E3 和 E5 |
| 电子邮件加密 | 通过发送和接收组织内外人员之间的加密电子邮件来保护个人数据。 | Microsoft 365 E3 和 E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>此解决方案中指南的组织

为了帮助你了解Microsoft 365隐私相关法规的可用工具，本指南分为多个部分。

![实施数据隐私法规信息保护的步骤。](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

这些部分分别对应于此解决方案中的一篇单独的文章。

> [!NOTE]
> 如果你已熟悉数据隐私义务，并且正在针对现有计划执行，你可能希望专注于防止、保护、保留和调查指南。

> [!IMPORTANT]
> 遵循本指南并不一定符合任何数据隐私法规，尤其是考虑在功能上下文之外需要执行的步骤数。 你有责任确保合规性，并咨询法律和合规性团队，或者向专门负责合规性的第三方寻求指导和建议。

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>计划：评估数据隐私风险并识别敏感项目

评估组织所受数据隐私法规和风险是开始实施改进（包括配置 Microsoft 365 中的功能）之前要执行的关键第一步。 此工作可能包括总体准备情况评估或特定敏感信息类型的标识，这些类型受组织需要遵守的法规控制。

有关详细信息，请参阅评估 [数据隐私风险并识别敏感项目](information-protection-deploy-assess.md)。

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a>跟踪：运行风险评估并检查合规性分数

合规性管理器（Microsoft 365 合规中心中提供<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank"></a>）内置功能，可跟踪和管理整体改进操作，以及适用于你的多个数据隐私法规的相关改进操作。

您可以使用特定于每个法规的内置评估模板，可在其中跟踪选定每个评估模板的行动项，并查看特定法规控制措施，以及将其与特定行动关联。

有关详细信息，请参阅使用 [合规性管理器管理改进操作](information-protection-deploy-compliance.md)。

## <a name="prevent-protect-personal-data"></a>防止：保护个人数据

Microsoft 365提供可用于帮助遵守数据隐私法规的标识、设备和威胁防护功能。

有关详细信息，请参阅对数据隐私法规使用标识 [、设备和威胁防护](information-protection-deploy-identity-device-threat.md)。

本文简要介绍了数据隐私法规在这些方面通常要求哪些内容，并提供了相关 Microsoft 365 解决方案列表，并提供了可帮助您满足任何实现要求的更多信息的链接。

## <a name="protect-information-subject-to-data-privacy-regulation"></a>保护受数据隐私条例保护的信息

数据隐私法规规定可在你的环境中使用大量个人信息保护控制措施，包括 GDPR 示例集、加州消费者保护法案 (CCPA) 、HIPAA-HITECH (美国医疗保健隐私法案) 和巴西数据保护法案 (LGPD) 中用于保护信息的 40 多个控制措施。

有关详细信息，请参阅 [保护受组织中数据隐私法规的约束的信息](information-protection-deploy-protect-information.md)。

本文规定了可用于满足组织中数据隐私的信息保护需求的主要控制方案。

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>保留：管理受数据隐私法规约束的信息

数据隐私法规要求在你的环境中可以使用的个人信息治理控制，包括 GDPR、CCPA、HIPAA-HITECH 和 LGPD 示例集内四种数据隐私法规中的 24 多个控制措施。

有关详细信息，请参阅 [在组织中受数据隐私法规约束的治理信息](information-protection-deploy-govern.md)。

虽然数据隐私法规对于信息治理（如有目的的保留、删除和存档）而言是模糊的，但本文规定了主要控制方案，您可以使用这些方案满足组织对数据隐私的信息管理 &mdash; &mdash; 需求。

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a>调查：监视、调查和响应数据隐私事件

在Microsoft 365相关功能时，可以使用一些功能来帮助你监视、调查和响应组织的数据隐私事件。

拥有使用这些功能的过程、过程和其他文档对于证明监管机构的合规性非常重要。

有关详细信息，请参阅 [监视和响应组织中数据隐私事件](information-protection-deploy-monitor-respond.md)。

## <a name="training-for-administrators"></a>管理员培训

Microsoft Learn 中的这些培训模块可帮助你了解对信息保护非常重要的功能。


#### <a name="information-protection"></a>信息保护

|培训：|使用 Microsoft 365 保护企业信息|
|:---|:---|
|![Teams信息保护培训图标。](../media/protect-enterprise-information-microsoft-365.svg)|保护和保证组织的信息安全以往任何时候都更具挑战性。 使用 Microsoft 365 保护企业信息学习路径介绍如何防止敏感信息被意外过度分享或滥用，如何发现和分类数据，如何使用敏感度标签保护数据，以及如何同时监视和分析敏感信息以防信息丢失。 此学习路径可帮助你准备Microsoft 365：安全管理员关联Microsoft 365认证：Enterprise专家认证。<br><br>1 小时 - Learning 路径 - 5 个模块|

> [!div class="nextstepaction"]
> [开始>](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="identity-and-access"></a>身份和访问

|培训：|使用 Azure Active Directory 提供标识和访问保护|
|:---|:---|
|![标识和访问培训图标。](../media/protect-identity-and-access-with-microsoft-365.svg)|标识和访问学习路径涵盖了最新的身份和访问技术、用于加强身份验证的工具以及组织内有关身份保护的指南。 Microsoft 访问和身份技术使你能够保护组织的身份（无论是本地身份还是在云中），并使用户能够从任何位置安全地工作。 此学习途径可帮助你准备 Microsoft 365 认证：安全管理员关联与Microsoft 365 认证：企业管理专家认证。<br><br>2 小时 52 分钟 - Learning 路径 - 6 个模块|

> [!div class="nextstepaction"]
> [开始>](/learn/modules/m365-identity-overview/introduction/)