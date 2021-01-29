---
title: 修复准备情况评估工具发现的问题
description: 针对工具找到的每个问题要执行的详细操作
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 360cd50556b77f141d1585f42ac08ee5990b4851
ms.sourcegitcommit: f3059a0065496623e36e5a084cd2291e6b844597
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "50040516"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="27424-104">修复准备情况评估工具发现的问题</span><span class="sxs-lookup"><span data-stu-id="27424-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="27424-105">对于每个检查，该工具将报告四个可能的结果之一：</span><span class="sxs-lookup"><span data-stu-id="27424-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="27424-106">结果</span><span class="sxs-lookup"><span data-stu-id="27424-106">Result</span></span>  |<span data-ttu-id="27424-107">含义</span><span class="sxs-lookup"><span data-stu-id="27424-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="27424-108">Ready</span><span class="sxs-lookup"><span data-stu-id="27424-108">Ready</span></span>     | <span data-ttu-id="27424-109">完成注册前无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="27424-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="27424-110">公告</span><span class="sxs-lookup"><span data-stu-id="27424-110">Advisory</span></span>    | <span data-ttu-id="27424-111">按照工具或本文中的步骤操作，获得注册和用户的最佳体验。</span><span class="sxs-lookup"><span data-stu-id="27424-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="27424-112">*你可以完成* 注册，但在部署第一台设备之前必须解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="27424-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="27424-113">未就绪</span><span class="sxs-lookup"><span data-stu-id="27424-113">Not ready</span></span> | <span data-ttu-id="27424-114">*如果不解决这些问题，注册将失败。*</span><span class="sxs-lookup"><span data-stu-id="27424-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="27424-115">按照工具或本文中的步骤进行解析。</span><span class="sxs-lookup"><span data-stu-id="27424-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="27424-116">错误</span><span class="sxs-lookup"><span data-stu-id="27424-116">Error</span></span> | <span data-ttu-id="27424-117">Azure Active Directory (AD) 角色没有足够的权限来运行此检查。</span><span class="sxs-lookup"><span data-stu-id="27424-117">The Azure Active Directory (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

> [!NOTE]
> <span data-ttu-id="27424-118">此工具报告的结果仅在运行设置的特定时间点反映设置的状态。</span><span class="sxs-lookup"><span data-stu-id="27424-118">The results reported by this tool reflect the status of your settings only at the specific point in time that you ran it.</span></span> <span data-ttu-id="27424-119">如果稍后对 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的策略进行了任何更改，则"就绪"的项目可能会变为"未准备就绪"。</span><span class="sxs-lookup"><span data-stu-id="27424-119">If you later make any changes to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, items that were "Ready" can become "Not ready."</span></span> <span data-ttu-id="27424-120">若要避免 Microsoft 托管桌面操作出现问题，请在更改任何策略之前检查本文中描述的特定设置。</span><span class="sxs-lookup"><span data-stu-id="27424-120">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in this article before you change any policies.</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="27424-121">Microsoft Intune 设置</span><span class="sxs-lookup"><span data-stu-id="27424-121">Microsoft Intune settings</span></span>

<span data-ttu-id="27424-122">可以在 Microsoft Endpoint Manager 管理中心访问 Intune [设置](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="27424-122">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="27424-123">Autopilot 部署配置文件</span><span class="sxs-lookup"><span data-stu-id="27424-123">Autopilot deployment profile</span></span>

<span data-ttu-id="27424-124">你不应具有任何面向已分配或具有 Microsoft 托管桌面设备的动态组的现有 Autopilot 配置文件。</span><span class="sxs-lookup"><span data-stu-id="27424-124">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="27424-125">Microsoft 托管桌面使用 Autopilot 预配新设备。</span><span class="sxs-lookup"><span data-stu-id="27424-125">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="27424-126">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="27424-126">**Not ready**</span></span>

<span data-ttu-id="27424-127">你拥有分配给所有设备的 Autopilot 配置文件。</span><span class="sxs-lookup"><span data-stu-id="27424-127">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="27424-128">有关步骤，请参阅 [使用 Windows Autopilot 在 Intune 中注册 Windows 设备](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="27424-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="27424-129">注册 Microsoft 托管桌面后，设置 Autopilot 策略以排除 **现代工作区设备 -所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="27424-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="27424-130">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-130">**Advisory**</span></span>

<span data-ttu-id="27424-131">确保 Autopilot 配置文件面向不包括 Microsoft 托管桌面设备的已分配或动态 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="27424-131">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="27424-132">有关步骤，请参阅 [使用 Windows Autopilot 在 Intune 中注册 Windows 设备](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="27424-132">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="27424-133">注册 Microsoft 托管桌面后，将 Autopilot 配置文件设置为排除 **现代工作区设备 -所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="27424-133">After Microsoft Managed Desktop enrollment, set your Autopilot profiles to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="27424-134">证书连接器</span><span class="sxs-lookup"><span data-stu-id="27424-134">Certificate connectors</span></span>

<span data-ttu-id="27424-135">如果有要注册到 Microsoft 托管桌面的设备使用的任何证书连接器，则连接器不应有任何错误。</span><span class="sxs-lookup"><span data-stu-id="27424-135">If you have any certificate connectors that will be used by the devices you want to enroll in Microsoft Managed Desktop, the connectors should not have any errors.</span></span> <span data-ttu-id="27424-136">只有下列公告之一适用于你的情况，因此请仔细检查。</span><span class="sxs-lookup"><span data-stu-id="27424-136">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="27424-137">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-137">**Advisory**</span></span>

<span data-ttu-id="27424-138">不存在证书连接器。</span><span class="sxs-lookup"><span data-stu-id="27424-138">No certificate connectors are present.</span></span> <span data-ttu-id="27424-139">你可能不需要任何连接器，但应评估是否需要一些连接器来建立 Microsoft 托管桌面设备的网络连接。</span><span class="sxs-lookup"><span data-stu-id="27424-139">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity on your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="27424-140">有关详细信息，请参阅为 [Microsoft 托管桌面准备证书和网络配置文件](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="27424-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="27424-141">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-141">**Advisory**</span></span>

<span data-ttu-id="27424-142">至少有一个证书连接器出错。</span><span class="sxs-lookup"><span data-stu-id="27424-142">At least one certificate connector has an error.</span></span> <span data-ttu-id="27424-143">如果需要此连接器向 Microsoft 托管桌面设备提供证书，则必须解决此错误。</span><span class="sxs-lookup"><span data-stu-id="27424-143">If you need this connector for providing certificates to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="27424-144">有关详细信息，请参阅为 [Microsoft 托管桌面准备证书和网络配置文件](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="27424-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="27424-145">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-145">**Advisory**</span></span>

<span data-ttu-id="27424-146">您至少有一个证书连接器，并且未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="27424-146">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="27424-147">但是，在准备部署时，可能需要创建配置文件以将连接器重新用于 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="27424-147">However, in preparation for deployment, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="27424-148">有关详细信息，请参阅为 [Microsoft 托管桌面准备证书和网络配置文件](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="27424-148">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="27424-149">条件访问策略</span><span class="sxs-lookup"><span data-stu-id="27424-149">Conditional access policies</span></span>

<span data-ttu-id="27424-150">条件访问策略不得阻止 Microsoft 托管桌面在 Intune 和 Azure AD (租户) 管理 Azure AD 组织。</span><span class="sxs-lookup"><span data-stu-id="27424-150">Conditional access policies must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>

<span data-ttu-id="27424-151">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="27424-151">**Not ready**</span></span>

<span data-ttu-id="27424-152">您至少有一个面向所有用户的条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="27424-152">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="27424-153">在注册期间，我们将从相关条件访问策略中排除 Microsoft Managed Desktop Service 帐户，并应用新的条件访问策略来限制对这些帐户的访问。</span><span class="sxs-lookup"><span data-stu-id="27424-153">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="27424-154">注册后，可以在 Microsoft Endpoint Manager 中查看 Microsoft 托管桌面条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="27424-154">After enrollment, you can review the Microsoft Managed Desktop conditional access policy in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="27424-155">有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="27424-155">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="27424-156">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-156">**Advisory**</span></span>

<span data-ttu-id="27424-157">您具有可能会阻止 Microsoft 托管桌面管理 Microsoft 托管桌面服务的条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="27424-157">You have conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="27424-158">在注册期间，我们将从相关条件访问策略中排除 Microsoft Managed Desktop Service 帐户，并应用新的条件访问策略来限制对这些帐户的访问。</span><span class="sxs-lookup"><span data-stu-id="27424-158">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="27424-159">有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="27424-159">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="27424-160">**错误**</span><span class="sxs-lookup"><span data-stu-id="27424-160">**Error**</span></span>

<span data-ttu-id="27424-161">Intune 管理员角色没有足够的权限进行此检查。</span><span class="sxs-lookup"><span data-stu-id="27424-161">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="27424-162">你还需要分配有以下任一 Azure AD 角色来运行此检查：</span><span class="sxs-lookup"><span data-stu-id="27424-162">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="27424-163">安全读取者</span><span class="sxs-lookup"><span data-stu-id="27424-163">Security Reader</span></span>
- <span data-ttu-id="27424-164">安全管理员</span><span class="sxs-lookup"><span data-stu-id="27424-164">Security Administrator</span></span>
- <span data-ttu-id="27424-165">条件访问管理员</span><span class="sxs-lookup"><span data-stu-id="27424-165">Conditional Access Administrator</span></span>
- <span data-ttu-id="27424-166">全局读取者</span><span class="sxs-lookup"><span data-stu-id="27424-166">Global Reader</span></span>
- <span data-ttu-id="27424-167">设备管理员</span><span class="sxs-lookup"><span data-stu-id="27424-167">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="27424-168">设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="27424-168">Device Compliance policies</span></span>

<span data-ttu-id="27424-169">Azure AD 组织中 Intune 设备合规性策略可能会影响 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="27424-169">Intune Device Compliance policies in your Azure AD organization might impact Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="27424-170">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="27424-170">**Not ready**</span></span>

<span data-ttu-id="27424-171">您至少有一个面向所有用户的合规性策略。</span><span class="sxs-lookup"><span data-stu-id="27424-171">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="27424-172">Microsoft 托管桌面包括面向 Microsoft 托管桌面设备的合规性策略。</span><span class="sxs-lookup"><span data-stu-id="27424-172">Microsoft Managed Desktop includes compliance policies that will target your Microsoft Managed Desktop devices.</span></span>  <span data-ttu-id="27424-173">更改策略以面向不包含任何 Microsoft 托管桌面用户或设备的特定 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="27424-173">Change the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users or devices.</span></span> <span data-ttu-id="27424-174">有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="27424-174">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="27424-175">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-175">**Advisory**</span></span>

<span data-ttu-id="27424-176">确保你拥有的任何合规性策略不面向任何 Microsoft 托管桌面用户。</span><span class="sxs-lookup"><span data-stu-id="27424-176">Make sure that any compliance policies you have don't target any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="27424-177">有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="27424-177">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-profiles"></a><span data-ttu-id="27424-178">设备配置文件</span><span class="sxs-lookup"><span data-stu-id="27424-178">Device Configuration profiles</span></span>

<span data-ttu-id="27424-179">Azure AD 组织的 Intune 设备配置文件不得面向任何 Microsoft 管理桌面设备或用户。</span><span class="sxs-lookup"><span data-stu-id="27424-179">Intune Device Configuration profiles in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="27424-180">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="27424-180">**Not ready**</span></span>

<span data-ttu-id="27424-181">你至少有一个配置文件面向所有用户、所有设备或两者。</span><span class="sxs-lookup"><span data-stu-id="27424-181">You have at least one configuration profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="27424-182">将配置文件重置为面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="27424-182">Reset the profile to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="27424-183">有关步骤，请参阅 [使用 Microsoft Intune 中的自定义设置创建配置文件](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="27424-183">For steps, see [Create a profile with custom settings in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="27424-184">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-184">**Advisory**</span></span>

<span data-ttu-id="27424-185">确保你拥有的任何配置策略不包括任何 Microsoft 托管桌面设备或用户。</span><span class="sxs-lookup"><span data-stu-id="27424-185">Make sure that any configuration policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="27424-186">有关步骤，请参阅 [使用 Microsoft Intune 中的自定义设置创建配置文件](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="27424-186">For steps, see [Create a profile with custom settings in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="27424-187">设备类型限制</span><span class="sxs-lookup"><span data-stu-id="27424-187">Device type restrictions</span></span>

<span data-ttu-id="27424-188">必须允许 Microsoft 托管桌面设备在 Intune 中注册。</span><span class="sxs-lookup"><span data-stu-id="27424-188">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="27424-189">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="27424-189">**Not ready**</span></span>

<span data-ttu-id="27424-190">你当前至少配置了一个注册限制策略，以防止 Windows 设备在 Intune 中注册。</span><span class="sxs-lookup"><span data-stu-id="27424-190">You currently have at least one enrollment restriction policy configured to prevent Windows devices from enrollment in Intune.</span></span> <span data-ttu-id="27424-191">按照针对 Microsoft [](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set)托管桌面用户的每个注册限制策略设置注册限制中的步骤操作，将 Windows (MDM) **设置为\*\*\*\*"允许"。**</span><span class="sxs-lookup"><span data-stu-id="27424-191">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) for each enrollment restriction policy that targets Microsoft Managed Desktop users and change the **Windows (MDM)** setting to **Allow**.</span></span> <span data-ttu-id="27424-192">但是，你可以将任何个人拥有的Windows (**MDM**) 设置为 **阻止**。</span><span class="sxs-lookup"><span data-stu-id="27424-192">You can, however, set any **personally owned** **Windows (MDM)** devices to **Block**.</span></span> 


### <a name="enrollment-status-page"></a><span data-ttu-id="27424-193">注册状态页</span><span class="sxs-lookup"><span data-stu-id="27424-193">Enrollment Status Page</span></span>

<span data-ttu-id="27424-194">你当前已启用 ESP (注册) 页。</span><span class="sxs-lookup"><span data-stu-id="27424-194">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="27424-195">如果你打算参加此功能的 Microsoft 托管桌面公共预览版，可以忽略此项。</span><span class="sxs-lookup"><span data-stu-id="27424-195">If you intend to participate in the Microsoft Managed Desktop public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="27424-196">有关详细信息，请参阅 [Autopilot 的首次运行体验和注册状态页](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="27424-196">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="27424-197">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="27424-197">**Not ready**</span></span>

<span data-ttu-id="27424-198">YOU have the ESP default profile set to **Show app and profile configuration progress.**</span><span class="sxs-lookup"><span data-stu-id="27424-198">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="27424-199">通过按照"设置注册状态"页中的步骤操作，禁用此设置或确保任何 Azure AD 组的工作分配不包括 Microsoft 托管 [桌面设备](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="27424-199">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="27424-200">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-200">**Advisory**</span></span>

<span data-ttu-id="27424-201">确保未将具有"显示应用"和配置文件配置进度设置的任何配置文件分配给任何包含 Microsoft 托管桌面设备的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="27424-201">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="27424-202">有关详细信息，请参阅" [设置注册状态"页](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="27424-202">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="microsoft-store-for-business"></a><span data-ttu-id="27424-203">适用于企业的 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="27424-203">Microsoft Store for Business</span></span>

<span data-ttu-id="27424-204">我们使用适用于 Business 的 Microsoft Store，在 Microsoft 托管桌面上部署公司门户应用，以允许用户选择安装某些应用，如 Microsoft Project 和 Microsoft Visio (（如果允许) ）。</span><span class="sxs-lookup"><span data-stu-id="27424-204">We use Microsoft Store for Business and deploy the Company Portal app on Microsoft Managed Desktop to allow users to optionally install some apps, such as Microsoft Project and Microsoft Visio (where permitted).</span></span>

<span data-ttu-id="27424-205">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="27424-205">**Not ready**</span></span>

<span data-ttu-id="27424-206">适用于 Business 的 Microsoft Store 未启用或未与 Intune 同步。</span><span class="sxs-lookup"><span data-stu-id="27424-206">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="27424-207">有关详细信息，请参阅如何使用 [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) 管理从适用于 Business 的 Microsoft Store 购买的应用，以及如何在设备上安装 [Intune 公司门户](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="27424-207">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on devices](../get-started/company-portal.md).</span></span>

### <a name="multifactor-authentication"></a><span data-ttu-id="27424-208">多重身份验证</span><span class="sxs-lookup"><span data-stu-id="27424-208">Multifactor authentication</span></span>

<span data-ttu-id="27424-209">多重身份验证不得阻止 Microsoft 托管桌面在 Intune 和 Azure AD (租户) 管理 Azure AD 组织。</span><span class="sxs-lookup"><span data-stu-id="27424-209">Multifactor authentication must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>


<span data-ttu-id="27424-210">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="27424-210">**Not ready**</span></span>

<span data-ttu-id="27424-211">为分配给所有用户的条件访问策略设置了一些多重身份验证策略，</span><span class="sxs-lookup"><span data-stu-id="27424-211">You have some multifactor authentication policies set as **required** for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="27424-212">在注册期间，我们将从相关条件访问策略中排除 Microsoft Managed Desktop Service 帐户，并应用新的条件访问策略来限制对这些帐户的访问。</span><span class="sxs-lookup"><span data-stu-id="27424-212">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="27424-213">有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="27424-213">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="27424-214">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-214">**Advisory**</span></span>

<span data-ttu-id="27424-215">条件访问策略需要多重身份验证，这些策略可能会阻止 Microsoft 托管桌面管理 Microsoft 托管桌面服务。</span><span class="sxs-lookup"><span data-stu-id="27424-215">You have multifactor authentication required on conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="27424-216">在注册期间，我们将从相关条件访问策略中排除 Microsoft Managed Desktop Service 帐户，并应用新的条件访问策略来限制对这些帐户的访问。</span><span class="sxs-lookup"><span data-stu-id="27424-216">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="27424-217">有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="27424-217">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="27424-218">**错误**</span><span class="sxs-lookup"><span data-stu-id="27424-218">**Error**</span></span>

<span data-ttu-id="27424-219">Intune 管理员角色没有足够的权限进行此检查。</span><span class="sxs-lookup"><span data-stu-id="27424-219">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="27424-220">你还需要分配有以下任一 Azure AD 角色来运行此检查：</span><span class="sxs-lookup"><span data-stu-id="27424-220">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="27424-221">安全读取者</span><span class="sxs-lookup"><span data-stu-id="27424-221">Security Reader</span></span>
- <span data-ttu-id="27424-222">安全管理员</span><span class="sxs-lookup"><span data-stu-id="27424-222">Security Administrator</span></span>
- <span data-ttu-id="27424-223">条件访问管理员</span><span class="sxs-lookup"><span data-stu-id="27424-223">Conditional Access Administrator</span></span>
- <span data-ttu-id="27424-224">全局读取者</span><span class="sxs-lookup"><span data-stu-id="27424-224">Global Reader</span></span>
- <span data-ttu-id="27424-225">设备管理员</span><span class="sxs-lookup"><span data-stu-id="27424-225">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="27424-226">PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="27424-226">PowerShell scripts</span></span>

<span data-ttu-id="27424-227">Windows PowerShell无法以面向 Microsoft 托管桌面设备的方式分配脚本。</span><span class="sxs-lookup"><span data-stu-id="27424-227">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="27424-228">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-228">**Advisory**</span></span>

<span data-ttu-id="27424-229">请确保 Azure AD Windows PowerShell中的脚本不面向任何 Microsoft 管理桌面设备或用户。</span><span class="sxs-lookup"><span data-stu-id="27424-229">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="27424-230">不要将 PowerShell 脚本分配给所有用户、所有设备或两者。</span><span class="sxs-lookup"><span data-stu-id="27424-230">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="27424-231">更改策略以使用面向不包含任何 Microsoft 托管桌面设备或用户的特定 Azure AD 组的工作分配。</span><span class="sxs-lookup"><span data-stu-id="27424-231">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="27424-232">有关详细信息，请参阅 Intune 中的 [Windows 10 设备上使用 PowerShell 脚本](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)。</span><span class="sxs-lookup"><span data-stu-id="27424-232">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="27424-233">地区</span><span class="sxs-lookup"><span data-stu-id="27424-233">Region</span></span>

<span data-ttu-id="27424-234">你的区域必须受 Microsoft 托管桌面支持。</span><span class="sxs-lookup"><span data-stu-id="27424-234">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="27424-235">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="27424-235">**Not ready**</span></span>

<span data-ttu-id="27424-236">你的 Azure AD 组织区域当前不受 Microsoft 托管桌面支持。</span><span class="sxs-lookup"><span data-stu-id="27424-236">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="27424-237">有关详细信息，请参阅 [Microsoft 托管桌面支持的地区和语言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="27424-237">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="27424-238">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-238">**Advisory**</span></span>

<span data-ttu-id="27424-239">Microsoft 托管桌面不支持 Azure AD 组织所在的一个或多个国家/地区。</span><span class="sxs-lookup"><span data-stu-id="27424-239">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="27424-240">有关详细信息，请参阅 [Microsoft 托管桌面支持的地区和语言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="27424-240">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="27424-241">安全基线</span><span class="sxs-lookup"><span data-stu-id="27424-241">Security baselines</span></span>

<span data-ttu-id="27424-242">安全基线策略不应面向任何 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="27424-242">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="27424-243">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="27424-243">**Not ready**</span></span>

<span data-ttu-id="27424-244">你有一个面向所有用户、所有设备或两者的安全基线配置文件。</span><span class="sxs-lookup"><span data-stu-id="27424-244">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="27424-245">更改策略以使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的工作分配。</span><span class="sxs-lookup"><span data-stu-id="27424-245">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="27424-246">有关步骤，请参阅 [使用安全基线在 Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)中配置 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="27424-246">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="27424-247">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-247">**Advisory**</span></span>

<span data-ttu-id="27424-248">确保已排除 Microsoft 托管桌面设备的任何安全基线策略。</span><span class="sxs-lookup"><span data-stu-id="27424-248">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="27424-249">有关步骤，请参阅 [使用安全基线在 Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)中配置 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="27424-249">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="27424-250">现代 **工作区设备 -所有** Azure AD 组是我们在注册 Microsoft 托管桌面时创建的动态组，因此你必须在注册后返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="27424-250">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="27424-251">Windows 应用</span><span class="sxs-lookup"><span data-stu-id="27424-251">Windows apps</span></span>

<span data-ttu-id="27424-252">查看希望 Microsoft 托管桌面用户拥有的应用。</span><span class="sxs-lookup"><span data-stu-id="27424-252">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="27424-253">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-253">**Advisory**</span></span>

<span data-ttu-id="27424-254">应准备希望 Microsoft 托管桌面用户拥有的应用清单。</span><span class="sxs-lookup"><span data-stu-id="27424-254">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="27424-255">由于这些应用必须由 Intune 部署，因此请评估是否重新使用现有 Intune 应用。</span><span class="sxs-lookup"><span data-stu-id="27424-255">Since these apps must be deployed by Intune, evaluate reusing existing Intune apps.</span></span> <span data-ttu-id="27424-256">请考虑使用公司门户 (请参阅"在设备上安装 [Intune](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) 公司门户"和"注册状态"页 (ESP) 将应用分发给你的用户。</span><span class="sxs-lookup"><span data-stu-id="27424-256">Consider using Company Portal (see [Install Intune Company Portal on devices](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="27424-257">有关详细信息，请参阅 [Microsoft 托管桌面中的应用](apps.md) 和 Autopilot 首次运行体验和 [注册状态页](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)。</span><span class="sxs-lookup"><span data-stu-id="27424-257">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run).</span></span>

<span data-ttu-id="27424-258">你可以要求 Microsoft 帐户代表在 Microsoft Endpoint Configuration Manager 中查询，以确定准备迁移到 Intune 或需要调整的应用。</span><span class="sxs-lookup"><span data-stu-id="27424-258">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="27424-259">Windows Hello 企业版</span><span class="sxs-lookup"><span data-stu-id="27424-259">Windows Hello for Business</span></span>

<span data-ttu-id="27424-260">Microsoft 托管桌面需要启用 Windows Hello 企业版。</span><span class="sxs-lookup"><span data-stu-id="27424-260">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="27424-261">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="27424-261">**Not ready**</span></span>

<span data-ttu-id="27424-262">Windows Hello 企业应用已禁用。</span><span class="sxs-lookup"><span data-stu-id="27424-262">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="27424-263">按照"创建 Windows Hello 企业应用"策略 [中的步骤启用它](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="27424-263">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="27424-264">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-264">**Advisory**</span></span>

<span data-ttu-id="27424-265">未设置 Windows Hello 企业应用。</span><span class="sxs-lookup"><span data-stu-id="27424-265">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="27424-266">按照创建 Windows Hello 企业策略 [中的步骤启用它](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)。</span><span class="sxs-lookup"><span data-stu-id="27424-266">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="27424-267">Windows 10 更新圈</span><span class="sxs-lookup"><span data-stu-id="27424-267">Windows 10 update rings</span></span>

<span data-ttu-id="27424-268">Intune 中的"Windows 10 更新圈"策略不得面向任何 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="27424-268">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="27424-269">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="27424-269">**Not ready**</span></span>

<span data-ttu-id="27424-270">你有一个面向所有设备、所有用户或两者同时面向的"更新圈"策略。</span><span class="sxs-lookup"><span data-stu-id="27424-270">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="27424-271">更改策略以使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的工作分配。</span><span class="sxs-lookup"><span data-stu-id="27424-271">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="27424-272">有关步骤，请参阅 [在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="27424-272">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="27424-273">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-273">**Advisory**</span></span>

<span data-ttu-id="27424-274">确保你已排除所有现代工作区设备 -所有 Azure AD **组的任何** 更新圈策略。</span><span class="sxs-lookup"><span data-stu-id="27424-274">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="27424-275">如果你向这些策略分配了 Azure AD 用户组，请确保你已排除所有已排除的新式 **工作区 -** 所有 Azure AD 组，将 Microsoft 托管桌面用户添加到 (或等效组) 。</span><span class="sxs-lookup"><span data-stu-id="27424-275">If you have assigned Azure AD user groups to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group that you add your Microsoft Managed Desktop users to (or an equivalent group).</span></span> <span data-ttu-id="27424-276">有关步骤，请参阅 [在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="27424-276">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="27424-277">现代 **工作区设备-全部** 和现代工作区 **-所有** Azure AD 组都是我们在注册 Microsoft 托管桌面时创建的组，因此你必须在注册后返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="27424-277">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="27424-278">Azure Active Directory 设置</span><span class="sxs-lookup"><span data-stu-id="27424-278">Azure Active Directory settings</span></span>

<span data-ttu-id="27424-279">可以在 Azure 门户访问 Azure Active Directory [设置](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="27424-279">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="27424-280">Intune 注册</span><span class="sxs-lookup"><span data-stu-id="27424-280">Intune enrollment</span></span>

<span data-ttu-id="27424-281">Azure AD 组织中 Windows 10 设备必须能够在 Intune 中自动注册。</span><span class="sxs-lookup"><span data-stu-id="27424-281">Windows 10 devices in your Azure AD organization must be able to automatically enroll in Intune.</span></span>

<span data-ttu-id="27424-282">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-282">**Advisory**</span></span>

<span data-ttu-id="27424-283">确保 MDM **用户作用域** 设置为"部分"或 **"全部**"，而不是 **"无"。**</span><span class="sxs-lookup"><span data-stu-id="27424-283">Make sure the **MDM User scope** is set to **Some** or **All**, not **None**.</span></span> <span data-ttu-id="27424-284">如果你选择 **"一** 些"，请在注册后返回，然后为组选择"新式 **工作区**-所有 Azure AD 组"或面向所有 Microsoft 托管桌面用户的等效组。</span><span class="sxs-lookup"><span data-stu-id="27424-284">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups** or an equivalent group targeting all of your Microsoft Managed Desktop users.</span></span>  <span data-ttu-id="27424-285">请参阅 [使用 Microsoft Intune 设置 Windows 设备的注册](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="27424-285">See [Set up enrollment for Windows devices by using Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment).</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="27424-286">临时订阅</span><span class="sxs-lookup"><span data-stu-id="27424-286">Ad hoc subscriptions</span></span>

<span data-ttu-id="27424-287">建议如何检查设置为 (false"的设置) 可能会阻止企业状态漫游正常工作。</span><span class="sxs-lookup"><span data-stu-id="27424-287">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="27424-288">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-288">**Advisory**</span></span>

<span data-ttu-id="27424-289">确保 **AllowAdHocSubscriptions** 设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="27424-289">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="27424-290">否则，企业状态漫游可能无法工作。</span><span class="sxs-lookup"><span data-stu-id="27424-290">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="27424-291">有关详细信息，请参阅 [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="27424-291">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="27424-292">企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="27424-292">Enterprise State Roaming</span></span>

<span data-ttu-id="27424-293">应启用企业状态漫游。</span><span class="sxs-lookup"><span data-stu-id="27424-293">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="27424-294">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-294">**Advisory**</span></span>

<span data-ttu-id="27424-295">确保为"所有"或"所选 **"组启用了** 企业 **状态** 漫游。</span><span class="sxs-lookup"><span data-stu-id="27424-295">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="27424-296">有关详细信息，请参阅在 [Azure Active Directory 中启用企业状态漫游](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)。</span><span class="sxs-lookup"><span data-stu-id="27424-296">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="27424-297">许可证</span><span class="sxs-lookup"><span data-stu-id="27424-297">Licenses</span></span>

<span data-ttu-id="27424-298">使用 Microsoft 托管桌面需要大量许可证。</span><span class="sxs-lookup"><span data-stu-id="27424-298">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="27424-299">**未准备就绪**</span><span class="sxs-lookup"><span data-stu-id="27424-299">**Not Ready**</span></span>

<span data-ttu-id="27424-300">你没有使用 Microsoft 托管桌面所需的全部许可证。</span><span class="sxs-lookup"><span data-stu-id="27424-300">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="27424-301">有关详细信息，请参阅[Microsoft 托管桌面技术和](../intro/technologies.md)[有关许可证的更多内容](prerequisites.md#more-about-licenses)。</span><span class="sxs-lookup"><span data-stu-id="27424-301">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="27424-302">安全帐户名称</span><span class="sxs-lookup"><span data-stu-id="27424-302">Security account names</span></span>

<span data-ttu-id="27424-303">某些安全帐户名称可能会与 Microsoft 托管桌面创建的帐户名冲突。</span><span class="sxs-lookup"><span data-stu-id="27424-303">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="27424-304">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="27424-304">**Not ready**</span></span>

<span data-ttu-id="27424-305">你至少具有一个与 Microsoft 托管桌面创建的帐户名称相冲突的帐户名称。</span><span class="sxs-lookup"><span data-stu-id="27424-305">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="27424-306">与 Microsoft 帐户代表合作，排除这些帐户名。</span><span class="sxs-lookup"><span data-stu-id="27424-306">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="27424-307">安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="27424-307">Security administrator roles</span></span>

<span data-ttu-id="27424-308">具有特定安全角色的用户必须在 Microsoft Defender for Endpoint 中分配这些角色。</span><span class="sxs-lookup"><span data-stu-id="27424-308">Users with certain security roles must have those roles assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="27424-309">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-309">**Advisory**</span></span>

<span data-ttu-id="27424-310">如果你的用户已分配到 Azure AD 组织中任何这些角色，请确保他们在 Microsoft Defender for Endpoint 中也分配了这些角色。</span><span class="sxs-lookup"><span data-stu-id="27424-310">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="27424-311">否则，具有这些角色的管理员将无法访问管理门户。</span><span class="sxs-lookup"><span data-stu-id="27424-311">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="27424-312">安全操作员</span><span class="sxs-lookup"><span data-stu-id="27424-312">Security Operator</span></span>
- <span data-ttu-id="27424-313">全局读取者</span><span class="sxs-lookup"><span data-stu-id="27424-313">Global Reader</span></span>

<span data-ttu-id="27424-314">有关详细信息，请参阅为基于角色 [的访问控制创建和管理角色](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)。</span><span class="sxs-lookup"><span data-stu-id="27424-314">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="27424-315">安全默认值</span><span class="sxs-lookup"><span data-stu-id="27424-315">Security default</span></span>

<span data-ttu-id="27424-316">Azure Active Directory 中的安全默认值将阻止 Microsoft 托管桌面管理设备。</span><span class="sxs-lookup"><span data-stu-id="27424-316">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="27424-317">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="27424-317">**Not ready**</span></span>

<span data-ttu-id="27424-318">你已打开安全默认值。</span><span class="sxs-lookup"><span data-stu-id="27424-318">You have Security defaults turned on.</span></span> <span data-ttu-id="27424-319">关闭安全默认值并设置条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="27424-319">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="27424-320">有关详细信息，请参阅 [常见条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。</span><span class="sxs-lookup"><span data-stu-id="27424-320">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="27424-321">自助服务密码重置</span><span class="sxs-lookup"><span data-stu-id="27424-321">Self-service Password Reset</span></span>

<span data-ttu-id="27424-322">SSPR (可) Microsoft 托管桌面用户（Microsoft 托管桌面服务帐户除外）启用 SSPR 密码重置功能。</span><span class="sxs-lookup"><span data-stu-id="27424-322">Self-service Password Reset (SSPR) can be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="27424-323">有关详细信息，请参阅 [教程：允许用户使用 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)自助服务密码重置解锁其帐户或重置密码。</span><span class="sxs-lookup"><span data-stu-id="27424-323">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="27424-324">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-324">**Advisory**</span></span>

<span data-ttu-id="27424-325">确保"SSPR **选择** "设置包括 Microsoft 托管桌面用户，但不包括 Microsoft 托管桌面服务帐户。</span><span class="sxs-lookup"><span data-stu-id="27424-325">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop users but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="27424-326">启用 SSPR 后，Microsoft 托管桌面服务帐户无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="27424-326">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="27424-327">标准用户角色</span><span class="sxs-lookup"><span data-stu-id="27424-327">Standard user role</span></span>

<span data-ttu-id="27424-328">除了分配了全局管理员和设备管理员的 Azure AD 角色的用户外，Microsoft 托管桌面用户将是没有本地管理员权限的标准用户。</span><span class="sxs-lookup"><span data-stu-id="27424-328">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="27424-329">当所有其他用户启动其 Microsoft 托管桌面设备时，将为其分配标准用户角色。</span><span class="sxs-lookup"><span data-stu-id="27424-329">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="27424-330">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-330">**Advisory**</span></span>

<span data-ttu-id="27424-331">注册后，Microsoft 托管桌面用户不会拥有其 Microsoft 托管桌面设备的本地管理员权限。</span><span class="sxs-lookup"><span data-stu-id="27424-331">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="27424-332">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="27424-332">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="27424-333">OneDrive</span><span class="sxs-lookup"><span data-stu-id="27424-333">OneDrive</span></span>

<span data-ttu-id="27424-334">" **仅在加入特定域** 的 PC 上允许同步"设置与 Microsoft 托管桌面冲突。</span><span class="sxs-lookup"><span data-stu-id="27424-334">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="27424-335">可以在 OneDrive 管理中心访问 OneDrive [设置](https://admin.onedrive.com)。</span><span class="sxs-lookup"><span data-stu-id="27424-335">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="27424-336">**公告**</span><span class="sxs-lookup"><span data-stu-id="27424-336">**Advisory**</span></span>

<span data-ttu-id="27424-337">仅在加入特定域的 PC 上 **使用"仅允许同步"** 设置。</span><span class="sxs-lookup"><span data-stu-id="27424-337">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="27424-338">此设置将不能用于 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="27424-338">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="27424-339">禁用此设置，并改为将 OneDrive 设置为使用条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="27424-339">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="27424-340">有关 [帮助，请参阅"规划条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 部署"。</span><span class="sxs-lookup"><span data-stu-id="27424-340">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>
