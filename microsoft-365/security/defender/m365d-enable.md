---
title: 在 Microsoft 365 安全中心打开 Microsoft 365 Defender
description: 了解如何启用 Microsoft 365 Defender 并开始集成安全事件和响应。
keywords: 入门， 启用 MTP， Microsoft 威胁防护， M365， 安全性， 数据位置， 所需权限， 许可证资格， 设置页面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 4165f13e24e1ecb53413025c59bf6f3195525b17
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056548"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="95625-104">打开 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95625-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="95625-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="95625-105">**Applies to:**</span></span>
- <span data-ttu-id="95625-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95625-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="95625-107">[Microsoft 365 Defender](microsoft-365-defender.md) 通过集成 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 和 Microsoft Defender for Identity 的关键功能来统一事件响应流程。</span><span class="sxs-lookup"><span data-stu-id="95625-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="95625-108">这种统一的体验增加了可在 Microsoft 365 安全中心访问的强大功能。</span><span class="sxs-lookup"><span data-stu-id="95625-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="95625-109">当具有所需权限的合格客户访问 Microsoft 365 安全中心时，Microsoft 365 Defender 将自动打开。</span><span class="sxs-lookup"><span data-stu-id="95625-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="95625-110">阅读本文，了解各种先决条件以及如何预配 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="95625-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="95625-111">检查许可证资格和所需权限</span><span class="sxs-lookup"><span data-stu-id="95625-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="95625-112">Microsoft 365 安全产品的许可证通常授权你在 Microsoft 365 安全中心使用 Microsoft 365 Defender，无需额外的许可费用。</span><span class="sxs-lookup"><span data-stu-id="95625-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="95625-113">我们建议获取 Microsoft 365 E5、E5 安全、A5 或 A5 安全许可证或提供所有支持服务访问权限的有效许可证组合。</span><span class="sxs-lookup"><span data-stu-id="95625-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="95625-114">有关许可的详细信息， [请阅读许可要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="95625-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="95625-115">检查角色</span><span class="sxs-lookup"><span data-stu-id="95625-115">Check your role</span></span>

<span data-ttu-id="95625-116">你必须是 **Azure** Active Directory 中的全局管理员或安全管理员才能启用 Microsoft 365 Defender。 </span><span class="sxs-lookup"><span data-stu-id="95625-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="95625-117">在 Azure AD 中查看角色</span><span class="sxs-lookup"><span data-stu-id="95625-117">View your roles in Azure AD</span></span>](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="95625-118">支持的服务</span><span class="sxs-lookup"><span data-stu-id="95625-118">Supported services</span></span>

<span data-ttu-id="95625-119">Microsoft 365 Defender 聚合已部署的各种受支持服务的数据。</span><span class="sxs-lookup"><span data-stu-id="95625-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="95625-120">它将集中处理和存储数据，以确定新的见解，并尽可能使用集中式响应工作流。</span><span class="sxs-lookup"><span data-stu-id="95625-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="95625-121">它这样做不会影响与集成服务关联的现有部署、设置或数据。</span><span class="sxs-lookup"><span data-stu-id="95625-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="95625-122">为了获得最佳保护并优化 Microsoft 365 Defender，我们建议在你的网络上部署所有适用的受支持服务。</span><span class="sxs-lookup"><span data-stu-id="95625-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="95625-123">有关详细信息，请阅读 [有关部署受支持的服务的信息](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="95625-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="onboard-to-the-service"></a><span data-ttu-id="95625-124">载入到服务</span><span class="sxs-lookup"><span data-stu-id="95625-124">Onboard to the service</span></span>
<span data-ttu-id="95625-125">载入 Microsoft 365 Defender 非常简单。</span><span class="sxs-lookup"><span data-stu-id="95625-125">Onboarding to Microsoft 365 Defender is simple.</span></span> <span data-ttu-id="95625-126">从导航菜单中，选择终结点部分下的任何项目，如事件、搜寻、操作中心或威胁分析，以启动载入过程。</span><span class="sxs-lookup"><span data-stu-id="95625-126">From the navigation menu, select any item under the Endpoints section, such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span> 

### <a name="data-center-location"></a><span data-ttu-id="95625-127">数据中心位置</span><span class="sxs-lookup"><span data-stu-id="95625-127">Data center location</span></span>

<span data-ttu-id="95625-128">Microsoft 365 Defender 将在 Microsoft Defender for Endpoint 使用的相同位置 [存储和处理数据](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。</span><span class="sxs-lookup"><span data-stu-id="95625-128">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="95625-129">如果你没有 Microsoft Defender for Endpoint，则根据活动的 Microsoft 365 安全服务的位置自动选择新的数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="95625-129">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="95625-130">所选数据中心位置将显示在屏幕中。</span><span class="sxs-lookup"><span data-stu-id="95625-130">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="95625-131">选择 **Microsoft** 365 安全中心中的"需要帮助？"，以联系 Microsoft 支持部门，了解在不同的数据中心位置预配 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="95625-131">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="95625-132">Microsoft Defender for Endpoint 在通过 Azure Defender (欧盟) 数据中心自动设置。</span><span class="sxs-lookup"><span data-stu-id="95625-132">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="95625-133">Microsoft 365 Defender 将自动在相同的欧盟数据中心中为已使用此方式预配终结点的 Defender 的客户进行预配。</span><span class="sxs-lookup"><span data-stu-id="95625-133">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="95625-134">确认服务已开启</span><span class="sxs-lookup"><span data-stu-id="95625-134">Confirm that the service is on</span></span>

<span data-ttu-id="95625-135">设置服务后，它将添加：</span><span class="sxs-lookup"><span data-stu-id="95625-135">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="95625-136">事件管理</span><span class="sxs-lookup"><span data-stu-id="95625-136">Incidents management</span></span>](incidents-overview.md)
- [<span data-ttu-id="95625-137">警报队列</span><span class="sxs-lookup"><span data-stu-id="95625-137">Alerts queue</span></span>](investigate-alerts.md)
- <span data-ttu-id="95625-138">用于管理[自动调查和响应](m365d-autoir.md)的操作中心</span><span class="sxs-lookup"><span data-stu-id="95625-138">An action center for managing [automated investigation and response](m365d-autoir.md)</span></span>
- <span data-ttu-id="95625-139">[高级搜寻](advanced-hunting-overview.md) 功能</span><span class="sxs-lookup"><span data-stu-id="95625-139">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>
- <span data-ttu-id="95625-140">威胁分析</span><span class="sxs-lookup"><span data-stu-id="95625-140">Threat analytics</span></span>

<span data-ttu-id="95625-141">![包含 Microsoft 365 Defender 功能的 Microsoft 365 安全中心导航窗格的图像，包含事件管理和其他 ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Defender 功能*</span><span class="sxs-lookup"><span data-stu-id="95625-141">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="95625-142">获取 Microsoft Defender for Identity 数据</span><span class="sxs-lookup"><span data-stu-id="95625-142">Getting Microsoft Defender for Identity data</span></span> 
<span data-ttu-id="95625-143">若要启用与 Microsoft Cloud App Security 的集成，你至少需要登录到 Microsoft Cloud App Security 一次。</span><span class="sxs-lookup"><span data-stu-id="95625-143">To enable the integration with Microsoft Cloud App Security, you'll need to login to the Microsoft Cloud App Security at least once.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="95625-144">获取帮助</span><span class="sxs-lookup"><span data-stu-id="95625-144">Get assistance</span></span>

<span data-ttu-id="95625-145">若要获取有关打开 Microsoft 365 Defender 的最常见问题的答案， [请阅读常见问题](m365d-enable-faq.md)解答。</span><span class="sxs-lookup"><span data-stu-id="95625-145">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](m365d-enable-faq.md).</span></span>

<span data-ttu-id="95625-146">Microsoft 支持人员可帮助在租户上设置或取消设置服务和相关资源。</span><span class="sxs-lookup"><span data-stu-id="95625-146">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="95625-147">有关帮助 **，请选择** Microsoft 365 安全中心中的"需要帮助？"。</span><span class="sxs-lookup"><span data-stu-id="95625-147">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="95625-148">联系支持人员时，请提及 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="95625-148">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="95625-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="95625-149">Related topics</span></span>

- [<span data-ttu-id="95625-150">常见问题</span><span class="sxs-lookup"><span data-stu-id="95625-150">Frequently asked questions</span></span>](m365d-enable-faq.md)
- [<span data-ttu-id="95625-151">许可要求和其他先决条件</span><span class="sxs-lookup"><span data-stu-id="95625-151">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="95625-152">部署支持的服务</span><span class="sxs-lookup"><span data-stu-id="95625-152">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="95625-153">Microsoft 365 Defender 概述</span><span class="sxs-lookup"><span data-stu-id="95625-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="95625-154">Microsoft Defender for Endpoint 概述</span><span class="sxs-lookup"><span data-stu-id="95625-154">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-advanced-threat-protection.md)
- [<span data-ttu-id="95625-155">Defender for Office 365 概述</span><span class="sxs-lookup"><span data-stu-id="95625-155">Defender for Office 365 overview</span></span>](../defender-365-security/defender-for-office-365.md)
- [<span data-ttu-id="95625-156">Microsoft Cloud App Security 概述</span><span class="sxs-lookup"><span data-stu-id="95625-156">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="95625-157">Microsoft Defender for Identity 概述</span><span class="sxs-lookup"><span data-stu-id="95625-157">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="95625-158">Microsoft Defender for Endpoint 数据存储</span><span class="sxs-lookup"><span data-stu-id="95625-158">Microsoft Defender for Endpoint data storage</span></span>](../defender-endpoint/data-storage-privacy.md)
