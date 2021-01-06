---
title: 在 Microsoft 365 安全中心打开 Microsoft 365 Defender
description: 了解如何启用 Microsoft 365 Defender 并开始集成安全事件和响应。
keywords: 入门， 启用 MTP， Microsoft 威胁防护， M365， 安全性， 数据位置， 所需权限， 许可证资格， 设置页面
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
ms.openlocfilehash: b052f70c1b618adef12c4f70c2b3fe55741697d5
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760502"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="0b71c-104">打开 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b71c-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0b71c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0b71c-105">**Applies to:**</span></span>
- <span data-ttu-id="0b71c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b71c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0b71c-107">[Microsoft 365 Defender](microsoft-threat-protection.md) 通过集成 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 和 Microsoft Defender for Identity 的关键功能来统一事件响应流程。</span><span class="sxs-lookup"><span data-stu-id="0b71c-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="0b71c-108">这种统一的体验增加了可在 Microsoft 365 安全中心访问的强大功能。</span><span class="sxs-lookup"><span data-stu-id="0b71c-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="0b71c-109">当具有所需权限的合格客户访问 Microsoft 365 安全中心时，Microsoft 365 Defender 将自动打开。</span><span class="sxs-lookup"><span data-stu-id="0b71c-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="0b71c-110">阅读本文以了解各种先决条件以及如何预配 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="0b71c-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="0b71c-111">检查许可证资格和所需权限</span><span class="sxs-lookup"><span data-stu-id="0b71c-111">Check license eligibility and required permissions</span></span>

<span data-ttu-id="0b71c-112">Microsoft 365 安全产品的许可证通常授权你在 Microsoft 365 安全中心内使用 Microsoft 365 Defender，而无需额外的许可费用。</span><span class="sxs-lookup"><span data-stu-id="0b71c-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="0b71c-113">我们建议获取 Microsoft 365 E5、E5 安全、A5 或 A5 安全许可证或提供所有支持服务访问权限的有效许可证组合。</span><span class="sxs-lookup"><span data-stu-id="0b71c-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="0b71c-114">有关详细的许可信息， [请阅读许可要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="0b71c-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="0b71c-115">检查角色</span><span class="sxs-lookup"><span data-stu-id="0b71c-115">Check your role</span></span>

<span data-ttu-id="0b71c-116">你必须是 **Azure** Active Directory 中的全局管理员或安全管理员才能启用 Microsoft 365 Defender。 </span><span class="sxs-lookup"><span data-stu-id="0b71c-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="0b71c-117">在 Azure AD 中查看角色</span><span class="sxs-lookup"><span data-stu-id="0b71c-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="0b71c-118">支持的服务</span><span class="sxs-lookup"><span data-stu-id="0b71c-118">Supported services</span></span>

<span data-ttu-id="0b71c-119">Microsoft 365 Defender 聚合已部署的各种受支持服务的数据。</span><span class="sxs-lookup"><span data-stu-id="0b71c-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="0b71c-120">它将集中处理和存储数据，以确定新的见解，并可能实现集中响应工作流。</span><span class="sxs-lookup"><span data-stu-id="0b71c-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="0b71c-121">这样做不会影响现有部署、设置或与集成服务关联的数据。</span><span class="sxs-lookup"><span data-stu-id="0b71c-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="0b71c-122">为了获得最佳保护并优化 Microsoft 365 Defender，我们建议在你的网络上部署所有适用的受支持服务。</span><span class="sxs-lookup"><span data-stu-id="0b71c-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="0b71c-123">有关详细信息，请阅读 [有关部署受支持的服务的信息](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="0b71c-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="0b71c-124">启动服务之前</span><span class="sxs-lookup"><span data-stu-id="0b71c-124">Before starting the service</span></span>

<span data-ttu-id="0b71c-125">在打开该服务之前，当你从导航窗格中选择事件、操作中心或搜寻时，Microsoft 365 安全中心 ([security.microsoft.com](https://security.microsoft.com)) 会显示 Microsoft 365 Defender 设置页。 </span><span class="sxs-lookup"><span data-stu-id="0b71c-125">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="0b71c-126">如果你不符合使用 Microsoft 365 Defender 条件，将不会显示这些导航项。</span><span class="sxs-lookup"><span data-stu-id="0b71c-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="0b71c-127">![如果 Microsoft 365 Defender 尚未在 Microsoft 365 安全中心中打开 ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365 Defender 设置，则显示 Microsoft 365 Defender 设置页面的图像*</span><span class="sxs-lookup"><span data-stu-id="0b71c-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="0b71c-128">启动服务</span><span class="sxs-lookup"><span data-stu-id="0b71c-128">Starting the service</span></span>

<span data-ttu-id="0b71c-129">若要打开 Microsoft 365 Defender，只需选择" **打开 Microsoft 365 Defender"** 并应用更改。</span><span class="sxs-lookup"><span data-stu-id="0b71c-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="0b71c-130">您还可以通过在导航窗格中选择"设置 (security.microsoft.com/settings) ，然后选择 **Microsoft 365 Defender。**  [](https://security.microsoft.com/settings)</span><span class="sxs-lookup"><span data-stu-id="0b71c-130">You can also access this option by selecting **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

> [!NOTE]
> <span data-ttu-id="0b71c-131">如果在 **导航窗格中看不到** "设置"或无法访问页面，请检查您的权限和许可证。</span><span class="sxs-lookup"><span data-stu-id="0b71c-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="0b71c-132">数据中心位置</span><span class="sxs-lookup"><span data-stu-id="0b71c-132">Data center location</span></span>

<span data-ttu-id="0b71c-133">Microsoft 365 Defender 将在 Microsoft [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)使用的相同位置存储和处理数据。</span><span class="sxs-lookup"><span data-stu-id="0b71c-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="0b71c-134">如果你没有 Microsoft Defender for Endpoint，则根据活动的 Microsoft 365 安全服务的位置自动选择新的数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="0b71c-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="0b71c-135">所选数据中心位置将显示在屏幕中。</span><span class="sxs-lookup"><span data-stu-id="0b71c-135">The selected data center location is shown in the screen.</span></span>

<span data-ttu-id="0b71c-136">选择 **"需要帮助"？** 在 Microsoft 365 安全中心中，联系 Microsoft 支持人员，以在不同数据中心位置预配 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="0b71c-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span>

> [!NOTE]
> <span data-ttu-id="0b71c-137">Microsoft Defender for Endpoint 在通过 Azure Defender 打开 (欧盟) 中自动设置。</span><span class="sxs-lookup"><span data-stu-id="0b71c-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="0b71c-138">Microsoft 365 Defender 将自动在相同的欧盟数据中心中为已为此终结点预配 Defender 的客户进行预配。</span><span class="sxs-lookup"><span data-stu-id="0b71c-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="0b71c-139">确认服务已开启</span><span class="sxs-lookup"><span data-stu-id="0b71c-139">Confirm that the service is on</span></span>

<span data-ttu-id="0b71c-140">设置服务后，它将添加：</span><span class="sxs-lookup"><span data-stu-id="0b71c-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="0b71c-141">事件管理</span><span class="sxs-lookup"><span data-stu-id="0b71c-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="0b71c-142">用于管理[自动调查和响应](mtp-autoir.md)的操作中心</span><span class="sxs-lookup"><span data-stu-id="0b71c-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="0b71c-143">[高级搜寻](advanced-hunting-overview.md) 功能</span><span class="sxs-lookup"><span data-stu-id="0b71c-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="0b71c-144">![包含 Microsoft 365 Defender 的 Microsoft 365 安全中心导航窗格的图像，其中 Microsoft 365 安全中心具有事件管理和其他 ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Defender 功能*</span><span class="sxs-lookup"><span data-stu-id="0b71c-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="0b71c-145">获取 Microsoft Defender for Identity 数据</span><span class="sxs-lookup"><span data-stu-id="0b71c-145">Getting Microsoft Defender for Identity data</span></span>

<span data-ttu-id="0b71c-146">若要与 Microsoft 365 Defender 共享 Microsoft Defender 的标识数据，请确保 Microsoft Cloud App Security 和 Microsoft Defender for Identity 集成已打开。</span><span class="sxs-lookup"><span data-stu-id="0b71c-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> <span data-ttu-id="0b71c-147">[详细了解此集成](https://docs.microsoft.com/cloud-app-security/mdi-integration)。</span><span class="sxs-lookup"><span data-stu-id="0b71c-147">[Learn more about this integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="get-assistance"></a><span data-ttu-id="0b71c-148">获取帮助</span><span class="sxs-lookup"><span data-stu-id="0b71c-148">Get assistance</span></span>

<span data-ttu-id="0b71c-149">若要获取有关打开 Microsoft 365 Defender 的最常见问题的答案，请阅读 [常见问题](mtp-enable-faq.md)解答。</span><span class="sxs-lookup"><span data-stu-id="0b71c-149">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="0b71c-150">Microsoft 支持人员可帮助预配或取消设置租户上的服务和相关资源。</span><span class="sxs-lookup"><span data-stu-id="0b71c-150">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="0b71c-151">For assistance， select **Need help？** in the Microsoft 365 security center.</span><span class="sxs-lookup"><span data-stu-id="0b71c-151">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="0b71c-152">联系支持人员时，请提及 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="0b71c-152">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0b71c-153">相关主题</span><span class="sxs-lookup"><span data-stu-id="0b71c-153">Related topics</span></span>

- [<span data-ttu-id="0b71c-154">常见问题</span><span class="sxs-lookup"><span data-stu-id="0b71c-154">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="0b71c-155">许可要求和其他先决条件</span><span class="sxs-lookup"><span data-stu-id="0b71c-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="0b71c-156">部署支持的服务</span><span class="sxs-lookup"><span data-stu-id="0b71c-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="0b71c-157">Microsoft 365 Defender 概述</span><span class="sxs-lookup"><span data-stu-id="0b71c-157">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="0b71c-158">Microsoft Defender for Endpoint 概述</span><span class="sxs-lookup"><span data-stu-id="0b71c-158">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="0b71c-159">Defender for Office 365 概述</span><span class="sxs-lookup"><span data-stu-id="0b71c-159">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="0b71c-160">Microsoft Cloud App Security 概述</span><span class="sxs-lookup"><span data-stu-id="0b71c-160">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="0b71c-161">Microsoft Defender for Identity 概述</span><span class="sxs-lookup"><span data-stu-id="0b71c-161">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="0b71c-162">适用于终结点数据存储的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0b71c-162">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
