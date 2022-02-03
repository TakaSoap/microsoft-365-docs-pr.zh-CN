---
title: 使用数据隐私风险评估数据隐私风险并识别Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 07/13/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: 确定数据隐私法规、相关方案、准备情况以及用户环境中Microsoft 365类型。
ms.openlocfilehash: 5f8b5844ad3db4152a6144f9506a0267fa3af8f2
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "62320747"
---
# <a name="assess-data-privacy-risks-and-identify-sensitive-items-with-microsoft-365"></a>使用数据隐私风险评估数据隐私风险并识别Microsoft 365

在实施任何相关改进操作（包括使用 Microsoft 365 实现的操作）之前，首先评估组织需要遵守的数据隐私法规和风险。

## <a name="potentially-applicable-data-privacy-regulations"></a>可能适用的数据隐私法规

有关更广泛的数据隐私法规框架的良好参考，请参阅 [Microsoft 服务](https://servicetrust.microsoft.com/) 信任门户和一般数据保护条例 [ (GDPR) 法规](/compliance/regulatory/gdpr)的一系列文章。 此外，查看有关你所属行业或地区可能受法规限制的法规材料。

### <a name="gdpr"></a>GDPR

GDPR 是数据隐私法规最已知和被引用的法规。 它规定收集、存储、处理和共享与欧盟/欧盟居民的已确定身份或可识别的自然人 (个人数据) 。

根据 GDPR 第 4 条：

- "个人数据"是指与已识别或可识别的自然人 ("数据主体"相关的) ;可识别的自然人是可直接或间接识别的自然人，尤其是通过引用姓名、标识号、位置数据、在线标识等标识符，或特定于该自然人的性、基因、精神、经济、文化或社会标识的一个或多个因素进行识别。

### <a name="iso-27001"></a>ISO 27001

遵守 ISO 27001 等其他标准也已被多个欧洲监管机构视为整个人员、流程和技术范围的有效意图代理。 在某些情况下，它指定的重叠和遵守 ISO-27001 驱动保护机制的标准可能会被视为履行某些隐私义务的代理。

### <a name="other-data-privacy-regulations"></a>其他数据隐私法规

其他重要的数据隐私法规还指定了个人数据处理要求。

在美国，其中包括加州消费者保护法案 ([CCPA](/compliance/regulatory/ccpa-faq)) 、HIPAA-HITECH (美国医疗保健隐私法案) 和 GlBA (《格雷姆雷法案) 。 其他特定于州的规定也就地或正在开发中。

世界各地的其他示例包括德国的国家 GDPR 实施法案 (BDSG) 、巴西数据保护法案 (LGPD) 等。

## <a name="regulation-mapping-to-microsoft-365-technical-control-categories"></a>法规与技术Microsoft 365类别的映射

许多与数据隐私相关的法规具有重叠要求，因此在开发任何技术控制方案之前，您应了解它们所遵守的法规。

为了稍后在此总体解决方案文章中进行参考，此表提供了数据隐私法规采样摘录。

|法规|文章/部分|摘录|适用的技术控制类别|
|---|---|---|---|
|GDPR|第 5 (1)  (f) |个人数据的处理方式应该确保个人数据的适当安全性，包括防止未经授权的或非法处理，以及防止意外丢失、销毁或损坏，使用适当的技术或组织措施 (完整性和保密性"。| (所有)  <br> 标识 <br> 设备 <br> 威胁防护 <br> 保护信息 <br> 管理信息 <br> 发现和响应|
||文章 (32)  (1)  (a) |考虑到技术状态、实现成本以及处理的性质、范围、上下文和目的，以及自然人的权利和自由出现不同可能性和严重性的风险，控制者和处理者应实施适当的技术和组织措施，以确保安全级别适合风险， 包括相应的 inter- (：) 个人数据的假名化和加密。|保护信息|
||文章 (13)  (2)  (a) |"...控制者应在获取个人数据时向数据主体提供确保公平、透明的处理所需的以下详细信息： () 将存储个人数据的时间段，或者如果不可能，则提供用于确定该时间段的条件。|管理信息|
||文章 (15)  (1)  (e) |数据主体有权从控制者确认是否正在处理有关其个人数据以及是否正在处理个人数据以及访问个人数据和以下信息的权利： (e) 是否存在从控制者纠正或清除个人数据或限制处理与数据主体或对象相关的个人数据的权利到此类处理|发现和响应|
|LGPD|文章 46|处理代理应采取安全、技术和管理措施，以保护个人数据免受未经授权的访问以及意外或非法的销毁、丢失、更改、通信或任何类型的不正确或非法处理的情况。|保护信息 <br> 管理信息 <br> 发现和响应|
||文章 48|控制者必须告知国家/机构以及数据主体，发生可能会给数据主体带来风险或相关损害的安全事件。|发现和响应|
|HIPPA-HITECH|45 CFR 164.312 (e)  (1) |实施技术安全措施，以防止对通过电子通信网络传输的电子受保护健康信息进行未经授权的访问。|保护信息|
||45 C.F.R. 164.312 (e)  (2)  (ii) |实施一种机制，在认为合适时对电子保护的运行状况信息进行加密。|保护信息|
||45 CFR 164.312 (c)  (2) |实施电子机制，以证实电子保护的运行状况信息未被未经授权更改或销毁。|管理信息|
||45 CFR 164.316 (b)  (1)  (i) |如果此子部分要求记录行动、活动或评估，请保留书面 (该记录可能是) 、活动或评估的电子记录|管理信息|
||45 CFR 164.316 (b)  (1)  (ii) |将本节第 (b)  (1) 段所需的文档自创建日期或最后生效日期起保留 6 年，以较高者为准。|管理信息|
||45 C.F.R. 164.308 (a)  (1)  (ii)  (D) |实施定期查看信息系统活动记录的过程，如审核日志、访问报告和安全事件跟踪报告|发现和响应|
||45 C.F.R. 164.308 (a)  (6)  (ii) |识别并响应可疑或已知的安全事件;在可允许的范围内缓解覆盖的实体或业务关联已知的安全事件的负面影响;并记录安全事件及其结果。|发现和响应|
||45 C.F.R. 164.312 (b) |实施硬件、软件和过程机制，以记录和检查包含或使用电子受保护运行状况信息的信息系统中的活动。|发现和响应|
|CCPA|1798.105 (c) |如果企业收到来自消费者的可验证请求，以删除被细分为 () 的消费者个人信息，则此节的) 应从其记录中删除消费者的个人信息，并指示任何服务提供商从记录中删除消费者的个人信息|发现和响应|
||1798.105 (d) | (1798.105 (c)  <br> 如果企业或服务提供商需要维护消费者的个人信息，则不应要求企业或服务提供商遵守消费者删除消费者个人信息的请求，以便： (参考当前法规获取其他信息) 。|发现和响应|
|||||

> [!IMPORTANT]
> 这不是一个详尽的列表。 有关 [所](../compliance/compliance-manager.md) 引用部分对所列技术控制类别的适用性，请参阅合规性管理器或法律或合规性顾问。

## <a name="knowing-your-data"></a>了解数据

不论您遵守哪些法规，组织内外的不同用户数据类型与系统交互都是影响整体个人数据保护策略的重要因素，但需遵守适用于组织的行业和政府法规。 这包括存储个人数据的位置、存储类型、存储量以及收集的情况。

![了解你的数据：它是哪种类型、它有多少以及收集什么情况。](../media/information-protection-deploy-assess/information-protection-deploy-assess-knowing-data.png)

### <a name="data-portability"></a>数据可移植性

随着数据的处理、优化和其他版本的派生，数据也会随着时间的推移而移动。 初始快照永远不够用。 需要有一个持续的过程来了解你的数据。 对于处理大量个人数据的大型组织来说，这是最大的挑战之一。 不解决"知道数据"问题的组织最终可能会面临非常高的风险，并可能获得监管机构的罚款。

![数据生命周期。](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-lifecycle.png)

### <a name="where-the-personal-data-is"></a>个人数据位于何处

要解决数据隐私法规，不能依赖于你认为个人数据可能存在于何处的一般概念，无论是现在还是将来。 数据隐私法规要求组织证明他们持续知道个人数据位于何处。 因此，必须获取所有数据源的初始快照，以可能存储个人信息（包括 Microsoft 365 环境）并建立持续监视和检测机制。

如果尚未评估与数据隐私法规相关的总体准备和风险，请使用以下 3 步框架开始。

![评估与数据隐私法规相关的总体准备和风险的步骤。](../media/information-protection-deploy-assess/information-protection-deploy-assess-grid.png)

> [!NOTE]
> 本文及其内容并不代表法律咨询服务。 它只是提供一些基本指南和指向可能在评估的早期阶段提供帮助的工具的链接。

## <a name="step-1-develop-a-foundational-understanding-of-your-organizations-personal-data-scenarios"></a>步骤 1：从基础上了解组织的个人数据方案

您需要根据数据隐私风险当前管理的类型、存储位置、对数据实施哪些保护性控制、如何管理数据的生命周期以及谁有权访问数据隐私风险来衡量数据隐私风险。

首先，清点环境中存在的个人数据类型Microsoft 365很重要。 使用以下类别：

- 执行日常业务功能所需的员工数据
- 组织具有的业务客户、合作伙伴和业务到企业或 B2B (的其他关系) 数据
- 组织具有的有关 (消费者的数据，这些客户向组织在企业到客户或 B2C) 方案中管理的在线服务提供相关信息

下面是组织典型部门不同类型的数据的示例。

![个人数据的类型。](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-types.png)

大部分受数据隐私条例保护的个人数据通常收集并存储在数据Microsoft 365。 来自面向消费者的 Web 或移动应用程序的任何个人数据都需要从此类应用程序导出到 Microsoft 365，以便受到 Microsoft 365 内的数据隐私审查。

与 Web 应用程序和 CRM 系统相比，Microsoft 365中数据隐私的曝光可能更加有限，此解决方案无法解决这些风险。

在评估风险配置文件时，还必须考虑以下常见的数据隐私合规性挑战：

- **个人数据分布。** 给定主题的信息如何分散？ 是否已知足以让监管机构认为适当的控制措施已到位？ 如果需要，可以进行调查和修正吗？
- **防止外排。** 如何保护给定类型或源的个人数据免遭泄露，以及如何响应？
- **保护与风险。** 哪些信息保护机制与风险相关，如何保持业务连续性和生产力，并最大限度地减少最终用户影响（如果需要最终用户干预） 例如，应该使用手动分类还是加密？
- **个人数据保留。** 出于有效的业务原因，包含个人数据的信息需要保留多久，如何避免过去一直保留的做法，同时满足业务连续性的保留需求？
- **处理数据主体请求。** 需要哪些机制来处理 DSR (数据主体) 任何修正操作（如匿名、修订和删除）？
- **持续监视和报告。** 哪些类型的日常监视、调查和报告技术可用于不同的数据类型和源？
- **数据处理的限制。** 对于通过这些方法收集或存储的信息，组织必须在隐私控制中反映到的数据使用是否有限制？ 例如，销售人员不会使用个人数据的承诺可能要求贵组织建立机制，以防止在与销售组织关联的系统中传输或存储该信息。

### <a name="employee-data-required-to-carry-out-day-to-day-business-functions"></a>执行日常业务功能所需的员工数据

组织本质上需要收集有关员工的数据以用于电子标识和 HR 目的，但需遵守其员工协议中同意的信息。 只要某人为公司工作，这通常就不是问题。 组织可能希望建立机制以防止恶意参与者泄露或泄露员工个人数据。

如果某人离开公司，组织通常会制定流程、过程以及保留和删除计划，用于删除用户帐户、停用邮箱和个人驱动器，以及更改人力资源系统等中的员工状态。 对于涉及诉讼的情况，法律调查的员工或其他方可能出于有效理由来获取有关存储在组织系统中个人数据的信息。 在某些情况下，该方可能请求删除或匿名处理此类数据。

为了满足此类需求，组织应制定相应的流程和过程，以满足预防性、检测性和修正性需求，以促进此类请求，并请注意，有关员工的一些信息可能合理视为对业务连续性至关重要。 例如，个人创作文件或执行函数的信息。

> [!NOTE]
> 有关调查并修正数据中个人数据Microsoft 365，请参阅[监视器和回复文章](information-protection-deploy-monitor-respond.md)。 你可能还需要使用自动分类和保护方案，以确保个人数据在组织内部受到控制，以及防止它在恶意参与者情况下离开组织。 有关详细信息 [，请参阅保护](information-protection-deploy-protect-information.md) 信息文章。

### <a name="data-the-organization-has-about-its-business-customers-in-the-b2b-scenario"></a>组织在 B2B 方案中拥有的业务客户数据

收集 B2B 信息也是一项挑战，因为您的组织可能需要在其各种系统中保留客户名称和交易的记录，以便业务连续性，同时防止该信息意外或恶意泄漏。 与员工数据一样，组织必须制定相关策略、过程和技术控制来保护此类数据，以及根据定义的保留和删除计划对这些数据进行期限设置。

通常，与外部客户、合作伙伴和组织有业务往来的其他实体之间的合同将具有处理此类数据的语言，包括实体与组织建立关系期间和之后的保护、保留和删除。

### <a name="data-the-organization-has-about-consumers-who-provide-information-to-online-services-that-the-organization-manages-in-the-b2c-scenario"></a>组织具有的有关向组织在 B2C 方案中管理的在线服务提供信息的消费者的数据

由于客户数据泄露的许多公共实例，此类别是人们最想了解的数据隐私。 这可能是有意为之（如与提供商签订合同的第三方）或无意间，如恶意参与者泄露。 消费者数据保护是欧盟和其他国家遵守这些法规的主要原因之一。 GDPR 和 CCPA 等数据隐私法规要求你进行规划：

- [行动计划](/compliance/regulatory/gdpr-action-plan)[和责任就绪清单](/compliance/regulatory/gdpr-arc-Office365)
- [数据保护影响评估](/compliance/regulatory/gdpr-data-protection-impact-assessments)
- [泄露通知](/compliance/regulatory/gdpr-breach-Office365)
- [数据主体请求](/compliance/regulatory/gdpr-dsr-Office365)

如果组织不执行大量直接来自消费者的数据收集，则此类别可能没有问题。 但是，你可能需要完成这些文章中概述的过程以实现合规性。

### <a name="step-1-summary"></a>步骤 1 摘要

了解风险及数据隐私法规是一个重要的第一步，基于对组织个人数据方案的基础了解。

如果在 Microsoft 365 环境中没有来自消费者的个人数据，或者它仅限于环境的某些部分，并且技术控制的需求基于存在消费者类型的数据泄露，则技术控制可能只需要在环境的高风险部分使用，而不是在任何地方使用。

虽然外部组织或标准控制集建议（如来自 Microsoft 365 中的合规性管理器）可能会帮助告知你的控制策略，但选择实施应受数据清单感知的驱动，以量化实际的风险暴露。

大多数组织都会接触上述方案之一。 采取全面的评估方法非常重要。

## <a name="step-2-assess-your-readiness-for-complying-with-data-privacy-regulations"></a>步骤 2：评估你遵守数据隐私法规的准备情况

尽管特定于 GDPR，免费 [Microsoft GDPR](https://clouddamcdnprodep.azureedge.net/gdc/1863571/original) 评估工具中的问题为了解整体数据隐私准备情况提供了良好的开端。

受其他数据隐私法规（如美国 CCPA 或巴西 LGPD）保护的组织也可从此工具的就绪清单（由于与 GDPR 重叠的规定）中获益。

GDPR 评估包含以下部分：

|节|说明|
|:-------|:-----|
|管控|<ol><li>隐私策略是否明确声明正在处理哪些数据信息？ </li><li>您是否定期运行 PIA (隐私) ？ </li><li> 您是否使用工具来管理 PI (的个人信息) ？ </li><li> 你是否具有对任意给定个人使用 PI 数据开展业务的法律授权？ 你是否跟踪数据许可？ </li><li> 你是否跟踪、实施和管理审核控制？ 是否监视数据泄露？ </li></ol>|
|删除和通知|<ol><li>是否提供有关如何访问用户数据的明确说明？ </li><li> 是否具有处理选择退出同意的已记录流程？ </li><li> 您是否具有数据自动删除过程？ </li><li> 在与客户互动时，你是否具有验证身份的流程？ </li></ol>|
|风险缓解和信息安全|<ol><li>你是否使用工具扫描非结构化数据？ </li><li>所有服务器是否都是最新的，您是否利用防火墙来保护它们？ </li><li>是否运行服务器的定期备份？ </li><li>是否主动监视数据泄露？ </li><li>是否对处于其余和传输中的数据进行加密？ </li></ol>|
|策略管理|<ol><li>如何管理 BINDING Corporate Rules (BCR) ？ </li><li>你是否跟踪数据许可？ </li><li> 在 1 到 5（完全涵盖）范围中，您的合同是否涵盖数据分类和处理要求？ </li><li>是否拥有并定期测试事件响应计划？ </li><li>使用什么策略管理访问？ </li></ol>|
|||

## <a name="step-3-identify-sensitive-information-types-that-occur-in-your-microsoft-365-environment"></a>步骤 3：确定在安全环境中发生的Microsoft 365类型

此步骤涉及标识受特定法规控制的特定敏感信息类型，以及在你的环境中Microsoft 365类型。

在包含个人的环境中查找内容可能是一项非常强大的任务，以前涉及结合使用合规性搜索、电子数据展示、Advanced eDiscovery、DLP 和审核。

借助 Microsoft 合规性管理中心中的新数据分类解决方案，使用内容资源管理器功能变得更加简单，该功能适用于[](../compliance/data-classification-content-explorer.md)内置或自定义敏感信息类型，包括与个人数据相关的类型。

### <a name="sensitive-information-types"></a>敏感信息类型

Microsoft 合规性管理中心预加载了 100 多种敏感信息类型，其中大多数与标识和定位个人数据相关。 根据正则表达式 () 正则表达式或函数定义的模式，这些内置敏感信息类型可以帮助识别和保护信用卡号、银行帐号、护照号等。 若要了解详细信息，请参阅[敏感信息类型查找的内容](../compliance/sensitive-information-type-entity-definitions.md)。

如果需要标识和保护特定于组织或区域类型的敏感项目（如员工标识的自定义格式，或内置敏感信息类型未涵盖的其他个人信息），可以使用以下方法创建自定义敏感信息类型：

- PowerShell
- 具有精确数据匹配的自定义规则 (EDM) 
- 通过合规性中心管理员 UI，如使用合规性分数 [和合规性管理器文章中的突出显示内容](information-protection-deploy-compliance.md)

您还可以自定义现有的内置敏感信息类型。

有关详细信息，请参阅以下文章：

- [自定义内置敏感信息类型](../compliance/customize-a-built-in-sensitive-information-type.md)
- [了解敏感信息类型](../compliance/sensitive-information-type-learn-about.md)
- [在安全与合规中心内创建自定义敏感信息类型](../compliance/create-a-custom-sensitive-information-type.md)
- [使用安全与合规中心 PowerShell 创建自定义敏感信息类型](../compliance/create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [使用基于精确数据匹配的分类创建自定义敏感信息类型](../compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

### <a name="content-explorer"></a>内容资源管理器

确定环境中出现敏感项目的重要工具是合规性管理中心内的新内容Microsoft 365资源管理器。[](../compliance/data-classification-content-explorer.md) 这是一个自动工具，用于对整个 Microsoft 365 订阅进行初始和持续扫描，以发现敏感信息类型出现并显示结果。

利用新的内容资源管理器工具，您可以使用内置敏感信息类型或自定义类型快速识别环境中敏感项目的位置。 这可能涉及到建立一个流程，并分配有定期调查敏感项目存在和位置的责任。

除了本文中重点介绍的其他步骤外，这还提供了一个起点，用于确定要通过计划的项目配置和监视进行保护Microsoft 365风险暴露、准备情况以及位置。

### <a name="other-methods-to-identify-personal-data-in-your-environment"></a>识别环境中个人数据的其他方法

除了内容资源管理器之外，组织还有权访问内容搜索功能，以使用高级搜索标准和自定义筛选器生成自定义搜索以查找其环境中的个人数据。

本文提供了关于使用内容搜索发现个人数据的详细 [指导](/compliance/regulatory/gdpr)。 GDPR 和 [CCPA 的 DSR](/compliance/regulatory/gdpr-dsr-Office365#introduction-to-dsrs) 中还探索了内容搜索和其他发现技术。

监视器和回复文章中提供了有关调查及修正Microsoft 365个人数据的其他[见解](information-protection-deploy-monitor-respond.md)。

> [!NOTE]
> 若要查找本地存储的文件中包含的敏感信息，请参阅 [Azure 信息保护](/azure/information-protection/quickstart-findsensitiveinfo)。
