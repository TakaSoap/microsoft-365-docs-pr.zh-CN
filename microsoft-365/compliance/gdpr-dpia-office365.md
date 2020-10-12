---
title: 使用 Office 365 的数据控制者指南
description: 此文档为数据控制者提供有关 Office 365 的信息，帮助他们确定是否需要 DPIA 以及要包含的详细信息。
keywords: DPIA, Office 365, Microsoft 365 文档, GDPR
ms.localizationpriority: Priority
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
ms.openlocfilehash: a51b01d419cc81efd82c7ed78f5b05d337353b39
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413480"
---
# <a name="data-protection-impact-assessments-guidance-for-data-controllers-using-microsoft-office-365"></a>数据保护影响评估：使用 Microsoft Office 365 的数据控制者指南 

根据一般数据保护条例 (GDPR)，需要由数据控制者准备数据保护影响评估 (DPIA)，用于处理“可能对自然人的权力和自由产生高风险”的操作。Microsoft Office 365 本身并不一定要求由使用它的数据控制者创建 DPIA。更准确地说，是否需要 DPIA 取决于数据控制者部署、配置和使用 Office 365 的方式和背景。

本文档的第 1 部分提供了有关 Office 365 的信息，以帮助你（数据控制者）确定是否需要 DPIA。  如果答案为“是”，本文档的第 2 部分和第 3 部分提供了来自 Microsoft 的重要信息，以帮助起草该信息。 具体来说，第 2 部分为 DPIA 的每个必需元素提供了适用于所有 Office 365 服务的答案。 第 3 部分提供了针对客户许多最相关信息需求的附加产品特定信息，用于起草其 DPIA。 第 3 部分还包含一个说明性的 DPIA 文档，你可以下载和修改该文档，以简化 DPIA 的起草。

Office 365 应用程序和服务包括但不限于 Exchange Online、SharePoint Online、OneDrive for Business、Yammer 和 Microsoft Teams。 通过 Office 365 可获得的更完整的服务列表可以在 [Office 365 数据主题请求指南](gdpr-dsr-office365.md)的表 1 和表 2 中看到。

## <a name="part-1-determining-whether-a-dpia-is-needed"></a>第 1 部分：确定是否需要 DPIA

GDPR 第 35 条要求数据控制者创建数据保护影响评估，“用于在考虑某种处理类型的本质、范围、上下文和目的的情况下评估该处理类型（尤其是使用新技术的处理类型）是否会对自然人的权力和自由产生高风险。” 它还列出了指示此类高风险的特定因素，我们将在下表中对其进行讨论。 确定是否需要 DPIA 时，你（数据控制者）应根据控制者对 Office 365 的特定实施和使用，考虑这些因素以及任何其他相关因素。

|||
|:-----|:-----|:-----|
|**风险因素**|**Office 365 的相关信息**|
|基于自动化处理对自然人的私人方面进行系统全面的评估（包括剖析以及会对自然人产生法律效应或显著影响自然人的决策）。 |根据数据控制者的配置，Office 365 可能会执行特定的自动数据处理，例如，由工作区分析执行的分析，它允许数据控制者根据用户邮箱中的电子邮件和日历标题信息来获取员工在组织内的协作方式。 <br><br> Office 365 并不适合执行对个人产生法律或类似显著影响的决策所依据的自动处理。 但是，由于 Office 365 是一项高度可定制的服务，数据控制者可能会将其用于此类处理。 |
|处理大量 <sup>1</sup> 特殊类别的数据（如揭示种族或族裔、政治观点、宗教或哲学信仰或工会成员身份的数据、基因数据处理、用于唯一标识自然人的生物识别数据、关于自然人性生活健康或性取向数据的数据），或与刑事犯罪和违法行为相关的个人数据； |Office 365 未设计用于处理特殊类别的个人数据。 <br><br> 不过，数据控制者可使用 Office 365 来处理枚举的特殊类别的数据。 Office 365 是一项高度可定制的服务，支持客户跟踪或处理任何类型的数据，包括特殊类别的个人数据。 任何此类使用都与控制者确定是否需要 DPIA 有关。 但作为数据处理者，Microsoft 不对此类使用进行任何控制，且通常对此类使用鲜有或没有任何见解。 |
|大规模系统化监视公开可访问区域|Office 365 不专用于进行或促进此类监视。 <br><br> 不过，数据控制者可用它处理通过此类监视收集的数据。 |
|||

>[!Note]
><sup>1</sup> 关于处理“大量”数据的标准，GDPR 的第 91 篇声明陈述如下：“如果涉及由个体医生、其他医疗保健专业人员或律师来处理患者或客户的个人数据，则个人数据的处理不应视为处理大量数据。 在这种情况下，不得强制进行数据保护影响评估。”

## <a name="part-2-contents-of-a-dpia"></a>第 2 部分：DPIA 的内容

第 35(7) 条规定，数据保护影响评估应指定处理的目的和预期处理的系统化说明。 在 Microsoft 的 DPIA 中，此类系统化说明包括所处理数据的类型、数据保留时间、数据存储位置和传输位置以及有权访问数据的第三方等因素。 此外，DPIA 还必须包括：

- 对与处理操作的目的相关的必要性和合理性的评估；
- 对自然人的权力和自由带来的风险的评估；以及
- 应对风险的措施（包括保护措施、安全措施和机制），以确保对个人数据的保护并证明符合一般数据保护条例的规定（将数据使用者和其他相关人员的合法权益考虑在内）。

下表提供了来自 Microsoft 的重要信息，可以帮助你起草 DPIA。 它包含有关 Office 365 的信息，这些信息与 DPIA 所需的各个元素息息相关。 与第 1 部分一样，数据控制者必须考虑下面提供的详细信息，以及具体实施和使用 Office 365 的详细信息。

|||
|:-----|:-----|
|**风险因素**|**Office 365 的相关信息**|
| 处理目的 | 使用 Office 365 处理数据的目的由实现、配置和使用它的控制者确定。 <br><br> 正如[联机服务条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)和[数据保护附录](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=67)中所规定，作为数据处理者，Microsoft 处理客户数据以根据客户的书面说明为客户提供联机服务。 <br><br> 正如[联机服务条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)和[数据保护附录](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=67)标准中的详细信息中，Microsoft 还使用个人数据来支持有限的合法业务运营，包括：(1) 账单和帐户管理；(2) 薪酬（例如，计算员工佣金和合作伙伴奖励）；(3) 内部报告和建模（例如，预测、收入、产能计划、产品策略）；(4) 打击可能影响 Microsoft 或 Microsoft 产品的欺诈、网络犯罪或网络攻击；(5) 改善可访问性、隐私或能效的核心功能；(6) 财务报告和履行法律义务（受联机服务条款中概述的客户数据披露的限制）。 <br><br> Microsoft 是用于支持这些特定合法业务运营的个人数据处理的控制者。 通常，Microsoft 在将个人数据用于我们的合法业务运营之前会对其进行汇总处理，从而消除 Microsoft 识别特定个人身份的能力，并以最不易识别的形式使用个人数据，以支持合法业务运营所需的处理。 <br><br> Microsoft 不会将因此获得的客户数据或信息用于分析、广告或类似商业目的。 |
| 处理的个人数据类别 | **客户数据**：这是客户或代表客户通过使用 Microsoft 联机服务向 Microsoft 提供的所有数据，包括文本、声音、视频或图像文件和软件。 它包括客户上传用于存储或处理的数据以及定制数据。 Office 365 中处理的客户数据示例包括 Exchange Online 中的电子邮件内容，以及存储在 SharePoint Online 或 OneDrive for Business 中的文档或文件。 <br><br> **服务生成的数据**：这是由 Microsoft 通过服务操作生成或派生的数据，例如使用或性能数据。 这些数据大多包含由 Microsoft 生成的假名标识符。 <br><br> **诊断数据：** 此数据由 Microsoft 从客户本地安装的与联机服务相关的软件中收集或获取，也称为遥测。 此数据通常由本地安装的软件或运行该软件的计算机的属性进行标识。 <br><br> **支持数据：** 客户或代表客户通过与 Microsoft 签订协定以获取联机服务技术支持而提供给 Microsoft 的数据（或客户授权 Microsoft 从联机服务获取的数据）。 <br><br> 客户数据、系统生成的数据和支持数据不包括管理员和数据，例如客户管理员联系信息、订阅信息和付款信息，Microsoft 在其作为数据控制者的角色中收集和处理这些数据，这不在本文档的讨论范围内。 |
| 数据保留 | **客户数据：** 如联机服务条款中的数据保护条款所述，Microsoft 将在客户有权使用服务的期间保留客户数据，直到按照客户的指示或联机服务条款删除或返回所有客户数据为止。 <br><br> 在客户订阅期间，客户可随时访问、提取和删除存储在服务中的客户数据，在某些情况下，还可访问旨在降低无意删除风险的特定产品功能（例如，Exchange 恢复的项目文件夹），产品文档对此进行了详细介绍。 <br><br> 除免费试用版和领英服务外，如果客户订阅到期或终止，帐户功能将受到限制，Microsoft 会将该帐户存储在该联机服务中的客户数据保留 90 天，便于客户提取数据。 90 天保留期结束后，Microsoft 将禁用客户帐户并删除客户数据。 <br><br> **服务生成的数据：** 在收集后，此数据的默认保留期限为长达 180 天，为了确保服务的安全性或履行法律或监管义务，可能会将该数据保留更长时间。 <br><br> 如需进一步了解可让客户随时删除在服务中维护的个人数据的服务功能，请参阅 [Office 365 数据主体请求指南](https://docs.microsoft.com/microsoft-365/compliance/gdpr-data-subject-requests?toc=/microsoft-365/enterprise/toc.json)。|
| 个人数据的位置和传输 | 如联机服务条款附件 1 所述，如果客户在澳大利亚、加拿大、欧盟、法国、印度、日本、韩国、英国或美国配置 Office 365 实例，Microsoft 将仅在该位置存储以下静态客户数据：(1) Exchange Online 邮箱内容（电子邮件正文、日历条目和电子邮件附件的内容）；(2) SharePoint Online 网站内容和该网站中存储的文件；(3) 上传到 OneDrive for Business 的文件；以及 (4) 上传到 Project Online 的项目内容。 <br><br> 对于来自欧洲经济区和瑞士的其他类型的个人数据，Microsoft 将确保在向第三方国家/地区或国际组织传输的个人数据时实施 GDPR 第 46 条中规定的相应安全措施。除 Microsoft 根据处理者标准合同条款和其他模板合同所做的承诺外，Microsoft 还获得了欧盟-美国和瑞士-美国隐私防护框架认证并践行其承诺。 |
| 与第三方下级处理者分享的数据 | Microsoft 会与充当下级处理者角色的第三方分享数据，以实现客户和技术支持、服务维护和其他操作。 Microsoft 将向其传输客户数据、支持数据或个人数据的任何分包商都会与 Microsoft 签订书面协议，该协议的效力不低于[联机服务条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)中的数据保护条款。 与其分享来自 Microsoft 核心联机服务的客户数据的所有第三方下级处理者都包含在[联机服务分包商列表](https://aka.ms/Online_Serv_Subcontractor_List)中。 可以访问支持数据的所有第三方下级处理者（包括客户在其支持互动期间选择共享的客户数据）都包含在 [Microsoft 商业支持承包商列表](https://aka.ms/servicesapprovedsuppliers)中。 |
| 与独立第三方分享的数据 | 某些 Office 365 产品包含扩展性选项，可根据控制者的选择与独立第三方共享数据。  例如，Exchange Online 是一种可扩展的平台，它允许第三方加载项或连接器与 Outlook 集成并扩展 Outlook 的功能集。 这些加载项或连接器的第三方提供商独立于 Microsoft，并且必须由使用其加载项或连接器帐户进行身份验证的用户或企业管理员来启用。 <br><br> 除非法律要求，否则 Microsoft 不会向执法部门公开客户数据或支持数据。如果执法部门联系 Microsoft 要求提供客户数据或支持数据，Microsoft 将尝试重定向执法部门，直接从客户处请求该数据。如果必须向执法部门公开客户数据或支持数据，Microsoft 将立即通知客户并提供所需副本（除非法律禁止这样做）。 <br><br> 收到其他任何第三方对客户数据或支持数据的请求后，Microsoft 将立即通知客户（除非法律严禁这样做）。除非法律要求配合，否则 Microsoft 将拒绝请求。如果请求有效，Microsoft 将尝试重定向第三方，直接从客户处请求该数据。 |
| 数据主体权利 | 当以处理者的身份操作时，Microsoft 向客户（即数据控制者）提供其数据使用者的个人数据以及依据 GDPR 行使权力时满足数据使用者请求的能力。 我们以与产品功能和我们作为处理者的角色一致的方式完成此操作。如果我们收到来自客户数据使用者的请求，请求依据 GDPR 行使其一项或多项权力，我们将重定向数据使用者，使其直接向数据控制者提出请求。 Office 365 数据主体请求指南向数据控制者介绍了如何使用 Office 365 中的功能来支持数据主体权限。 <br><br> 对于为支持合法业务流程而处理的个人数据，来自需要依据 GDPR 行使权力的数据主体的请求应定向到 Microsoft，如 [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)中所述。 <br><br> Microsoft 在将个人数据用于我们的合法业务运营之前通常会对其进行汇总处理，并且无法在汇总中识别特定个人的个人数据。 这将极大地降低个人的隐私风险。  如果 Microsoft 不能识别个人身份，它将无法支持数据主体的访问权、擦除权、可移植权或对处理的限制权或反对权。 |
| 对与处理操作的目的相关的必要性和合理性的评估 | 这种评估将取决于控制者的处理需求和目的。 <br><br> 为了向数据控制者提供服务，Microsoft 需要进行某些处理，此类是必要且合理的。 |
| 对数据使用者的权力和自由带来的风险的评估 | 使用 Office 365 对数据使用者的权力和自由带来的关键风险取决于数据控制者实施、配置和使用它的方式和背景。 <br><br> Microsoft 将采取相关措施来支持提供服务，例如对用于支持其合法业务运营的个人数据进行匿名化或汇总处理，以便最大程度地降低对使用该服务的数据主体进行此类处理的风险。 <br><br> 然而，与其他所有服务一样，该服务中保存的个人数据也可能存在未经授权访问或意外泄露的风险。 OTS 中介绍了 Microsoft 为应对此类风险而采取的措施，详见本文后面的详细信息。 |
| 应对风险的措施（包括保护措施、安全措施和机制），以确保对个人数据的保护并证明符合此 GDPR 的规定（将数据使用者和其他相关人员的合法权益考虑在内）。 | Microsoft 致力于帮助保护客户的信息安全。 按照 GDPR 第 32 条的规定，Microsoft 已采取并且将维持和遵循适当的技术和组织措施，这些措施旨在防止客户数据和支持数据意外泄露、未经授权或非法访问、公开、篡改、丢失或损坏。 <br><br> 此外，Microsoft 履行 GDPR 规定的适用于数据处理者的所有其他义务，包括但不限于数据保护影响评估和记录保存。 <br><br> 当 Microsoft 为其合法业务运营处理个人数据时，它将履行适用于数据控制者的 GDPR 义务。 |

## <a name="part-3-dpias-are-hard-but-this-may-help"></a>第 3 部分： DPIA 很难，但可能有所帮助

如果你确定组织需要起草 DPIA，则本节中的信息旨在帮助你简化该流程。

本节内容：

- 提供与 Office 365 和特定于产品的信息相关的服务元素，以及
- 提供空白模型 DPIA 模板供你下载、修改和使用，以便起草你自己的 DPIA。 

### <a name="dpia-service-elements-matrix"></a>DPIA 服务元素矩阵

[DPIA 服务元素矩阵](../downloads/dpia-service-elements-matrix-final-10-2020.xlsx)是一个内容组织，你在开始记录 DPIA 时可能会发现它有所帮助。 它是按服务组织的，并且提供了特定于产品的信息和文档链接，可以帮助你更轻松地为所需的 DPIA 元素起草响应性答案。

### <a name="customizable-dpia-document"></a>可自定义的 DPIA 文档

我们意识到，起草 DPIA 可能是一项耗时的工作。 尽管每个客户的 DPIA 因各个组织配置和使用 Office 365 的方式而异，但是以下文档可以为你节省时间。 你可以下载[可自定义的 DPIA 文档](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/customizable-dpia-document-final-10-2020.docx)作为可修改的说明性模板，以便快速上手。 你可以免费使用，并根据具体实施情况调整服务。 本文档不应被解释为 Microsoft 或其任何附属机构提供的法律意见。 如果你对 DPIA 的起草流程有任何疑问，建议咨询你的律师。

## <a name="learn-more"></a>了解详细信息

- [Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
