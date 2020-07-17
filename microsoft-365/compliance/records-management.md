---
title: 记录管理
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: 通过 Microsoft 365 中的记录管理，你可以将保留计划应用到文件计划中，以管理保留、记录声明和处置。
ms.openlocfilehash: 48705ac6d0c271ca2646de7c058a340ee3f736ae
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818952"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="56e4f-103">Microsoft 365 中的记录管理</span><span class="sxs-lookup"><span data-stu-id="56e4f-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="56e4f-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="56e4f-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="56e4f-105">所有类型的组织都需要一个记录管理解决方案跨公司数据管理法规、法律和业务关键记录。</span><span class="sxs-lookup"><span data-stu-id="56e4f-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="56e4f-106">Microsoft 365 中的记录管理有助于组织管理其法律义务，提供证明遵守法规的能力，并通过定期处置不再需要保留、不再具有价值或不再需要用于业务目的的项目来提高效率。</span><span class="sxs-lookup"><span data-stu-id="56e4f-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="56e4f-107">Microsoft 365 中的记录管理提供了以下功能：</span><span class="sxs-lookup"><span data-stu-id="56e4f-107">Records management in Microsoft 365 provides the following capabilities:</span></span>

- <span data-ttu-id="56e4f-108">**将内容标记为记录**。</span><span class="sxs-lookup"><span data-stu-id="56e4f-108">**Label content as a record**.</span></span> <span data-ttu-id="56e4f-109">创建并发布将内容标记为[记录](records.md)的保留标签，该类标签随后可由最终用户应用，或通过标识敏感信息、关键字或内容类型[自动应用](labels.md#applying-a-retention-label-automatically-based-on-conditions)。</span><span class="sxs-lookup"><span data-stu-id="56e4f-109">Create and publish retention labels that mark content as a [record](records.md) that can then be applied by end users or [auto-applied](labels.md#applying-a-retention-label-automatically-based-on-conditions) by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="56e4f-110">**使用文件计划迁移和管理保留要求**。</span><span class="sxs-lookup"><span data-stu-id="56e4f-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="56e4f-111">通过使用[文件计划](file-plan-manager.md)，可将现有保留计划引入 Microsoft 365，或者构建一个新的保留计划来增强管理功能。</span><span class="sxs-lookup"><span data-stu-id="56e4f-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="56e4f-112">**在记录标签中建立保留和删除策略**。</span><span class="sxs-lookup"><span data-stu-id="56e4f-112">**Establish retention and deletion policies within the record label**.</span></span> <span data-ttu-id="56e4f-113">根据各种因素（包括上次修改日期或创建日期）定义[保留](create-retention-policies.md#retaining-content-for-a-specific-period-of-time)和[处置](create-retention-policies.md#deleting-content-thats-older-than-a-specific-age)期间。</span><span class="sxs-lookup"><span data-stu-id="56e4f-113">Define [retention](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](create-retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="56e4f-114">使用[基于事件的保留](event-driven-retention.md)**触发基于事件的保留**。</span><span class="sxs-lookup"><span data-stu-id="56e4f-114">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="56e4f-115">使用[处置评审](disposition.md#disposition-reviews)和[记录删除](disposition.md#disposition-of-records)证明**审核并验证处置**。</span><span class="sxs-lookup"><span data-stu-id="56e4f-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="56e4f-116">使用[导出选项](disposition.md#filter-and-export-the-views)**导出有关所有已处置项的信息**。</span><span class="sxs-lookup"><span data-stu-id="56e4f-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="56e4f-117">为组织中的记录管理器功能**设置特定权限**，以便[具有正确的访问权限](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="56e4f-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="56e4f-118">通过 Microsoft 365 中的记录管理解决方案，你可以将组织的保留计划合并到文件计划中，以管理保留、记录声明和处置，从而支持完整的内容生命周期。</span><span class="sxs-lookup"><span data-stu-id="56e4f-118">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition to support the full lifecycle of your content.</span></span>

## <a name="next-steps"></a><span data-ttu-id="56e4f-119">后续步骤</span><span class="sxs-lookup"><span data-stu-id="56e4f-119">Next steps</span></span>

<span data-ttu-id="56e4f-120">如果已准备好开始使用 Microsoft 365 中的记录管理，请参阅[了解记录](records.md)。</span><span class="sxs-lookup"><span data-stu-id="56e4f-120">If you are ready to get started with records management in Microsoft 365, see [Learn about records](records.md).</span></span>
