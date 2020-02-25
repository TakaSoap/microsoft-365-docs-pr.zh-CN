---
title: 在 Microsoft 365 安全中心中打开 Microsoft 威胁防护
description: 了解如何启用 Microsoft 威胁防护并开始集成安全事件和响应。
keywords: 入门、启用 MTP、Microsoft 威胁防护、M365、security、data location、必需权限、许可证资格、设置页面
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 73f76dee8a59229138f906e593a84220c7f70aee
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235211"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="ed7b3-104">打开 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="ed7b3-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="ed7b3-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ed7b3-105">**Applies to:**</span></span>
- <span data-ttu-id="ed7b3-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="ed7b3-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="ed7b3-107">Microsoft 威胁防护通过集成 Microsoft Defender 高级威胁防护 (ATP)、Office 365 ATP、Microsoft Cloud App Security 和 Azure ATP 的关键功能来统一事件响应流程。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="ed7b3-108">这种统一的体验增加了可在 Microsoft 365 安全中心访问的强大功能。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="ed7b3-109">检查许可证资格和必需权限</span><span class="sxs-lookup"><span data-stu-id="ed7b3-109">Check license eligibility and required permissions</span></span>
<span data-ttu-id="ed7b3-110">Microsoft 365 E5、Microsoft 365 E5 安全或等效的许可证组合的客户可以使用 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-110">Customers with Microsoft 365 E5, Microsoft 365 E5 Security, or an equivalent combination of licenses can use Microsoft Threat Protection.</span></span> <span data-ttu-id="ed7b3-111">有关更多信息，请[阅读许可要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-111">For more information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

<span data-ttu-id="ed7b3-112">您必须是**全局管理员**或[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)中的**安全管理员**才能打开 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-112">You must be a **global administrator** or a **security administrator** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to turn on Microsoft Threat Protection.</span></span>

## <a name="start-using-the-service"></a><span data-ttu-id="ed7b3-113">开始使用服务</span><span class="sxs-lookup"><span data-stu-id="ed7b3-113">Start using the service</span></span>
<span data-ttu-id="ed7b3-114">Microsoft 威胁防护从各种集成服务中聚合数据。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-114">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="ed7b3-115">它将集中处理和存储数据，以确定新的见解并使集中响应工作流成为可能。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-115">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="ed7b3-116">在你打开服务之前，Microsoft 365 安全中心（[security.microsoft.com](https://security.microsoft.com)）不会在导航窗格中显示**事件**和**操作中心**选项。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-116">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) doesn't show the **Incidents** and the **Action center** options in the navigation pane.</span></span>

<span data-ttu-id="ed7b3-117">![未安装 microsoft 威胁防护功能](../../media/mtp-off.png)
的 microsoft 365 安全中心导航窗格的图像关闭 microsoft*365 安全中心，并关闭 microsoft 威胁防护*</span><span class="sxs-lookup"><span data-stu-id="ed7b3-117">![Image of Microsoft 365 security center navigation pane without Microsoft Threat Protection features](../../media/mtp-off.png)
*Microsoft 365 security center with Microsoft Threat Protection turned off*</span></span>

<span data-ttu-id="ed7b3-118">若要打开 Microsoft 威胁防护，请在导航窗格中选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-118">To turn on Microsoft Threat Protection, select **Settings** in the navigation pane.</span></span> <span data-ttu-id="ed7b3-119">在 "**[设置" 页](https://security.microsoft.com/settings)** 中，转到 " **Microsoft 威胁防护** > **" 自愿加入/自愿退出**。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-119">In the **[Settings page](https://security.microsoft.com/settings)**, go to **Microsoft Threat Protection** > **Opt-in / Opt-out**.</span></span>

>[!NOTE]
><span data-ttu-id="ed7b3-120">如果在导航窗格中看不到**设置**或无法访问页面，请检查您的权限和许可证。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-120">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="ed7b3-121">选择数据中心位置</span><span class="sxs-lookup"><span data-stu-id="ed7b3-121">Select data center location</span></span>
<span data-ttu-id="ed7b3-122">如果已为组织设置了 Microsoft Defender ATP，则数据将在为 [Microsoft Defender ATP 数据](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)选择的同一数据中心位置进行存储和处理。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-122">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="ed7b3-123">如果你没有 Microsoft Defender ATP，系统将要求你选择一个专门用于 Microsoft 威胁防护的新数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-123">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="ed7b3-124">您需要先提供许可，然后才能在服务和聚合之间共享数据。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-124">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="ed7b3-125">确认服务已开启</span><span class="sxs-lookup"><span data-stu-id="ed7b3-125">Confirm that the service is on</span></span>
<span data-ttu-id="ed7b3-126">设置服务后，它将添加：</span><span class="sxs-lookup"><span data-stu-id="ed7b3-126">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="ed7b3-127">事件管理</span><span class="sxs-lookup"><span data-stu-id="ed7b3-127">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="ed7b3-128">用于管理[自动调查和响应](mtp-autoir.md)的操作中心</span><span class="sxs-lookup"><span data-stu-id="ed7b3-128">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="ed7b3-129">[高级搜寻](advanced-hunting-overview.md)功能（添加到现有**搜寻**页面）</span><span class="sxs-lookup"><span data-stu-id="ed7b3-129">[Advanced hunting](advanced-hunting-overview.md) capabilities to the existing **Hunting** page</span></span>

<span data-ttu-id="ed7b3-130">![Microsoft 365 security center 导航窗格的图像与 microsoft 威胁防护功能](../../media/mtp-on.png)
*microsoft 365 security center with 事件管理和其他 Microsoft 威胁防护功能*</span><span class="sxs-lookup"><span data-stu-id="ed7b3-130">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="ed7b3-131">获取 Azure ATP 数据</span><span class="sxs-lookup"><span data-stu-id="ed7b3-131">Getting Azure ATP data</span></span>
<span data-ttu-id="ed7b3-132">要使用 Microsoft 威胁防护共享 Azure ATP 数据，请确保已打开 Microsoft Cloud App Security 和 Azure ATP 集成。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-132">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="ed7b3-133">了解有关此集成的更多信息</span><span class="sxs-lookup"><span data-stu-id="ed7b3-133">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="ed7b3-134">关闭 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="ed7b3-134">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="ed7b3-135">要停止使用 Microsoft 威胁防护，请转到 Microsoft 365 安全中心中的“**设置**” > “**Microsoft 威胁防护**” > “**选择加入/选择退出**”。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-135">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="ed7b3-136">取消选择**打开 Microsoft 威胁防护**并保存更改。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-136">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="ed7b3-137">将永久删除数据，并将从 Microsoft 365 安全中心删除相应的功能。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-137">Data will be permanently deleted and corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="ed7b3-138">获取帮助</span><span class="sxs-lookup"><span data-stu-id="ed7b3-138">Get assistance</span></span>

<span data-ttu-id="ed7b3-139">Microsoft 支持人员可帮助设置或取消设置或取消设置租户上的服务和相关资源。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-139">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="ed7b3-140">若要获取帮助，请在 Microsoft 365 安全中心中选择 **"需要帮助？** "。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-140">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="ed7b3-141">联系支持时，请提及 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="ed7b3-141">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ed7b3-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="ed7b3-142">Related topics</span></span>

- [<span data-ttu-id="ed7b3-143">Microsoft 威胁防护概述</span><span class="sxs-lookup"><span data-stu-id="ed7b3-143">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="ed7b3-144">许可要求和其他先决条件</span><span class="sxs-lookup"><span data-stu-id="ed7b3-144">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="ed7b3-145">Microsoft Defender ATP 概述</span><span class="sxs-lookup"><span data-stu-id="ed7b3-145">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="ed7b3-146">Office 365 ATP 概述</span><span class="sxs-lookup"><span data-stu-id="ed7b3-146">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="ed7b3-147">Microsoft Cloud App Security 概述</span><span class="sxs-lookup"><span data-stu-id="ed7b3-147">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="ed7b3-148">Azure ATP 概述</span><span class="sxs-lookup"><span data-stu-id="ed7b3-148">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="ed7b3-149">Microsoft Defender ATP 数据存储</span><span class="sxs-lookup"><span data-stu-id="ed7b3-149">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
