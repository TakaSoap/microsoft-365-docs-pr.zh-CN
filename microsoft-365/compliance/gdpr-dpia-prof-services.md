---
title: 使用 Microsoft 专业服务的数据控制器的指南
description: 本文档提供相关信息将帮助他们以确定是否需要 DPIA 的专业服务以及要包含的详细信息的数据控制器。
keywords: DPIA，Microsoft 专业服务，Microsoft 365 文档 GDPR
robots: NOINDEX,NOFOLLOW
author: BrendaCarter
ms.localizationpriority: Priority
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
manager: laurawi
ms.collection: GDPR
ms.openlocfilehash: 316f780fc324f95783416c52070b38c12d5078af
ms.sourcegitcommit: 73fb9a7cf1b7b1045a304391ed393acb7b909317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2018
ms.locfileid: "26865656"
---
# <a name="data-protection-impact-assessments-guidance-for-data-controllers-using-microsoft-professional-services"></a>使用 Microsoft 专业服务的数据控制器的数据保护影响评估： 指南

## <a name="introduction-to-microsoft-professional-services"></a>Microsoft 专业服务简介

Microsoft 专业服务包括不同组技术架构师、 工程师、 顾问和专用于助客户的 Microsoft 的使命上提供的技术支持人员执行操作的详细信息和实现的详细信息。在此处查找有关 Microsoft 专业服务的更多信息 (<https://www.microsoft.com/microsoftservices/professional_services.aspx>) 并转到 Microsoft 专业服务部分中，Microsoft 信任中心上 (<https://www.microsoft.com/trustcenter/cloudservices/commercialsupport>)。

Microsoft 专业服务认真地考虑其义务下常规数据保护法规 (GDPR)。本文档中的信息旨在提供有关如何信息 Microsoft 的支持和咨询客户可以使用下 GDPR 准备数据保护影响评估 (DPIAs) 时的产品。

### <a name="introduction-to-dpias"></a>DPIAs 简介

下常规数据保护法规 (GDPR)，数据控制器所需准备 DPIA 处理操作的"可能会导致高风险的权限和自然的人员的 freedoms。"没有任何固有一定将由数据控制器使用它需要的 DPIA 创建的 Microsoft 专业服务中。而是 DPIA 是否需要将依赖的详细信息和的类型的服务和数据控制器如何使用专业服务上下文。

本文档旨在提供信息将帮助他们来确定是否需要 DPIA，如果是这样，什么详细要包含的专业服务数据控制器。

## <a name="part-1--determining-whether-a-dpia-is-needed"></a>第 1 部分 - 确定是否需要 DPIA

文章 35 的 GDPR 需要创建数据保护影响评估"[w] 下面一种尤其要指出的处理使用新技术，并考虑的性质，范围、 上下文和处理的目的是可能导致数据控制器在高风险的权限和自然的人员的 freedoms。"将进一步设置出特定将指示此类高风险下, 表中讨论的因素。在确定是否需要 DPIA，数据控制器应考虑这些因素，以及其他相关因素，全国数据控制器的特定实现和 use(s) 的专业服务。

***表 1-风险因素和相关信息***

<!--start table here NO HEADER -->

|||
|:-----|:-----|
|**风险因素**|**专业服务的相关信息**|
|基于自动化处理对自然人的私人方面进行系统全面的评估（包括剖析以及会对自然人产生法律效应或显著影响自然人的决策）；|专业服务并执行某些例程或自动处理数据，如中断/修复支持 （例如，提供协助客户其计算机中断时），帐户迁移和分析系统漏洞。专业服务解决方案，不包括客户开发涵盖下的注意，并不旨在执行处理上的决策基于产生对个人的法律或同样重大影响。|
|处理大量[^1]特殊类别的数据，如种族或族裔、政治观点、宗教或哲学信仰、工会成员身份、基因数据、用于唯一标识自然人的生物识别数据、关于自然人性生活健康或性取向数据的数据，或与刑事犯罪和违法行为相关的个人数据；|专业服务都不适用于占用需要处理的个人数据，特殊类别的工作中排除客户开发属于下面的注释。<p>但是，数据控制器可以使用咨询解决方案的专业服务来处理数据枚举特殊类别。例如，专业服务提供医疗保健行业数据库开发数据控制器无法用于处理个人健康状况相关联的数据。它是控制器评估的责任和限制或文档根据该用法。</p>|
| 大规模系统化监视公开可访问区域|专业服务并不旨在利用需要或方便了此类监控工作中，不包括客户开发属于下面的注释。<p>如果数据控制器专业服务用于开发系统此类型或 IT 系统用于处理通过这种监控比收集数据它将为的数据控制器责任，如下所述。</p>|
|||

<!-- end of table -->
  
[自定义开发的注释]专业服务提供了多种咨询解决方案。数据控制器可能无法请求的解决方案按照上述条件，将为高风险的解决方案。例如，数据控制器可能会请求专业服务创建的解决方案开发的雇用决策的业务智能引擎或信用卡应用程序或解决方案涉及用户跟踪，专门的使用 Artificial智能 (AI) / 分析或特殊类别的个人数据的处理。

协定开头，专业服务具有流程评估和它可能会要求从事的地址高风险解决方案。作为的这一部分，专业服务可能需要开发 DPIA 或其他条件 （例如商定操作指南） 所需的数据处理器下 GDPR 来自 GDPR 合规性 （例如合同条款） 上的数据控制器、 计划担保。但是，Microsoft 的操作无论它是数据控制器 （如果适用） 的客户数据的处理器从开发使用 input DPIA 的责任。

## <a name="part-2--contents-of-a-dpia"></a>第 2 部分 - DPIA 的内容

第 35(7) 条规定，数据保护影响评估应指定处理的目的和预期处理的系统化说明。综合 DPIA 的系统化说明可能包括所处理数据的类型、数据保留时间、数据存储位置和传输位置以及有权访问数据的第三方等因素。此外，DPIA 还必须包括：

-   对与处理操作的目的相关的必要性和合理性的评估；

-   对自然人的权力和自由带来的风险的评估；以及

-   应对风险的措施（包括保护措施、安全措施和机制），以确保对个人数据的保护并证明符合此条例的规定（将数据使用者和其他相关人员的合法权益考虑在内）。

下表包含与每个这些元素相关的专业服务的信息。第 1 部分，与数据控制器必须考虑下面，以及其他相关因素，控制器的特定实现的上下文和 use(s) 的专业服务中提供的详细信息。

***表 2-DPIA 相关的专业服务的元素***

<!--start table here -->

|||
|:-----|:-----|
|**DPIA 的元素** |**专业服务的相关信息**|
|处理目的|由实现，配置，然后使用它的控制器确定处理使用专业服务的数据如下。<p>为指定的[Microsoft 专业服务数据保护附录](http://aka.ms/professionalservicesdpa)(MPSDPA)，Microsoft，作为数据处理器，处理支持和咨询数据只是为了给我们的客户数据控制器提供请求的服务。Microsoft 不会使用支持和咨询的数据或任何广告或类似的与商业目的派生的信息。</p>|
|由实现，配置，然后使用它的控制器确定处理使用专业服务的数据如下。|为指定的[Microsoft 专业服务数据保护附录](http://aka.ms/professionalservicesdpa)(MPSDPA)，Microsoft，作为数据处理器，处理支持和咨询数据只是为了给我们的客户数据控制器提供请求的服务。Microsoft 不会使用支持和咨询的数据或任何广告或类似的与商业目的派生的信息。|
|处理的个人数据类别|支持和咨询的数据意味着所有数据，包括通过提供服务的所有文本、 声音、 视频、 图像文件或软件，或代表，客户向 Microsoft 提供的 （或客户授予 Microsoft 从联机服务获取）若要获取专业服务或支持的 Microsoft。这可能包括电话、 聊天、 电子邮件或 web 窗体上收集的信息。它可能包括问题，向 Microsoft 来解决支持问题，自动疑难解答，或通过访问远程具有客户权限客户系统传输的文件的说明。<p>客户数据以及支持数据不包括客户联系人或帐单数据，如订阅信息和付款数据，以及哪些 Microsoft 收集并在其容量 as 数据控制器处理这是本文档的范围之外。</p>|
|数据保留|Microsoft 客户服务以及以确保质量所需的工作效率结束后保留期的持续时间和服务的连续性的支持和咨询的数据将保留。例如，支持案例关闭数据后是数据通常保留一段，以确保能够引用该如果重新出现问题，并重新打开这种情况。<p>专业服务提供支持时, 支持案例关闭时定义的工作效率长度。当专业服务提供咨询服务时，服务期限通常由工作订单定义。在其他情况下，由业务关系的维护定义的工作效率长度。在所有情况下，支持和咨询的数据将删除或返回没有过度使用专业服务*数据主题权限指南*中所述的功能的延迟的请求或根据客户的说明。</p>|
|个人数据的位置和传输|专业服务，包括需要提供全天候支持的性质可能世界各地传输数据。可请求 Microsoft 运行中的位置的列表。对于咨询服务，如果同意中的工作顺序，可能会保存数据中-国家/地区。<p>有关在欧洲经济区瑞士、 Microsoft 个人数据将确保的传输的个人数据到第三个国家/地区和国际组织会受到相应的保护措施的 GDPR 文章 46 中所述。在标准合同子句的处理器和[MPSDPA](http://aka.ms/professionalservicesdpa)中所述其他模型合同下的 Microsoft 的承诺，除了 Microsoft 认证欧盟美国和瑞士美国隐私盾牌框架和承诺它们伴有。|
|与第三方分享的数据|Microsoft 与第三方充当我们子处理器支持函数，如客户和技术支持、 服务维护和其他操作共享数据。Microsoft 将支持和咨询的数据传输到任何分包将输入到的数据保护使用条款[MPSDPA](http://aka.ms/professionalservicesdpa)比没有较少保护与 Microsoft 的编写协议。所有第三方子处理器与下[MPSDPA](http://aka.ms/professionalservicesdpa)共享的支持和咨询数据都包含在[Microsoft 商业支持承包商列表](http://aka.ms/servicesapprovedsuppliers)。<p>Microsoft 将不支持和咨询的数据向披露法律强制实施除非法律要求。如果法律强制实施联系 Microsoft 支持和咨询的数据需求，Microsoft 将尝试重定向法律管制局，直接从客户请求的数据。如果强迫披露给法律强制实施的支持和咨询的数据，Microsoft 将立即通知客户，并提供一份需求，除非法律禁止从这样做。<p>收到的支持和咨询的数据的任何其他第三方请求 Microsoft 及时将通知客户，除非法律禁止。Microsoft 将拒绝该请求，除非符合法律要求。如果该请求是有效的 Microsoft 将尝试重定向第三方请求直接从客户的数据。</p>|
|数据使用者权力|作为处理器运行时, Microsoft 可向客户 （数据控制器） 及其数据主题以及满足数据主题请求时它们执行 GDPR 其权利的功能的个人数据。我们执行以便产品和为处理器。 我们角色的功能一致的方式如果我们收到请求来自受练习一个或多个下 GDPR，其权限的客户数据我们请求重定向受到生成数据其直接向 数据控制器。<p>*专业的服务已由数据主题请求的 GDPR 文档*提供客户可以如何解决其数据主题权限义务专业服务中的说明。</p>|
对与处理操作的目的相关的必要性和合理性的评估|这种评估将取决于控制者的处理需求和目的。<p>在由 Microsoft 执行的处理，这类处理是必要和以提供到数据控制器服务成比例。Microsoft 承诺这[MPSDPA](http://aka.ms/professionalservicesdpa)中。</p>|
|对数据使用者的权力和自由带来的风险的评估|权限和数据主题 freedoms 因专业服务使用的关键风险将操作以及哪些上下文数据控制器实现、 配置，并使用专业服务和任何由专业人员提供的解决方案中的函数服务。<p>然而，与其他所有服务一样，该服务中保存的个人数据可能存在未经授权的访问或意外泄漏的风险。下面介绍 Microsoft 所采取的用来应对此类风险的措施。</p>|
| 应对风险的措施（包括保护措施、安全措施和机制），以确保对个人数据的保护并证明符合此 GDPR 的规定（将数据使用者和其他相关人员的合法权益考虑在内）。<!--is this the correct ending? -->|Microsoft 致力于保护客户信息的安全性。依照的 GDPR 文章 32 的规定，Microsoft 已实现将维护和按照相应的技术和组织度量值用于保护支持和针对意外、 未经授权或非法咨询数据访问、 泄露，篡改、 丢失或破坏。<p>此外，Microsoft 履行 GDPR 规定的适用于数据处理者的所有其他义务，包括但不限于数据保护影响评估和记录保存。</p>|
|||

<!-- end of table -->

[^1]: With respect to the criteria that the processing be on a “large scale,” Recital 91 of the GDPR clarifies that: “The processing of personal data should not be considered to be on a large scale if the processing concerns personal data from patients or clients by an individual physician, other health care professional or lawyer. In such cases, a data protection impact assessment should not be mandatory.”


#### <a name="learn-more"></a>了解详细信息
[Microsoft 信任中心](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)