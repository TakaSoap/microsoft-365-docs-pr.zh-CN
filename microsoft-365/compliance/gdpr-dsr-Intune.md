---
title: 针对 GDPR 的 Intune 数据主体请求
description: ''
keywords: Microsoft 365, Microsoft 365 教育版, Microsoft 365 文档, GDPR
author: dougeby
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: dougeby
manager: angrobe
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: fa65d33795108a16759fa87d476bb5a4dc94a281
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285194"
---
# <a name="intune-data-subject-requests-for-the-gdpr"></a><span data-ttu-id="3d647-103">针对 GDPR 的 Intune 数据主体请求</span><span class="sxs-lookup"><span data-stu-id="3d647-103">Intune Data Subject Requests for the GDPR</span></span>
<span data-ttu-id="3d647-p101">根据 EU 数据保护条例 (GDPR)，用户（在条例中称为“*数据主体*”）有权管理由雇主或其他类型机构或组织（称为“*数据控制者*”或简称为“*控制者*”）收集的个人数据。根据 GDPR，个人数据的定义非常广泛，包括与身份已识别或可识别的自然人相关的任何数据。根据 GDPR，数据主体有权对自己的个人数据执行以下操作：获取个人数据副本、请求更正个人数据、限制个人数据处理、删除个人数据或接收电子格式的个人数据（以便于转移给其他控制者）。数据主体为了对自己的个人数据执行操作而向控制者发出的正式请求，称为“*数据主体请求*”或“DSR”。</span><span class="sxs-lookup"><span data-stu-id="3d647-p101">The EU Data Protection Regulation (GDPR) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request* or DSR.</span></span>

<span data-ttu-id="3d647-p102">本指南讨论了如何使用 Microsoft 产品、服务和管理工具帮助我们的控制者客户查找和操作个人数据以响应 DSR。具体而言，这包括如何查找、访问和操作驻留在 Microsoft 云中的个人数据。下面是本指南中所列流程的快速概述：</span><span class="sxs-lookup"><span data-stu-id="3d647-p102">The guide discusses how to use Microsoft products, services, and administrative tools to help our controller customers find and act on personal data to respond to DSRs. Specifically, this includes how to find, access, and act on personal data that reside in the Microsoft cloud. Here’s a quick overview of the processes outlined in this guide:</span></span>

1.  <span data-ttu-id="3d647-p103">***发现*** - 使用搜索和发现工具更轻松地查找可能是 DSR 主体的客户数据。一旦收集了潜在响应文档，则可以执行一个或多个下列步骤中所述的 DSR 操作。或者，你可能会确定请求不符合组织有关响应 DSR 的指导原则。</span><span class="sxs-lookup"><span data-stu-id="3d647-p103">***Discover***—Use search and discovery tools to more easily find customer data that may be the subject of a DSR. Once potentially responsive documents are collected, you can perform one or more of the DSR actions described in the following steps to respond to the request. Alternatively, you may determine that the request doesn't meet your organization’s guidelines for responding to DSRs.</span></span>

2.  <span data-ttu-id="3d647-114">***访问*** - 检索驻留在 Microsoft 云中的个人数据，如果提出请求，还制作可供数据主体使用的个人数据副本。</span><span class="sxs-lookup"><span data-stu-id="3d647-114">***Access***—Retrieve personal data that resides in the Microsoft cloud and, if requested, make a copy of it that can be available to the data subject.</span></span>

3.  <span data-ttu-id="3d647-115">***纠正*** - 进行更改或者对个人数据实施其他请求的操作（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="3d647-115">***Rectify***—Make changes or implement other requested actions on the personal data, where applicable.</span></span>

4.  <span data-ttu-id="3d647-p104">***限制*** - 通过移除各种 Azure 服务的许可证或者在可能的情况下关闭所需服务，限制个人数据的处理。你也可以从 Microsoft 云中移除数据并仍将其保留在內部或其他位置。</span><span class="sxs-lookup"><span data-stu-id="3d647-p104">***Restrict***—Restrict the processing of personal data, either by removing licenses for various Azure services or turning off the desired services where possible. You can also remove data from the Microsoft cloud and retain it on-premises or at another location.</span></span>

5.  <span data-ttu-id="3d647-118">***删除*** - 永久删除驻留在 Microsoft 云中的个人数据。</span><span class="sxs-lookup"><span data-stu-id="3d647-118">***Delete***—Permanently remove personal data that resided in the Microsoft cloud.</span></span>

6.  <span data-ttu-id="3d647-119">***导出*** - 向数据主体提供个人数据的电子副本（采用机器可读格式）。</span><span class="sxs-lookup"><span data-stu-id="3d647-119">***Export***—Provide an electronic copy (in a machine-readable format) of personal data to the data subject.</span></span>

<span data-ttu-id="3d647-120">本指南中的每个部分概述了数据控制者组织为响应对 Microsoft 云中个人数据的 DSR 而采取的技术过程。</span><span class="sxs-lookup"><span data-stu-id="3d647-120">Each section in this guide outlines the technical procedures that a data controller organization can take to respond to a DSR for personal data in the Microsoft cloud.</span></span>

<span id="_Toc511384801" class="anchor"><span id="_Toc511163872" class="anchor"><span id="_Toc511136229" class="anchor"><span id="_Toc511125162" class="anchor"><span id="_Toc511120749" class="anchor"><span id="_Toc511122656" class="anchor"><span id="_Toc508792503" class="anchor"></span></span></span></span></span></span></span>
#### <a name="terminology"></a><span data-ttu-id="3d647-121">术语</span><span class="sxs-lookup"><span data-stu-id="3d647-121">Terminology</span></span>

<span data-ttu-id="3d647-122">下面提供了与本指南相关的术语定义。</span><span class="sxs-lookup"><span data-stu-id="3d647-122">The following provides definitions of terms that are relevant to this guide.</span></span>

-   <span data-ttu-id="3d647-123">*控制者* - 单独或与其他人一起确定个人数据处理的用途和途径的自然人或法人、公共机构、机关或其他实体；如果欧盟或成员国法律确定了此类处理的用途和途径，欧盟或成员国法律可能会规定控制者或具体提名条件。</span><span class="sxs-lookup"><span data-stu-id="3d647-123">*Controller*—The natural or legal person, public authority, agency or other body which, alone or jointly with others, determines the purposes and means of the processing of personal data; where the purposes and means of such processing are determined by Union or Member State law, the controller or the specific criteria for its nomination may be provided for by Union or Member State law.</span></span>

-   <span data-ttu-id="3d647-124">*个人数据*和*数据主体* - 身份已识别或可识别的自然人（“数据主体”）的任何相关信息；身份可识别的自然人是指可被直接或间接识别的自然人，尤其是通过参考姓名、证件号码、位置数据、联机标识等标识，或通过参考特定于该自然人的身体、生理、基因、精神、经济、文化或社会标识的一个或多个因素进行识别。</span><span class="sxs-lookup"><span data-stu-id="3d647-124">*Personal data* and *data subject*—Any information relating to an identified or identifiable natural person (‘data subject’); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural or social identity of that natural person.</span></span>

-   <span data-ttu-id="3d647-125">*处理者* - 代表控制者处理个人数据的自然人或法人、公共机构、机关或其他主体。</span><span class="sxs-lookup"><span data-stu-id="3d647-125">*Processor*—A natural or legal person, public authority, agency or other body which processes personal data on behalf of the controller.</span></span>

-   <span data-ttu-id="3d647-p105">*客户数据* - 客户或代表客户通过使用企业服务提供给 Microsoft 的所有数据，包括所有文字、声音、视频或图像文件以及软件。客户数据包括 (1) 最终用户的身份信息（例如，Azure Active Directory 中的用户名和联系人信息）和客户上传到特定服务或者在特定服务中创建的客户内容（例如，Azure 存储帐户中的客户内容，Azure SQL 数据库的客户内容，或 Azure 虚拟机中的客户虚拟机映像）。</span><span class="sxs-lookup"><span data-stu-id="3d647-p105">*Customer Data*—All data, including all text, sound, video, or image files, and software, that are provided to Microsoft by, or on behalf of, a customer through use of the enterprise service. Customer Data includes both (1) identifiable information of end users (e.g., user names and contact information in Azure Active Directory) and Customer Content that a customer uploads into or creates in specific services (e.g., customer content in an Azure Storage account, customer content of an Azure SQL Database, or a customer’s virtual machine image in Azure Virtual Machines).</span></span>

-   <span data-ttu-id="3d647-p106">*系统生成日志* - Microsoft 生成的日志和相关数据，可帮助 Microsoft 向用户提供企业服务。系统生成日志主要包括化名数据，例如唯一标识符，这通常是系统生成的无法单独识别个人但用于向用户提供企业服务的一个数字。系统生成日志还可能包含有关最终用户的身份信息，例如用户名。</span><span class="sxs-lookup"><span data-stu-id="3d647-p106">*System-Generated Logs*—Logs and related data generated by Microsoft that help Microsoft provide enterprise services to users. System-generated logs contain primarily pseudonymized data, such as unique identifiers – typically a number generated by the system that cannot on its own identify an individual person but is used to deliver the enterprise services to users. System-generated logs may also contain identifiable information about end users, such as a user name.</span></span>  

<span id="_Toc511384802" class="anchor"><span id="_Toc511163873" class="anchor"><span id="_Toc511136230" class="anchor"><span id="_Toc511125163" class="anchor"><span id="_Toc511120750" class="anchor"><span id="_Toc511122657" class="anchor"><span id="_Toc508792504" class="anchor"></span></span></span></span></span></span></span>

#### <a name="how-to-use-this-guide"></a><span data-ttu-id="3d647-131">如何使用本指南</span><span class="sxs-lookup"><span data-stu-id="3d647-131">How to use this guide</span></span>

<span data-ttu-id="3d647-132">本指南由两部分组成：</span><span class="sxs-lookup"><span data-stu-id="3d647-132">This guide consists of two parts:</span></span>

<span data-ttu-id="3d647-p107">**第 1 部分：响应对客户数据的数据主体请求** - 本指南第 1 部分讨论了如何访问、纠正、限制、删除数据和将数据从你创建数据的应用程序中导出。本节详细介绍了如何针对客户内容以及最终用户的身份信息执行 DSR。</span><span class="sxs-lookup"><span data-stu-id="3d647-p107">**Part 1: Responding to Data Subject Requests for Customer Data** — Part 1 of this guide discusses how to access, rectify, restrict, delete, and export data from applications in which you have authored data. This section details how to execute DSRs against both Customer Content and also identifiable information of end users.</span></span>

<span data-ttu-id="3d647-p108">**第 2 部分：响应对系统生成日志的数据主体请求** - 在你使用 Microsoft 的企业服务时，Microsoft 会生成一些信息（称为系统生成日志）以提供服务。本指南第 2 部分讨论了如何访问、删除和导出 Azure 的此类信息。</span><span class="sxs-lookup"><span data-stu-id="3d647-p108">**Part 2: Responding to Data Subject Requests for System-Generated Logs** — When you use Microsoft’s enterprise services, Microsoft generates some information, known as System-Generated Logs, in order to provide the service. Part 2 of this guide discusses how to access, delete and export such information for Azure.</span></span>

<span id="_Toc511384803" class="anchor"><span id="_Toc511163874" class="anchor"></span></span>







### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-intune"></a><span data-ttu-id="3d647-137">了解 Azure Active Directory 和 Microsoft Intune 的 DSR</span><span class="sxs-lookup"><span data-stu-id="3d647-137">Understanding DSRs for Azure Active Directory and Microsoft Intune</span></span>

<span data-ttu-id="3d647-p109">在考虑提供给企业客户的服务时，必须始终在特定 Azure Active Directory (AAD) 租户环境中执行 DSR。需要注意的是，始终在给定的 AAD 租户内执行 DSR。如果用户参与了多个租户，则务必注意*仅*在收到请求的特定租户内执行给定的 DSR。必须知道的是，这意味着一个企业客户执行 DSR **不会**影响相邻企业客户的数据。</span><span class="sxs-lookup"><span data-stu-id="3d647-p109">When considering services provided to enterprise customers, execution of DSRs must always be understood within the context of a specific Azure Active Directory (AAD) tenant. Notably, DSRs are always executed within a given AAD tenant. If a user is participating in multiple tenants, it is important to emphasize that a given DSR is *only* executed within the context of the specific tenant the request was received within. This is critical to understand as it means the execution of a DSR by one enterprise customer **will not** impact the data of an adjacent enterprise customer.</span></span>

<span data-ttu-id="3d647-p110">这同样也适用于提供给企业客户的 Microsoft Intune：针对*与 AAD 租户关联*的 Intune 帐户执行 DSR **将仅**与租户内的数据相关。此外，在处理租户内的 Intune 帐户时，请务必了解以下内容：</span><span class="sxs-lookup"><span data-stu-id="3d647-p110">The same also applies for Microsoft Intune provided to an enterprise customer: execution of a DSR against an Intune account *associated with an AAD tenant* **will only** pertain to data within the tenant. In addition, it is important to understand the following when handling Intune accounts within a tenant:</span></span>

-   <span data-ttu-id="3d647-p111">如果 Intune 用户创建了 Azure 订阅，订阅将视为 AAD 租户。因此，如上文所述，DSR 的范围仅限于租户。</span><span class="sxs-lookup"><span data-stu-id="3d647-p111">If an Intune user creates an Azure subscription, the subscription will be handled as if it were an AAD tenant. Consequently, DSRs are scoped within the tenant as described above.</span></span>

-   <span data-ttu-id="3d647-p112">如果删除通过 Intune 帐户创建的 Azure 订阅，**不会影响**实际 Intune 帐户。同样，如上所述，Azure 订阅中执行的 DSR 仅限于租户本身。</span><span class="sxs-lookup"><span data-stu-id="3d647-p112">If an Azure subscription created via an Intune account is deleted, **it will not affect** the actual Intune account. Again, as noted above, DSRs executing within the Azure subscription are limited to the scope of the tenant itself.</span></span>

<span data-ttu-id="3d647-p113">在**给定租户外**针对 Intune 帐户本身的 DSR 将通过消费者隐私面板执行。请参考“Windows 数据主体请求指南”了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="3d647-p113">DSRs against an Intune account itself, **outside a given tenant**, are executed via the Consumer Privacy Dashboard. Please refer to the Windows Data Subject Request Guide for further details.</span></span>

<span id="_Toc508792505" class="anchor"><span id="_Toc511384804" class="anchor"><span id="_Toc511163875" class="anchor"><span id="_Toc511136231" class="anchor"><span id="_Toc511125164" class="anchor"><span id="_Toc511120751" class="anchor"><span id="_Toc511122658" class="anchor"></span></span></span></span></span></span></span>

## <a name="part-1-dsr-guide-for-customer-data"></a><span data-ttu-id="3d647-150">第 1 部分：客户数据的 DSR 指南</span><span class="sxs-lookup"><span data-stu-id="3d647-150">Part 1: DSR Guide for Customer Data</span></span>

<span id="_Toc511384805" class="anchor"><span id="_Toc511163876" class="anchor"><span id="_Toc511136232" class="anchor"><span id="_Toc511125165" class="anchor"><span id="_Toc511120752" class="anchor"><span id="_Toc511122659" class="anchor"></span></span></span></span></span></span>

### <a name="executing-dsrs-against-customer-data"></a><span data-ttu-id="3d647-151">针对客户数据执行 DSR</span><span class="sxs-lookup"><span data-stu-id="3d647-151">Executing DSRs against Customer Data</span></span>

<span data-ttu-id="3d647-p114">Microsoft 让你能够通过 Azure 门户访问、删除和导出某些客户数据，也可直接通过特定服务的预先存在的应用程序编程接口 (API) 或用户界面 (UI)（也称为*产品内体验*）。有关此类产品内体验的详细信息，在各个服务的参考文档中进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="3d647-p114">Microsoft provides the ability to access, delete, and export certain Customer Data through the Azure Portal and also directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services (also referred to as *in-product experiences*). Details regarding such in-product experiences are described in the respective services’ reference documentation.</span></span>

>[!Important]  
><span data-ttu-id="3d647-p115">支持产品内 DSR 的服务要求直接使用服务的应用程序编程接口 (API) 或用户界面 (UI)，描述适用的 CRUD（创建、读取、更新、删除）操作。因此，除了在 Azure 门户中内执行 DSR 之外，还必须在给定服务内执行 DSR，以便完成针对给定数据主体的完整请求。请参考特定服务的参考文档以了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="3d647-p115">Services supporting in-product DSRs require direct usage of the service’s application programming interface (API) or user interface (UI), describing applicable CRUD (create, read, update, delete) operations. Consequently, execution of DSRs within a given service must be done in addition to execution of a DSR within the Azure Portal in order to complete a full request for a given data subject. Please refer to specific services’ reference documentation for further details.</span></span>

<span id="_Discover" class="anchor"><span id="_Toc508792508" class="anchor"><span id="_Toc511122661" class="anchor"><span id="_Toc511120754" class="anchor"><span id="_Toc511125167" class="anchor"><span id="_Toc511136234" class="anchor"><span id="_Toc511163877" class="anchor"><span id="_Toc511384806" class="anchor"></span></span></span></span></span></span></span></span>
### <a name="step-1-discover"></a><span data-ttu-id="3d647-157">步骤 1：发现</span><span class="sxs-lookup"><span data-stu-id="3d647-157">Step 1: Discover</span></span>

<span data-ttu-id="3d647-p116">响应 DSR 的第一步是查找作为请求主体的个人数据。这第一步（查找和审查所涉及的个人数据）将帮助你确定 DSR 是否符合组织有关接受或拒绝 DSR 的要求。例如，在查找并审查所涉及的个人数据后，你可以确定请求不符合组织的要求，因为这样做可能会对他人的权利和自由产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="3d647-p116">The first step in responding to a DSR is to find the personal data that is the subject of the request. This first step - finding and reviewing the personal data at issue - will help you determine whether a DSR meets your organization's requirements for honoring or declining a DSR. For example, after finding and reviewing the personal data at issue, you may determine the request doesn’t meet your organization’s requirements because doing so may adversely affect the rights and freedoms of others.</span></span>

<span data-ttu-id="3d647-p117">找到数据后，可执行特定操作以满足数据主体的请求。有关详细信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="3d647-p117">After you find the data, you can then perform the specific action to satisfy the request by the data subject. For details, see the following:</span></span>
- [<span data-ttu-id="3d647-163">数据收集</span><span class="sxs-lookup"><span data-stu-id="3d647-163">Data collection</span></span>](https://docs.microsoft.com/intune/privacy-data-collect)
- [<span data-ttu-id="3d647-164">数据存储和处理</span><span class="sxs-lookup"><span data-stu-id="3d647-164">Data storage and processing</span></span>](https://docs.microsoft.com/intune/privacy-data-store-process)
- [<span data-ttu-id="3d647-165">查找个人数据</span><span class="sxs-lookup"><span data-stu-id="3d647-165">View personal data</span></span>](https://docs.microsoft.com/intune/privacy-data-view-correct#view-personal-data)

### <a name="step-2-access"></a><span data-ttu-id="3d647-166">步骤 2：访问</span><span class="sxs-lookup"><span data-stu-id="3d647-166">Step 2: Access</span></span>
<span data-ttu-id="3d647-p118">在找到包含潜在响应 DSR 的个人数据的客户数据后，应该由你和你的组织决定将哪些数据提供给数据主体。可以通过实际文档副本、经过适当编校的版本或者你认为适合共享的部分的屏幕截图来提供。对于访问请求的每个响应，需要检索包含响应数据的文档或其他项目的副本。</span><span class="sxs-lookup"><span data-stu-id="3d647-p118">After you’ve found Customer Data containing personal data that is potentially responsive to a DSR, it is up to you and your organization to decide which data to provide to the data subject. You can provide them with a copy of the actual document, an appropriately redacted version, or a screenshot of the portions you have deemed appropriate to share. For each of these responses to an access request, you will have to retrieve a copy of the document or other item that contains the responsive data.</span></span>

<span data-ttu-id="3d647-170">将副本提供给数据主体时，可能需要删除或修订有关其他数据主体和任何机密信息的个人信息。</span><span class="sxs-lookup"><span data-stu-id="3d647-170">When providing a copy to the data subject, you may have to remove or redact personal information about other data subjects and any confidential information.</span></span>

<span data-ttu-id="3d647-171"><span id="_Using_Content_Search_1" class="anchor"></span>以下内容说明了如何在对 DSR 访问请求的响应中获取数据副本。</span><span class="sxs-lookup"><span data-stu-id="3d647-171"><span id="_Using_Content_Search_1" class="anchor"></span>The following explains how to get a copy of data in response to a DSR access request.</span></span>

<span id="_Rectify" class="anchor"><span id="_Ref511119463" class="anchor"><span id="_Toc511122665" class="anchor"><span id="_Toc511120758" class="anchor"><span id="_Toc511125171" class="anchor"><span id="_Toc511136238" class="anchor"><span id="_Toc511163881" class="anchor"><span id="_Toc511384810" class="anchor"></span></span></span></span></span></span></span></span>

#### <a name="azure-active-directory"></a><span data-ttu-id="3d647-172">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3d647-172">Azure Active Directory</span></span>

<span data-ttu-id="3d647-p119"><span id="_Forms_1" class="anchor"></span>Microsoft 提供了门户和产品内体验，让企业客户的租户管理员能够管理 DSR 访问请求。DSR 访问请求允许访问用户的个人数据，包括：(a) 最终用户的身份信息，以及 (b) 系统生成日志。</span><span class="sxs-lookup"><span data-stu-id="3d647-p119"><span id="_Forms_1" class="anchor"></span>Microsoft offers both a portal and in-product experiences providing the enterprise customer’s tenant administrator the capability to manage DSR access requests. DSR Access requests allow for access of the personal data of the user, including: (a) identifiable information about an end-user and (b) system-generated logs.</span></span>

<span id="_Toc511384811" class="anchor"><span id="_Toc511163882" class="anchor"><span id="_Toc511136239" class="anchor"><span id="_Toc511125172" class="anchor"><span id="_Toc511120759" class="anchor"><span id="_Toc511122666" class="anchor"></span></span></span></span></span></span>
#### <a name="service-specific-interfaces"></a><span data-ttu-id="3d647-175">特定于服务的界面</span><span class="sxs-lookup"><span data-stu-id="3d647-175">Service-Specific Interfaces</span></span>

<span data-ttu-id="3d647-176">Microsoft Intune 通过用户界面 (UI) 或预先存在的应用程序编程接口 (API) 直接提供[发现客户数据](#step-1-discover)的功能。</span><span class="sxs-lookup"><span data-stu-id="3d647-176">Microsoft Intune provides the ability to [discover Customer Data](#step-1-discover) directly via user interfaces (UIs) or pre-existing application programming interfaces (APIs).</span></span>

<span id="_Sway" class="anchor"><span id="_Toc508792516" class="anchor"><span id="_Toc511122667" class="anchor"><span id="_Toc511120760" class="anchor"><span id="_Toc511125173" class="anchor"><span id="_Toc511136240" class="anchor"><span id="_Toc511163883" class="anchor"><span id="_Toc511384812" class="anchor"></span></span></span></span></span></span></span></span>
### <a name="step-3-rectify"></a><span data-ttu-id="3d647-177">步骤 3：纠正</span><span class="sxs-lookup"><span data-stu-id="3d647-177">Step 3: Rectify</span></span>

<span data-ttu-id="3d647-p120">如果数据主体要求你纠正驻留在你组织数据中的个人数据，你和你的组织需要确定是否接受请求。纠正数据可能包括以下操作：编辑、修订个人数据或从文档或其他项目类型中移除个人数据。</span><span class="sxs-lookup"><span data-stu-id="3d647-p120">If a data subject has asked you to rectify the personal data that resides in your organization’s data, you and your organization will have to determine whether it’s appropriate to honor the request. Rectifying the data may include taking actions such as editing, redacting, or removing personal data from a document or other type or item.</span></span> 

<span id="_Toc511384813" class="anchor"><span id="_Toc511163884" class="anchor"><span id="_Toc511136241" class="anchor"><span id="_Toc511125174" class="anchor"><span id="_Toc511120761" class="anchor"><span id="_Toc511122668" class="anchor"></span></span></span></span></span></span>


 <span data-ttu-id="3d647-p121">Microsoft 作为数据处理者不提供纠正系统生成的日志的功能，因为它反映真实活动并构成 Microsoft 服务内事件的历史记录。对于 Intune，管理员无法更新特定于设备或应用的信息。如果最终用户想要纠正任何个人数据（例如，设备名称），他们必须直接在其设备上执行此操作。此类更改将在他们下次连接到 Intune 时同步。</span><span class="sxs-lookup"><span data-stu-id="3d647-p121">As a data processor, Microsoft does not offer the ability to correct system-generated logs as it reflects factual activities and constitutes a historical record of events within Microsoft services. With respect to Intune, admins can’t update device or app specific information. If an end user wants to correct any personal data (like the device name), they must do so directly on their device. Such changes are synchronized the next time they connect to Intune.</span></span>

### <a name="step-4-restrict"></a><span data-ttu-id="3d647-184">步骤 4：限制</span><span class="sxs-lookup"><span data-stu-id="3d647-184">Step 4: Restrict</span></span>

<span data-ttu-id="3d647-p122"><span id="_Delete" class="anchor"></span>数据主体可能会请求限制其个人数据的处理。我们提供 Azure 门户和预先存在的应用程序编程接口 (API) 或用户界面 (UI)。这些体验让企业客户的租户管理员能够通过数据导出和数据删除组合功能来管理此类 DSR。有关详细信息，请参阅[处理个人数据](https://docs.microsoft.com/intune/privacy-data-store-process#processing-personal-data)。</span><span class="sxs-lookup"><span data-stu-id="3d647-p122"><span id="_Delete" class="anchor"></span>Data subjects may request that you restrict processing of their personal data. We provide both the Azure Portal and pre-existing application programming interfaces (APIs) or user interfaces (UIs). These experiences provide the enterprise customer’s tenant administrator the capability to manage such DSRs through a combination of data export and data deletion. For details, see [Processing personal data](https://docs.microsoft.com/intune/privacy-data-store-process#processing-personal-data).</span></span>

<span id="_Toc508792528" class="anchor"><span id="_Toc511122671" class="anchor"><span id="_Toc511120764" class="anchor"><span id="_Toc511125177" class="anchor"><span id="_Toc511136244" class="anchor"><span id="_Toc511163887" class="anchor"><span id="_Toc511384816" class="anchor"></span></span></span></span></span></span></span>
### <a name="step-5-delete"></a><span data-ttu-id="3d647-189">步骤 5：删除</span><span class="sxs-lookup"><span data-stu-id="3d647-189">Step 5: Delete</span></span>

<span data-ttu-id="3d647-p123">从组织的客户数据中删除个人数据的“清除权限”是 GDPR 中提供的重要保护。删除个人数据包括删除所有个人数据和系统生成的日志（审核日志信息除外）。有关详细信息，请参阅[删除最终用户个人数据](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#delete-end-user-personal-data)。</span><span class="sxs-lookup"><span data-stu-id="3d647-p123">The “right to erasure” by the removal of personal data from an organization’s Customer Data is a key protection in the GDPR. Removing personal data includes removing all personal data and system-generated logs, except audit log information. For details, see [Delete end user personal data](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#delete-end-user-personal-data).</span></span>


<span id="_Toc511384822" class="anchor"><span id="_Toc511163893" class="anchor"><span id="_Toc511136250" class="anchor"><span id="_Toc511125183" class="anchor"><span id="_Toc511120770" class="anchor"><span id="_Toc511122677" class="anchor"></span></span></span></span></span></span>
## <a name="part-2-system-generated-logs"></a><span data-ttu-id="3d647-193">第 2 部分：系统生成的日志</span><span class="sxs-lookup"><span data-stu-id="3d647-193">Part 2: System-Generated Logs</span></span>
<span data-ttu-id="3d647-p124">审核日志向租户管理员提供在 Microsoft Intune 中生成的更改的活动记录。审核日志适用于许多管理活动，通常包括创建、更新（编辑）、删除和分配操作。也可以查看生成审核事件的远程任务。这些审核日志可能包含在 Intune 中注册了设备的用户的个人数据。管理员无法删除审核日志。有关详细信息，请参阅[审核个人数据](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#audit-personal-data)。</span><span class="sxs-lookup"><span data-stu-id="3d647-p124">Audit logs provide tenant admins with a record of activities that generate a change in Microsoft Intune. Audit logs are available for many manage activities and typically create, update (edit), delete, and assign actions. Remote tasks that generate audit events can also be reviewed. These audit logs may contain personal data from users whose devices are enrolled in Intune. Admins can't delete audit logs. For details, see [Audit personal data](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#audit-personal-data).</span></span>


## <a name="notify-about-exporting-or-deleting-issues"></a><span data-ttu-id="3d647-200">通知导出或删除问题</span><span class="sxs-lookup"><span data-stu-id="3d647-200">Notify about exporting or deleting issues</span></span>
<span data-ttu-id="3d647-201">如果在从 Azure 门户导出或删除数据时遇到问题，请转到 Azure 门户“帮助 + 支持”\*\*\*\* 边栏选项卡，并在“订阅管理 > 其他安全与合规请求 > 隐私”边栏选项卡和“GDPR 请求”\*\*\*\* 下提交新票证。</span><span class="sxs-lookup"><span data-stu-id="3d647-201">If you run into issues while exporting or deleting data from the Azure portal, go to the Azure portal **Help + Support** blade and submit a new ticket under **Subscription Management > Other Security and Compliance Request > Privacy Blade and GDPR Requests**.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="3d647-202">了解更多</span><span class="sxs-lookup"><span data-stu-id="3d647-202">Learn more</span></span>
[<span data-ttu-id="3d647-203">Microsoft 信任中心</span><span class="sxs-lookup"><span data-stu-id="3d647-203">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)