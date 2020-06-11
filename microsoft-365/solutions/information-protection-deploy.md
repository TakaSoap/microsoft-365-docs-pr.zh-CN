---
title: 为 Microsoft 365 中的数据隐私法规部署信息保护
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: 配置安全和服务基础结构，以保护您的信息并遵守数据隐私法规。
ms.openlocfilehash: 35ccfb21accd969c2a2cbdddde9a4ec1c7eeed64
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695100"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>为 Microsoft 365 中的数据隐私法规部署信息保护

此解决方案提供了有关如何在 Microsoft 365 服务中规划和保护存储在 Microsoft 服务中的个人数据的指南，并可能会遵守数据隐私法规（如欧盟的常规数据保护法规（GDPR））。 此解决方案重点介绍了适用的 Microsoft 信息保护和合规性功能、Microsoft 合规性分数和评估工具，可帮助您了解数据。 
 
此外，还提供了有关您的数据隐私需求的 Microsoft 标识、设备和威胁防护控制以及数据事件发现和响应工具的其他信息。 

## <a name="organization-of-this-guidance-material"></a>本指南资料的组织结构

为了帮助您了解可用于识别、管理、控制和监视个人数据受一种或多种与隐私相关的法规约束的 Microsoft 365 工具，本指南分为几节。
 
![为数据隐私法规部署信息保护](../media/information-protection-deploy/information-protection-deploy-grid.png)

这两个部分分别对应于本解决方案中的一篇文章。

>[!Note]
>如果您已熟悉您的数据隐私义务并正针对现有计划执行，您可能希望将重点放在阻止、保护、保留和调查指南中。

>[!Important]
>遵循本指南并不一定会使您符合任何数据隐私法规，尤其要考虑功能上下文之外所需的步骤数。 您有责任确保您的合规性并咨询您的法律和合规性团队，或者从第三方（具体符合合规性）中寻求指导和建议。
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>Plan：评估数据隐私风险并确定敏感项目 

评估您的组织所依赖的数据隐私法规和风险是开始实施改进（包括通过 Microsoft 365 配置实现的）之前需要执行的重要第一步。 这可能包括您的组织需要遵守的管理法规控制和在 Microsoft 365 环境中出现的特定敏感信息类型的总体准备情况评估或标识。

有关详细信息，请参阅[评估数据隐私风险和标识敏感项目](information-protection-deploy-assess.md)。

## <a name="track-use-compliance-score-and-compliance-manager"></a>跟踪：使用合规性分数和合规性管理器 

合规性分数和合规性管理器提供了 Microsoft 365 合规性管理中心和服务信任门户中提供的一组集成工具。 此外，这些工具还提供了内置的功能，可以跟踪和管理整体以及与您所受到的多个数据隐私保护法规相关的整体改进措施。

这些工具还允许您利用特定于每个法规的内置评估模板，您可以在其中跟踪选定的每个评估模板的操作项，并查看特定的规章控件，并将它们与特定操作相关联。

有关详细信息，请参阅[使用合规性分数和合规性管理器管理改进操作](information-protection-deploy-compliance.md)。

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>阻止：对数据隐私法规使用标识、设备和威胁防护

Microsoft 365 提供了大量标识、设备和威胁防护功能，可用于帮助遵守数据隐私法规遵从性。 

有关详细信息，请参阅[对数据隐私法规使用标识、设备和威胁防护](information-protection-deploy-identity-device-threat.md)。

本文简要介绍了在这些领域中通常要调用的数据隐私法规，并提供了相关 Microsoft 365 解决方案的列表，并提供了可帮助您满足任何实现要求的详细信息的链接。 

## <a name="protect-information-subject-to-data-privacy-regulation"></a>保护受数据隐私法规制约的信息

数据隐私规章规定了许多可在您的环境中使用的个人信息保护控件，其中包括40个在 GDPR、加利福尼亚州消费者保护法（CCPA）、HIPAA-高科技（美国卫生保健隐私保护法案）和巴西数据保护法案（LGPD）中的四个数据隐私规章中保护信息控制。

有关详细信息，请参阅[保护受组织中数据隐私法规制约的信息](information-protection-deploy-protect-information.md)。

本文介绍了可用于为组织中的数据隐私提供寻址信息保护需求的主要控件方案。

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>保留：管理受数据隐私法规约束的信息

数据隐私管理法规要求在您的环境中可采用的个人信息治理控制措施，包括 GDPR、CCPA、HIPAA-高科技和 LGPD 的示例集中四个数据隐私法规的四个以上的控制措施。

有关详细信息，请参阅[管理组织中的数据隐私法规所依据的信息](information-protection-deploy-govern.md)。

尽管在故意保留、删除和存档等信息管理方面，数据保密法规可能不 &mdash; 明确，但 &mdash; 本文还介绍了主要控件方案，您可以对组织中的数据隐私使用地址信息治理需求。

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a>调查：监视和响应数据隐私法规的主题

有 Microsoft 365 功能可帮助您在您的组织中监视、调查数据隐私事件并在 operationalize 相关功能时对其做出响应。 

对于每个以上的过程、过程和其他文档来说，向管理法规遵守合规性可能非常重要。

有关详细信息，请参阅[监视和响应组织中的数据隐私事件](information-protection-deploy-monitor-respond.md)。
