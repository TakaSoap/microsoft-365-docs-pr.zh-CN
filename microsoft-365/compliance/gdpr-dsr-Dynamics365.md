---
title: 符合 GDPR 的 Dynamics 365 数据主体请求
description: 指南介绍了如何使用 Microsoft 的产品、服务和管理工具来帮助我们的控制者客户查找和处理个人数据以响应 DSR 请求：
keywords: Microsoft 365, Microsoft 365 教育版, Microsoft 365 文档, GDPR
author: BrendaCarter
localization_priority: Priority
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/13/2018
ms.author: bcarter
manager: laurawi
ms.collection: GDPR
ms.openlocfilehash: e1c79ae466264e302b282244f477dafcc6b49afe
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866073"
---
# <a name="dynamics-365-data-subject-requests-for-the-gdpr"></a>符合 GDPR 的 Dynamics 365 数据主体请求

根据 EU 数据保护条例 (GDPR)，用户（在条例中称为“*数据主体*”）有权管理由雇主或其他类型机构或组织（称为“*数据控制者*”或简称为“*控制者*”）收集的个人数据。在 GDPR 中，个人数据的定义很广泛，包括与身份已识别或可识别的自然人相关的任何数据。根据 GDPR，数据主体有权对自己的个人数据执行以下操作：获取个人数据副本、请求更改个人数据、限制个人数据处理、删除个人数据或接收电子格式的个人数据（以便于转移给其他控制者）。数据主体为了对自己的个人数据执行操作而向控制者发出的正式请求，在本文档中称为“*数据主体权利请求*”或“DSR 请求”。<span id="_Toc510437912" class="anchor"><span id="_Toc508792504" class="anchor"></span></span>

本指南讨论了如何使用 Microsoft 的产品、服务和管理工具帮助我们的控制者客户查找和操作个人数据以响应 DSR 请求。具体而言，这包括如何查找、访问和操作驻留在 Microsoft 云中的个人数据。下面是本指南中所列流程的快速概述：

1. ***发现*** - 使用搜索和发现工具更轻松地查找可能是 DSR 请求主体的客户数据。一旦收集了潜在响应文档，则可以执行一个或多个下列步骤中所述的 DSR 操作。或者，你可能会确定请求不符合组织有关响应 DSR 请求的指导原则。

2. ***访问*** - 检索驻留在 Microsoft 云中的个人数据，根据请求，还会制作可供数据主体使用的个人数据副本。

3. ***纠正*** - 进行更改或者对个人数据实施其他请求的操作（如果适用）。

4.  ***限制*** - 通过移除各种联机服务的许可证或者在可能的情况下关闭所需服务，限制个人数据的处理。你也可以从 Microsoft 云中移除数据并将其保留在內部或其他位置。

5. ***删除*** - 永久移除驻留在 Microsoft 云中的个人数据。

6. ***导出*** - 向数据主体提供个人数据的电子副本（采用机器可读格式）。

本指南中的每个部分概述了数据控制者组织为响应对 Microsoft 云中个人数据的 DSR 请求而采取的技术过程。

### <a name="gdpr-terminology"></a>GDPR 术语

下面提供了与本指南相关的术语定义：

- <em>控制者 - </em>单独或与其他人一起确定个人数据处理的用途和途径的自然人或法人、公共机构、机关或其他实体；如果欧盟或成员国法律确定了此类处理的用途和途径，欧盟或成员国法律可能会规定控制者或具体提名条件。

- *个人数据*和<em>数据主体 - </em>已确定身份或可识别的自然人（“数据主体”）的任何相关信息；可识别的自然人是指可被直接或间接识别的自然人，尤其是通过参考姓名、证件号码、位置数据、网络标识等标识，或通过参考特定于该自然人的身体、生理、基因、精神、经济、文化或社会标识的一个或多个因素进行识别。

- <em>处理者 - </em>代表控制者处理个人数据的自然人或法人、公共机构、机关或其他主体。

- *客户数据* - 客户或代表客户通过使用企业服务提供给 Microsoft 的所有文本、声音、视频或图像文件和软件，如 Microsoft Online Services 条款所定义。

- *系统生成日志 *-** Microsoft 生成的日志和相关数据，可帮助 Microsoft 向用户提供企业服务。系统生成日志主要包括化名数据，例如唯一标识符，这通常是系统生成的无法单独识别个人但用于向用户提供企业服务的一个数字。系统生成日志还可能包含有关最终用户的身份信息，例如用户名。  

### <a name="how-this-guide-can-help-you-meet-your-controller-responsibilities"></a>本指南将如何帮助你履行控制者职责

本指南分为两个部分，介绍了如何使用 Dynamics 365 产品、服务和管理工具来帮助你查找和处理 Microsoft 云中的数据以响应根据 GDPR 行使其权利的数据主体提出的请求。第一部分处理客户数据中包括的个人数据，第二部分处理系统生成日志中捕获的其他化名个人数据。

**第 1 部分：响应对客户数据中包括的个人数据的数据主体权利 (DSR) 请求。** 本指南第 1 部分讨论如何访问、纠正、限制、删除个人数据以及将个人数据从 Dynamics 365 应用程序（软件即服务）导出，这些数据会作为提供给联机服务的客户数据的一部分进行处理。

**第 2 部分：响应对化名数据的数据主体权利请求。** 在你使用 Dynamics 365 企业服务时，Microsoft 会生成某些信息（在本文档中称为 *“系统生成日志”*）以提供服务，这仅限于最终用户留下的使用情况信息以识别其在系统中的操作。虽然在不使用其他信息的情况下，此数据无法归于特定数据主体，但根据 GDPR，有些数据被视为个人数据。本指南的第 2 部分讨论如何访问、删除和导出由 Dynamics 365 产生的系统生成日志。

### <a name="preparing-for-data-subject-rights-investigations"></a>准备数据主体权限调查

当数据主体行使其权利并提出请求时，请考虑以下几点：

- 通过使用数据主体在请求中提供给你的信息，正确识别人员和角色（例如员工、客户、供应商）。此信息可能是姓名、员工 ID 或客户编码或其他标识符。

- 记录请求的日期和时间（必须在 30 天内完成请求）。

- 确认请求符合组织有关接受或拒绝数据主体请求的要求。例如，必须确保执行请求与你的其他法律、财务或法规义务不冲突，也不侵犯他人的权利和自由。

- 确认你有与该请求相关的信息。

## <a name="part-1-responding-to-data-subject-rights-requests-for-personal-data-includced-in-customer-data"></a>第 1 部分：响应针对客户数据中包含的个人数据的数据主体权限请求

在下面的文章中，你将找到可帮助你准备和响应对 Dynamics 365 中处理的客户数据中所包括的个人数据的 DSR 请求。请务必注意，个人数据可能存在于 Microsoft 在联机服务订阅的服务过程中处理的其他数据类别，例如 Microsoft 隐私声明中定义的管理员数据或支持数据。本文档仅限于在发现和管理影响你提供给 Dynamics 365 的客户数据中存在的个人数据的 DSR 请求。

Dynamics 365 是一个提供多项数据处理功能的联机服务，采用软件即服务 (SaaS) 形式。因此，Dynamics 365 提供了一组广泛的功能来处理各种数据，这些按性质、用途或其他特定属性（如销售数据、交易、财报、HR 信息等）而不同。鉴于这种多样性，Dynamics 365 提供了多个表单、字段、架构、端点和客户数据处理逻辑，这也反映在每个应用程序中处理 DSR 请求的多种方式上。当 Dynamics 365 应用程序提供多种方式来处理特定 DSR 请求时，我们将通过指向每个应用程序所提供的技术说明，在本指南中指出这些方式。

### <a name="microsoft-dynamics-365"></a>Microsoft Dynamics 365
#### <a name="finding-customer-data"></a>查找客户数据

响应数据主体权利请求的第一步是搜索并标识作为请求主体的客户数据。

对客户数据进行适当分类是处理 Microsoft Dynamics 365 for Customer Engagement 中的个人数据的基础。Dynamics 365 for Customer Engagement 可以围绕数据分类灵活构建应用程序扩展。适当的分类可帮助你将信息识别为个人数据，从而能够在响应数据主体的请求时找到并进行检索。这还可帮助遵守有关收集和管理个人数据的法律和法规要求。

Microsoft 提供了一些功能，可帮助你响应数据主体权利请求，从而访问客户数据。但是，你需要负责确保找到个人数据并适当分类。

<span id="_Toc511225657" class="anchor"></span>***Dynamics 365 for Customer Engagement*** 提供了多种方法在记录中搜索个人数据：高级查找搜索、相关性搜索和搜索记录。所有这些功能都可以用来识别（查找）个人数据。

-   [高级查找搜索](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)

-   [相关性搜索](https://docs.microsoft.com/dynamics365/customer-engagement/basics/relevance-search-results)，可以使用仪表板相关性搜索保存以供将来参考

-   [搜索记录](https://docs.microsoft.com/dynamics365/customer-engagement/basics/search-records)，跨多个记录类型

在 Dynamics 365 for Marketing 中，还有以下其他功能：

1.  [构建 Power BI 报告](https://docs.microsoft.com/power-bi/service-connect-to-microsoft-dynamics-crm)，以筛选并识别客户数据。

2.  对市场营销执行的联系人和对象使用 Insight Views，以识别可能包含客户数据的其他数据点。

<span id="_Toc511225658" class="anchor"></span>***Dynamics 365 for Finance and Operations*** 提供了几种搜索客户数据的方法。你作为租户管理员，可以执行以下操作来搜索客户数据：

-   按照用于快速发现个人数据的方式整理客户数据，请参阅[如何分类数据库存](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#detailed-inventory)完成此操作。

-   使用[人员搜索报告](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report)查找并收集个人数据。

-   通过创建新实体或扩展现有实体，[扩展人员搜索报告](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report)。

-   使用搜索和筛选功能查找特定个人数据以及通过使用 Microsoft Office 导出功能导出该数据或使用浏览器扩展将该信息打印到 .pdf。

-   创建用于定位和导出个人数据的自定义表单。

-   创建允许经过身份验证的客户查看其个人数据的外部门户或网站。

***Dynamics for Business Central*** 提供了多种方式来搜索客户数据。有关详细信息，请参阅[搜索、筛选数据以及为数据排序](https://docs.microsoft.com/dynamics-nav-app/ui-enter-criteria-filters)。

<span id="_Toc511225660" class="anchor"></span>***Dynamics 365 for Talent*** 提供了高级搜索和筛选功能来查找特定个人数据，并提供了 Microsoft Office 导出功能导出该信息或使用浏览器扩展将该信息打印到 .pdf。

-   使用[人员搜索报告](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report)查找并收集客户数据。

-   通过创建新实体或扩展现有实体，[扩展人员搜索报告](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report)。

### <a name="providing-a-copy-of-customer-data"></a>提供客户数据副本

可使用全面的实体导出功能导出 ***Dynamics 365 for Customer Engagement*** 中的客户数据。客户数据可以导出到静态的 Excel 文件以促进数据移植请求。然后，使用 Excel，可以编辑要包含在移植请求中的个人数据，然后另存为常用的机器可读格式，例如 .csv 或 .xml。

此外，在 Dynamics 365 for Marketing 中，提供了一个[专用 API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact)，让客户能够建立扩展以检索所捕获的可能包含个人数据的客户交互的其他记录。该 API 从后端系统加载所有相关信息并将其汇总到单个可移植文档中。

可使用全面的实体导出功能导出 ***Dynamics 365 for Finance and Operations*** 中的客户数据。通过使用[*数据管理和集成实体*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity)，租户管理员可利用提供的实体、创建新实体或扩展现有实体，以使用[*数据导入和导出作业*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job)将个人数据重复导出到 Excel 或各种其他常用格式。或者，可以将许多列表导出到静态 Excel 文件以促进数据移植请求。将客户数据导出到 Excel 后，可以编辑要包含在移植请求中的个人数据，然后将该文件另存为常用的机器可读格式，例如 .csv 或 .xml。你还可以考虑使用*人员搜索报告 *为数据主体提供已分类为个人数据的数据。 

在 ***Dynamics 365 Business Central*** 中，可使用两种功能向数据主体提供客户数据副本：

可以将客户数据导出到 Excel 文件。然后在 Excel 中，可以编辑要包括在移植请求中的客户数据，并将其另存为常用的机器可读格式，如 .csv 或 .xml。有关详细信息，请参阅[将业务数据导出到 Excel](https://docs.microsoft.com/zh-CN/dynamics365/business-central/about-export-data)。

在 ***Dynamics 365 for Talent*** 中，可以使用[扩展人员搜索报告](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report)收集信息以支持对数据主体个人数据副本的请求。

### <a name="rectifying-customer-data"></a>纠正客户数据错误

<span id="_Toc511225663" class="anchor"></span>***Dynamics 365 for Customer Engagement*** 提供以下方法来更正不准确或不完整的客户数据或擦除客户数据：

-   使用“查找客户数据”中提及的功能搜索客户数据，以及直接在客户参与表单中编辑数据。可直接修改在单行或多行中完成的编辑。

-   批量编辑多个客户参与记录，你可以利用 Microsoft Office 加载项将数据导出到 Microsoft Excel，进行更改，然后将修改过的数据从 Excel 导入 Dynamics 365 for Customer Engagement。

此外，在 Dynamics 365 for Marketing 中，还可以：

-   通过直接编辑一行或多行“更新我的数据”登录页面

-   准备一个具有许多可编辑的联系人字段的[订阅中心](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/set-up-subscription-center)页面。这可以让最终用户尽可能多地更新自己的信息。

在 ***Dynamics 365 for Finance and Operation*** 中，还可能使用[*自定义工具*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page)，但你需要负责决策和实施。

<span id="_Toc511225664" class="anchor"></span>***Dynamics 365 Business Central*** 提供了两种方法来更正不准确或不完整的客户数据。

若要快速地批量编辑多个 Business Central 记录，可使用 [Business Central Excel 加载项](https://docs.microsoft.com/zh-CN/dynamics365/business-central/finance-analyze-excel#the--excel-add-in)将列表导出为 Excel 以更正多个记录，然后在 Business Central 中从 Excel 发布修改过的数据。有关详细信息，请参阅[将业务数据导出到 Excel](https://docs.microsoft.com/zh-CN/dynamics365/business-central/about-export-data)。

- 可以更改存储在任何字段中的客户数据（例如客户卡片中有关客户的信息）通过手动编辑包含目标个人数据的数据元素。有关详细信息，请参阅[输入数据](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data)。

#### <a name="brief-note-about-modifying-entries-in-business-transactions"></a>有关修改业务交易条目的简短说明
交易记录（如常规、客户和纳税分类账条目）对于企业资源规划系统的完整性至关重要。作为财务或其他事务一部分的个人数据将“按原样”保存，以符合财务法律（例如税法）、防范诈骗（例如安全审计跟踪）或遵从行业认证。因此，Dynamics 365 for Finance and Operations 和 Dynamics 365 Business Central 限制修改此类记录中的数据。

如果你将个人数据存储在业务交易记录中，则更正、删除数据或限制个人数据处理以接受数据主体的请求的唯一方法是使用 Dynamics 365 Business Central[ 自定义功能](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/index)。[](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#reasons-why-certain-personal-data-may-not-be-modified-or-deleted)因此，由你负责决定接受和实施数据主体的修改请求。

### <a name="restricting-the-processing-of-customer-data"></a>限制客户数据的处理

当你收到来自数据主体的限制处理客户数据的请求时，可轻松从联机服务提取受影响的客户数据并将其存储在单独的容器中（例如具有数据隔离功能的内部存储或单独的网络服务），独立于任意云应用程序提供的处理功能。

***Dynamics 365 Business Central*** 提供了替代机制，例如数据处理阻止，让用户能够阻止特定数据主体的记录。有关详细信息，请参阅[限制数据主体的数据处理](https://docs.microsoft.com/dynamics365/business-central/admin-responding-to-requests-about-personal-data#restrict-data-processing-for-a-data-subject)。当记录被标记为已阻止时，Dynamics 365 Business Central 将停止处理该数据主体的客户数据。你不能创建使用被阻止记录的新交易；例如，如果客户或销售人员被阻止，则不能为客户创建新发票。

### <a name="deleting-customer-data"></a>删除客户数据

当数据主体要求你删除其客户数据时，有几种方法可执行此操作：

-   批量编辑多个 Dynamics 365 记录，你可以利用 Microsoft Office 加载项将数据导出到 Microsoft Excel，进行更改，然后将修改过的数据从 Excel 导入回联机服务。

-   你可以通过查找想要删除的数据然后手动删除包含目标客户数据的数据元素，删除存储在任何字段中的客户数据，例如对表示数据主体的联系人记录和包含个人数据的其他记录使用硬性删除。

此外，在 Dynamics 365 for Marketing 中，删除联系人将确保也移除包含个人信息的交互数据。对于任何自定义字段或实体，必须自定义你的系统，以确保将所有客户数据从相关记录删除和/或取消与联系人数据的链接，以便移除所有个人信息。详细信息：[《开发人员指南（市场营销）》](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/marketing-developer-guide)。

或者，在 ***Dynamics 365 for Finance and Operations*** 中，可能使用[*自定义工具*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page)擦除/修改客户数据。

在 ***Dynamics 365 Business Central*** 中，当数据主体要求你删除其碰巧包括在你的客户数据中的个人数据时，有几种方法可处理此请求：

-   若要快速批量编辑多个 Business Central 记录，可使用 [Business Central Excel 加载项](https://docs.microsoft.com/zh-CN/dynamics365/business-central/finance-analyze-excel#the--excel-add-in)将数据导出到 Excel 以删除多条记录，然后将这些更改从 Excel 发布回 Business Central。有关详细信息，请参阅[将业务数据导出到 Excel](https://docs.microsoft.com/zh-CN/dynamics365/business-central/about-export-data)。

-   可以通过手动删除包含目标客户数据的数据元素来删除存储在任何字段中的客户数据。有关详细信息，请参阅[输入数据](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data)。

-   你可以直接删除客户数据，例如通过删除联系人然后运行“删除已取消交互日志条目”批处理作业来删除该联系人的交互。

-   你可以[删除文档](https://docs.microsoft.com/dynamics365/business-central/admin-manage-documents)，包含诸如备忘录和已过帐的销售与采购发票等客户数据的文档。

除了批量或单个删除零散记录之外，请注意，只有已离职的工作人员可以完全从 ***Dynamics 365 for Talent*** 中删除。[请按照这些步骤删除已离职的工作人员](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/respond-dsr-request-talent#additional-notes-that-apply-to-requests-for-personal-data)。

### <a name="exporting-customer-data"></a>导出客户数据

若要响应数据移植请求，可使用全面的实体导出功能导出 ***Dynamics 365 for Customer Engagement*** 中的客户数据。客户数据可以导出到静态 Excel 文件以促进数据移植请求。使用 Excel，可编辑要包含在移植请求中的个人数据，然后将其另存为常用的机器可读格式，例如 .csv 或 .xml。

此外，在 Dynamics 365 for Marketing 中，提供了一个[专用 API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact)，让客户能够建立扩展以检索所捕获的可能包含个人数据的客户交互的其他记录。该 API 从后端系统加载所有相关信息并将其汇总到单个可移植文档中。

<span id="_Toc511225669" class="anchor"></span>***Dynamics 365 for Finance and Operations*** 提供了[数据管理和集成实体](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity)，可用于启用提供的实体、新创建的实体或扩展的实体，以使用[数据导入和导出作业](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job)将个人数据重复导出到 Excel 或各种其他常用格式。或者，可将许多列表导出到静态 Excel 文件以促进数据移植请求。将客户数据以这种方式导出到 Excel 后，你可以编辑要包括在移植请求中的个人数据，然后将该文件另存为常用的机器可读格式，例如 .csv 或 .xml。

Dynamics 365 for Finance and Operations 和 ***Dynamics 365 for Talent*** 都提供了人员搜索报告，可为数据主体提供已分类为个人数据的数据。 

- <span id="_Toc511225670" class="anchor"></span>***Dynamics 365 Business Central*** 提供以下功能，

- 你可以将客户数据导出到 Excel 文件。然后，在 Excel 中，可以编辑要包括在移植请求中的客户数据，并将其另存为常用的机器可读格式，如 .csv 或 .xml。有关详细信息，请参阅[将业务数据导出到 Excel](https://docs.microsoft.com/dynamics-nav-app/about-export-data)。

你可以将客户数据导出到 Excel 文件。然后，在 Excel 中，可以编辑要包括在移植请求中的客户数据，并将其另存为常用的机器可读格式，如 .csv 或 .xml。有关详细信息，请参阅[将业务数据导出到 Excel](https://docs.microsoft.com/zh-CN/dynamics365/business-central/about-export-data)。

### <a name="microsoft-social-engagement"></a>Microsoft Social Engagement

<span id="_Toc511166412" class="anchor"></span>由于 Microsoft Social Engagement 处理可能在客户数据和社交内容中找到的个人数据，因此该应用程序提供了一个独特的方式来处理 DSR 请求，因为它与从社交网络中检索到的个人数据相关。社交内容是从社交媒体网络（如 Twitter、Facebook 和 YouTube）和数据索引或数据聚合服务收集的公开可用内容，用于响应客户在 Microsoft Social Engagement 中执行的搜索查询。社交内容不是客户数据。Microsoft Online Service 条款中介绍了有关处理、使用和存储社交内容的进一步限制。

### <a name="finding-personal-data"></a>查找个人数据

响应数据主体的请求的第一步是搜索并识别作为该请求主体的个人数据。Microsoft Social Engagement 存储以下数据：

#### <a name="for-social-media-users"></a>对于社交媒体用户

- Social Engagement 从社交平台获取的社交媒体用户数据（在 Social Engagement 中称为 *“作者”*）。可能包括姓名、用户名、个人资料图片、位置、网站和个人简历（如果作者提供）。

- Social Engagement 员工用来对作者进行分组和分类的作者标签，例如，影响者、竞争对手或粉丝。

#### <a name="for-employees"></a>对于员工

- 用户个人资料包括 Office 365 中管理的员工姓名、联系信息和个人资料图片。

- 已创建帖子提醒和走向提醒的员工提供的电子邮件地址。

- Social Engagement 中按员工进行身份验证以与社交平台上的其他人交互的社交媒体帐户（在 Social Engagement 中称为 *“社区个人资料”*）。它们归员工或组织所有，包括员工在社交平台上注册帐户时提供的数据。这些个人资料在社交媒体上代表组织，用于在 Social Engagement 应用程序内代表组织与帖子交互。

- Power BI 中的用户名，如果你的组织为 Power BI 使用 [Social Engagement 内容包](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/get-content-pack-for-power-bi)来分析社交媒体上的团队绩效。

此第一步（查找和查看所涉及的个人数据）将帮助你确定数据主体的请求是否符合组织有关接受或拒绝请求的要求。例如，查找并查看个人数据之后，你可能会确定该请求不符合组织的要求，因为这样做可能会对他人的权利和自由产生不利影响。

#### <a name="social-media-users-authors"></a>社交媒体用户（作者）

-   若要查找他们的个人数据，请遵循[查找和删除作者](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#find-and-delete-an-author)中的前四个步骤。

-   员工可以创建用于在社交平台上搜索某些定义内容的 Social Engagement 规则；这些搜索规则可能包含作者姓名。要确保找到这些规则，请查看以下相应帐户的社交帐户搜索规则：[Twitter](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/add-rules-search-topic#add-a-twitter-rule)、[Instagram](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/add-rules-search-topic#add-an-instagram-rule) 和 [YouTube](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/add-rules-search-topic#add-a-includetnyoutubeincludestn-youtubemd-rule)。

-   若要查找作者的作者标签，首先请按[作者](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/understand-filters#authors)[筛选帖子](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/use-filters#add-edit-or-remove-a-filter)，然后[查看作者标签](https://go.microsoft.com/fwlink/?linkid=864795)。

##### <a name="your-employees"></a>你的员工 

若要查找：

-   用户个人资料，请转到“Office 365 管理中心”[](https://portal.office.com/adminportal/home)。在“管理中心”**** 中，选择“用户”****。在“活动用户”**** 页面上，在列表中搜索用户。  
    在 Social Engagement 中，转到“设置”**\>**“用户管理”以查看自动与 Office 365 同步的信息。

-   提醒的收件人，遵循[以管理员身份管理提醒收件人](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator)中的前两个步骤。

-   按员工输入的社区个人资料数据，转到“设置”**\>**“社区个人资料”。（有关详细信息，请参阅[管理社区个人资料](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-social-profiles)。）

-   Power BI 中的用户名，打开 Social Engagement Power BI 仪表板并按员工姓名进行筛选。

### <a name="providing-a-copy-of-personal-data"></a>提供个人数据副本

GDPR 为数据主体提供了根据请求获取个人数据副本的权利。找到包含潜在响应请求的数据的客户内容后，由你和你的组织决定是否为数据主体提供副本。

#### <a name="social-media-users-authors"></a>社交媒体用户（作者）

- 若要导出作者的个人数据，请按照[导出作者信息](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#export-author-information)中的步骤将数据导出到 Excel 文件。

- 若要提取添加到特定作者的作者标签，你可以[导出作者标签数据](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#export-author-tags-data)。

##### <a name="your-employees"></a>你的员工
若要导出：

- 用户个人资料中的客户数据，转到[](https://portal.office.com/adminportal/home)“Office 365 管理中心”。在“管理中心”**** 中，选择“用户”****。在“活动用户”**** 页面上，搜索你要导出其数据的用户。删除目标用户之外的所有用户，然后选择“导出”**** 将数据导出到 .csv 文件，你可以在这里使用 Excel 查看信息。

- 提醒收件人（提醒中仅有的客户数据）的电子邮件地址。遵循[以管理员身份管理提醒收件人](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator)中的步骤。然后选择“导出”****，下载包括此收件人的提醒的 Excel 列表。

- Power BI 的用户名：“参与报告”[](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/get-content-pack-for-power-bi)在社交媒体上的团队绩效报告中显示用户名。若要导出此数据，请在 PowerBI 仪表板或[报告](https://docs.microsoft.com/power-bi/power-bi-report-add-filter)中按用户进行筛选，并[导出数据](https://docs.microsoft.com/power-bi/power-bi-visualization-export-data)。

### <a name="rectifying-personal-data"></a>纠正个人数据

更正不准确或不完整的个人数据：

#### <a name="social-media-users-authors"></a>社交媒体用户（作者）

-   必须要求数据所有者（作者）在社交平台（如 Twitter、WordPress 或 Tumblr）上进行更改。数据主体拥有社交媒体帐户中的数据，因此只有他们可以更改。一旦作者做出更改，Social Engagement 将自动同步修订后的详细信息。

-   作者标签，遵循[更改作者标签](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#change-author-tags)中的步骤。

##### <a name="your-employees"></a>你的员工

-   用户个人资料：若要对用户个人资料中的客户数据进行更改，请参阅[更改 Office 365 中的用户名和电子邮件地址](https://support.office.com/article/change-a-user-name-and-email-address-in-office-365-fb5ac074-e203-4e1f-9843-b9d1a3e03297)和[向 Office 365 添加个人资料照片](https://support.office.com/article/add-your-profile-photo-to-office-365-2eaf93fd-b3f1-43b9-9cdc-bdcd548435b7)。  
    这些更改会在 Social Engagement 中自动同步。若要查找这些更改，请转到“设置”****\>“用户管理”****。

-   提醒收件人：可以[更改提醒](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#change-an-alert)。

### <a name="restricting-the-processing-of-personal-data"></a>限制个人数据的处理

#### <a name="social-media-users-authors"></a>社交媒体用户（作者）
若要停止处理 Social Engagement 中作者的客户数据，请[删除作者](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#delete-an-author)。

这将阻止将来处理此数据主体以及任何将来帖子的数据，还会删除所有有关此作者的数据和此作者提供的数据。每当 Social Engagement 获得新的帖子时，都会自动检查作者先前是否已删除，并丢弃来自已删除作者的帖子。这不会影响用户在社交平台上的帐户。

##### <a name="your-employees"></a>你的员工

- 若要停止处理员工的客户数据，你可以在 Office 365 中[移除其许可证](https://support.office.com/article/remove-licenses-from-users-in-office-365-for-business-9b497c85-d0a4-4735-80fa-d3565bc05bd1)。这将删除所有与 Social Engagement 相关的项目，如用户角色和个人资料、所有相关的用户定义的自定义设置、提醒、活动地图和数据流。搜索主题和社区个人资料将不会删除；但是，管理员会继承已删除用户的社区个人资料的所有权，可以根据请求将其删除。

- 若要限制发送提醒电子邮件，可以按照[以管理员身份管理提醒收件人](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator)中的步骤将电子邮件地址从已添加到的所有提醒中删除。

### <a name="deleting-personal-data"></a>删除个人数据

GDPR 为数据主体提供了在某些情况下请求从控制者删除个人数据的权利。通过从组织移除此类数据的“被遗忘权”是 GDPR 中的一项关键保护措施。

#### <a name="social-media-users-authors"></a>社交媒体用户（作者）

若要永久删除 Social Engagement 中某个作者的所有个人数据，请删除此作者的完整社区个人资料。请参阅[](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors)[删除作者](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#delete-an-author)。  
一旦执行此操作，将无法撤销。这会删除 Social Engagement 上所有有关此作者的数据和此作者提供的数据。每当 Social Engagement 获得新的帖子时，都会自动检查作者先前是否已删除，并丢弃来自已删除作者的帖子。这不会影响用户在社交平台上的帐户。

若要删除作者标签，请参阅[删除作者标签](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#remove-author-tags)。

>[注意] 如果你被要求移除有关特定作者的信息，我们建议你首先确认该作者的身份以验证请求。若要确认其身份，可从其社交媒体帐户请求作者发送一条私人消息。

Social Engagement 已从多个社交平台（如 Twitter、WordPress、Tumblr）实现合规性源，以处理以前直接在社交平台上触发的类似帖子删除的信号。每次安装 Social Engagement，都会自动激活此功能，无需任何用户交互。此外，Social Engagement 还提供了一个机制，允许从 Social Engagement 上构建社交内容的服务（如 Dynamics 365 for Customer Engagement）继承这些信号。

##### <a name="your-employees"></a>你的员工

若要永久删除所有员工的客户数据，你可以在 Office 365 中[移除其许可证](https://support.office.com/article/remove-licenses-from-users-in-office-365-for-business-9b497c85-d0a4-4735-80fa-d3565bc05bd1)。

-   这将删除所有与 Social Engagement 相关的项目，如用户角色和个人资料、所有相关的用户定义的自定义设置、提醒、活动地图和数据流。搜索主题和社区个人资料将不会删除。（管理员会继承已删除用户的社区个人资料的所有权，可以根据请求将其删除。）

-   这些更改会在 Social Engagement 中自动同步。若要查找这些更改，请转到“设置”**\>**“用户管理”。

-   删除员工的个人数据时，将对 PowerBI 参与报告中的员工条目进行匿名处理。

你可以[删除社区个人资料](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-social-profiles#delete-a-social-profile)。

若要删除已添加到所有提醒的电子邮件地址，请执行[以管理员身份管理提醒收件人](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator)中的步骤。[](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator)

### <a name="exporting-personal-data"></a>导出个人数据
可以采用电子格式为数据主体提供其个人数据。

#### <a name="social-media-users-authors"></a>社交媒体用户（作者）

若要导出作者的个人数据，请按照[导出作者信息](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#export-author-information)中的步骤将数据导出到 Excel 文件。

若要提取添加到特定作者的作者标签，你可以[导出作者标签数据](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#export-author-tags-data)。

##### <a name="your-employees"></a>你的员工
若要导出：

- 用户个人资料中的客户数据，转到[](https://portal.office.com/adminportal/home)“Office 365 管理中心”。在“管理中心”**** 中，选择“用户”****。在“活动用户”**** 页面上，搜索你要导出其数据的用户。删除目标用户之外的所有用户，然后选择“导出”**** 将数据导出到 .csv 文件，你可以在这里使用 Excel 查看信息。

- 提醒收件人（提醒中仅有的个人数据）的电子邮件地址。请遵循[以管理员身份管理提醒收件人](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator)中的步骤。然后选择“导出”****，下载包括此收件人的提醒的 Excel 列表。

- Power BI 的用户名：“参与报告”[](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/get-content-pack-for-power-bi)在社交媒体上的团队绩效报告中显示用户名。若要导出此数据，请在 PowerBI 仪表板或[报告](https://docs.microsoft.com/power-bi/power-bi-report-add-filter)中按用户进行筛选，并[导出数据](https://docs.microsoft.com/power-bi/power-bi-visualization-export-data)。

## <a name="part-2-responding-to-dsrs-for-system-generated-logs"></a>第 2 部分：响应针对系统生成日志的 DSR

Microsoft 还为你提供了访问、导出和删除根据 GDPR 中“个人数据”的广泛定义可能被视为个人数据的系统生成日志。根据 GDPR，系统生成日志的示例包括：

-   产品和服务使用情况数据，例如用户活动日志

-   用户搜索请求和查询数据

-   作为系统功能一部分的产品和服务所生成的数据以及用户或其他系统的交互

<span id="_Toc511045103" class="anchor"><span id="_Toc511043191" class="anchor"><span id="_Toc511041446" class="anchor"><span id="_Toc511030410" class="anchor"><span id="_Toc510769888" class="anchor"></span></span></span></span></span>请注意，不支持限制或纠正系统生成日志中的数据。系统生成日志中的数据构成 Microsoft 云内执行的实际操作和诊断数据，对此类数据的修改将会损坏操作的历史记录，增加诈骗及安全风险。

### <a name="accessing-and-exporting-system-generated-logs"></a>访问和导出系统生成日志

管理员可以访问与特定用户使用 Dynamics 365 服务和应用程序的情况相关联的系统生成日志。若要访问和导出系统生成日志，请执行以下操作：

1.  转到 [Microsoft 服务信任门户](https://servicetrust.microsoft.com/)并使用 Dynamics 365 全局管理员的凭据登录。

2.  在页面顶部的“隐私”**** 下拉列表中，单击“数据主体请求”****。

3.  在“**数据主体请求**”页面的“**系统生成日志**”下，单击“**数据日志导出**”。

> “**数据日志导出**”随即显示。请注意，将显示由你的组织提交的导出数据请求列表。

4.  若要为用户创建新的请求，请单击“创建导出数据请求”****。

在创建新的请求后，它将列在“数据日志导出”**** 页面上，在这里你可以跟踪其状态。完成请求后，可以单击链接以访问系统生成日志，这些日志将在请求创建 30 内导出到你组织的 Azure 存储位置。数据将保存为常用的机器可读文件格式，如 JSON 和 XML。如果你还没有 Azure 帐户和 Azure 存储位置，将需要为你的组织创建 Azure 帐户和/或 Azure 存储位置，以便数据日志导出工具可以导出系统生成日志。

Azure 通过让组织以本机 JSON 格式将数据导出到指定 Azure 存储容器来支持此操作。[Microsoft Azure 存储 - Blob 存储简介](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage)文章。

**重要提示**：你必须是租户管理员才能从租户导出用户数据。

下表概述了如何访问和导出系统生成日志：

<table>
<tbody>
<tr class="odd">
<td align="left"><strong>“Microsoft 数据日志导出”工具需要多长时间才能完成请求？</strong>
<td align="left">这取决于若干因素。在大多数情况下，一到两天内可以完成，但最多可能需要 30 天。</td>
</tr>
<tr class="odd">
<td align="left"><strong>输出内容采用什么格式？</strong></td>
<td align="left">输出内容是结构化的机器可读文件（如 XML、CSV 或 JSON）。</td>
</tr>
<tr class="even">
<td align="left"><strong>“数据日志导出”工具会返回哪些数据？</strong></td>
<td align="left">“数据日志导出”工具会返回 Microsoft 存储的系统生成日志。导出的数据将跨越各种 Microsoft 服务，包括 Office 365、Azure 和 Dynamics。</td>
</tr>
<tr class="odd">
<td align="left"><strong>谁有权访问“数据日志导出”工具以提交对系统生成日志的访问请求？</strong></td>
<td align="left">Dynamics 365 全局管理员将有权访问 GDPR 日志管理器实用工具。</td>
</tr>
<tr class="even">
<td align="left"><strong>如何向用户返回数据？</strong></td>
<td align="left">数据将导出到你组织的 Azure 存储位置；由你组织的管理员来确定他们如何向用户显示/返回此数据。</td>
</tr>
<tr class="odd">
<td align="left"><strong>系统生成日志中的数据看上去是怎样的？</strong></td>
<td align="left"><p>JSON 格式的系统生成日志记录示例：</p>
<p>[{</p>
<p>  &quot;DateTime&quot;: &quot;2017-04-28T12:09:29-07:00&quot;,</p>
<p>  &quot;AppName&quot;: &quot;SharePoint&quot;,</p>
<p>  &quot;Action&quot;: &quot;OpenFile&quot;,</p>
<p>  &quot;IP&quot;: &quot;154.192.13.131&quot;,</p>
<p>  &quot;DevicePlatform&quot;: &quot;Windows 1.0.1607&quot;</p>
<p>}]</p></td>
</tr>
</tbody>
</table>

[注意] 出于安全和审核目的，部分功能将禁止导出或删除包含个人信息的系统生成日志，以维护此类信息的完整性。

### <a name="deleting-system-generated-logs"></a>删除系统生成日志
若要删除通过访问请求检索到的系统生成日志，必须从服务移除用户并永久删除其 Azure Active Directory 帐户。有关永久删除用户的说明，请参阅本指南的[“删除用户”](https://microsoft-my.sharepoint.com/personal/kated_microsoft_com/Documents/DSR%20Guide%20v4%20-(newly%20created%20for%20O365%20only).docx#_Deleting_a_user)部分。请务必注意，永久删除用户帐户操作一旦启动便无法恢复。

永久删除用户帐户，同时在 30 天内将用户数据从几乎所有 Dynamics 365 服务的系统生成日志中移除。

#### <a name="learn-more"></a>了解详细信息

[Microsoft 信任中心](https://www.microsoft.com/zh-CN/TrustCenter/Privacy/gdpr/default.aspx)
