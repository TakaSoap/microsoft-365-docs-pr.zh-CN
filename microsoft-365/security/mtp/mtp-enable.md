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
ms.openlocfilehash: b6ac30f7e32bbec80952ad4f2104032886b11503
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016339"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="5f630-104">打开 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="5f630-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="5f630-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5f630-105">**Applies to:**</span></span>
- <span data-ttu-id="5f630-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="5f630-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="5f630-107">[Microsoft 威胁防护](microsoft-threat-protection.md)通过在 Microsoft Defender 高级威胁防护（ATP）、OFFICE 365 ATP、Microsoft 云应用安全性和 Azure atp 之间集成关键功能，统一了你的事件响应流程。</span><span class="sxs-lookup"><span data-stu-id="5f630-107">[Microsoft Threat Protection](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="5f630-108">这种统一的体验增加了可在 Microsoft 365 安全中心访问的强大功能。</span><span class="sxs-lookup"><span data-stu-id="5f630-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="5f630-109">当具有所需权限的符合条件的客户访问 Microsoft 365 安全中心时，Microsoft 威胁防护将自动启用。</span><span class="sxs-lookup"><span data-stu-id="5f630-109">Microsoft Threat Protection automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="5f630-110">阅读本文以了解各种先决条件以及如何设置 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="5f630-110">Read this article to understand various prerequisites and how Microsoft Threat Protection is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="5f630-111">检查许可证资格和必需权限</span><span class="sxs-lookup"><span data-stu-id="5f630-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="5f630-112">Microsoft 365 安全产品的许可证通常使您能够在 Microsoft 365 安全中心中使用 Microsoft 威胁防护，而无需额外的许可费用。</span><span class="sxs-lookup"><span data-stu-id="5f630-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft Threat Protection in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="5f630-113">我们建议获取 Microsoft 365 E5、E5、E5 或 A5 安全许可证或有效的许可证组合，以提供对所有支持的服务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="5f630-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="5f630-114">有关许可的详细信息，请[阅读许可要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="5f630-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="5f630-115">检查你的角色</span><span class="sxs-lookup"><span data-stu-id="5f630-115">Check your role</span></span>
<span data-ttu-id="5f630-116">您必须是**全局管理员**或 Azure Active Directory 中的**安全管理员**才能打开 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="5f630-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="5f630-117">在 Azure AD 中查看你的角色</span><span class="sxs-lookup"><span data-stu-id="5f630-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="5f630-118">支持的服务</span><span class="sxs-lookup"><span data-stu-id="5f630-118">Supported services</span></span>
<span data-ttu-id="5f630-119">Microsoft 威胁防护可从已部署的各种受支持的服务中聚合数据。</span><span class="sxs-lookup"><span data-stu-id="5f630-119">Microsoft Threat Protection aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="5f630-120">它将集中处理和存储数据，以确定新的见解并使集中响应工作流成为可能。</span><span class="sxs-lookup"><span data-stu-id="5f630-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="5f630-121">这样做不会影响与集成服务关联的现有部署、设置或数据。</span><span class="sxs-lookup"><span data-stu-id="5f630-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="5f630-122">若要获得最佳保护并优化 Microsoft 威胁防护，建议在网络上部署所有适用的受支持的服务。</span><span class="sxs-lookup"><span data-stu-id="5f630-122">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="5f630-123">有关详细信息，请[参阅部署支持的服务](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="5f630-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="5f630-124">启动服务之前</span><span class="sxs-lookup"><span data-stu-id="5f630-124">Before starting the service</span></span>
<span data-ttu-id="5f630-125">在你打开服务之前，Microsoft 365 安全中心（[security.microsoft.com](https://security.microsoft.com)）会在你选择 "**事件**"、"**操作中心**" 或 "导航窗格" 中的 "**搜寻**" 时显示 "microsoft 威胁防护设置" 页。</span><span class="sxs-lookup"><span data-stu-id="5f630-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="5f630-126">如果你不符合使用 Microsoft 威胁防护的条件，则不会显示这些导航项目。</span><span class="sxs-lookup"><span data-stu-id="5f630-126">These navigation items are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="5f630-127">![显示 microsoft 威胁防护设置页面的图像如果尚未在 microsoft ](../../media/mtp-enable/mtp-settings.png)
 *365 安全中心中*打开 microsoft 威胁防护设置的 microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="5f630-127">![Image of the Microsoft Threat Protection settings page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft Threat Protection settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="5f630-128">启动服务</span><span class="sxs-lookup"><span data-stu-id="5f630-128">Starting the service</span></span>
<span data-ttu-id="5f630-129">若要打开 Microsoft 威胁防护，只需选择 **"启用 Microsoft 威胁防护**" 并应用更改。</span><span class="sxs-lookup"><span data-stu-id="5f630-129">To turn on Microsoft Threat Protection, simply select **Turn on Microsoft Threat Protection** and apply the change.</span></span> <span data-ttu-id="5f630-130">您还可以通过在导航窗格中选择 "**设置**" （[security.microsoft.com/settings](https://security.microsoft.com/settings)），然后选择 " **microsoft 威胁防护**" 来访问此选项。</span><span class="sxs-lookup"><span data-stu-id="5f630-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="5f630-131">如果在导航窗格中看不到**设置**或无法访问页面，请检查您的权限和许可证。</span><span class="sxs-lookup"><span data-stu-id="5f630-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="5f630-132">数据中心位置</span><span class="sxs-lookup"><span data-stu-id="5f630-132">Data center location</span></span>
<span data-ttu-id="5f630-133">Microsoft 威胁防护将在[Microsoft DEFENDER ATP 使用的相同位置](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)存储和处理数据。</span><span class="sxs-lookup"><span data-stu-id="5f630-133">Microsoft Threat Protection will store and process data in the [same location used by Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="5f630-134">如果你没有 Microsoft Defender ATP，将根据活动的 Microsoft 365 安全服务的位置自动选择新的数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="5f630-134">If you don't have Microsoft Defender ATP, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="5f630-135">屏幕上显示了所选的数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="5f630-135">The selected data center location is shown in the screen.</span></span> 

<span data-ttu-id="5f630-136">在 Microsoft 365 安全中心中选择 **"需要帮助？** "，以与 microsoft 支持部门联系，以了解如何在其他数据中心位置设置 Microsoft 威胁保护。</span><span class="sxs-lookup"><span data-stu-id="5f630-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft Threat Protection in a different data center location.</span></span> 

>[!NOTE]
><span data-ttu-id="5f630-137">在通过 Azure 安全中心启用欧盟（EU）数据中心时，Microsoft Defender ATP 将自动设置。</span><span class="sxs-lookup"><span data-stu-id="5f630-137">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="5f630-138">对于已使用此方式预配 Microsoft Defender ATP 的客户，microsoft 威胁防护将自动在同一 EU 数据中心中进行设置。</span><span class="sxs-lookup"><span data-stu-id="5f630-138">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="5f630-139">确认服务已开启</span><span class="sxs-lookup"><span data-stu-id="5f630-139">Confirm that the service is on</span></span>
<span data-ttu-id="5f630-140">设置服务后，它将添加：</span><span class="sxs-lookup"><span data-stu-id="5f630-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="5f630-141">事件管理</span><span class="sxs-lookup"><span data-stu-id="5f630-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="5f630-142">用于管理[自动调查和响应](mtp-autoir.md)的操作中心</span><span class="sxs-lookup"><span data-stu-id="5f630-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="5f630-143">[高级搜寻](advanced-hunting-overview.md)功能</span><span class="sxs-lookup"><span data-stu-id="5f630-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="5f630-144">![Microsoft 365 security center 导航窗格的图像与 Microsoft 威胁防护功能 ](../../media/mtp-enable/mtp-on.png)
 *microsoft 365 security center with 事件管理和其他 Microsoft 威胁防护功能*</span><span class="sxs-lookup"><span data-stu-id="5f630-144">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="5f630-145">获取 Azure ATP 数据</span><span class="sxs-lookup"><span data-stu-id="5f630-145">Getting Azure ATP data</span></span>
<span data-ttu-id="5f630-146">要使用 Microsoft 威胁防护共享 Azure ATP 数据，请确保已打开 Microsoft Cloud App Security 和 Azure ATP 集成。</span><span class="sxs-lookup"><span data-stu-id="5f630-146">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="5f630-147">了解有关此集成的更多信息</span><span class="sxs-lookup"><span data-stu-id="5f630-147">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="5f630-148">关闭 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="5f630-148">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="5f630-149">要停止使用 Microsoft 威胁防护，请转到 Microsoft 365 安全中心中的“**设置**” > “**Microsoft 威胁防护**” > “**选择加入/选择退出**”。</span><span class="sxs-lookup"><span data-stu-id="5f630-149">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="5f630-150">取消选择 **"打开 Microsoft 威胁防护**" 并应用更改。</span><span class="sxs-lookup"><span data-stu-id="5f630-150">Unselect **Turn on Microsoft Threat Protection** and apply the changes.</span></span>

<span data-ttu-id="5f630-151">将从 Microsoft 365 安全中心删除相应的功能。</span><span class="sxs-lookup"><span data-stu-id="5f630-151">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="5f630-152">获取帮助</span><span class="sxs-lookup"><span data-stu-id="5f630-152">Get assistance</span></span>

<span data-ttu-id="5f630-153">若要获取有关启用 Microsoft 威胁防护的最常见问题的解答，请[阅读 FAQ](mtp-enable-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="5f630-153">To get answers to the most commonly asked questions about turning on Microsoft Threat Protection, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="5f630-154">Microsoft 支持人员可帮助设置或取消设置或取消设置租户上的服务和相关资源。</span><span class="sxs-lookup"><span data-stu-id="5f630-154">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="5f630-155">若要获取帮助，请在 Microsoft 365 安全中心中选择 **"需要帮助？** "。</span><span class="sxs-lookup"><span data-stu-id="5f630-155">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="5f630-156">联系支持时，请提及 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="5f630-156">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5f630-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="5f630-157">Related topics</span></span>

- [<span data-ttu-id="5f630-158">常见问题</span><span class="sxs-lookup"><span data-stu-id="5f630-158">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="5f630-159">许可要求和其他先决条件</span><span class="sxs-lookup"><span data-stu-id="5f630-159">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="5f630-160">部署支持的服务</span><span class="sxs-lookup"><span data-stu-id="5f630-160">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="5f630-161">Microsoft 威胁防护概述</span><span class="sxs-lookup"><span data-stu-id="5f630-161">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="5f630-162">Microsoft Defender ATP 概述</span><span class="sxs-lookup"><span data-stu-id="5f630-162">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="5f630-163">Office 365 ATP 概述</span><span class="sxs-lookup"><span data-stu-id="5f630-163">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="5f630-164">Microsoft Cloud App Security 概述</span><span class="sxs-lookup"><span data-stu-id="5f630-164">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="5f630-165">Azure ATP 概述</span><span class="sxs-lookup"><span data-stu-id="5f630-165">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="5f630-166">Microsoft Defender ATP 数据存储</span><span class="sxs-lookup"><span data-stu-id="5f630-166">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)