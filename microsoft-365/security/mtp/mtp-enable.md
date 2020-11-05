---
title: 在 Microsoft 365 安全中心启用 Microsoft 365 Defender
description: 了解如何启用 Microsoft 365 Defender 并开始集成安全事件和响应。
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
ms.openlocfilehash: c5b8cae9e4eabcb2b3c6a7eb76971784193a221d
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920498"
---
# <a name="turn-on-microsoft-365-defender"></a><span data-ttu-id="22975-104">打开 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22975-104">Turn on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="22975-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="22975-105">**Applies to:**</span></span>
- <span data-ttu-id="22975-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22975-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="22975-107">[Microsoft 365 Defender](microsoft-threat-protection.md) 通过在 microsoft Defender for Endpoint、microsoft Defender for Office 365、Microsoft 云应用安全性和 microsoft Defender for Identity 中集成关键功能，统一了你的事件响应过程。</span><span class="sxs-lookup"><span data-stu-id="22975-107">[Microsoft 365 Defender](microsoft-threat-protection.md) unifies your incident response process by integrating key capabilities across Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="22975-108">这种统一的体验增加了可在 Microsoft 365 安全中心访问的强大功能。</span><span class="sxs-lookup"><span data-stu-id="22975-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="22975-109">Microsoft 365 Defender 在具有所需权限的符合条件的客户访问 Microsoft 365 安全中心时自动启用。</span><span class="sxs-lookup"><span data-stu-id="22975-109">Microsoft 365 Defender automatically turns on when eligible customers with the required permissions visit Microsoft 365 security center.</span></span> <span data-ttu-id="22975-110">阅读本文以了解各种先决条件以及如何设置 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="22975-110">Read this article to understand various prerequisites and how Microsoft 365 Defender is provisioned.</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="22975-111">检查许可证资格和必需权限</span><span class="sxs-lookup"><span data-stu-id="22975-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="22975-112">Microsoft 365 安全产品的许可证通常使您能够在 Microsoft 365 安全中心使用 Microsoft 365 Defender，而无需额外的许可费用。</span><span class="sxs-lookup"><span data-stu-id="22975-112">A license to a Microsoft 365 security product generally entitles you to use Microsoft 365 Defender in Microsoft 365 security center without additional licensing cost.</span></span> <span data-ttu-id="22975-113">我们建议获取 Microsoft 365 E5、E5、E5 或 A5 安全许可证或有效的许可证组合，以提供对所有支持的服务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="22975-113">We do recommend getting a Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses that provides access to all supported services.</span></span>

<span data-ttu-id="22975-114">有关许可的详细信息，请 [阅读许可要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="22975-114">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="22975-115">检查你的角色</span><span class="sxs-lookup"><span data-stu-id="22975-115">Check your role</span></span>
<span data-ttu-id="22975-116">您必须是 **全局管理员** 或 Azure Active Directory 中的 **安全管理员** 才能打开 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="22975-116">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> [<span data-ttu-id="22975-117">在 Azure AD 中查看你的角色</span><span class="sxs-lookup"><span data-stu-id="22975-117">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a><span data-ttu-id="22975-118">支持的服务</span><span class="sxs-lookup"><span data-stu-id="22975-118">Supported services</span></span>
<span data-ttu-id="22975-119">Microsoft 365 Defender 聚合来自您已部署的各种受支持服务的数据。</span><span class="sxs-lookup"><span data-stu-id="22975-119">Microsoft 365 Defender aggregates data from the various supported services that you've already deployed.</span></span> <span data-ttu-id="22975-120">它将集中处理和存储数据，以确定新的见解并使集中响应工作流成为可能。</span><span class="sxs-lookup"><span data-stu-id="22975-120">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span> <span data-ttu-id="22975-121">这样做不会影响与集成服务关联的现有部署、设置或数据。</span><span class="sxs-lookup"><span data-stu-id="22975-121">It does this without affecting existing deployments, settings, or data associated with the integrated services.</span></span>

<span data-ttu-id="22975-122">若要获得最佳保护并优化 Microsoft 365 Defender，建议在网络上部署所有适用的受支持的服务。</span><span class="sxs-lookup"><span data-stu-id="22975-122">To get the best protection and optimize Microsoft 365 Defender, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="22975-123">有关详细信息，请 [参阅部署支持的服务](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="22975-123">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="before-starting-the-service"></a><span data-ttu-id="22975-124">启动服务之前</span><span class="sxs-lookup"><span data-stu-id="22975-124">Before starting the service</span></span>
<span data-ttu-id="22975-125">在打开服务之前，Microsoft 365 安全中心 ( [security.microsoft.com](https://security.microsoft.com)) 在选择 " **事件** "、" **操作中心** " 或 "导航窗格" 中的 " **搜寻** " 时显示 "microsoft 365 Defender 设置" 页。</span><span class="sxs-lookup"><span data-stu-id="22975-125">Before you turn on the service, the Microsoft 365 security center ( [security.microsoft.com](https://security.microsoft.com)) shows the Microsoft 365 Defender settings page when you select **Incidents** , **Action center** , or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="22975-126">如果你不符合使用 Microsoft 365 Defender 的资格，则不会显示这些导航项。</span><span class="sxs-lookup"><span data-stu-id="22975-126">These navigation items are not shown if you are not eligible to use Microsoft 365 Defender.</span></span>

<span data-ttu-id="22975-127">![Microsoft 365 Defender ](../../media/mtp-enable/mtp-settings.png)
 *在 microsoft 365 安全中心中未启用 Microsoft 365 defender 设置* 时显示的 microsoft 365 defender 设置页面的图像</span><span class="sxs-lookup"><span data-stu-id="22975-127">![Image of the Microsoft 365 Defender settings page shown if Microsoft 365 Defender has not been turned on](../../media/mtp-enable/mtp-settings.png)
*Microsoft 365 Defender settings in Microsoft 365 security center*</span></span>

## <a name="starting-the-service"></a><span data-ttu-id="22975-128">启动服务</span><span class="sxs-lookup"><span data-stu-id="22975-128">Starting the service</span></span>
<span data-ttu-id="22975-129">若要打开 Microsoft 365 Defender，只需选择 **"打开 microsoft 365 defender** " 并应用更改。</span><span class="sxs-lookup"><span data-stu-id="22975-129">To turn on Microsoft 365 Defender, simply select **Turn on Microsoft 365 Defender** and apply the change.</span></span> <span data-ttu-id="22975-130">您还可以通过在导航窗格中选择 " **设置** " ( [security.microsoft.com/settings](https://security.microsoft.com/settings)) ，然后选择 " **microsoft 365 Defender** " 来访问此选项。</span><span class="sxs-lookup"><span data-stu-id="22975-130">You can also access this option by selecting **Settings** ( [security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and then selecting **Microsoft 365 Defender**.</span></span>

>[!NOTE]
><span data-ttu-id="22975-131">如果在导航窗格中看不到 **设置** 或无法访问页面，请检查您的权限和许可证。</span><span class="sxs-lookup"><span data-stu-id="22975-131">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="data-center-location"></a><span data-ttu-id="22975-132">数据中心位置</span><span class="sxs-lookup"><span data-stu-id="22975-132">Data center location</span></span>
<span data-ttu-id="22975-133">Microsoft 365 Defender 将存储和处理 [Microsoft Defender For Endpoint 使用的相同位置](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)中的数据。</span><span class="sxs-lookup"><span data-stu-id="22975-133">Microsoft 365 Defender will store and process data in the [same location used by Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="22975-134">如果没有 Microsoft Defender for Endpoint，将根据活动的 Microsoft 365 安全服务的位置自动选择新的数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="22975-134">If you don't have Microsoft Defender for Endpoint, a new data center location is automatically selected based on the location of active Microsoft 365 security services.</span></span> <span data-ttu-id="22975-135">屏幕上显示了所选的数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="22975-135">The selected data center location is shown in the screen.</span></span> 

<span data-ttu-id="22975-136">在 Microsoft 365 安全中心中选择 **"需要帮助？** "，以联系 microsoft 支持部门，了解如何在其他数据中心位置设置 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="22975-136">Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.</span></span> 

>[!NOTE]
><span data-ttu-id="22975-137">Microsoft Defender for Endpoint 在欧洲联合 (EU 通过 Azure Defender 打开时自动设置) 数据中心。</span><span class="sxs-lookup"><span data-stu-id="22975-137">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="22975-138">对于以这种方式为终结点预配了 Defender 的客户，Microsoft 365 Defender 将自动在相同的欧盟数据中心中进行预配。</span><span class="sxs-lookup"><span data-stu-id="22975-138">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Defender for Endpoint in this manner.</span></span> 

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="22975-139">确认服务已开启</span><span class="sxs-lookup"><span data-stu-id="22975-139">Confirm that the service is on</span></span>
<span data-ttu-id="22975-140">设置服务后，它将添加：</span><span class="sxs-lookup"><span data-stu-id="22975-140">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="22975-141">事件管理</span><span class="sxs-lookup"><span data-stu-id="22975-141">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="22975-142">用于管理[自动调查和响应](mtp-autoir.md)的操作中心</span><span class="sxs-lookup"><span data-stu-id="22975-142">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="22975-143">[高级搜寻](advanced-hunting-overview.md) 功能</span><span class="sxs-lookup"><span data-stu-id="22975-143">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="22975-144">![Microsoft 365 Defender 功能的 Microsoft 365 security center 导航窗格的图像 ](../../media/mtp-enable/mtp-on.png)
 *microsoft 365 安全中心与事件管理和其他 Microsoft 365 功能*</span><span class="sxs-lookup"><span data-stu-id="22975-144">![Image of Microsoft 365 security center navigation pane with Microsoft 365 Defender features](../../media/mtp-enable/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft 365 Defender capabilities*</span></span>

### <a name="getting-microsoft-defender-for-identity-data"></a><span data-ttu-id="22975-145">获取用于标识数据的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="22975-145">Getting Microsoft Defender for Identity data</span></span>
<span data-ttu-id="22975-146">若要与 Microsoft 365 Defender 共享 Microsoft Defender 的标识数据，请确保 Microsoft 云应用安全性和 Microsoft Defender for Identity integration 已打开。</span><span class="sxs-lookup"><span data-stu-id="22975-146">To share Microsoft Defender for Identity data with Microsoft 365 Defender, ensure that Microsoft Cloud App Security and Microsoft Defender for Identity integration is turned on.</span></span> [<span data-ttu-id="22975-147">了解有关此集成的更多信息</span><span class="sxs-lookup"><span data-stu-id="22975-147">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-365-defender"></a><span data-ttu-id="22975-148">关闭 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22975-148">Turn off Microsoft 365 Defender</span></span>
<span data-ttu-id="22975-149">若要停止使用 microsoft 365 defender，请 **Settings** 转到 microsoft  >  365 安全中心中的设置 **microsoft 365 Defender**  >  **自愿加入/自愿退出** 。</span><span class="sxs-lookup"><span data-stu-id="22975-149">To stop using Microsoft 365 Defender, go to **Settings** > **Microsoft 365 Defender** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="22975-150">取消选择 **"打开 Microsoft 365 Defender** 并应用更改"。</span><span class="sxs-lookup"><span data-stu-id="22975-150">Unselect **Turn on Microsoft 365 Defender** and apply the changes.</span></span>

<span data-ttu-id="22975-151">将从 Microsoft 365 安全中心删除相应的功能。</span><span class="sxs-lookup"><span data-stu-id="22975-151">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="22975-152">获取帮助</span><span class="sxs-lookup"><span data-stu-id="22975-152">Get assistance</span></span>

<span data-ttu-id="22975-153">若要获取有关启用 Microsoft 365 Defender 的最常见问题的解答，请 [阅读 FAQ](mtp-enable-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="22975-153">To get answers to the most commonly asked questions about turning on Microsoft 365 Defender, [read the FAQ](mtp-enable-faq.md).</span></span>

<span data-ttu-id="22975-154">Microsoft 支持人员可帮助设置或取消设置或取消设置租户上的服务和相关资源。</span><span class="sxs-lookup"><span data-stu-id="22975-154">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="22975-155">若要获取帮助，请在 Microsoft 365 安全中心中选择 **"需要帮助？** "。</span><span class="sxs-lookup"><span data-stu-id="22975-155">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="22975-156">联系支持时，请注明 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="22975-156">When contacting support, mention Microsoft 365 Defender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="22975-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="22975-157">Related topics</span></span>

- [<span data-ttu-id="22975-158">常见问题</span><span class="sxs-lookup"><span data-stu-id="22975-158">Frequently asked questions</span></span>](mtp-enable-faq.md)
- [<span data-ttu-id="22975-159">许可要求和其他先决条件</span><span class="sxs-lookup"><span data-stu-id="22975-159">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="22975-160">部署支持的服务</span><span class="sxs-lookup"><span data-stu-id="22975-160">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="22975-161">Microsoft 365 Defender 概述</span><span class="sxs-lookup"><span data-stu-id="22975-161">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="22975-162">Microsoft Defender for Endpoint 概述</span><span class="sxs-lookup"><span data-stu-id="22975-162">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="22975-163">适用于 Office 的 Defender 365 概述</span><span class="sxs-lookup"><span data-stu-id="22975-163">Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="22975-164">Microsoft Cloud App Security 概述</span><span class="sxs-lookup"><span data-stu-id="22975-164">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="22975-165">Microsoft Defender for Identity 概述</span><span class="sxs-lookup"><span data-stu-id="22975-165">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="22975-166">Microsoft Defender for Endpoint data storage</span><span class="sxs-lookup"><span data-stu-id="22975-166">Microsoft Defender for Endpoint data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
