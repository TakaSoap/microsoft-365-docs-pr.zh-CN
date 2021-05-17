---
title: 从德国 Microsoft 云迁移期间电子数据展示体验的信息
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：从德国 Microsoft 云迁移电子数据展示迁移步骤。
ms.openlocfilehash: 16da6e6d1994ae107b62ff1f915454568a35344d
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592129"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="3f74e-103">从德国 Microsoft 云迁移期间电子数据展示体验的信息</span><span class="sxs-lookup"><span data-stu-id="3f74e-103">Information about the eDiscovery experience during the migration from Microsoft Cloud Deutschland</span></span>
<span data-ttu-id="3f74e-104">以下各节提供有关从德国 Microsoft 云 (德国 microsoft 云迁移到新的德国数据中心) Office 365服务时电子数据展示体验的其他信息。</span><span class="sxs-lookup"><span data-stu-id="3f74e-104">The following sections provide additional information about the eDiscovery experience when moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="ediscovery-administration-until-phase-4"></a><span data-ttu-id="3f74e-105">第 4 阶段前电子数据展示管理</span><span class="sxs-lookup"><span data-stu-id="3f74e-105">eDiscovery administration until phase 4</span></span>
<span data-ttu-id="3f74e-106">在第 4 阶段之前，安全与合规中心将完全可用。</span><span class="sxs-lookup"><span data-stu-id="3f74e-106">Until phase 4, the Security and Compliance Center will be fully available.</span></span> <span data-ttu-id="3f74e-107">所有内容仍保留在德国 Microsoft 云中，并且由德国 Microsoft 云安全与合规中心 https://protection.office.de/) (。</span><span class="sxs-lookup"><span data-stu-id="3f74e-107">All content still remains in the Microsoft Cloud Germany and is manageable by the Microsoft Cloud Germany Security and Compliance Center (https://protection.office.de/).</span></span>

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a><span data-ttu-id="3f74e-108">阶段 4 到阶段 9 结束之间的电子数据展示体验</span><span class="sxs-lookup"><span data-stu-id="3f74e-108">eDiscovery experience between phase 4 until the the end of phase 9</span></span>
<span data-ttu-id="3f74e-109">从阶段 4 开始到阶段 9 完成，电子数据展示搜索将失败或返回已迁移的 SharePoint Online、OneDrive for Business 和 Exchange Online 位置的 0 个结果。</span><span class="sxs-lookup"><span data-stu-id="3f74e-109">From the beginning of phase 4 until phase 9 is completed, eDiscovery searches will fail or return 0 results for SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated.</span></span>

> [!NOTE]
> <span data-ttu-id="3f74e-110">在迁移过程中，客户可以在安全与合规中心（包括内容搜索）&案例、保留、 [搜索](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)和 [导出](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)。</span><span class="sxs-lookup"><span data-stu-id="3f74e-110">During migration, customers can continue to create cases, holds, searches, and exports in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations), including [Content Search](https://docs.microsoft.com/microsoft-365/compliance/search-for-content).</span></span> <span data-ttu-id="3f74e-111">但是，针对 SharePoint Online、OneDrive for Business 和Exchange Online迁移的位置的搜索将返回 0 个结果或产生错误。</span><span class="sxs-lookup"><span data-stu-id="3f74e-111">However, searches against SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated will either return 0 results or produce an error.</span></span>

<span data-ttu-id="3f74e-112">如果搜索在迁移过程中返回零结果或错误，请对 SharePoint Online 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3f74e-112">In the event that a search returns zero results or an error during migration, please take the following action for SharePoint Online:</span></span> 
- <span data-ttu-id="3f74e-113">按照从 SharePoint 或 OneDrive for Business OneDrive 下载文件和文件夹中的说明，直接从 SharePoint Online 或 SharePoint[下载网站](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)。</span><span class="sxs-lookup"><span data-stu-id="3f74e-113">Download sites directly from the SharePoint Online or OneDrive for Business site by following the instructions in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05).</span></span> <span data-ttu-id="3f74e-114">此方法需要SharePoint联机管理员权限或只读权限。</span><span class="sxs-lookup"><span data-stu-id="3f74e-114">This method will require SharePoint Online administrator permissions or read-only permissions on the site.</span></span>
- <span data-ttu-id="3f74e-115">如果超出限制，如从 OneDrive 或[SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)下载文件和文件夹中介绍，客户可以按照将 SharePoint 和 Teams 文件与计算机同步中的指导使用 OneDrive for Business 同步[客户端](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)。</span><span class="sxs-lookup"><span data-stu-id="3f74e-115">If limits are exceeded, as explained in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), customers can use the OneDrive for Business sync client by following the guidance in [Sync SharePoint and Teams files with your computer](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88).</span></span>

- <span data-ttu-id="3f74e-116">有关详细信息，请参阅 就地电子数据展示[中的Exchange Server。](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery)</span><span class="sxs-lookup"><span data-stu-id="3f74e-116">For more information, see  [In-Place eDiscovery in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery).</span></span>


## <a name="ediscovery-administration-after-phase-9"></a><span data-ttu-id="3f74e-117">第 9 阶段之后电子数据展示管理</span><span class="sxs-lookup"><span data-stu-id="3f74e-117">eDiscovery administration after phase 9</span></span>

<span data-ttu-id="3f74e-118">**适用于：** 使用电子数据展示的所有客户</span><span class="sxs-lookup"><span data-stu-id="3f74e-118">**Applies to:** All customers using eDiscovery</span></span>

<span data-ttu-id="3f74e-119">在第 9 阶段，将完成移动到新的德国数据中心区域的最后步骤。</span><span class="sxs-lookup"><span data-stu-id="3f74e-119">In phase 9, the final steps for moving to the new German datacenter region will be completed.</span></span> <span data-ttu-id="3f74e-120">在此阶段，将迁移其余的所有服务组件。</span><span class="sxs-lookup"><span data-stu-id="3f74e-120">In this phase, all remaining service components will be migrated.</span></span> <span data-ttu-id="3f74e-121">在第 9 阶段之后，不再支持使用德国 Microsoft 云 (protection.office.de) 合规中心。</span><span class="sxs-lookup"><span data-stu-id="3f74e-121">After phase 9, using the Security and Compliance Center in Microsoft Cloud Germany (protection.office.de) is no longer supported.</span></span> <span data-ttu-id="3f74e-122">请改为使用新的[安全中心](https://security.microsoft.com/)[或合规中心](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="3f74e-122">Please use the new [Security Center](https://security.microsoft.com/) or [Compliance Center](https://compliance.microsoft.com/) instead.</span></span> <span data-ttu-id="3f74e-123">所有数据已迁移到新的管理门户。</span><span class="sxs-lookup"><span data-stu-id="3f74e-123">All data have been migrated to the new admin portals.</span></span> 

| <span data-ttu-id="3f74e-124">步骤 (步骤) </span><span class="sxs-lookup"><span data-stu-id="3f74e-124">Step(s)</span></span> | <span data-ttu-id="3f74e-125">说明</span><span class="sxs-lookup"><span data-stu-id="3f74e-125">Description</span></span> | <span data-ttu-id="3f74e-126">影响</span><span class="sxs-lookup"><span data-stu-id="3f74e-126">Impact</span></span> |
|:-------|:-------|:-------|
|  <span data-ttu-id="3f74e-127">所有 SharePoint Online、OneDrive for Business 和 Exchange Online 位置已随安全与合规中心 (SCC) 一起迁移。</span><span class="sxs-lookup"><span data-stu-id="3f74e-127">All SharePoint Online, OneDrive for Business, and Exchange Online locations have been migrated along with the Security and Compliance Center (SCC).</span></span> | <span data-ttu-id="3f74e-128">所有电子数据展示活动都应从全球租户运行。</span><span class="sxs-lookup"><span data-stu-id="3f74e-128">All eDiscovery activity should be run from the worldwide tenant.</span></span> <span data-ttu-id="3f74e-129">搜索现在将 100% 成功。</span><span class="sxs-lookup"><span data-stu-id="3f74e-129">Searches will now be 100% successful.</span></span> <span data-ttu-id="3f74e-130">任何失败或错误应遵循正常支持渠道。</span><span class="sxs-lookup"><span data-stu-id="3f74e-130">Any failures or errors should follow normal support channels.</span></span> | <span data-ttu-id="3f74e-131">无</span><span class="sxs-lookup"><span data-stu-id="3f74e-131">None</span></span> |
||||

### <a name="ediscovery-retention-policy"></a><span data-ttu-id="3f74e-132">电子数据展示保留策略</span><span class="sxs-lookup"><span data-stu-id="3f74e-132">eDiscovery Retention Policy</span></span>
<span data-ttu-id="3f74e-133">**适用于：**  作为迁移前步骤的一部分应用保留策略的所有客户</span><span class="sxs-lookup"><span data-stu-id="3f74e-133">**Applies to:**  All customers who applied a retention policy as part of the pre-migration steps</span></span>

| <span data-ttu-id="3f74e-134">步骤 (步骤) </span><span class="sxs-lookup"><span data-stu-id="3f74e-134">Step(s)</span></span> | <span data-ttu-id="3f74e-135">说明</span><span class="sxs-lookup"><span data-stu-id="3f74e-135">Description</span></span> | <span data-ttu-id="3f74e-136">影响</span><span class="sxs-lookup"><span data-stu-id="3f74e-136">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="3f74e-137">删除在迁移前步骤期间创建的组织范围内的保留策略</span><span class="sxs-lookup"><span data-stu-id="3f74e-137">Remove organization-wide retention policies that were created during pre-migration steps</span></span> | <span data-ttu-id="3f74e-138">客户可以删除在客户迁移前工作期间创建的组织范围的保留策略。</span><span class="sxs-lookup"><span data-stu-id="3f74e-138">Customers can remove the organization-wide retention policies that were created during the customers' pre-migration work.</span></span> | <span data-ttu-id="3f74e-139">无</span><span class="sxs-lookup"><span data-stu-id="3f74e-139">None</span></span> |
||||
