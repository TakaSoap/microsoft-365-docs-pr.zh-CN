---
title: 打开Microsoft 365 Defender安全Microsoft 365中的安全中心
description: 了解如何启用安全Microsoft 365 Defender开始集成安全事件和响应。
keywords: 入门， 启用 Microsoft 365 Defender， Microsoft 365 Defender， M365， 安全性， 数据位置， 所需权限， 许可证资格， 设置页面
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
ms.openlocfilehash: 102666834562d0576920c746842582c2870b3738
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007605"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="fce62-104">打开 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fce62-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fce62-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="fce62-105">**Applies to:**</span></span>
- <span data-ttu-id="fce62-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fce62-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="fce62-107">[Microsoft 365 Defender](microsoft-365-defender.md)集成 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 和 Microsoft Defender for Identity 的关键功能，统一事件响应流程。</span><span class="sxs-lookup"><span data-stu-id="fce62-107">[Microsoft 365 Defender](microsoft-365-defender.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="fce62-108">这种统一的体验增加了可在 Microsoft 365 安全中心访问的强大功能。</span><span class="sxs-lookup"><span data-stu-id="fce62-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="fce62-109">Microsoft 365 Defender具有所需权限的合格客户访问安全中心时，Microsoft 365启用。</span><span class="sxs-lookup"><span data-stu-id="fce62-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="fce62-110">阅读本文，了解各种先决条件以及如何Microsoft 365 Defender配置。</span><span class="sxs-lookup"><span data-stu-id="fce62-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="fce62-111">检查许可证资格和所需权限</span><span class="sxs-lookup"><span data-stu-id="fce62-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="fce62-112">安全产品的许可证Microsoft 365你有权在安全Microsoft 365 Defender Microsoft 365使用许可证，而无需支付额外的许可费用。</span><span class="sxs-lookup"><span data-stu-id="fce62-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="fce62-113">我们建议获取一个Microsoft 365 E5、E5 安全、A5 或 A5 安全许可证，或提供访问所有受支持的服务的有效许可证组合。</span><span class="sxs-lookup"><span data-stu-id="fce62-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="fce62-114">有关许可的详细信息， [请阅读许可要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="fce62-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="fce62-115">检查角色</span><span class="sxs-lookup"><span data-stu-id="fce62-115">Check your role</span></span>

<span data-ttu-id="fce62-116">您必须是 **全局管理员** 或安全管理员Azure Active Directory才能启用Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="fce62-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="fce62-117">在 Azure AD 中查看角色</span><span class="sxs-lookup"><span data-stu-id="fce62-117">View your roles in Azure AD</span></span>](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="fce62-118">支持的服务</span><span class="sxs-lookup"><span data-stu-id="fce62-118">Supported services</span></span>

<span data-ttu-id="fce62-119">Microsoft 365 Defender聚合已部署的各种受支持服务的数据。</span><span class="sxs-lookup"><span data-stu-id="fce62-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="fce62-120">它将集中处理和存储数据，以确定新的见解，并尽可能使用集中式响应工作流。</span><span class="sxs-lookup"><span data-stu-id="fce62-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="fce62-121">它这样做不会影响与集成服务关联的现有部署、设置或数据。</span><span class="sxs-lookup"><span data-stu-id="fce62-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="fce62-122">为了获得最佳保护并优化Microsoft 365 Defender，我们建议在你的网络上部署所有适用的受支持服务。</span><span class="sxs-lookup"><span data-stu-id="fce62-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="fce62-123">有关详细信息，请阅读 [有关部署受支持的服务的信息](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="fce62-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="onboard-to-the-service"></a><span data-ttu-id="fce62-124">载入到服务</span><span class="sxs-lookup"><span data-stu-id="fce62-124">Onboard to the service</span></span>
<span data-ttu-id="fce62-125">载入Microsoft 365 Defender非常简单。</span><span class="sxs-lookup"><span data-stu-id="fce62-125">Onboarding to Microsoft 365 Defender is simple.</span></span> <span data-ttu-id="fce62-126">从导航菜单中，选择任何项目，如事件&**警报、搜寻**、操作中心或威胁分析，以启动载入过程。 </span><span class="sxs-lookup"><span data-stu-id="fce62-126">From the navigation menu, select any item, such as **Incidents & alerts**, **Hunting**, **Action center**, or **Threat analytics** to initiate the onboarding process.</span></span> 

### <a name="data-center-location"></a><span data-ttu-id="fce62-127">数据中心位置</span><span class="sxs-lookup"><span data-stu-id="fce62-127">Data center location</span></span>

<span data-ttu-id="fce62-128">Microsoft 365 Defender将在 Microsoft Defender for Endpoint 使用的相同位置[存储和处理数据](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。</span><span class="sxs-lookup"><span data-stu-id="fce62-128">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="fce62-129">如果你没有 Microsoft Defender for Endpoint，则根据活动安全服务的位置自动选择Microsoft 365位置。</span><span class="sxs-lookup"><span data-stu-id="fce62-129">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="fce62-130">所选数据中心位置将显示在屏幕中。</span><span class="sxs-lookup"><span data-stu-id="fce62-130">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="fce62-131">在 **安全中心选择**"需要帮助Microsoft 365联系 Microsoft 支持人员，Microsoft 365 Defender不同的数据中心位置预配服务。</span><span class="sxs-lookup"><span data-stu-id="fce62-131">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="fce62-132">过去，Microsoft Defender for Endpoint 在通过 Azure Defender (欧盟) 数据中心自动预配。</span><span class="sxs-lookup"><span data-stu-id="fce62-132">In the past, Microsoft Defender for Endpoint automatically provisioned in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="fce62-133">Microsoft 365 Defender将在同一欧盟数据中心为过去以此方式预配 Defender for Endpoint 的客户自动预配。</span><span class="sxs-lookup"><span data-stu-id="fce62-133">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner in the past.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="fce62-134">确认服务已开启</span><span class="sxs-lookup"><span data-stu-id="fce62-134">Confirm that the service is on</span></span>

<span data-ttu-id="fce62-135">设置服务后，它将添加：</span><span class="sxs-lookup"><span data-stu-id="fce62-135">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="fce62-136">事件管理</span><span class="sxs-lookup"><span data-stu-id="fce62-136">Incidents management</span></span>](incidents-overview.md)
- [<span data-ttu-id="fce62-137">警报队列</span><span class="sxs-lookup"><span data-stu-id="fce62-137">Alerts queue</span></span>](investigate-alerts.md)
- <span data-ttu-id="fce62-138">用于管理[自动调查和响应](m365d-autoir.md)的操作中心</span><span class="sxs-lookup"><span data-stu-id="fce62-138">An action center for managing [automated investigation and response](m365d-autoir.md)</span></span>
- <span data-ttu-id="fce62-139">[高级搜寻](advanced-hunting-overview.md) 功能</span><span class="sxs-lookup"><span data-stu-id="fce62-139">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>
- <span data-ttu-id="fce62-140">威胁分析</span><span class="sxs-lookup"><span data-stu-id="fce62-140">Threat analytics</span></span>

<span data-ttu-id="fce62-141">![安全Microsoft 365导航窗格的图像，Microsoft 365 Defender事件Microsoft 365和其他安全中心功能的安全 ](../../media/overview-incident.png)
 *Microsoft 365 Defender窗格*</span><span class="sxs-lookup"><span data-stu-id="fce62-141">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/overview-incident.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="fce62-142">获取 Microsoft Defender for Identity 数据</span><span class="sxs-lookup"><span data-stu-id="fce62-142">Getting Microsoft Defender for Identity data</span></span> 
<span data-ttu-id="fce62-143">若要启用与Microsoft Cloud App Security集成，至少需要登录Microsoft Cloud App Security登录一次。</span><span class="sxs-lookup"><span data-stu-id="fce62-143">To enable the integration with Microsoft Cloud App Security, you'll need to login to the Microsoft Cloud App Security at least once.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="fce62-144">获取帮助</span><span class="sxs-lookup"><span data-stu-id="fce62-144">Get assistance</span></span>

<span data-ttu-id="fce62-145">若要获取有关打开"打开"的最常见问题的解答，Microsoft 365 Defender[常见问题解答](m365d-enable-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="fce62-145">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](m365d-enable-faq.md).</span></span>

<span data-ttu-id="fce62-146">Microsoft 支持人员可帮助在租户上设置或取消设置服务和相关资源。</span><span class="sxs-lookup"><span data-stu-id="fce62-146">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="fce62-147">为获得 **帮助，请选择** 安全中心Microsoft 365需要帮助？"。</span><span class="sxs-lookup"><span data-stu-id="fce62-147">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="fce62-148">联系支持人员时，请提及Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="fce62-148">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fce62-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="fce62-149">Related topics</span></span>

- [<span data-ttu-id="fce62-150">常见问题</span><span class="sxs-lookup"><span data-stu-id="fce62-150">Frequently asked questions</span></span>](m365d-enable-faq.md)
- [<span data-ttu-id="fce62-151">许可要求和其他先决条件</span><span class="sxs-lookup"><span data-stu-id="fce62-151">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="fce62-152">部署支持的服务</span><span class="sxs-lookup"><span data-stu-id="fce62-152">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="fce62-153">Microsoft 365 Defender概述</span><span class="sxs-lookup"><span data-stu-id="fce62-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="fce62-154">Microsoft Defender for Endpoint 概述</span><span class="sxs-lookup"><span data-stu-id="fce62-154">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="fce62-155">Defender for Office 365 概述</span><span class="sxs-lookup"><span data-stu-id="fce62-155">Defender for Office 365 overview</span></span>](../office-365-security/defender-for-office-365.md)
- [<span data-ttu-id="fce62-156">Microsoft Cloud App Security 概述</span><span class="sxs-lookup"><span data-stu-id="fce62-156">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="fce62-157">Microsoft Defender for Identity 概述</span><span class="sxs-lookup"><span data-stu-id="fce62-157">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="fce62-158">Microsoft Defender for Endpoint 数据存储</span><span class="sxs-lookup"><span data-stu-id="fce62-158">Microsoft Defender for Endpoint data storage</span></span>](../defender-endpoint/data-storage-privacy.md)
