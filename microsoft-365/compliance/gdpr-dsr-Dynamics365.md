---
title: 符合 GDPR 和 CCPA 的 Dynamics 365 数据主体请求
description: 了解如何查找个人数据并对其进行操作，并对 Dynamics 365 客户提出的 DSR 和 CCPA 请求作出响应。
keywords: Microsoft 365, Microsoft 365 教育版, Microsoft 365 文档, GDPR, CCPA
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
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 04ecbd6e52a56ea83f3b2e2eaebd02de20cfbe52
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817661"
---
# <a name="dynamics-365-data-subject-requests-for-the-gdpr-and-ccpa"></a>符合 GDPR 和 CCPA 的 Dynamics 365 数据主体请求

The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of it, requesting changes to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called in this document a *Data Subject Rights Request* or DSR request.

同样，加州消费者隐私法案 (CCPA) 规定了加州消费者的隐私权和义务，包括与 GDPR 的数据主体权利类似的权利，例如删除、访问和接收（可移植性）其个人信息的权利。  CCPA 还就某些披露规定了在选择行使权限时防止歧视的保障措施，并就分类为“销售”的特定数据传输提出了“选择退出/选择加入”要求。 “出售”广义定义为包含共享数据来换取有值对价的行为。 有关 CCPA 的详细信息，请参阅[加州消费者隐私法案](offering-ccpa.md)和[加州消费者隐私法案常见问题解答](ccpa-faq.md)。

本指南介绍了如何使用 Microsoft 的产品、服务和管理工具来帮助我们的控制者客户查找和处理个人数据以响应 DSR 请求。 具体而言，这包括如何查找、访问和处理驻留在 Microsoft 云中的个人数据或个人信息。 以下是本指南中所述的过程的快速概览：

- **发现：** 使用搜索和发现工具更轻松地查找可能是 DSR 请求主体的客户数据。 收集了潜在的响应性文档后，你便可以执行下列步骤中所述的一项或多项 DSR 操作来响应请求。 或者，可以确定请求不符合组织用于响应 DSR 请求的指导原则。
- **访问：** 检索驻留在 Microsoft 云中的个人数据，如果提出请求，还制作可供数据主体使用的个人数据副本。
- **纠正：** 进行更改或者对个人数据实施其他请求的操作（如果适用）。
- **限制：** 通过移除各种在线服务的许可证，或者在可能的情况下关闭所需的服务，限制对个人数据的处理。 你可以
- **删除：** 永久移除驻留在 Microsoft 云中的个人数据。
- **导出/接收（可移植性）：** 向数据主体提供个人数据或个人信息的电子副本（采用机器可读格式）。 根据 CCPA 的定义，个人信息是指与已识别或可识别人员相关的任何信息。 个人的私人、公共或工作角色之间没有任何区别。 所定义的“个人信息”术语与 GDPR 下的“个人信息”大致相同。 但是，CCPA 还包括家人和家庭数据。 有关 CCPA 的详细信息，请参阅[加州消费者隐私法案](offering-ccpa.md)和[加州消费者隐私法案常见问题解答](ccpa-faq.md)。

本指南中的每个部分概述了数据控制者组织为响应对 Microsoft 云中个人数据的 DSR 请求而采取的技术过程。

### <a name="gdpr-terminology"></a>GDPR 术语

下面提供了与本指南相关的术语定义：

- **控制者：** 单独或与其他人一起确定个人数据处理的用途和途径的自然人或法人、公共机构、机关或其他实体；如果欧盟或成员国法律确定了此类处理的用途和途径，欧盟或成员国法律可能会规定控制者或具体提名条件。
- **个人数据和数据主体：** 身份已识别或可识别的自然人（“数据主体”）的任何相关信息；身份可识别的自然人是指可被直接或间接识别的自然人，尤其是通过参考姓名、证件号码、位置数据、联机标识符等标识，或通过参考特定于该自然人的身体、生理、基因、精神、经济、文化或社会标识的一个或多个因素进行识别。
- **处理者：** 代表控制者处理个人数据的自然人或法人、公共机构、机关或其他主体。
- **客户数据：** 客户或代表客户通过使用企业服务提供给 Microsoft 的所有数据，包括所有文字、声音、视频或图像文件以及软件。 客户数据包括 (1) 最终用户的身份信息（例如，Azure Active Directory 中的用户名和联系人信息）和客户上传到特定服务或者在特定服务中创建的客户内容（例如，Azure 存储帐户中的客户内容，Azure SQL 数据库的客户内容，或 Azure 虚拟机中的客户虚拟机映像）。
- **系统生成日志：** Microsoft 生成的日志和相关数据，可帮助 Microsoft 向用户提供企业服务。 系统生成日志主要包括化名数据，例如唯一标识符 — 这通常是系统生成的无法单独识别个人但用于向用户提供企业服务的一个数字。 系统生成日志还可能包含有关最终用户的身份信息，例如用户名。

### <a name="how-this-guide-can-help-you-meet-your-controller-responsibilities"></a>本指南将如何帮助你履行控制者职责

本指南分为两个部分，介绍了如何使用 Dynamics 365 产品、服务和管理工具来帮助你查找和处理 Microsoft 云中的数据以响应根据 GDPR 行使其权利的数据主体提出的请求。 第一部分处理客户数据中包括的个人数据，第二部分处理系统生成日志中捕获的其他化名个人数据。

- **第 1 部分：响应对客户数据中包括的个人数据的数据主体权利 (DSR) 请求：** 本指南第 1 部分讨论如何访问、纠正、限制、删除个人数据以及将个人数据从 Dynamics 365 应用程序（软件即服务）导出，这些数据会作为提供给联机服务的客户数据的一部分进行处理。
- **第 2 部分：响应对假名数据的数据主体权限请求：** 当你使用 Dynamics 365 企业服务时，Microsoft 会生成某些信息（在本文档中称为*系统生成日志*）来提供服务，它仅限于最终用户在系统中标识其操作时留下的使用足迹。 虽然在不使用其他信息的情况下，此数据无法归于特定数据主体，但根据 GDPR 规定，有些数据被视为个人数据。 本指南的第 2 部分讨论如何访问、删除和导出由 Dynamics 365 生成的系统生成日志。

### <a name="preparing-for-data-subject-rights-investigations"></a>准备数据主体权限调查

当数据主体行使其权利并提出请求时，请考虑以下几点：

- 通过使用数据主体在请求中提供给你的信息，正确识别人员和角色 — 例如员工、客户、供应商。 此信息可能是姓名、员工 ID 或客户编码或其他标识符。
- Record the data and time of the request. (You have 30 days to complete the request.)
- Affirm that the request meets your organization's requirements for honoring or declining a data subject's request. For example, you must make sure that executing the request doesn't conflict with any other legal, financial, or regulatory obligations that you have, or infringe on the rights and freedoms of others.
- 确认你有与该请求相关的信息。

## <a name="part-1-responding-to-data-subject-rights-requests-for-personal-data-included-in-customer-data"></a>第 1 部分：响应针对客户数据中包含的个人数据的数据主体权限请求

In the articles below, you'll find information to help you prepare for and respond to DSR requests for personal data included in customer data processed in Dynamics 365. It is important to note that personal data could be present in other categories of data processed by Microsoft during the course of the service of an online services subscription, such as administrator data or support data defined in the Microsoft Privacy Statement. This document is limited to assist you in the process of discovery and management of DSR requests affecting personal data present in the customer data that you have provided to Dynamics 365.

Dynamics 365 is an online service that offers multiple data processing capabilities as a software-as-a-service (SaaS). As such, Dynamics 365 offers a broad array of functionality intended to process a diverse collection of data, which could vary by nature, purpose or other specific attributes, such as sales data, transactions, financials, HR information, etc. In light of this diversity, Dynamics 365 offers multiple forms, fields, schemas, end points, and logic to process customer data, which is also reflected in the multiple ways in which DSR requests could be addressed in each application. When Dynamics 365 applications offer several ways to address specific DSR requests, we will note those in this guide by pointing to the technical descriptions offered by each application.

### <a name="dynamics-365"></a>Dynamics 365

#### <a name="finding-customer-data"></a>查找客户数据

响应数据主体权利请求的第一步是搜索并标识作为请求主体的客户数据。

Classifying customer data appropriately is the cornerstone of working with personal data in Dynamics 365 Customer Engagement business applications. Dynamics 365 for Customer Engagement offers flexibility to build out an application extension around data classification. Proper classification enables you to identify information as personal data, thereby making it possible to locate and retrieve it when responding to requests from a data subject. It can also help enable compliance with legislative and regulatory requirements for collecting and managing personal data.

Microsoft provides capabilities that assist you in responding to data subject rights requests, and thereby accessing customer data. However, it is your responsibility to ensure that personal data is located and classified appropriately.

***Dynamics 365 for Customer Engagement*** 提供了多种方法在记录中搜索个人数据：高级查找搜索、搜索记录。 所有这些功能都可以用来识别（查找）个人数据。

- [高级查找搜索](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)
- [搜索记录](https://docs.microsoft.com/dynamics365/customer-engagement/basics/search-records)，跨多个记录类型

在 Dynamics 365 for Marketing 中，还有以下其他功能：

1. [构建 Power BI 报告](https://docs.microsoft.com/power-bi/service-connect-to-microsoft-dynamics-crm)，以筛选并识别客户数据。
2. 对市场营销执行的联系人和对象使用 Insight Views，以识别可能包含客户数据的其他数据点。

***Dynamics 365 Customer Service Insights*** 提供了一系列资源，可帮助你[查找客户数据](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-discovery)，以响应客户的 GDPR 请求。 

***Dynamics 365 for Finance and Operations*** 提供了几种搜索客户数据的方法。 你作为租户管理员，可以执行以下操作来搜索客户数据：

- 按照用于快速发现个人数据的方式整理客户数据，请参阅[如何分类数据库存](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#detailed-inventory)完成此操作。
- 使用[人员搜索报告](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report)查找并收集个人数据。
- 通过创建新实体或扩展现有实体，[扩展人员搜索报告](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report)。
- 使用搜索和筛选功能查找特定个人数据以及通过使用 Microsoft Office 导出功能导出该数据或使用浏览器扩展将该信息打印到 .pdf。
- 创建用于定位和导出个人数据的自定义表单。
- 创建允许经过身份验证的客户查看其个人数据的外部门户或网站。

***Dynamics 365 Business Central*** 提供了几种搜索客户数据的方法。 有关详细信息，请参阅[对数据进行搜索、筛选和排序](https://docs.microsoft.com/dynamics365/business-central/ui-enter-criteria-filters)。

***Dynamics 365 for Talent*** 提供了高级搜索和筛选功能来查找特定个人数据，并提供了 Microsoft Office 导出功能导出该信息或使用浏览器扩展将该信息打印到 .pdf。

- 使用[人员搜索报告](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report)查找并收集客户数据。
- 通过创建新实体或扩展现有实体，[扩展人员搜索报告](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report)。

### <a name="providing-a-copy-of-customer-data"></a>提供客户数据副本

可使用全面的实体导出功能导出 ***Dynamics 365 for Customer Engagement*** 中的客户数据。 客户数据可以导出到静态的 Excel 文件以促进数据移植请求。 然后，使用 Excel，可以编辑要包含在移植请求中的个人数据，然后另存为常用的机器可读格式，例如 .csv 或 .xml。 可通过[公共数据服务 Web API](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/overview) 导出 Dynamics 365 for Customer Engagement 记录。

Additionally, for Dynamics 365 for Marketing a [dedicated API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) is provided that allows customer to build extensions that retrieve additional records of captured customer interactions that may contain personal data. The API loads all the relevant information from the back-end system and assembles it into a single, portable document.

***Dynamics 365 Customer Service Insights*** 允许你使用数据导出功能[提供客户数据的副本](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export)。

可使用全面的实体导出功能导出 ***Dynamics 365 for Finance and Operations*** 中的客户数据。 通过使用[*数据管理和集成实体*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity)，租户管理员可利用提供的实体、创建新实体或扩展现有实体，以使用[*数据导入和导出作业*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job)将个人数据重复导出到 Excel 或各种其他常用格式。  或者，可以将许多列表导出到静态 Excel 文件以促进数据移植请求。 将客户数据导出到 Excel 后，可以编辑要包含在移植请求中的个人数据，然后将该文件另存为常用的机器可读格式，例如 .csv 或 .xml。 你还可以考虑使用*人员搜索报告*为数据主体提供已分类为个人数据的数据。

在 ***Dynamics 365 Business Central*** 中，可使用两种功能向数据主体提供客户数据副本：

你可以将客户数据导出到 Excel 文件。 然后，在 Excel 中，可以编辑要包括在移植请求中的客户数据，并将其另存为常用的机器可读格式，如 .csv 或 .xml。 有关详细信息，请参阅[将业务数据导出到 Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data)。

在 ***Dynamics 365 for Talent*** 中，可以使用[扩展人员搜索报告](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report)收集信息以支持对数据主体个人数据副本的请求。

### <a name="rectifying-customer-data"></a>纠正客户数据错误

***Dynamics 365 for Customer Engagement*** 提供以下方法来更正不准确或不完整的客户数据或擦除客户数据：

- 使用“查找客户数据”中提及的功能搜索客户数据，以及直接在客户参与表单中编辑数据。 可直接修改在单行或多行中完成的编辑。
- 批量编辑多个客户参与记录，你可以利用 Microsoft Office 加载项将数据导出到 Microsoft Excel，进行更改，然后将修改过的数据从 Excel 导入 Dynamics 365 for Customer Engagement。

此外，在 Dynamics 365 for Marketing 中，还可以：

- 通过直接编辑一行或多行“更新我的数据”登录页面
- Prepare a [subscription centers](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/set-up-subscription-center) page that has as many editable contact fields that can be included. This enables an end user to update their own information as much as possible.

***Dynamics 365 Customer Service Insights*** 还提供了一些功能，使组织能够[纠正或更改客户数据](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-summary)。

在 ***Dynamics 365 for Finance and Operation*** 中，还可能使用[*自定义工具*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page)，但你需要负责决策和实施。

***Dynamics 365 Business Central*** 提供了两种方法来更正不准确或不完整的客户数据。

To quickly bulk-edit multiple Business Central records, you can export lists to Excel using the [Business Central Excel Add-in](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) to correct multiple records, and then publish the modified data from Excel in Business Central. For details, see [Exporting your Business Data to Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).

可以更改存储在任何字段中的客户数据 — 例如客户卡片中有关客户的信息 — 通过手动编辑包含目标个人数据的数据元素。 有关详细信息，请参阅[输入数据](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data)。

#### <a name="brief-note-about-modifying-entries-in-business-transactions"></a>有关修改业务交易条目的简短说明

Transactional records, such as general, customer, and tax ledger entries, are essential to the integrity of an enterprise resource planning system. Personal data that is part of a financial or other transaction is kept "as is" for compliance with financial laws (for example, tax laws), prevention of fraud (such as security audit trail), or compliance with industry certifications. Therefore, Dynamics 365 for Finance and Operations and Dynamics 365 Business Central restrict modifying data in such records.

If you store personal data in business transaction records, the only way to correct, delete, or restrict processing of personal data to honor a data subject's request is to use the Dynamics 365 Business Central [customization capabilities](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/index). Th[](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#reasons-why-certain-personal-data-may-not-be-modified-or-deleted)e decision to honor a modification data subject request and implementation thereof is your responsibility.

### <a name="restricting-the-processing-of-customer-data"></a>限制客户数据的处理

当你收到来自数据主体的限制处理客户数据的请求时，可轻松从联机服务提取受影响的客户数据并将其存储在单独的容器中（即具有数据隔离功能的内部存储或单独的网络服务），独立于任意云应用程序提供的处理功能。

***Dynamics 365 Business Central*** 提供了替代机制，例如数据处理阻止，让用户能够阻止特定数据主体的记录。 有关详细信息，请参阅[限制数据主体的数据处理](https://docs.microsoft.com/dynamics365/business-central/admin-responding-to-requests-about-personal-data#restrict-data-processing-for-a-data-subject)。 当记录被标记为已阻止时，Dynamics 365 Business Central 将停止处理该数据主体的客户数据。 你不能创建使用被阻止记录的新交易；例如，如果客户或销售人员被阻止，则不能为客户创建新发票。

### <a name="deleting-customer-data"></a>删除客户数据

当数据主体要求你删除其客户数据时，有几种方法可执行此操作：

- 批量编辑多个 Dynamics 365 记录，你可以利用 Microsoft Office 加载项将数据导出到 Microsoft Excel，进行更改，然后将修改过的数据从 Excel 导入回联机服务。
- 你可以通过查找想要删除的数据然后手动删除包含目标客户数据的数据元素，删除存储在任何字段中的客户数据，例如对表示数据主体的联系人记录和包含个人数据的其他记录使用硬性删除。

此外，在 Dynamics 365 for Marketing 中，删除联系人将确保也移除包含个人信息的交互数据。 对于任何自定义字段或实体，必须自定义你的系统，以确保将所有客户数据从相关记录删除和/或取消与联系人数据的链接，以便移除所有个人信息。 详细信息：[《开发人员指南（市场营销）》](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/marketing-developer-guide)。

***Dynamics 365 Customer Service Insights*** 还为组织提供了用于[删除客户数据](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-delete)的功能。

或者，在 ***Dynamics 365 for Finance and Operations*** 中，可能使用[*自定义工具*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page)擦除/修改客户数据。

在 ***Dynamics 365 Business Central*** 中，当数据主体要求你删除其碰巧包括在你的客户数据中的个人数据时，有几种方法可处理此请求：

- To quickly bulk-edit multiple Business Central records, you can export data to Excel using the [Business Central Excel Add-in](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) to delete multiple records, and then publish these changes from Excel back in Business Central. For details, see [Exporting your Business Data to Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).
- 可以通过手动删除包含目标客户数据的数据元素来删除存储在任何字段中的客户数据。 有关详细信息，请参阅[输入数据](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data)。
- 你可以直接删除客户数据，例如通过删除联系人然后运行“删除已取消交互日志条目”批处理作业来删除该联系人的交互。
- 你可以[删除文档](https://docs.microsoft.com/dynamics365/business-central/admin-manage-documents)，包含诸如备忘录和已过帐的销售与采购发票等客户数据的文档。

Besides bulk or individual deletion of discrete records, please note that only terminated workers can be fully deleted from ***Dynamics 365 for Talent***. [Follow these steps to delete terminated workers](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/respond-dsr-request-talent#additional-notes-that-apply-to-requests-for-personal-data).

### <a name="exporting-customer-data"></a>导出客户数据

若要响应数据移植请求，可使用全面的实体导出功能导出 ***Dynamics 365 for Customer Engagement*** 中的客户数据。 客户数据可以导出到静态的 Excel 文件以促进数据移植请求。 然后，使用 Excel，可以编辑要包含在移植请求中的个人数据，然后另存为常用的机器可读格式，例如 .csv 或 .xml。

Additionally, for Dynamics 365 for Marketing a [dedicated API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) is provided that allows customer to build extensions that retrieve additional records of captured customer interactions that may contain personal data. The API loads all the relevant information from the back-end system and assembles it into a single, portable document.

对于 ***Dynamics 365 Customer Service Insights***，你可以通过 Azure 管理门户来[导出客户数据](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export)。

***Dynamics 365 for Finance and Operations*** 提供了[数据管理和集成实体](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity)，可用于启用提供的实体、新创建的实体或扩展的实体，以使用[数据导入和导出作业](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job)将个人数据重复导出到 Excel 或各种其他常用格式。  或者，可以将许多列表导出到静态 Excel 文件以促进数据移植请求。 将客户数据以这种方式导出到 Excel 后，你可以编辑要包括在移植请求中的个人数据，然后将该文件另存为常用的机器可读格式，例如 .csv 或 .xml。

Dynamics 365 for Finance and Operations 和 ***Dynamics 365 for Talent*** 都提供了人员搜索报告，可为数据主体提供已分类为个人数据的数据。 

***Dynamics 365 Business Central*** 提供以下功能：

- 你可以将客户数据导出到 Excel 文件。 然后，在 Excel 中，可以编辑要包括在移植请求中的客户数据，并将其另存为常用的机器可读格式，如 .csv 或 .xml。 有关详细信息，请参阅[将业务数据导出到 Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data)。
- 你可以将客户数据导出到 Excel 文件。 然后，在 Excel 中，可以编辑要包括在移植请求中的客户数据，并将其另存为常用的机器可读格式，如 .csv 或 .xml。 有关详细信息，请参阅[将业务数据导出到 Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data)。


## <a name="part-2-responding-to-dsrs-for-system-generated-logs"></a>第 2 部分：响应针对系统生成日志的 DSR

Microsoft also provides you with the ability to access, export, and delete system-generated logs that may be deemed personal under the GDPR's broad definition of "personal data." Examples of system-generated logs that may be deemed personal under GDPR include:

- 产品和服务使用情况数据，例如用户活动日志
- 用户搜索请求和查询数据
- 作为系统功能一部分的产品和服务所生成的数据以及用户或其他系统的交互

Note that the ability to restrict or rectify data in system-generated logs is not supported. Data in system-generated logs constitutes factual actions conducted within the Microsoft cloud and diagnostic data, and modifications to such data would compromise the historical record of actions and increase fraud and security risks.

### <a name="accessing-and-exporting-system-generated-logs"></a>访问和导出系统生成日志

Admins can access system-generated logs associated with a particular user's use of Dynamics 365 services and applications. To access and export system-generated logs:

1. 转到 [Microsoft 服务信任门户](https://servicetrust.microsoft.com/)并使用 Dynamics 365 全局管理员的凭据登录。
2. 在页面顶部的“**隐私**”下拉列表中，单击“**数据主体请求**”。
3. 在“**数据主体请求**”页面的“**系统生成日志**”下，单击“**数据日志导出**”。
    > [!NOTE]
    > The **Data Log Export** is displayed. Note that a list of export data requests submitted by your organization is displayed.
4. 若要为用户创建新的请求，请单击“创建导出数据请求”****。

After you create a new request, it will be listed on the **Data Log Export** page where you can track its status. After a request is complete, you can click a link to access the system-generated logs, which will be exported to your organization's Azure storage location within 30 days of creating the request. The data will be saved in common, machine-readable file formats such as JSON or XML. If you don't have an Azure account and Azure storage location, you'll need to create an Azure account and/or Azure storage location for your organization so that the Data Log Export tool can export the system-generated logs.

Azure 通过让组织以本机 JSON 格式将数据导出到指定 Azure 存储容器来支持此操作。[Microsoft Azure 存储 — Blob 存储简介](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage)文章。 检索到的数据不包括可能会危及服务安全性和稳定性的数据。

> [!IMPORTANT]
> 你必须是租户管理员才能从租户中导出用户数据。

下表概述了如何访问和导出系统生成日志：

| | |
|:----|:---|
| | |
|**“Microsoft 数据日志导出”工具需要多长时间才能完成请求？**| This can depend on several factors. In most cases it should complete in one or two days, but it can take up to 30 days. |
|**输出内容采用什么格式？**| 输出内容是结构化的机器可读文件（如 XML、CSV 或 JSON）。 |
|**“数据日志导出”工具会返回哪些数据？**| “数据日志导出”工具会返回 Microsoft 存储的系统生成日志。 导出的数据将跨越各种 Microsoft 服务，包括 Office 365、Azure 和 Dynamics。 |
|***谁有权访问“数据日志导出”工具以提交对系统生成日志的访问请求？**| Dynamics 365 全局管理员将有权访问 GDPR 日志管理器实用工具。 |
|**如何向用户返回数据？**| 数据将导出到你组织的 Azure 存储位置；由你组织的管理员来确定他们如何向用户显示/返回此数据。 |
|**系统生成日志中的数据看上去是怎样的？**| JSON 格式的系统生成日志记录示例： <br><br> "DateTime": "2017-04-28T12:09:29-07:00", <br> "AppName": "SharePoint", <br> "Action": "OpenFile", <br> "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" |

### <a name="deleting-system-generated-logs"></a>删除系统生成日志

要删除通过访问请求检索的系统生成日志，必须从服务中删除该用户，然后永久删除其 Azure Active Directory 帐户。 有关如何永久删除用户的说明，请参阅“Azure 数据主体请求”主题中的[步骤 5：删除](gdpr-dsr-azure.md#step-5-delete)部分。 请务必注意，永久删除用户帐户的操作一旦启动便不可逆。 永久删除用户帐户将在 30 天内从几乎所有 Dynamics 365 服务的系统生成日志中删除用户数据（不包括可能会危及服务安全性和稳定性的数据）。

## <a name="learn-more"></a>了解详细信息

- [Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
