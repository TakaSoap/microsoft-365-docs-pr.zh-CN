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
ms.openlocfilehash: 5a22996ce9e39dc16191ddddc6aa9393de557bbc
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579406"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="f0351-104">修复准备情况评估工具发现的问题</span><span class="sxs-lookup"><span data-stu-id="f0351-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="f0351-105">对于每个检查，该工具将报告四个可能的结果之一：</span><span class="sxs-lookup"><span data-stu-id="f0351-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="f0351-106">结果</span><span class="sxs-lookup"><span data-stu-id="f0351-106">Result</span></span>  |<span data-ttu-id="f0351-107">含义</span><span class="sxs-lookup"><span data-stu-id="f0351-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="f0351-108">Ready</span><span class="sxs-lookup"><span data-stu-id="f0351-108">Ready</span></span>     | <span data-ttu-id="f0351-109">完成注册前无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="f0351-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="f0351-110">公告</span><span class="sxs-lookup"><span data-stu-id="f0351-110">Advisory</span></span>    | <span data-ttu-id="f0351-111">按照工具或本文中的步骤操作，获得注册和用户的最佳体验。</span><span class="sxs-lookup"><span data-stu-id="f0351-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="f0351-112">*你可以完成* 注册，但在部署第一台设备之前必须修复这些问题。</span><span class="sxs-lookup"><span data-stu-id="f0351-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="f0351-113">未就绪</span><span class="sxs-lookup"><span data-stu-id="f0351-113">Not ready</span></span> | <span data-ttu-id="f0351-114">*如果不修复这些问题，注册将失败。*</span><span class="sxs-lookup"><span data-stu-id="f0351-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="f0351-115">请按照工具或本文中的步骤进行解析。</span><span class="sxs-lookup"><span data-stu-id="f0351-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="f0351-116">错误</span><span class="sxs-lookup"><span data-stu-id="f0351-116">Error</span></span> | <span data-ttu-id="f0351-117">你 (Azure Active Directory) AD 角色没有足够的权限运行此检查。</span><span class="sxs-lookup"><span data-stu-id="f0351-117">The Azure Active Directory (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

> [!NOTE]
> <span data-ttu-id="f0351-118">此工具报告的结果仅反映设置在运行它的特定时间点的状态。</span><span class="sxs-lookup"><span data-stu-id="f0351-118">The results reported by this tool reflect the status of your settings only at the specific point in time that you ran it.</span></span> <span data-ttu-id="f0351-119">如果稍后对 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的策略进行了任何更改，则"就绪"的项目可能会变为"未就绪"。</span><span class="sxs-lookup"><span data-stu-id="f0351-119">If you later make any changes to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, items that were "Ready" can become "Not ready."</span></span> <span data-ttu-id="f0351-120">若要避免 Microsoft 托管桌面操作出现问题，请在更改任何策略之前检查本文中描述的特定设置。</span><span class="sxs-lookup"><span data-stu-id="f0351-120">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in this article before you change any policies.</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="f0351-121">Microsoft Intune 设置</span><span class="sxs-lookup"><span data-stu-id="f0351-121">Microsoft Intune settings</span></span>

<span data-ttu-id="f0351-122">可以在 Microsoft Endpoint Manager 管理中心访问 Intune [设置](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="f0351-122">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="f0351-123">Autopilot 部署配置文件</span><span class="sxs-lookup"><span data-stu-id="f0351-123">Autopilot deployment profile</span></span>

<span data-ttu-id="f0351-124">不应有任何面向已分配或动态组（使用 Microsoft 托管桌面设备）的现有 Autopilot 配置文件。</span><span class="sxs-lookup"><span data-stu-id="f0351-124">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0351-125">Microsoft 托管桌面使用 Autopilot 预配新设备。</span><span class="sxs-lookup"><span data-stu-id="f0351-125">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="f0351-126">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="f0351-126">**Not ready**</span></span>

<span data-ttu-id="f0351-127">你拥有分配给所有设备的 Autopilot 配置文件。</span><span class="sxs-lookup"><span data-stu-id="f0351-127">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="f0351-128">有关步骤，请参阅 [使用 Windows Autopilot 在 Intune](/mem/autopilot/enrollment-autopilot)中注册 Windows 设备。</span><span class="sxs-lookup"><span data-stu-id="f0351-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="f0351-129">注册 Microsoft 托管桌面后，设置 Autopilot 策略以排除 **现代工作区设备 -所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="f0351-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="f0351-130">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-130">**Advisory**</span></span>

<span data-ttu-id="f0351-131">确保 Autopilot 配置文件面向不包括 Microsoft 托管桌面设备的已分配或动态 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="f0351-131">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0351-132">有关步骤，请参阅 [使用 Windows Autopilot 在 Intune](/mem/autopilot/enrollment-autopilot)中注册 Windows 设备。</span><span class="sxs-lookup"><span data-stu-id="f0351-132">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="f0351-133">注册 Microsoft 托管桌面后，设置 Autopilot 配置文件以排除 **现代工作区设备 -所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="f0351-133">After Microsoft Managed Desktop enrollment, set your Autopilot profiles to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="f0351-134">证书连接器</span><span class="sxs-lookup"><span data-stu-id="f0351-134">Certificate connectors</span></span>

<span data-ttu-id="f0351-135">如果你有任何证书连接器将由你想要在 Microsoft 托管桌面中注册的设备使用，则连接器不应有任何错误。</span><span class="sxs-lookup"><span data-stu-id="f0351-135">If you have any certificate connectors that will be used by the devices you want to enroll in Microsoft Managed Desktop, the connectors should not have any errors.</span></span> <span data-ttu-id="f0351-136">只有以下公告之一适用于你的情况，因此请仔细检查它们。</span><span class="sxs-lookup"><span data-stu-id="f0351-136">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="f0351-137">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-137">**Advisory**</span></span>

<span data-ttu-id="f0351-138">不存在证书连接器。</span><span class="sxs-lookup"><span data-stu-id="f0351-138">No certificate connectors are present.</span></span> <span data-ttu-id="f0351-139">可能不需要任何连接器，但应评估是否需要一些连接器来建立 Microsoft 托管桌面设备的网络连接。</span><span class="sxs-lookup"><span data-stu-id="f0351-139">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity on your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0351-140">有关详细信息，请参阅准备 [Microsoft 托管桌面的证书和网络配置文件](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="f0351-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="f0351-141">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-141">**Advisory**</span></span>

<span data-ttu-id="f0351-142">至少有一个证书连接器出现错误。</span><span class="sxs-lookup"><span data-stu-id="f0351-142">At least one certificate connector has an error.</span></span> <span data-ttu-id="f0351-143">如果需要此连接器向 Microsoft 托管桌面设备提供证书，则必须解决此错误。</span><span class="sxs-lookup"><span data-stu-id="f0351-143">If you need this connector for providing certificates to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="f0351-144">有关详细信息，请参阅准备 [Microsoft 托管桌面的证书和网络配置文件](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="f0351-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="f0351-145">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-145">**Advisory**</span></span>

<span data-ttu-id="f0351-146">您至少有一个证书连接器，并且未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="f0351-146">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="f0351-147">但是，在准备部署时，可能需要创建配置文件以重用 Microsoft 托管桌面设备的连接器。</span><span class="sxs-lookup"><span data-stu-id="f0351-147">However, in preparation for deployment, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0351-148">有关详细信息，请参阅准备 [Microsoft 托管桌面的证书和网络配置文件](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="f0351-148">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="f0351-149">条件访问策略</span><span class="sxs-lookup"><span data-stu-id="f0351-149">Conditional access policies</span></span>

<span data-ttu-id="f0351-150">条件访问策略不得阻止 Microsoft 托管桌面在 Intune 和 Azure AD (租户) 管理 Azure AD 组织。</span><span class="sxs-lookup"><span data-stu-id="f0351-150">Conditional access policies must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>

<span data-ttu-id="f0351-151">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="f0351-151">**Not ready**</span></span>

<span data-ttu-id="f0351-152">您至少有一个面向所有用户的条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="f0351-152">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="f0351-153">注册期间，我们会将 Microsoft 托管桌面服务帐户从相关条件访问策略中排除，并应用新的条件访问策略来限制对这些帐户的访问。</span><span class="sxs-lookup"><span data-stu-id="f0351-153">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="f0351-154">注册后，可以在 Microsoft Endpoint Manager 中查看 Microsoft 托管桌面条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="f0351-154">After enrollment, you can review the Microsoft Managed Desktop conditional access policy in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="f0351-155">有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="f0351-155">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="f0351-156">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-156">**Advisory**</span></span>

<span data-ttu-id="f0351-157">您具有可能会阻止 Microsoft 托管桌面管理 Microsoft 托管桌面服务的条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="f0351-157">You have conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="f0351-158">注册期间，我们会将 Microsoft 托管桌面服务帐户从相关条件访问策略中排除，并应用新的条件访问策略来限制对这些帐户的访问。</span><span class="sxs-lookup"><span data-stu-id="f0351-158">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="f0351-159">有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="f0351-159">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="f0351-160">**错误**</span><span class="sxs-lookup"><span data-stu-id="f0351-160">**Error**</span></span>

<span data-ttu-id="f0351-161">Intune 管理员角色没有足够的权限进行此检查。</span><span class="sxs-lookup"><span data-stu-id="f0351-161">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="f0351-162">还需要分配以下任一 Azure AD 角色来运行此检查：</span><span class="sxs-lookup"><span data-stu-id="f0351-162">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="f0351-163">安全读取者</span><span class="sxs-lookup"><span data-stu-id="f0351-163">Security Reader</span></span>
- <span data-ttu-id="f0351-164">安全管理员</span><span class="sxs-lookup"><span data-stu-id="f0351-164">Security Administrator</span></span>
- <span data-ttu-id="f0351-165">条件访问管理员</span><span class="sxs-lookup"><span data-stu-id="f0351-165">Conditional Access Administrator</span></span>
- <span data-ttu-id="f0351-166">全局读取者</span><span class="sxs-lookup"><span data-stu-id="f0351-166">Global Reader</span></span>
- <span data-ttu-id="f0351-167">设备管理员</span><span class="sxs-lookup"><span data-stu-id="f0351-167">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="f0351-168">设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="f0351-168">Device Compliance policies</span></span>

<span data-ttu-id="f0351-169">Azure AD 组织中 Intune 设备合规性策略可能会影响 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="f0351-169">Intune Device Compliance policies in your Azure AD organization might impact Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="f0351-170">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="f0351-170">**Not ready**</span></span>

<span data-ttu-id="f0351-171">您至少有一个面向所有用户的合规性策略。</span><span class="sxs-lookup"><span data-stu-id="f0351-171">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="f0351-172">Microsoft 托管桌面包括面向 Microsoft 托管桌面设备的合规性策略。</span><span class="sxs-lookup"><span data-stu-id="f0351-172">Microsoft Managed Desktop includes compliance policies that will target your Microsoft Managed Desktop devices.</span></span>  <span data-ttu-id="f0351-173">将策略更改为面向不包含任何 Microsoft 托管桌面用户或设备的特定 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="f0351-173">Change the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users or devices.</span></span> <span data-ttu-id="f0351-174">有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="f0351-174">For steps, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="f0351-175">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-175">**Advisory**</span></span>

<span data-ttu-id="f0351-176">确保你拥有的任何合规性策略不面向任何 Microsoft 托管桌面用户。</span><span class="sxs-lookup"><span data-stu-id="f0351-176">Make sure that any compliance policies you have don't target any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="f0351-177">有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="f0351-177">For steps, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-profiles"></a><span data-ttu-id="f0351-178">设备配置文件</span><span class="sxs-lookup"><span data-stu-id="f0351-178">Device Configuration profiles</span></span>

<span data-ttu-id="f0351-179">Azure AD 组织中 Intune 设备配置文件不得面向任何 Microsoft 管理桌面设备或用户。</span><span class="sxs-lookup"><span data-stu-id="f0351-179">Intune Device Configuration profiles in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="f0351-180">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="f0351-180">**Not ready**</span></span>

<span data-ttu-id="f0351-181">你至少具有一个面向所有用户和/或所有设备的配置文件。</span><span class="sxs-lookup"><span data-stu-id="f0351-181">You have at least one configuration profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="f0351-182">重置配置文件以面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="f0351-182">Reset the profile to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0351-183">有关步骤，请参阅 [使用 Microsoft Intune 中的自定义设置创建配置文件](/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="f0351-183">For steps, see [Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="f0351-184">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-184">**Advisory**</span></span>

<span data-ttu-id="f0351-185">确保你拥有的任何配置策略不包括任何 Microsoft 托管桌面设备或用户。</span><span class="sxs-lookup"><span data-stu-id="f0351-185">Make sure that any configuration policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="f0351-186">有关步骤，请参阅 [使用 Microsoft Intune 中的自定义设置创建配置文件](/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="f0351-186">For steps, see [Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="f0351-187">设备类型限制</span><span class="sxs-lookup"><span data-stu-id="f0351-187">Device type restrictions</span></span>

<span data-ttu-id="f0351-188">必须允许 Microsoft 托管桌面设备在 Intune 中注册。</span><span class="sxs-lookup"><span data-stu-id="f0351-188">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="f0351-189">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="f0351-189">**Not ready**</span></span>

<span data-ttu-id="f0351-190">你当前至少配置了一个注册限制策略，以防止 Windows 设备在 Intune 中注册。</span><span class="sxs-lookup"><span data-stu-id="f0351-190">You currently have at least one enrollment restriction policy configured to prevent Windows devices from enrollment in Intune.</span></span> <span data-ttu-id="f0351-191">按照针对 Microsoft 托管桌面 [用户](/mem/intune/enrollment/enrollment-restrictions-set) 的每个注册限制策略设置注册限制中的步骤操作，将 **Windows (MDM)** 设置为 **允许**。</span><span class="sxs-lookup"><span data-stu-id="f0351-191">Follow the steps in [Set enrollment restrictions](/mem/intune/enrollment/enrollment-restrictions-set) for each enrollment restriction policy that targets Microsoft Managed Desktop users and change the **Windows (MDM)** setting to **Allow**.</span></span> <span data-ttu-id="f0351-192">但是，你可以将个人拥有的任何 **Windows (MDM)** 设置为 **阻止**。</span><span class="sxs-lookup"><span data-stu-id="f0351-192">You can, however, set any **personally owned** **Windows (MDM)** devices to **Block**.</span></span> 


### <a name="enrollment-status-page"></a><span data-ttu-id="f0351-193">注册状态页</span><span class="sxs-lookup"><span data-stu-id="f0351-193">Enrollment Status Page</span></span>

<span data-ttu-id="f0351-194">YOU currently have the Enrollment Status Page (ESP) enabled.</span><span class="sxs-lookup"><span data-stu-id="f0351-194">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="f0351-195">如果你打算参与此功能的 Microsoft 托管桌面公共预览版，可以忽略此项。</span><span class="sxs-lookup"><span data-stu-id="f0351-195">If you intend to participate in the Microsoft Managed Desktop public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="f0351-196">有关详细信息，请参阅 [Autopilot 首次运行体验和注册状态页面](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="f0351-196">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="f0351-197">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="f0351-197">**Not ready**</span></span>

<span data-ttu-id="f0351-198">将 ESP 默认配置文件设置为"**显示应用和配置文件配置进度"。**</span><span class="sxs-lookup"><span data-stu-id="f0351-198">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="f0351-199">通过按照设置注册状态页 中的步骤操作，禁用此设置或确保任何 Azure AD 组的工作分配不包括 Microsoft 托管 [桌面设备](/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="f0351-199">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="f0351-200">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-200">**Advisory**</span></span>

<span data-ttu-id="f0351-201">确保未将具有"显示应用和配置文件配置进度"设置的任何配置文件分配给任何包含 Microsoft 托管桌面设备的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="f0351-201">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0351-202">有关详细信息，请参阅设置 [注册状态页](/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="f0351-202">For more information, see [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="microsoft-store-for-business"></a><span data-ttu-id="f0351-203">适用于企业的 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="f0351-203">Microsoft Store for Business</span></span>

<span data-ttu-id="f0351-204">我们使用适用于 Business 的 Microsoft Store，在 Microsoft 托管桌面上部署公司门户应用，以允许用户选择安装某些应用，如 Microsoft Project 和 Microsoft Visio (（如果允许) ）。</span><span class="sxs-lookup"><span data-stu-id="f0351-204">We use Microsoft Store for Business and deploy the Company Portal app on Microsoft Managed Desktop to allow users to optionally install some apps, such as Microsoft Project and Microsoft Visio (where permitted).</span></span>

<span data-ttu-id="f0351-205">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="f0351-205">**Not ready**</span></span>

<span data-ttu-id="f0351-206">适用于 Business 的 Microsoft Store 未启用或未与 Intune 同步。</span><span class="sxs-lookup"><span data-stu-id="f0351-206">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="f0351-207">有关详细信息，请参阅如何使用 [Microsoft Intune](/mem/intune/apps/windows-store-for-business) 管理从适用于企业 Microsoft Store 购买的批量应用和在设备上安装 [Intune 公司门户](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="f0351-207">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on devices](../get-started/company-portal.md).</span></span>

### <a name="multifactor-authentication"></a><span data-ttu-id="f0351-208">多重身份验证</span><span class="sxs-lookup"><span data-stu-id="f0351-208">Multifactor authentication</span></span>

<span data-ttu-id="f0351-209">多重身份验证不得阻止 Microsoft 托管桌面在 Intune 和 Azure AD (托管) 管理 Azure AD 组织。</span><span class="sxs-lookup"><span data-stu-id="f0351-209">Multifactor authentication must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>


<span data-ttu-id="f0351-210">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="f0351-210">**Not ready**</span></span>

<span data-ttu-id="f0351-211">您具有为分配给所有用户的条件 **访问策略所需的** 一些多重身份验证策略。</span><span class="sxs-lookup"><span data-stu-id="f0351-211">You have some multifactor authentication policies set as **required** for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="f0351-212">注册期间，我们会将 Microsoft 托管桌面服务帐户从相关条件访问策略中排除，并应用新的条件访问策略来限制对这些帐户的访问。</span><span class="sxs-lookup"><span data-stu-id="f0351-212">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="f0351-213">有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="f0351-213">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="f0351-214">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-214">**Advisory**</span></span>

<span data-ttu-id="f0351-215">对于可能阻止 Microsoft 托管桌面管理 Microsoft 托管桌面服务的条件访问策略，您需要进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="f0351-215">You have multifactor authentication required on conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="f0351-216">注册期间，我们会将 Microsoft 托管桌面服务帐户从相关条件访问策略中排除，并应用新的条件访问策略来限制对这些帐户的访问。</span><span class="sxs-lookup"><span data-stu-id="f0351-216">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="f0351-217">有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="f0351-217">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="f0351-218">**错误**</span><span class="sxs-lookup"><span data-stu-id="f0351-218">**Error**</span></span>

<span data-ttu-id="f0351-219">Intune 管理员角色没有足够的权限进行此检查。</span><span class="sxs-lookup"><span data-stu-id="f0351-219">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="f0351-220">还需要分配以下任一 Azure AD 角色来运行此检查：</span><span class="sxs-lookup"><span data-stu-id="f0351-220">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="f0351-221">安全读取者</span><span class="sxs-lookup"><span data-stu-id="f0351-221">Security Reader</span></span>
- <span data-ttu-id="f0351-222">安全管理员</span><span class="sxs-lookup"><span data-stu-id="f0351-222">Security Administrator</span></span>
- <span data-ttu-id="f0351-223">条件访问管理员</span><span class="sxs-lookup"><span data-stu-id="f0351-223">Conditional Access Administrator</span></span>
- <span data-ttu-id="f0351-224">全局读取者</span><span class="sxs-lookup"><span data-stu-id="f0351-224">Global Reader</span></span>
- <span data-ttu-id="f0351-225">设备管理员</span><span class="sxs-lookup"><span data-stu-id="f0351-225">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="f0351-226">PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="f0351-226">PowerShell scripts</span></span>

<span data-ttu-id="f0351-227">Windows PowerShell脚本无法以面向 Microsoft 托管桌面设备的方式分配。</span><span class="sxs-lookup"><span data-stu-id="f0351-227">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="f0351-228">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-228">**Advisory**</span></span>

<span data-ttu-id="f0351-229">请确保 Azure AD Windows PowerShell中的脚本不面向任何 Microsoft 管理桌面设备或用户。</span><span class="sxs-lookup"><span data-stu-id="f0351-229">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="f0351-230">不要将 PowerShell 脚本分配给所有用户、所有设备或两者。</span><span class="sxs-lookup"><span data-stu-id="f0351-230">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="f0351-231">更改策略以使用面向不包括任何 Microsoft 托管桌面设备或用户的特定 Azure AD 组的分配。</span><span class="sxs-lookup"><span data-stu-id="f0351-231">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="f0351-232">有关详细信息，请参阅在 [Intune 中的 Windows 10 设备上使用 PowerShell 脚本](/mem/intune/apps/intune-management-extension)。</span><span class="sxs-lookup"><span data-stu-id="f0351-232">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="f0351-233">地区</span><span class="sxs-lookup"><span data-stu-id="f0351-233">Region</span></span>

<span data-ttu-id="f0351-234">你的区域必须受 Microsoft 托管桌面支持。</span><span class="sxs-lookup"><span data-stu-id="f0351-234">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="f0351-235">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="f0351-235">**Not ready**</span></span>

<span data-ttu-id="f0351-236">你的 Azure AD 组织区域当前不受 Microsoft 托管桌面支持。</span><span class="sxs-lookup"><span data-stu-id="f0351-236">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="f0351-237">有关详细信息，请参阅 [Microsoft 托管桌面支持的地区和语言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="f0351-237">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="f0351-238">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-238">**Advisory**</span></span>

<span data-ttu-id="f0351-239">Microsoft 托管桌面不支持 Azure AD 组织所在的一个或多个国家/地区。</span><span class="sxs-lookup"><span data-stu-id="f0351-239">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="f0351-240">有关详细信息，请参阅 [Microsoft 托管桌面支持的地区和语言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="f0351-240">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="f0351-241">安全基线</span><span class="sxs-lookup"><span data-stu-id="f0351-241">Security baselines</span></span>

<span data-ttu-id="f0351-242">安全基线策略不应面向任何 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="f0351-242">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="f0351-243">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="f0351-243">**Not ready**</span></span>

<span data-ttu-id="f0351-244">你有一个面向所有用户、所有设备或两者的安全基线配置文件。</span><span class="sxs-lookup"><span data-stu-id="f0351-244">You have a security baseline profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="f0351-245">更改策略以使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的分配。</span><span class="sxs-lookup"><span data-stu-id="f0351-245">Change the policy to use an assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0351-246">有关步骤，请参阅 [使用安全基线在 Intune](/mem/intune/protect/security-baselines)中配置 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="f0351-246">For steps, see [Use security baselines to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="f0351-247">注册期间，我们会将新的安全基线应用于所有 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="f0351-247">During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0351-248">注册后，可以在 Microsoft Endpoint Manager 的配置策略区域中查看Microsoft 托管桌面安全基线策略。</span><span class="sxs-lookup"><span data-stu-id="f0351-248">After enrollment, you can review the Microsoft Managed Desktop security baseline policy in the **Configuration policy** area of Microsoft Endpoint Manager.</span></span>

<span data-ttu-id="f0351-249">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-249">**Advisory**</span></span>

<span data-ttu-id="f0351-250">确保已排除 Microsoft 托管桌面设备的任何安全基线策略。</span><span class="sxs-lookup"><span data-stu-id="f0351-250">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0351-251">有关步骤，请参阅 [使用安全基线在 Intune](/mem/intune/protect/security-baselines)中配置 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="f0351-251">For steps, see [Use security baselines to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="f0351-252">注册期间，我们会将新的安全基线应用于所有 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="f0351-252">During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0351-253">现代 **工作区设备 - 所有** Azure AD 组是注册 Microsoft 托管桌面时创建的动态组，因此你必须在注册后返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="f0351-253">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span> 


### <a name="windows-apps"></a><span data-ttu-id="f0351-254">Windows 应用</span><span class="sxs-lookup"><span data-stu-id="f0351-254">Windows apps</span></span>

<span data-ttu-id="f0351-255">查看希望 Microsoft 托管桌面用户拥有的应用。</span><span class="sxs-lookup"><span data-stu-id="f0351-255">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="f0351-256">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-256">**Advisory**</span></span>

<span data-ttu-id="f0351-257">应准备希望 Microsoft 托管桌面用户拥有的应用清单。</span><span class="sxs-lookup"><span data-stu-id="f0351-257">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="f0351-258">由于这些应用必须由 Intune 部署，因此请评估是否重新使用现有 Intune 应用。</span><span class="sxs-lookup"><span data-stu-id="f0351-258">Since these apps must be deployed by Intune, evaluate reusing existing Intune apps.</span></span> <span data-ttu-id="f0351-259">请考虑使用公司门户 (在设备上安装 [Intune 公司](../get-started/company-portal.md) 门户和注册状态页 (ESP) 将应用分发到用户。</span><span class="sxs-lookup"><span data-stu-id="f0351-259">Consider using Company Portal (see [Install Intune Company Portal on devices](../get-started/company-portal.md) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="f0351-260">有关详细信息，请参阅 [Microsoft 托管桌面](apps.md) 中的应用和 Autopilot 的首次运行体验和 [注册状态页面](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="f0351-260">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="f0351-261">你可以要求 Microsoft 帐户代表在 Microsoft Endpoint Configuration Manager 中查询，以确定准备迁移到 Intune 或需要调整的应用。</span><span class="sxs-lookup"><span data-stu-id="f0351-261">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="f0351-262">Windows Hello 企业版</span><span class="sxs-lookup"><span data-stu-id="f0351-262">Windows Hello for Business</span></span>

<span data-ttu-id="f0351-263">Microsoft 托管桌面需要启用 Windows Hello 企业版。</span><span class="sxs-lookup"><span data-stu-id="f0351-263">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="f0351-264">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="f0351-264">**Not ready**</span></span>

<span data-ttu-id="f0351-265">Windows Hello 企业应用已禁用。</span><span class="sxs-lookup"><span data-stu-id="f0351-265">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="f0351-266">按照创建 Windows Hello 企业策略 [中的步骤启用它](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="f0351-266">Enable it by following the steps in [Create a Windows Hello for Business policy](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="f0351-267">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-267">**Advisory**</span></span>

<span data-ttu-id="f0351-268">未设置 Windows Hello 企业版本。</span><span class="sxs-lookup"><span data-stu-id="f0351-268">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="f0351-269">按照创建 Windows Hello 企业策略 [中的步骤启用它](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)。</span><span class="sxs-lookup"><span data-stu-id="f0351-269">Enable it by following the steps in [Create a Windows Hello for Business policy](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="f0351-270">Windows 10 更新圈</span><span class="sxs-lookup"><span data-stu-id="f0351-270">Windows 10 update rings</span></span>

<span data-ttu-id="f0351-271">Intune 中的"Windows 10 更新圈"策略不得面向任何 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="f0351-271">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="f0351-272">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="f0351-272">**Not ready**</span></span>

<span data-ttu-id="f0351-273">你有一个面向所有设备、所有用户或两者同时面向的"更新圈"策略。</span><span class="sxs-lookup"><span data-stu-id="f0351-273">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="f0351-274">将策略更改为使用面向不包括任何 Microsoft 托管桌面设备的特定 Azure AD 组的分配。</span><span class="sxs-lookup"><span data-stu-id="f0351-274">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0351-275">有关步骤，请参阅在 Intune 中管理 [Windows 10 软件更新](/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="f0351-275">For steps, see [Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="f0351-276">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-276">**Advisory**</span></span>

<span data-ttu-id="f0351-277">确保你拥有的任何更新圈策略不包括现代 **工作区设备 -所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="f0351-277">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="f0351-278">如果你已向这些策略分配了 Azure AD 用户组，请确保你已排除所有更新圈策略，并且你已排除将 Microsoft 托管桌面用户添加到 (或等效组) 的新式工作区 **-** 所有 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="f0351-278">If you have assigned Azure AD user groups to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group that you add your Microsoft Managed Desktop users to (or an equivalent group).</span></span> <span data-ttu-id="f0351-279">有关步骤，请参阅在 Intune 中管理 [Windows 10 软件更新](/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="f0351-279">For steps, see [Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="f0351-280">现代 **工作区设备 -全部** 和现代工作区 **-所有** Azure AD 组都是我们在注册 Microsoft 托管桌面时创建的组，因此你必须在注册后返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="f0351-280">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="f0351-281">Azure Active Directory 设置</span><span class="sxs-lookup"><span data-stu-id="f0351-281">Azure Active Directory settings</span></span>

<span data-ttu-id="f0351-282">可以在 Azure 门户访问 Azure Active Directory [设置](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="f0351-282">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="f0351-283">Intune 注册</span><span class="sxs-lookup"><span data-stu-id="f0351-283">Intune enrollment</span></span>

<span data-ttu-id="f0351-284">Azure AD 组织的 Windows 10 设备必须能够在 Intune 中自动注册。</span><span class="sxs-lookup"><span data-stu-id="f0351-284">Windows 10 devices in your Azure AD organization must be able to automatically enroll in Intune.</span></span>

<span data-ttu-id="f0351-285">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-285">**Advisory**</span></span>

<span data-ttu-id="f0351-286">确保 MDM **用户作用域设置为**"部分"**或"\*\*\*\*全部"，** 而不是"**无"。**</span><span class="sxs-lookup"><span data-stu-id="f0351-286">Make sure the **MDM User scope** is set to **Some** or **All**, not **None**.</span></span> <span data-ttu-id="f0351-287">如果选择"**一些**"，请在注册后返回，然后为组选择"新式 **工作区 -** 所有Azure AD"组，或选择面向所有 Microsoft 托管桌面用户的等效组。</span><span class="sxs-lookup"><span data-stu-id="f0351-287">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups** or an equivalent group targeting all of your Microsoft Managed Desktop users.</span></span>  <span data-ttu-id="f0351-288">请参阅 [使用 Microsoft Intune 设置 Windows 设备的注册](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="f0351-288">See [Set up enrollment for Windows devices by using Microsoft Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment).</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="f0351-289">临时订阅</span><span class="sxs-lookup"><span data-stu-id="f0351-289">Ad hoc subscriptions</span></span>

<span data-ttu-id="f0351-290">建议如何检查设置，如果 (设置为"false"，) 可能会阻止企业状态漫游正常工作。</span><span class="sxs-lookup"><span data-stu-id="f0351-290">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="f0351-291">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-291">**Advisory**</span></span>

<span data-ttu-id="f0351-292">确保 **AllowAdHocSubscriptions** 设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="f0351-292">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="f0351-293">否则，企业状态漫游可能无法工作。</span><span class="sxs-lookup"><span data-stu-id="f0351-293">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="f0351-294">有关详细信息，请参阅 [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="f0351-294">For more information, see [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="f0351-295">企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="f0351-295">Enterprise State Roaming</span></span>

<span data-ttu-id="f0351-296">应启用企业状态漫游。</span><span class="sxs-lookup"><span data-stu-id="f0351-296">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="f0351-297">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-297">**Advisory**</span></span>

<span data-ttu-id="f0351-298">确保为"全部"或" **所选组"** 启用企业状态 **漫游** 。</span><span class="sxs-lookup"><span data-stu-id="f0351-298">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="f0351-299">有关详细信息，请参阅在 [Azure Active Directory 中启用企业状态漫游](/azure/active-directory/devices/enterprise-state-roaming-enable)。</span><span class="sxs-lookup"><span data-stu-id="f0351-299">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="f0351-300">许可证</span><span class="sxs-lookup"><span data-stu-id="f0351-300">Licenses</span></span>

<span data-ttu-id="f0351-301">使用 Microsoft 托管桌面需要大量许可证。</span><span class="sxs-lookup"><span data-stu-id="f0351-301">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="f0351-302">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="f0351-302">**Not Ready**</span></span>

<span data-ttu-id="f0351-303">你没有使用 Microsoft 托管桌面所需的全部许可证。</span><span class="sxs-lookup"><span data-stu-id="f0351-303">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="f0351-304">有关详细信息，请参阅[Microsoft 托管桌面技术和](../intro/technologies.md)[有关许可证的更多内容](prerequisites.md#more-about-licenses)。</span><span class="sxs-lookup"><span data-stu-id="f0351-304">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="microsoft-managed-desktop-service-accounts"></a><span data-ttu-id="f0351-305">Microsoft 托管桌面服务帐户</span><span class="sxs-lookup"><span data-stu-id="f0351-305">Microsoft Managed Desktop service accounts</span></span>

<span data-ttu-id="f0351-306">某些帐户名可能会与 Microsoft 托管桌面创建用于管理 Microsoft 托管桌面服务的帐户名称冲突。</span><span class="sxs-lookup"><span data-stu-id="f0351-306">Certain account names could conflict with account names created by Microsoft Managed Desktop to manage the Microsoft Managed Desktop service.</span></span>

<span data-ttu-id="f0351-307">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="f0351-307">**Not ready**</span></span>

<span data-ttu-id="f0351-308">您至少有一个与 Microsoft 托管桌面创建的帐户名称相冲突的帐户名称。</span><span class="sxs-lookup"><span data-stu-id="f0351-308">You have at least one account name that will conflict with account names created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="f0351-309">与 Microsoft 帐户代表合作，排除这些帐户名。</span><span class="sxs-lookup"><span data-stu-id="f0351-309">Work with your Microsoft account representative to exclude these account names.</span></span> <span data-ttu-id="f0351-310">我们不会公开列出帐户名称，以最大限度地降低安全风险。</span><span class="sxs-lookup"><span data-stu-id="f0351-310">We don't list the account names publicly to minimize security risk.</span></span> 


### <a name="security-administrator-roles"></a><span data-ttu-id="f0351-311">安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="f0351-311">Security administrator roles</span></span>

<span data-ttu-id="f0351-312">具有特定安全角色的用户必须在 Microsoft Defender for Endpoint 中分配这些角色。</span><span class="sxs-lookup"><span data-stu-id="f0351-312">Users with certain security roles must have those roles assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="f0351-313">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-313">**Advisory**</span></span>

<span data-ttu-id="f0351-314">如果你的用户已分配到 Azure AD 组织中任何这些角色，请确保他们在 Microsoft Defender for Endpoint 中也分配了这些角色。</span><span class="sxs-lookup"><span data-stu-id="f0351-314">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="f0351-315">否则，具有这些角色的管理员将无法访问管理门户。</span><span class="sxs-lookup"><span data-stu-id="f0351-315">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="f0351-316">安全操作员</span><span class="sxs-lookup"><span data-stu-id="f0351-316">Security Operator</span></span>
- <span data-ttu-id="f0351-317">全局读取者</span><span class="sxs-lookup"><span data-stu-id="f0351-317">Global Reader</span></span>

<span data-ttu-id="f0351-318">有关详细信息，请参阅为基于角色 [的访问控制创建和管理角色](/windows/security/threat-protection/microsoft-defender-atp/user-roles)。</span><span class="sxs-lookup"><span data-stu-id="f0351-318">For more information, see [Create and manage roles for role-based access control](/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="f0351-319">安全默认值</span><span class="sxs-lookup"><span data-stu-id="f0351-319">Security default</span></span>

<span data-ttu-id="f0351-320">Azure Active Directory 中的安全默认值将阻止 Microsoft 托管桌面管理设备。</span><span class="sxs-lookup"><span data-stu-id="f0351-320">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="f0351-321">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="f0351-321">**Not ready**</span></span>

<span data-ttu-id="f0351-322">你已打开"安全性默认值"。</span><span class="sxs-lookup"><span data-stu-id="f0351-322">You have Security defaults turned on.</span></span> <span data-ttu-id="f0351-323">关闭安全默认值并设置条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="f0351-323">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="f0351-324">有关详细信息，请参阅 Common [Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。</span><span class="sxs-lookup"><span data-stu-id="f0351-324">For more information, see [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="f0351-325">自助服务密码重置</span><span class="sxs-lookup"><span data-stu-id="f0351-325">Self-service Password Reset</span></span>

<span data-ttu-id="f0351-326">SSPR (SSPR) 可以启用所有 Microsoft 托管桌面用户（不包括 Microsoft 托管桌面服务帐户）。</span><span class="sxs-lookup"><span data-stu-id="f0351-326">Self-service Password Reset (SSPR) can be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="f0351-327">有关详细信息，请参阅教程： [允许用户使用 Azure Active Directory](/azure/active-directory/authentication/tutorial-enable-sspr)自助服务密码重置解锁其帐户或重置密码。</span><span class="sxs-lookup"><span data-stu-id="f0351-327">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="f0351-328">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-328">**Advisory**</span></span>

<span data-ttu-id="f0351-329">确保"SSPR **选择** "设置包括 Microsoft 托管桌面用户，但不包括 Microsoft 托管桌面服务帐户。</span><span class="sxs-lookup"><span data-stu-id="f0351-329">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop users but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="f0351-330">启用 SSPR 后，Microsoft 托管桌面服务帐户无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="f0351-330">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="f0351-331">标准用户角色</span><span class="sxs-lookup"><span data-stu-id="f0351-331">Standard user role</span></span>

<span data-ttu-id="f0351-332">除了分配了全局管理员和设备管理员的 Azure AD 角色的用户外，Microsoft 托管桌面用户将是没有本地管理员权限的标准用户。</span><span class="sxs-lookup"><span data-stu-id="f0351-332">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="f0351-333">当所有其他用户启动其 Microsoft 托管桌面设备时，将为其分配标准用户角色。</span><span class="sxs-lookup"><span data-stu-id="f0351-333">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="f0351-334">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-334">**Advisory**</span></span>

<span data-ttu-id="f0351-335">注册后，Microsoft 托管桌面用户将没有 Microsoft 托管桌面设备的本地管理员权限。</span><span class="sxs-lookup"><span data-stu-id="f0351-335">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="f0351-336">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="f0351-336">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="f0351-337">OneDrive</span><span class="sxs-lookup"><span data-stu-id="f0351-337">OneDrive</span></span>

<span data-ttu-id="f0351-338">" **仅允许在加入特定域** 的 PC 上同步"设置将与 Microsoft 托管桌面冲突。</span><span class="sxs-lookup"><span data-stu-id="f0351-338">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="f0351-339">可以在 OneDrive 管理中心访问 OneDrive [设置](https://admin.onedrive.com)。</span><span class="sxs-lookup"><span data-stu-id="f0351-339">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="f0351-340">**公告**</span><span class="sxs-lookup"><span data-stu-id="f0351-340">**Advisory**</span></span>

<span data-ttu-id="f0351-341">你正在使用" **仅允许在加入特定域的 PC 上同步"** 设置。</span><span class="sxs-lookup"><span data-stu-id="f0351-341">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="f0351-342">此设置将不能用于 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="f0351-342">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="f0351-343">禁用此设置，改为将 OneDrive 设置为使用条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="f0351-343">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="f0351-344">请参阅 [规划条件访问部署](/azure/active-directory/conditional-access/plan-conditional-access) 获取帮助。</span><span class="sxs-lookup"><span data-stu-id="f0351-344">See [Plan a Conditional Access deployment](/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>