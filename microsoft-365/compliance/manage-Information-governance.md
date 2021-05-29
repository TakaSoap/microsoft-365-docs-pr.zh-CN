---
title: Microsoft 365 中的 Microsoft 信息治理
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
recommendations: false
description: 实施 Microsoft 信息治理功能，以管理数据，满足合规性或监管要求。
ms.openlocfilehash: a62b1a20aa07c8b5d147fd24e3867c4d4c50174e
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683531"
---
# <a name="microsoft-information-governance-in-microsoft-365"></a><span data-ttu-id="b2eb6-103">Microsoft 365 中的 Microsoft 信息治理</span><span class="sxs-lookup"><span data-stu-id="b2eb6-103">Microsoft Information Governance in Microsoft 365</span></span>

><span data-ttu-id="b2eb6-104">*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="b2eb6-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="b2eb6-105">使用 Microsoft 信息管理（有时缩写为 MIG）功能来管理数据，以满足合规性或监管要求。</span><span class="sxs-lookup"><span data-stu-id="b2eb6-105">Use Microsoft Information Governance (sometimes abbreviated to MIG) capabilities to govern your data for compliance or regulatory requirements.</span></span>

![管理数据 - 信息治理和记录管理](../media/information-governance-records-management.png)

<span data-ttu-id="b2eb6-107">需要保护数据？</span><span class="sxs-lookup"><span data-stu-id="b2eb6-107">Looking to protect your data?</span></span> <span data-ttu-id="b2eb6-108">请参阅 [Microsoft 365 中的 Microsoft 信息保护](information-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="b2eb6-108">See [Microsoft Information Protection in Microsoft 365](information-protection.md).</span></span>

<span data-ttu-id="b2eb6-p102">为帮助遵守数据隐私法规，我们设计工作流指导你完成端到端流程，以在 Microsoft 365 中计划和实现功能，包括安全访问、威胁防护、信息保护和数据管理。有关详细信息，请参阅 [使用 Microsoft 365 为数据隐私法规部署信息保护](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy)。</span><span class="sxs-lookup"><span data-stu-id="b2eb6-p102">To help you comply with data privacy regulations, we’ve designed a workflow to guide you through an end-to-end process to plan and implement capabilities across Microsoft 365, including secure access, threat protection, information protection, and data governance. For more information, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).</span></span> 

## <a name="information-governance"></a><span data-ttu-id="b2eb6-111">信息管理政策</span><span class="sxs-lookup"><span data-stu-id="b2eb6-111">Information governance</span></span>

<span data-ttu-id="b2eb6-112">保留所需要的东西，删除不需要的东西：</span><span class="sxs-lookup"><span data-stu-id="b2eb6-112">To keep what you need and delete what you don't:</span></span>
 
|<span data-ttu-id="b2eb6-113">功能</span><span class="sxs-lookup"><span data-stu-id="b2eb6-113">Capability</span></span>|<span data-ttu-id="b2eb6-114">它能解决什么问题？</span><span class="sxs-lookup"><span data-stu-id="b2eb6-114">What problems does it solve?</span></span>|<span data-ttu-id="b2eb6-115">开始行动</span><span class="sxs-lookup"><span data-stu-id="b2eb6-115">Get started</span></span>|
|:------|:------------|:--------------------|:-----------------------------|
|[<span data-ttu-id="b2eb6-116">保留策略和保留标签</span><span class="sxs-lookup"><span data-stu-id="b2eb6-116">Retention policies and retention labels</span></span>](retention.md)| <span data-ttu-id="b2eb6-117">通过策略管理和删除工作流程以保留或删除电子邮件、文档、即时消息等内容。</span><span class="sxs-lookup"><span data-stu-id="b2eb6-117">Retain or delete content with policy management and a deletion workflow for email, documents, instant messages, and more</span></span> <br /><br /><span data-ttu-id="b2eb6-118">示例方案：[自动保留应用内容标签](apply-retention-labels-automatically.md)</span><span class="sxs-lookup"><span data-stu-id="b2eb6-118">Example scenario: [Apply a retention label to content automatically](apply-retention-labels-automatically.md)</span></span> | [<span data-ttu-id="b2eb6-119">开始使用保留策略和保留标签</span><span class="sxs-lookup"><span data-stu-id="b2eb6-119">Get started with retention policies and retention labels</span></span>](get-started-with-retention.md)|
|[<span data-ttu-id="b2eb6-120">导入服务</span><span class="sxs-lookup"><span data-stu-id="b2eb6-120">Import service</span></span>](importing-pst-files-to-office-365.md)| <span data-ttu-id="b2eb6-121">将 PST 文件批量导入到 Exchange Online 邮箱，以保留和搜索电子邮件信息，以满足合规性或法规要求</span><span class="sxs-lookup"><span data-stu-id="b2eb6-121">Bulk-import PST files to Exchange Online mailboxes to retain and search email messages for compliance or regulatory requirements</span></span> | [<span data-ttu-id="b2eb6-122">使用网络上传将组织的 PST 文件导入到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b2eb6-122">Use network upload to import your organization's PST files to Microsoft 365</span></span>](use-network-upload-to-import-pst-files.md)|
|[<span data-ttu-id="b2eb6-123">存档第三方数据</span><span class="sxs-lookup"><span data-stu-id="b2eb6-123">Archive third-party data</span></span>](archiving-third-party-data.md)| <span data-ttu-id="b2eb6-124">从社交媒体平台、即时通讯平台、文档协作平台导入、归档、应用第三方数据的合规性解决方案。</span><span class="sxs-lookup"><span data-stu-id="b2eb6-124">Import, archive, and apply compliance solutions to third-party data from social media platforms, instant messaging platforms, and document collaboration platforms</span></span>| [<span data-ttu-id="b2eb6-125">第三方连接器</span><span class="sxs-lookup"><span data-stu-id="b2eb6-125">Third-party connectors</span></span>](archiving-third-party-data.md#third-party-data-connectors)|
|[<span data-ttu-id="b2eb6-126">非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="b2eb6-126">Inactive mailboxes</span></span>](inactive-mailboxes-in-office-365.md)| <span data-ttu-id="b2eb6-127">在员工离开组织后保留邮箱内容</span><span class="sxs-lookup"><span data-stu-id="b2eb6-127">Retain mailbox content after employees leave the organization</span></span> | [<span data-ttu-id="b2eb6-128">创建和管理非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="b2eb6-128">Create and manage inactive mailboxes</span></span>](create-and-manage-inactive-mailboxes.md)|

## <a name="records-management"></a><span data-ttu-id="b2eb6-129">记录管理</span><span class="sxs-lookup"><span data-stu-id="b2eb6-129">Records management</span></span>

<span data-ttu-id="b2eb6-130">为法律、业务或法规义务管理高价值内容：</span><span class="sxs-lookup"><span data-stu-id="b2eb6-130">To manage high-value content for legal, business, or regulatory obligations:</span></span>

|<span data-ttu-id="b2eb6-131">功能</span><span class="sxs-lookup"><span data-stu-id="b2eb6-131">Capability</span></span>|<span data-ttu-id="b2eb6-132">它能解决什么问题？</span><span class="sxs-lookup"><span data-stu-id="b2eb6-132">What problems does it solve?</span></span>|<span data-ttu-id="b2eb6-133">开始行动</span><span class="sxs-lookup"><span data-stu-id="b2eb6-133">Get started</span></span>|
|:------|:------------|---------------------|:----------------------------|
|[<span data-ttu-id="b2eb6-134">记录管理</span><span class="sxs-lookup"><span data-stu-id="b2eb6-134">Records management</span></span>](records-management.md)| <span data-ttu-id="b2eb6-135">针对电子邮件和文档的单一解决方案，可将保留计划和要求纳入文件计划中，通过记录声明、保留和处置来支持内容完整生命周期。</span><span class="sxs-lookup"><span data-stu-id="b2eb6-135">A single solution for email and documents that incorporates retention schedules and requirements into a file plan that supports the full lifecycle of your content with records declaration, retention, and disposition</span></span> <br /><br /><span data-ttu-id="b2eb6-136">示例方案：[记录的处置](disposition.md#disposition-of-records)</span><span class="sxs-lookup"><span data-stu-id="b2eb6-136">Example scenario: [Disposition of records](disposition.md#disposition-of-records)</span></span>|[<span data-ttu-id="b2eb6-137">开始进行记录管理</span><span class="sxs-lookup"><span data-stu-id="b2eb6-137">Get started with records management</span></span>](get-started-with-records-management.md) |

## <a name="licensing-requirements"></a><span data-ttu-id="b2eb6-138">许可要求</span><span class="sxs-lookup"><span data-stu-id="b2eb6-138">Licensing requirements</span></span>

<span data-ttu-id="b2eb6-139">Microsoft 信息治理的许可要求取决于使用的方案和功能，而不是为本页列出的每个功能设置许可要求。</span><span class="sxs-lookup"><span data-stu-id="b2eb6-139">License requirements for Microsoft Information Governance depend on the scenarios and features you use, rather than set licensing requirements for each capability listed on this page.</span></span> <span data-ttu-id="b2eb6-140">若要了解许可要求和选项，请参阅 Microsoft 365 许可文档中的 [信息管理](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) 和 [记录管理](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management) 部分，并下载相关的 PDF 或 Excel。</span><span class="sxs-lookup"><span data-stu-id="b2eb6-140">To understand your licensing requirements and options, see the [Information Governance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) and [Records Management](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management) sections from the Microsoft 365 licensing documentation, and download the related PDF or Excel.</span></span>