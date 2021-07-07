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
ms.openlocfilehash: 866d1a2de820fca4c66537583dc5f55098149931
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327007"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="13622-104">修复准备情况评估工具发现的问题</span><span class="sxs-lookup"><span data-stu-id="13622-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="13622-105">对于每个检查，该工具将报告四个可能的结果之一：</span><span class="sxs-lookup"><span data-stu-id="13622-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="13622-106">结果</span><span class="sxs-lookup"><span data-stu-id="13622-106">Result</span></span>  |<span data-ttu-id="13622-107">含义</span><span class="sxs-lookup"><span data-stu-id="13622-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="13622-108">Ready</span><span class="sxs-lookup"><span data-stu-id="13622-108">Ready</span></span>     | <span data-ttu-id="13622-109">完成注册前无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="13622-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="13622-110">公告</span><span class="sxs-lookup"><span data-stu-id="13622-110">Advisory</span></span>    | <span data-ttu-id="13622-111">按照工具或本文中的步骤操作，获得注册和用户的最佳体验。</span><span class="sxs-lookup"><span data-stu-id="13622-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="13622-112">*你可以完成* 注册，但在部署第一台设备之前必须修复这些问题。</span><span class="sxs-lookup"><span data-stu-id="13622-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="13622-113">未就绪</span><span class="sxs-lookup"><span data-stu-id="13622-113">Not ready</span></span> | <span data-ttu-id="13622-114">*如果不修复这些问题，注册将失败。*</span><span class="sxs-lookup"><span data-stu-id="13622-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="13622-115">请按照工具或本文中的步骤进行解析。</span><span class="sxs-lookup"><span data-stu-id="13622-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="13622-116">错误</span><span class="sxs-lookup"><span data-stu-id="13622-116">Error</span></span> | <span data-ttu-id="13622-117">你Azure Active Directory (AD) 角色的权限不足，无法运行此检查。</span><span class="sxs-lookup"><span data-stu-id="13622-117">The Azure Active Directory (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

> [!NOTE]
> <span data-ttu-id="13622-118">此工具报告的结果仅反映设置在运行它的特定时间点的状态。</span><span class="sxs-lookup"><span data-stu-id="13622-118">The results reported by this tool reflect the status of your settings only at the specific point in time that you ran it.</span></span> <span data-ttu-id="13622-119">如果您稍后对 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的策略进行了任何更改，则"就绪"的项目可能会变为"未就绪"。</span><span class="sxs-lookup"><span data-stu-id="13622-119">If you later make any changes to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, items that were "Ready" can become "Not ready."</span></span> <span data-ttu-id="13622-120">若要避免与Microsoft 托管桌面问题，请在更改任何策略之前检查本文中描述的特定设置。</span><span class="sxs-lookup"><span data-stu-id="13622-120">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in this article before you change any policies.</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="13622-121">Microsoft Intune设置</span><span class="sxs-lookup"><span data-stu-id="13622-121">Microsoft Intune settings</span></span>

<span data-ttu-id="13622-122">可以在管理中心访问 intune Microsoft Endpoint Manager[设置](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="13622-122">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="13622-123">Autopilot 部署配置文件</span><span class="sxs-lookup"><span data-stu-id="13622-123">Autopilot deployment profile</span></span>

<span data-ttu-id="13622-124">不应有任何面向已分配或动态组的现有 Autopilot 配置文件Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="13622-124">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="13622-125">Microsoft 托管桌面 Autopilot 预配新设备。</span><span class="sxs-lookup"><span data-stu-id="13622-125">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="13622-126">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="13622-126">**Not ready**</span></span>

<span data-ttu-id="13622-127">你拥有分配给所有设备的 Autopilot 配置文件。</span><span class="sxs-lookup"><span data-stu-id="13622-127">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="13622-128">有关步骤，请参阅在[Intune Windows Autopilot 注册Windows设备](/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="13622-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="13622-129">注册Microsoft 托管桌面，设置 Autopilot 策略以排除 **现代工作区设备 -所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="13622-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="13622-130">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-130">**Advisory**</span></span>

<span data-ttu-id="13622-131">确保你的 Autopilot 配置文件面向不包括任何设备的已分配或Microsoft 托管桌面 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="13622-131">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="13622-132">有关步骤，请参阅在[Intune Windows Autopilot 注册Windows设备](/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="13622-132">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="13622-133">注册Microsoft 托管桌面，设置 Autopilot 配置文件以排除 **现代工作区设备 -所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="13622-133">After Microsoft Managed Desktop enrollment, set your Autopilot profiles to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="13622-134">证书连接器</span><span class="sxs-lookup"><span data-stu-id="13622-134">Certificate connectors</span></span>

<span data-ttu-id="13622-135">如果你有任何证书连接器将由你想要在 Microsoft 托管桌面 注册的设备使用，则连接器不应有任何错误。</span><span class="sxs-lookup"><span data-stu-id="13622-135">If you have any certificate connectors that will be used by the devices you want to enroll in Microsoft Managed Desktop, the connectors should not have any errors.</span></span> <span data-ttu-id="13622-136">只有以下公告之一适用于你的情况，因此请仔细检查它们。</span><span class="sxs-lookup"><span data-stu-id="13622-136">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="13622-137">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-137">**Advisory**</span></span>

<span data-ttu-id="13622-138">不存在证书连接器。</span><span class="sxs-lookup"><span data-stu-id="13622-138">No certificate connectors are present.</span></span> <span data-ttu-id="13622-139">你可能不需要任何连接器，但应评估是否需要一些连接器在 Microsoft 托管桌面 连接。</span><span class="sxs-lookup"><span data-stu-id="13622-139">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity on your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="13622-140">有关详细信息，请参阅准备[证书和网络配置文件Microsoft 托管桌面。](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="13622-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="13622-141">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-141">**Advisory**</span></span>

<span data-ttu-id="13622-142">至少有一个证书连接器出现错误。</span><span class="sxs-lookup"><span data-stu-id="13622-142">At least one certificate connector has an error.</span></span> <span data-ttu-id="13622-143">如果需要此连接器向设备Microsoft 托管桌面证书，则必须解决此错误。</span><span class="sxs-lookup"><span data-stu-id="13622-143">If you need this connector for providing certificates to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="13622-144">有关详细信息，请参阅准备[证书和网络配置文件Microsoft 托管桌面。](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="13622-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="13622-145">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-145">**Advisory**</span></span>

<span data-ttu-id="13622-146">您至少有一个证书连接器，并且未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="13622-146">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="13622-147">但是，在准备部署时，可能需要创建一个配置文件，以将连接器重新用于Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="13622-147">However, in preparation for deployment, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="13622-148">有关详细信息，请参阅准备[证书和网络配置文件Microsoft 托管桌面。](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="13622-148">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

### <a name="company-portal"></a><span data-ttu-id="13622-149">公司门户</span><span class="sxs-lookup"><span data-stu-id="13622-149">Company Portal</span></span>

<span data-ttu-id="13622-150">Microsoft 托管桌面要求 IT 管理员使用 Intune 公司门户 为用户安装Microsoft 托管桌面服务器。</span><span class="sxs-lookup"><span data-stu-id="13622-150">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="13622-151">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="13622-151">**Not ready**</span></span>

<span data-ttu-id="13622-152">您未为公司门户安装任何内容。</span><span class="sxs-lookup"><span data-stu-id="13622-152">You do not have Company Portal installed for your users.</span></span> <span data-ttu-id="13622-153">购买公司门户并强制 Intune 和 适用于企业的 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="13622-153">Purchase Company Portal and force a sync between Intune and Microsoft Store for Business.</span></span> <span data-ttu-id="13622-154">有关详细信息，请参阅 Install [Intune 公司门户 on devices。](../get-started/company-portal.md)</span><span class="sxs-lookup"><span data-stu-id="13622-154">For more information, see [Install Intune Company Portal on devices](../get-started/company-portal.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="13622-155">条件访问策略</span><span class="sxs-lookup"><span data-stu-id="13622-155">Conditional access policies</span></span>

<span data-ttu-id="13622-156">条件访问策略不得Microsoft 托管桌面 Intune 和 Azure AD (Azure AD) 管理 Azure AD 组织。</span><span class="sxs-lookup"><span data-stu-id="13622-156">Conditional access policies must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>

<span data-ttu-id="13622-157">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="13622-157">**Not ready**</span></span>

<span data-ttu-id="13622-158">您至少有一个面向所有用户的条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="13622-158">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="13622-159">注册期间，我们会从Microsoft 托管桌面访问策略中排除服务帐户，并应用新的条件访问策略来限制访问这些帐户。</span><span class="sxs-lookup"><span data-stu-id="13622-159">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="13622-160">注册后，可以在 Microsoft 托管桌面中查看条件访问Microsoft Endpoint Manager。</span><span class="sxs-lookup"><span data-stu-id="13622-160">After enrollment, you can review the Microsoft Managed Desktop conditional access policy in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="13622-161">有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="13622-161">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="13622-162">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-162">**Advisory**</span></span>

<span data-ttu-id="13622-163">您具有可能会阻止用户管理 Microsoft 托管桌面服务的条件Microsoft 托管桌面策略。</span><span class="sxs-lookup"><span data-stu-id="13622-163">You have conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="13622-164">注册期间，我们会从Microsoft 托管桌面访问策略中排除服务帐户，并应用新的条件访问策略来限制访问这些帐户。</span><span class="sxs-lookup"><span data-stu-id="13622-164">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="13622-165">有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="13622-165">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="13622-166">**Error**</span><span class="sxs-lookup"><span data-stu-id="13622-166">**Error**</span></span>

<span data-ttu-id="13622-167">Intune 管理员角色没有足够的权限进行此检查。</span><span class="sxs-lookup"><span data-stu-id="13622-167">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="13622-168">还需要分配以下任一 Azure AD 角色来运行此检查：</span><span class="sxs-lookup"><span data-stu-id="13622-168">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="13622-169">安全读取者</span><span class="sxs-lookup"><span data-stu-id="13622-169">Security Reader</span></span>
- <span data-ttu-id="13622-170">安全管理员</span><span class="sxs-lookup"><span data-stu-id="13622-170">Security Administrator</span></span>
- <span data-ttu-id="13622-171">条件访问管理员</span><span class="sxs-lookup"><span data-stu-id="13622-171">Conditional Access Administrator</span></span>
- <span data-ttu-id="13622-172">全局读取者</span><span class="sxs-lookup"><span data-stu-id="13622-172">Global Reader</span></span>
- <span data-ttu-id="13622-173">设备管理员</span><span class="sxs-lookup"><span data-stu-id="13622-173">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="13622-174">设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="13622-174">Device Compliance policies</span></span>

<span data-ttu-id="13622-175">Azure AD 组织中 Intune 设备合规性策略可能会影响Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="13622-175">Intune Device Compliance policies in your Azure AD organization might impact Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="13622-176">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="13622-176">**Not ready**</span></span>

<span data-ttu-id="13622-177">您至少有一个面向所有用户的合规性策略。</span><span class="sxs-lookup"><span data-stu-id="13622-177">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="13622-178">Microsoft 托管桌面包括面向你的设备Microsoft 托管桌面策略。</span><span class="sxs-lookup"><span data-stu-id="13622-178">Microsoft Managed Desktop includes compliance policies that will target your Microsoft Managed Desktop devices.</span></span>  <span data-ttu-id="13622-179">将策略更改为面向不包含任何用户或设备Microsoft 托管桌面 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="13622-179">Change the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users or devices.</span></span> <span data-ttu-id="13622-180">有关步骤，请参阅 Create [a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="13622-180">For steps, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="13622-181">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-181">**Advisory**</span></span>

<span data-ttu-id="13622-182">确保你拥有的任何合规性策略不面向任何Microsoft 托管桌面用户。</span><span class="sxs-lookup"><span data-stu-id="13622-182">Make sure that any compliance policies you have don't target any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="13622-183">有关步骤，请参阅 Create [a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="13622-183">For steps, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-profiles"></a><span data-ttu-id="13622-184">设备配置文件</span><span class="sxs-lookup"><span data-stu-id="13622-184">Device Configuration profiles</span></span>

<span data-ttu-id="13622-185">Azure AD 组织中 Intune 设备配置文件不得面向任何 Microsoft 管理桌面设备或用户。</span><span class="sxs-lookup"><span data-stu-id="13622-185">Intune Device Configuration profiles in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="13622-186">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="13622-186">**Not ready**</span></span>

<span data-ttu-id="13622-187">你至少具有一个面向所有用户和/或所有设备的配置文件。</span><span class="sxs-lookup"><span data-stu-id="13622-187">You have at least one configuration profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="13622-188">将配置文件重置为面向不包括任何设备的特定 Azure AD Microsoft 托管桌面组。</span><span class="sxs-lookup"><span data-stu-id="13622-188">Reset the profile to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="13622-189">有关步骤，请参阅[Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="13622-189">For steps, see [Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="13622-190">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-190">**Advisory**</span></span>

<span data-ttu-id="13622-191">确保你拥有的任何配置策略不包括任何Microsoft 托管桌面或用户。</span><span class="sxs-lookup"><span data-stu-id="13622-191">Make sure that any configuration policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="13622-192">有关步骤，请参阅[Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="13622-192">For steps, see [Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="13622-193">设备类型限制</span><span class="sxs-lookup"><span data-stu-id="13622-193">Device type restrictions</span></span>

<span data-ttu-id="13622-194">Microsoft 托管桌面设备必须在 Intune 中注册。</span><span class="sxs-lookup"><span data-stu-id="13622-194">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="13622-195">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="13622-195">**Not ready**</span></span>

<span data-ttu-id="13622-196">你当前至少配置了一个注册限制策略Windows Intune 中注册。</span><span class="sxs-lookup"><span data-stu-id="13622-196">You currently have at least one enrollment restriction policy configured to prevent Windows devices from enrollment in Intune.</span></span> <span data-ttu-id="13622-197">按照 [为面向用户](/mem/intune/enrollment/enrollment-restrictions-set)的每个注册限制策略设置注册Microsoft 托管桌面中的步骤操作，Windows (**MDM**) 设置为 **"允许"。**</span><span class="sxs-lookup"><span data-stu-id="13622-197">Follow the steps in [Set enrollment restrictions](/mem/intune/enrollment/enrollment-restrictions-set) for each enrollment restriction policy that targets Microsoft Managed Desktop users and change the **Windows (MDM)** setting to **Allow**.</span></span> <span data-ttu-id="13622-198">但是，你可以将 MDM设备上个人拥有 **Windows ()** 设置为 **阻止**。</span><span class="sxs-lookup"><span data-stu-id="13622-198">You can, however, set any **personally owned** **Windows (MDM)** devices to **Block**.</span></span> 


### <a name="enrollment-status-page"></a><span data-ttu-id="13622-199">注册状态页</span><span class="sxs-lookup"><span data-stu-id="13622-199">Enrollment Status Page</span></span>

<span data-ttu-id="13622-200">YOU currently have the Enrollment Status Page (ESP) enabled.</span><span class="sxs-lookup"><span data-stu-id="13622-200">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="13622-201">如果你打算参加此功能的公共Microsoft 托管桌面预览版，可以忽略此项。</span><span class="sxs-lookup"><span data-stu-id="13622-201">If you intend to participate in the Microsoft Managed Desktop public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="13622-202">有关详细信息，请参阅 [Autopilot 首次运行体验和注册状态页面](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="13622-202">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="13622-203">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="13622-203">**Not ready**</span></span>

<span data-ttu-id="13622-204">将 ESP 默认配置文件设置为"**显示应用和配置文件配置进度"。**</span><span class="sxs-lookup"><span data-stu-id="13622-204">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="13622-205">通过按照设置注册状态页 中的步骤操作，禁用此设置或确保任何 Azure AD 组的工作分配不包括Microsoft 托管桌面[设备](/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="13622-205">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="13622-206">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-206">**Advisory**</span></span>

<span data-ttu-id="13622-207">确保未将具有"显示应用和配置文件配置进度"设置的任何配置文件分配给任何 Azure AD 组，该组Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="13622-207">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="13622-208">有关详细信息，请参阅设置 [注册状态页](/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="13622-208">For more information, see [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="microsoft-store-for-business"></a><span data-ttu-id="13622-209">适用于企业的 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="13622-209">Microsoft Store for Business</span></span>

<span data-ttu-id="13622-210">我们使用 适用于企业的 Microsoft Store 在 Microsoft 托管桌面 上部署 公司门户 应用，以允许用户选择安装某些应用，例如 Microsoft Project 和 Microsoft Visio (（如果允许) ）。</span><span class="sxs-lookup"><span data-stu-id="13622-210">We use Microsoft Store for Business and deploy the Company Portal app on Microsoft Managed Desktop to allow users to optionally install some apps, such as Microsoft Project and Microsoft Visio (where permitted).</span></span>

<span data-ttu-id="13622-211">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="13622-211">**Not ready**</span></span>

<span data-ttu-id="13622-212">适用于企业的 Microsoft Store未启用或未与 Intune 同步。</span><span class="sxs-lookup"><span data-stu-id="13622-212">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="13622-213">有关详细信息，请参阅[如何使用](/mem/intune/apps/windows-store-for-business)适用于企业的 Microsoft Store 管理批量购买的应用Microsoft Intune在设备上Intune 公司门户[购买的应用](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="13622-213">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on devices](../get-started/company-portal.md).</span></span>

### <a name="multifactor-authentication"></a><span data-ttu-id="13622-214">多重身份验证</span><span class="sxs-lookup"><span data-stu-id="13622-214">Multifactor authentication</span></span>

<span data-ttu-id="13622-215">多重身份验证不得阻止Microsoft 托管桌面 Intune 和 Azure AD (租户) Azure AD 组织。</span><span class="sxs-lookup"><span data-stu-id="13622-215">Multifactor authentication must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>


<span data-ttu-id="13622-216">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="13622-216">**Not ready**</span></span>

<span data-ttu-id="13622-217">您具有为分配给所有用户的条件 **访问策略所需的** 一些多重身份验证策略。</span><span class="sxs-lookup"><span data-stu-id="13622-217">You have some multifactor authentication policies set as **required** for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="13622-218">注册期间，我们会从Microsoft 托管桌面访问策略中排除服务帐户，并应用新的条件访问策略来限制访问这些帐户。</span><span class="sxs-lookup"><span data-stu-id="13622-218">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="13622-219">有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="13622-219">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="13622-220">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-220">**Advisory**</span></span>

<span data-ttu-id="13622-221">您具有条件访问策略所需的多重身份验证，这些策略Microsoft 托管桌面管理 Microsoft 托管桌面 服务。</span><span class="sxs-lookup"><span data-stu-id="13622-221">You have multifactor authentication required on conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="13622-222">注册期间，我们会从Microsoft 托管桌面访问策略中排除服务帐户，并应用新的条件访问策略来限制访问这些帐户。</span><span class="sxs-lookup"><span data-stu-id="13622-222">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="13622-223">有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="13622-223">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="13622-224">**Error**</span><span class="sxs-lookup"><span data-stu-id="13622-224">**Error**</span></span>

<span data-ttu-id="13622-225">Intune 管理员角色没有足够的权限进行此检查。</span><span class="sxs-lookup"><span data-stu-id="13622-225">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="13622-226">还需要分配以下任一 Azure AD 角色来运行此检查：</span><span class="sxs-lookup"><span data-stu-id="13622-226">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="13622-227">安全读取者</span><span class="sxs-lookup"><span data-stu-id="13622-227">Security Reader</span></span>
- <span data-ttu-id="13622-228">安全管理员</span><span class="sxs-lookup"><span data-stu-id="13622-228">Security Administrator</span></span>
- <span data-ttu-id="13622-229">条件访问管理员</span><span class="sxs-lookup"><span data-stu-id="13622-229">Conditional Access Administrator</span></span>
- <span data-ttu-id="13622-230">全局读取者</span><span class="sxs-lookup"><span data-stu-id="13622-230">Global Reader</span></span>
- <span data-ttu-id="13622-231">设备管理员</span><span class="sxs-lookup"><span data-stu-id="13622-231">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="13622-232">PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="13622-232">PowerShell scripts</span></span>

<span data-ttu-id="13622-233">Windows PowerShell无法以面向特定设备的方式分配Microsoft 托管桌面脚本。</span><span class="sxs-lookup"><span data-stu-id="13622-233">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="13622-234">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-234">**Advisory**</span></span>

<span data-ttu-id="13622-235">请确保 Azure AD Windows PowerShell中的脚本不面向任何 Microsoft 管理桌面设备或用户。</span><span class="sxs-lookup"><span data-stu-id="13622-235">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="13622-236">不要将 PowerShell 脚本分配给所有用户、所有设备或两者。</span><span class="sxs-lookup"><span data-stu-id="13622-236">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="13622-237">将策略更改为使用面向特定 Azure AD 组（不包括任何设备Microsoft 托管桌面的分配。</span><span class="sxs-lookup"><span data-stu-id="13622-237">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="13622-238">有关详细信息，请参阅在[Intune Windows 10设备上使用 PowerShell 脚本](/mem/intune/apps/intune-management-extension)。</span><span class="sxs-lookup"><span data-stu-id="13622-238">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="13622-239">区域</span><span class="sxs-lookup"><span data-stu-id="13622-239">Region</span></span>

<span data-ttu-id="13622-240">你的区域必须受 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="13622-240">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="13622-241">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="13622-241">**Not ready**</span></span>

<span data-ttu-id="13622-242">你的 Azure AD 组织区域当前不受 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="13622-242">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="13622-243">有关详细信息，请参阅支持Microsoft 托管桌面[和语言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="13622-243">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="13622-244">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-244">**Advisory**</span></span>

<span data-ttu-id="13622-245">Azure AD 组织所在的一个或多个国家/地区不受 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="13622-245">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="13622-246">有关详细信息，请参阅支持Microsoft 托管桌面[和语言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="13622-246">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="13622-247">安全基线</span><span class="sxs-lookup"><span data-stu-id="13622-247">Security baselines</span></span>

<span data-ttu-id="13622-248">安全基线策略不应面向任何Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="13622-248">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="13622-249">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="13622-249">**Not ready**</span></span>

<span data-ttu-id="13622-250">你有一个面向所有用户、所有设备或两者的安全基线配置文件。</span><span class="sxs-lookup"><span data-stu-id="13622-250">You have a security baseline profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="13622-251">更改策略以使用面向不包括任何设备的特定 Azure AD Microsoft 托管桌面分配。</span><span class="sxs-lookup"><span data-stu-id="13622-251">Change the policy to use an assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="13622-252">有关步骤，请参阅[使用安全基线配置Windows 10 Intune 中的设备](/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="13622-252">For steps, see [Use security baselines to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="13622-253">在注册期间，我们将新的安全基线应用于所有Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="13622-253">During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="13622-254">注册后，你可以查看Microsoft 托管桌面策略区域中的"安全基线策略"Microsoft Endpoint Manager。 </span><span class="sxs-lookup"><span data-stu-id="13622-254">After enrollment, you can review the Microsoft Managed Desktop security baseline policy in the **Configuration policy** area of Microsoft Endpoint Manager.</span></span>

<span data-ttu-id="13622-255">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-255">**Advisory**</span></span>

<span data-ttu-id="13622-256">确保你已排除的任何安全基线策略Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="13622-256">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="13622-257">有关步骤，请参阅[使用安全基线配置Windows 10 Intune 中的设备](/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="13622-257">For steps, see [Use security baselines to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="13622-258">在注册期间，我们将新的安全基线应用于所有Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="13622-258">During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="13622-259">现代 **工作区设备 - 所有** Azure AD 组是注册 Microsoft 托管桌面 时创建的动态组，因此你必须在注册后返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="13622-259">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span> 

### <a name="unlicensed-admins"></a><span data-ttu-id="13622-260">未授权的管理员</span><span class="sxs-lookup"><span data-stu-id="13622-260">Unlicensed admins</span></span>

<span data-ttu-id="13622-261">当我们与 Azure AD 组织交互时，必须启用此设置以避免出现"缺少权限"错误。</span><span class="sxs-lookup"><span data-stu-id="13622-261">This setting must be enabled to avoid a "lack of permissions" error when we interact with your Azure AD organization.</span></span> 

<span data-ttu-id="13622-262">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="13622-262">**Not ready**</span></span>

<span data-ttu-id="13622-263">**应启用允许访问** 未授权的管理员。</span><span class="sxs-lookup"><span data-stu-id="13622-263">**Allow access to unlicensed admins** should be enabled.</span></span> <span data-ttu-id="13622-264">有关步骤，请参阅 [来宾帐户的先决条件](/microsoft-365/managed-desktop/get-ready/guest-accounts)。</span><span class="sxs-lookup"><span data-stu-id="13622-264">For steps, see [Prerequisites for guest accounts](/microsoft-365/managed-desktop/get-ready/guest-accounts).</span></span>

### <a name="windows-apps"></a><span data-ttu-id="13622-265">Windows应用</span><span class="sxs-lookup"><span data-stu-id="13622-265">Windows apps</span></span>

<span data-ttu-id="13622-266">查看希望用户拥有Microsoft 托管桌面的应用。</span><span class="sxs-lookup"><span data-stu-id="13622-266">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="13622-267">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-267">**Advisory**</span></span>

<span data-ttu-id="13622-268">你应该准备希望用户拥有的应用Microsoft 托管桌面清单。</span><span class="sxs-lookup"><span data-stu-id="13622-268">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="13622-269">由于这些应用必须由 Intune 部署，因此请评估是否重新使用现有 Intune 应用。</span><span class="sxs-lookup"><span data-stu-id="13622-269">Since these apps must be deployed by Intune, evaluate reusing existing Intune apps.</span></span> <span data-ttu-id="13622-270">请考虑使用公司门户 (在设备上安装Intune 公司门户[和](../get-started/company-portal.md)注册状态页 (ESP) 将应用分发给你的用户。</span><span class="sxs-lookup"><span data-stu-id="13622-270">Consider using Company Portal (see [Install Intune Company Portal on devices](../get-started/company-portal.md) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="13622-271">有关详细信息，请参阅[Autopilot](../get-started/esp-first-run.md) [Microsoft 托管桌面](apps.md)和注册状态页的应用和首次运行体验。</span><span class="sxs-lookup"><span data-stu-id="13622-271">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="13622-272">你可以让 Microsoft 帐户代表在 Microsoft Endpoint Configuration Manager中确定准备迁移到 Intune 或需要调整的应用。</span><span class="sxs-lookup"><span data-stu-id="13622-272">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="13622-273">Windows Hello 企业版</span><span class="sxs-lookup"><span data-stu-id="13622-273">Windows Hello for Business</span></span>

<span data-ttu-id="13622-274">Microsoft 托管桌面需要Windows Hello For Business。</span><span class="sxs-lookup"><span data-stu-id="13622-274">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="13622-275">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="13622-275">**Not ready**</span></span>

<span data-ttu-id="13622-276">Windows Hello For Business 禁用。</span><span class="sxs-lookup"><span data-stu-id="13622-276">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="13622-277">按照 Create [a Windows Hello for Business policy 中的步骤启用它](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="13622-277">Enable it by following the steps in [Create a Windows Hello for Business policy](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="13622-278">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-278">**Advisory**</span></span>

<span data-ttu-id="13622-279">Windows Hello未设置适用于 Business 的组。</span><span class="sxs-lookup"><span data-stu-id="13622-279">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="13622-280">按照 Create [a Windows Hello for Business policy 中的步骤启用它](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)。</span><span class="sxs-lookup"><span data-stu-id="13622-280">Enable it by following the steps in [Create a Windows Hello for Business policy](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="13622-281">Windows 10更新圈</span><span class="sxs-lookup"><span data-stu-id="13622-281">Windows 10 update rings</span></span>

<span data-ttu-id="13622-282">Intune Windows 10更新圈"策略不得面向任何Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="13622-282">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="13622-283">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="13622-283">**Not ready**</span></span>

<span data-ttu-id="13622-284">你有一个面向所有设备、所有用户或两者同时面向的"更新圈"策略。</span><span class="sxs-lookup"><span data-stu-id="13622-284">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="13622-285">更改策略以使用面向不包含任何设备配置的特定 Azure AD Microsoft 托管桌面分配。</span><span class="sxs-lookup"><span data-stu-id="13622-285">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="13622-286">有关步骤，请参阅[在 Intune Windows 10软件更新。](/mem/intune/protect/windows-update-for-business-configure)</span><span class="sxs-lookup"><span data-stu-id="13622-286">For steps, see [Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="13622-287">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-287">**Advisory**</span></span>

<span data-ttu-id="13622-288">确保你拥有的任何更新圈策略不包括现代 **工作区设备 -所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="13622-288">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="13622-289">如果你已向这些策略分配了 Azure AD 用户组，请确保你已排除所有更新圈策略，并且你已排除将 Microsoft 托管桌面 用户添加到 (或等效组) 的新式 **工作区 -** 所有 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="13622-289">If you have assigned Azure AD user groups to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group that you add your Microsoft Managed Desktop users to (or an equivalent group).</span></span> <span data-ttu-id="13622-290">有关步骤，请参阅[在 Intune Windows 10软件更新。](/mem/intune/protect/windows-update-for-business-configure)</span><span class="sxs-lookup"><span data-stu-id="13622-290">For steps, see [Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="13622-291">现代 **工作区设备 -全部** 和现代 **工作区 -所有** Azure AD 组都是我们在注册 Microsoft 托管桌面 时创建的组，因此你必须在注册后返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="13622-291">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="13622-292">Azure Active Directory设置</span><span class="sxs-lookup"><span data-stu-id="13622-292">Azure Active Directory settings</span></span>

<span data-ttu-id="13622-293">可以在 Azure Azure Active Directory访问[自定义设置](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="13622-293">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="13622-294">Intune 注册</span><span class="sxs-lookup"><span data-stu-id="13622-294">Intune enrollment</span></span>

<span data-ttu-id="13622-295">Windows 10 Azure AD 组织的设备必须能够在 Intune 中自动注册。</span><span class="sxs-lookup"><span data-stu-id="13622-295">Windows 10 devices in your Azure AD organization must be able to automatically enroll in Intune.</span></span>

<span data-ttu-id="13622-296">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-296">**Advisory**</span></span>

<span data-ttu-id="13622-297">确保 MDM **用户作用域设置为**"部分"**或"\*\*\*\*全部"，** 而不是"**无"。**</span><span class="sxs-lookup"><span data-stu-id="13622-297">Make sure the **MDM User scope** is set to **Some** or **All**, not **None**.</span></span> <span data-ttu-id="13622-298">如果你选择 **"一些**"，请在注册后返回，然后为组选择"新式 **工作区 -** 所有 Azure AD"组，或选择面向所有用户的Microsoft 托管桌面组。 </span><span class="sxs-lookup"><span data-stu-id="13622-298">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups** or an equivalent group targeting all of your Microsoft Managed Desktop users.</span></span>  <span data-ttu-id="13622-299">请参阅[使用 Windows 设置设备注册Microsoft Intune。](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="13622-299">See [Set up enrollment for Windows devices by using Microsoft Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment).</span></span>

### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="13622-300">临时订阅</span><span class="sxs-lookup"><span data-stu-id="13622-300">Ad hoc subscriptions</span></span>

<span data-ttu-id="13622-301">建议如何检查设置，如果 (设置为"false"，) 可能会Enterprise状态漫游正常工作。</span><span class="sxs-lookup"><span data-stu-id="13622-301">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="13622-302">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-302">**Advisory**</span></span>

<span data-ttu-id="13622-303">确保 **AllowAdHocSubscriptions** 设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="13622-303">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="13622-304">否则，Enterprise状态漫游可能不起作用。</span><span class="sxs-lookup"><span data-stu-id="13622-304">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="13622-305">有关详细信息，请参阅 [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings)。</span><span class="sxs-lookup"><span data-stu-id="13622-305">For more information, see [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="13622-306">企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="13622-306">Enterprise State Roaming</span></span>

<span data-ttu-id="13622-307">Enterprise应启用状态漫游。</span><span class="sxs-lookup"><span data-stu-id="13622-307">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="13622-308">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-308">**Advisory**</span></span>

<span data-ttu-id="13622-309">确保为"Enterprise"**组** 或"所选组"启用状态 **漫游**。</span><span class="sxs-lookup"><span data-stu-id="13622-309">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="13622-310">有关详细信息，请参阅 Enable [Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable)。</span><span class="sxs-lookup"><span data-stu-id="13622-310">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="13622-311">许可证</span><span class="sxs-lookup"><span data-stu-id="13622-311">Licenses</span></span>

<span data-ttu-id="13622-312">需要大量许可证才能使用Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="13622-312">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="13622-313">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="13622-313">**Not Ready**</span></span>

<span data-ttu-id="13622-314">没有使用许可证所需的全部许可证Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="13622-314">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="13622-315">有关详细信息，请参阅Microsoft 托管桌面[和](../intro/technologies.md)[关于许可证的更多信息](prerequisites.md#more-about-licenses)。</span><span class="sxs-lookup"><span data-stu-id="13622-315">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="microsoft-managed-desktop-service-accounts"></a><span data-ttu-id="13622-316">Microsoft 托管桌面服务帐户</span><span class="sxs-lookup"><span data-stu-id="13622-316">Microsoft Managed Desktop service accounts</span></span>

<span data-ttu-id="13622-317">某些帐户名可能会与管理 Microsoft 托管桌面 服务Microsoft 托管桌面名称冲突。</span><span class="sxs-lookup"><span data-stu-id="13622-317">Certain account names could conflict with account names created by Microsoft Managed Desktop to manage the Microsoft Managed Desktop service.</span></span>

<span data-ttu-id="13622-318">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="13622-318">**Not ready**</span></span>

<span data-ttu-id="13622-319">您至少有一个帐户名称与由 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="13622-319">You have at least one account name that will conflict with account names created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="13622-320">与 Microsoft 帐户代表合作，排除这些帐户名。</span><span class="sxs-lookup"><span data-stu-id="13622-320">Work with your Microsoft account representative to exclude these account names.</span></span> <span data-ttu-id="13622-321">我们不会公开列出帐户名称，以最大限度地降低安全风险。</span><span class="sxs-lookup"><span data-stu-id="13622-321">We don't list the account names publicly to minimize security risk.</span></span> 


### <a name="security-administrator-roles"></a><span data-ttu-id="13622-322">安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="13622-322">Security administrator roles</span></span>

<span data-ttu-id="13622-323">具有特定安全角色的用户必须在 Microsoft Defender for Endpoint 中分配这些角色。</span><span class="sxs-lookup"><span data-stu-id="13622-323">Users with certain security roles must have those roles assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="13622-324">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-324">**Advisory**</span></span>

<span data-ttu-id="13622-325">如果你的用户已分配到 Azure AD 组织中任何这些角色，请确保他们在 Microsoft Defender for Endpoint 中也分配了这些角色。</span><span class="sxs-lookup"><span data-stu-id="13622-325">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="13622-326">否则，具有这些角色的管理员将无法访问管理门户。</span><span class="sxs-lookup"><span data-stu-id="13622-326">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="13622-327">安全操作员</span><span class="sxs-lookup"><span data-stu-id="13622-327">Security Operator</span></span>
- <span data-ttu-id="13622-328">全局读取者</span><span class="sxs-lookup"><span data-stu-id="13622-328">Global Reader</span></span>

<span data-ttu-id="13622-329">有关详细信息，请参阅为基于角色 [的访问控制创建和管理角色](/windows/security/threat-protection/microsoft-defender-atp/user-roles)。</span><span class="sxs-lookup"><span data-stu-id="13622-329">For more information, see [Create and manage roles for role-based access control](/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="13622-330">安全默认值</span><span class="sxs-lookup"><span data-stu-id="13622-330">Security default</span></span>

<span data-ttu-id="13622-331">Azure Active Directory中的Microsoft 托管桌面将阻止用户管理设备。</span><span class="sxs-lookup"><span data-stu-id="13622-331">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="13622-332">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="13622-332">**Not ready**</span></span>

<span data-ttu-id="13622-333">你已打开"安全性默认值"。</span><span class="sxs-lookup"><span data-stu-id="13622-333">You have Security defaults turned on.</span></span> <span data-ttu-id="13622-334">关闭安全默认值并设置条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="13622-334">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="13622-335">有关详细信息，请参阅 Common [Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。</span><span class="sxs-lookup"><span data-stu-id="13622-335">For more information, see [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="13622-336">自助服务密码重置</span><span class="sxs-lookup"><span data-stu-id="13622-336">Self-service Password Reset</span></span>

<span data-ttu-id="13622-337">SSPR (可) SSPR 密码重置Microsoft 托管桌面服务帐户之外的所有Microsoft 托管桌面密码重置。</span><span class="sxs-lookup"><span data-stu-id="13622-337">Self-service Password Reset (SSPR) can be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="13622-338">有关详细信息，请参阅[教程：允许用户](/azure/active-directory/authentication/tutorial-enable-sspr)使用自助密码重置解锁Azure Active Directory重置密码。</span><span class="sxs-lookup"><span data-stu-id="13622-338">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="13622-339">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-339">**Advisory**</span></span>

<span data-ttu-id="13622-340">确保"SSPR **选择**"设置包括Microsoft 托管桌面但不包括Microsoft 托管桌面帐户。</span><span class="sxs-lookup"><span data-stu-id="13622-340">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop users but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="13622-341">Microsoft 托管桌面启用 SSPR 后，服务帐户将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="13622-341">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="13622-342">标准用户角色</span><span class="sxs-lookup"><span data-stu-id="13622-342">Standard user role</span></span>

<span data-ttu-id="13622-343">除了分配了全局管理员和设备管理员的 Azure AD 角色的用户外，Microsoft 托管桌面用户将是没有本地管理员权限的标准用户。</span><span class="sxs-lookup"><span data-stu-id="13622-343">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="13622-344">当所有其他用户启动其新设备时，将为其分配一个Microsoft 托管桌面角色。</span><span class="sxs-lookup"><span data-stu-id="13622-344">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="13622-345">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-345">**Advisory**</span></span>

<span data-ttu-id="13622-346">Microsoft 托管桌面注册后，用户将不会在 Microsoft 托管桌面设备上拥有本地管理员权限。</span><span class="sxs-lookup"><span data-stu-id="13622-346">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="13622-347">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="13622-347">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="13622-348">OneDrive</span><span class="sxs-lookup"><span data-stu-id="13622-348">OneDrive</span></span>

<span data-ttu-id="13622-349">"**仅允许在加入特定域** 的 PC 上同步"设置与"仅允许同步Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="13622-349">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="13622-350">可以在管理OneDrive访问OneDrive[设置](https://admin.onedrive.com)。</span><span class="sxs-lookup"><span data-stu-id="13622-350">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="13622-351">**公告**</span><span class="sxs-lookup"><span data-stu-id="13622-351">**Advisory**</span></span>

<span data-ttu-id="13622-352">你正在使用" **仅允许在加入特定域的 PC 上同步"** 设置。</span><span class="sxs-lookup"><span data-stu-id="13622-352">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="13622-353">此设置将不能用于Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="13622-353">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="13622-354">禁用此设置，改为将OneDrive设置为使用条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="13622-354">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="13622-355">请参阅 [规划条件访问部署](/azure/active-directory/conditional-access/plan-conditional-access) 获取帮助。</span><span class="sxs-lookup"><span data-stu-id="13622-355">See [Plan a Conditional Access deployment](/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>
