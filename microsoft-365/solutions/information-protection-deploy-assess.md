---
title: 评估数据隐私风险并使用 Microsoft 365 标识敏感项目
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 07/13/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: 确定 Microsoft 365 环境中的数据隐私法规、相关方案、准备情况和敏感信息类型。
ms.openlocfilehash: 0cfa9f8a22810027e1a31ce2ace8b42f26ef9eb2
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126592"
---
# <a name="assess-data-privacy-risks-and-identify-sensitive-items-with-microsoft-365"></a>评估数据隐私风险并使用 Microsoft 365 标识敏感项目

在实施任何相关的改进操作（包括使用 Microsoft 365 功能和服务可实现的）之前，评估您的组织所遵循的数据隐私法规和风险是关键的首要步骤。 

## <a name="potentially-applicable-data-privacy-regulations"></a>可能适用的数据隐私法规

有关数据隐私管理法规的更广泛的规章框架的良好参考，请参阅[Microsoft 服务信任门户](https://servicetrust.microsoft.com/)和有关[常规 data PROTECTION 规章（GDPR）规章的一系列文章](../compliance/gdpr.md)，以及您的行业或地区可能受管理的规章上的其他材料。

### <a name="gdpr"></a>GDPR

GDPR （最著名和引用的数据隐私法规）规定了收集、存储、处理和共享与是欧盟（EU）的某个标识的自然个人相关的任何个人数据的收集、存储、处理和共享。 

根据 GDPR 文章4： 

- "个人数据" 表示与标识的或可标识的自然人员（"数据主体"）相关的任何信息;可识别的自然用户可以直接或间接地通过引用标识符（如名称、标识号码、位置数据、联机标识符或该自然人员的物理、physiological、遗传、精神、经济、文化或社会身份）的引用来进行识别。

### <a name="iso-27001"></a>ISO 27001

遵循其他标准（如 ISO 27001）也被多个欧洲监管机构识别为跨个人、过程和技术频谱的一个有效的意向代理。 它指定的标准会重叠并遵守 ISO-27001 驱动的保护机制，在某些情况下，可以将其视为满足某些隐私义务的代理。

### <a name="other-data-privacy-regulations"></a>其他数据隐私法规

其他明显的数据隐私法规也指定了处理个人数据的要求。

在美国，其中包括加利福尼亚州消费者保护法（[CCPA](../compliance/ccpa-faq.md)）、HIPAA-高科技（美国卫生保健隐私法案）和 Graham 里奇比利雷 ACT （GLBA）。 其他特定于状态的法规也就地或在开发中。 

在世界各地，其他示例包括德国国家 GDPR 实施法案（BDSG）、巴西数据保护法案（LGPD）和其他许多其他示例。

## <a name="regulation-mapping-to-microsoft-365-technical-control-categories"></a>法规到 Microsoft 365 的技术控制类别的映射

许多与隐私相关的法规都有重叠的要求，因此在开发任何技术控制方案之前，应了解它们所服从的法规。 

在此整体解决方案的文章的后续参考中，此表提供了对数据隐私法规的采样的摘录。 

| 管制 | 文章/部分 | 部分 | 适用的技术控制类别 |
|:-------|:-----|:-------|:-------|
| GDPR | 第5篇文章（1）（f） | 应以确保个人数据的适当安全性的方式处理个人数据，包括使用适当的技术或组织措施（"完整性" 和 "机密性"）来防止未经授权或非法处理以及防止意外丢失、破坏或损坏。  |  各种 <br> 标识 <br> 设备 <br> 威胁防护 <br> 保护信息 <br> 管理信息 <br> 发现和响应 |
|  | 文章（32）（1）（a） | 考虑到艺术的状态、实现的成本以及处理的性质、范围、上下文和目的，以及对自然人员的权利和自然人的可能性和严重性有不同的风险，而控制器和处理器应实施适当的技术和组织措施，以确保适合风险的安全级别，其中包括 alia：（a）个人数据的假名化和加密。 | 保护信息 |
|  | 文章（13）（2）（a） | "...在获取个人数据时，控制器应提供以下详细信息，以确保公平和透明处理：（a）存储个人数据的时间段，或者，如果不可能，则用于确定该时间段的条件。 | 管理信息 |
|  | 文章（15）（1）（e） | 数据主体应具有从控制器确认获取的权限，以确定是否正在处理与他/她有关的个人数据，在这种情况下，对个人数据和以下信息的访问权限：（e）是否存在从控制器纠正请求的权限，或擦除个人数据或将有关数据主体或对象的个人数据处理限制为此类处理。 | 发现和响应 |
| LGPD | 文章46 | 处理代理应采用安全性、技术和管理措施，以保护个人数据免遭未经授权的访问和意外或非法的销毁、丢失、篡改、通信或任何类型的不正确或非法处理的情况。 | 保护信息 <br> 管理信息 <br> 发现和响应|
|  | 文章48 | 控制器必须与国家/地区颁发机构和数据主体进行通信。可能会给数据主体带来风险或相关损坏的安全事件的出现。 | 发现和响应 |
| HIPPA-高科技 | 45 CFR 164.312 （e）（1） | 实施技术安全措施，以防止未经授权访问通过电子通信网络传输的电子保护健康信息。 | 保护信息 |
|  | 45 C.F.R。 164.312 （e）（2）（ii） | 在认为合适时实现一种加密电子保护的健康信息的机制。 | 保护信息 |
|  | 45 CFR 164.312 （c）（2） | 实现电子机制，以 corroborate 未经授权的方式更改或销毁电子保护的运行状况信息。 | 管理信息 |
|  | 45 CFR 164.316 （b）（1）（i） | 如果要记录此 subpart 所需的操作、活动或评估，请维护操作、活动或评估的书面（可能是电子的）记录 | 管理信息 |
|  | 45 CFR 164.316 （b）（1）（ii） | 将此部分的 "段落（b）（1）" 所需的文档从其创建日期的6年或该日期的最后生效日期（以稍后为准）中保留。 | 管理信息 |
|  | 45 C.F.R。 164.308 （a）（1）（ii）（D） | 实施定期查看信息系统活动记录的过程，例如审核日志、访问报告和安全事件跟踪报告 | 发现和响应 |
|  | 45 C.F.R。 164.308 （a）（6）（ii） | 确定和响应可疑或已知的安全事件;降低范围切实可行、对被覆盖的实体或业务关联的安全事件的有害影响;并记录安全事件及其结果。 | 发现和响应 |
|  | 45 C.F.R。 164.312 （b） | 实施硬件、软件和程序机制，以记录和检查包含或使用电子保护运行状况信息的信息系统中的活动。 | 发现和响应 |
| CCPA | 1798.105 （c） | 从使用者处收到可验证的请求以删除与本部分中的分支（a）相关的个人信息的企业应从其记录中删除使用者的个人信息，并指示所有服务提供商从其记录中删除使用者的个人信息。 | 发现和响应 |
|  | 1798.105 （d） | （1798.105 的例外（c） <br> 如果业务或服务提供商需要维护使用者的个人信息（请参阅当前规章以获取其他信息），则业务或服务提供商应不需要遵守使用者的删除使用者的个人信息的请求。 | 发现和响应 |
|||||

>[!Important]
>这不是一个详尽的列表。 请参阅[合规性管理器](../compliance/compliance-manager-overview.md)或你的法律或合规性顾问，了解有关所引用的部分的适用性的详细信息，请参阅所列的技术控制类别。
>

## <a name="knowing-your-data"></a>了解你的数据

无论您遵守什么管理法规，在组织内部和外部的不同用户数据类型与您的系统进行交互的所有重要因素都可能影响您的整体个人数据保护策略，这取决于适用于您的组织的行业和政府法规。 这包括存储个人数据的位置、类型以及它的用途，以及在什么情况下收集的情况。
 
![了解您的数据：类型是什么，以及它在什么情况下收集到什么情况下](../media/information-protection-deploy-assess/information-protection-deploy-assess-knowing-data.png)

### <a name="data-portability"></a>数据可移植性 

在处理、优化和其他版本的过程中，数据也会随时间推移而来回移动。 初始快照永远不会足够。 需要有一个持续的过程来了解你的数据。 这表示处理大量个人数据的大型组织的最大挑战之一。 未解决 "数据" 问题的组织可能最终会有很高的风险，并且可能会从管理机构中受到罚款。

![数据生命周期](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-lifecycle.png)
 
### <a name="where-the-personal-data-is"></a>个人数据的位置

若要解决数据隐私法规，您不能依赖于您认为个人数据可能存在于什么位置（现在或将来）的一般概念。 数据隐私管理法规要求组织证明他们知道个人数据是什么持续的。 这使您可以获取所有数据源的初始快照以存储个人信息（包括 Microsoft 365 环境）的初始快照，并为持续监控和检测建立机制。

如果尚未评估与数据隐私法规相关的总准备情况和风险，请使用以下3步框架开始。 

![评估与数据隐私法规相关的总体准备情况和风险的步骤](../media/information-protection-deploy-assess/information-protection-deploy-assess-grid.png)

>[!Note]
>本文及其内容并不旨在取代法律顾问服务。 它只提供了一些基本指导和链接，这些链接指向在评估的早期阶段可能会获得帮助的一些工具。
>
 
## <a name="step-1-develop-a-foundational-understanding-of-your-organizations-personal-data-scenarios"></a>步骤1：开发对组织的个人数据方案的基础了解 

您需要根据当前管理的个人数据的类型、存储的位置、对其实施的保护性控制、对其生命周期的管理方式以及谁有权访问来评估数据隐私风险的暴露程度。 

作为起始点，请务必清点 Microsoft 365 环境中存在的个人数据类型。 使用以下类别：

- 执行日常业务功能所需的员工数据
- 组织的业务客户、合作伙伴以及企业到企业（B2B）方案中的其他关系的相关数据
- 组织关于向企业到客户（B2C）方案中的组织管理的联机服务提供信息的使用者的数据

下面的示例展示了组织的典型部门的不同类型的数据。

![个人数据的类型](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-types.png)

大多数受数据隐私法规制约的个人数据通常收集并存储在 Microsoft 365 之外。 来自面向消费者的 web 或移动应用程序的任何个人数据都需要从这些应用程序导出到 Microsoft 365，以便在 Microsoft 365 中进行数据隐私审查。 

Microsoft 365 中的数据隐私暴露可能更有限，相对于你的 web 应用程序和 CRM 系统，此解决方案不会解决这些漏洞。

在评估风险配置文件时，请考虑以下常见的数据隐私合规性挑战：

 - **个人数据分发。** 分散是关于指定主题的信息的方式？ 它是否足够充分，能够说服管理机构正确控制是否就绪？ 如果需要，可以对其进行调查并修正吗？
- **针对 exfiltration 进行防护。** 如何保护给定类型或源中的个人数据不受威胁以及如何进行响应？
- **保护与风险。** 在需要最终用户干预的情况之下，哪些信息保护机制适用于风险以及如何维护业务连续性和工作效率并将最终用户影响降至最低？ 例如，是否应使用手动分类或加密？
- **个人数据保留。** 出于有效的业务原因，包含个人数据的信息需要保留多长时间，以及如何避免过期的保留和永久做法，与业务连续性的保留需求平衡？
- **处理数据主体请求。** 处理数据主体请求（Dsr）和任何补救措施（如 anonymization、密文和删除）将需要哪些机制？
- **持续监控和报告。** 对于不同的数据类型和源，可以使用哪种日常监控、调查和报告技术？
- **对数据处理的限制。** 对于通过这些方法收集或存储的信息的数据使用是否存在限制，这些方法必须由组织在隐私控件中反映出来？ 例如，销售人员不会使用个人数据的承诺可能要求贵组织将这些信息转移或存储在与销售组织相关联的系统中。

### <a name="employee-data-required-to-carry-out-day-to-day-business-functions"></a>执行日常业务功能所需的员工数据

按性质组织的组织需要收集有关电子邮件标识和 HR 目的的员工的数据，具体取决于他们在员工协议中同意的内容。 只要某人为公司工作，通常就不会出现问题。 组织可能希望设置适当的机制来防止恶意参与者 exfiltration 或泄漏员工个人数据。 

如果某人离开公司，组织通常会在删除用户帐户、取消邮箱和个人驱动器以及更改员工在诸如人力资源系统等方面的状态时进行流程、过程和保留和删除计划。 在涉及诉讼的情况下，法律调查的员工或另一方可能具有获取有关组织系统中存储的个人数据的信息的有效原因。 在某些情况下，该方可能会请求删除或匿名此类数据。 

为了满足此类需求，组织应具有解决预防性、侦探和补救需求的过程和过程，以促进此类请求，请注意，有关某个员工的一些信息可能被视为对业务连续性至关重要。 例如，个人创作的文件或执行函数的信息。 

>[!Note]
>有关 Microsoft 365 中的个人数据的调查和修正技术，请参阅[监视器和响应文章](information-protection-deploy-monitor-respond.md)。 您可能还需要采用自动化分类和保护方案，以确保个人数据在组织内部进行控制，同时阻止它在恶意主角情况下离开组织。 有关详细信息，请参阅[保护信息一文](information-protection-deploy-protect-information.md)。
>
 
### <a name="data-the-organization-has-about-its-business-customers-in-the-b2b-scenario"></a>组织关于 B2B 方案中的业务客户的相关数据

B2B 信息的收集也是一项挑战，因为您的组织可能需要在其各个系统中保留客户名称和事务的记录以实现业务连续性目的，同时保护这些信息不会受到无意或恶意 exfiltration。 与员工数据一样，组织必须具有策略、过程和技术控制措施来保护此类数据，并根据定义的保留和删除计划来查看它的年龄。 

通常情况下，外部客户、合作伙伴和组织从事的其他实体的合同将使用语言处理此类数据的处理，包括在实体与组织之间的关系期间和之后的保护、保留和删除。 

### <a name="data-the-organization-has-about-consumers-who-provide-information-to-online-services-that-the-organization-manages-in-the-b2c-scenario"></a>组织关于向在 B2C 方案中组织管理的联机服务提供信息的使用者的数据

由于客户数据泄露的许多公共实例，大多数人都会想到数据隐私的类别。 这可以是有意的，例如向提供程序提供合同的第三方，或无意中，例如由恶意主角 exfiltration。 消费者数据保护是欧盟和其他公司颁布这些法规的主要原因之一。 像 GDPR 和 CCPA 这样的数据隐私法规要求您规划以下内容：

- [行动计划](../compliance/gdpr-action-plan.md)和[责任就绪清单](../compliance/gdpr-arc-office365.md)
- [数据保护影响评估](../compliance/gdpr-data-protection-impact-assessments.md)
- [违规通知](../compliance/gdpr-breach-office365.md)
- [数据主体请求](../compliance/gdpr-dsr-office365.md)

如果您的组织不执行大量直接的消费者数据收集，则此类别可能会降低问题。 但是，您可能仍需要完成这些文章中概述的过程以实现合规性。

### <a name="step-1-summary"></a>步骤1摘要

了解风险和数据隐私法规的暴露是一个重要的第一步，基于组织的个人数据方案的基础了解。

如果您没有来自 Microsoft 365 环境中的使用者的个人数据，或者它已局限于环境的某些部分，并且对技术控制的需求 predicated 在使用者类型数据暴露的情况下，则该技术控制可能只需要在环境的高风险部分（而不是到处）中使用。

尽管外部组织或标准控制集建议（如 Microsoft 365 中的合规性分数）可能有助于通知控制策略，但您选择的实施应由数据清单感知驱动，以量化实际风险暴露。

大多数组织将对上述方案之一有一些暴露。 采用整体评估方法非常重要。

## <a name="step-2-assess-your-readiness-for-complying-with-data-privacy-regulations"></a>步骤2：评估您是否已遵守数据隐私法规

虽然特定于 GDPR，但在免费的[MICROSOFT GDPR 评估工具](https://www.microsoft.com/cyberassessment/en/gdpr/uso365)中提出的问题使您能够更好地开始了解您的总体数据隐私准备情况。 

受其他数据隐私法规约束（如美国或巴西 LGPD 中的 CCPA）的组织可能还会受益于此工具的就绪到期情况（与 GDPR 重叠的规定）清单。

GDPR 评估包括以下几个部分：

| 分区 | 说明 |
|:-------|:-----|
| 治理 | <ol><li>您的隐私策略是否明确声明要处理的数据信息？ </li><li>您是否定期运行隐私影响评估（Pia）？ </li><li> 您是否使用工具来管理个人信息（PI）？ </li><li> 您是否有合法的颁发机构在任何给定的人上使用 PI 数据开展业务？ 您是否跟踪数据的同意？ </li><li> 您是否跟踪、实现和管理审核控件？ 您是否监视数据泄露？ </li></ol>|
| 删除和通知 | <ol><li>您是否提供了有关如何访问用户数据的显式说明？ </li><li> 您是否已记录处理自愿退出同意的流程？ </li><li> 您是否有数据的自动删除过程？ </li><li>   您是否有在与客户合作时验证标识的过程？ </li></ol>|
| 风险缓解和信息安全 | <ol><li>您是否使用工具扫描非结构化数据？ </li><li>所有服务器是否都处于最新状态，是否使用防火墙来保护它们？ </li><li>您是否在运行服务器的定期备份？ </li><li>您是否积极监视数据泄露？ </li><li>您是否在静态和传输中对数据进行加密？ </li></ol>|
| 策略管理 | <ol><li>如何管理您的绑定企业规则（BCRs）？ </li><li>您是否跟踪数据的同意？ </li><li> 在完全覆盖1到5、5个范围的情况下，您的合同是否涵盖数据分类和处理要求？ </li><li>您是否有并定期测试事件响应计划？ </li><li>您使用什么策略来管理访问？ </li></ol>|
|||
 
## <a name="step-3-identify-sensitive-information-types-that-occur-in-your-microsoft-365-environment"></a>步骤3：确定在 Microsoft 365 环境中出现的敏感信息类型。 

此步骤涉及标识特定的敏感信息类型，这些类型受特定管理法规控制，以及在 Microsoft 365 环境中出现的问题。 

在您的环境中查找包含个人的内容可能是一项艰巨的任务，以前的任务结合使用合规性搜索、电子数据展示、高级电子数据展示、DLP 和审核。 

使用 Microsoft 合规性管理中心中的新**数据分类**解决方案，[内容资源管理器](../compliance/data-classification-content-explorer.md)功能就变得更加简单，该功能可用于内置或自定义敏感信息类型，包括与个人数据相关的信息类型。
 
### <a name="sensitive-information-types"></a>敏感信息类型

Microsoft 合规性管理中心预加载了100以上的敏感信息类型，与确定和查找个人数据相关的大部分信息类型都是如此。 这些内置的敏感信息类型可帮助根据正则表达式（regex）或函数定义的模式来识别和保护信用卡号码、银行帐号、护照号码等。 若要了解详细信息，请参阅[敏感信息类型查找的内容](../compliance/what-the-sensitive-information-types-look-for.md)。

如果需要标识和保护组织特有或区域类型的敏感项目（如员工 Id 的自定义格式）或非内置敏感信息类型已包含的其他个人信息，则可以使用以下方法创建自定义敏感信息类型： 

- PowerShell
- 具有精确数据匹配（EDM）的自定义规则
- 通过合规性中心管理 UI （在[使用合规性分数和合规性管理器文章](information-protection-deploy-compliance.md)中突出显示）

您还可以自定义现有的内置敏感信息类型。

有关详细信息，请参阅以下文章：

- [自定义内置敏感信息类型](../compliance/customize-a-built-in-sensitive-information-type.md)
- [自定义敏感信息类型](../compliance/custom-sensitive-info-types.md)
- [在安全与合规中心内创建自定义敏感信息类型](../compliance/create-a-custom-sensitive-information-type.md)
- [使用安全与合规中心 PowerShell 创建自定义敏感信息类型](../compliance/create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [使用基于数据的确切分类创建自定义敏感信息类型](../compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

### <a name="content-explorer"></a>内容浏览器

Microsoft 365 合规性管理中心中的新[内容浏览器](../compliance/data-classification-content-explorer.md)是用于确定环境中敏感项目发生情况的重要工具。 它是一种自动工具，用于对整个 Microsoft 365 订阅进行初始和日常扫描，以实现敏感信息类型和结果的显示。
 
通过新的内容资源管理器工具，可以使用内置的敏感信息类型或自定义的信息类型快速标识环境中敏感项目的位置。 这可能包括建立过程和分配的责任，以便定期调查敏感项目的状态和位置。

除了本文中突出显示的其他步骤，这还提供了一个起始点，用于确定要通过规划的 Microsoft 365 配置和监视来保护的敏感项目的总体风险暴露程度、准备情况和位置。 

### <a name="other-methods-to-identify-personal-data-in-your-environment"></a>在您的环境中标识个人数据的其他方法

除了内容浏览器之外，组织还可以访问内容搜索功能，以生成自定义搜索以在其环境中使用高级搜索条件和自定义筛选器查找个人数据。

[本文](../compliance/search-for-and-find-personal-data.md)提供了有关使用个人数据发现内容搜索的详细指南。 还在[dsr 中对 GDPR 和 CCPA](../compliance/gdpr-dsr-office365.md#introduction-to-dsrs)研究了内容搜索和其他发现技术。

有关 Microsoft 365 中的个人数据调查和修正技术的其他见解，请在[监视器和响应文章](information-protection-deploy-monitor-respond.md)中提供。
