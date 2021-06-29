---
title: 修复准备情况评估工具发现的问题
description: 针对工具找到的每个问题要采取的详细操作
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 0296e8151162ad4f2855fdd29ff2fc0ed4b4d6b2
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177569"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="4fb5a-104">修复准备情况评估工具发现的问题</span><span class="sxs-lookup"><span data-stu-id="4fb5a-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="4fb5a-105">对于每个检查，该工具将报告四个可能的结果之一：</span><span class="sxs-lookup"><span data-stu-id="4fb5a-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="4fb5a-106">结果</span><span class="sxs-lookup"><span data-stu-id="4fb5a-106">Result</span></span>  |<span data-ttu-id="4fb5a-107">含义</span><span class="sxs-lookup"><span data-stu-id="4fb5a-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="4fb5a-108">Ready</span><span class="sxs-lookup"><span data-stu-id="4fb5a-108">Ready</span></span>     | <span data-ttu-id="4fb5a-109">完成注册前无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="4fb5a-110">公告</span><span class="sxs-lookup"><span data-stu-id="4fb5a-110">Advisory</span></span>    | <span data-ttu-id="4fb5a-111">按照工具或本文中的步骤操作，获得注册和用户的最佳体验。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="4fb5a-112">*你可以完成* 注册，但在部署第一台设备之前必须修复这些问题。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="4fb5a-113">未就绪</span><span class="sxs-lookup"><span data-stu-id="4fb5a-113">Not ready</span></span> | <span data-ttu-id="4fb5a-114">*如果不修复这些问题，注册将失败。*</span><span class="sxs-lookup"><span data-stu-id="4fb5a-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="4fb5a-115">请按照工具或本文中的步骤进行解析。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="4fb5a-116">错误</span><span class="sxs-lookup"><span data-stu-id="4fb5a-116">Error</span></span> | <span data-ttu-id="4fb5a-117">你Azure Active Directory (AD) 角色的权限不足，无法运行此检查。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-117">The Azure Active Directory (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

> [!NOTE]
> <span data-ttu-id="4fb5a-118">此工具报告的结果仅反映设置在运行它的特定时间点的状态。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-118">The results reported by this tool reflect the status of your settings only at the specific point in time that you ran it.</span></span> <span data-ttu-id="4fb5a-119">如果您稍后对 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的策略进行了任何更改，则"就绪"的项目可能会变为"未就绪"。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-119">If you later make any changes to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, items that were "Ready" can become "Not ready."</span></span> <span data-ttu-id="4fb5a-120">若要避免与Microsoft 托管桌面问题，请在更改任何策略之前检查本文中描述的特定设置。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-120">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in this article before you change any policies.</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="4fb5a-121">Microsoft Intune设置</span><span class="sxs-lookup"><span data-stu-id="4fb5a-121">Microsoft Intune settings</span></span>

<span data-ttu-id="4fb5a-122">可以在管理中心访问 intune Microsoft Endpoint Manager[设置](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-122">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="4fb5a-123">Autopilot 部署配置文件</span><span class="sxs-lookup"><span data-stu-id="4fb5a-123">Autopilot deployment profile</span></span>

<span data-ttu-id="4fb5a-124">不应有任何面向已分配或动态组的现有 Autopilot 配置文件Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-124">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4fb5a-125">Microsoft 托管桌面 Autopilot 预配新设备。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-125">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="4fb5a-126">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-126">**Not ready**</span></span>

<span data-ttu-id="4fb5a-127">你拥有分配给所有设备的 Autopilot 配置文件。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-127">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="4fb5a-128">有关步骤，请参阅在[Intune Windows Autopilot 注册Windows设备](/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="4fb5a-129">注册Microsoft 托管桌面，设置 Autopilot 策略以排除 **现代工作区设备 -所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="4fb5a-130">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-130">**Advisory**</span></span>

<span data-ttu-id="4fb5a-131">确保你的 Autopilot 配置文件面向不包括任何设备的已分配或Microsoft 托管桌面 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-131">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4fb5a-132">有关步骤，请参阅在[Intune Windows Autopilot 注册Windows设备](/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-132">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="4fb5a-133">注册Microsoft 托管桌面，设置 Autopilot 配置文件以排除 **现代工作区设备 -所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-133">After Microsoft Managed Desktop enrollment, set your Autopilot profiles to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="4fb5a-134">证书连接器</span><span class="sxs-lookup"><span data-stu-id="4fb5a-134">Certificate connectors</span></span>

<span data-ttu-id="4fb5a-135">如果你有任何证书连接器将由你想要在 Microsoft 托管桌面 注册的设备使用，则连接器不应有任何错误。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-135">If you have any certificate connectors that will be used by the devices you want to enroll in Microsoft Managed Desktop, the connectors should not have any errors.</span></span> <span data-ttu-id="4fb5a-136">只有以下公告之一适用于你的情况，因此请仔细检查它们。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-136">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="4fb5a-137">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-137">**Advisory**</span></span>

<span data-ttu-id="4fb5a-138">不存在证书连接器。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-138">No certificate connectors are present.</span></span> <span data-ttu-id="4fb5a-139">你可能不需要任何连接器，但应评估是否需要一些连接器在 Microsoft 托管桌面 连接。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-139">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity on your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4fb5a-140">有关详细信息，请参阅准备[证书和网络配置文件Microsoft 托管桌面。](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="4fb5a-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="4fb5a-141">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-141">**Advisory**</span></span>

<span data-ttu-id="4fb5a-142">至少有一个证书连接器出现错误。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-142">At least one certificate connector has an error.</span></span> <span data-ttu-id="4fb5a-143">如果需要此连接器向设备Microsoft 托管桌面证书，则必须解决此错误。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-143">If you need this connector for providing certificates to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="4fb5a-144">有关详细信息，请参阅准备[证书和网络配置文件Microsoft 托管桌面。](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="4fb5a-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="4fb5a-145">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-145">**Advisory**</span></span>

<span data-ttu-id="4fb5a-146">您至少有一个证书连接器，并且未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-146">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="4fb5a-147">但是，在准备部署时，可能需要创建一个配置文件，以将连接器重新用于Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-147">However, in preparation for deployment, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4fb5a-148">有关详细信息，请参阅准备[证书和网络配置文件Microsoft 托管桌面。](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="4fb5a-148">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

### <a name="company-portal"></a><span data-ttu-id="4fb5a-149">公司门户</span><span class="sxs-lookup"><span data-stu-id="4fb5a-149">Company Portal</span></span>

<span data-ttu-id="4fb5a-150">Microsoft 托管桌面要求 IT 管理员使用 Intune 公司门户 为用户安装Microsoft 托管桌面服务器。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-150">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="4fb5a-151">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-151">**Not ready**</span></span>

<span data-ttu-id="4fb5a-152">您未为公司门户安装任何内容。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-152">You do not have Company Portal installed for your users.</span></span> <span data-ttu-id="4fb5a-153">购买公司门户并强制 Intune 和 适用于企业的 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-153">Purchase Company Portal and force a sync between Intune and Microsoft Store for Business.</span></span> <span data-ttu-id="4fb5a-154">有关详细信息，请参阅 Install [Intune 公司门户 on devices。](../get-started/company-portal.md)</span><span class="sxs-lookup"><span data-stu-id="4fb5a-154">For more information, see [Install Intune Company Portal on devices](../get-started/company-portal.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="4fb5a-155">条件访问策略</span><span class="sxs-lookup"><span data-stu-id="4fb5a-155">Conditional access policies</span></span>

<span data-ttu-id="4fb5a-156">条件访问策略不得Microsoft 托管桌面 Intune 和 Azure AD (Azure AD) 管理 Azure AD 组织。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-156">Conditional access policies must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>

<span data-ttu-id="4fb5a-157">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-157">**Not ready**</span></span>

<span data-ttu-id="4fb5a-158">您至少有一个面向所有用户的条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-158">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="4fb5a-159">注册期间，我们会从Microsoft 托管桌面访问策略中排除服务帐户，并应用新的条件访问策略来限制访问这些帐户。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-159">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="4fb5a-160">注册后，可以在 Microsoft 托管桌面中查看条件访问Microsoft Endpoint Manager。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-160">After enrollment, you can review the Microsoft Managed Desktop conditional access policy in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="4fb5a-161">有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-161">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="4fb5a-162">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-162">**Advisory**</span></span>

<span data-ttu-id="4fb5a-163">您具有可能会阻止用户管理 Microsoft 托管桌面服务的条件Microsoft 托管桌面策略。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-163">You have conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="4fb5a-164">注册期间，我们会从Microsoft 托管桌面访问策略中排除服务帐户，并应用新的条件访问策略来限制访问这些帐户。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-164">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="4fb5a-165">有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-165">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="4fb5a-166">**Error**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-166">**Error**</span></span>

<span data-ttu-id="4fb5a-167">Intune 管理员角色没有足够的权限进行此检查。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-167">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="4fb5a-168">还需要分配以下任一 Azure AD 角色来运行此检查：</span><span class="sxs-lookup"><span data-stu-id="4fb5a-168">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="4fb5a-169">安全读取者</span><span class="sxs-lookup"><span data-stu-id="4fb5a-169">Security Reader</span></span>
- <span data-ttu-id="4fb5a-170">安全管理员</span><span class="sxs-lookup"><span data-stu-id="4fb5a-170">Security Administrator</span></span>
- <span data-ttu-id="4fb5a-171">条件访问管理员</span><span class="sxs-lookup"><span data-stu-id="4fb5a-171">Conditional Access Administrator</span></span>
- <span data-ttu-id="4fb5a-172">全局读取者</span><span class="sxs-lookup"><span data-stu-id="4fb5a-172">Global Reader</span></span>
- <span data-ttu-id="4fb5a-173">设备管理员</span><span class="sxs-lookup"><span data-stu-id="4fb5a-173">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="4fb5a-174">设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="4fb5a-174">Device Compliance policies</span></span>

<span data-ttu-id="4fb5a-175">Azure AD 组织中 Intune 设备合规性策略可能会影响Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-175">Intune Device Compliance policies in your Azure AD organization might impact Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="4fb5a-176">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-176">**Not ready**</span></span>

<span data-ttu-id="4fb5a-177">您至少有一个面向所有用户的合规性策略。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-177">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="4fb5a-178">Microsoft 托管桌面包括面向你的设备Microsoft 托管桌面策略。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-178">Microsoft Managed Desktop includes compliance policies that will target your Microsoft Managed Desktop devices.</span></span>  <span data-ttu-id="4fb5a-179">将策略更改为面向不包含任何用户或设备Microsoft 托管桌面 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-179">Change the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users or devices.</span></span> <span data-ttu-id="4fb5a-180">有关步骤，请参阅 Create [a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-180">For steps, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="4fb5a-181">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-181">**Advisory**</span></span>

<span data-ttu-id="4fb5a-182">确保你拥有的任何合规性策略不面向任何Microsoft 托管桌面用户。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-182">Make sure that any compliance policies you have don't target any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="4fb5a-183">有关步骤，请参阅 Create [a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-183">For steps, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-profiles"></a><span data-ttu-id="4fb5a-184">设备配置文件</span><span class="sxs-lookup"><span data-stu-id="4fb5a-184">Device Configuration profiles</span></span>

<span data-ttu-id="4fb5a-185">Azure AD 组织中 Intune 设备配置文件不得面向任何 Microsoft 管理桌面设备或用户。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-185">Intune Device Configuration profiles in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="4fb5a-186">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-186">**Not ready**</span></span>

<span data-ttu-id="4fb5a-187">你至少具有一个面向所有用户和/或所有设备的配置文件。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-187">You have at least one configuration profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="4fb5a-188">将配置文件重置为面向不包括任何设备的特定 Azure AD Microsoft 托管桌面组。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-188">Reset the profile to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4fb5a-189">有关步骤，请参阅[Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-189">For steps, see [Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="4fb5a-190">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-190">**Advisory**</span></span>

<span data-ttu-id="4fb5a-191">确保你拥有的任何配置策略不包括任何Microsoft 托管桌面或用户。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-191">Make sure that any configuration policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="4fb5a-192">有关步骤，请参阅[Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-192">For steps, see [Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="4fb5a-193">设备类型限制</span><span class="sxs-lookup"><span data-stu-id="4fb5a-193">Device type restrictions</span></span>

<span data-ttu-id="4fb5a-194">Microsoft 托管桌面设备必须在 Intune 中注册。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-194">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="4fb5a-195">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-195">**Not ready**</span></span>

<span data-ttu-id="4fb5a-196">你当前至少配置了一个注册限制策略Windows Intune 中注册。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-196">You currently have at least one enrollment restriction policy configured to prevent Windows devices from enrollment in Intune.</span></span> <span data-ttu-id="4fb5a-197">按照 [为面向用户](/mem/intune/enrollment/enrollment-restrictions-set)的每个注册限制策略设置注册Microsoft 托管桌面中的步骤操作，Windows (**MDM**) 设置为 **"允许"。**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-197">Follow the steps in [Set enrollment restrictions](/mem/intune/enrollment/enrollment-restrictions-set) for each enrollment restriction policy that targets Microsoft Managed Desktop users and change the **Windows (MDM)** setting to **Allow**.</span></span> <span data-ttu-id="4fb5a-198">但是，你可以将 MDM设备上个人拥有 **Windows ()** 设置为 **阻止**。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-198">You can, however, set any **personally owned** **Windows (MDM)** devices to **Block**.</span></span> 


### <a name="enrollment-status-page"></a><span data-ttu-id="4fb5a-199">注册状态页</span><span class="sxs-lookup"><span data-stu-id="4fb5a-199">Enrollment Status Page</span></span>

<span data-ttu-id="4fb5a-200">YOU currently have the Enrollment Status Page (ESP) enabled.</span><span class="sxs-lookup"><span data-stu-id="4fb5a-200">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="4fb5a-201">如果你打算参加此功能的公共Microsoft 托管桌面预览版，可以忽略此项。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-201">If you intend to participate in the Microsoft Managed Desktop public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="4fb5a-202">有关详细信息，请参阅 [Autopilot 首次运行体验和注册状态页面](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-202">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="4fb5a-203">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-203">**Not ready**</span></span>

<span data-ttu-id="4fb5a-204">将 ESP 默认配置文件设置为"**显示应用和配置文件配置进度"。**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-204">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="4fb5a-205">通过按照设置注册状态页 中的步骤操作，禁用此设置或确保任何 Azure AD 组的工作分配不包括Microsoft 托管桌面[设备](/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-205">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="4fb5a-206">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-206">**Advisory**</span></span>

<span data-ttu-id="4fb5a-207">确保未将具有"显示应用和配置文件配置进度"设置的任何配置文件分配给任何 Azure AD 组，该组Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-207">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4fb5a-208">有关详细信息，请参阅设置 [注册状态页](/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-208">For more information, see [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="microsoft-store-for-business"></a><span data-ttu-id="4fb5a-209">适用于企业的 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="4fb5a-209">Microsoft Store for Business</span></span>

<span data-ttu-id="4fb5a-210">我们使用 适用于企业的 Microsoft Store 在 Microsoft 托管桌面 上部署 公司门户 应用，以允许用户选择安装某些应用，例如 Microsoft Project 和 Microsoft Visio (（如果允许) ）。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-210">We use Microsoft Store for Business and deploy the Company Portal app on Microsoft Managed Desktop to allow users to optionally install some apps, such as Microsoft Project and Microsoft Visio (where permitted).</span></span>

<span data-ttu-id="4fb5a-211">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-211">**Not ready**</span></span>

<span data-ttu-id="4fb5a-212">适用于企业的 Microsoft Store未启用或未与 Intune 同步。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-212">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="4fb5a-213">有关详细信息，请参阅[如何使用](/mem/intune/apps/windows-store-for-business)适用于企业的 Microsoft Store 管理批量购买的应用Microsoft Intune在设备上Intune 公司门户[购买的应用](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-213">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on devices](../get-started/company-portal.md).</span></span>

### <a name="multifactor-authentication"></a><span data-ttu-id="4fb5a-214">多重身份验证</span><span class="sxs-lookup"><span data-stu-id="4fb5a-214">Multifactor authentication</span></span>

<span data-ttu-id="4fb5a-215">多重身份验证不得阻止Microsoft 托管桌面 Intune 和 Azure AD (租户) Azure AD 组织。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-215">Multifactor authentication must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>


<span data-ttu-id="4fb5a-216">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-216">**Not ready**</span></span>

<span data-ttu-id="4fb5a-217">您具有为分配给所有用户的条件 **访问策略所需的** 一些多重身份验证策略。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-217">You have some multifactor authentication policies set as **required** for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="4fb5a-218">注册期间，我们会从Microsoft 托管桌面访问策略中排除服务帐户，并应用新的条件访问策略来限制访问这些帐户。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-218">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="4fb5a-219">有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-219">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="4fb5a-220">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-220">**Advisory**</span></span>

<span data-ttu-id="4fb5a-221">您具有条件访问策略所需的多重身份验证，这些策略Microsoft 托管桌面管理 Microsoft 托管桌面 服务。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-221">You have multifactor authentication required on conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="4fb5a-222">注册期间，我们会从Microsoft 托管桌面访问策略中排除服务帐户，并应用新的条件访问策略来限制访问这些帐户。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-222">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="4fb5a-223">有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-223">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="4fb5a-224">**Error**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-224">**Error**</span></span>

<span data-ttu-id="4fb5a-225">Intune 管理员角色没有足够的权限进行此检查。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-225">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="4fb5a-226">还需要分配以下任一 Azure AD 角色来运行此检查：</span><span class="sxs-lookup"><span data-stu-id="4fb5a-226">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="4fb5a-227">安全读取者</span><span class="sxs-lookup"><span data-stu-id="4fb5a-227">Security Reader</span></span>
- <span data-ttu-id="4fb5a-228">安全管理员</span><span class="sxs-lookup"><span data-stu-id="4fb5a-228">Security Administrator</span></span>
- <span data-ttu-id="4fb5a-229">条件访问管理员</span><span class="sxs-lookup"><span data-stu-id="4fb5a-229">Conditional Access Administrator</span></span>
- <span data-ttu-id="4fb5a-230">全局读取者</span><span class="sxs-lookup"><span data-stu-id="4fb5a-230">Global Reader</span></span>
- <span data-ttu-id="4fb5a-231">设备管理员</span><span class="sxs-lookup"><span data-stu-id="4fb5a-231">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="4fb5a-232">PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="4fb5a-232">PowerShell scripts</span></span>

<span data-ttu-id="4fb5a-233">Windows PowerShell无法以面向特定设备的方式分配Microsoft 托管桌面脚本。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-233">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="4fb5a-234">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-234">**Advisory**</span></span>

<span data-ttu-id="4fb5a-235">请确保 Azure AD Windows PowerShell中的脚本不面向任何 Microsoft 管理桌面设备或用户。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-235">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="4fb5a-236">不要将 PowerShell 脚本分配给所有用户、所有设备或两者。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-236">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="4fb5a-237">将策略更改为使用面向特定 Azure AD 组（不包括任何设备Microsoft 托管桌面的分配。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-237">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="4fb5a-238">有关详细信息，请参阅在[Intune Windows 10设备上使用 PowerShell 脚本](/mem/intune/apps/intune-management-extension)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-238">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="4fb5a-239">区域</span><span class="sxs-lookup"><span data-stu-id="4fb5a-239">Region</span></span>

<span data-ttu-id="4fb5a-240">你的区域必须受 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-240">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="4fb5a-241">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-241">**Not ready**</span></span>

<span data-ttu-id="4fb5a-242">你的 Azure AD 组织区域当前不受 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-242">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="4fb5a-243">有关详细信息，请参阅支持Microsoft 托管桌面[和语言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-243">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="4fb5a-244">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-244">**Advisory**</span></span>

<span data-ttu-id="4fb5a-245">Azure AD 组织所在的一个或多个国家/地区不受 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-245">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="4fb5a-246">有关详细信息，请参阅支持Microsoft 托管桌面[和语言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-246">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="4fb5a-247">安全基线</span><span class="sxs-lookup"><span data-stu-id="4fb5a-247">Security baselines</span></span>

<span data-ttu-id="4fb5a-248">安全基线策略不应面向任何Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-248">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="4fb5a-249">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-249">**Not ready**</span></span>

<span data-ttu-id="4fb5a-250">你有一个面向所有用户、所有设备或两者的安全基线配置文件。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-250">You have a security baseline profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="4fb5a-251">更改策略以使用面向不包括任何设备的特定 Azure AD Microsoft 托管桌面分配。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-251">Change the policy to use an assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4fb5a-252">有关步骤，请参阅[使用安全基线配置Windows 10 Intune 中的设备](/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-252">For steps, see [Use security baselines to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="4fb5a-253">在注册期间，我们将新的安全基线应用于所有Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-253">During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4fb5a-254">注册后，你可以查看Microsoft 托管桌面策略区域中的"安全基线策略"Microsoft Endpoint Manager。 </span><span class="sxs-lookup"><span data-stu-id="4fb5a-254">After enrollment, you can review the Microsoft Managed Desktop security baseline policy in the **Configuration policy** area of Microsoft Endpoint Manager.</span></span>

<span data-ttu-id="4fb5a-255">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-255">**Advisory**</span></span>

<span data-ttu-id="4fb5a-256">确保你已排除的任何安全基线策略Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-256">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4fb5a-257">有关步骤，请参阅[使用安全基线配置Windows 10 Intune 中的设备](/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-257">For steps, see [Use security baselines to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="4fb5a-258">在注册期间，我们将新的安全基线应用于所有Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-258">During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4fb5a-259">现代 **工作区设备 - 所有** Azure AD 组是注册 Microsoft 托管桌面 时创建的动态组，因此你必须在注册后返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-259">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span> 


### <a name="windows-apps"></a><span data-ttu-id="4fb5a-260">Windows应用</span><span class="sxs-lookup"><span data-stu-id="4fb5a-260">Windows apps</span></span>

<span data-ttu-id="4fb5a-261">查看希望用户拥有Microsoft 托管桌面的应用。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-261">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="4fb5a-262">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-262">**Advisory**</span></span>

<span data-ttu-id="4fb5a-263">你应该准备希望用户拥有的应用Microsoft 托管桌面清单。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-263">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="4fb5a-264">由于这些应用必须由 Intune 部署，因此请评估是否重新使用现有 Intune 应用。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-264">Since these apps must be deployed by Intune, evaluate reusing existing Intune apps.</span></span> <span data-ttu-id="4fb5a-265">请考虑使用公司门户 (在设备上安装Intune 公司门户[和](../get-started/company-portal.md)注册状态页 (ESP) 将应用分发给你的用户。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-265">Consider using Company Portal (see [Install Intune Company Portal on devices](../get-started/company-portal.md) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="4fb5a-266">有关详细信息，请参阅[Autopilot](../get-started/esp-first-run.md) [Microsoft 托管桌面](apps.md)和注册状态页的应用和首次运行体验。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-266">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="4fb5a-267">你可以让 Microsoft 帐户代表在 Microsoft Endpoint Configuration Manager中确定准备迁移到 Intune 或需要调整的应用。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-267">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="4fb5a-268">Windows Hello 企业版</span><span class="sxs-lookup"><span data-stu-id="4fb5a-268">Windows Hello for Business</span></span>

<span data-ttu-id="4fb5a-269">Microsoft 托管桌面需要Windows Hello For Business。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-269">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="4fb5a-270">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-270">**Not ready**</span></span>

<span data-ttu-id="4fb5a-271">Windows Hello For Business 禁用。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-271">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="4fb5a-272">按照 Create [a Windows Hello for Business policy 中的步骤启用它](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="4fb5a-272">Enable it by following the steps in [Create a Windows Hello for Business policy](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="4fb5a-273">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-273">**Advisory**</span></span>

<span data-ttu-id="4fb5a-274">Windows Hello未设置适用于 Business 的组。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-274">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="4fb5a-275">按照 Create [a Windows Hello for Business policy 中的步骤启用它](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-275">Enable it by following the steps in [Create a Windows Hello for Business policy](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="4fb5a-276">Windows 10更新圈</span><span class="sxs-lookup"><span data-stu-id="4fb5a-276">Windows 10 update rings</span></span>

<span data-ttu-id="4fb5a-277">Intune Windows 10更新圈"策略不得面向任何Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-277">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="4fb5a-278">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-278">**Not ready**</span></span>

<span data-ttu-id="4fb5a-279">你有一个面向所有设备、所有用户或两者同时面向的"更新圈"策略。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-279">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="4fb5a-280">更改策略以使用面向不包含任何设备配置的特定 Azure AD Microsoft 托管桌面分配。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-280">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4fb5a-281">有关步骤，请参阅[在 Intune Windows 10软件更新。](/mem/intune/protect/windows-update-for-business-configure)</span><span class="sxs-lookup"><span data-stu-id="4fb5a-281">For steps, see [Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="4fb5a-282">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-282">**Advisory**</span></span>

<span data-ttu-id="4fb5a-283">确保你拥有的任何更新圈策略不包括现代 **工作区设备 -所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-283">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="4fb5a-284">如果你已向这些策略分配了 Azure AD 用户组，请确保你已排除所有更新圈策略，并且你已排除将 Microsoft 托管桌面 用户添加到 (或等效组) 的新式 **工作区 -** 所有 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-284">If you have assigned Azure AD user groups to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group that you add your Microsoft Managed Desktop users to (or an equivalent group).</span></span> <span data-ttu-id="4fb5a-285">有关步骤，请参阅[在 Intune Windows 10软件更新。](/mem/intune/protect/windows-update-for-business-configure)</span><span class="sxs-lookup"><span data-stu-id="4fb5a-285">For steps, see [Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="4fb5a-286">现代 **工作区设备 -全部** 和现代 **工作区 -所有** Azure AD 组都是我们在注册 Microsoft 托管桌面 时创建的组，因此你必须在注册后返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-286">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="4fb5a-287">Azure Active Directory设置</span><span class="sxs-lookup"><span data-stu-id="4fb5a-287">Azure Active Directory settings</span></span>

<span data-ttu-id="4fb5a-288">可以在 Azure Azure Active Directory访问[自定义设置](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-288">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="4fb5a-289">Intune 注册</span><span class="sxs-lookup"><span data-stu-id="4fb5a-289">Intune enrollment</span></span>

<span data-ttu-id="4fb5a-290">Windows 10 Azure AD 组织的设备必须能够在 Intune 中自动注册。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-290">Windows 10 devices in your Azure AD organization must be able to automatically enroll in Intune.</span></span>

<span data-ttu-id="4fb5a-291">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-291">**Advisory**</span></span>

<span data-ttu-id="4fb5a-292">确保 MDM **用户作用域设置为**"部分"**或"\*\*\*\*全部"，** 而不是"**无"。**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-292">Make sure the **MDM User scope** is set to **Some** or **All**, not **None**.</span></span> <span data-ttu-id="4fb5a-293">如果你选择 **"一些**"，请在注册后返回，然后为组选择"新式 **工作区 -** 所有 Azure AD"组，或选择面向所有用户的Microsoft 托管桌面组。 </span><span class="sxs-lookup"><span data-stu-id="4fb5a-293">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups** or an equivalent group targeting all of your Microsoft Managed Desktop users.</span></span>  <span data-ttu-id="4fb5a-294">请参阅[使用 Windows 设置设备注册Microsoft Intune。](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="4fb5a-294">See [Set up enrollment for Windows devices by using Microsoft Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment).</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="4fb5a-295">临时订阅</span><span class="sxs-lookup"><span data-stu-id="4fb5a-295">Ad hoc subscriptions</span></span>

<span data-ttu-id="4fb5a-296">建议如何检查设置，如果 (设置为"false"，) 可能会Enterprise状态漫游正常工作。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-296">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="4fb5a-297">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-297">**Advisory**</span></span>

<span data-ttu-id="4fb5a-298">确保 **AllowAdHocSubscriptions** 设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-298">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="4fb5a-299">否则，Enterprise状态漫游可能不起作用。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-299">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="4fb5a-300">有关详细信息，请参阅 [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-300">For more information, see [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="4fb5a-301">企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="4fb5a-301">Enterprise State Roaming</span></span>

<span data-ttu-id="4fb5a-302">Enterprise应启用状态漫游。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-302">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="4fb5a-303">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-303">**Advisory**</span></span>

<span data-ttu-id="4fb5a-304">确保为"Enterprise"**组** 或"所选组"启用状态 **漫游**。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-304">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="4fb5a-305">有关详细信息，请参阅 Enable [Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-305">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="4fb5a-306">许可证</span><span class="sxs-lookup"><span data-stu-id="4fb5a-306">Licenses</span></span>

<span data-ttu-id="4fb5a-307">需要大量许可证才能使用Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-307">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="4fb5a-308">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-308">**Not Ready**</span></span>

<span data-ttu-id="4fb5a-309">没有使用许可证所需的全部许可证Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-309">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="4fb5a-310">有关详细信息，请参阅Microsoft 托管桌面[和](../intro/technologies.md)[关于许可证的更多信息](prerequisites.md#more-about-licenses)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-310">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="microsoft-managed-desktop-service-accounts"></a><span data-ttu-id="4fb5a-311">Microsoft 托管桌面服务帐户</span><span class="sxs-lookup"><span data-stu-id="4fb5a-311">Microsoft Managed Desktop service accounts</span></span>

<span data-ttu-id="4fb5a-312">某些帐户名可能会与管理 Microsoft 托管桌面 服务Microsoft 托管桌面名称冲突。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-312">Certain account names could conflict with account names created by Microsoft Managed Desktop to manage the Microsoft Managed Desktop service.</span></span>

<span data-ttu-id="4fb5a-313">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-313">**Not ready**</span></span>

<span data-ttu-id="4fb5a-314">您至少有一个帐户名称与由 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-314">You have at least one account name that will conflict with account names created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="4fb5a-315">与 Microsoft 帐户代表合作，排除这些帐户名。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-315">Work with your Microsoft account representative to exclude these account names.</span></span> <span data-ttu-id="4fb5a-316">我们不会公开列出帐户名称，以最大限度地降低安全风险。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-316">We don't list the account names publicly to minimize security risk.</span></span> 


### <a name="security-administrator-roles"></a><span data-ttu-id="4fb5a-317">安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="4fb5a-317">Security administrator roles</span></span>

<span data-ttu-id="4fb5a-318">具有特定安全角色的用户必须在 Microsoft Defender for Endpoint 中分配这些角色。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-318">Users with certain security roles must have those roles assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="4fb5a-319">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-319">**Advisory**</span></span>

<span data-ttu-id="4fb5a-320">如果你的用户已分配到 Azure AD 组织中任何这些角色，请确保他们在 Microsoft Defender for Endpoint 中也分配了这些角色。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-320">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="4fb5a-321">否则，具有这些角色的管理员将无法访问管理门户。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-321">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="4fb5a-322">安全操作员</span><span class="sxs-lookup"><span data-stu-id="4fb5a-322">Security Operator</span></span>
- <span data-ttu-id="4fb5a-323">全局读取者</span><span class="sxs-lookup"><span data-stu-id="4fb5a-323">Global Reader</span></span>

<span data-ttu-id="4fb5a-324">有关详细信息，请参阅为基于角色 [的访问控制创建和管理角色](/windows/security/threat-protection/microsoft-defender-atp/user-roles)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-324">For more information, see [Create and manage roles for role-based access control](/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="4fb5a-325">安全默认值</span><span class="sxs-lookup"><span data-stu-id="4fb5a-325">Security default</span></span>

<span data-ttu-id="4fb5a-326">Azure Active Directory中的Microsoft 托管桌面将阻止用户管理设备。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-326">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="4fb5a-327">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-327">**Not ready**</span></span>

<span data-ttu-id="4fb5a-328">你已打开"安全性默认值"。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-328">You have Security defaults turned on.</span></span> <span data-ttu-id="4fb5a-329">关闭安全默认值并设置条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-329">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="4fb5a-330">有关详细信息，请参阅 Common [Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-330">For more information, see [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="4fb5a-331">自助服务密码重置</span><span class="sxs-lookup"><span data-stu-id="4fb5a-331">Self-service Password Reset</span></span>

<span data-ttu-id="4fb5a-332">SSPR (可) SSPR 密码重置Microsoft 托管桌面服务帐户之外的所有Microsoft 托管桌面密码重置。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-332">Self-service Password Reset (SSPR) can be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="4fb5a-333">有关详细信息，请参阅[教程：允许用户](/azure/active-directory/authentication/tutorial-enable-sspr)使用自助密码重置解锁Azure Active Directory重置密码。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-333">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="4fb5a-334">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-334">**Advisory**</span></span>

<span data-ttu-id="4fb5a-335">确保"SSPR **选择**"设置包括Microsoft 托管桌面但不包括Microsoft 托管桌面帐户。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-335">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop users but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="4fb5a-336">Microsoft 托管桌面启用 SSPR 后，服务帐户将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-336">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="4fb5a-337">标准用户角色</span><span class="sxs-lookup"><span data-stu-id="4fb5a-337">Standard user role</span></span>

<span data-ttu-id="4fb5a-338">除了分配了全局管理员和设备管理员的 Azure AD 角色的用户外，Microsoft 托管桌面用户将是没有本地管理员权限的标准用户。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-338">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="4fb5a-339">当所有其他用户启动其新设备时，将为其分配一个Microsoft 托管桌面角色。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-339">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="4fb5a-340">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-340">**Advisory**</span></span>

<span data-ttu-id="4fb5a-341">Microsoft 托管桌面注册后，用户将不会在 Microsoft 托管桌面设备上拥有本地管理员权限。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-341">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="4fb5a-342">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="4fb5a-342">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="4fb5a-343">OneDrive</span><span class="sxs-lookup"><span data-stu-id="4fb5a-343">OneDrive</span></span>

<span data-ttu-id="4fb5a-344">"**仅允许在加入特定域** 的 PC 上同步"设置与"仅允许同步Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-344">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="4fb5a-345">可以在管理OneDrive访问OneDrive[设置](https://admin.onedrive.com)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-345">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="4fb5a-346">**公告**</span><span class="sxs-lookup"><span data-stu-id="4fb5a-346">**Advisory**</span></span>

<span data-ttu-id="4fb5a-347">你正在使用" **仅允许在加入特定域的 PC 上同步"** 设置。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-347">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="4fb5a-348">此设置将不能用于Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-348">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="4fb5a-349">禁用此设置，改为将OneDrive设置为使用条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-349">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="4fb5a-350">请参阅 [规划条件访问部署](/azure/active-directory/conditional-access/plan-conditional-access) 获取帮助。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-350">See [Plan a Conditional Access deployment](/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>
