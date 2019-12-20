---
title: 在 Microsoft 365 安全中心中打开 Microsoft 威胁防护
description: 了解如何启用 Microsoft 威胁防护并开始集成安全事件和响应。
keywords: 入门, MTP, Microsoft 威胁防护, M365, 安全, 数据位置
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 7790e079d4b39b5d41961a26bb17009adb1bec1d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808447"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="9a70d-104">打开 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="9a70d-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="9a70d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9a70d-105">**Applies to:**</span></span>
- <span data-ttu-id="9a70d-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="9a70d-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="9a70d-107">Microsoft 威胁防护通过集成 Microsoft Defender 高级威胁防护 (ATP)、Office 365 ATP、Microsoft Cloud App Security 和 Azure ATP 的关键功能来统一事件响应流程。</span><span class="sxs-lookup"><span data-stu-id="9a70d-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="9a70d-108">这种统一的体验增加了可在 Microsoft 365 安全中心访问的强大功能。</span><span class="sxs-lookup"><span data-stu-id="9a70d-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-your-eligibility"></a><span data-ttu-id="9a70d-109">检查资格</span><span class="sxs-lookup"><span data-stu-id="9a70d-109">Check your eligibility</span></span>
<span data-ttu-id="9a70d-110">拥有 Microsoft 365 E5 或等效许可证的客户可以使用 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="9a70d-110">Customers with a Microsoft 365 E5 or equivalent license can use Microsoft Threat Protection.</span></span> <span data-ttu-id="9a70d-111">有关更多信息，请[阅读许可要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="9a70d-111">For more information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="9a70d-112">开始使用服务</span><span class="sxs-lookup"><span data-stu-id="9a70d-112">Start using the service</span></span>
<span data-ttu-id="9a70d-113">打开 Microsoft 威胁防护服务可聚合来自各种集成服务的数据。</span><span class="sxs-lookup"><span data-stu-id="9a70d-113">Turning on the Microsoft Threat Protection service aggregates data from the various integrated services.</span></span> <span data-ttu-id="9a70d-114">系统将对数据进行集中处理和存储，以确定新的见解，并使集中的响应工作流程成为可能。</span><span class="sxs-lookup"><span data-stu-id="9a70d-114">The data will be processed and stored centrally to identify new insights and to make centralized response workflows possible.</span></span>

<span data-ttu-id="9a70d-115">在你打开该服务之前，Microsoft 365 安全中心 ([security.microsoft.com](https://security.microsoft.com)) 不会在菜单上显示“**事件**”和“**操作中心**”选项。</span><span class="sxs-lookup"><span data-stu-id="9a70d-115">Before you turn the service on, Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) does not show the **Incidents** and the **Action center** options on the menu.</span></span>

<span data-ttu-id="9a70d-116">![不包含 Microsoft 威胁防护功能的 Microsoft 365 安全中心菜单图像](../images/mtp-off.png)
*关闭了 Microsoft 威胁防护的 Microsoft 365 安全中心*</span><span class="sxs-lookup"><span data-stu-id="9a70d-116">![Image of Microsoft 365 security center menu without Microsoft Threat Protection features](../images/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="9a70d-117">要打开 Microsoft 威胁防护服务，请转到 Microsoft 365 安全中心中的“**设置**” > “**Microsoft 威胁防护**” > “**选择加入/选择退出**”。</span><span class="sxs-lookup"><span data-stu-id="9a70d-117">To turn the Microsoft Threat Protection service on, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="9a70d-118">要执行此任务，你需要是 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 中的全局管理员或安全管理员。</span><span class="sxs-lookup"><span data-stu-id="9a70d-118">You will need to be a global administrator or a security administrator in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to perform this task.</span></span>

<span data-ttu-id="9a70d-119">如果已为组织设置了 Microsoft Defender ATP，则数据将在为 [Microsoft Defender ATP 数据](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)选择的同一数据中心位置进行存储和处理。</span><span class="sxs-lookup"><span data-stu-id="9a70d-119">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="9a70d-120">如果你没有 Microsoft Defender ATP，系统将要求你选择一个专门用于 Microsoft 威胁防护的新数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="9a70d-120">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> <span data-ttu-id="9a70d-121">你需要确认同意，才能在服务和聚合之间共享数据。</span><span class="sxs-lookup"><span data-stu-id="9a70d-121">You will need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="9a70d-122">确认服务已开启</span><span class="sxs-lookup"><span data-stu-id="9a70d-122">Confirm that the service is on</span></span>
<span data-ttu-id="9a70d-123">设置服务后，它将添加：</span><span class="sxs-lookup"><span data-stu-id="9a70d-123">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="9a70d-124">事件管理</span><span class="sxs-lookup"><span data-stu-id="9a70d-124">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="9a70d-125">用于管理[自动调查和响应](mtp-autoir.md)的操作中心</span><span class="sxs-lookup"><span data-stu-id="9a70d-125">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="9a70d-126">[高级搜寻](advanced-hunting-overview.md)功能（添加到现有**搜寻**页面）</span><span class="sxs-lookup"><span data-stu-id="9a70d-126">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="9a70d-127">![包含 Microsoft 威胁防护功能的 Microsoft 365 安全中心菜单图像](../images/mtp-on.png)
*包含事件管理和其他 Microsoft 威胁防护功能的 Microsoft 365 安全中心*</span><span class="sxs-lookup"><span data-stu-id="9a70d-127">![Image of Microsoft 365 security center menu with Microsoft Threat Protection features](../images/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection features*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="9a70d-128">获取 Azure ATP 数据</span><span class="sxs-lookup"><span data-stu-id="9a70d-128">Getting Azure ATP data</span></span>
<span data-ttu-id="9a70d-129">要使用 Microsoft 威胁防护共享 Azure ATP 数据，请确保已打开 Microsoft Cloud App Security 和 Azure ATP 集成。</span><span class="sxs-lookup"><span data-stu-id="9a70d-129">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="9a70d-130">了解有关此集成的更多信息</span><span class="sxs-lookup"><span data-stu-id="9a70d-130">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="9a70d-131">关闭 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="9a70d-131">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="9a70d-132">要停止使用 Microsoft 威胁防护，请转到 Microsoft 365 安全中心中的“**设置**” > “**Microsoft 威胁防护**” > “**选择加入/选择退出**”。</span><span class="sxs-lookup"><span data-stu-id="9a70d-132">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="9a70d-133">取消选择**打开 Microsoft 威胁防护**并保存更改。</span><span class="sxs-lookup"><span data-stu-id="9a70d-133">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="9a70d-134">数据将被永久删除，相应的功能将从 Microsoft 365 安全中心中删除。</span><span class="sxs-lookup"><span data-stu-id="9a70d-134">Data will be permanently deleted and corresponding features will be removed from Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="9a70d-135">获取帮助</span><span class="sxs-lookup"><span data-stu-id="9a70d-135">Get assistance</span></span>

<span data-ttu-id="9a70d-136">Microsoft 员工可以帮助在你的租户上设置或取消设置服务和相关资源。</span><span class="sxs-lookup"><span data-stu-id="9a70d-136">Microsoft staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="9a70d-137">如需帮助，[请联系顶级支持](https://go.microsoft.com/fwlink/?LinkID=733758)。</span><span class="sxs-lookup"><span data-stu-id="9a70d-137">For assistance, [contact premier support](https://go.microsoft.com/fwlink/?LinkID=733758).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9a70d-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="9a70d-138">Related topics</span></span>

- [<span data-ttu-id="9a70d-139">Microsoft 威胁防护概述</span><span class="sxs-lookup"><span data-stu-id="9a70d-139">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="9a70d-140">许可要求和其他先决条件</span><span class="sxs-lookup"><span data-stu-id="9a70d-140">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="9a70d-141">Microsoft Defender ATP 概述</span><span class="sxs-lookup"><span data-stu-id="9a70d-141">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="9a70d-142">Office 365 ATP 概述</span><span class="sxs-lookup"><span data-stu-id="9a70d-142">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="9a70d-143">Microsoft Cloud App Security 概述</span><span class="sxs-lookup"><span data-stu-id="9a70d-143">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="9a70d-144">Azure ATP 概述</span><span class="sxs-lookup"><span data-stu-id="9a70d-144">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="9a70d-145">Microsoft Defender ATP 数据存储</span><span class="sxs-lookup"><span data-stu-id="9a70d-145">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
