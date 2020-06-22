---
title: GDPR 和 CCPA 下规定的 Office 365 数据主题要求
description: 了解 GDPR 和 CCPA 下规定的用户权限，以及 Office 365 如何帮助企业查找和处理数据以响应 DSR。
keywords: Office 365, DSR, Microsoft 365, Microsoft 365 教育版, Microsoft 365 文档, GDPR, CCPA
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
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 00ad2290a252ad014e9b364d9aa5ce59f94c6516
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817641"
---
# <a name="office-365-data-subject-requests-for-the-gdpr-and-ccpa"></a>符合 GDPR 和 CCPA 的 Office 365 数据主体请求

## <a name="introduction-to-dsrs"></a>DSR 简介

The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of it, requesting changes to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request* or DSR. The controller is obligated to promptly consider each DSR and provide a substantive response either by taking the requested action or by providing an explanation for why the DSR cannot be accommodated by the controller. A controller should consult with its own legal or compliance advisers regarding the proper disposition of any given DSR.

同样，加州消费者隐私法案 (CCPA) 规定了加州消费者的隐私权和义务，包括与 GDPR 的数据主体权利类似的权利，例如删除、访问和接收（可移植性）其个人信息的权利。 CCPA 还就某些披露规定了在选择行使权限时防止歧视的保障措施，并就分类为“销售”的特定数据传输提出了“选择退出/选择加入”要求。 “出售”广义定义为包含共享数据来换取有值对价的行为。 有关 CCPA 的详细信息，请参阅[加州消费者隐私法案](offering-ccpa.md)和[加州消费者隐私法案常见问题解答](ccpa-faq.md)。

本指南介绍了如何使用 Office 365 产品、服务和管理工具来帮助查找和处理个人数据或个人信息以响应 DSR。 具体而言，这包括如何查找、访问和处理驻留在 Microsoft 云中的个人数据或个人信息。 以下是本指南中所述的过程的快速概览：

- **发现：** 使用搜索和发现工具更轻松地查找可能是 DSR 主体的客户的数据。 收集了潜在的响应性文档后，你便可以执行下列步骤中所述的一项或多项 DSR 操作来响应请求。 或者，你也可以确定请求是否不符合组织的 DSR 响应指南。
- **访问：** 检索驻留在 Microsoft 云中的个人数据，如果提出请求，还制作可供数据主体使用的个人数据副本。
- **纠正：** 进行更改或者对个人数据实施其他请求的操作（如果适用）。
- **限制：** 通过移除各种 Microsoft 云服务的许可证，或者在可能的情况下关闭所需的服务，限制对个人数据的处理。 此外还可以从 Microsoft 云中删除数据，并将其保留在本地或其他位置。
- **删除：** 永久删除保存在 Microsoft 云中的个人数据。
- **导出/接收（可移植性）：** 向数据主体提供个人数据或个人信息的电子副本（采用机器可读格式）。 根据 CCPA 的定义，个人信息是指与已识别或可识别人员相关的任何信息。 个人的私人、公共或工作角色之间没有任何区别。 所定义的“个人信息”术语与 GDPR 下的“个人信息”大致相同。 但是，CCPA 还包括家人和家庭数据。 有关 CCPA 的详细信息，请参阅[加州消费者隐私法案](offering-ccpa.md)和[加州消费者隐私法案常见问题解答](ccpa-faq.md)。

### <a name="terminology"></a>术语

下面提供了与本指南相关的 GDPR 术语定义。

- **控制者：** 单独或与其他人一起确定个人数据处理的用途和途径的自然人或法人、公共机构、机关或其他实体；如果欧盟或成员国法律确定了此类处理的用途和途径，欧盟或成员国法律可能会规定控制者或具体提名条件。
- **个人数据和数据主体：** 身份已识别或可识别的自然人（“数据主体”）的任何相关信息；身份可识别的自然人是指可被直接或间接识别的自然人，尤其是通过参考姓名、证件号码、位置数据、联机标识符等标识，或通过参考特定于该自然人的身体、生理、基因、精神、经济、文化或社会标识的一个或多个因素进行识别。
- **处理者：** 代表控制者处理个人数据的自然人或法人、公共机构、机关或其他主体。
- **客户数据：** 客户或代表客户通过使用企业服务提供给 Microsoft 的所有数据，包括所有文字、声音、视频或图像文件以及软件。 客户数据包括 (1) 可识别的最终用户信息（例如，Azure Active Directory 中的用户名和联系信息）和客户上传至或在特定服务中创建的客户内容（例如，Word 或 Excel 文档中或者 Exchange Online 电子邮件文本中的客户内容；添加到 SharePoint Online 网站或保存至 OneDrive for Business 帐户的客户内容）。
- **系统生成日志：** Microsoft 生成的日志和相关数据，可帮助 Microsoft 向用户提供企业服务。 系统生成日志主要包括化名数据，例如唯一标识符 - 这通常是系统生成的无法单独识别个人但用于向用户提供企业服务的一个数字。 系统生成日志还可能包含最终用户的身份信息，例如用户名。

### <a name="how-to-use-this-guide"></a>如何使用本指南

本指南分为四个部分，可帮助你查找与你的用例相关的信息。

- **[第 1 部分：响应针对客户数据的 DSR](#part-1-responding-to-dsrs-for-customer-data)：***客户数据*是指在运营企业的日常操作中，在 Office 365 中生成和存储的数据。 可用于创作数据的最常用 Office 365 应用程序包括 Word、Excel、PowerPoint、Outlook 和 OneNote。 Office 365 还包括 SharePoint Online、Teams 和 Forms 等应用程序，可用于更好地与他人协作。 本指南的第 1 部分讨论如何发现 Office 365 应用程序中用于在 Office 365 联机服务中创作和存储数据的访问、纠正、限制、删除和导出数据。 它介绍了由 Microsoft 充当你组织的数据处理者，因而租户管理员可使用 DSR 功能的产品和服务。
- **[第 2 部分：响应与 Office 365 生成的见解相关的 DSR](#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365)：** Office 365 通过 Delve、MyAnalytics 和 Workplace Analytics 等服务提供一些见解。 本指南第 2 部分介绍了这些见解是如何生成的，以及如何响应与它们相关的 DSR。
- **[第 3 部分：响应针对系统生成日志的 DSR](#part-3-responding-to-dsrs-for-system-generated-logs)：** 在使用 Office 365 企业服务时，Microsoft 会生成某些信息（如记录在线服务中功能的使用情况或性能的服务日志）。 大部分服务生成的数据包含 Microsoft 生成的匿名标识符，因此，此类别在本文档中称为“*系统生成日志*”。 虽然在不使用其他信息的情况下，此数据无法归于特定数据主体，但根据 GDPR 针对“个人数据”的定义，有些数据被视为个人数据。 本指南的第 3 部分讨论如何访问、删除和导出由系统生成日志。
- **[第 4 部分：帮助响应 DSR 的其他资源s](#part-4-additional-resources-to-assist-you-with-dsrs)：** 本指南的第 4 部分列出了使用某些 Office 365 产品和服务时，由 Microsoft 作为数据控制者的有限场景。

>[!NOTE]
>In most cases, when users in your organization use Microsoft Office 365 products and services, you are the data controller and Microsoft is the processor. As a data controller, you are responsible for responding to the data subject directly. To assist you with this, Parts 1-3 of this guide detail the technical capabilities available to your organization to respond to a DSR request. In some limited scenarios, however, Microsoft will be the data controller when people use certain Office 365 products and services. In these cases, the information in Part 4 provides guidance on how data subjects can submit DSR requests to Microsoft.

### <a name="office-365-national-clouds"></a>Office 365 区域云

The Microsoft Office 365 services are also available in the following national cloud environments: [Office 365 Germany](https://docs.microsoft.com/microsoft-365/admin/admin-overview/learn-about-office-365-germany), [Office 365 operated by 21Vianet (China)](https://docs.microsoft.com/microsoft-365/admin/services-in-china/services-in-china), and [Office 365 US Government](https://www.microsoft.com/microsoft-365/government/compare-office-365-government-plans). Most of the guidance for managing data subject requests described in this document applies to these national cloud environments. However, due to the isolated nature of these environments, there are some exceptions. Where notable for a given subsection, these exceptions are called out in a corresponding note.

### <a name="hybrid-deployments"></a>混合部署

Your organization may consist of Microsoft offerings that are a combination of cloud-based services and on-premises server products. In general, a hybrid deployment is typically the sharing of user accounts (identity management) and resources (such as mailboxes, web sites, and data) that exist in the cloud and on-premises. Common hybrid scenarios include:

- Exchange 混合部署，其中某些用户使用本地邮箱，其他用户则使用 Exchange Online 邮箱。
- SharePoint 混合部署，其中站点和文件服务器均位于本地，而 OneDrive for Business 帐户在 Office 365 中。
- 与 Azure Activity Directory 同步的本地身份管理系统 (Active Directory)，它是 Office 365 的基础目录服务。

When responding to a DSR request, you may have to determine if data that's responsive to a DSR request is in the Microsoft cloud or in your on-premise organization, and then take the appropriate steps to respond to that request. The Office 365 Data Subject Request Guide (this guide) provides guidance for responding to cloud-based data. For guidance for data in your on-premises organization, see [GDPR for Office on-premises Servers](https://docs.microsoft.com/Office365/Enterprise/gdpr-for-office-servers).

## <a name="part-1-responding-to-dsrs-for-customer-data"></a>第 1 部分：响应针对客户数据的 DSR

响应针对客户数据的 DSR 的相关指导分为以下四个部分：

- [使用内容搜索电子数据展示工具响应 DSR](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)
- [使用应用内功能响应 DSR](#using-in-app-functionality-to-respond-to-dsrs)
- [响应 DSR 纠正请求](#responding-to-dsr-rectification-requests)
- [响应 DSR 限制请求](#responding-to-dsr-restriction-requests)

### <a name="how-to-determine-the-office-365-applications-that-may-be-in-scope-for-a-dsr-for-customer-data"></a>如何确定可能属于针对客户数据的 DSR 范围内的 Office 365 应用程序

帮助确定搜索个人数据的位置或要搜索的内容，这有助于确定组织中的用户可用于在 Office 365 中创建和存储数据的 Office 365 应用程序。 了解此信息可缩小属于 DSR 范围内的 Office 365 应用程序的范围，帮助确定如何搜索和访问与 DSR 相关的个人数据。 具体而言，这意味着是否可以使用内容搜索工具，或者是否必须使用在其中创建了数据的应用程序的应用内功能。

A quick way to identify the Office 365 applications that people in your organization are using to create Customer Data is to determine which applications are included in your organization's Microsoft 365 for business subscription. To do this, you can access user accounts in the Office 365 admin portal and look at the product licensing information. See [Assign licenses to users](../admin/manage/assign-licenses-to-users.md).

## <a name="using-the-content-search-ediscovery-tool-to-respond-to-dsrs"></a>使用内容搜索电子数据展示工具响应 DSR

When looking for personal data within the larger set of data your organization creates and stores using in Office 365, you may want to first consider which applications people have most likely used to author the data you're looking for. Microsoft estimates that over 90% of an organization's data that is stored in Office 365 is authored in Word, Excel, PowerPoint, OneNote, and Outlook. Documents authored in these Office applications, even if purchased through Microsoft 365 Apps for enterprise or an Office perpetual license, are most likely stored on a SharePoint Online site, in a user's OneDrive for Business account, or in a user's Exchange Online mailbox. That means you can use the Content Search eDiscovery tool to search (and perform other DSR-related actions) across SharePoint Online sites, OneDrive for Business accounts, and Exchange Online mailboxes (including the sites and mailboxes associated with Microsoft 365 Groups, Microsoft Teams, EDU Assignments) to find documents and mailbox items that may be relevant to the DSR you're investigating. You can also use the Content Search tool to discover Customer Data authored in other Office 365 applications.

下表列出了用户用于创建客户创作内容（可使用内容搜索工具发现）的 Office 365 应用程序。 DSR 指南的此部分提供了有关如何发现、访问、导出和删除使用这些 Office 365 应用程序创建的数据的指南。

***表 1：可使用内容搜索在其中查找客户数据的应用程序***

| | |
| :---: | :---:|
![日历图标](../media/O365-DSR-Doc-Final_image3.png) <br> 日历 | ![SharePoint 图标](../media/o365-sharepoint-64x64.png) <br> SharePoint  |
| ![Excel 图标](../media/o365-excel-64x64.png) <br> Excel | ![Skype for Business 图标](../media/o365-skypeforbusiness-64x64.png) <br> Skype for Business |
| ![Office Lens 图标](../media/o365-lens-64x64.png) <br> Office Lens | ![任务图标](../media/O365-DSR-Doc-Final_image8.png) <br> 任务 |
| ![OneDrive 图标](../media/o365-OneDrive-64x64.png) <br> OneDrive for Business |![Teams 图标](../media/o365-teams-64x64.png) <br> Teams |
| ![OneNote 图标](../media/o365-onenote-64x64.png) <br> OneNote| ![待办操作图标](../media/o365-todo-64x64.png) <br> 待办事项 |
| ![Outlook 图标](../media/o365-outlook-64x64.png) <br> Outlook/Exchange | ![视频图标](../media/O365-DSR-Doc-Final_image14.png) <br> 视频 |
| ![人员图标](../media/O365-DSR-Doc-Final_image15.png) <br> 人员 | ![Visio 图标](../media/o365-visio-64x64.png) <br> Visio |
| ![PowerPoint 图标](../media/o365-powerpoint-64x64.png) <br> PowerPoint | ![Word 图标](../media/o365-word-64x64.png) <br> Word
||

>[!NOTE]
>The Content Search eDiscovery tool is not available in [Office 365 operated by 21Vianet (China)](https://docs.microsoft.com/microsoft-365/admin/services-in-china/services-in-china). This means you won't able to use this tool to search for and export Customer Data in the Office 365 applications shown in Table 1. However, you can use the In-Place eDiscovery tool in Exchange Online to search for content in user mailboxes. You can also use the eDiscovery Center in SharePoint Online to search for content in SharePoint sites and OneDrive accounts. Alternatively, you can ask a document owner to help you find and make changes or deletions to content or export it if necessary. For more information, see:</br><br> * [创建就地电子数据展示搜索](https://docs.microsoft.com/exchange/create-in-place-ediscovery-search-exchange-2013-help)<br> * [在 SharePoint Online 中设置电子数据展示中心](https://support.office.com/article/Set-up-an-eDiscovery-Center-in-SharePoint-Online-A18F8975-AA7F-43B4-A7D6-001D14744D8E)

### <a name="using-content-search-to-find-personal-data"></a>使用内容搜索查找个人数据

响应 DSR 的第一步是查找作为 DSR 主体的个人数据。 这包括使用 Office 365 电子数据展示工具（在 Office 365 中的所有组织数据内）搜索个人数据，或直接转到在其中创建了数据的本机应用程序。 此第一步（查找和审查所涉及的个人数据）可帮助确定 DSR 是否符合组织有关接受或拒绝数据主体请求的要求。 例如，在查找并审查所涉及的个人数据后，可以确定请求不符合组织的要求，因为这样做可能会对他人的权利和自由产生负面影响，或者个人数据包含在组织可出于合法的商业利益而保留的业务记录中。

As previously stated, Microsoft estimates that over 90% of an organization's data is created with Office applications, such as Word and Excel. This means that you can use the Content Search in the Security & Compliance Center to search for most DSR-related data.

This guide assumes that you or the person searching for personal data that may be responsive to a DSR request is familiar with or has experience using the Content Search tool in the Security & Compliance Center. For general guidance on using Content Search, see [Content Search in Office 365](https://docs.microsoft.com/microsoft-365/compliance/content-search). Be sure that the person running the searches has been assigned the necessary permissions in the Security & Compliance Center. This person should be added as a member of the eDiscovery Manager role group in the Security & Compliance Center; see [Assign eDiscovery permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions). Consider adding other people in your organization who are involved in investigating DSRs to the eDiscovery Manager role group, so they can perform the necessary actions in the Content Search tool such as previewing and exporting search results. However, unless you set up compliance boundaries (as described [here](#set-up-compliance-boundaries-to-limit-the-scope-of-content-searches)) be aware that an eDiscovery Manager can search all content locations in your organization, including ones that may not be related to a DSR investigation.

找到数据后，可执行特定操作以满足数据主体的请求。

>[!NOTE]
>在 Office 365 德国版中，安全与合规中心位于 https://protection.office.de。

#### <a name="searching-content-locations"></a>搜索内容位置

可使用内容搜索工具搜索以下类型的内容位置。

- Exchange Online 邮箱。 这包括与 Microsoft 365 组和 Microsoft Teams 关联的邮箱
- Exchange Online 公用文件夹
- SharePoint Online 网站。 这包括与 Microsoft 365 组和 Microsoft Teams 关联的网站
- OneDrive for Business 帐户

>[!NOTE]
>This guide assumes that all data that might be relevant to a DSR investigation is stored in Office 365; in other words, stored in the Microsoft cloud. Data stored on a user's local computer or on-premises on your organization's file servers is outside the scope of a DSR investigation for data stored in Office 365. For guidance about responding to DSR requests for data in on-premises organizations, see [GDPR for Office on-premises Servers](https://docs.microsoft.com/Office365/Enterprise/gdpr-for-office-servers).

#### <a name="tips-for-searching-content-locations"></a>搜索内容位置相关提示

- 首先搜索组织中的所有内容位置（可通过单次搜索完成），快速确定哪些内容位置包含与搜索查询匹配的项目。 然后可以重新运行搜索，并将搜索范围缩小为包含相关项目的特定位置。
- Use search statistics to identify the top locations that contain items that match your search query. See [View keyword statistics for Content Search results](https://docs.microsoft.com/microsoft-365/compliance/view-keyword-statistics-for-content-search).
- 在审核日志中搜索作为 DSR 主体的用户最近执行的文件和文件夹活动。 搜索审核日志将返回审核记录列表，这些记录包含用户最近与其进行了交互的资源的名称和位置。 可以使用此信息生成内容搜索查询。 请参阅[在安全与合规中心搜索审核日志](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。

#### <a name="building-search-queries-to-find-personal-data"></a>生成查找个人数据的搜索查询

要调查的 DSR 很可能包含标识符，可在搜索个人数据的关键字搜索查询中使用这些标识符。 下面列出了可在查找个人数据的搜索查询中使用的一些常见标识符：

- 电子邮件地址或别名
- 电话号码
- 通讯地址
- 雇员 ID 号
- 国家/地区身份证号码或欧盟成员版社会安全号码

要调查的 DSR 很可能包含标识符和有关属于请求主体的个人数据的其他详细信息，可在搜索查询中使用这些信息。

只搜索电子邮件地址或员工 ID 可能会返回大量结果。 要缩小搜索范围，使其返回与 DSR 相关度最高的内容，可以向搜索查询添加条件。 添加条件时，关键字和搜索条件通过 **AND** 布尔运算符在逻辑上相连。 这意味着搜索结果中仅返回*同时*与关键字和条件匹配的项。

The following table lists some conditions you can use to narrow the scope of a search. The table also lists the values that you can use for each condition to search for specific document types and mailbox items.

***表 2：使用条件缩小搜索范围***

||||
| :--- | :--- |:--- |
|**条件**|**说明** |**条件值示例**|
| 文件类型 | 文档或文件的扩展名。 使用此条件，可搜索通过 Office 365 应用程序创建的 Office 文档和文件。 在搜索位于 SharePoint Online 网站和 OneDrive for Business 帐户中的文档时，可使用此条件。<br/>相应的文档属性为 filetype。 <br/>有关可搜索的文件扩展名的完整列表，请参阅“SharePoint 中的默认爬网文件扩展名和解析文件类型”（https://technet.microsoft.com/library/jj219530.aspx)）。|&nbsp;&bull;&nbsp;&nbsp;csv — 搜索逗号分隔值 (CSV) 文件；Excel 可保存为 CSV 格式，CSV 文件可轻松导入 Excel 中<br><br>&bull;&nbsp;&nbsp;docx — 搜索 Word 文件 <br><br>&bull;&nbsp;&nbsp;mpp — 搜索 Project 文件<br/><br>&bull;&nbsp;&nbsp;one — 搜索 OneNote 文件 <br><br>&bull;&nbsp;&nbsp;pdf — 搜索保存为 PDF 格式的文件 <br><br>&bull;&nbsp;&nbsp;pptx — 搜索 PowerPoint 文件 <br><br>&bull;&nbsp;&nbsp;xlxs — 搜索 Excel 文件 <br><br>&bull;&nbsp;&nbsp;vsd — 搜索 Visio 文件 <br><br>&bull;&nbsp;&nbsp;wmv — 搜索 Windows Media 视频文件 <br>|
| 邮件类型 | 要搜索的电子邮件类型。 使用此条件，可在邮箱中搜索联系人（人员）、会议（日历）任务或 Skype for Business 对话。 相应的电子邮件属性为 *kind*。|&bull;&nbsp;&nbsp;*联系人 — 搜索邮箱的“我的联系人”列表（人员）<br><br>&bull;&nbsp;&nbsp;* 电子邮件 — 搜索电子邮件 <br><br>&bull;&nbsp;&nbsp;*即时消息 — 搜索 Skype for Business 对话<br><br>&bull;&nbsp;&nbsp;* 会议 — 搜索约会和会议请求（日历） <br><br>&bull;&nbsp;&nbsp;*任务 — 搜索“我的任务”列表（任务）；使用此值将返回在微软待办中创建的任务。<br>|
| 合规性标记 |The label assigned to an email message or a document. Labels are used to classify email and documents for data governance and enforce retention rules based on the classification defined by the label. Use this condition to search for items that have been automatically or manually assigned a label.<br/>This is a useful condition for DSR investigations because your organization may be using labels to classify content related to data privacy or that contains personal data or sensitive information. See the "Using Content Search to find all content with a specific label applied to it" section in [Overview of labels in Office 365.](https://docs.microsoft.com/microsoft-365/compliance/labels)|合规性标记=“个人数据”|
||||

There are many more email and document properties and search conditions that you can use to build more complex search queries. See the following sections in the [Keyword queries and search conditions for Content Search](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions) help topic for more information.

- [可搜索的电子邮件属性](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)
- [可搜索的网站（文档）属性](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)
- [搜索条件](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)

#### <a name="searching-for-personal-data-in-sharepoint-lists-discussions-and-forms"></a>搜索 SharePoint 列表、讨论和表单中的个人数据

In addition to searching for personal data in documents, you can also use Content Search to search for other types of data that's created by using native SharePoint Online apps. This includes data created by using SharePoint lists, discussions, and forms. When you run a Content Search and search SharePoint Online sites (or OneDrive for Business accounts) data from lists, discussions, and forms that match the search criteria will be returned in the search results.

##### <a name="examples-of-search-queries"></a>搜索查询示例

下面列出了一些搜索查询示例，这些查询使用关键字和条件来搜索个人数据以响应 DSR。 这些示例展示了两个版本的查询：一个使用关键字语法（条件包含在“关键字”框中），另一个展示了基于 GUI 的使用条件的查询。

##### <a name="example-1"></a>示例 1

此示例返回 SharePoint Online 网站和 OneDrive for Business 帐户中包含指定电子邮件地址的 Excel 文件。 如果电子邮件地址出现在文件元数据中，则可能会返回文件。

***关键字语法***

```Query
pilar@contoso.com AND filetype="xlxs"
```

***GUI***

![关键字对话框](../media/O365-DSR-Doc_image18.png)

##### <a name="example-2"></a>示例 2

此示例返回 SharePoint Online 网站和 OneDrive for Business 帐户中包含指定员工 ID 和出生日期的 Excel 或 Word 文件。

(98765 OR "01-20-1990") AND (filetype="xlxs" OR filetype="docx")

***GUI***

![关键字对话框](../media/O365-DSR-Doc_image19.png)

##### <a name="example-3"></a>示例 3

此示例返回包含指定身份证号码（法国社会安全号码 (INSEE)）的电子邮件

```Query
"1600330345678 97" AND kind="email"
```

***GUI***

![关键字对话框](../media/O365-DSR-Doc_image20.png)

#### <a name="working-with-partially-indexed-items-in-content-search"></a>处理内容搜索中的部分索引项

部分索引项（也称为*未编制索引的项*）是出于某些原因未针对搜索完全编制索引的 Exchange Online 邮箱项目以及 SharePoint Online 和 OneDrive for Business 文档，无法使用内容搜索对其进行搜索。 大多数电子邮件和网站都可成功编制索引，因为它们在 [Office 365 索引限制](https://docs.microsoft.com/microsoft-365/compliance/limits-for-content-search)的范围内。 未针对搜索对电子邮件或文件编制索引的原因包括：

- 文件类型是[索引无法识别或不支持](https://docs.microsoft.com/microsoft-365/compliance/partially-indexed-items-in-content-search)的文件类型。 虽然该文件类型有时支持索引，但是特定文件出现索引错误
- 电子邮件的附件文件中未包含有效的图柄，如图像文件（这是部分索引电子邮件项最常见的原因）
- 附加到电子邮件的文件太大，或附加的文件过多

We recommend that you learn more about partially indexed items so that you can work with them when responding to DSR requests. For more information, see:

- [处理 Office 365 内容搜索中的部分索引项](https://docs.microsoft.com/microsoft-365/compliance/partially-indexed-items-in-content-search)
- [使用 Office 365 电子数据展示调查部分索引项](https://docs.microsoft.com/microsoft-365/compliance/investigating-partially-indexed-items-in-ediscovery)
- [导出未编制索引的项](export-search-results.md)

#### <a name="tips-for-working-with-partially-indexed-items"></a>处理部分索引项的相关提示

It's possible that data responsive to a DSR investigation may be in a partially indexed item. Here's some suggestions for working with partially indexed items:

- 运行搜索后，估计的部分索引项数目显示在搜索统计信息中。 此估计不包括 SharePoint Online 和 OneDrive for Business 中的部分索引项。 导出内容搜索报告，了解有关部分索引项的信息。 **Unindexed Items.csv** 报告包含未编制索引的项的相关信息，包括项目的位置、URL（如果项目位于 SharePoint Online 或 OneDrive for Business 中）以及主题行（对于邮件）或文档名称。 有关详细信息，请参阅[导出内容搜索报告](https://docs.microsoft.com/microsoft-365/compliance/export-a-content-search-report)。

- 随内容搜索结果一起返回的部分索引项统计信息和列表包含位于所搜索内容位置的所有部分索引项。

- 要检索潜在响应 DSR 调查的部分索引项，可执行下列某项项操作：

##### <a name="export-all-partially-indexed-items"></a>导出所有部分索引项

可同时导出内容搜索的结果和位于所搜索内容位置的部分索引项。 还可以只导出部分索引项。 然后可在本机应用程序中打开它们并查看内容。 必须使用此选项才可导出 SharePoint Online 和 OneDrive for Business 中的项目。 请参阅[从安全与合规中心导出内容搜索结果](export-search-results.md)。

##### <a name="export-a-specific-set-of-partially-indexed-items-from-mailboxes"></a>从邮箱导出一组特定的部分索引项

可以重新运行内容搜索，以搜索特定的部分索引项列表，然后将其导出，而无需导出搜索的所有部分索引邮箱项目。 仅可针对邮箱项目执行此操作。 请参阅[为 Office 365 中的定向内容搜索准备 CSV 文件](https://docs.microsoft.com/microsoft-365/compliance/csv-file-for-an-id-list-content-search)。

### <a name="next-steps"></a>后续步骤

找到与 DSR 相关的个人数据后，请务必保留用于查找数据的特定内容搜索。 可能需要重复使用此搜索完成 DSR 响应过程中的其他步骤，如[获取数据副本](#providing-a-copy-of-personal-data)、[导出数据](#exporting-personal-data)或[永久删除数据](#deleting-personal-data)。

### <a name="additional-considerations-for-selected-applications"></a>选定应用程序的其他注意事项

以下各节介绍了搜索以下 Office 365 应用程序中的数据时需要注意的事项。

- [Office Lens](#office-lens)
- [OneDrive for Business 和 SharePoint 体验设置](#onedrive-for-business-and-sharepoint-online-experience-settings)
- [Microsoft Teams 教育版](#microsoft-teams-for-education)
- [微软待办](#microsoft-to-do)
- [Skype for Business](#skype-for-business)

#### <a name="office-lens"></a>Office Lens

使用 Office Lens（运行 iOS、Android 和 Windows 的设备支持的一个相机应用）的用户可对白板、硬拷贝文档、名片和包含大量文本的其他事物拍摄照片。 Office Lens 使用光学字符识别技术，可提取图像中的文本并将其保存为 Office 文档（例如 Word、PowerPoint 和 OneNote）或 PDF 文件。 然后，用户可将包含图像中文本的文件上传到其 Office 365 中的 OneDrive for Business 帐户。 这意味着可使用内容搜索工具搜索、访问、删除和导出基于 Office Lens 图像创建的文件中的数据。 有关 Office Lens 的详细信息，请参阅：

- [Office Lens for iOS](https://support.microsoft.com/zh-CN/office/microsoft-office-lens-for-ios-fbdca5f4-1b1b-4391-a931-dc1c2582397b)
- [Office Lens for Android](https://support.office.com/article/Office-Lens-for-Android-ec124207-0049-4201-afaf-b5874a8e6f2b)
- [Office Lens for Windows](https://support.microsoft.com/zh-CN/office/office-lens-for-windows-577ec09d-8da2-4029-8bb7-12f8114f472a)

#### <a name="onedrive-for-business-and-sharepoint-online-experience-settings"></a>OneDrive for Business 和 SharePoint Online 体验设置

In addition to user-created files stored in OneDrive for Business accounts and SharePoint Online sites, these services store information about the user that is used to enable various experiences. Users still in your organization can access much of this information by using in-product functionality. The following information provides guidance on how to access, view, and export OneDrive for Business and SharePoint Online application data.

##### <a name="sharepoint-user-profiles"></a>SharePoint 用户个人资料

借助用户的 Delve 个人资料，用户可维护存储在 SharePoint Online 用户个人资料中的数据，包括生日、手机号码（和其他联系人信息）、自我评价、项目、技能和专业知识、教育经历、兴趣和爱好。

###### <a name="end-users"></a>最终用户

End users can discover, access, and rectify SharePoint Online user profile data using the Delve profile experience. See [View and update your profile in Office Delve](https://support.office.com/article/view-and-update-your-profile-in-office-delve-4e84343b-eedf-45a1-aeb9-8627ccca14ba) for more details.

用户还可通过导航到其 OneDrive for Business 帐户中的“**编辑个人资料**”页面来访问其 SharePoint 个人资料数据，要访问该页面，可转到 OneDrive for Business 帐户 URL 下的 **EditProfile.aspx** 路径。 例如，对于用户 <strong>user1@contoso.com</strong>，该用户的 OneDrive for Business 帐户位于：

```URL
`https://contoso-my.sharepoint.com/personal/user1\_contoso\_com/\_layouts/15/OneDrive.aspx`
```

“编辑个人资料”页面的 URL 将为：

```URL
`https://contoso-my.sharepoint.com/personal/user1\_contoso\_com/\_layouts/15/EditProfile.aspx`
```

无法在 SharePoint Online 中更改源于 Azure Active Directory 的属性。 但是，用户可通过选择 Office 365 标头中的“**照片**”，然后选择“**我的帐户**”转到其“**帐户**”页面。 要在其中更改数据，用户需要与管理员协作，发现、访问或纠正用户个人资料属性。

###### <a name="admins"></a>管理员

管理员可以在 SharePoint 管理中心访问和纠正个人资料属性。 在“**SharePoint 管理中心**”中，单击“**用户个人资料**”选项卡。单击“**管理用户个人资料**”，输入用户的姓名，然后单击“**查找**”。 管理员可以右键单击任意用户，然后选择“**编辑我的个人资料**”。 无法在 SharePoint Online 中更改源于 Azure Active Directory 的属性。

An admin can export all User Profile properties for a user by using the **Export-SPOUserProfile** cmdlet in SharePoint Online PowerShell. See  [Export-SPOUserProfile](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spouserprofile?view=sharepoint-ps).

有关用户个人资料的详细信息，请参阅[在 SharePoint 管理中心管理用户个人资料](https://docs.microsoft.com/sharepoint/manage-user-profiles)。

##### <a name="user-information-list-on-sharepoint-online-sites"></a>SharePoint Online 网站上的用户信息列表

用户的 SharePoint 用户个人资料子集将同步到他们访问的或有权访问的每个网站的用户信息列表。 这在 SharePoint Online 体验中使用（例如文档库中的“人员”列），以显示有关该用户的基本信息，如文档创建者的姓名。 用户信息列表中的数据将匹配存储在 SharePoint 用户个人资料中的信息，如果源发生更改，将自动纠正。 对于已删除的用户，此数据仍保留在他们与之进行交互的网站中，以实现 SharePoint 列字段的引用完整性。 

Admins can control which properties are replicable inside the SharePoint admin center. To do this:

1. 转到“**SharePoint 管理中心**”，单击“**用户个人资料**”选项卡。
2. 单击“管理用户属性”****，查看属性列表。
3. 右键单击任意属性，然后选择“编辑”**** 并调整各种设置。
4. 可通过“**策略设置**”下的“可复制”属性来控制是否在用户信息列表中显示某个属性。 并非所有属性都支持此调整。

An admin can export all User information properties for a user on a given site by using the **Export-SPOUserInfo** cmdlet in SharePoint Online PowerShell. See [Export-SPOUserInfo](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spouserinfo?view=sharepoint-ps).

##### <a name="onedrive-for-business-experience-settings"></a>OneDrive for Business 体验设置

A user's OneDrive for Business experience stores information to help the user find and navigate content of interest to them. Most of this information can be accessed by end users using in-product features. An admin can export the information using a [PowerShell Script](https://docs.microsoft.com/powershell/scripting/overview) and [SharePoint Client-Side Object Model (CSOM)](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-client-library-code) commands.

有关设置、存储方式和如何将其导出的详细信息，请参阅[导出 OneDrive for Business 体验设置](https://docs.microsoft.com/sharepoint/export-odfb-lists)。

##### <a name="onedrive-for-business-and-sharepoint-online-search"></a>OneDrive for Business 和 SharePoint Online 搜索

The in-app search experience in OneDrive for Business and SharePoint Online stores a user's search queries for 30 days to increase relevance of search results. An admin can export search queries for a user by using the **Export-SPOQueryLogs** cmdlet in SharePoint Online PowerShell. See [Export-SPOQueryLogs](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spoquerylogs?view=sharepoint-ps).

#### <a name="microsoft-teams-for-education"></a>Microsoft Teams 教育版

Microsoft Teams for Education offers two additional collaboration features that teachers and students can use that creates and stores personal data: Assignments and OneNote Class Notebook. You can use Content Search to discover data in both.

##### <a name="assignments"></a>作业

Students files associated with an Assignment are stored in a document library in the corresponding Teams SharePoint Online site. IT admins can use the Content Search tool to search for student files that are related to assignments. For example, an admin could search all SharePoint Online sites in the organization and use the student's name and class or assignment name in the search query to find data relevant to a DSR.

There's other data related to Assignments that isn't stored in the class team SharePoint Online site, which means it's not discoverable with Content Search. This includes:

- 教师在作业中分配给学生的文件
- 学生成绩和教师反馈
- 每个学生为作业提交的文档列表
- 作业元数据

对于这种类型的数据，IT 管理员或数据所有者（如教师）可能必须进入课堂团队中的作业才可查找与 DSR 相关的数据。

##### <a name="onenote-class-notebook"></a>OneNote 课堂笔记本

The OneNote Class Notebook is stored in the class team SharePoint Online site. Every student in a class has a private notebook that's shared with the teacher. There's also a content library where a teacher can share documents with students, and a collaboration space for all students in the class. Data related to these capabilities is discoverable with Content Search.

下面介绍了搜索课堂笔记本的具体指南。

1. 使用以下搜索条件运行内容搜索：

   - 搜索所有 SharePoint Online 网站

   - 将课堂团队的名称包含在搜索关键字内；例如，“9C Biology”。

2. 预览搜索结果，并查看对应于课堂笔记本的项目。
3. Select that item, and then copy the folder path that's displayed in the details pane. This is the root folder for the Class Notebook.
4. Edit the search that you created in step 1 and replace the class name in the keyword query with the folder path of the Class Notebook and precede the folder path with the **path** site property; for example, **path:"<https://contosoedu.onmicrosoft.com/sites/9C> Biology/SiteAssets/9C Biology Notebook/"**. Be sure to include the quotation marks and the trailing forward slash.
5. 添加搜索条件，选择文件类型条件，使用 one 作为文件类型的值。 这将在搜索结果中返回所有 OneNote 文件。 最终的关键字语法如下所示：[](#building-search-queries-to-find-personal-data)

    ```Query
   path:"<https://contosoedu.onmicrosoft.com/sites/9C> Biology/SiteAssets/9C Biology Notebook/" AND filetype="one"
   ```

6.  重新运行内容搜索。 搜索结果应包括班级团队中 Class Notebook 的所有 OneNote 文件。

#### <a name="microsoft-to-do"></a>微软待办

微软待办中的任务（称为*待办事项*，保存在*待办事项列表*中）在用户的 Exchange Online 邮箱中保存为“任务”。 这意味着你可以使用“内容搜索”工具来搜索、访问、删除和导出待办事项。 有关详细信息，请参阅[设置微软待办](https://support.microsoft.com/zh-CN/office/set-up-microsoft-to-do-490c1a8c-2333-4952-8125-841afadb9620)。

#### <a name="skype-for-business"></a>Skype for Business

下面提供了有关如何访问、查看和导出 Skype for Business 中的个人数据的一些其他信息。

- Files attached to a meeting are retained in the actual meeting for 180 days and then become inaccessible. These files can be accessed by meeting participants by joining the meeting from the meeting request and then viewing or downloading the attached file. See the "Use the attachments in the meeting" section in [Preload attachments for a Skype for Business meeting](https://support.microsoft.com/zh-CN/office/preload-attachments-for-a-skype-for-business-meeting-fd3d9f9d-b448-4754-b813-02e49393f251).
- Conversations in Skype for Business are retained in the Conversation History folder in user mailboxes. You can use Content Search to search mailboxes for data in Skype conversations.
- A data subject can export their contacts in Skype for Business. To do this, they would right-click a contact group in Skype for Business and click **Copy**. Then they can paste the list of email addresses into a text or Word document.
- If the Exchange Online mailbox of a meeting participant is placed on Litigation Hold or assigned to an Office 365 retention policy, files attached to a meeting are retained in the participants mailbox. You can use Content Search to search for those files in the participant's mailbox if the retention period for the file has not expired. For more information about retaining files, see [Retaining large files attached to a Skype for Business meeting](https://docs.microsoft.com/skypeforbusiness/set-up-policies-in-your-organization/retaining-large-files-attached-to-a-meeting).

## <a name="providing-a-copy-of-personal-data"></a>提供个人数据副本

After you've found personal data that is potentially responsive to a DSR, it's up to you and your organization to decide which data to provide the data subject. For example, you can provide them with a copy of the actual document, an appropriately redacted version, or a screenshot of the portions that you've deemed appropriate to share. For each of these responses to an access request, you'll have to retrieve a copy of the document or other item that contains the responsive data.

将副本提供给数据主体时，可能需要删除或修订有关其他数据主体和任何机密信息的个人信息。

### <a name="using-content-search-to-get-a-copy-of-personal-data"></a>使用内容搜索获取个人数据副本

可通过两种方法使用内容搜索工具获取运行搜索后找到的文档或邮箱项目副本。

- Preview the search results and then download a copy of the document or item. This is a good way to download a few items or files.
- 导出搜索结果，然后下载搜索返回的所有项目副本。 此方法更为复杂，但却是下载大量响应 DSR 的项目的好方法。 导出搜索结果中还包括一些实用的报告。 可使用这些报告来获取有关每个项目的其他信息。 **Results.csv** 报告尤其有用，因为它包含大量有关导出项目的信息，如项目的提取位置（例如电子邮件的邮箱，或者位于 SharePoint Online 和 OneDrive for Business 网站上的文档或列表的 URL）。 如果你需要在 DSR 调查过程中与项目所有者联系，此信息可帮助你识别该所有者的身份。 有关导出搜索结果时包含的报告的详细信息，请参阅[导出内容搜索报告](https://docs.microsoft.com/microsoft-365/compliance/export-a-content-search-report)。

#### <a name="preview-and-download-items"></a>预览和下载项目

运行新搜索或打开现有搜索后，可审阅与搜索查询匹配的每个项目，验证其是否与正在调查的 DSR 相关。 这还包括在搜索结果中返回的 SharePoint 列表和网页。 你还可下载原始文件（如果必须向数据所有者提供该原始文件）。 在两种情况下，都可进行屏幕截图，满足数据主体获取信息的请求。

某些类型的项目无法预览。 如果一个项目或文件类型不支持预览，可选择将各项目下载到本地计算机、映射的网络驱动器或其他网络位置。 仅可预览[受支持的文件类型](https://docs.microsoft.com/microsoft-365/compliance/content-search)。

预览和下载项目：

1. 在安全与合规中心打开内容搜索。
2. 如果未显示结果，请单击“**预览结果**”。
3. 单击一个项目即可查看。
4. Click **Download original file** to download the item to your local computer. You'll also have to download items that can't be previewed.

有关预览搜索结果的详细信息，请参阅[预览搜索结果](https://docs.microsoft.com/microsoft-365/compliance/content-search)。

#### <a name="export-and-download-items"></a>导出和下载项目

You can also export the results of a content search to get a copy of email messages, documents, lists, and web pages containing the personal data, though this method is more involved than previewing items. See the next section for details about [exporting the results of a Content Search](#export-and-download-content-using-content-search).

## <a name="exporting-personal-data"></a>导出个人数据

The "right of data portability" allows a data subject to request an electronic copy of personal data that's in a "structured, commonly used, machine-readable format", and to request that your organization transmit these electronic files to another data controller. Microsoft supports this right in two ways:

- 提供以常用的计算机可读本机电子格式保存数据的 Office 365 应用程序。 有关 Office 文件格式的详细信息，请参阅 [Office 文件格式技术文档](https://msdn.microsoft.com/library/office/cc313105(v=office.12).aspx)。
- 使组织能够以本机文件格式或可以轻松导入其他应用程序的格式（如 CSV、TXT 和 JSON）导出数据。

为了满足 DSR 导出请求，可以以本机文件格式导出 Office 文档，并从其他 Office 365 应用程序导出数据。

### <a name="export-and-download-content-using-content-search"></a>使用内容搜索导出和下载内容

When you export the results of a Content Search, email items can be downloaded as PST files or as individual messages (.msg files). When you export documents and lists from SharePoint Online and OneDrive for Business sites, copies in the native file formats are exported. For example, SharePoint lists are exported as CSV files and Web pages are exported as .aspx or html files.

>[!NOTE]
>使用内容搜索从某个用户的邮箱导出邮箱项目时，需要向该用户（你要导出其邮箱中的项目的用户）分配 Exchange Online 计划 2 许可证。 

导出和下载项目：

1. 在安全与合规中心打开内容搜索。
2. 在搜索飞出页面上，单击![下载图标](../media/o365-dsr_image21.png)“**更多**”，然后单击“**导出结果**”。 你还可导出报告。
3. Complete the sections on the **Export results** fly out page. Be sure to use the scroll bar to view all export options.
4. 返回安全与合规中心的内容搜索页面，并单击“**导出**”选项卡。
5. 单击“**刷新**”更新页面。
6. 在“**名称**”列中，单击刚刚创建的导出作业。 导出作业的名称为内容搜索名称追加 **\_Export**。
7. 在导出飞出页面上，单击“**导出密钥**”下的“**复制到剪贴板**”。 在步骤 10 中，将使用此密钥下载搜索结果
8. 在飞出页面顶部，单击![下载图标](../media/o365-dsr_image21.png)“**下载结果**”。
9. 如果系统提示安装 **Microsoft Office 365 电子数据展示导出工具**，请单击“**安装**”。
10. 在“**电子数据展示导出工具**”中，将在步骤 7 中复制的导出密钥粘贴在相应的框中。
11. 单击“**浏览**”指定要下载搜索结果文件的位置。
12. 单击“**开始**”将搜索结果下载到计算机。

When the export process is complete, you can access the files in the location on your local computer where they were downloaded. Results of a content search are downloaded to a folder named after the Content Search. Documents from sites are copied to a subfolder named **SharePoint**. Mailbox items are copied to subfolder named **Exchange**.

有关详细的分步说明，请参阅[从安全与合规中心导出内容搜索结果](export-search-results.md)。

### <a name="downloading-documents-and-lists-from-sharepoint-online-and-onedrive-for-business"></a>从 SharePoint Online 和 OneDrive for Business 下载文档和列表

Another way to export data from SharePoint Online and OneDrive for Business is to download documents and lists directly from a SharePoint Online site or a OneDrive for Business account. You would have to get assigned the permissions to access a site, and then go to the site and download the contents. See:

- [从 OneDrive 或 SharePoint 下载文件和文件夹](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)
- [将 SharePoint 列表导出到 Excel](https://support.office.com/article/export-to-excel-from-sharepoint-bfb2ea48-6118-4fa9-abb6-cced9424e5d9)

For some DSR export requests, you may want to allow the data subject to download content themselves. This enables the data subject to go to a SharePoint Online site or shared folder and click **Sync** to sync all contents in the document library or selected folders. See:

- [使用户能够通过新的 OneDrive 同步客户端同步 SharePoint 文件](https://docs.microsoft.com/sharepoint/let-users-use-new-onedrive-sync-client)
- [通过新的 OneDrive 同步客户端同步 SharePoint 文件](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-client-6de9ede8-5b6e-4503-80b2-6190f3354a88)

## <a name="deleting-personal-data"></a>删除个人数据

“擦除权限”可从组织的客户数据中移除个人数据，这是 GDPR 中的一项关键保护措施。 删除个人数据包括删除整个文档或文件，或删除文档或文件中的特定数据（相关操作和过程与本指南“纠正”部分所述的操作和过程相似）。

在调查或准备删除个人数据以响应 DSR 时，需要了解以下有关 Office 365 如何进行数据删除（和保留）的一些重要事项。

- **软删除与硬删除：** 在诸如 Exchange Online、SharePoint Online 和 OneDrive for Business 等 Office 365 服务中，存在*软删除*和*硬删除*的概念，它们在从 Microsoft 云中永久删除无法恢复之前与已删除项目的可恢复性有关（通常在一段有限时间内）。 在此上下文中，在硬删除项目之前一段有限的时间内，用户和/或管理员可恢复已软删除的项目。 硬删除某个项目后，该项目将标记为永久删除，并将在相应的 Office 365 服务进行处理后立即清除。 下面介绍了如何软删除和硬删除邮箱和网站中的项目（而无论是数据所有者还是管理员删除了项目）项目：

    - **邮箱：** 从“已删除邮件”文件夹删除某个项目，或通过按 **Shift + Delete** 删除某个项目时，该项目即被软删除。 软删除项目后，该项目移动到邮箱中的“可恢复邮件”文件夹。 此时，在已删除项目保留期限到期之前（在 Office 365 中，已删除项目保留策略为 14 天，但可由管理员增加到最多 30 天），用户可恢复该项目。 保留期限到期后，项目被硬删除，并移动到一个隐藏文件夹（名为“*清除*”文件夹）。 该项目将在下一次处理邮箱时（每七天处理一次邮箱）从 Office 365 中永久删除（清除）。

    - **SharePoint Online 和 OneDrive for Business 网站**：删除某个文件或文档后，该文件或文档移动到网站的回收站（也称为*第一阶段回收站*，与 Windows 中的回收站类似）。 删除的项目在回收站中保留 93 天（Office 365 中网站的已删除项目保留期限）。 之后，该项目自动移动到网站集的的回收站（也称为*第二阶段回收站*）。 （请注意，具有相应权限的用户或管理员也可从第一阶段回收站中删除项目）。 此时，项目即被软删除；仍可由 SharePoint Online 中的网站集管理员或 OneDrive for Business 中的用户或管理员恢复。 项目从第二阶段回收站中删除后（无论是手动还是自动），该项目即被硬删除，用户或 IT 管理员无法再进行访问。第一阶段回收站和第二阶段回收站的保留期限都为 93 天。这意味着第二阶段回收站保留期从首次删除项目时开始。 因此，两个回收站的总保留时间为 93 天。

>[!NOTE]
>了解可导致项目软删除或硬删除的操作有助于在响应删除请求时，确定如何以符合 GDPR 要求的方式删除数据。

- **法定保留和保留策略：** 在 Office 365 中，可对邮箱和网站实施“保留”。 简言之，这意味着如果邮箱或网站处于保留状态，则在项目的保留期限到期或删除保留之前，不会永久删除（硬删除）任何内容。 在删除客户内容以响应 DSR 时，这一点非常重要：如果从处于保留状态的内容位置硬删除某个项目，不会从 Office 365 永久删除该项目。 这意味着 IT 管理员有可能恢复该项目。如果组织的要求和策略规定永久删除 Office 365 中的数据并使其无法恢复以响应 DSR，则必须从邮箱或网站删除保留，以便永久删除 Office 365 中的数据。 组织针对响应 DSR 的指导原则很可能已制定了一个流程，用于确定是特定 DSR 删除请求还是法定保留优先。 如果删除了保留以便删除项目，可在删除项目后重新实施保留。

### <a name="deleting-documents-in-sharepoint-online-and-onedrive-for-business"></a>删除 SharePoint Online 和 OneDrive for Business 中的文档

找到 SharePoint Online 网站或 OneDrive for Business 帐户中需要删除的文档后（按照本指南“发现”部分的指导操作），需要向数据隐私部主管或 IT 管理员分配访问网站和删除文档的必要权限。 在适当情况下，也可指示文档所有者删除文档。

下面是从网站删除文档的高级流程。

1. 转到网站并定位文档。
2. Delete the document. When you delete a document from a site, it's sent to the first-stage Recycle Bin.
3. Go to the first-stage Recycle Bin (the site Recycle Bin) and delete the same document you deleted in the previous step. The document is sent to the second-stage Recycle Bin. **At this point, the document is soft-deleted**.
4. Go to the second-stage Recycle Bin (which is the site collection Recycle Bin) and delete the same document that you deleted from the first-stage Recycle Bin. **At this point, the document is hard-deleted.**

>[!IMPORTANT]
>You can't delete a document that is located on a site that is on hold (with one of the retention or legal hold features in Office 365). In the case where a DSR delete request takes precedence over a legal hold, the hold would have to be removed from the site before a document could be permanently deleted.

有关详细过程，请参阅以下主题。

- [从 SharePoint 文档库删除文件、文件夹或链接](https://support.microsoft.com/zh-CN/office/delete-a-file-folder-or-link-from-a-sharepoint-document-library-71f3c90a-0d24-4d80-8b66-f88234b79a52)
- [删除 SharePoint 网站回收站中的项目或将其清空](https://support.microsoft.com/zh-CN/office/delete-items-or-empty-the-recycle-bin-of-a-sharepoint-site-2e713599-d13e-40d6-96dc-66f0a366f74e)
- [从网站集回收站中删除项目](https://support.microsoft.com/zh-CN/office/delete-items-from-the-site-collection-recycle-bin-dd5c00c2-aef6-4458-9d04-80b185077653)
- [获取对前员工用户数据的访问权限并备份该数据](https://docs.microsoft.com/microsoft-365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data)中的“获取对前员工 OneDrive for Business 文档的访问权限”部分
- [删除 OneDrive for Business 中的文件或文件夹](https://support.office.com/article/Delete-files-or-folders-in-OneDrive-21fe345a-e488-4fa7-932b-f053c1bebe8a)
- [删除 SharePoint 中的列表](https://support.microsoft.com/zh-CN/office/delete-a-list-in-sharepoint-2a7bca5b-b8fd-4e5b-8f4b-2ac034f3070d)
- [删除 SharePoint Online 中的列表项](https://support.office.com/article/delete-list-items-in-sharepoint-online-db722233-4a38-4889-a6cf-4b33fe5c60c0)

### <a name="deleting-a-sharepoint-site"></a>删除 SharePoint 网站

You may determine that the best way to respond to a DSR delete request is to delete an entire SharePoint site, which will delete all that data located in the site. You can do this by running cmdlets in SharePoint Online PowerShell.

- 使用 [Remove-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-sposite?view=sharepoint-ps) cmdlet 删除网站，并将其移动到 SharePoint Online 回收站（软删除）。
- 使用 [Remove-SPODeletedSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spodeletedsite?view=sharepoint-ps) cmdlet 永久删除网站（硬删除）。

无法删除实施了电子数据展示保留或分配到保留策略的网站。 必须先从电子数据展示保留或保留策略删除网站，然后才能删除网站。

### <a name="deleting-a-onedrive-for-business-site"></a>删除 OneDrive for Business 网站

Similarly, you may determine to delete a user's OneDrive for Business site in response to a DSR deletion request. If you delete the user's Office 365 account, their OneDrive for Business site is retained (and restorable) for 30 days. After 30 days, it's moved to the SharePoint Online Recycle Bin (soft-deleted), and then after 93 days, it's permanently deleted (hard-deleted). To accelerate this process, you can use the [Remove-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-sposite?view=sharepoint-ps) cmdlet to move the OneDrive for Business site to the Recycle Bin and then use the [Remove-SPODeletedSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spodeletedsite?view=sharepoint-ps) cmdlet to permanently delete it. As with sites in SharePoint Online, you can't delete a user's OneDrive for Business site if it was assigned to an eDiscovery hold or a retention policy before the user's account was deleted.

### <a name="deleting-onedrive-for-business-and-sharepoint-online-experience-settings"></a>删除 OneDrive for Business 和 SharePoint Online 体验设置

除了存储在 OneDrive for Business 帐户和 SharePoint Online 站点中的用户创建的文件外，这些服务还存储用于实现各种体验的用户相关信息。 本文档中以前记录了这些信息。 请参阅[使用内容搜索电子数据展示工具来响应 DSR](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs) 下的[选定应用程序的其他注意事项](#additional-considerations-for-selected-applications)部分，了解有关如何访问、查看和导出 OneDrive for Business 和 SharePoint Online 应用程序数据的信息。

#### <a name="deleting-a-sharepoint-user-profile"></a>删除 SharePoint 用户个人资料

The SharePoint user profile will be permanently deleted 30 days after the user account is deleted in Azure Active Directory. However, you can hard-delete the user account, which will remove the SharePoint user profile. For more information, see the [Deleting a user section in this guide](#deleting-a-user).

An admin can expedite the deletion of the User Profile for a user by using the **Remove-SPOUserProfile** cmdlet in SharePoint Online PowerShell. See [Remove-SPOUserProfile](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spouserprofile?view=sharepoint-ps). This requires the user to be at least soft-deleted in Azure Active Directory.

#### <a name="deleting-user-information-lists-on-sharepoint-online-sites"></a>删除 SharePoint Online 网站上的用户信息列表

For users that have left the organization, this data remains in the sites they interacted with for referential integrity of SharePoint column fields. An admin can delete all User information properties for a user on a given site by using the **Remove-SPOUserInfo** command in SharePoint Online PowerShell. See [Remove-SPOUserInfo](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spouserinfo?view=sharepoint-ps) for information about running this PowerShell cmdlet.

默认情况下，此命令会保留用户的显示名称，并删除属性，如电话号码、电子邮件地址、技能和专业知识或者从 SharePoint Online 用户个人资料复制的其他属性。 管理员可以使用 **RedactUser** 参数来指定用户信息列表中用户的备用显示名称。 这会影响用户体验的多个部分，并在查看网站中的文件历史记录时，将导致信息丢失。

Finally, the redaction capability will not remove all metadata or content referencing a user from documents. The way to achieve redaction of file content and metadata is described in the [Making changes to content in OneDrive for Business and SharePoint Online](#making-changes-to-content-in-onedrive-for-business-and-sharepoint-online) section in this guide. This method consists of downloading, deleting, and then uploading a redacted copy of the file.

#### <a name="deleting-onedrive-for-business-experience-settings"></a>删除 OneDrive for Business 体验设置

The recommended way to delete all OneDrive for Business experience settings and information is to remove the user's OneDrive for Business site, after reassigning any retained files to other users. An admin can delete these lists using [PowerShell Script](https://docs.microsoft.com/powershell/scripting/overview) and [SharePoint Client-Side Object Model (CSOM)](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-client-library-code) commands. See [Deleting OneDrive for Business experience settings](https://docs.microsoft.com/sharepoint/delete-odfb-lists) for more information about the settings, how they are stored, and how to delete them.

#### <a name="onedrive-for-business-and-sharepoint-online-search-queries"></a>OneDrive for Business 和 SharePoint Online 搜索查询

用户在 OneDrive for Business 和 SharePoint Online 搜索体验中创建的搜索查询在用户创建该查询 30 天后自动删除。

### <a name="deleting-items-in-exchange-online-mailboxes"></a>删除 Exchange Online 邮箱中的项目

可能需要删除 Exchange Online 邮箱中的项目来满足 DSR 删除请求。 IT 管理员可通过两种方法删除邮箱中的项目，具体取决于是要软删除还是硬删除目标项目。 与 SharePoint Online 或 OneDrive for Business 网站上的文档相似，无法从 Office 365 永久删除处于保留状态的邮箱中的项目。 必须先删除保留，然后才能删除该项目。 同样，必须确定是保留邮箱还是 DSR 删除请求优先。

#### <a name="soft-delete-mailbox-items"></a>软删除邮箱项目

可以使用内容搜索操作功能软删除内容搜索返回的项目。 如前文所述，软删除的项目移到邮箱中的“可恢复邮件”文件夹。

下文快速概述了此过程：

1. 创建并运行内容搜索，查找要从用户邮箱中删除的项目。 可能需要重新运行搜索以缩小搜索结果的范围，以便搜索结果中只返回要删除的项目。
2. 在 Office 365 PowerShell 中使用 **New-ComplianceSearchAction** **-Purge** 命令，软删除由在上一步中创建的内容搜索返回的项目。

有关详细说明，请参阅[在组织中搜索并删除电子邮件](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)。

#### <a name="hard-delete-mailbox-items"></a>硬删除邮箱项目

If you have to hard-delete mailbox items in response to the DSR deletion request, you can use the **Search-Mailbox -DeleteContent** command in Exchange Online PowerShell. If you use this method, consider using Content Search to develop and refine a search query so that only the items that are to be deleted are returned in the search. Then you can use that query syntax when you run the **Search-Mailbox -DeleteContent** command.

有关详细说明，请参阅[搜索并删除邮件](https://technet.microsoft.com/library/ff459253(v=exchg.150).aspx)。

#### <a name="hard-delete-items-in-a-mailbox-on-hold"></a>硬删除处于保留状态的邮箱中的项目

As previously explained, if you hard-delete items in a mailbox on hold, items are not removed from the mailbox. They are moved to a hidden folder in the Recoverable Items folder (the **Purges** folder) and will remain there until the hold duration for the item expires or until the hold is removed from the mailbox. If either of those things happen, the items will be purged from Office 365 the next time that the mailbox is processed.

Your organization might determine that items being permanently deleted when the hold duration expires meets the requirements for a DSR deletion request. However, if you determine that mailbox items must be immediately purged from Office 365, you would have to remove the hold from the mailbox and then hard-deleted the items from the mailbox. For detailed instructions, see [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](https://docs.microsoft.com/microsoft-365/compliance/delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold).

>[!NOTE]
>要按照上一主题中所述的过程硬删除邮箱项目以满足 DSR 删除请求，可能需要在邮箱仍处于保留状态时软删除这些项目，以便它们移动到“可恢复的项目”文件夹。

## <a name="deleting-a-user"></a>删除用户

In addition to deleting personal data in response to a DSR deletion request, a data subject's "right to be forgotten" may also be fulfilled by deleting their user account. Here are some reasons that you might want to delete a user:

- 数据主体已离开（或正在离开）组织。
- The data subject has requested that you delete system-generated logs that have been collected about them. Examples of data in system-generated logs include Office 365 app and service usage data, information about search requests performed by the data subject, and data generated by product and services as a product of system functionality and interaction by users or other systems. For more information, see [Part 3: Responding to DSRs for system-generated Logs](#part-3-responding-to-dsrs-for-system-generated-logs) in this guide.
- 永久防止数据主体访问或处理 Office 365 中的数据（与通过[响应 DSR 限制请求](#responding-to-dsr-restriction-requests)部分中所述的方法临时限制访问完全不同）。

删除用户帐户后：

- 用户无法再登录 Office 365 或访问组织的任何 Microsoft 资源，例如其 OneDrive for Business 帐户、SharePoint Online 网站或其 Exchange Online 邮箱。
- 将删除与该用户帐户关联的个人数据，例如电子邮件地址，别名、电话号码和通讯地址
- 某些 Office 365 应用将删除有关该用户的信息。 例如，在 Microsoft Flow 中，将从共享流的所有者列表中移除已删除的用户。
- 删除用户帐户 30 天后，将删除有关数据主体的系统生成日志（不包括可能会危及服务安全性和稳定性的数据）。 有关详细信息，请参阅[删除系统生成日志](#deleting-system-generated-logs)部分。

>[!IMPORTANT]
>After you delete a user account, that person will lose the ability to sign in to Office 365 and the ability to sign in to any products or services for which he or she formerly relied upon for a work or school account. That person would also be unable to initiate any DSR requests through Microsoft directly in instances where Microsoft is the data controller. For more information, see the [Product and services authenticated with an Org ID for which Microsoft is a data controller](#product-and-services-authenticated-with-an-org-id-for-which-microsoft-is-a-data-controller) section in Part 4 of this guide.

>[!NOTE]
>In the event that you are a customer currently engaged in FastTrack migrations, deleting the user account will not delete the data copy held by the Microsoft FastTrack team, which is held for the sole purpose of completing the migration. If, during the migration, you would like the Microsoft FastTrack team to also delete the data copy, you can [submit a request](https://go.microsoft.com/fwlink/?linkid=874544). In the ordinary course of business, Microsoft FastTrack will delete all data copies once the migration is complete.

与前文所述有关删除个人数据的软删除和硬删除数据相似，删除用户帐户时，也有软删除和硬删除状态。

- 最初删除用户帐户（通过在管理中心或 Azure 门户中删除用户）时，用户帐户被软删除，并在最多 30 天后移动到 Azure 中的回收站。 此时，可以还原该用户帐户。
- If you permanently deleted the user account, the user account is hard-deleted and removed from the Recycle Bin in Azure. At this point, the user account can't be restored, and any data associated with the user account will be permanently removed from the Microsoft cloud. Hard-deleting an account deletes system-generated logs about the data subject, except for data that may compromise the security or stability of the service.

下面是从组织删除用户的高级流程。

1. 转到管理中心或 Azure 门户，并找到用户。

2. Delete the user. When you initially delete the user, the user's account is sent to the Recycle Bin. At this point, the user is soft-deleted. The account is retained in the soft-deleted for 30 days, which allows you to restore the account. After 30 days, the account is automatically hard-deleted. For specific instructions, see [Delete users from Azure AD](https://docs.microsoft.com/azure/active-directory/add-users-azure-active-directory).<br><br> 还可在管理中心软删除用户帐户。 请参阅[从组织中删除用户](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)。

3. 如果不想等到 30 天后才硬删除用户帐户，可以手动进行硬删除。 要在 Azure 门户中执行此操作，请转到最近删除的用户列表并永久删除用户。 此时，用户被硬删除。 有关说明，请参阅[如何永久删除最近删除的用户](https://docs.microsoft.com/azure/active-directory/active-directory-users-restore)。

无法在 Office 365 管理门户中硬删除用户。

>[!NOTE]
>In Office 365 operated by 21Vianet (China), you can't permanently delete a user as previously described. To permanently delete a user, you can submit a request via the Office 365 admin portal at this [URL](https://portal.partner.microsoftonline.cn/AdminPortal/Home#/homepage). Go to **Commerce** and then select **Subscription** -> **Privacy** ->  **GDPR** and enter the required information.

### <a name="removing-exchange-online-data"></a>删除 Exchange Online 数据

删除用户时，需要注意用户的 Exchange Online 邮箱会发生哪些变化。 硬删除用户帐户后（在先前流程的步骤 3 中），已删除用户的邮箱未自动从 Office 365 中清除。 硬删除用户帐户后，需要最多 60 天才可从 Office 365 中永久删除该用户帐户。 下面描述了删除用户帐户后的邮箱生命周期，以及该期间内邮箱数据的状态：

- **第 1 天 — 第 30 天** — 可通过还原软删除的用户帐户完全还原邮箱。
- **第 31 天 — 第 60 天** — 在硬删除用户帐户 30 天后，组织中的管理员可恢复邮箱中的数据，并将其导入其他邮箱。 这样，组织将能在必要时恢复邮箱数据。
- **第 61 天 – 第 90 天** - 管理员不再能恢复邮箱中的数据。 邮箱数据将被标记为永久删除，并且最多还要 30 天才会被从 Office 365 中清除。

如果确定此邮箱生命周期无法满足组织响应 DSR 删除请求的要求，可在硬删除用户帐户*后*[联系 Microsoft 支持部门](https://support.microsoft.com/)，请求 Microsoft 手动启动永久删除邮箱数据的流程。 此永久删除邮箱数据的流程在邮箱生命周期的第 61 天自动开始，因此没有理由在生命周期的此时间点后联系 Microsoft。

## <a name="using-in-app-functionality-to-respond-to-dsrs"></a>使用应用内功能响应 DSR

While most Customer Data is authored and produced using the applications described in the previous section, Office 365 also offers many other applications that customers can use to produce and store Customer Data. However, Content Search doesn't currently have the ability to find data authored in these other Office 365 applications. To find data generated by these applications, you or the data owner must use in-product functionality or features to find data that may be relevant to a DSR. The following table lists these Office 365 applications. Click the application icon to go the section in this guide that describes how to respond to DSR requests for data authored in the application.

***表 3：可在其中使用应用内功能查找客户数据的应用程序***

||||
|:-----:|:-----:|:-----:|:-----:|
| ![Access 图标](../media/o365-access-64x64.png) <br> [Access](#access) | ![Office 图标](../media/O365-DSR-Doc_image22.png) <br> [Business App <br> for Office 365](#business-apps-for-office-365) | ![Office 图标](../media/O365-DSR-Doc_image22.png) <br> [教育版](#education)|
| ![Flow 图标](../media/o365-flow-64x64.png) <br> [Flow](#flow) | ![Forms 图标](../media/o365-forms-64x64.png) <br> [Forms](#forms) |![Kaizala 图标](../media/o365-kaizala-64x64.png) <br> [Kaizala](#kaizala) |
| ![Planner 图标](../media/o365-planner-64x64.png) <br> [Planner](#planner) |![PowerApps 图标](../media/o365-powerapps-64x64.png) <br> [Power Apps](#powerapps) |![Power BI 图标](../media/o365-powerbi-64x64.png) <br> [Power BI](#power-bi) |
|![Project 图标](../media/o365-project-64x64.png) <br> [Project](#project-online) |![Publisher 图标](../media/o365-publisher-64x64.png) <br> [Publisher](#publisher) |![Stream 图标](../media/o365-stream-64x64.png) <br> [Stream](#stream) |![Sway 图标](../media/o365-sway-64x64.png) <br> [Sway](#sway) | ![Whiteboard 图标](../media/O365-DSR-Doc_image36.png) <br> [Whiteboard](#whiteboard) |
|![Yammer 图标](../media/o365-yammer-64x64.png) <br> [Yammer](#yammer) |
|||

### <a name="access"></a>Access

以下各节介绍如何在 Microsoft Access 中使用应用内功能查找、访问、导出和删除个人数据。

##### <a name="discover"></a>发现

There are several ways that you can search for records in an Access database that might be responsive to a DSR request. For a DSR investigation, you can search for records that related to the data subject or search for records that contain specific data. For example, you could either search or go to a record that corresponds to the data subject. Or you can search for records that contain specific data, such as personal data about the data subject. For more information, see:

- [在 Access 数据库中查找记录](https://support.microsoft.com/zh-CN/office/find-records-in-an-access-database-705220b7-0255-4ef9-9349-6bd7442d1b7e) 
- [创建简单的选择查询](https://support.office.com/article/create-a-simple-select-query-de8b1c8d-14e9-4b25-8e22-70888d54de59)

##### <a name="access"></a>Access

After you find the records or fields that are relevant to the DSR request, you can take a screenshot of the data or export it to an Excel file, Word file, or a text file. You can also create and print a report based on a record source, or a select query that you created to find the data. See:

- [Access 中的报表简介](https://support.office.com/article/introduction-to-reports-in-access-e0869f59-7536-4d19-8e05-7158dcd3681c)
- [将数据导出到 Excel](https://support.office.com/article/export-data-to-excel-64e974e6-ae43-4301-a53e-20463655b1a9)
- [将数据导出到 Word 文档](https://support.microsoft.com/zh-CN/office/export-access-data-to-a-word-document-6e954c8e-2243-4cb9-8544-607e5b7bfc12)
- [将数据导出到文本文件](https://support.microsoft.com/zh-CN/office/export-data-to-a-text-file-f72dfc38-a8a0-4c5b-8c2c-bf2950814140)

##### <a name="export"></a>导出

如前所述，可将数据从 Access 数据库导出为不同文件格式。 选择导出的文件格式可能由来自数据主体的特定 DSR 导出请求决定。 有关如何以不同的文件格式导出 Access 数据的主题列表，请参阅[导入和导出](https://support.microsoft.com/zh-CN/office/import-and-export-c060505b-d8ac-4499-8879-733e56c6106f)。

##### <a name="delete"></a>删除

可从 Access 数据库删除整个记录或仅删除一个字段。 从 Access 数据库删除记录的最快方式是在数据表视图中打开表，选择要删除的字段中的记录（行）或仅数据，然后按“Delete”。 此外可以使用为查找数据而创建的选择查询，然后将其转换为删除查询。 请参阅：

- [从数据库删除一个或多个记录](https://support.office.com/article/ways-to-add-edit-and-delete-records-5e90a80c-106d-4c55-996e-07d7200980ce)
- [创建并运行删除查询](https://support.office.com/article/create-and-run-a-delete-query-6da65fe1-0fc7-4a64-8ef0-c052cd4c3ec5)

### <a name="business-apps-for-office-365"></a>Business Apps for Office 365

该部分介绍如何使用以下每个 Business Apps for Office 365 中的应用内功能对 DSR 请求作出响应。

- [Bookings](#bookings)
- [企业一览表](#listings)
- [Connections](#connections)
- [Outlook Customer Manager](#outlook-customer-manager)
- [Invoicing](#invoicing)

#### <a name="bookings"></a>Bookings

以下各部分介绍如何使用 Microsoft Bookings 中的应用内功能查找、访问、导出和删除个人数据。 此方法适用于独立 Bookings 应用，也适用于通过业务中心访问的 Bookings。

Microsoft Bookings allows administrators and users or staff, with a Bookings license in their organization, to set up booking pages so customers can schedule and make changes to appointments, receive confirmation emails, updates, cancellation, and reminders email. Business owners and their staff can also book events on behalf of their customers with Bookings. 

客户、管理员或员工可以创建以下类型的数据：

- **客户、合作伙伴和好友的联系信息** - 此数据包含姓名、电话号码、电子邮件、地址和备注。

    - 可以使用 Bookings Web、iOS 和 Android 客户端手动创建任何人的联系人。
    
    - 任何人的联系人都可以从 C1 的移动设备导入到使用 Bookings iOS 和 Android 客户端的 Bookings。
    
    - 联系人也可以通过已预订的任何人的预订工作流在创建预订时自动创建，而不考虑预订是由用户代表客户创建的，还是由客户使用所有者的预订页面创建的。

- **预订事件** - 预订事件是业务所有者或其指定员工与客户之间的会议，这些会议是业务所有者或客户通过业务所有者的公开预订页面创建。 此数据包括姓名、地址、电子邮件地址、电话号码以及业务所有者在预订时从客户处收集的任何其他信息。

- **电子邮件确认/取消/更新** - 这些是系统生成和发送的与特定预订事件关联的电子邮件消息。 这些消息包含预定交付相关服务的员工的相关信息，并包含业务所有者或客户在预订时输入的客户的相关个人信息。

所有客户内容都存储在托管组织 Bookings 的 Exchange Online 邮箱中。 只要业务所有者和客户在服务中处于活动状态，就会保留该内容，除非他们明确要求删除数据或者离开服务。 该内容可通过产品内 UI、cmdlet 或通过删除相关预订邮箱进行删除。 一旦启动删除操作，数据将在业务所有者设置的时间段内被删除。 

如果客户决定不再使用这些服务，将在 90 天后删除其客户内容。 有关在用户帐户删除后删除邮箱内容的详细信息，请参阅[删除 Exchange Online 数据](#removing-exchange-online-data)。

#### <a name="end-user-identifiable-information"></a>最终用户身份信息

End user Identifiable Information (EUII) includes personal and contact information about the staff that gets scheduled in Bookings. It's added to the Staff details pages when the business owner sets up Bookings and makes updates after the setup. It contains staff member's name, initials, email address, and phone number. This data is stored in the Exchange Online mailbox that hosts Bookings.

This data is retained for as long as the staff member is active in the service unless it's explicitly deleted the business owner or an admin using the in-app UI or by deleting the relevant booking mailbox. When the admin initiates the deletion of staff's details, or if the staff member leaves the service, their details are deleted in accordance with the Exchange Online mailbox's content retention policies set by the business owner or admin.

##### <a name="discoveraccess"></a>发现/访问

Bookings 收集并将存储以下类型数据：

- **公司档案信息：** 有关使用 Bookings 的业务的客户内容是通过 Bookings 的业务信息表单收集的，并且如果客户将 Bookings 与业务中心一起使用，该内容还将与业务中心的公司档案同步。 与此数据关联的唯一 EUII 是 C1 的电子邮件地址。 新的预订通知和更新电子邮件将发送到此地址。
- **客户联系人：** 可以在 Bookings Web、iOS 和 Android 版客户端中手动创建联系人，也可以从移动设备导入联系人。 在使用自助预订页面期间，也会自动创建联系人。 它们包含 EUII，并且存储在 Bookings 邮箱中。
- **员工详细信息：** 客户内容包括有关员工的数据，这些员工有资格交付通过 Bookings Web、iOS 或 Android 版客户端创建的服务。 员工详细信息可包含姓名、电子邮件地址和电话号码。
- **预订事件：** 这些事件是客户会议以及企业使用 Web 客户端或 Android/iOS 应用创建的相关客户内容，或者是客户使用公共预订页面（或 Facebook 页面）创建的客户内容。 这些事件可包括姓名、地址、电子邮件地址、电话号码和约会详细信息。
- **会议请求、电子邮件确认/取消/更新以及电子邮件提醒：** 这些是系统发送的与预订关联的电子邮件消息。 它们包含员工数据以及在预订时输入的客户数据。

##### <a name="export"></a>导出

To export data corresponding to the business owner, staff and customers, you can use the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>删除

可以删除以下类型的 Bookings 数据以响应 DSR 删除请求：

- **业务配置文件信息和联系人：** 你可以在管理中心中删除 Bookings 邮箱。 删除邮箱后，你可以在 30 天内将其还原。 30 天后，该帐户及相应的邮箱将被永久删除。 有关删除用户帐户的详细信息，请参阅[删除用户](#deleting-a-user)部分。
- **员工详细信息：** 你可以从 Bookings 仪表板中删除员工。 若要永久删除员工，你可以删除其 Office 365 帐户。
- **预订事件：** 你可以从 Bookings 日历中删除预订事件，这将移除客户的信息。
- **会议请求、电子邮件确认/取消/更新和电子邮件提醒：** 你可以从 Bookings 日历中删除这些内容，这将移除客户的信息。

Business owners and admins can also delete their customer's data by using the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

Additionally, you can delete business owner and staff data, you can delete the corresponding user account. See the section  [Deleting a user](#deleting-a-user).

#### <a name="listings"></a>企业一览表

以下各节介绍如何在 Microsoft 企业一览表中使用应用内功能查找、访问、导出和删除个人数据。

##### <a name="discover"></a>发现

企业一览表所有者可以将其业务连接到 Google、必应、Yelp 和 Facebook 以查看评级和评论的聚合视图。 企业一览表收集并存储以下类型数据：

- Google 评论和评级
- 必应评论和评级
- Yelp 评论和评级
- Facebook 评论和评级

##### <a name="access"></a>访问
企业一览表所有者可以登录到企业一览表仪表板以查看自己的评论和评级。

##### <a name="export"></a>导出

To export business owner, staff and customer data, use the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>删除

If a Listings owner would like to delete their Listings information, they can disconnect from the provider on the Listings page. After they disconnect, their Listings information will be deleted.

#### <a name="connections"></a>Connections

以下各节介绍如何在 Microsoft Connections 中使用应用内功能查找、访问、导出和删除个人数据。

##### <a name="discover"></a>发现

Connections 收集并将存储以下类型数据： 

- 客户/联系人是由企业使用 Web 客户端或移动应用（iOS、Android）创建的，或者向业务联系人发送电子邮件市场营销活动时使用应用创建而成。 客户数据可包括姓名、地址、电子邮件地址和税务 ID 号。 联系人在所有业务中心应用中共享。
- 客户可以在 Connections 注册页面上进行注册并保存其个人信息。
- 电子邮件营销活动中的链接

##### <a name="access"></a>Access

Connections 所有者可以登录到 Connections 仪表板并查看他们发送的电子邮件营销活动。

##### <a name="export"></a>导出

To export business owner, staff and customer data, use the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>删除

After a Connections owner sends an email campaign, they can't delete the campaign. If there are any draft campaigns they want to delete, they can sign in to the Connections dashboard and delete the draft campaigns.

#### <a name="outlook-customer-manager"></a>Outlook Customer Manager

以下各节介绍如何在 Outlook Customer Manager 中使用应用内功能查找、访问、导出和删除个人数据。

##### <a name="discover"></a>发现

Outlook Customer Manager 收集并存储 Outlook Customer Manager 所有者及其客户和业务联系人的用户信息。

- Owner data. This includes name, address, and email address. Documents and files that an owner shares with a customer are stored in OneDrive for Business, SharePoint Online, and as tasks in Outlook.
- Customer and business contact data. Customer data can include name, address, and email address. Customer and contact data is created by the business in Outlook or Outlook web app. Contacts are shared across Business center. Documents and files that a customer shares with a business are stored in OneDrive for Business, SharePoint Online, and as tasks in Outlook.

Outlook Customer Manager 还在 Exchange 中存储有关客户的活动和见解。

##### <a name="access"></a>Access

Outlook Customer Manager 所有者可以登录到 Outlook 或 Outlook Web 应用中，然后转到 Outlook Customer Manager 仪表板查看他们以前与客户之间的交互。

##### <a name="export"></a>导出

To export business owner and customer data, use the Outlook Customer Manager privacy portal. For details. See [Export or delete user data using the Outlook Customer Manager privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>删除

To delete customer data, use the Outlook Customer Manager privacy portal. See [Export or delete user data using the Outlook Customer Manager privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

#### <a name="invoicing"></a>Invoicing

以下各节介绍如何在 Microsoft Invoicing 中使用应用内功能查找、访问、导出和删除个人数据。

##### <a name="discover"></a>发现

Invoicing 收集并将存储以下类型数据：

- **联系人：** 联系人是在为客户/业务联系人创建发票或估算时由企业创建的。 联系人在业务中心中是共享的。 客户数据包括姓名、地址、电子邮件地址和报税号。
- **发票：** 系统会创建发票并将其发送给客户，并且发票同时代表债务责任和纳税责任。
- **估算：** 企业还可将估算发送给客户。 如果客户接受估算，则其将转换为发票。 估算将在客户接受后转换为发票。 估算记录在转换为发票后不会保留。

##### <a name="access"></a>Access

用户可以转到其业务中心的 Invoicing 仪表板，查看他们所创建的发票草稿和已经向客户显示的发票。

##### <a name="export"></a>导出

To export customer invoicing data, use the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>删除

After an invoice is created and sent, it can't be deleted due to accounting laws. The Invoicing owner can request that Microsoft delete some or all their information from Office 365.

Alternatively, you can delete the invoicing owner's user account in Office 365. See the section [Deleting a user](#deleting-a-user).

### <a name="education"></a>教育

该部分介绍如何使用以下 Microsoft 教育版应用中的应用内功能对 DSR 请求作出响应。

- 作业
- 课堂笔记本

#### <a name="assignments"></a>作业

以下各节介绍如何在作业中使用应用内功能查找、访问、导出和删除个人数据。

##### <a name="discoveraccess"></a>发现/访问

Assignments stores information that is generated both by teachers and students. Some of this information is store in SharePoint and some is stored in a non-SharePoint location.

##### <a name="finding-assignments-data-stored-in-sharepoint"></a>查找存储在 SharePoint 中的作业数据

Students files associated with a Submission for Assignment are stored in a document library (named **Student Work**) and files associated with Assignments that are created by teachers and (accessible by students) are stored in a different document library (named **Class Files**). Both document libraries are in the corresponding Class Team SharePoint site.

管理员可使用安全与合规中心的内容搜索工具搜索与作业提交相关的学生文件（在“学生作业”和“课堂作业”库中）以及与作业相关的文件。 例如，管理员可搜索组织中的所有 SharePoint 网站，并在搜索查询中使用学生姓名和课程/作业名称，以查找与 DSR 请求相关的数据。

同样，管理员可在与作业相关的教师文件中搜索教师分配给学生的文件。 例如，管理员可搜索组织中的所有 SharePoint 网站，并在搜索查询中使用教师姓名和班级或作业名称来查找与 DSR 请求相关的数据。

有关详细信息，请参阅：

- [作业管理员文档](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-admin-documentation)
- [使用内容搜索电子数据展示工具响应 DSR](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)（在本指南中）

##### <a name="finding-assignments-data-not-stored-in-sharepoint"></a>查找未存储在 SharePoint 中的作业数据

以下类型的作业数据未存储在课堂团队 SharePoint 网站中，因此无法使用内容搜索发现。 此数据包含以下信息：

- 学生成绩和教师反馈
- 每个学生为作业提交的文档列表
- 作业详细信息，如作业的截止日期

To find data, an admin or a teacher would have to go into the Assignment in the Class Team site to find data that may be relevant to a DSR request. An admin can add themselves as an owner to the class and view all the assignments for that class team.

即使学生不再是课堂成员，其数据仍然可能会出现在课堂中，并标记为“不再选修”。 本例中，提交 DSR 请求的学生必须向管理员提供已经正式选修的课程列表。

##### <a name="export"></a>导出

对于特定学生注册参加的所有课程，可使用 PowerShell 脚本获取该学生的课程列表，然后使用 PowerShell 脚本导出其作业数据。 请参阅：

- [配置 Teams 的作业](https://docs.microsoft.com/microsoft-365/education/deploy/configure-assignments-for-teams)
- [获取特定学生的课程列表](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-get)
- [从作业中导出学生和教师数据](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-export)。

If the student has been removed from the Team Class site, the admin can add the student back to the site before running the export script. Or the admin can use the input file for the script to identify every class that the student was ever enrolled in. You can also use the Assignment export script to export submissions data for all assignments that a teacher has access to.

##### <a name="delete"></a>Delete

对于特定学生注册参加的所有课程，可使用 PowerShell 脚本获取该学生的课程列表，然后使用 PowerShell 脚本删除其作业数据。 应在从课程中删除学生之前执行此操作。 请参阅：

- [配置 Teams 的作业](https://docs.microsoft.com/microsoft-365/education/deploy/configure-assignments-for-teams)
- [获取特定学生的课程列表](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-get)
- [从作业中删除学生数据](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-delete)。

If the student has been removed from the Team Class site, the admin can add the student back to the site before running the export script. Or the admin can use the input file for the script to identify every class that the student was ever enrolled in. You can't use the Assignments deletion script to delete teacher data because all Assignments are shared across the Class Team site. As an alternative, an admin would have to add themselves to the Class Team site and then delete a specific Assignment.

#### <a name="class-notebook"></a>课堂笔记本

本指南前面讨论了在课堂笔记本中搜索内容。 请参阅 [OneNote 课堂笔记本](#onenote-class-notebook)部分。 内容搜索工具还可用于从课堂笔记本中导出数据。 或者，管理员或数据主体也可从课堂笔记本中导出数据。 请参阅[保存课堂笔记本副本](https://support.office.com/article/44733e18-0ef1-4d4b-be51-fc2ac5bfe9ec)。

### <a name="flow"></a>Flow

以下各节介绍如何在 Microsoft Flow 中使用应用内功能查找、访问、导出和删除个人数据。

#### <a name="discover"></a>发现

People can use Flow to perform data-related tasks such as synchronizing files between applications, copying files from one Office 365 service to another, and collecting data from one Office 365 app and storing it in another. For example, a user could set up a Flow to save Outlook email attachments to their OneDrive for Business account. In this example, you could use the Content Search tool to search the user's mailbox for the email message that contained the attachment or search their OneDrive for Business account for the file. This is an example where data handled by Flow might be discoverable in the Office 365 services connected by a Flow workflow.

Additionally, people can use Flow to copy or upload files from Office 365 to an external service, such as Dropbox. In these cases, a DSR request concerning the data in an external service would have to be submitted to the external service, who is processing the data in this type of scenario.

如果管理员收到 DSR 请求，他们可将自己添加为用户流的所有者。 这使管理员能够执行导出流定义、运行历史记录和执行流权限重新分配等功能。 请参阅[在管理中心管理流](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/)。

要将自己添加为 Flow 的所有者，管理员需要具有以下权限的帐户：

- Flow/PowerApps 计划 2 许可证（付费或试用版）

- [全局管理员\ ](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)

    或

- [Azure Active Directory 全局管理员](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)

具有这些特权的管理员可使用 Flow 管理中心访问组织中的所有流。

将自己添加为某个流的所有者。

1. 转到 <https://admin.flow.microsoft.com>
2. 使用 Office 365 帐户登录。
3. 在“**环境**”页面上，单击要访问的流的环境。 组织具有一个默认环境。
4. On the page for the environment that you selected, click **Resources**, and then click **Flows.** A list of all flows in the environment is displayed.
5. 单击要将自己添加为其成员的流对应的“查看详细信息”****。
6. 在“**所有者**”下，单击“**管理共享**”。
7. 在“**共享**”浮出控件上，将自己添加为成员，然后保存更改。

使自己成为所有者后，转到“**流**”\>“**我的流**”\>“**团队流**”以访问流。 可在其中下载运行历史记录或导出流。 请参阅：

- [Download flow run history](https://flow.microsoft.com/blog/download-history-recurrence/)（下载流运行历史记录）
- [Export and import your flows across environments with packaging](https://flow.microsoft.com/blog/import-export-bap-packages/)（通过打包导出和导入各环境中的流）

#### <a name="access"></a>访问

用户可以访问流的定义和运行历史记录。

- **流定义：** 用户可以导出流的定义（导出为 Flow 包，格式化为压缩文件中的 JSON）。 请参阅[通过打包导出和导入各环境中的流](https://flow.microsoft.com/blog/import-export-bap-packages/)。
- **流运行历史记录：** 用户可以下载其每个流的运行历史记录。 流运行历史记录下载为 CSV 文件，可在 Excel 中打开以进行筛选和搜索。 用户还可以下载多个流的运行历史记录。 请参阅[下载流运行历史记录](https://flow.microsoft.com/blog/download-history-recurrence/)。

#### <a name="delete"></a>删除

管理员可在 Flow 管理中心将自己添加为用户流的所有者。 如果用户离开组织并且其 Office 365 帐户已被删除，将会保留他们是唯一所有者的流。 这有助于组织为流切换新的所有者，并避免可能用于共享业务进程的流的相关业务出现任何中断。 然后，管理员需要确定是删除归该用户所有的流，还是重新分配给新的所有者，并采取行动。

对于共享流，从组织中删除用户时，将从所有者列表中删除其姓名。

#### <a name="export"></a>导出

An admin can export the definition and run history of a user's flows. To do this, an admin must add themselves as an owner of the user's flow in the Flow admin center

- **流定义** - 管理员将自己添加为流的所有者后，可转到“**流**”\>“**我的流**”\>“**团队流**”导出流定义（导出为 Flow 包，格式化为压缩文件中的 JSON）。 请参阅[通过打包导出和导入各环境中的流](https://flow.microsoft.com/blog/import-export-bap-packages/)。

- **流运行历史记录：** 同样，管理员必须将自己添加为某个流的所有者才可导出其流运行历史记录。 流运行历史记录下载为 CSV 文件，可在 Excel 中打开以进行筛选和搜索。 还可以下载多个流的运行历史记录（只要具有所有权）。 请参阅[下载流运行历史记录](https://flow.microsoft.com/blog/download-history-recurrence/)。

#### <a name="connections-and-custom-connectors-in-flow"></a>Flow 中的连接和自定义连接器

连接需要用户提供凭据才可连接到 API、SaaS 应用程序和自定义开发系统。 这些连接归建立该连接的用户所有，并且可在产品内[管理](https://docs.microsoft.com/flow/add-manage-connections)。 重新分配流后，管理员可使用 PowerShell cmdlet 列出这些连接，并在删除用户数据时删除这些连接。

使用自定义连接器，组织可通过连接到未提供现成连接器的系统来扩展流的功能。 自定义连接器作者可与组中的其他人[共享](https://docs.microsoft.com/flow/register-custom-api)其连接器。 收到 DSR 删除请求后，管理员应考虑重新分配这些连接器的所有权，以避免业务中断。 要加快此流程，管理员可使用 PowerShell cmdlet 来列出、重新分配或删除自定义连接器。

### <a name="forms"></a>Forms

以下各节介绍如何在 Microsoft Forms 中使用应用内功能查找、访问、导出和删除个人数据。

#### <a name="discover"></a>发现

Forms users can go to <https://forms.office.com> and select **My forms** to see the Forms they've created. They can also select **Shared with me** to view Forms others have shared via a link. If there are many Forms to sort through, users can use the in-product search bar to search for Forms by title or author. To determine whether Microsoft Forms is a place where personal data responsive to your DSR is likely to reside, you can ask the Data Subject to search his or her **Shared with me** list to determine which users ("Forms owners") have sent Forms to the Data Subject. You can then ask the forms owners to select **Share** in the top navigation bar and send you a link to a specific form so you can view it and further determine whether it is material to your DSR.

#### <a name="access"></a>Access

找到相关表单后，可通过单击“**响应**”选项卡访问对表单的响应。深入了解如何[检查测验结果](https://support.microsoft.com/zh-CN/office/check-and-share-your-quiz-results-c4a9b45c-d62f-4eb7-b5db-ad81892c7c07)或[表单结果](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af)。 要在 Excel 中查看响应结果，请选择“**响应**”选项卡，然后单击“**在 Excel 中打开**”。 如果要向数据主体发送表单副本，可以对应用程序中以 RTF 格式显示的相关问题和解答进行屏幕截图，或向数据主体发送结果的 Excel 副本。 如果在使用 Excel，并且只想与数据主体共享部分调查结果，可先删除某些行或列，或修订剩余部分，然后再共享结果。 或者，可以转到 **“共享”\>“获取链接以复制”**（在“共享为模板”下），为数据主体提供整个表单的副本。

#### <a name="delete"></a>删除

Any survey, quiz, questionnaire, or poll can be permanently deleted by its owner. If you would like to honor a DSR "forget me" and delete a form in its entirety, find the Form in the list of forms, select the series of dots (ellipsis) in the upper right corner of the form preview window, and then click **Delete**. Once a Form is deleted, it can't be retrieved. For information, see [Delete a Form](https://support.microsoft.com/zh-CN/office/delete-a-form-2207e468-ce1b-4c4a-a256-caf631d87af0).

#### <a name="export"></a>导出

要导出表单问题并响应 Excel 文件，请打开表单，选择“**响应**”选项卡，然后选择“**在 Excel 中打开**”。

### <a name="kaizala"></a>Kaizala

以下各节介绍如何在 Microsoft Kaizala 中使用应用内功能查找、访问、导出和删除个人数据。

#### <a name="discover"></a>发现

A user's organizational data, which is data that is shared in organizational groups, can be accessed by an admin from the Kaizala management portal. Organizational data is retained for a duration of time determined by your organization's retention policies. In addition to user data, Kaizala servers also store the following types of organizational data:

- 组织组一部分的成员列表
- 组织组消息数据，它们是跨组织组共享的消息和响应
- 组织中的用户列表
- 为组织中所有用户捕获的产品和服务使用情况数据。
- 组织创建的 Kaizala 操作
- Kaizala 连接器数据

A user's consumer data can be accessed by the data subject using the Kaizala mobile app for consumer data. Consumer data includes the following types of data:

- Kaizala 上的专用组数据（存储在 Kaizala 服务器长达 90 天）
- 用户个人资料信息，以及用户联系人
- 和用户同组的成员列表
- 在组间共享的组消息和响应
- 用户的联系人列表（存储在 Kaizala 服务上）
- 由 Kaizala 用户所执行的事务（仅适用于印度的 Kaizala 用户）
- 用户的产品和服务使用情况数据

#### <a name="access"></a>Access

Kaizala users can go to their mobile device to see Kaizala content they've created on their device. To determine whether Kaizala mobile apps is a place where personal data responsive to a DSR is likely to reside, you can ask the data subject to search their Kaizala app for the requested information.

#### <a name="export"></a>导出

When users in your organization use Kaizala, consumer data is generated, and organizational data may be generated if the user participates in an organization group. Admins can export a user's organizational data from the Kaizala management portal. Kaizala consumer users can export their private data from the Kaizala mobile app. In both cases, note that product and service usage data is also export when an admin or user exports Kaizala data. For details, see:

- [导出或删除 Kaizala 中的用户组织数据](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)
- [导出或删除 Kaizala 移动应用中的数据](https://docs.microsoft.com/office365/kaizala/export-or-delete-your-data)

#### <a name="delete"></a>删除

A Kaizala admin can remove a Kaizala user's account in the Kaizala management portal. After a user account is deleted, the user is removed from all groups that belong to your organization and organizational data is deleted from their device. 

To remove all private data from the user's mobile device, the Kaizala user can delete their Kaizala account. After the account is deleted, all related Kaizala content including, chats, photos, and other data will be deleted from the device.

有关详细信息，请参阅：

- [导出或删除 Kaizala 中的用户组织数据](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)
- [导出或删除 Kaizala 移动应用中的数据](https://docs.microsoft.com/office365/kaizala/export-or-delete-your-data)

### <a name="planner"></a>规划器

以下各节介绍如何在 Microsoft Planner 中使用应用内功能查找、访问、导出和删除个人数据。

#### <a name="discover"></a>发现

Planner 计划与 Microsoft 365 组关联，而 Microsoft 365 组的文件存储在组的关联 SharePoint Online 网站中。 这意味可以使用内容搜索，通过搜索网站中的 Microsoft 365 组来查找 Planner 文件。 要执行此操作，需要有 Microsoft 365 组的 URL。 请参阅“Office 365 中的内容搜索”帮助主体中的[搜索 Microsoft Teams 和 Microsoft 365 组](https://docs.microsoft.com/microsoft-365/compliance/content-search)，了解有关获取 Microsoft 365 组相关信息的提示，了解如何在对应的 SharePoint Online 网站中搜索 Planner 文件。

#### <a name="access"></a>Access

如前所述，你可以搜索基础 SharePoint Online 网站和与计划关联的邮箱。 然后，你可以预览或下载相关搜索结果来访问数据。

#### <a name="delete"></a>删除

You can manually delete a user's personally information by either giving yourself permissions to access the plans the user is part of or signing in as the user to make the changes. See [Delete user data in Microsoft Planner](https://support.office.com/article/delete-user-data-in-microsoft-planner-4349ded2-1891-4896-8e27-05fd40f3929f).

#### <a name="export"></a>导出

You can use a PowerShell script to export a user's data from Planner. When you export the data, a separate JSON file is export for each plan that the user is a part of. See [Export user data from Microsoft Planner](https://support.office.com/article/export-user-data-from-microsoft-planner-91258c96-b353-4da1-b6d9-d78e4809cf08).

### <a name="power-bi"></a>Power BI

以下各节介绍如何在 Microsoft Power BI 中使用应用内功能查找、访问、导出和删除个人数据。

#### <a name="discover"></a>发现
You can search for content in the different workspaces in Power BI, including dashboards, reports, workbooks, and datasets. Each type of workspace contains a search field that you can use to search that workspace. See [Searching, finding, and sorting content in Power BI service](https://docs.microsoft.com/power-bi/service-navigation-search-filter-sort).

#### <a name="access"></a>Access

可在 Power BI 中打印仪表板、报表以及报表中的视觉对象。 无法打印整个报表；一次只能打印一页。 为此，请转到报表，使用搜索字段查找特定数据，然后打印该页面。 请参阅[从 Power BI 服务打印](https://docs.microsoft.com/power-bi/service-print)。

#### <a name="delete"></a>删除

要删除仪表板、报表和工作簿，请参阅[删除 Power BI 服务中的几乎任何内容](https://docs.microsoft.com/power-bi/service-delete)。

Deleting a dashboard, report, or workbook doesn't delete the underlying dataset. Because Power BI relies on a live connection to the underlying source data to be complete and accurate, deleting personal data must be done there. (For example, if you created a Power BI report that is connected to Dynamics 365 for Sales as the live data source, you would have to make any corrections to the data in Dynamics 365 for Sales.)

删除数据之后，可以使用 Power BI 中的[计划的数据刷新](https://docs.microsoft.com/power-bi/refresh-scheduled-refresh)功能来更新存储在 Power BI 中的数据集，之后，已删除的数据不会再反映在任何之前利用了该数据的 Power BI 报表或仪表板中。 为帮助符合 GDPR 要求，应该制定相应的策略，确保按照适当的节奏刷新数据。

#### <a name="export"></a>导出

为了推进数据移植请求，可导出 Power BI 中的仪表板和报表：

- You can export the underlying data for dashboards and reports to a static Excel file. See the video in [Printing from Power BI service](https://docs.microsoft.com/power-bi/service-print). Using Excel, you can then edit the personal data to be included in the portability request, and save it in a commonly used, machine-readable format such as .csv or .xml.
- You can export (download) a report from the Power BI service in Office 365 to a .pbix file if it was originally published using Power BI Desktop. You can then import this file to Power BI Desktop and publish (export) it to the Power BI service of another organization. See [Export a report from Power BI service to Desktop](https://docs.microsoft.com/power-bi/service-export-to-pbix).

### <a name="powerapps"></a>PowerApps

以下各节介绍了如何在 Microsoft PowerApps 中使用应用内功能查找、访问、导出和删除个人数据。 这些步骤概述了管理员可如何为应用和依赖资源切换新的所有者，以减少业务中断。

#### <a name="discover"></a>发现

PowerApps 是一项服务，可用于生成可在组织内共享和使用的应用。 在生成或运行应用的过程中，用户最终将在 PowerApps 服务中存储多种类型的资源和数据，包括应用、环境、连接、自定义连接器以及权限。

为了帮助推进与 PowerApps 相关的 DSR 请求，可利用在 [PowerApps 管理中心](https://admin.powerapps.com/)和 [PowerApps 管理员 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871804) 中公开的管理操作。 访问这些工具需要具有以下权限的帐户：

- PowerApps 计划 2 付费证或 PowerApps 计划 2 试用版许可证。 可在[此处](https://web.powerapps.com/trial)注册 30 天的试用版许可证。
- [全局管理员](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)或
- [Azure Active Directory 全局管理员](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)

有关查找个人数据的详细信息，请参阅[发现 PowerApps 个人数据](https://go.microsoft.com/fwlink/?linkid=871880)。

PowerApps 服务还包括 Common Data Service For Apps，可让用户在 Common Data Service 数据库的标准和自定义实体中存储数据。 可从 [PowerApps 生成器门户](https://web.powerapps.com)查看存储在这些实体中的数据，并使用[高级查找](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)的产品内搜索功能搜索实体中的特定数据。 有关发现 Common Data Service 中的个人数据的详细信息，请参阅[发现 Common Data Service 个人数据](https://go.microsoft.com/fwlink/?linkid=871881)。

#### <a name="access"></a>Access

管理员能够使用 [PowerApps 管理中心](https://admin.powerapps.com/)或 [PowerApps 管理员 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871804) 为自己分配访问和运行应用以及关联资源（包括流、连接和自定义连接器）的特权。

After you have access to the user's app, you can use a web browser to open the app. After you open an app, you can take a screenshot of the data. See [Use PowerApps in a web browser](https://docs.microsoft.com/powerapps/run-app-browser).

#### <a name="delete"></a>删除

由于 PowerApps 允许用户生成对组织日常运营至关重要的业务线应用，因此，当有用户离开了组织，并且其 Office 365 帐户被删除时，管理员需要确定是要删除归该用户所有的应用，还是仅重新分配给新的所有者。 这有助于组织为应用切换新的所有者，并避免可能用于共享业务的应用流程的相关业务出现任何中断。

对于共享数据（如应用），管理员必须确定是要永久删除该用户的共享数据，还是要通过将数据重新分配给自己或组织中的其他人来保留这些数据。 请参阅[删除 PowerApps 个人数据](https://go.microsoft.com/fwlink/?linkid=871883)。

Any data that was stored by a user in an entity in a Common Data Service For Apps database will also need to be reviewed and (if desired) deleted by an admin using the in-product capabilities. See [Delete Common Data Service user personal data](https://go.microsoft.com/fwlink/?linkid=871886).

#### <a name="export"></a>导出

Admins have the ability to export personal data stored for a user within the PowerApps service using the [PowerApps Admin Center](https://admin.powerapps.com/) and [PowerApps Admin PowerShell cmdlets](https://go.microsoft.com/fwlink/?linkid=871804). See [Export PowerApps personal data](https://go.microsoft.com/fwlink/?linkid=871883).

You can also use the in-product search capabilities of [Advanced Find](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search) to search for a user's personal data in any entity. For details about exporting personal data in the Common Data Service, see [Export Common Data Service personal data](https://go.microsoft.com/fwlink/?linkid=871889).

#### <a name="connections-and-custom-connectors-in-powerapps"></a>PowerApps 中的连接和自定义连接器

连接需要用户提供凭据才可连接到 API、SaaS 应用程序和自定义开发系统。 这些连接归建立该连接的用户所有，并且可在产品内[管理](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection)。 重新分配 PowerApps 后，管理员可使用 PowerShell cmdlet 列些连出这接，并在删除用户数据时删除这些连接。

使用自定义连接器，组织可通过连接到未提供现成连接器的系统来扩展 PowerApps 的功能。 自定义连接器作者可与组中的其他人[共享](https://docs.microsoft.com/connectors/custom-connectors/use-custom-connector-powerapps)其连接器。 收到 DSR 删除请求后，管理员应考虑重新分配这些连接器的所有权，以避免业务中断。 要加快此流程，管理员可使用 PowerShell cmdlet 来列出、重新分配或删除自定义连接器。

### <a name="project-online"></a>Project Online

以下各节介绍如何在 Microsoft Project Online 中使用应用内功能查找、访问、导出和删除个人数据。

#### <a name="discover-and-access"></a>发现和访问

可使用内容搜索来搜索与某个项目关联的 SharePoint Online 网站（首次创建项目时，可选择创建关联的 SharePoint Online 网站）；内容搜索不会搜索 Project Online 中实际项目包含的数据，只会搜索关联的网站。 尽管内容搜索将搜索有关项目的元数据（如主题中提及的人员），但是，这可能有助于查找（和访问）包含 DSR 相关数据的项目。

>[!TIP]
>The URL for the site collection in your organization where sites associated with Projects is **https://\<your org\>.sharepoint.com/sites/pwa**; for example, **https://contoso.sharepoint.com/pwa**. You can use this specific site collection as the location of your content search and then the name of the Project in the search query. Additionally, an IT admin can use the Site Collections page in the SharePoint admin center to get a list of PWA site collections in the organization.

#### <a name="delete"></a>Delete

You can delete information about a user from your Project Online environment. See [Delete user data from Project Online](https://support.office.com/article/delete-user-data-from-project-online-252fa593-9c25-47ed-b861-643fe8bf1cb7).

#### <a name="export"></a>导出

You can a specific user's content from your Project Online environment. This data is exported to multiple files in the JSON format. For step-by instructions see, [Export user data from Project Online](https://support.office.com/article/export-user-data-from-project-online-27f3838d-3dbe-4b98-80dc-df55f851154d). For detailed information about the files that are exported, see [Project Online export json object definitions](https://support.office.com/article/project-online-export-json-object-definitions-ce5faeae-9af4-4696-b847-a1f4f20327c7).

### <a name="publisher"></a>Publisher

以下部分介绍如何使用 Microsoft Publisher 中的应用内功能来查找、访问、导出和删除个人数据。

#### <a name="discover"></a>发现

你可以使用应用内搜索功能，像在大多数 Office 应用程序中一样查找 Publisher 文件中的文本。 请参阅[查找和替换文本](https://support.office.com/article/find-and-replace-text-bfe54275-b7c7-4d0f-904d-a2f38d322268)。

#### <a name="access"></a>访问

找到数据后，你可以获取其屏幕截图，或将其复制并粘贴到 Word 或文本文件中，并将该文件提供给数据使用者。 你也可以将出版物另存为 Word、PDF 或 XPS 文件。 请参阅：

  - [将出版物另存为 Word 文档](https://support.microsoft.com/zh-CN/office/save-a-publication-as-a-word-document-b5eaaae5-6f1b-48c1-bebc-44460376b693)
  - [使用 Publisher 将出版物另存为或转换为 .pdf 或 .xps ](https://support.microsoft.com/zh-CN/office/save-as-or-convert-a-publication-to-pdf-or-xps-using-publisher-657332d0-d2c2-464a-9870-e9b3d22e6469)

#### <a name="export"></a>导出

你可以将实际的 Publisher 文件提供给数据使用者，或者如前所述，你可以将出版物另存为 Word、PDF 或 XPS 文件。 请参阅：

  - [将出版物另存为 Word 文档](https://support.microsoft.com/zh-CN/office/save-a-publication-as-a-word-document-b5eaaae5-6f1b-48c1-bebc-44460376b693)
  - [使用 Publisher 将出版物另存为或转换为 .pdf 或 .xps ](https://support.microsoft.com/zh-CN/office/save-as-or-convert-a-publication-to-pdf-or-xps-using-publisher-657332d0-d2c2-464a-9870-e9b3d22e6469)

#### <a name="delete"></a>删除

你可以从出版物中删除内容、删除整个页面，或者删除整个 Publisher 文件。 请参阅[添加或删除页面](https://support.office.com/article/add-or-delete-pages-daf71e39-86e0-4bbc-a186-d5ec70450b08)。

### <a name="stream"></a>Stream

以下各节介绍如何在 Microsoft Stream 中使用应用内功能查找、访问、导出和删除个人数据。

#### <a name="discover"></a>发现

若要发现可能与数据主体请求相关的生成或上传到 Stream 的内容，Stream 管理员可以运行用户报表，以确定 Stream 用户可能上传、创建或由用户发布的视频、视频说明、组、频道或评论。 有关如何生成报表的说明，请参阅[管理 Microsoft Stream 中的用户数据](https://docs.microsoft.com/stream/managing-user-data)。 报表输出采用 HTML 格式，并且包含可用于导航到可能感兴趣的视频的超链接。 如果想要查看已设置自定义权限的视频而你不是视频原始用户的成员，可在管理员模式下查看，请参阅 [Microsoft Stream 中的管理员功能](https://docs.microsoft.com/stream/manage-content-permissions)。  

#### <a name="access"></a>Access

Depending on the nature of the data subject request, a copy of the report described above can be used help satisfy a data subject request. The user report includes the Stream user's name and unique ID, a list of videos the user uploaded, a list of videos the user has access to, a list of channels the user created, a list of all the groups the user is a member of, and a list of all comments the user left on videos. The report further shows whether the user viewed each video listed in the user report. If you would like to provide the data subject with access to a video to satisfy a DSR request, you can share the video.

#### <a name="export"></a>导出

请参阅 Stream 的访问部分。 

#### <a name="delete"></a>删除

To delete or edit videos or any other Stream content, a Stream admin can select view in admin mode to perform the necessary function. See [Admin capabilities in Microsoft Stream](https://docs.microsoft.com/stream/manage-content-permissions). If a user has left the organization and would like to have their name removed from appearing next to videos that they uploaded, you can remove their name or replace it with another. See [Managing deleted users in Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users).

### <a name="sway"></a>Sway

以下各节介绍如何在 Microsoft Sway 中使用应用内功能查找、访问、导出和删除个人数据。

#### <a name="discover"></a>发现

使用 Sway（位于 [www.sway.com](https://sway.office.com/)）创建的内容仅供所有者和作者已向其授权查看 Sway 的用户查看。 请参阅 [Sway 中的隐私设置](https://support.microsoft.com/zh-CN/office/privacy-settings-in-sway-394b551c-be6f-4bd7-a70a-f318d72bf217)。 要确定 Sway 是否可能包含响应 DSR 的个人数据，可以让数据主体和组织用户搜索其 Sway，并与你共享任何可能包含响应数据主体请求的个人数据的 Sway。 有关如何共享 Sway 的信息，请参阅[共享你的 Sway](https://support.microsoft.com/zh-CN/office/share-your-sway-1cf853b8-ef7e-46b0-b704-003e58d28998) 一文中的“从组织帐户共享 Sway”。

#### <a name="access"></a>Access

如果在 Sway 中发现了要与数据主体共享的个人数据，可通过多种方式为数据主体提供对数据的访问。 可为数据主体提供 Sway 联机版本的副本（如上文所述）；可对 Sway 中要共享的相关部分进行屏幕截图，或者可以打印 Sway 或将其下载到 Word（或转换为 PDF）。 下面的“导出”部分中进一步介绍了如何下载 Sway。

#### <a name="delete"></a>删除

To learn how to delete a Sway, go to the "How do I delete my Sway?" section in [Privacy settings in Sway](https://support.microsoft.com/zh-CN/office/privacy-settings-in-sway-394b551c-be6f-4bd7-a70a-f318d72bf217).

#### <a name="export"></a>导出

要导出 Sway，请打开想要下载的 Sway，选择右上角的一系列点（省略号），选择“**导出**”，然后选择“**Word**”或“**PDF**”。

### <a name="whiteboard"></a>Whiteboard

以下各部分介绍如何在 Microsoft Whiteboard 中使用应用内功能查找、访问、导出和删除个人数据。

- [Surface Hub 上的 Whiteboard 2016](#whiteboard-2016-on-surface-hub)
- [所有其他平台上的 Whiteboard](#whiteboard-for-pc-surface-hub-and-other-platforms)

#### <a name="whiteboard-2016-on-surface-hub"></a>Surface Hub 上的 Whiteboard 2016

本部分介绍如何响应对使用 Surface Hub 上的内置 Whiteboard 2016 应用创建的数据的 DSR 请求。

##### <a name="discover"></a>发现

Whiteboard files (.wbx files) are stored in users' OneDrive for Business account. You can ask the data subject or other users if whiteboards they created may contain personal data responsive to a DSR request. They can share a whiteboard with you, or you can get a copy of it to give to the data subject.

若要访问和转移白板： 

1. Give yourself access to the user's OneDrive for Business account. See the "Get access to the former employee's OneDrive for Business documents" section in [Get access to and back up a former user's data](https://docs.microsoft.com/microsoft-365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data).
2. 转到用户 OneDrive for Business 帐户中的“Whiteboard 应用数据”文件夹，并复制想要转移的白板的 .wbx 文件。
3. 自行访问数据主体的 OneDrive for Business 帐户，然后转至“Whiteboard 应用数据”文件夹。
4. 粘贴上一步中复制的 .wbx 文件。

##### <a name="access"></a>Access

如果在对 DSR 访问请求作出响应的白板中发现了个人数据，则可以以多种方式提供数据主体对白板的访问：

- 获取白板相关部分的屏幕截图。
- Upload a copy of the .wbx file to the data subject's OneDrive for Business account. See the previous section for steps on accessing and transferring .wbx files.
- 将白板副本导出为 .png 文件。

##### <a name="export"></a>导出

如果已获得白板副本，可以将其导出。 

1. 在 Surface Hub 上启动 Whiteboard。
2. Tap the Share button and then select Export a copy.
You can export a whiteboard to a OneNote (.one) file or to an image (.png) file.

##### <a name="delete"></a>删除

可以自行访问用户的 OneDrive for Business 帐户，然后删除白板。

1. Give yourself access to the data subject's OneDrive for Business account. See the "Get access to the former employee's OneDrive for Business documents" section in [Get access to and back up a former user's data](https://docs.microsoft.com/microsoft-365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data)
2. 请转到“Whiteboard 应用数据”文件夹，然后删除此文件夹的内容。

#### <a name="whiteboard-for-pc-surface-hub-and-other-platforms"></a>适用于电脑、Surface Hub 和其他平台的 Whiteboard

If an admin receives a DSR request for data in the new Whiteboard app, they can use Whiteboard PowerShell to add themselves (or other users) as an owner of a user's whiteboards. This enables an admin to perform actions including accessing, exporting, and deleting whiteboards. Use either the **Set-WhiteboardOwner** cmdlet to add yourself or another user as the owner of a whiteboard or use the **Invoke-TransferAllWhiteboards** cmdlet to transfer the ownership of all whiteboards for a specific user to a new owner. For information about using these cmdlets and installing the Whiteboard PowerShell module, see Microsoft Whiteboard cmdlet reference.
After you or another person has ownership of a whiteboard, see [Microsoft Whiteboard cmdlet reference](https://docs.microsoft.com/powershell/module/whiteboard/?view=whiteboard-ps).

在你或其他人获得某个白板的所有权后，请参阅 [Whiteboard 支持文章](https://go.microsoft.com/fwlink/?linkid=872780)，以获得有关访问、导出和删除白板的详细指导。

### <a name="yammer"></a>Yammer

以下各节介绍如何在 Microsoft Yammer 中使用应用内功能查找、访问、导出和删除个人数据。

#### <a name="discover"></a>发现

从 Yammer 管理中心，Yammer 验证管理员（全局管理员或在 Yammer 中设置的验证管理员）可导出给定用户的相关数据。 导出的内容包括用户发布和修改的消息和文件，以及用户所创建主题和组的相关信息。 导出用户特定的数据时，管理员还可在收件箱中收到包含用户帐户活动数据的邮件，可将这些数据提供给用户（如果这样选择）。 有关详细说明，请参阅 [Yammer Enterprise：隐私](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)。

用户特定的导出适用于单个网络，因此，如果用户位于外部 Yammer 网络中，管理员必须针对外部网络和主网络导出数据。

要访问未包含在数据导出中的数据，可对用户的个人资料、设置、组成员身份、添加为书签的消息、关注的用户以及关注的主题进行屏幕截图。 用户或管理员可以收集此信息。 有关详细信息，请参阅 [Yammer Enterprise：隐私](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)。

#### <a name="access"></a>Access

You can view data in the exported files, including the full text of messages and the contents of files. You can also click links in the exported files to go directly to the posted messages and files in Yammer, and to groups, and topics the user created, messages the user liked, messages where the user is @mentioned, polls the user has voted on, and links the user has added.

每用户数据导出不包括：

- 用户的个人资料：
    - If the user has a Yammer identity, the user has full control of their profile. For information on how to view and modify the profile, see [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851).
    
    - If the user has an Office 365 identity, the Yammer user profile is pulled automatically from Office 365, which gets the profile information from Azure Active Directory (AAD). Yammer users can temporarily change their profiles in Yammer, but these changes are overwritten when there is a change in AAD, so you must view and change directory data in AAD. See [Manage Yammer users across their lifecycle from Office 365](https://docs.microsoft.com/yammer/manage-yammer-users/manage-users-across-their-lifecycle) and [Add or change profile information for a user in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-users-profile-azure-portal).

-   用户的设置：

- The user can view and change their own settings. For information on how to view and modify user settings, see [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851). An admin can view this information and take screenshots, but can't change it. Go to Yammer settings \> **People**, and then click the name of the user.<br/>
    - 用户的组成员身份、添加为书签的消息、关注的用户和关注的主题。
    
    - The user can view this information. For information on how, see [Tips for staying organized in Yammer](https://support.office.com/article/tips-for-staying-organized-in-yammer-40ae9666-75c0-4254-a84c-d87a9542f380). An admin can view this information and take screenshots, but can't change it. Go to Yammer settings \> **People**, and then click the name of the user.

#### <a name="export"></a>导出

For instructions for how to export data, see [Manage GDPR data subject requests in Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise). You must run a per-user export for each Yammer network the user is a member of.

用户删除消息或文件时，Yammer 可设置数据保留设置（软删除或硬删除数据）。 如果设置为软删除，则用户删除的数据将包含在导出中。 如果 Yammer 数据保留设置设为硬删除，则 Yammer 中不再存储已删除的信息，因此该信息不会包含在导出中。

#### <a name="delete"></a>删除

Yammer allows verified admins to execute a GDPR-compliant delete via the Yammer admin center if they receive a DSR. This option is called Erase User, and it suspends the user for 14 days and then removes all their personal data, excluding files and messages. If the user is a guest user, this must be done for each external network the guest user is a member of.

>[!NOTE]
>If an admin wants to remove the files and messages of a user during the 14-day window, they will have to perform a user level export to identify the files and messages, and then decide which ones to delete either by in-product deletion or by using a PowerShell script. After the 14-day window, the admin can no longer associate the user with their files or messages.

When a user is deleted with the Erase User option, notification is sent to the Yammer Inbox of all network admins and verified admins. The Erase User option deletes the user's Yammer profile, but does not delete their Office 365 or Azure Active Directory profile.

有关删除用户的详细步骤，请参阅[在 Yammer Enterprise 中管理 GDPR 数据主体请求](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)。

## <a name="responding-to-dsr-rectification-requests"></a>响应 DSR 纠正请求

如果数据主体要求你纠正驻留在你的组织数据（存储在 Office 365 中）中的个人数据，你和你的组织需要确定是否可以接受该请求。 如果选择接受该请求，则纠正数据可能需要进行多种操作，如编辑、修订个人数据，或将个人数据从文档或其他类型的项目中删除。 完成此操作的最佳方法是请求数据/文档所有者使用相应的 Office 365 应用程序进行请求的更改。 也可以请求组织中的 IT 管理员户进行更改。 这可能需要 IT 管理员（或组织中具有相应特权的其他人员，如 SharePoint Online 网站集管理员）为自己或组织中处理 DSR 的其他人分配必要的权限，以便获取对文档或文档所在内容位置的访问权限，从而直接对文档进行更改。

### <a name="requesting-that-the-data-owner-to-make-the-approved-change"></a>请求数据所有者进行已批准的更改

The most direct way to rectify personal data is to ask the data owner to make the change. After you locate the data that is the subject of the DSR, you can provide the following information so that they can make the change.

- 需要更改的项目的位置和文件名（对于文档和其他文件）。 查找相关数据是发现过程中包含的内容，前文中介绍了此[发现过程](#using-content-search-to-find-personal-data)。
- 数据所有者应进行的已批准的更改

你可能需要考虑实施确认流程，由你或涉及 DSR 调查的其他人验证已进行请求的更改。

### <a name="gaining-access-to-a-sharepoint-online-site-or-onedrive-for-business-account-to-make-changes"></a>获取对 SharePoint Online 网站或 OneDrive for Business 帐户的访问权限以便进行更改

If it's not feasible for the data owner to implement the data subject's request for rectification, an IT admin or SharePoint admin in your organization can get access to the content location and make the required changes. Or, an admin can assign you or another data privacy officer the necessary permissions.

#### <a name="sharepoint-online"></a>SharePoint Online

要分配针对 SharePoint Online 网站的管理员或所有者权限以便你或其他人可以访问和编辑该文档，请参阅

- [管理网站集的管理员](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators)

- [编辑和管理 SharePoint 列表和库的权限](https://support.office.com/article/Edit-and-manage-permissions-for-a-SharePoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782)

#### <a name="onedrive-for-business"></a>OneDrive for Business

全局管理员可通过以下方式访问用户的 OneDrive for Business 帐户。

1. 使用全局管理员凭据登录 Office 365。
2. 转到“管理中心”。
3. 转到“**活动用户**”并选择某个用户。
4. 在细节窗格中展开“**OneDrive for Business 设置**”，然后单击“**访问文件**”。
5. 单击 URL，访问用户的 OneDrive for Business 帐户。

### <a name="gaining-access-to-an-exchange-online-mailbox-to-make-changes-to-data"></a>获取对 Exchange Online 邮箱的访问权限以对数据进行更改

A global admin can assign themselves the permissions necessary to open and edit (or delete) items in another user's mailbox, as if they were the mailbox owner. A global admin can also assign these permissions to another user. Specifically, the global admin needs to add the **Read and manage** permission, which is the Full Access permission in Exchange Online. For details, see:

- [向 Office 365 中的其他用户授予邮箱权限](https://docs.microsoft.com/microsoft-365/admin/add-users/give-mailbox-permissions-to-another-user)
- [访问其他人的邮箱](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081)

如果对用户邮箱实施了法定保留，或用户邮箱已分配到保留策略，则所有版本的邮箱都会保留，直到保留期限到期或从邮箱删除了保留。 这意味着如果更改了邮箱项目以响应 DSR 纠正请求，会在用户邮箱“可恢复邮件”文件夹中的一个隐藏文件夹中保留一份原始项目（进行更改前的项目）副本。

### <a name="making-changes-to-content-in-onedrive-for-business-and-sharepoint-online"></a>更改 OneDrive for Business 和 SharePoint Online 中的内容

Admins or data owners can make changes to SharePoint Online documents, lists, and pages. Keep the following things in mind when making changes to SharePoint content:

- 更新文档将保存新版本的文档，其中包含修订内容。 不会更新较早版本的文档。 这意味着作为 DSR 纠正请求主体的数据可能一直保留在较早版本的主题中。 可删除较早版本的主题，然后将其从 Office 365 中永久删除。 请参阅本指南的[删除 SharePoint Online 和 OneDrive for Business 中的文档](#deleting-documents-in-sharepoint-online-and-onedrive-for-business)部分。
- 要完成 SharePoint 文件修订，并从文件中删除数据主体的所有痕迹（包括所有版本的文件和数据主体执行的所有记录的活动），需要执行以下步骤：

    1. 将文件副本下载到本地计算机。
    2. Permanently delete the file from SharePoint Online, by deleting the file, and then deleting if from the first-stage and second-stage Recycle Bin. See the [Deleting documents in SharePoint Online and OneDrive for Business](#deleting-documents-in-sharepoint-online-and-onedrive-for-business) section in this guide.
    3. 在本地计算机上修订文档副本。
    4. 将修订后的文件上传到原始 SharePoint Online 位置。

- Data in SharePoint lists can be edited. See [Add, edit, or delete list items](https://support.microsoft.com/zh-CN/office/add-edit-or-delete-list-items-a4b31f53-f044-470e-9823-4526594bacde).

IT 管理员也可更正与文档关联某些个人属性：

User information from the SharePoint User Profile or Office 365 is often associated with OneDrive for Business and SharePoint Online documents to represent that person. For example, a user's name in a Created By or Modified By People column for a document or list item. This user information can be rectified in several ways, depending on the source:

- 在自己的本地 Active Directory 中纠正用户属性。 对于从本地 AD 同步用户属性（如用户显示名称、名字等）的客户，应在本地 AD 中纠正这些属性。 正确映射的属性将流入 Office 365，然后流入 OneDrive for Business 和 SharePoint Online。
- 在管理中心纠正用户属性。 OneDrive for Business 和 SharePoint Online 体验中可自动反映对帐户信息的更改。 有关信息，请参阅[在 Azure Active Directory 中添加或更改个人资料信息](https://go.microsoft.com/fwlink/?linkid=864809)。 对于源于 Office 365 的属性，无法在 SharePoint 端进行任何更改。
- Rectify user properties in the SharePoint user profile experience of the SharePoint admin center. In the user profiles tab of the SharePoint admin center, admins can click **Manage user profiles**, and look up any user's properties. Then they can choose to Edit the user's properties.
- Rectify user properties in a custom source. Custom SharePoint profile properties may be syncing from a custom source via Microsoft Identity Manager (MIM) or another method.

并非所有体验都会受到影响，可能会保留较早的信息。 例如，作为文档中文本的用户姓名。

### <a name="making-changes-to-content-in-power-bi"></a>更改 Power BI 中的内容

Power BI relies on the underlying source data used in its dashboards and reports to be complete and accurate, so correcting inaccurate or incomplete source data must be done there. For example, if you created a Power BI report that is connected to Dynamics 365 for Sales as the live data source, you would have to make any corrections to the data in Dynamics 365 for Sales.

After those changes are made, you can take advantage of the [scheduled data refresh](https://docs.microsoft.com/power-bi/refresh-scheduled-refresh) capabilities to update the dataset that is stored in Power BI so that the revised data is reflected in the dependent Power BI assets. To help comply with GDPR requirements, you should have policies in place to ensure that you are refreshing your data at an appropriate cadence.

### <a name="making-changes-to-content-in-yammer"></a>更改 Yammer 中的内容

For messages, a user can edit a given message to rectify any inaccuracies. They can request a list of all their messages from a Yammer verified admin, and then click a link in the file to review each message.

For files, a user can edit a given file to rectify any inaccuracies. They can request a list of all the files they posted from a Yammer verified admin, and then access the files in Yammer. Files that are exported into the Files folder can be viewed by searching for the file by number. For example, for a file named 12345678.ppx in the export, use the Search box in Yammer to search for 1235678.ppx. Or, go to <strong>https://www.yammer.com/\<network\_name\>/\#/files/\<file\_number\></strong>; for example, <strong>https://www.yammer.com/contosomkt.onmicrosoft.com/\#/files/12345678</strong>.

对于用户可通过其个人资料和设置访问的数据，用户可以进行任何必要的更改。

- 用户的个人资料：

    - If the user has a Yammer identity, the user has full control of their profile. For information on how to view and modify the profile, see [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851).
    - 如果用户拥有 Office 365 标识，则会自动从 Office 365 中拉取 Yammer 用户个人资料，获取 Azure Active Directory (AAD) 中的个人资料信息。 Yammer 用户可在 Yammer 中临时更改其个人资料，但在 AAD 中进行的更改会覆盖这些更改，因此，最好在 AAD 中查看和更改目录数据。 用户需要请求更新 AAD。 请参阅[从 Office 365 管理 Yammer 用户的整个生命周期](https://docs.microsoft.com/yammer/manage-yammer-users/manage-users-across-their-lifecycle)和[在 Azure Active Directory 中添加或更改用户的个人资料信息](https://docs.microsoft.com/azure/active-directory/active-directory-users-profile-azure-portal)。

- 用户的设置：

    - The user can change their own settings. For information on how to view and modify user settings, see [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851).
    - The user's group membership, bookmarked messages, followed users, and followed topics. The user can change this information; see [Tips for staying organized in Yammer](https://support.office.com/article/tips-for-staying-organized-in-yammer-40ae9666-75c0-4254-a84c-d87a9542f380).

## <a name="responding-to-dsr-restriction-requests"></a>响应 DSR 限制请求

可通过下面的方法限制 Office 365 中的数据处理：

- 删除 Office 365 应用程序许可证，阻止用户通过应用程序访问数据
- 阻止用户访问其 OneDrive for Business 帐户
- 关闭 Office 365 服务的数据处理
- 暂时从 SharePoint Online 和 OneDrive for Business 中删除数据，并将数据保留在本地
- 暂时限制对 SharePoint Online 网站的所有访问
- 阻止用户登录 Office 365

如果组织稍后确定限制不再适用，可通过反向执行用于实施限制的步骤来结束限制，如重新分配许可证、重新打开服务，或允许用户登录 Office 365。

### <a name="removing-the-license-for-an-office-365-application"></a>删除 Office 365 应用程序的许可证

如上文所述，默认情况下，组织的 Microsoft 365 商业版订阅中包含的所有 Office 365 应用程序的许可证都分配给所有用户。 如果需要限制对作为 DSR 主体的数据的访问，IT 管理员可以使用 Office 365 管理门户暂时关闭应用程序的用户许可证。 如果用户之后尝试使用该应用程序，他们将收到未经授权的产品通知或一条显示他们不再有权访问的消息。 有关详细信息，请参阅[在 Office 365 商业版中删除用户许可证](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)。

**注意：**

- 要限制用户访问 Yammer，必须先[强制 Yammer 用户使用 Office 365 标识](https://docs.microsoft.com/yammer/configure-your-yammer-network/enforce-office-365-identity)，然后删除用户的 Yammer 许可证。

- 对于利用 Power BI Embedded 的方案，可以限制访问嵌入了内容的独立软件供应商 (ISV) 应用程序。

### <a name="preventing-users-from-accessing-their-onedrive-for-business-account"></a>阻止用户访问其 OneDrive for Business 帐户

删除用户的 SharePoint Online 许可证不会阻止用户访问其 OneDrive for Business 帐户（如果该帐户已存在）。 必须删除用户针对其 OneDrive for Business 帐户的权限才可实现该目的。 为此，可以删除用户的 OneDrive for Business 帐户网站集所有者身份。 具体而言，必须在用户个人资料中将用户从网站集主管理员和网站集管理员组中删除。 请参阅的[在 SharePoint 管理中心管理用户个人资料](https://docs.microsoft.com/sharepoint/manage-user-profiles)的“添加和删除 OneDrive for Business 帐户的管理员”部分。

### <a name="turning-off-an-office-365-service"></a>关闭 Office 365 服务

也可通过关闭 Office 365 服务来应对限制数据处理的 DSR 请求。 这将影响整个组织中的所有用户，并阻止每位用户使用服务或访问服务中的数据。

The most expedient way to turn off a service is to use Office 365 PowerShell and remove the corresponding user license from all users in the organization. This will in effect restrict anyone from access data in that service. For detailed instructions, see [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and follow the procedures to disable Office 365 services for users from a single licensing plan.

>[!NOTE]
>For Yammer, in additional to removing the Yammer license from user accounts, you also must disable users' ability to sign in to Yammer with Yammer credentials (by enforcing the use of their Office 365 credentials when signing in). For detailed instructions, see [Turn off Yammer access for Microsoft 365 users](https://support.office.com/article/Turn-off-Yammer-access-for-Office-365-users-1f79bfad-f713-4143-aa5d-5584985ce53a).

### <a name="temporarily-removing-data-from-sharepoint-online-or-onedrive-for-business-sites"></a>暂时从 SharePoint Online 或 OneDrive for Business 网站中删除数据

Another way to restrict the processing of personal data is to temporarily remove it from Office 365 in response to a DSR. When your organization determines that the restriction no longer applies, you can import the data back into Office 365.

由于大多数 Office 文档都位于 SharePoint Online 或 OneDrive for Business 网站中，因此下文提供了从这些网站删除文档然后重新导入的高级流程。

1. Get a copy of the document that is the subject of the restriction request. You may have to request either access to the site or ask a global admin or a site collection administrator to provide you with a copy of the document.
2. 在本地位置（如文件服务器或文件共享）或 Microsoft 云中除 Office 365 租户之外的位置存储文档。
3. Permanently delete (purge) the original document from Office 365. This is a 3-step process:

    a.  Delete the original copy of the document. When you delete a document from a site, it's sent to the site Recycle Bin (also called the *first-stage Recycle Bin*).

    b.  Go to the site Recycle Bin and delete that copy of the document. When you delete a document from the site Recycle Bin, it's sent to the site collection Recycle Bin (also called the *second-stage Recycle Bin*). See [Delete a file, folder, or link from a SharePoint document library](https://support.microsoft.com/zh-CN/office/delete-a-file-folder-or-link-from-a-sharepoint-document-library-71f3c90a-0d24-4d80-8b66-f88234b79a52).

    c.  Go to the site collection Recycle Bin and delete that copy of the document, which permanently removes it from Office 365. See [Delete items from the site collection recycle bin](https://support.microsoft.com/zh-CN/office/delete-items-from-the-site-collection-recycle-bin-dd5c00c2-aef6-4458-9d04-80b185077653).

4. 限制不再适用时，可在 Office 365 中将存储在本地的文档副本重新上传到网站。

>[!IMPORTANT]
>The preceding procedure won't work if the document is located on a site that is on hold (with one of the retention or legal hold features in Office 365). In the case where a restriction request for a DSR takes precedence over a legal hold, the hold would have to be removed from the site before a document could be permanently deleted. Additionally, the document history for deleted documents is permanently removed.

### <a name="temporarily-restricting-access-to-sharepoint-online-sites"></a>暂时限制对 SharePoint Online 网站的访问

SharePoint Online 管理员可通过锁定网站集（通过在 SharePoint Online PowerShell 中使用 **Set-SPOSite -LockState** 命令）暂时阻止所有用户访问 SharePoint Online 网站集。 这可阻止用户访问网站集或网站中包含的任何内容或数据。 如果稍后确定用户可访问网站，管理员可解锁网站。 请参阅 [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite)，了解有关运行此 PowerShell cmdlet 的信息。

### <a name="preventing-a-user-from-signing-in-to-office-365"></a>阻止用户登录 Office 365

An IT admin can also prevent a user from signing into Office 365, which would prevent the user from accessing any Office 365 online service or processing any data stored in Office 365. See [Block a former employee's access to Office 365 data](https://docs.microsoft.com/microsoft-365/admin/add-users/remove-former-employee).

## <a name="part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365"></a>第 2 部分：响应与 Office 365 生成的见解相关的 DSR

Microsoft Office 365 服务套件包括多种联机服务，可为选择使用这些服务的用户和组织提供见解。

- Delve 和 MyAnalytics 为单个用户提供见解
- Workplace Analytics 为组织提供见解。

以下各节介绍了这些服务：

### <a name="delve"></a>Delve

在 Delve 中，用户可管理他们的 Office 365 个人资料，并发现可能与他们相关的人员和文档。 用户只能看到他们有权访问的文档。 有关一系列 Delve 相关实用文章，请参阅 [Office Delve](https://support.office.com/article/What-is-Office-Delve-1315665a-c6af-4409-a28d-49f8916878ca)。

#### <a name="access-and-export"></a>访问和导出

Admins can't access or export a users' Delve data. This means that users have to access and export Delve data themselves. Most of the data types can be accessed and exported directly from Delve, but some data types are only available through other services.

##### <a name="data-available-in-the-delve-user-interface"></a>Delve 用户界面中提供的数据

- **个人资料数据：** 这是 Azure Active Directory 中组织的全局地址列表中的个人资料信息，以及用户选择添加的与自己相关的可选信息。 若要在 Delve 中访问或导出个人资料数据，用户可单击“**我**”\>“**更新个人资料**”。 他们可以直接从页面中复制内容或
- **博客数据：** 这是用户发布的博客文章。 若要访问或导出博客数据，用户可以单击“**我**”\>“**所有文章**”。 他们可以直接从页面中复制内容或获取屏幕截图。
- **最近的人员数据：** 这些是 Delve 在给定时间推断为与用户最相关的组织中的人员。 当用户在“单击某个人以查看他们正在处理的内容”窗格中单击“**我**”\>“**全部查看**”时，Delve 将显示在给定时间与用户最相关的人员。

##### <a name="data-available-through-an-export-link-in-delve"></a>通过 Delve 中的导出链接提供的数据

- **人员列表数据：** 这些是用户已在 Delve 中查看的人员。 “**人员**”列表显示在主页上的左侧窗格中。 用户可以导出他们最近在 Delve 中查看的人员的列表。
- **收藏夹数据：** 这些是用户已标记为其收藏夹的版块和文档。 “**收藏夹**”页面显示用户已添加到其收藏夹的版块和文档。 用户可以将导出其当前收藏夹版块和文档的列表。
- **功能设置数据：** 这些是用户使用 Delve 时生成的 Delve 配置或操作。 用户可以导出这些设置的完整列表。

To access or export the above data, the user can click the gear icon in the upper-right corner in Delve, and then click **Feature settings** > **Export data**. Information is exported in JSON format.

##### <a name="data-thats-available-through-other-services"></a>通过其他服务提供的数据

- **热门文档数据：** 这些是可能与用户相关的文档和电子邮件附件。 Delve 会基于用户的活动以及他们在 Office 365 中协同工作的人员动态组织其文档和电子邮件。 当用户打开 Delve 或单击“**主页**”时，Delve 会显示在给定时间与用户最相关的文档或附件。 若要访问或导出实际文档和附件，用户可以转到通过其提供了文档的 Office 365 服务（例如 Office.com、SharePoint Online、OneDrive for Business 或 Exchange Online）。
- **最近的文档和电子邮件附件数据：** 这些是用户最近修改过的文档和电子邮件附件。 当用户在“返回最近的文档和电子邮件附件”窗格中单击“**我**”\>“**全部查看**” 时，Delve 会显示用户在给定时间修改的最新文档和电子邮件附件。 若要访问或导出实际文档和附件，用户可以转到通过其提供了文档或附件的 Office 365 服务；例如，Office.com、SharePoint Online、OneDrive for Business 或 Exchange Online。
- **来自你周围的人员的文档数据：** 这些是 Delve 在给定时间推断为与用户最相关的文档。 当用户在“发现来自你周围的人员的文档”窗格中单击“**我**”\>“**全部查看**”时，Delve 会显示在给定时间与用户最相关的文档。 若要访问或导出实际文档，用户可以转到通过其提供了文档或附件的 Office 365 服务；例如，Office.com、SharePoint Online、OneDrive for Business 或 Exchange Online。

#### <a name="rectify"></a>纠正

用户可以修改 Delve 中的以下信息：

- **个人资料信息：** 用户可以单击“**我**”\>“**更新个人资料**”来更新其信息。 根据全局地址列表中组织的设置，用户可能无法修改其所有个人资料信息，例如其姓名或职称。
- **功能设置：** 用户可以单击 Delve 中右上角的齿轮图标，然后单击“**功能设置**”\>来更改所需的设置。

#### <a name="restrict"></a>限制

To restrict processing in Delve for your organization, you can turn off the Office Graph. Learn more [here](https://docs.microsoft.com/sharepoint/delve-for-office-365-admins).

#### <a name="delete"></a>删除

用户可删除 Delve 中的以下信息：

- **个人资料信息：** 若要删除个人资料信息，用户可以单击“**我**”\>“**更新个人资料**”，并删除自由格式文本。 根据全局地址列表中组织的设置，用户可能无法修改其所有个人资料信息，例如其姓名或职称。
- **文档和电子邮件附件：** 若要删除文档或附件，用户必须存储文档或附件的服务（例如 SharePoint Online、OneDrive for Business 或 Exchange Online），并在该处删除文档。

### <a name="myanalytics"></a>MyAnalytics

MyAnalytics provides statistics to users to help them understand how they spend their time at work. To help your users better understand the data that is presented to them in their personal dashboard and how that data is calculated, direct your users to the [MyAnalytics personal dashboard](https://docs.microsoft.com/workplace-analytics/myanalytics/use/dashboard-2) help topic.

#### <a name="access-and-export"></a>访问和导出

如果组织使用 MyAnalytics，Microsoft 将会生成面向所有用户的见解。 所有 MyAnalytics 见解均派生自用户邮箱中的电子邮件和会议标头。 用户可以转到 [MyAnalytics 仪表板](https://delve.office.com)，同时登录其 Office 365 帐户，查看生成的有关如何安排工作时间的见解。 如果用户想要保存其信息的永久副本，还可对看到的内容进行屏幕截图。

#### <a name="rectify"></a>纠正

All insights generated by MyAnalytics are derived from the user's mail and calendar items. Therefore, there is nothing to rectify other than the source email or calendar items.

#### <a name="restrict"></a>限制

To restrict processing for a specific user, you can opt them out of MyAnalytics. To see how, see [Configure MyAnalytics user settings](https://docs.microsoft.com/workplace-analytics/myanalytics/setup/configure-myanalytics).

#### <a name="delete"></a>删除

All mailbox content, including MyAnalytics data, is purged when a user account is "hard-deleted" from Active Directory. For more information, see the [Deleting a user](#deleting-a-user) section in this guide.

### <a name="workplace-analytics"></a>工作区分析

Workplace Analytics allows organizations to augment Office 365 data with their own business data to gain insights about organizational productivity, collaboration patterns, and employee engagement. [This article](https://docs.microsoft.com/workplace-analytics/index-orig) explains the control that your organization has over the data that Workplace Analytics processes and who has access to that data.

在工作区分析中提供 DSR 方面的协助： 

1. Determine whether your organization is using Workplace Analytics. For more information, see [Assign licenses to users](../admin/manage/assign-licenses-to-users.md). If your organization is not using Workplace Analytics, there is no further action.

2. 如果组织在使用 Workplace Analytics，则查看组织中具有 Workplace Analytics 管理员角色的人员。 此外，还应确定数据主体的邮箱是否已获得 Workplace Analytics 许可。 如有必要，请求 Workplace Analytics 管理员联系 Microsoft 支持部门处理以下 DSR 请求： 

#### <a name="access-and-export"></a>访问和导出

由你创建的 Workplace Analytics 见解报表可能包含也可能不含组织中已获得 Workplace Analytics 许可的用户的个人数据，具体取决于组织用于补充 Office 365 数据的信息。 Workplace Analytics 管理员需要审阅这些报表，确定其是否包含用户的个人数据。 如果报表包含用户的个人数据，则需要确定是否要向用户提供该报表的副本。 Workplace Analytics 允许你导出报表。 

#### <a name="rectify"></a>纠正

如上文所述，Workplace Analytics 结合使用 Office 365 数据以及你提供的组织数据（用于生成你感兴趣的报表）。 无法纠正 Office 365 数据，该数据基于用户的电子邮件和日历活动。 但是，可将你拥有的组织数据上传到 Workplace Analytics，生成可纠正的报表。 要执行此操作，需要更正并上传源数据，并返回报表以生成新的 Workplace Analytics 报表。

#### <a name="restrict"></a>限制

要限制特定用户的处理，可以删除其 工作区分析许可证。

#### <a name="delete"></a>删除

If a data subject would like to be removed from a Workplace Analytics report or set of reports, you can delete the report. It is your responsibility to delete users from any organizational data that you used to generate the report, and reupload the data. All data about the user is removed when a user account is "hard-deleted" from Azure Active Directory. 

全局管理员可以采取以下步骤来删除数据主体的个人数据： 

1. 删除数据主体的工作区分析许可证。
2. Delete the Azure Active Directory (AAD) entry for the data subject. (For more information, see [Delete a user](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user).)
3. Contact support and have support open a ticket for a Data Subject Rights (DSR) user-delete request. In this ticket, identify the data subject by using their User Principal Name (UPN).
4. 从公司的 HR 系统导出 HR 数据副本（请参阅[导出数据](https://docs.microsoft.com/workplace-analytics/setup/prepare-organizational-data)），从该 HR 数据文件删除数据主体的信息，然后将编辑后的 HR 数据文件以 .csv 格式上传到工作区分析（请参阅[上传组织数据](https://docs.microsoft.com/workplace-analytics/setup/upload-organizational-data)）。

## <a name="part-3-responding-to-dsrs-for-system-generated-logs"></a>第 3 部分：响应对系统生成日志的 DSR

Microsoft also provides you with the ability to access, export, and delete system-generated logs that may be deemed personal under the GDPR's broad definition of "personal data." Examples of system-generated logs that may be deemed personal under GDPR include:

- 产品和服务使用情况数据，例如用户活动日志
- 用户搜索请求和查询数据
- 作为系统功能一部分的产品和服务所生成的数据以及用户或其他系统的交互

不支持限制或纠正系统生成日志中的数据。 系统生成日志中的数据构成 Microsoft 云内执行的实际操作和诊断数据，对此类数据的修改将会损坏操作的历史记录，增加诈骗及安全风险。

### <a name="accessing-and-exporting-system-generated-logs"></a>访问和导出系统生成日志

租户管理员是组织内唯一可以访问与特定用户的 Office 365 服务和应用使用情况相关联的系统生成日志的人员。 为导出请求检索到的数据将以机器可读格式提供，并在允许用户知道数据与哪些服务关联的文件中提供。 如上所述，检索到的数据不包括可能会危及服务安全性或稳定性的数据。

访问和导出系统生成的日志：

1. 登录到 Azure 门户，然后选择“**所有服务**。
2. 在筛选器中键入“策略”，然后选择“**策略**”。
3. 在“**策略**”边栏选项卡中，依次选择“**用户策略**”、“**管理用户请求**”和“**添加导出请求**”。
4. 完成“**导出数据请求**”：

    - **用户**。 键入请求导出的 Azure Active Directory 用户的电子邮件地址。
    - **订阅**。 选择用于报告资源使用情况并计算服务费用的帐户。 这也是您的 Azure 存储帐户位置。
    - **存储帐户**。 选择 Azure 存储的位置 (Blob)。 有关详细信息，请参阅 “Microsoft Azure 存储简介 — Blob 存储”一文。
    - **容器**。 创建新的（或选择现有的）容器作为存放用户导出的隐私数据的存储位置。

5. 选择“创建”****。

导出请求进入**挂起**状态。 你可以在“**用户隐私**” > “**概述**”边栏选项卡上查看报告状态。

>[!IMPORTANT]
>由于个人数据可能来自多个系统，因此导出过程可能需要一个月才能完成。

### <a name="notify-about-exporting-or-deleting-issues"></a>通知导出或删除问题

如果在从 Azure 门户导出或删除数据时遇到问题，请转到 Azure 门户“**帮助 + 支持**”边栏选项卡，并在“**订阅管理**” > “**其他安全与合规请求**” > “**隐私边栏选项卡和 GDPR 请求**”下提交新票证。

>[!NOTE]
 >从 Azure 门户导出数据时，将不会导出某些应用程序的系统生成的数据。 若要导出这些应用程序的数据，请参阅[导出系统生成的日志数据所需的其他步骤](https://docs.microsoft.com/microsoft-365/compliance/gdpr-system-generated-log-data)。

下面概述了如何访问和导出系统生成日志：

- **使用 Azure 门户执行的导出请求需要多长时间才能完成请求？**：这取决于若干因素。 通常，一到两天内可以完成，但最多可能需要 30 天。
- **输出内容采用什么格式？**：输出内容是结构化的计算机可读文件（如 XML、CSV 或 JSON）。
- **谁有权访问 Azure 门户以提交对系统所生成数据的访问请求？**：Office 365 全局管理员有权访问 Azure 门户。
- **导出结果将返回哪些数据？**：结果中包含 Microsoft 所存储的系统生成的日志。 导出的数据将跨越各种 Microsoft 服务，包括 Office 365、Azure 和 Dynamics。 结果不包括可能会危及服务安全性或稳定性的数据。
- **如何向用户返回数据？**：数据将导出到你组织的 Azure 存储位置；由你组织的管理员来确定他们如何向用户显示/返回此数据。
- **系统生成的日志数据的样式是怎样的？**：下面是 JSON 格式的数据的示例：

    ```JSON
    [{
    "DateTime": "2017-04-28T12:09:29-07:00",
    "AppName": "SharePoint",
    "Action": "OpenFile",
    "IP": "154.192.13.131",
    "DevicePlatform": "Windows 1.0.1607"
    }]
    ```

还可通过在安全与合规中心搜索 Office 365 审核日志来检索一些最常用的 Microsoft 服务（如 Exchange Online、SharePoint Online、Skype for Business、Yammer 和 Office 365 组）的产品和服务使用情况。 有关详细信息，请参阅附录 A 中的[在 DSR 调查中使用 Office 365 审核日志搜索工具](#use-the-audit-log-search-tool-in-dsr-investigations)。你可能会对使用审核日志感兴趣，因为无法向组织中的其他人（例如合规部主管）分配搜索审核日志并访问此数据的权限。

### <a name="deleting-system-generated-logs"></a>删除系统生成日志

To delete system-generated logs retrieved through an access request, you must remove the user from the service and permanently delete their Azure Active Directory account. For instructions about permanently delete a user, see the [Deleting a user section](#deleting-a-user) in this guide. It's important to note that permanently deleting a user account is irreversible once initiated.

永久删除用户帐户将在 30 天内从几乎所有 Office 365 服务的系统生成日志中删除用户数据（不包括可能会危及服务安全性和稳定性的数据）。 

此 30 天期限一个例外情况是在 Exchange Online 中永久删除用户帐户所用的时间超过 30 天。 这是由于 Exchange Online 内容的关键性质，以防止数据意外丢失。 Exchange Online 设计为有意地在永久删除用户帐户后将数据置于保留状态最多 60 天。 要在 30 天的时间范围内永久删除用户 Exchange Online 数据，请在永久删除 Azure Active Directory 中的用户帐户后联系 [Microsoft 支持人员](https://support.microsoft.com/)，请求在计划删除流程之外手动删除用户的 Exchange Online 数据。 有关详细信息，请参阅本指南前文所述的[删除 Exchange Online 数据](#removing-exchange-online-data)

Deleting a user's account will not remove system-generated logs for Yammer and Kaizala. To remove the data from these applications, see one of the following:

- Yammer - [在 Yammer Enterprise 中管理 GDPR 数据主体请求](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- Kaizala - [导出或删除 Kaizala 中的用户组织数据](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

#### <a name="national-clouds"></a>国家云

全局 IT 管理员需要执行以下操作以导出以下国家云中的系统生成日志数据：

- **Office 365 德国版**：按照上面的步骤操作。
- **Office 365 美国政府版**：[转到 Office 365 管理门户](https://portal.office365.us)，然后向 Microsoft 支持部门提交请求。
- **由世纪互联运营的 Office 365（中国版）**：[转到由世纪互联运营的 Office 365 的管理门户](https://portal.partner.microsoftonline.cn/AdminPortal/Home#/homepage)，然后转到“**商务**“ > “**订阅**” > “**隐私**” > “**GDPR**”并输入所需的信息。

## <a name="part-4-additional-resources-to-assist-you-with-dsrs"></a>第 4 部分：可提供 DSR 协助的其他资源

### <a name="dsr-guides-for-other-microsoft-enterprise-services"></a>其他 Microsoft 企业服务的 DSR 指南

本指南专用于有关如何使用 Office 365 产品、服务和管理工具查找和处理个人数据以响应 DSR 的主题。 转到 [Microsoft 服务信任门户](https://servicetrust.microsoft.com/)，访问针对其他 Microsoft 企业服务的类似指南。

### <a name="microsoft-support"></a>Microsoft 支持

"Support Data" is the data you and your users provide to Microsoft if your organization or your users engage with Microsoft to receive product support related to Office 365 or other Microsoft products and services (for example, to troubleshoot unexpected product behavior). Some of this data may contain personal data. For more information, see [Microsoft Support and Professional Services Data Subject Requests for the GDPR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-prof-services).

### <a name="product-and-services-authenticated-with-an-org-id-for-which-microsoft-is-a-data-controller"></a>通过组织 ID 进行身份验证且由 Microsoft 作为数据控制者的产品和服务

本指南的第 1 部分至第 3 部分介绍了由 Microsoft 充当组织的数据处理者，因而租户管理员可使用 DSR 功能的产品和服务。 在许多情况下，组织中的用户可能会使用其工作或学校帐户（也称为“Azure Active Directory ID”或“AAD”）登录由 Microsoft 充当数据控制者的 Microsoft 产品和服务。 对于所有此类产品和服务，用户需要直接向 Microsoft 发出自己的数据主体请求，而 Microsoft 将直接针对该用户满足请求。 涉及存储用户创作内容的产品和服务经过精心设计，使用户能够使用产品的固有功能访问、导出、纠正和删除其用户创作内容。 相关情景包括：

- **可选的已连接联机服务：** Microsoft 365 企业应用版为用户提供了一些可选的已连接联机服务。 [此处](https://support.office.com/article/microsoft-s-other-connected-services-92c234f1-dc91-4dc1-925d-6c90fc3816d8)列出了服务和相关用户控件。 是否允许最终用户使用这些服务取决于你自己。 有关详细信息，请参阅[管理员如何管理 Microsoft 365 企业应用版中的控制者服务](https://docs.microsoft.com/DeployOffice/manage-controller-services-office-365-proplus)。 如果这些可选服务处理个人数据，Microsoft 是这些服务的数据控制者。
- **用户反馈：** 如果用户选择提供有关 Microsoft 产品和服务的反馈，且此类反馈包含个人数据，则由 Microsoft 作为该反馈的数据控制者。 Microsoft 针对 Microsoft 收集的反馈（包括由 Microsoft 子处理商管理的反馈）实现任何数据主体请求，Microsoft 已指示用户不要在反馈收集过程中包括个人数据时例外。 例外：如果 Microsoft 已指示用户不要在反馈收集过程中包括个人数据，Microsoft 将依赖该指示并假定未提供任何个人数据。 已创建第三方反馈服务提供程序独立帐户的用户需要直接通过这些服务程序实现其 DSR。
- **经过工作或学校帐户身份验证的 Windows：** 如果组织已购买 Windows 许可证，而组织中的用户已使用其工作或学校帐户针对组织提供的 Windows 进行了身份验证，则由 Microsoft 作为数据控制者。
- **用户获取的产品或服务：** 如果你允许以个人身份行事的用户获取使用 AAD 进行身份验证的 Microsoft 产品或服务（例如，Microsoft Store 中提供的 Office 加载项或应用程序），Microsoft 可能是数据控制者。 对于任何此类 Microsoft 产品或服务，用户必须直接联系 Microsoft，才能发出 DSR。

>[!IMPORTANT]
>If you delete a user as enabled via Azure Active Directory, your (former) user will lose the ability to sign in to any products or services for which he or she formerly relied upon for a work or school account. Additionally, Microsoft will no longer be able to authenticate the user in connection with a DSR request for products or services for which Microsoft is a data controller. If you wish to enable a user to initiate DSRs against such services, it is important you instruct your user to do so before you delete the user's AAD account.

### <a name="personal-accounts"></a>个人帐户

如果用户曾使用 Microsoft 帐户（即个人帐户）从 Microsoft 获取由 Microsoft 作为数据控制者的产品和服务并自行使用，则他们将可通过 [Microsoft 隐私仪表板](https://account.microsoft.com/account/privacy)发出 DSR 请求。

### <a name="third-party-products"></a>第三方产品

如果组织或以个人身份行事的用户已从第三方获取了产品或服务，并使用其 Microsoft 工作或学校帐户进行身份验证，则任何数据主体请求都应转到合适的第三方。

## <a name="appendix-a-preparing-for-dsr-investigations"></a>附录 A：准备 DSR 调查

为了使用 Office 365 服务帮助组织准备执行 DSR 调查，请考虑以下建议：

- 在安全与合规中心使用 DSR 电子数据展示事例工具管理 DSR 调查
- 设置合规性边界，以限制内容搜索范围
- 在 DSR 调查中使用审核日志搜索工具

### <a name="use-the-dsr-case-tool-to-manage-dsr-investigations"></a>使用 DSR 事例工具管理 DSR 调查

We recommend that you use the DSR case tool in Security & Compliance Center to manage DSR investigations. By using the DSR case tool, you can:

- 为每个 DSR 调查创建单独的事例。

- 使用内置搜索查询搜索与特定数据主体相关的所有内容。 创建新事例并开始搜索时，可搜索以下内容位置：

   - 组织中的所有邮箱（包括与所有 Microsoft Teams 和 Microsoft 365 组相关联的邮箱）
   - 组织中的所有 SharePoint Online 网站和 OneDrive for Business 帐户
   - 组织中的所有 Microsoft Teams 网站和 Microsoft 365 组网站
   - Exchange Online 中的所有公用文件夹

- 修改默认搜索查询并重新运行搜索，以缩小搜索结果的范围。

- 通过将人员添加为事例成员，控制有权访问事例的人员；只有成员才能访问事例，并在安全与合规中心的“DSR 事例”页面上查看其在事例列表中的事例。 此外，可为同一事例的不同成员分配不同的权限。 例如，可以只允许一些成员查看事例和内容搜索结果，而允许其他成员创建搜索和导出搜索结果。

- 创建导出作业，导出响应 DSR 导出请求的搜索结果。 可以导出内容搜索返回的所有内容。 还会导出与数据主体相关的其他 Office 365 数据。

- 创建导出作业，导出响应 DSR 导出请求的搜索结果。 可以导出内容搜索返回的所有内容。 还可以导出 Office 漫游服务的系统生成日志。

- 在 DSR 调查过程完成时删除案件集。 这会删除所有内容搜索，并导出与案件集关联的作业。

若要开始使用 DSR 案件集，请参阅[在安全与合规中心内使用 DSR 案件集工具管理 GDPR 数据主体请求](https://docs.microsoft.com/microsoft-365/compliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool)。

>[!IMPORTANT]
>An eDiscovery Administrator can view and manage all DSR cases in your organization. For more information about the different roles related to eDiscovery, see [Assign eDiscovery permissions to potential case members](https://docs.microsoft.com/Office365/SecurityCompliance/assign-ediscovery-permissions).

### <a name="set-up-compliance-boundaries-to-limit-the-scope-of-content-searches"></a>设置合规性边界，以限制内容搜索范围

Compliance Boundaries are implemented by using the search permissions filtering functionality in the Security & Compliance Center. Compliance Boundaries create logical search boundaries within an organization that control/limit which content locations (for example Exchange Online mailboxes and SharePoint Online sites) that an IT admin or compliance officer can search. Compliance Boundaries are useful for multi-national organizations that need to respect geographical boundaries, governmental organizations that need to separate different agencies, and business organizations that segregated into business unit or department. For all these scenarios, Compliance Boundaries can be used in DSR investigations to limit which mailboxes and sites can be searched by people involved in the investigation.

可结合使用合规性边界和电子数据展示事例，将可在调查中搜索的内容位置限制为机构或业务部门内的内容位置。

下面概括介绍了如何针对 DSR 调查实现合规性边界（结合使用电子数据展示事例）。

1. 确定组织中将指定为合规性边界的机构。

2. Determine which user object attribute in Azure Active Directory will be used to define the compliance boundary. For example, you might choose the Country, CountryCode, or Department attribute, so that members of the admin role group that you create in the next step can only search the content locations of the users that have a specific value for that attribute. This is how you limit who can search for content in a specific agency.

>[!NOTE]
>目前，对于 OneDrive for Business，必须执行额外的步骤，并请求 Microsoft 支持部门将属性同步到 OneDrive for Business 帐户。

4. Create an admin role group in the Security & Compliance Center for each compliance boundary. We recommend that you create these role groups by copying the built-in eDiscovery Manager role group and then removing any roles as necessary.

5. 以电子数据展示管理者的身份向每个特定角色组添加成员。 成员是负责调查和响应 DSR 人员，通常包括 IT 管理员、数据隐私部主管、合规性管理员和人力资源代表。

6. 为每个合规性边界创建搜索权限筛选器，以便对应管理员角色组中的成员可仅搜索机构/合规性边界内的用户的邮箱和网站。 使用搜索权限筛选器，对应角色组的成员可仅搜索对应于机构/合规性边界的具有用户对象属性值的内容位置。

有关分步说明，请参阅[在 Office 365 中为电子数据展示调查设置合规性边界](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries)。

### <a name="use-the-audit-log-search-tool-in-dsr-investigations"></a>在 DSR 调查中使用审核日志搜索工具

IT admins can use the audit log search tool in the Security & Compliance Center to identity documents, files, and other Office 365 resources that users have created, accessed, changed, or deleted. Searching for this kind activity can be useful in DSR investigations. For example, in SharePoint Online and OneDrive for Business, auditing events are logged when users perform these activities:

- 访问文件
- 修改文件
- 移动文件
- 上传或下载文件

可以针对特定活动、活动类型、特定用户执行的活动和其他搜索条件搜索审核日志。 除了 SharePoint Online 和 OneDrive for Business 活动外，还可搜索 Flow、Power BI 和 Microsoft Teams 中的活动。 审核记录可保留 90 天。 因此，无法立即搜索超过 90 天前发生的用户活动。 有关审核活动的完整列表以及搜索审核日志的方法，请参阅[在安全与合规中心搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。

>[!TIP]
>要避开上文讨论的 90 天的限制，并保留组织审核记录的运行历史记录，可以定期（例如每 30 天）导出所有活动，从而获得组织审核记录的连续记录。

## <a name="appendix-b-change-log"></a>附录 B：更改日志

下表列出了 Office 365 DSR 指南自 2018 年 5 月 25 日首次发布以来的更改。

|日期  |部分/应用 |更改  |
|:---------|:---------|:---------|
|9/18/2018 | [Whiteboard](#whiteboard) |Whiteboard Preview is no longer in preview and has been released to general availability. Therefore, the section on Whiteboard Preview was renamed to "Whiteboard for PC, Surface Hub, and other platforms"; procedures to access, export, and delete data were removed from this section and replaced with a link to the Whiteboard support article.|
|11/08/2018 | [工作区分析](#workplace-analytics) |向“删除”部分添加了关于从工作区分析删除数据主体以及从工作区分析报表删除数据主体相关信息的分步指南。|
|11/12/2018| 全部| 修复了受损坏的书签和指向外部主题的链接。|
|2019 年 1 月 9 日| StaffHub |在“删除”部分，更新了永久删除用户帐户时所发生情况的描述。|
|2019 年 5 月 8 日| [Publisher](#publisher)|添加了有关为 Publisher 响应 DSR 的内容。|
|2019 年 7 月 11 日| [MyAnalytics](#myanalytics)|管理员无法再使用安全与合规中心内的 DSR 事例工具导出 MyAnalytics 数据，因为所有用户现都可在 MyAnalytics 应用中查看自己的数据。 |
|2019/11/6|[教育版](#education)|链接到有关使用 PowerShell 脚本的新主题以获取特定学生的课程列表，然后导出或删除其数据。|
|2020 年 1 月 28 日| 全部 | 已从文档中删除 StaffHub，StaffHub 已停用。 |
||||
