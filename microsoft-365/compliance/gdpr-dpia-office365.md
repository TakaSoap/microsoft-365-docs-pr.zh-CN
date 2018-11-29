---
title: 使用 Office 365 的数据控制器的指南
description: 本文档提供相关信息将帮助他们以确定是否需要 DPIA 的专业服务以及要包含的详细信息的数据控制器。
keywords: DPIA，Office 365 中，Microsoft 365 文档 GDPR
author: BrendaCarter
ms.localizationpriority: high
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
manager: laurawi
ms.collection: GDPR
ms.openlocfilehash: 4b96a80d0817a180d9a1400fa347d5345ecdec74
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866026"
---
# <a name="data-protection-impact-assessments-guidance-for-data-controllers-using-microsoft-office-365"></a>使用 Microsoft Office 365 的数据控制器的数据保护影响评估： 指南 

下常规数据保护法规 (GDPR)，数据控制器所需准备数据保护影响评估 (DPIA) 处理操作的"可能会导致高风险的权限和自然的人员的 freedoms。"没有任何固有一定将由数据控制器使用它需要的 DPIA 创建的 Microsoft Office 365 中。 而是 DPIA 是否需要将依赖的详细信息和上下文数据控制器部署、 配置和使用 Office 365。

本文档旨在提供数据控制器信息将帮助他们以确定是否需要 DPIA 的 Office 365，如果是这样，什么详细包括。它适用于 Office 365 应用程序和服务，包括但不是限于 Exchange Online、 SharePoint Online 的 OneDrive for Business，Yammer for Business 和 Power BI Skype。 （请参阅，如表 1 和 2 的 Office 365 数据主题请求的指南。） 
 
### <a name="part-1--determining-whether-a-dpia-is-needed"></a>第 1 部分 - 确定是否需要 DPIA 

文章 35 的 GDPR 需要创建数据保护影响评估"[w] 下面一种尤其要指出的处理使用新技术，并考虑的性质，范围、 上下文和处理的目的是可能导致数据控制器在高风险的权限和自然的人员的 freedoms。"将进一步设置出特定将指示此类高风险下, 表中讨论的因素。在确定是否需要 DPIA，数据控制器应考虑这些因素，以及其他相关因素，全国控制器的特定实现和 Office 365 use(s)。


***表 1-风险因素和 Office 365 的相关信息***

<!--start table here HEADER -->

|||
|:-----|:-----|:-----|
|**风险因素**|**关于 Office 365 的相关信息**|
|与自然人员相关的个人方面其上自动处理，包括分析，且的决策基于产生有关自然的人员的法律效果所基于的系统和大量评估或同样显著影响的自然的人员 |根据数据控制器的配置，Office 365 可能执行数据，如分析允许数据控制器派生见解上如何人员协作中的工作区分析执行某些自动的处理基于从用户的邮箱的电子邮件和日历标头信息的组织。<p>Office 365 旨在不执行自动处理作为决策产生法律或同样重大影响个人的基础。但是，Office 365 是高度自定义服务，因为数据控制器无法可能将其用于这类处理。</p>|
|特殊类别的数据 （个人数据显示关于或种族、 政治观点、 宗教或理论信仰，或交易联合成员资格和遗传数据，为了生物数据处理大型 scale1 上的处理用于唯一地标识自然的人员、 与有关运行状况数据或与有关自然人员的性别生命或性方向数据），或与刑事定罪和分子相关的个人数据 |Office 365 不专门处理的个人数据的特殊类别。<p>但是，数据控制器可以使用 Office 365 来处理数据枚举特殊类别。Office 365 是高度自定义服务，使客户能够跟踪或其他方式的处理任何类型的个人数据，包括特殊类别的个人数据。相关的控制器确定是否需要 DPIA 到任何此类使用。但为数据处理器，Microsoft 具有不能控制此类使用，并且通常会小或无深入此类使用。</p>|
|在大型刻度 * 特殊类别的数据 （个人数据显示关于或种族、 政治观点、 宗教或理论信仰，或交易联合成员资格和处理遗传数据，为了生物数据处理用于唯一地标识自然的人员、 与有关运行状况数据或与有关自然人员的性别生命或性方向数据），或与刑事定罪和分子相关的个人数据 |Office 365 不专门处理的个人数据的特殊类别。<p>但是，数据控制器可以使用 Office 365 来处理数据枚举特殊类别。Office 365 是高度自定义服务，使客户能够跟踪或其他方式的处理任何类型的个人数据，包括特殊类别的个人数据。相关的控制器确定是否需要 DPIA 到任何此类使用。但为数据处理器，Microsoft 具有不能控制此类使用，并且通常会小或无深入此类使用。</p>|
|大规模系统化监视公开可访问区域|Office 365 不旨在召开或加快此类监控。<p>但是，数据控制器无法使用它处理通过这种监控收集数据</p>|
|||

<!-- end of table -->[*]对于处理位于"大型"的条件，Recital 91 的 GDPR 阐明:"个人数据处理不应考虑为大规模上，如果处理涉及患者或通过客户端中的个人数据单个医生、 其他保健 professional 或律师。在这种情况下，数据保护影响评估不应为必需。"

### <a name="part-2--contents-of-a-dpia"></a>第 2 部分 - DPIA 的内容 
文章 35(7) 规定数据保护影响评估指定处理的目的和系统化预想处理的说明。 Microsoft 的 DPIAs 中此类系统性说明包括因素，如类型的数据处理、 保留数据多长时间，位于数据并将数据传输，和哪些第三方可能有权访问数据。 此外，DPIA 必须包括： 
- 对与处理操作的目的相关的必要性和合理性的评估；  
- 对自然人的权力和自由带来的风险的评估；以及  
- 应对风险的措施（包括保护措施、安全措施和机制），以确保对个人数据的保护并证明符合此条例的规定（将数据使用者和其他相关人员的合法权益考虑在内）。 

下表提供可帮助进行 DPIA 绘制的 microsoft 关键信息。它包含有关与每个 DPIA 的必需元素相关的 Office 365 的信息。 第 1 部分，与数据控制器必须考虑下面提供以及其自己的特定实现的详细信息和 use(s) 的 Office 365 的详细信息。

***表 2-的元素和有关 Office 365 的相关因素***

<!--start table here HEADER -->

|||
|:-----|:-----|
|**风险因素**|**关于 Office 365 的相关信息**|
|处理目的|由实现，配置，然后使用它的控制器确定处理使用 Office 365 的数据如下。<p>由[联机服务条款](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)，Microsoft，作为数据处理器，处理客户数据只是为了提供给我们的客户数据控制器，包括与提供这些服务兼容的目的的请求的服务。Microsoft 不会使用客户数据或任何广告或类似的与商业目的派生的信息。</p>|
|处理的个人数据类别|[客户数据]<br>这是所有数据，包括文本、 声音、 视频或图像文件和软件，客户提供给 Microsoft 或都不提供通过他们的 Microsoft online services 使用的客户的代表。它包括客户上载存储或处理，以及自定义项的数据。处理 Office 365 中的客户数据的示例包括电子邮件内容在 Exchange Online，并且文档或文件存储在 SharePoint Online 或 OneDrive for Business。<p>[系统生成的日志数据]<br>这是 Microsoft 将生成运行该服务，如使用或性能数据的数据。这些数据的大多数包含由 Microsoft 生成的 pseudonymous 标识符。<p>[支持数据]<br>这是通过或代表客户向 Microsoft 提供的数据 （或该客户授予 Microsoft 从联机服务获取） 通过与 Microsoft 合作，以获取对联机服务的技术支持。</p><p>客户数据、 系统生成的日志数据以及支持数据，不包括管理员和帐单数据，如客户管理员联系信息、 订阅信息和付款数据，这 Microsoft 收集并处理中作为其容量数据控制器和这是本文档的范围之外。</p>|
|数据保留|[客户数据]<br>在联机服务条款中的数据保护条款出设置，Microsoft 将保留客户数据的持续时间的客户的右侧，以使用服务和所有客户数据直到被删除或返回根据客户的说明或Online Services 术语的词。<p>根本时间期间的客户的订阅的术语客户将能够访问、 提取，并删除存储在服务中的客户数据，在某些情况下，特定产品功能的主题应缓解可以防止由于无意的风险删除 （例如，Exchange 已恢复的项目文件夹），为进一步产品文档中所述。</p><p>除免费试用版和 LinkedIn 服务，Microsoft 将保留客户数据存储在联机服务中的有限的功能帐户 90 天后到期或终止客户的订阅，以便客户可能提取数据。90 天保留期结束后，Microsoft 将禁用客户的帐户，并删除客户数据。</p><p>[系统生成的日志数据]<br>此数据保留为默认期间的最多 180 天从受到更长时间保留期的集合，其中所需的安全的服务或以满足法律或法规义务。</p><p>使客户可以删除任何时候维护服务中的个人数据的服务功能的详细信息，请参阅[Office 365 数据主题请求指南 》](https://docs.microsoft.com/microsoft-365/compliance/gdpr-data-subject-requests?toc=/microsoft-365/enterprise/toc.json)。|
|个人数据的位置和传输|Microsoft 中所述数据保护使用条款联机服务条款，如果客户设置 Office 365 中澳大利亚、 加拿大、 欧盟、 法国、 印度、 日本、 韩国、 英国或美国其实例，将存储在仅中该位置的 rest 关注客户数据: （1) Exchange Online 邮箱内容 （电子邮件正文、 日历项和电子邮件附件的内容）、 （2) SharePoint Online 网站内容和网站，（3） 文件上载到的文件存储中OneDrive for Business，和 (4) 项目内容上载到 Project Online。<p>有关其他类型的个人数据从欧洲经济区和瑞士，Microsoft 将确保的传输的个人数据到第三个国家/地区和国际组织会受到相应的保护措施的 GDPR 文章 46 中所述。在标准合同子句的处理器和其他模型合同下的 Microsoft 承诺，除了 Microsoft 认证欧盟美国和瑞士美国隐私盾牌 Framework 以及它们所需要的承诺。</p>|
|与第三方 subprocessors 共享的数据|Microsoft 与第三方充当我们 subprocessors 为支持函数，如客户和技术支持、 服务维护和其他操作共享数据。Microsoft 将客户数据或支持数据传输到任何分包将输入到与 Microsoft 书面协议的任何较少保护比[联机服务条款](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)的数据保护条款。所有第三方 subprocessors 与其共享从 Microsoft 的核心联机服务的客户数据都包含在[联机服务转包列表](https://aka.ms/Online_Serv_Subcontractor_List)中。可以访问支持的数据 （包括客户选择对其支持交互期间共享的客户数据） 的所有第三方 subprocessors 都包含在[Microsoft 商业支持承包商列表](http://aka.ms/servicesapprovedsuppliers)中。 |
|数据共享与独立的第三方|某些 Office 365 产品包含的扩展性选项会启用，请在控制器的选举与独立的第三方共享数据。 例如，Exchange Online 是一个可扩展的平台，允许第三方外接程序或连接器将与 Outlook 集成和扩展 Outlook 的功能集。这些第三方提供程序加载项或连接器的行动独立于 Microsoft，必须由企业管理员，负责对其外接程序或连接器帐户进行身份验证的用户启用其外接程序或连接器。<p>Microsoft 将不泄露客户数据或支持数据到法律强制实施除非法律要求。如果法律强制实施联系 Microsoft 与客户数据或支持数据的请求，Microsoft 将尝试重定向法律管制局，直接从客户请求的数据。如果强迫告知法律强制实施客户数据或支持数据，Microsoft 将立即通知客户，并提供一份需求，除非法律禁止从这样做。</p><p>收到其他任何第三方对客户数据或支持数据的请求后，Microsoft 将立即通知客户（除非法律严禁这样做）。除非法律要求配合，否则 Microsoft 将拒绝请求。如果请求有效，Microsoft 将尝试重定向第三方，直接从客户处请求该数据。</p>|
|数据使用者权力|作为处理器运行时, Microsoft 可向客户 （数据控制器） 及其数据主题以及满足数据主题请求时它们执行 GDPR 其权利的功能的个人数据。我们执行以便产品和为处理器。 我们角色的功能一致的方式如果我们收到请求来自客户的数据主题，若要实际使用一个或多个 GDPR，其权利我们请求重定向受到生成数据其直接向 the 数据控制器。<p>[Office 365 数据主题请求指南](https://docs.microsoft.com/microsoft-365/compliance/gdpr-data-subject-requests?toc=/microsoft-365/enterprise/toc.json)提供有关如何支持在 Office 365 中使用的功能的数据主题权限对数据控制器的说明。</p>|
|对与处理操作的目的相关的必要性和合理性的评估|这种评估将取决于控制者的处理需求和目的。<p>在由 Microsoft 执行的处理，这类处理是必要和以提供到数据控制器服务成比例。</p>|
|对数据使用者的权力和自由带来的风险的评估|从 Office 365 使用的权限和数据主题 freedoms 关键风险将如何和的上下文数据控制器实现，配置，然后使用它的一项功能。<p>然而，与其他所有服务一样，该服务中保存的个人数据可能存在未经授权的访问或意外泄漏的风险。下面介绍 Microsoft 所采取的用来应对此类风险的措施。</p>|
|应对风险的措施（包括保护措施、安全措施和机制），以确保对个人数据的保护并证明符合此 GDPR 的规定（将数据使用者和其他相关人员的合法权益考虑在内）。|Microsoft 致力于帮助保护客户的信息安全。按照 GDPR 第 32 条的规定，Microsoft 已采取并且将维持和遵循适当的技术和组织措施，这些措施旨在防止客户数据和支持数据意外泄露、未经授权或非法访问、公开、篡改、丢失或损坏。<p>此外，Microsoft 履行 GDPR 规定的适用于数据处理者的所有其他义务，包括但不限于数据保护影响评估和记录保存。</p>|
|||

<!-- end of table -->

#### <a name="learn-more"></a>了解详细信息
[Microsoft 信任中心](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)