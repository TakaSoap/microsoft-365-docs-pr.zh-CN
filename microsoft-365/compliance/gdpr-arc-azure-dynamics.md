---
title: 适用于 GDPR 的 Azure 和 Dynamics 365 责任就绪清单
description: 使用 Microsoft Azure 时，提供访问支持 GDPR 需要的信息的便捷方式。
keywords: ARC Azure, Microsoft 365, Microsoft 365 教育版, Microsoft 365 文档, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dd94ab9bfcc4ca1c9e8f6b99364fa99dde5ff644
ms.sourcegitcommit: 22fd8517707ed3ab6ef996247ad2aa372535ee56
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46815254"
---
# <a name="azure-and-dynamics-365-accountability-readiness-checklist-for-the-gdpr"></a>适用于 GDPR 的 Azure 和 Dynamics 365 责任就绪清单

## <a name="1-introduction"></a>1. 简介

这些责任就绪清单提供了在使用 Microsoft Azure 和 Dynamics 365 时，访问支持一般数据保护条例 (GDPR) 时可能需要的信息的便捷方式。 此清单是根据以下标准中规定的一组用于个人数据处理器的隐私和安全控制的标题和参考编号（位于每个清单主题的括号中）进行组织：

- [ISO/IEC 27701](https://shop.bsigroup.com/ProductDetail/?pid=000000000030351736) 安全技术要求。
- [ISO/IEC 27001](https://shop.bsigroup.com/ProductDetail?pid=000000000030347472) 隐私管理要求。

可以使用合规性分数 [[16](gdpr-arc-Azure.md#16)] 来管理此清单中的项目，具体方法是引用 GDPR 磁贴中的“客户托管控件”下的控件 ID 和控件标题。 此控件结构还用于组织 Microsoft Azure 和 Dynamics 365 为支持 GDPR 而实现的内部控件的演示文稿（可从[服务信任门户](https://servicetrust.microsoft.com/ViewPage/TrustDocuments)下载）。

此控件结构还将用于组织[Microsoft Dynamics 365 用于支持 GDPR 所实施的内部控件](https://aka.ms/gdprcontrols)的演示文稿。

有关更多 GDPR 相关的文档，请访问 [https://aka.ms/gdprgetstarted](https://aka.ms/gdprgetstarted)。

## <a name="2-conditions-for-collection-and-processing"></a>2. 收集和处理的条件

|||||
|:----|:----|:-----|:-----|
|**类别**|**客户注意事项**|**支持 Microsoft 文档**|**引用 GDPR 文章**|
| ***确定法律依据 (7.2.2)*** | 客户应了解与处理过程的法律依据相关的任何要求，例如是否必须首先给予同意。 | Microsoft Azure 不直接支持征得用户许可。 Microsoft 服务如何处理个人数据的说明（将纳入你的责任文档）现在可用：<br>- *Azure 适用的客户数据保护影响评估关键信息* [[11](gdpr-arc-Azure.md#11)] <br>- *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)] | (5)(1)(a)、(6)(1)(a)、(6)(1)(b)、(6)(1)(c)、(6)(1)(d)、(6)(1)(e)、(6)(1)(f)、(6)(3)、(6)4)(a)、(6)(4)(b)、(6)(4)(c)、(6)(4)(d)、(6)(4)(e)、(8)(3)、(9)(1)、(9)(2)(b)、(9)(2)(c)、(9)(2)(d)、(9)(2)(e)、(9)(2)(f)、(9)(2)(g)、(9)(2)(h)、(9)(2)(i)、(9)(2)(j)、(9)(3)、(9)(4)、(10)、(17)(3)(a)、(17)(3)(b)、(17)(3)(c)、(17)(3)(d)、(17)(3)(e)、(18)(2)、(22)(2)(a)、(22)(2)(b)、(22)(2)(c)、(22)(4) |
| ***确定何时征得许可 (7.2.3)*** | 在处理个人数据（有需要的情况、处理类型超出要求范围等）之前，客户应了解征得个人同意的法律或法规要求，包括如何收集同意。 | Microsoft Azure 不直接支持征得用户许可。 | (8)(1)、(8)(2) |
| ***征得和记录许可 (7.2.4)*** | 当确定需要执行此操作时，客户应适当地征得同意。此外，客户还应该了解如何提出和收集征得同意的请求。 | Microsoft Azure 不直接支持征得用户许可。 | (7)(1)、(7)(2)、(9)(2)(a) |
| ***隐私影响评估 (7.2.5)*** | 客户应了解完成隐私影响评估的要求（何时执行、需要哪些类别的数据以及完成评估的时间）。 | 服务信任门户[数据保护影响评估 (DPIA) 页面](https://servicetrust.microsoft.com/ViewPage/GDPRDPIA)中介绍了 Microsoft 服务如何确定何时执行 DPIA，以及 Microsoft 的 DPIA 计划概述（包括涉及的 DPO）。若要获取 DPIA 方面的支持，请访问：<br>- *Azure 适用的客户数据保护影响评估关键信息* [[11](gdpr-arc-Azure.md#11)] <br> - *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)] | 文章 (35) |
| ***与 PII 处理者签订合同 (7.2.6)*** | 客户应确保其与处理者的合同包括帮助处理与处理和保护个人数据相关的任何相关法律或法规义务的要求。 | Microsoft 合同要求我们协助你履行 GDPR 规定的义务，包括支持数据主体权利。<br> 请参阅 *Microsoft Online Services 条款、数据保护条款，请参阅“处理个人数据”；GDPR* [[1](gdpr-arc-Azure.md#1)] | (5)(2)、(28)(3)(e)、(28)(9) |
| ***与处理 PII 有关的记录 (7.2.7)*** | 客户应保存与处理个人数据相关的所有必要和必需的记录（例如用途、安全措施等）。 如果某些记录必须由次级处理者提供，则客户应确保他们可以获取这些记录。 | Microsoft 服务提供的相关工具，有助于你维护必要记录来证明合规性以及支持履行 GDPR 规定的责任。 请参阅 *Azure 安全文档* [[2](gdpr-arc-Azure.md#2)]，了解[活动和诊断日志记录](https://docs.microsoft.com/azure/security/blueprints/fedramp-iaaswa-overview#logging-and-auditing)和记录*Dynamics 365 中的审核与报告* [[17](gdpr-arc-Azure.md#17)]中的个人数据处理。 | (5)(2)、(24)(1)、(30)(1)(a)、(30)(1)(b)、(30)(1)(c)、(30)(1)(d)、(30)(1)(g)、(30)(1)(f)、(30)(3)、(30)(4)、(30)(5) |

## <a name="3-rights-of-data-subjects"></a>3. 数据主体的权限

|||||
|:-----|:-----|:-----|:-----|
|**类别**|**客户注意事项**|**支持 Microsoft 文档**|**引用 GDPR 文章**|
|***确定 PII 主体的权限并启用练习 (7.3.1)***|客户应了解与处理其个人数据相关的个人权限的要求。 这些权限包括访问、更正和清除等。 如果客户使用第三方系统，他们应该确定系统中的哪些部分（如果存在）提供与使个人能够行使其权限（例如访问其数据）相关的工具。 系统提供这些功能时，客户应根据需要进行使用。|Microsoft 提供的功能，有助于你支持数据主体权利。 请参阅*符合 GDPR 的 Azure 数据主体请求* [[9](gdpr-arc-Azure.md#9)]、符合 GDPR 的 Dynamics 365 数据主体请求 [[10](gdpr-arc-Azure.md#10)]、 Microsoft Azure（全部）ISO/IEC 27001:2013 ISMS 适用性声明，请参阅 ISO/IEC 27018 管制 A.1.1。|(12)(2)|
|***确定 PII 主体（数据主体）的信息 (7.3.2)***|客户应了解有关可提供给个人的个人数据的处理的信息类型的要求。这可能包括如下类似信息：<br>- 有关控制者及其代表的联系人详细信息；<br>- 有关处理的信息（目的、国际传输和相关安全措施、保留时间等）；<br>- 主体如何访问和/或修改其个人数据的信息；请求清除或限制处理；接收其个人数据的副本，及其个人数据的可移植性<br>- 获取个人数据的来源和方法（如果不是从主体直接获取）<br>- 有关提起诉讼的权限和向谁提起诉讼的信息；<br>- 有关更正个人数据的信息；<br>- 组织不再如往常一样识别数据主体（PII 主体）的通知（如果处理不再需要识别数据主体）；<br>- 个人数据的传输和/或泄露；<br>- 是否仅根据个人数据自动处理来自动决策；<br>- 有关数据主体信息更新和提供的频率的信息（例如，“及时”通知、组织定义的频率等）<p>在客户使用第三方系统或处理器时，他们应确定其中的哪些信息（如果有）需要由他们提供，以确保他们可以从第三方获取所需的信息。</p>|可以在向数据主体提供的数据中添加的 Microsoft 服务相关信息。 请参阅*符合 GDPR 的 Azure 数据主体请求* [[9](gdpr-arc-Azure.md#9)]、*Azure 适用的客户数据保护影响评估关键信息* [[18](gdpr-arc-Azure.md#18)] 和*谁可以访问你的数据和所依据的条款* [[7](gdpr-arc-Azure.md#7)]。|(11)(2)、(13)(1)(a)、(13)(1)(b)、(13)(1)(c)、(13)(1)(d)、(13)(1)(e)、(13)(1)(f)、(13)(2)(c)、(13)(2)(d)、(13)(2)(e)、(13)(3)、(13)(4)、(14)(1)(a)、(14)(1)(b)、(14)(1)(c)、(14)(1)(d)、(14)(1)(e)、(14)(1)(f)、(14)(2)(b)、(14)(2)(e)、(14)(2)(f)、(14)(3)(a)、(14)(3)(b)、(14)(3)(c)、(14)(4)、(14)(5)(a)、(14)(5)(b)、(14)(5)(c)、(14)(5)(d)、(15)(1)(a)、(15)(1)(b)、(15)(1)(c)、(15)(1)(d)、(15)(1)(e)、(15)(1)(f)、(15)(1)(g)、(15)(1)(h)、(15)(2)、(18)(3)、(21)(4)|
|***向 PII 主体提供信息 (7.3.3)***|客户应遵守有关所需信息如何/何时/以何种形式向与处理其个人数据相关的个人提供的所有要求。 如果第三方提供所需信息，则客户应确保该信息符合 GDPR 要求的参数。|可以在向数据主体提供的数据中添加的 Microsoft 服务的模板化信息。 请参阅*符合 GDPR 的 Azure 数据主体请求* [[9](gdpr-arc-Azure.md#9)] 和 *Azure 适用的客户数据保护影响评估关键信息* [[11](gdpr-arc-Azure.md#11)]、*Dynamics 365 适用的客户数据保护影响评估关键信息* [[18](gdpr-arc-Azure.md#18)]。|(11)(2)、(12)(1)、(12)(7)、(13)(3)、(21)(4)|
|***提供修改或撤销同意的机制 (7.3.4)***|客户应了解通知用户有权访问、更正和/或清除其个人数据以及提供使他们可以执行上述操作的机制的要求。如果使用第三方系统并将此机制作为其功能的一部分提供，则客户应根据需要使用该功能。|可用于定义在请求征得许可时向数据主体提供的信息的 Microsoft 服务功能相关信息可用。<br>- *符合 GDPR 的 Azure 数据主体请求* [[9](gdpr-arc-Azure.md#9)] <br> - *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)]|(7)(3)、(13)(2)(c)、(14)(2)(d)、(18)(1)(a)、(18)(1)(b)、(18)(1)(c)、(18)(1)(d)|
|***提供反对处理机制 (7.3.5)***|客户应了解有关数据主体权限的要求。如果个人有权反对处，则客户应该通知他们，并且提供个人提出其异议的方式。|可以在向数据主体提供的数据中添加的、与要处理的对象相关的 Microsoft 服务相关信息。<br>- *符合 GDPR 的 Azure 数据主体请求* [[9](gdpr-arc-Azure.md#9)]，请参阅*第 4 步：限制* <br> - *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)]| (13)(2)(b)、(14)(2)(c)、(21)(1)、(21)(2)、(21)(3)、(21)(5)、(21)(6)|
|***PII 主体权利行使共享 (7.3.6)***|在行使个人权利（例如个人请求清除或修改等）的基础上，客户应了解在通知已与其共享个人数据的第三方数据修改实例方面存在的要求。|便于你发现与第三方共享的个人数据的 Microsoft 服务功能相关信息。<br>- *符合 GDPR 的 Azure 数据主体请求* [[9](gdpr-arc-Azure.md#9)] <br> - *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)]|(19)|
|***更正或清除 (7.3.7)***|客户应了解通知用户有权访问、更正和/或清除其个人数据以及提供使他们可以执行上述操作的机制的要求。如果使用第三方系统并将此机制作为其功能的一部分提供，则客户应根据需要使用该功能。|有关向数据主体所提供的数据中可以包含的与其访问、更正或清除个人数据的功能相关的 Microsoft 服务的模板化信息。<br>-*符合 GDPR 的 Azure 数据主体请求* [[9](gdpr-arc-Azure.md#9)]，请参阅“第 5 步：删除”<br> - *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)] 参见“删除”。 | (5)(1)(d)、(13)(2)(b)、(14)(2)(c)、(16)、(17)(1)(a)、(17)(1)(b)、(17)(1)(c)、(17)(1)(d)、(17)(1)(e)、(17)(1)(f)、(17)(2)|
|***提供经过处理的 PII 的副本 (7.3.8)***|客户应该了解关于向个人提供正在处理个人数据副本的要求。 这些包括副本格式（即计算机可读）、传输副本等要求。如果客户使用提供此功能的第三方系统来提供副本，则应根据需要使用此功能。|有关 Microsoft 服务中的功能，可允许你获取向数据主体所提供的数据中可以包含的其个人数据的副本。<br>*  *符合 GDPR 的 Azure 数据主体请求* [[9](gdpr-arc-Azure.md#9)] ，请参阅“第 6 步：导出” <br> - *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)] 参见“导出”。 | 15)(3), (15)(4), (20)(1), (20)(2), (20)(3), (20)(4)|
|***请求管理 (7.3.9)***|客户应了解接受和响应的要求，以使来自与处理个人数据相关的个人请求合法。如果客户使用第三方系统，则他们应了解该系统是否提供了此类处理请求的功能。如果提供此功能，则客户应该利用这些机制根据需要处理请求。|管理数据主体请求过程中定义提供给数据主体的信息时可以使用的 Microsoft 服务功能的信息。<br>- *符合 GDPR 的 Azure 数据主体请求* [[9](gdpr-arc-Azure.md#9)] <br> - *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)]|(12)(3)、(12)(4)、(12)(5)、(12)(6)、(15)(1)(a)、(15)(1)(b)、(15)(1)(c)、(15)(1)(d)、(15)(1)(e)、(15)(1)(f)、(15)(1)(g)、(15)(1)(h)|
|***自动决策 (7.3.10)***|客户应了解有关自动处理个人数据的要求以及作出此类自动决策的情况。这些包括向个人提供有关处理的信息、反对此类处理或获得人为干预。如果这些功能由第三方系统提供，那么客户应确保第三方提供任何所需的信息或支持。|关于 Microsoft 服务中任何功能的信息（该信息可支持可用于责任文档的自动决策制定），以及有关这些功能的数据主体的模板化信息。<br>- *Azure 适用的客户数据保护影响评估关键信息* [[11](gdpr-arc-Azure.md#11)]<br>- *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)]|(13)(2)(f)、(14)(2)(g)、(22)(1)、(22)(3)|

## <a name="4-privacy-by-design-and-default"></a>4. 经设计默认的隐私

|||||
|:-----|:-----|:-----|:-----|
|**类别**|**客户注意事项**|**支持 Microsoft 文档**|**引用 GDPR 文章**|
| ***限制收集 (7.4.1)*** | 客户应了解针对个人数据的限制要求（例如，应限制为收集指定用途所需的内容）。 | 由 Microsoft 服务收集的数据的说明。<br>- *Microsoft Online Services 条款、数据保护条款，请参阅“处理个人数据”；GDPR* [[1](gdpr-arc-Azure.md#1)]<br>- *Azure 适用的客户数据保护影响评估关键信息* [[11](gdpr-arc-Azure.md#11)]<br>- *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)]| (5)(1)(b)、(5)(1)(c) |
| ***限制处理 (7.4.2)*** | 客户负责限制处理个人数据，以便将其限制在满足所确定目的的适当范围内。 | 由 Microsoft 服务收集的数据的说明。<br>- Microsoft Online Services 条款、数据保护条款，请参阅“处理个人数据”；GDPR [[1](gdpr-arc-Azure.md#1)]<br>- *Azure 适用的客户数据保护影响评估关键信息* [[11](gdpr-arc-Azure.md#11)]<br>- *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)]| (25)(2) |
| ***定义和记录 PII 最小化和去标识化目标 (7.4.3)*** | 客户应了解有关去标识化个人资料的要求，这包括应何时使用、去标识化的程度以及无法使用的情况。 | 在适当的情况下，Microsoft 会在内部应用去标识化和假名化，从而提供个人数据的额外隐私保护措施。 | (5)(1)(c) |
| ***遵守标识级别 (7.4.4)*** | 客户应使用并遵守其组织设定的去标识化目标和方法。 | 在适当的情况下，Microsoft 会在内部应用去标识化和假名化，从而提供个人数据的额外隐私保护措施。 | (5)(1)(c) |
| ***PII 去标识化和删除 (7.4.5)*** | 客户应了解有关过去用于确定目的的个人资料的保留要求。在由系统提供工具的情况下，客户应根据需要利用这些工具清除或删除。 | Microsoft 服务提供的功能，以支持数据保留策略。<br>- *符合 GDPR 的 Azure 数据主体请求* [[9](gdpr-arc-Azure.md#9)]，请参阅“第 5 步：删除”<br> - *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)] | (5)(1)(c)、(5)(1)(e)、(6)(4)(e)、(11)(1)、(32)(1)(a) |
| ***临时文件 (7.4.6)*** | 客户应该了解系统可能创建的临时文件，它们也许会导致不符合有关处理个人数据的策略（例如，个人数据在临时文件中保留的时间比所需或允许的时间要长）。 系统提供用于临时文件删除或检查的工具时，客户应该使用这些工具来遵守要求。 | 服务提供的用于标识个人数据以支持临时文件策略的功能描述。<br>- *符合 GDPR 的 Azure 数据主体请求* [[9](gdpr-arc-Azure.md#9)]，请参阅“第 1 步：发现” <br> - *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)]| (5)(1)(c) |
| ***保留时间 (7.4.7)*** | 考虑到确定的目的，客户应确定个人数据的保留时间。 | 可以在向数据主体提供的文档中添加的、Microsoft 服务保留个人数据的相关信息。<br>- *Microsoft Online Services 条款、数据保护条款，请参阅“数据安全之数据保留”* [[1](gdpr-arc-Azure.md#1)] | (13)(2)(a)、(14)(2)(a) |
| ***处置 (7.4.8)*** | 客户应利用系统提供的任何删除或处置机制来删除个人数据。 | Microsoft 服务提供的功能，以支持数据删除策略。<br>- *符合 GDPR 的 Azure 数据主体请求* [[9](gdpr-arc-Azure.md#9)]，请参阅“第 5 步：删除” <br> - *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)] 参见“删除” | (5)(1)(f) |
| ***收集过程 (7.4.9)*** | 客户应了解有关个人数据准确性的要求（例如，收集准确性，使数据保持最新等），并利用系统为此提供的任何机制。 | Microsoft 服务如何支持确保个人数据的准确性，以及提供用于支持数据准确性策略的任何功能。<br>- *符合 GDPR 的 Azure 数据主体请求* [[9](gdpr-arc-Azure.md#9)] 请参阅“第 3 步：修订” <br> - *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)]，请参阅“修订” | (5)(1)(d) |
| ***传输控件 (7.4.10)***  | 客户应了解保护个人数据传输的要求，包括谁可以访问传输机制、传输记录等。 | 由 Microsoft 服务传输的个人数据类型、在两点之间传输的位置以及传输法律安全措施的描述。<br>- *Azure 适用的客户数据保护影响评估关键信息* [[11](gdpr-arc-Azure.md#11)] <br>- *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)] | (5)(1)(f) |
| ***识别 PII 传输基础 (7.5.1)*** | 客户应知道将个人数据 (PII) 传输到不同地理位置的要求，并记录下哪些措施可以满足这些要求。 | 由 Microsoft 服务传输的个人数据类型、在两点之间传输的位置以及传输法律安全措施的描述。<br>- *Azure 适用的客户数据保护影响评估关键信息* [[11](gdpr-arc-Azure.md#11)] <br>- *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)] | 文章 (44)、(45)、(46)、(47)、(48) 和 (49) |
| ***可向其传输 PII 的国家/地区和组织 (7.5.2)*** | 客户应了解并能够向个人提供个人数据已经或可能被传输到的国家/地区。如果第三方/处理者可以执行此传输操作，则客户应从处理者获取此信息。   | 由 Microsoft 服务传输的个人数据类型、在两点之间传输的位置以及传输法律安全措施的描述。<br>- *Azure 适用的客户数据保护影响评估关键信息* [[11](gdpr-arc-Azure.md#11)]<br>- *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)] <br>- *谁以及根据哪些条款可以访问你的数据* [[7](gdpr-arc-Azure.md#7)] | (30)(1)(e)  |
| ***传输 PII（个人数据）的记录 (7.5.3)*** | 客户应维护与个人数据传输相关的所有必要和所需记录。在第三方/处理者执行传输时，客户应确保其维护相应的记录并在必要时获取这些记录。 | 由 Microsoft 服务传输的个人数据类型、在两点之间传输的位置以及传输法律安全措施的描述。<br>- *Azure 适用的客户数据保护影响评估关键信息*[[11](gdpr-arc-Azure.md#11)]<br>- *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)]<br>- *谁以及根据哪些条款可以访问你的数据* [[7](gdpr-arc-Azure.md#7)] | (30)(1)(e) |
| ***对第三方的 PII 披露记录 (7.5.4)*** | 客户应了解关于向哪些人披露了个人数据的记录的要求。这包括向执法机构披露的记录等。如果第三方/数据处理者披露了这些数据，则客户应确保其保留了相应的记录并在必要时获得这些记录。 | 列出个人数据披露接收者类别的文档，其中包括可用披露记录。<br>- 谁可以访问你的数据和所依据的条款 [[7](gdpr-arc-Azure.md#7)] <br>- Intune 中的隐私和个人数据 [[15](gdpr-arc-Azure.md#15)]，请参阅 *Intune 中的数据安全和共享* | (30)(1)(d) |
| ***联合控制者 (7.5.5)*** | 客户应确定他们是否与其他任何组织同为联合控制者，并适当地记录和分配责任。 | 正如联机服务条款 (OST) 中所规定，作为数据处理者，Microsoft 处理客户数据只是为了向客户（即数据控制者）提供所请求的服务。<br>- *Microsoft Online Services 条款、数据保护条款，请参阅“处理个人数据”；GDPR* [[1](gdpr-arc-Azure.md#1)] | (26)(1)、(26)(2) |

## <a name="5-data-protection--security"></a>5. 数据保护与安全

|||||
|:-----|:-----|:-----|:-----|
|**类别**|**客户注意事项**|**支持 Microsoft 文档**|**引用 GDPR 文章**|
| ***了解组织及其上下文 (5.2.1)*** | 客户应确定他们在处理个人数据方面的角色，（如控制者、处理者、协同控制者）以确定处理个人数据的相应要求（法规等）。 | Microsoft 如何在处理个人数据时将每个服务确定为处理者或控制者。<br>- *Microsoft Online Services 条款、数据保护条款*，请参阅“处理个人数据”；GDPR“处理者和控制者角色和责任”[[1](gdpr-arc-Azure.md#1)] | (24)(3)、(28)(10)、(28)(5)、(28)(6)、(32)(3)、(40)(1)、(40)(2)(a)、(40)(2)(b)、(40)(2)(c)、(40)(2)(d)、(40)(2)(e)、(40)(2)(f)、(40)(2)(g)、(40)(2)(h)、(40)(2)(i)、(40)(2)(j)、(40)(2)(k)、(40)(3)、(40)(4)、(40)(5)、(40)(6)、(40)(7)、(40)(8)、(40)(9)、(40)(10)、(40)(11)、(41)(1)、(41)(2)(a)、(41)(2)(b)、(41)(2)(c)、(41)(2)(d)、(41)(3)、(41)(4)、(41)(5)、(41)(6)、(42)(1)、(42)(2)、(42)(3)、(42)(4)、(42)(5)、(42)(6)、(42)(7)、(42)(8) |
| ***了解相关方的需求和期望 (5.2.2)*** | 客户应确定可能在处理个人数据方面发挥作用或感兴趣的各方（例如监管机构、审计机构、数据主体、合同规定的个人数据处理者），并了解在需要时与各方合作的要求。 | Microsoft 如何在考虑到个人数据处理风险的情况下纳入所有利益干系人的意见。<br>- *Azure 适用的客户数据保护影响评估关键信息* [[11](gdpr-arc-Azure.md#11)] <br>- *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)] | (35)(9)、(36)(1)、(36)(3)(a)、(36)(3)(b)、(36)(3)(c)、(36)(3)(d)、(36)(3)(e)、(36)(3)(f)、(36)(5) |
| ***确定信息安全管理系统的范围（5.2.3、5.2.4）*** | 作为客户拥有的任何整体安全或隐私程序的一部分，它们应包括与之相关的个人数据处理和要求。 | Microsoft 服务如何在信息安全管理和隐私计划中纳入个人数据处理。<br>* *Microsoft Azure（全部）ISO/IEC 27001:2013 ISMS 适用性声明* [[13](gdpr-arc-Azure.md#13)]，请参阅 A.19-A.29<br>* SOC 2 类型 2 审核报告[[12](gdpr-arc-Azure.md#12)] | (32)(2) |
| ***规划 (5.3)*** | 客户应将个人数据处理视为他们完成的任何风险评估的一部分，并在他们认为有必要以减轻他们控制的个人数据相关风险时采取控制措施。 | Microsoft 服务如何在整体安全和隐私计划中纳入个人数据处理风险。<br>- *Microsoft Azure（全部）ISO/IEC 27001:2013 ISMS 适用性声明* [[13](gdpr-arc-Azure.md#13)]，请参阅 A.19-A.29 | (32)(1)(b)、(32)(2) |
| ***信息安全策略 (6.2)*** | 客户应该加强任何现有的信息安全政策以将个人数据保护包括在内，其中包括遵守任何适用法律所必需的策略。 | 与信息安全和任何个人信息保护措施相关的 Microsoft 策略。<br>- *Microsoft Azure（全部）ISO/IEC 27001:2013 ISMS 适用性声明* [13]，请参阅 A.19-A.29<br>- SOC 2 类型 2 审核报告 [[12](gdpr-arc-Azure.md#12)] | (24)(2) |
| ***信息安全组织客户注意事项 (6.3)*** | 客户应在其组织内定义个人数据的安全和保护职责。这包括建立特定角色来监督隐私相关事宜，包括 DPO。应提供适当的培训和管理支持来支持这些角色。 | 有关 Microsoft 数据保护管理人员角色及职责性质、报告结构和联系信息的概述。<br>- Microsoft DPO 信息 [[17](gdpr-arc-Azure.md#17)] | (37)(1)(a)、(37)(1)(b)、(37)(1)(c)、(37)(2)、(37)(3)、(37)(4)、(37)(5)、(37)(6)、(37)(7)、(38)(1)、(38)(2)、(38)(3)、(38)(4)、(38)(5)、(38)(6)、(39)(1)(a)、(39)(1)(b)、(39)(1)(c)、(39)(1)(d)、(39)(1)(e)、(39)(2) |
| ***人员安全 (6.4)*** | 客户应确定并分配提供与保护个人数据相关的相关培训的责任。 | 有关 Microsoft 数据保护管理人员角色及其职责性质、报告结构和联系信息的概述。<br>- *Microsoft 云安全策略* [[4](gdpr-arc-Azure.md#4)] 请参阅“03. 人力资源安全”<br>- *FedRAMP 中等 FedRAMP 系统安全计划* [[3](gdpr-arc-Azure.md#3)]，请参阅“13.2 感知和培训 (AT)” | (39)(1)(b) |
| ***信息分类 (6.5.1)*** | 客户应将个人数据明确纳入数据分类方案。 | Microsoft 如何在数据分类、标记和跟踪信息中纳入个人数据。<br>-*Azure 适用的客户数据保护影响评估关键信息* [[11](gdpr-arc-Azure.md#11)] <br>- *客户数据保护影响评估适用的 Dynamics 365 关键信息* [[18](gdpr-arc-Azure.md#18)]| (39)(1)(b) |
| ***管理可移动媒体 (6.5.2)*** | 客户应确定使用可移动媒体的内部策略，因为这涉及个人数据保护（例如加密设备）。 | Microsoft 服务如何保护任何可移动媒体上的个人信息安全性。<br>- *FedRAMP 中等 FedRAMP 系统安全计划* [[3](gdpr-arc-Azure.md#3)]，请参阅“13.10 媒体保护 (MP)” | (32)(1)(a)、(5)(1)(f) |
| ***物理媒体传输 (6.5.3)*** | 客户应确定在传输物理媒体（如加密）时保护个人数据的内部策略。 | Microsoft 服务如何在物理媒体的任何传输中保护个人数据。<br>- FedRAMP 中等 FedRAMP 系统安全计划 [[3](gdpr-arc-Azure.md#3)]，请参阅“13.10 媒体保护 (MP)”<br> | (32)(1)(a)、(5)(1)(f) |
| ***用户访问管理 (6.6.1)*** | 客户应了解他们在使用的服务中对访问控制负有的职责，并使用可用工具管理相应职责。 | Microsoft 服务提供的工具，有助于你强制执行访问控制。<br>- Azure 安全文档之用户注册。<br>- Azure 安全文档 [[2](gdpr-arc-Azure.md#2)]，请参阅[通过身份和访问控制保护个人数据](https://docs.microsoft.com/azure/security/protect-personal-data-identity-access-controls) | (5)(1)(f) |
| ***用户注册和注销 (6.6.2)*** | 客户应使用他们可用的工具来管理其所使用的服务中的用户注册和注销。 | Microsoft 服务提供的工具，有助于你强制执行访问控制。<br>- Azure 安全文档之用户注册。<br>- Azure 安全文档 [[2](gdpr-arc-Azure.md#2)]，请参阅[通过身份和访问控制保护个人数据](https://docs.microsoft.com/azure/security/protect-personal-data-identity-access-controls) | (5)(1)(f) |
| ***用户访问权限预配 (6.6.3)*** | 客户应该使用他们可用的工具在其所使用的服务内管理用户配置文件，尤其是管理针对个人数据的授权访问。 | Microsoft 服务如何支持对个人数据执行正式访问控制，包括用户 ID、角色以及用户注册和注销。<br>- Azure 安全文档 [[2](gdpr-arc-Azure.md#2)]，请参阅[通过身份和访问控制保护个人数据](https://docs.microsoft.com/azure/security/protect-personal-data-identity-access-controls) | (5)(1)(f) |
| ***特权访问管理 (6.6.4)*** | 客户应该使用他们可用的工具在其所使用的服务内管理用户 ID，以促进跟踪访问（尤其针对个人数据）。 | Microsoft 服务如何支持对个人数据执行正式访问控制，包括用户 ID、角色以及用户注册和注销。<br>- Azure 安全文档 [[2](gdpr-arc-Azure.md#2)]，请参阅[通过身份和访问控制保护个人数据](https://docs.microsoft.com/azure/security/protect-personal-data-identity-access-controls) | (5)(1)(f) |
| ***安全登录过程 (6.6.5)*** | 客户应利用服务中提供的机制来确保必要时为其用户提供安全登录功能。 | Microsoft 服务如何支持与个人数据相关的内部访问控制策略。<br>- 谁可以访问你的数据和所依据的条款 [[7](gdpr-arc-Azure.md#7)] | (5)(1)(f) |
| ***加密 (6.7)*** | 客户应确定哪些数据需要加密，以及他们正在使用的服务是否提供这种功能。客户应根据需要通过可用的工具来使用加密。 | Microsoft 服务如何支持加密和假名化，以减少个人数据处理风险。<br>- Azure 安全文档 [[2](gdpr-arc-Azure.md#2)]，请参阅[通过加密保护静态个人数据](https://docs.microsoft.com/azure/security/protect-personal-data-at-rest)和[通过加密保护传输中的个人数据](https://docs.microsoft.com/azure/security/protect-personal-data-in-transit-encryption)以及 [Azure 加密概述](https://docs.microsoft.com/azure/security/security-azure-encryption-overview) | (32)(1)(a) |
| ***安全处置或重新使用的设备 (6.8.1)*** | 在客户使用云计算服务（PaaS、SaaS、IaaS）的情况下，他们应了解云提供商如何确保在将存储空间分配给其他客户之前将个人数据从该空间中清除。 | Microsoft 服务如何确保在设备转让或重用前从存储设备中清除个人数据。<br>- Microsoft Azure 数据安全（数据清理和泄露）[[5](gdpr-arc-Azure.md#5)] | (5)(1)(f) |
| ***清除桌面和清除屏幕策略 (6.8.2)*** | 客户应考虑显示个人数据的硬拷贝材料相关的风险，并可能限制此类材料的创建。如果正在使用的系统提供限制此类材料的功能（例如，设置为防止打印或复制/粘贴敏感数据），客户应根据需要使用这些功能。 | Microsoft 管理硬拷贝所采取的措施。<br>-Microsoft 内部维护这些控件。 请参见 *Microsoft Azure（全部）ISO/IEC 27001:2013 ISMS 适用性声明* [[15](gdpr-arc-Azure.md#13)]  A.11.2.9 | (5)(1)(f) |
| ***分离开发、测试和运行环境 (6.9.1)*** | 客户应考虑在组织内的开发和测试环境中使用个人数据的影响。 | Microsoft 如何确保个人数据在开发和测试环境中受到保护。<br>- *Microsoft Azure（全部）ISO/IEC 27001:2013 ISMS 适用性声明* [[13](gdpr-arc-Azure.md#13)]，请参阅 A.12.1.4<br>- 对安全性、隐私和合规性 RFI 的 Azure 标准响应 [6]。<br>- Azure 控件 530：生产环境与开发/测试相互独立 [[16](gdpr-arc-Azure.md#16)]。 | 5(1)(f) |
| ***信息备份 (6.9.2)*** | 客户应确保他们使用系统提供的功能来创建数据冗余并在必要时进行测试。 | Microsoft 如何确保可能包含个人数据的数据的可用性，如何确保已还原数据的准确性以及 Microsoft 服务提供的可备份和还原数据的工具和过程的准确性。<br>- FedRAMP 中等 FedRAMP 系统安全计划 [[3](gdpr-arc-Azure.md#3)]，请参阅“10.9 可用性” | (32)(1)(c)、(5)(1)(f) |
| ***事件日志记录 (6.9.3)*** | 客户应了解系统提供的记录功能，并利用这些功能来确保他们可以记录他们认为必要的与个人数据相关的操作。 | Microsoft 服务为你记录的数据包括用户活动、异常、错误和信息安全事件，以及如何访问这些日志以作为保存记录的一部分使用。<br>- Azure 安全文档之用户注册。<br>- Azure 安全文档 [[2](gdpr-arc-Azure.md#2)]，请参阅[通过 Azure 报告工具执行个人数据文档保护](https://docs.microsoft.com/azure/security/protection-personal-data-azure-reporting-tools) | (5)(1)(f) |
| ***保护日志信息 (6.9.4)***  | 客户应考虑保护可能包含个人数据或可能包含与个人数据处理相关记录的日志信息的要求。在使用的系统提供保护日志功能时，客户应根据需要利用这些功能。 | Microsoft 如何保护可能包含个人数据的日志。<br>- Azure 安全文档 [[2](gdpr-arc-Azure.md#2)]，请参阅[通过 Azure 报告工具执行个人数据文档保护](https://docs.microsoft.com/azure/security/protection-personal-data-azure-reporting-tools) | (5)(1)(f) |
| ***信息传输策略和过程 (6.10.1)*** | 对于个人数据可能在物理媒体上传输（例如在服务器或设施之间移动的硬盘）的情况，客户应有应对过程。这些包括日志、授权和跟踪。如果第三方或其他处理者正在传送物理介质，则客户应确保该组织有应对流程来确保个人数据的安全。 | Microsoft 服务如何传输可能包含个人数据的物理介质，包括传输时间以及为保护数据而采取的保护措施等情况。<br>- *FedRAMP 中等 FedRAMP 系统安全计划* [[3](gdpr-arc-Azure.md#3)]，请参阅“13.10 媒体保护 (MP)” | (5)(1)(f) |
| ***保密性或保密协议 (6.10.2)*** | 客户应确定保密协议的必要性，或者有权访问个人数据的个人或对个人数据负有相关责任的个人的等同性。  | Microsoft 服务如何确保有权访问个人数据的个人承诺保密。<br>- *SOC 2 类型 2 审核报告* [[12](gdpr-arc-Azure.md#12)]，请参阅 CC1.4 pp72, SOC2—13 | (5)(1)(f)、(28)(3)(b)、(38)(5) |
| ***保护公共网络上的应用服务 (6.11.1)*** | 客户应了解个人数据加密的要求，尤其是通过公共网络发送的情况。如果系统提供加密数据的机制，则客户应根据需要使用这些机制。 | Microsoft 服务为保护传输中的数据（包括数据加密）而采取的措施的说明、以及 Microsoft 服务在数据通过公用数据网络（包括任何加密措施）时如何保护可能包含个人数据的数据的说明。<br>- Azure 安全文档 [[2](gdpr-arc-Azure.md#2)] 请参阅[通过加密保护传输中的个人数据](https://docs.microsoft.com/azure/security/protect-personal-data-in-transit-encryption) | (5)(1)(f)、(32)(1)(a) |
| ***安全系统工程原理 (6.11.2)*** | 客户应了解系统是如何从考虑保护个人数据的角度设计和策划的。如果客户使用由第三方设计的系统，则他们有责任确保已慎重考虑此类保护措施。 | Microsoft 服务如何将个人数据保护原则纳入安全设计/工程原则的强制性部分。<br>- SOC 2 类型 2 审核报告 [12]，请参阅 CC7.1 pp90 和[什么是安全开发生命周期？](https://www.microsoft.com/sdl/) | (25)(1) |
| ***供应商关系 (6.12)*** | 客户应确保任何信息安全和个人数据保护要求以及第三方责任均在合同信息或其他协议中得到解决。协议还应给出处理说明。 | Microsoft 服务如何在我们与供应商达成的协议中指定安全和数据保护，以及我们如何确保这些协议得到有效执行。<br>- 谁可以访问你的数据和所依据的条款 [[7](gdpr-arc-Azure.md#7)] | (5)(1)(f)、(28)(1)、(28)(3)(a)、(28)(3)(b)、(28)(3)(c)、(28)(3)(d)、(28)(3)(e)、(28)(3)(f)、(28)(3)(g)、(28)(3)(h)、(30)(2)(d)、(32)(1)(b) |
| ***信息安全事件管理和改进 (6.13.1)*** | 客户应具有确定何时发生个人数据泄露的流程。 | Microsoft 服务如何确定安全事件是否是个人数据泄露事件，以及我们如何向你传达泄露事件。<br>-*Azure 和 GDPR 规定的泄露通知* [[10](gdpr-arc-Azure.md#10)] | (33)(2) |
| ***责任和过程（在信息安全事件期间）(6.13.2)*** | 客户应在涉及个人数据的数据泄露或安全事件期间了解并记录他们的职责。职责包括通知各相关方、与处理者或其他第三方进行通信，以及在客户组织内的职责。 | 如何在检测到安全事件或个人数据泄露时通知 Microsoft 服务。<br>-*Azure 和 GDPR 规定的泄露通知* [[10](gdpr-arc-Azure.md#10)] | (5)(1)(f)、(33)(1)、(33)(3)(a)、(33)(3)(b)、(33)(3)(c)、(33)(3)(d)、(33)(4)、(33)(5)、(34)(1)、(34)(2)、(34)(3)(a)、(34)(3)(b)、(34)(3)(c)、(34)(4) |
| ***信息安全事件响应 (6.13.3)*** | 客户应具有确定何时发生个人数据泄露的流程。 | Microsoft 服务提供的信息说明，有助于你确定是否发生了个人数据泄露。<br>- *Azure 和 GDPR 规定的泄露通知* [[10](gdpr-arc-Azure.md#10)] | (33)(1)、(33)(2)、(33)(3)(a)、(33)(3)(b)、(33)(3)(c)、(33)(3)(d)、(33)(4)、(33)(5)、(34)(1)、(34)(2) |
| ***记录保护 (6.15.1)*** | 客户应了解与个人数据处理相关且需要维护的记录的相关要求。 | Microsoft 服务如何存储与个人数据处理相关的记录。<br>- Azure 安全文档之用户注册。<br>- Azure 安全文档 [[2](gdpr-arc-Azure.md#2)]，请参阅[通过 Azure 报告工具执行个人数据文档保护](https://docs.microsoft.com/azure/security/protection-personal-data-azure-reporting-tools) | (5)(2)、(24)(2)  |
| ***独立审查信息安全 (6.15.2)*** | 客户应了解对个人数据处理安全性评估的要求。这包括内部或外部审核或其他评估处理安全性的措施。如果客户依赖其他第三方组织进行全部或部分处理，则应收集有关由他们执行的此类评估的信息。 | Microsoft 服务如何测试和评估技术和组织措施的有效性，以确保处理的安全性，包括第三方的任何审核。<br/>*Microsoft Online Services 条款、数据保护条款，请参阅“数据安全之审核合规性”*[[1](gdpr-arc-Azure.md#1)] | (32)(1)(d)、(32)(2) |
| ***技术符合性审查 (6.15.3)*** | 客户应了解测试和评估处理个人数据安全性的要求。这包括技术测试，如渗透测试。如果客户使用第三方系统或处理者，则他们应了解他们在保护和测试安全方面承担的责任（例如管理配置以保护数据，然后测试这些配置设置）。如果第三方负责安全性处理的全部或部分，则客户应该了解第三方为确保处理的安全性而进行的测试或评估。 | 如何基于标识的风险（包括由第三方发起的测试，以及技术测试类型和测试中任何可用的报表）对 Microsoft 服务测试安全性。<br>- *Microsoft Online Services 条款、数据保护条款，请参阅“数据安全之审核合规性”*[[1](gdpr-arc-Azure.md#1)]<br>- 有关外部认证的列表，请参阅 **Microsoft 信任中心合规性**产品 [[14](gdpr-arc-Azure.md#14)]<br>- 若要详细了解如何对应用程序执行渗透测试，请参阅 *Azure 安全文档* [[2](gdpr-arc-Azure.md#2)] [渗透测试](https://docs.microsoft.com/azure/security/azure-security-pen-testing) | (32)(1)(d)、(32)(2) |

## <a name="6-bibliography-of-resources-and-links"></a>6. 资源和链接参考文献

|**ID**|**说明/链接**|
|:-----|:-----|
| 1 <a name="1"> </a> | [联机服务条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
| 2 <a name="2"></a>  | [Azure 安全文档](https://docs.microsoft.com/azure/security/)，请参阅治理和合规性，GDPR |
| 3 <a name="3"> </a> | [FedRAMP 中等 FedRAMP 系统安全计划 (SSP)](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=e46a519a-bcf6-4dc2-8f60-6d0e4e00a85e&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_FedRAMP_Reports) |
| 4 <a name="4"> </a>   | [Microsoft 云安全策略](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)  |
| 5 <a name="5"> </a>   | [ Microsoft Azure 数据安全（数据清理和泄露）](https://blogs.msdn.microsoft.com/walterm/2014/09/04/microsoft-azure-data-security-data-cleansing-and-leakage/) |
| 6 <a name="6"> </a>   | [对安全性、隐私和合规性 RFI 的 Azure 标准响应](https://gallery.technet.microsoft.com/Azure-Standard-Response-to-5de19cb6) |
| 7 <a name="7"> </a>   | [谁可以访问你的数据和所依据的条款](https://www.microsoft.com/trustcenter/Privacy/Who-can-access-your-data-and-on-what-terms) |
| 8 <a name="8"> </a>   | [次级处理者合同：与 Microsoft 签订合同](https://www.microsoft.com/procurement/supplier-contracting.aspx#SSPA) |
| 9 <a name="9"> </a>   | [针对 GDPR 的 Azure 数据主体请求](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure) |
| 10 <a name="10"> </a> | [GDPR 规定的 Azure 和 Dynamics 365 泄露通知](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics) |
| 11 <a name="11"> </a> | [Azure 适用的客户数据保护影响评估关键信息](https://aka.ms/DPIAAzure) |
| 12 <a name="12"> </a> | [SOC 2 类型 2 审核报告 [12]](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=3c7123a5-f507-48b7-8dce-cd948e6150e6&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC_%2F_SSAE_16_Reports) |
| 13 <a name="13"> </a> | [Microsoft Azure（全部）ISO/IEC 27001:2013 ISMS 适用性声明](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=47d89200-b24b-491d-b657-7c523ddfb6f9&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_ISO_Reports) |
| 14 <a name="14"> </a> | [Microsoft 信任中心合规性产品/服务](offering-home.md)  |
| 15 <a name="15"> </a> | [Microsoft DPO 信息](https://aka.ms/GDPRDPO) |
| 16 <a name="16"> </a> | [客户数据保护影响适用的 Dynamics 365 关键信息](https://servicetrust.microsoft.com/ViewPage/GDPRDPIA?command=Download&downloadType=Document&downloadId=ef2902bb-3137-4f4a-8ca6-af35afaa6bec&docTab=2ba9a350-555c-11e8-b74a-77b1f31da06e_DPIA) |
| 17 <a name="17"> </a> | [Dynamics 365 中的审核与报告](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-use-comprehensive-auditing) |
| 18 <a name="18"> </a> | [符合 GDPR 的 Dynamics 365 数据主体请求](https://servicetrust.microsoft.com/ViewPage/GDPRDSR) |

## <a name="learn-more"></a>了解详细信息

- [Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
- [Azure 合规性文档](https://docs.microsoft.com/azure/compliance/)
