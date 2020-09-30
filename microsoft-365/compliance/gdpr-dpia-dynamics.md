---
title: 根据 GDPR 对 Dynamics 进行 DPIA
description: 提供有关 Dynamics 365 信息的数据控制者，以帮助确定是否需要 DPIA，以及要包含的详细信息。
keywords: DPIA, Microsoft 365, Dynbamics 365, Microsoft 365 文档, GDPR
robots: NOINDEX,NOFOLLOW
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
hideEdit: true
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 29da829ddf20a24776ef40b7aefb02cdf1546669
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "48305052"
---
# <a name="data-protection-impact-assessments-guidance-for-data-controllers-using-dynamics-365"></a>数据保护影响评估：使用 Dynamics 365 的数据控制者指南

根据一般数据保护条例 (GDPR)，需要由数据控制者准备数据保护影响评估 (DPIA)，用于处理“可能对自然人的权力和自由产生高风险”的操作。Dynamics 365 本身并不一定要求由使用它的数据控制者创建 DPIA。更准确地说，是否需要 DPIA 取决于数据控制者部署、配置和使用 Dynamics 365 的*方式*和背景。

此文档的目的是为数据控制者提供 Dynamics 365 的相关信息，帮助他们确定是否需要 DPIA 以及要包含的详细信息。

## <a name="part-1-determining-whether-a-dpia-is-needed"></a>第 1 部分：确定是否需要 DPIA

GDPR 第 35 条规定需要由数据控制者来创建数据保护影响评估，“用于在考虑某种处理类型的本质、范围、环境和目的的情况下评估该处理类型（尤其是使用新技术的处理类型）是否会自然人的权力和自由产生高风险。”它进一步规定了指示此类高风险的特定因素（将在下表中讨论）。根据控制者的特定实现和 Dynamics 365 的使用情况，确定是否需要 DPIA 时，数据控制者应考虑以下因素，以及任何其他相关因素。

||||
|:----|:----|:--|
|**风险因素**|**Dynamics 365 的相关信息**| |
| 基于自动化处理对自然人的私人方面进行系统全面的评估（包括剖析以及会对自然人产生法律效应或显著影响自然人的决策）； | Dynamics 365 确实执行特定数据自动化处理，例如潜在客户或机遇评分（例如，预测销售出产品的可能性）。 但这并不适合执行对个人产生法律或类似显著影响的决策所依据的处理。<br><br> 但是，由于 Dynamics 365 是一项高度可定制的服务，可将数据控制者配置为用于此类处理，例如针对雇佣决策或信用额度申请的评分。 |   |
| 处理大量 <sup>1</sup> 特殊类别的数据，如种族或族裔、政治观点、宗教或哲学信仰、工会成员身份、基因数据、用于唯一标识自然人的生物识别数据、关于自然人性生活健康或性取向数据的数据，或与刑事犯罪和违法行为相关的个人数据； | Dynamics 365 不专用于处理特殊类别的个人数据。 <br><br> 不过，数据控制者*可*使用 Dynamics 365 处理枚举的特殊类别的数据。 例如，Dynamics 365 提供医保行业模板，可用来处理与健康状况关联的个人数据。 此外，Dynamics 365 是一项高度可定制的服务，支持客户跟踪或处理任何类型的个人数据，包括特殊类别的个人数据。 但作为数据处理者，Microsoft 不对此类使用进行任何控制，且通常对此类使用鲜有或没有任何见解。 |   |
| 大规模系统化监视公开可访问区域 | Dynamics 365 不专用于进行或促进此类监视。 <br><br> 不过，数据控制者可用它处理通过此类监视收集的数据。 | |

>[!Note]
><sup>1</sup> 关于处理“大量”数据的标准，GDPR 的第 91 篇声明陈述如下：“如果涉及由个体医生、其他医疗保健专业人员或律师来处理患者或客户的个人数据，则个人数据的处理不应视为处理大量数据。 在这种情况下，不得强制进行数据保护影响评估。”

## <a name="part-2-contents-of-a-dpia"></a>第 2 部分：DPIA 的内容

第 35(7) 条规定，数据保护影响评估应指定处理的目的和预期处理的系统化说明。 综合 DPIA 的系统化说明可能包括所处理数据的类型、数据保留时间、数据存储位置和传输位置以及有权访问数据的第三方等因素。 此外，DPIA 还必须包括：

- 对与处理操作的目的相关的必要性和合理性的评估；
- 对自然人的权力和自由带来的风险的评估；以及
- 应对风险的措施（包括保护措施、安全措施和机制），以确保对个人数据的保护并证明符合此条例的规定（将数据使用者和其他相关人员的合法权益考虑在内）。

下表包含与上述每个元素相关的 Dynamics 365 信息。如第 1 部分中所述，根据控制者的具体实施和 Dynamics 365 的使用情况，数据控制者必须考虑下面提供的详细信息，以及任何其他相关因素。

|||
|:---|:---|
|**DPIA 的元素**|**Dynamics 365 的相关信息**|
| 处理目的 | 使用 Dynamics 365 处理数据的目的由实现、配置和使用它的控制者确定。 <br><br> Dynamics 365 是一个联机处理平台，由多项离散的在线服务组成，每项服务都具有不同的处理目的。Dynamics 365 所提供的服务类型如下所示： <br><br> **客户参与**本质上是一项客户关系管理服务。它包括下列在线服务：Dynamics 365 for Sales、Dynamics 365 for Marketing、Dynamics 365 for Customer Service、Dynamics 365 for Project Service 和 Dynamics 365 for Field Service。<br><br>**Dynamics 365 for Finance and Operations, Enterprise edition** (D365FOEE) 是软件即服务 (SaaS) 型企业资源规划套件，即主要向针对销售、服务、财务和运营、制造和人力资源的企业客户管理提供。<br><br>**Dynamics 365 for Retail** (D365FR) 以软件即服务的形式提供，同时集成了适用于企业零售商和分销商的本地销售点解决方案。<br><br>**Dynamics 365 Lifecycle Services (LCS)** 是一项辅助型在线服务，主要被企业客户用来部署、管理和维护客户的 D365FOEE、D365FR 实现。<br><br>**Dynamics 365 for Business Central** 是 Microsoft 以软件即服务 (SaaS) 的形式向小中型企业提供的一项企业资源规划服务。 该服务处理个人数据以协助财务、制造、客户关系管理、供应链、分析和电子商务。<br><br>**Dynamics 365 for Talent** 以软件即服务 (SaaS) 的形式向客户提供针对人力资源的管理并包括下列服务：<br><br> *核心人力资源* — 此服务用于简化记录保存任务并自动执行与组织人员配置相关的流程。 这些流程包括员工保留、福利管理、薪酬、培训、绩效考核和变更管理。<br><br> *吸引* - 此服务用于找寻、面试和录用人员。<br> *入职* - 此服务用于帮助新员工进入工作岗位 *。<br><br>**Microsoft Social Engagement** (MSE) 是一项面向企业客户的 Dynamics 365 辅助性服务，可以 (i) 处理公共社交媒体文章和有限数量社交媒体中的数据使用者发布的个人数据，以帮助他们分析和确定相关主题（例如趋势），并在这些虚拟场所（例如粉丝页面）管理企业或机构的状态，包括发布到特定社交媒体的内容（聆听）；和 (ii) 通过社交媒体中的私密交流，直接与数据使用者联系（参与）。<br><br> 在其操作上面所枚举服务的处理能力方面，Dynamics 365 仅处理个人数据，以提供所述的在线服务，包括与提供这些服务（例如个性化、安全性、诈骗和恶意软件防护、故障排除和改进）相符的目的。<br><br> 正如[联机服务条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)和[数据保护附录](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=67)中所规定，作为数据处理者，Microsoft 处理客户数据以根据客户的书面说明为客户提供联机服务。 <br><br> 正如[联机服务条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)和[数据保护附录](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=67)标准中的详细信息中，Microsoft 还使用个人数据来支持有限的合法业务运营，包括：(1) 账单和帐户管理；(2) 薪酬（例如，计算员工佣金和合作伙伴奖励）；(3) 内部报告和建模（例如，预测、收入、产能计划、产品策略）；(4) 打击可能影响 Microsoft 或 Microsoft 产品的欺诈、网络犯罪或网络攻击；(5) 改善可访问性、隐私或能效的核心功能；(6) 财务报告和履行法律义务（受联机服务条款中概述的客户数据披露的限制）。 <br><br> Microsoft 是用于支持这些特定合法业务运营的个人数据处理的控制者。 通常，Microsoft 在将个人数据用于我们的合法业务运营之前会对其进行汇总处理，从而消除 Microsoft 识别特定个人身份的能力，并以最不易识别的形式使用个人数据，以支持合法业务运营所需的处理。 <br><br> Microsoft 不会将因此获得的客户数据或信息用于分析、广告或类似商业目的。 |
| 处理的个人数据类别  | **客户数据**：这是客户或代表客户通过使用 Microsoft 联机服务向 Microsoft 提供的所有数据，包括文本、声音、视频或图像文件和软件。 它包括客户上传用于存储或处理的数据以及定制数据。 Office 365 中处理的客户数据示例包括 Exchange Online 中的电子邮件内容，以及存储在 SharePoint Online 或 OneDrive for Business 中的文档或文件。 <br><br> **服务生成的数据**：这是由 Microsoft 通过服务操作生成或派生的数据，例如使用或性能数据。 这些数据大多包含由 Microsoft 生成的假名标识符。 <br><br> **支持数据**：客户或代表客户通过与 Microsoft 签订协定以获取联机服务技术支持而提供给 Microsoft 的数据（或客户授权 Microsoft 从联机服务获取的数据）。 <br><br> 客户数据、系统生成的数据和支持数据不包括管理员和数据，例如客户管理员联系信息、订阅信息和付款信息，Microsoft 在其作为数据控制者的角色中收集和处理这些数据，这不在本文档的讨论范围内。 |
| 数据保留 | Microsoft 将在客户有权使用服务的期间保留客户数据，直到按照客户的指示或联机服务条款删除或返回所有客户数据为止。  在客户订阅期内，客户可随时访问和提取服务中存储的客户数据。 如果客户订阅到期或终止，帐户功能将受到限制，Microsoft 会将该帐户存储在该联机服务中的客户数据保留 90 天，便于客户提取数据。 90 天保留期结束后，Microsoft 将禁用客户帐户并删除客户数据。<br><br> 客户可随时使用 Dynamic [数据使用者权限指南](gdpr-dsr-dynamics365.md)中所述的功能删除客户数据和匿名数据。 |
| 个人数据的位置和传输 | 如果客户在澳大利亚、加拿大、欧盟、印度、日本、英国或美国配置其 Dynamics 365 Core Services 实例，Microsoft 将在特定地理区域内存储静态客户数据，《联机服务条款》中规定了某些例外情况。 有关客户数据存储的详细信息，请参阅[信任中心](https://www.microsoft.com/trustcenter/cloudservices/dynamics365)。<br><br>对于来自欧洲经济区和瑞士的个人数据，Microsoft 将确保在向第三方国家/地区或国际组织传输的个人数据时实施 GDPR 第 46 条中规定的相应安全措施。 除 Microsoft 根据处理者标准合同条款和其他模板合同所做的承诺外，Microsoft 还获得了欧盟-美国和瑞士-美国隐私防护框架认证并践行其承诺。 |
| 对与处理操作的目的相关的必要性和合理性的评估 | 这种评估将取决于控制者的处理需求和目的。<br><br>在处理者能力方面，Microsoft 提议 D365 仅处理个人数据，以向用户提供其在线服务，包括与提供这些服务（例如客户个性化、安全性、诈骗和恶意软件防护、故障排除和改进）相符的目的。如有必要，Microsoft 代表客户（租户）处理数据，以提供“在线服务条款”( [https://microsoft.com/licensing/contracts](https://microsoft.com/licensing/contracts)) 中所规定的请求服务。 |
| 对数据使用者的权力和自由带来的风险的评估 | 使用 Dynamics 365 对数据使用者的权力和自由带来的关键风险取决于数据控制者实施、配置和使用它的方式和背景。<br><br> Microsoft 采取相关措施来支持提供服务，例如对用于支持其合法业务运营的个人数据进行匿名化或汇总处理，以便最大程度地降低对使用该服务的数据主体进行此类处理的风险。 <br><br> 然而，与其他所有服务一样，该服务中保存的个人数据可能存在未经授权的访问或意外泄漏的风险。下面介绍 Microsoft 所采取的用来应对此类风险的措施。 |
| 与第三方下级处理者分享的数据 | Microsoft 会与充当下级处理者角色的第三方分享数据，以实现客户和技术支持、服务维护和其他操作。 Microsoft 将向其传输客户数据、支持数据或个人数据的任何分包商都会与 Microsoft 签订书面协议，该协议的效力不低于联机服务条款中的数据保护条款。 与其分享来自 Microsoft 核心联机服务的客户数据的所有第三方下级处理者都包含在联机服务分包商列表中。 可以访问支持数据的所有第三方下级处理者（包括客户在其支持互动期间选择共享的客户数据）都包含在 Microsoft 商业支持承包商列表中。 |
| 数据主体权利 | 当以处理者的身份操作时，Microsoft 向客户（即数据控制者）提供其数据使用者的个人数据以及依据 GDPR 行使权力时满足数据使用者请求的能力。 我们以与产品功能和我们作为处理者的角色一致的方式完成此操作。如果我们收到来自客户数据使用者的请求，请求依据 GDPR 行使其一项或多项权力，我们将重定向数据使用者，使其直接向数据控制者提出请求。 针对 GDPR 和 CCPA 的 Dynamics 365 数据主体请求向数据控制者介绍了如何使用 Dynamics 365 中的功能来支持数据主体权限。 <br><br> 对于为支持合法业务流程而处理的个人数据，来自需要依据 GDPR 行使权力的数据主体的请求应定向到 Microsoft，如 Microsoft 隐私声明中所述。 <br><br> Microsoft 在将个人数据用于我们的合法业务运营之前通常会对其进行汇总处理，并且无法在汇总中识别特定个人的个人数据。 这将极大地降低个人的隐私风险。  如果 Microsoft 不能识别个人身份，它将无法支持数据主体的访问权、擦除权、可移植权或对处理的限制权或反对权。 |
| 应对风险的措施（包括保护措施、安全措施和机制），以确保对个人数据的保护并证明符合此 GDPR 的规定（将数据使用者和其他相关人员的合法权益考虑在内）。 | Microsoft 致力于帮助保护客户的信息安全。 按照 GDPR 第 32 条的规定，Microsoft 已采取并且将维持和遵循适当的技术和组织措施，这些措施旨在防止客户数据和支持数据意外泄露、未经授权或非法访问、公开、篡改、丢失或损坏。<br><br>有关针对 Dynamics 365 实现的安全性的 Microsoft 管理控制（技术和业务处理控制）详细列表，请访问[服务信任门户](https://servicetrust.microsoft.com/)。 Microsoft 还将履行适用于数据处理者的所有其他 GDPR 义务，包括但不限于提供数据保护影响评估和准确的记录。 <br><br> 当 Microsoft 为其合法业务运营处理个人数据时，它将履行适用于数据控制者的 GDPR 义务。 |

## <a name="learn-more"></a>了解详细信息

- [Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
