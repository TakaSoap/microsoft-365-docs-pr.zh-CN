---
title: 修复准备情况评估工具发现的问题
description: 对工具找到的每个问题执行的详细操作
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b77313a18a5744549e492de991e282bc34dbb6da
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002413"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="74809-104">修复准备情况评估工具发现的问题</span><span class="sxs-lookup"><span data-stu-id="74809-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="74809-105">对于每个检查，该工具将报告以下四个可能的结果之一：</span><span class="sxs-lookup"><span data-stu-id="74809-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="74809-106">结果</span><span class="sxs-lookup"><span data-stu-id="74809-106">Result</span></span>  |<span data-ttu-id="74809-107">含义</span><span class="sxs-lookup"><span data-stu-id="74809-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="74809-108">Ready</span><span class="sxs-lookup"><span data-stu-id="74809-108">Ready</span></span>     | <span data-ttu-id="74809-109">完成注册前不需要执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="74809-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="74809-110">欲</span><span class="sxs-lookup"><span data-stu-id="74809-110">Advisory</span></span>    | <span data-ttu-id="74809-111">按照工具或本文中的步骤操作，以获取注册和用户的最佳体验。</span><span class="sxs-lookup"><span data-stu-id="74809-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="74809-112">你 *可以* 完成注册，但必须先解决这些问题，然后再部署你的第一个设备。</span><span class="sxs-lookup"><span data-stu-id="74809-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="74809-113">未就绪</span><span class="sxs-lookup"><span data-stu-id="74809-113">Not ready</span></span> | <span data-ttu-id="74809-114">*如果不解决这些问题，注册将失败。*</span><span class="sxs-lookup"><span data-stu-id="74809-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="74809-115">按照工具或本文中的步骤进行操作，以解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="74809-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="74809-116">错误</span><span class="sxs-lookup"><span data-stu-id="74809-116">Error</span></span> | <span data-ttu-id="74809-117">您正在使用的 Azure Active Director (AD) 角色没有足够的权限来运行此检查。</span><span class="sxs-lookup"><span data-stu-id="74809-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="74809-118">Microsoft Intune 设置</span><span class="sxs-lookup"><span data-stu-id="74809-118">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="74809-119">Autopilot 部署配置文件</span><span class="sxs-lookup"><span data-stu-id="74809-119">Autopilot deployment profile</span></span>

<span data-ttu-id="74809-120">您不应具有任何目标为分配的或 Microsoft 托管桌面使用的动态组的现有 Autopilot 配置文件。</span><span class="sxs-lookup"><span data-stu-id="74809-120">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="74809-121">Microsoft 托管桌面使用 Autopilot 配置新设备。</span><span class="sxs-lookup"><span data-stu-id="74809-121">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="74809-122">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="74809-122">**Not ready**</span></span>

<span data-ttu-id="74809-123">您有一个分配给所有设备的 Autopilot 配置文件。</span><span class="sxs-lookup"><span data-stu-id="74809-123">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="74809-124">有关步骤，请参阅 [使用 Windows Autopilot 在 Intune 中注册 Windows 设备](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="74809-124">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="74809-125">在 Microsoft 托管桌面注册之后，将您的 Autopilot 策略设置为排除 **新式工作区设备-所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="74809-125">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="74809-126">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-126">**Advisory**</span></span>

<span data-ttu-id="74809-127">确保您的 Autopilot 配置文件面向不包含将在注册中创建的 Microsoft 托管桌面设备的已分配或动态 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="74809-127">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="74809-128">有关步骤，请参阅 [使用 Windows Autopilot 在 Intune 中注册 Windows 设备](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="74809-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="74809-129">在 Microsoft 托管桌面注册之后，将您的 Autopilot 策略设置为排除 **新式工作区设备-所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="74809-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="74809-130">证书连接器</span><span class="sxs-lookup"><span data-stu-id="74809-130">Certificate connectors</span></span>

<span data-ttu-id="74809-131">如果你有要在 Microsoft 托管桌面中注册的设备使用的任何证书连接器，连接器将不能包含任何错误。</span><span class="sxs-lookup"><span data-stu-id="74809-131">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="74809-132">以下建议仅适用于你的情况，因此请仔细检查。</span><span class="sxs-lookup"><span data-stu-id="74809-132">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="74809-133">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-133">**Advisory**</span></span>

<span data-ttu-id="74809-134">不存在任何证书连接器。</span><span class="sxs-lookup"><span data-stu-id="74809-134">No certificate connectors are present.</span></span> <span data-ttu-id="74809-135">您可能不需要任何连接器，但应评估是否需要对 Microsoft 托管桌面设备进行网络连接。</span><span class="sxs-lookup"><span data-stu-id="74809-135">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="74809-136">有关详细信息，请参阅 [为 Microsoft 托管桌面准备证书和网络配置文件](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="74809-136">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="74809-137">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-137">**Advisory**</span></span>

<span data-ttu-id="74809-138">至少一个证书连接器有错误。</span><span class="sxs-lookup"><span data-stu-id="74809-138">At least one certificate connector has an error.</span></span> <span data-ttu-id="74809-139">如果需要此连接器连接到 Microsoft 托管桌面设备，则必须解决该错误。</span><span class="sxs-lookup"><span data-stu-id="74809-139">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="74809-140">有关详细信息，请参阅 [为 Microsoft 托管桌面准备证书和网络配置文件](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="74809-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="74809-141">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-141">**Advisory**</span></span>

<span data-ttu-id="74809-142">您至少有一个证书连接器，并且未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="74809-142">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="74809-143">但是，您可能需要创建一个配置文件以重用 Microsoft 托管桌面设备的连接器。</span><span class="sxs-lookup"><span data-stu-id="74809-143">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="74809-144">有关详细信息，请参阅 [为 Microsoft 托管桌面准备证书和网络配置文件](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="74809-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="74809-145">条件访问策略</span><span class="sxs-lookup"><span data-stu-id="74809-145">Conditional access policies</span></span>

<span data-ttu-id="74809-146">Azure AD 组织中的条件访问策略不得以任何 Microsoft 管理桌面用户为目标。</span><span class="sxs-lookup"><span data-stu-id="74809-146">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="74809-147">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="74809-147">**Not ready**</span></span>

<span data-ttu-id="74809-148">您至少具有一个面向所有用户的条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="74809-148">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="74809-149">将策略重置为面向不包含将在注册时创建的 Microsoft 托管桌面服务帐户的 Azure AD 组的特定 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="74809-149">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="74809-150">有关步骤，请参阅 [条件访问：用户和组](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。</span><span class="sxs-lookup"><span data-stu-id="74809-150">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="74809-151">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-151">**Advisory**</span></span>

<span data-ttu-id="74809-152">请确保您已排除了所有条件访问 **策略 "AZURE** AD 组"。</span><span class="sxs-lookup"><span data-stu-id="74809-152">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="74809-153">有关步骤，请参阅 [调整条件访问](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="74809-153">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="74809-154">**新式 Workplace Service 帐户** Azure AD 组是我们在注册时为服务创建的动态组。</span><span class="sxs-lookup"><span data-stu-id="74809-154">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="74809-155">注册后，必须返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="74809-155">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="74809-156">有关这些服务帐户的详细信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="74809-156">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="74809-157">**Error**</span><span class="sxs-lookup"><span data-stu-id="74809-157">**Error**</span></span>

<span data-ttu-id="74809-158">Intune 管理员角色对此检查没有足够的权限。</span><span class="sxs-lookup"><span data-stu-id="74809-158">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="74809-159">您还需要分配给运行此检查的任何 Azure AD 角色：</span><span class="sxs-lookup"><span data-stu-id="74809-159">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="74809-160">安全读取者</span><span class="sxs-lookup"><span data-stu-id="74809-160">Security Reader</span></span>
- <span data-ttu-id="74809-161">安全管理员</span><span class="sxs-lookup"><span data-stu-id="74809-161">Security Administrator</span></span>
- <span data-ttu-id="74809-162">条件访问管理员</span><span class="sxs-lookup"><span data-stu-id="74809-162">Conditional Access Administrator</span></span>
- <span data-ttu-id="74809-163">全局读取者</span><span class="sxs-lookup"><span data-stu-id="74809-163">Global Reader</span></span>
- <span data-ttu-id="74809-164">设备管理员</span><span class="sxs-lookup"><span data-stu-id="74809-164">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="74809-165">设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="74809-165">Device Compliance policies</span></span>

<span data-ttu-id="74809-166">Azure AD 组织中的 Intune 设备合规性策略不得以任何 Microsoft 托管桌面用户为目标。</span><span class="sxs-lookup"><span data-stu-id="74809-166">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="74809-167">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="74809-167">**Not ready**</span></span>

<span data-ttu-id="74809-168">您至少具有一个面向所有用户的合规性策略。</span><span class="sxs-lookup"><span data-stu-id="74809-168">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="74809-169">将策略重置为面向不包含任何 Microsoft 托管桌面用户的特定 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="74809-169">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="74809-170">有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="74809-170">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="74809-171">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-171">**Advisory**</span></span>

<span data-ttu-id="74809-172">确保任何不包含任何 Microsoft 托管桌面用户的合规性策略。</span><span class="sxs-lookup"><span data-stu-id="74809-172">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="74809-173">有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="74809-173">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="74809-174">设备配置策略</span><span class="sxs-lookup"><span data-stu-id="74809-174">Device Configuration policies</span></span>

<span data-ttu-id="74809-175">Azure AD 组织中的 Intune 设备配置策略不得以任何 Microsoft 管理桌面设备或用户为目标。</span><span class="sxs-lookup"><span data-stu-id="74809-175">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="74809-176">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="74809-176">**Not ready**</span></span>

<span data-ttu-id="74809-177">至少有一个针对所有用户、所有设备或同时针对这两者的配置策略。</span><span class="sxs-lookup"><span data-stu-id="74809-177">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="74809-178">将策略重置为面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="74809-178">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="74809-179">有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="74809-179">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="74809-180">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-180">**Advisory**</span></span>

<span data-ttu-id="74809-181">确保任何不包含任何 Microsoft 托管桌面设备或用户的合规性策略。</span><span class="sxs-lookup"><span data-stu-id="74809-181">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="74809-182">有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="74809-182">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="74809-183">设备类型限制</span><span class="sxs-lookup"><span data-stu-id="74809-183">Device type restrictions</span></span>

<span data-ttu-id="74809-184">必须允许 Microsoft 托管桌面设备在 Intune 中注册。</span><span class="sxs-lookup"><span data-stu-id="74809-184">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="74809-185">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="74809-185">**Not ready**</span></span>

<span data-ttu-id="74809-186">按照 " [设置注册限制](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) " 中的步骤将设置更改为 " **允许** "。</span><span class="sxs-lookup"><span data-stu-id="74809-186">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="74809-187">"注册状态" 页</span><span class="sxs-lookup"><span data-stu-id="74809-187">Enrollment Status Page</span></span>

<span data-ttu-id="74809-188">您当前已启用 "注册状态" 页面 (ESP) 。</span><span class="sxs-lookup"><span data-stu-id="74809-188">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="74809-189">如果你参与此功能的公开预览，则可以忽略此项。</span><span class="sxs-lookup"><span data-stu-id="74809-189">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="74809-190">有关详细信息，请参阅 [首次运行体验 With Autopilot 和注册状态页](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="74809-190">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="74809-191">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="74809-191">**Not ready**</span></span>

<span data-ttu-id="74809-192">您已将 ESP 默认配置文件设置为 **显示应用和配置文件配置进度** 。</span><span class="sxs-lookup"><span data-stu-id="74809-192">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="74809-193">通过执行 " [设置注册状态" 页](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)中的步骤，禁用此设置或确保对任何 Azure AD 组的分配不包括 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="74809-193">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="74809-194">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-194">**Advisory**</span></span>

<span data-ttu-id="74809-195">确保具有 " **显示应用程序" 和 "配置文件配置进度** " 设置的任何配置文件未分配给任何包含 Microsoft 托管桌面设备的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="74809-195">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="74809-196">有关详细信息，请参阅 [设置注册状态页](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="74809-196">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="74809-197">Intune 注册</span><span class="sxs-lookup"><span data-stu-id="74809-197">Intune enrollment</span></span>

<span data-ttu-id="74809-198">Azure AD 组织中的 Windows 10 设备必须在 Intune 中自动注册。</span><span class="sxs-lookup"><span data-stu-id="74809-198">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="74809-199">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-199">**Advisory**</span></span>

<span data-ttu-id="74809-200">确保将 MDM 用户作用域设置为 " **部分** 或 **全部** "，而不是 " **无** "。</span><span class="sxs-lookup"><span data-stu-id="74809-200">Make sure the MDM User scope is set to **Some** or **All** , not **None**.</span></span> <span data-ttu-id="74809-201">如果选择 " **某些** "，请在注册后返回，并选择 **新式工作区-** **组** 的所有 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="74809-201">If you choose **Some** , come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="74809-202">适用于企业的 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="74809-202">Microsoft Store for Business</span></span>

<span data-ttu-id="74809-203">我们使用 Microsoft Store for Business，以便您可以下载公司门户，以部署一些应用程序，如 Microsoft Project 和 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="74809-203">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="74809-204">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="74809-204">**Not ready**</span></span>

<span data-ttu-id="74809-205">适用于企业的 Microsoft Store 不是已启用或未与 Intune 同步。</span><span class="sxs-lookup"><span data-stu-id="74809-205">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="74809-206">有关详细信息，请参阅 [如何使用 Microsoft Intune 在 Microsoft Store For Business 中管理批量购买的应用](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) ，并 [在设备上安装 Intune 公司门户](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="74809-206">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="74809-207">多重身份验证</span><span class="sxs-lookup"><span data-stu-id="74809-207">Multi-factor authentication</span></span>

<span data-ttu-id="74809-208">多因素身份验证不能意外应用于 Microsoft 托管桌面服务帐户。</span><span class="sxs-lookup"><span data-stu-id="74809-208">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="74809-209">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="74809-209">**Not ready**</span></span>

<span data-ttu-id="74809-210">您有一些多重身份验证 (MFA) 策略设置为分配给所有用户的条件访问策略的 "必需"。</span><span class="sxs-lookup"><span data-stu-id="74809-210">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="74809-211">将策略更改为使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的工作分配。</span><span class="sxs-lookup"><span data-stu-id="74809-211">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="74809-212">有关详细信息，请参阅 [条件访问策略](#conditional-access-policies) 和 [条件访问：要求对所有用户进行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。</span><span class="sxs-lookup"><span data-stu-id="74809-212">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="74809-213">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-213">**Advisory**</span></span>

<span data-ttu-id="74809-214">请确保任何需要 MFA 的条件访问策略排除 **新式工作区-所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="74809-214">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="74809-215">有关详细信息，请参阅 [条件访问策略](#conditional-access-policies) 和 [条件访问：要求对所有用户进行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。</span><span class="sxs-lookup"><span data-stu-id="74809-215">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="74809-216">**新式工作区-所有** Azure AD 组是在注册 Microsoft 托管桌面时创建的动态组，因此你必须在注册后返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="74809-216">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="74809-217">**Error**</span><span class="sxs-lookup"><span data-stu-id="74809-217">**Error**</span></span>

<span data-ttu-id="74809-218">Intune 管理员角色对此检查没有足够的权限。</span><span class="sxs-lookup"><span data-stu-id="74809-218">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="74809-219">您还需要分配给运行此检查的任何 Azure AD 角色：</span><span class="sxs-lookup"><span data-stu-id="74809-219">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="74809-220">安全读取者</span><span class="sxs-lookup"><span data-stu-id="74809-220">Security Reader</span></span>
- <span data-ttu-id="74809-221">安全管理员</span><span class="sxs-lookup"><span data-stu-id="74809-221">Security Administrator</span></span>
- <span data-ttu-id="74809-222">条件访问管理员</span><span class="sxs-lookup"><span data-stu-id="74809-222">Conditional Access Administrator</span></span>
- <span data-ttu-id="74809-223">全局读取者</span><span class="sxs-lookup"><span data-stu-id="74809-223">Global Reader</span></span>
- <span data-ttu-id="74809-224">设备管理员</span><span class="sxs-lookup"><span data-stu-id="74809-224">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="74809-225">PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="74809-225">PowerShell scripts</span></span>

<span data-ttu-id="74809-226">无法以 Microsoft 托管桌面设备的目标方式分配 Windows PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="74809-226">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="74809-227">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-227">**Advisory**</span></span>

<span data-ttu-id="74809-228">请确保 Azure AD 组织中的 Windows PowerShell 脚本不会针对任何 Microsoft 管理桌面设备或用户。</span><span class="sxs-lookup"><span data-stu-id="74809-228">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="74809-229">不要将 PowerShell 脚本分配给所有用户、所有设备，或同时针对两者。</span><span class="sxs-lookup"><span data-stu-id="74809-229">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="74809-230">将策略更改为使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的工作分配。</span><span class="sxs-lookup"><span data-stu-id="74809-230">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="74809-231">有关详细信息，请参阅在 [Intune 中使用 Windows 10 设备上的 PowerShell 脚本](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)。</span><span class="sxs-lookup"><span data-stu-id="74809-231">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="74809-232">区域</span><span class="sxs-lookup"><span data-stu-id="74809-232">Region</span></span>

<span data-ttu-id="74809-233">Microsoft 托管桌面必须支持你的区域。</span><span class="sxs-lookup"><span data-stu-id="74809-233">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="74809-234">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="74809-234">**Not ready**</span></span>

<span data-ttu-id="74809-235">Microsoft 托管桌面目前不支持 Azure AD 组织区域。</span><span class="sxs-lookup"><span data-stu-id="74809-235">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="74809-236">有关详细信息，请参阅 [Microsoft 托管桌面支持的区域和语言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="74809-236">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="74809-237">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-237">**Advisory**</span></span>

<span data-ttu-id="74809-238">Microsoft 托管桌面不支持 Azure AD 组织所在的一个或多个国家/地区。</span><span class="sxs-lookup"><span data-stu-id="74809-238">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="74809-239">有关详细信息，请参阅 [Microsoft 托管桌面支持的区域和语言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="74809-239">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="74809-240">安全基准</span><span class="sxs-lookup"><span data-stu-id="74809-240">Security baselines</span></span>

<span data-ttu-id="74809-241">安全基准策略不应以任何 Microsoft 托管桌面设备为目标。</span><span class="sxs-lookup"><span data-stu-id="74809-241">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="74809-242">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="74809-242">**Not ready**</span></span>

<span data-ttu-id="74809-243">您有一个面向所有用户、所有设备或两者的安全基准配置文件。</span><span class="sxs-lookup"><span data-stu-id="74809-243">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="74809-244">将策略更改为使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的工作分配。</span><span class="sxs-lookup"><span data-stu-id="74809-244">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="74809-245">有关步骤，请参阅 [使用安全基准在 Intune 中配置 Windows 10 设备](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="74809-245">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="74809-246">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-246">**Advisory**</span></span>

<span data-ttu-id="74809-247">请确保任何安全基准策略都已排除 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="74809-247">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="74809-248">有关步骤，请参阅 [使用安全基准在 Intune 中配置 Windows 10 设备](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="74809-248">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="74809-249">**新式工作区设备-所有** Azure AD 组是在注册 Microsoft 托管桌面时创建的动态组，因此你必须在注册后返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="74809-249">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="74809-250">Windows 应用</span><span class="sxs-lookup"><span data-stu-id="74809-250">Windows apps</span></span>

<span data-ttu-id="74809-251">查看你希望 Microsoft 托管桌面用户拥有的应用。</span><span class="sxs-lookup"><span data-stu-id="74809-251">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="74809-252">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-252">**Advisory**</span></span>

<span data-ttu-id="74809-253">应准备您希望 Microsoft 托管桌面用户拥有的应用程序的清单。</span><span class="sxs-lookup"><span data-stu-id="74809-253">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="74809-254">由于这些应用程序必须由 Intune 部署，因此请评估 "重新使用现有 Intune 应用"。</span><span class="sxs-lookup"><span data-stu-id="74809-254">Since these these apps must be deployed by Intune, evaluate re-using existing Intune apps.</span></span> <span data-ttu-id="74809-255">请考虑使用公司门户 (请参阅在设备和注册状态页 [上安装 Intune 公司门户](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) (ESP) 将应用程序分发给用户。</span><span class="sxs-lookup"><span data-stu-id="74809-255">Consider using Company Portal (see [Install Intune Company Portal on devices](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="74809-256">有关详细信息，请参阅 [Microsoft 托管桌面中的应用程序](apps.md) 和 [首次运行体验中的 Autopilot 和注册状态页](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)。</span><span class="sxs-lookup"><span data-stu-id="74809-256">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run).</span></span>

<span data-ttu-id="74809-257">可以在 Microsoft 终结点配置管理器中向 Microsoft 帐户代表查询，以确定那些准备迁移到 Intune 或需要调整的应用程序。</span><span class="sxs-lookup"><span data-stu-id="74809-257">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="74809-258">Windows Hello 企业版</span><span class="sxs-lookup"><span data-stu-id="74809-258">Windows Hello for Business</span></span>

<span data-ttu-id="74809-259">Microsoft 托管桌面要求启用 Windows Hello 企业版。</span><span class="sxs-lookup"><span data-stu-id="74809-259">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="74809-260">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="74809-260">**Not ready**</span></span>

<span data-ttu-id="74809-261">Windows Hello 企业版已禁用。</span><span class="sxs-lookup"><span data-stu-id="74809-261">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="74809-262">按照[创建 Windows Hello 企业版策略](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)中的步骤启用它</span><span class="sxs-lookup"><span data-stu-id="74809-262">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="74809-263">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-263">**Advisory**</span></span>

<span data-ttu-id="74809-264">Windows Hello 企业版尚未设置。</span><span class="sxs-lookup"><span data-stu-id="74809-264">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="74809-265">按照 [创建 Windows Hello 企业版策略](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)中的步骤启用它。</span><span class="sxs-lookup"><span data-stu-id="74809-265">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="74809-266">Windows 10 更新环</span><span class="sxs-lookup"><span data-stu-id="74809-266">Windows 10 update rings</span></span>

<span data-ttu-id="74809-267">Intune 中的 "Windows 10 更新循环" 策略不得以任何 Microsoft 托管桌面设备为目标。</span><span class="sxs-lookup"><span data-stu-id="74809-267">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="74809-268">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="74809-268">**Not ready**</span></span>

<span data-ttu-id="74809-269">您有一个面向所有设备和/或所有用户的 "更新循环" 策略。</span><span class="sxs-lookup"><span data-stu-id="74809-269">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="74809-270">将策略更改为使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的工作分配。</span><span class="sxs-lookup"><span data-stu-id="74809-270">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="74809-271">有关步骤，请参阅 [在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="74809-271">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="74809-272">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-272">**Advisory**</span></span>

<span data-ttu-id="74809-273">确保任何更新环策略都排除了 **新式工作区设备-所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="74809-273">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="74809-274">如果已将 Azure AD 用户组分配给这些策略，请确保所有更新环策略也都已排除 **新式工作区-所有** 包含 Microsoft 托管桌面用户的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="74809-274">If you have assigned Azure AD user group to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group which includes your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="74809-275">有关步骤，请参阅 [在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="74809-275">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="74809-276">新式的 **工作区设备-all** 和 **新式工作区-所有** Azure AD 组都分配了我们在注册 Microsoft 托管桌面时创建的组，因此在注册后必须返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="74809-276">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are assigned groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="74809-277">Azure Active Directory 设置</span><span class="sxs-lookup"><span data-stu-id="74809-277">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="74809-278">临时订阅</span><span class="sxs-lookup"><span data-stu-id="74809-278">Ad hoc subscriptions</span></span>

<span data-ttu-id="74809-279">建议如何检查 (如果设置为 "false" 的设置 ) 可能会阻止企业状态漫游正常工作。</span><span class="sxs-lookup"><span data-stu-id="74809-279">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="74809-280">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-280">**Advisory**</span></span>

<span data-ttu-id="74809-281">确保将 **AllowAdHocSubscriptions** 设置为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="74809-281">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="74809-282">否则，企业状态漫游可能无法工作。</span><span class="sxs-lookup"><span data-stu-id="74809-282">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="74809-283">有关详细信息，请参阅 [set-msolcompanysettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="74809-283">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="74809-284">企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="74809-284">Enterprise State Roaming</span></span>

<span data-ttu-id="74809-285">应启用企业状态漫游。</span><span class="sxs-lookup"><span data-stu-id="74809-285">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="74809-286">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-286">**Advisory**</span></span>

<span data-ttu-id="74809-287">确保为 **所有** 或 **选定** 的组启用了企业状态漫游。</span><span class="sxs-lookup"><span data-stu-id="74809-287">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="74809-288">有关详细信息，请参阅 [在 Azure Active Directory 中启用企业状态漫游](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)。</span><span class="sxs-lookup"><span data-stu-id="74809-288">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="74809-289">许可证</span><span class="sxs-lookup"><span data-stu-id="74809-289">Licenses</span></span>

<span data-ttu-id="74809-290">需要许多许可证才能使用 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="74809-290">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="74809-291">**未准备就绪**</span><span class="sxs-lookup"><span data-stu-id="74809-291">**Not Ready**</span></span>

<span data-ttu-id="74809-292">你没有使用 Microsoft 托管桌面所需的所有许可证。</span><span class="sxs-lookup"><span data-stu-id="74809-292">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="74809-293">有关详细信息，请参阅 [Microsoft 托管桌面技术](../intro/technologies.md) 和 [有关许可证的详细](prerequisites.md#more-about-licenses)信息。</span><span class="sxs-lookup"><span data-stu-id="74809-293">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="74809-294">安全帐户名称</span><span class="sxs-lookup"><span data-stu-id="74809-294">Security account names</span></span>

<span data-ttu-id="74809-295">某些安全帐户名称与 Microsoft 托管桌面创建的名称相冲突。</span><span class="sxs-lookup"><span data-stu-id="74809-295">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="74809-296">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="74809-296">**Not ready**</span></span>

<span data-ttu-id="74809-297">至少有一个帐户名称与 Microsoft 托管桌面创建的帐户名称冲突。</span><span class="sxs-lookup"><span data-stu-id="74809-297">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="74809-298">与你的 Microsoft 帐户代表合作，以排除这些帐户名称。</span><span class="sxs-lookup"><span data-stu-id="74809-298">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="74809-299">安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="74809-299">Security administrator roles</span></span>

<span data-ttu-id="74809-300">具有特定安全角色的用户必须在 Microsoft Defender for Endpoint 中分配这些角色。</span><span class="sxs-lookup"><span data-stu-id="74809-300">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="74809-301">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-301">**Advisory**</span></span>

<span data-ttu-id="74809-302">如果你已将用户分配到 Azure AD 组织中的任何角色，请确保他们还在 Microsoft Defender for Endpoint 中分配了这些角色。</span><span class="sxs-lookup"><span data-stu-id="74809-302">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="74809-303">否则，拥有这些角色的管理员将无法访问管理门户。</span><span class="sxs-lookup"><span data-stu-id="74809-303">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="74809-304">安全操作员</span><span class="sxs-lookup"><span data-stu-id="74809-304">Security Operator</span></span>
- <span data-ttu-id="74809-305">全局读取者</span><span class="sxs-lookup"><span data-stu-id="74809-305">Global Reader</span></span>

<span data-ttu-id="74809-306">有关详细信息，请参阅 [创建和管理基于角色的访问控制的角色](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)。</span><span class="sxs-lookup"><span data-stu-id="74809-306">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="74809-307">安全性默认</span><span class="sxs-lookup"><span data-stu-id="74809-307">Security default</span></span>

<span data-ttu-id="74809-308">Azure Active Directory 中的安全性默认值将阻止 Microsoft 托管桌面管理设备。</span><span class="sxs-lookup"><span data-stu-id="74809-308">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="74809-309">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="74809-309">**Not ready**</span></span>

<span data-ttu-id="74809-310">您启用了安全默认设置。</span><span class="sxs-lookup"><span data-stu-id="74809-310">You have Security defaults turned on.</span></span> <span data-ttu-id="74809-311">关闭安全默认设置并设置条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="74809-311">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="74809-312">有关详细信息，请参阅 [常见条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。</span><span class="sxs-lookup"><span data-stu-id="74809-312">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="74809-313">自助服务密码重置</span><span class="sxs-lookup"><span data-stu-id="74809-313">Self-service Password Reset</span></span>

<span data-ttu-id="74809-314">自助服务密码重置 (应为所有不包括 Microsoft 托管桌面服务帐户的 Microsoft 托管桌面用户启用 SSPR) 。</span><span class="sxs-lookup"><span data-stu-id="74809-314">Self-service Password Reset (SSPR) should be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="74809-315">有关详细信息，请参阅 [教程：使用户能够解锁其帐户或使用 Azure Active Directory 自助服务密码重置重置密码](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)。</span><span class="sxs-lookup"><span data-stu-id="74809-315">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="74809-316">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-316">**Advisory**</span></span>

<span data-ttu-id="74809-317">请确保 SSPR **选择** 的设置包括 Microsoft 托管桌面设备，但不包括 Microsoft 托管桌面服务帐户。</span><span class="sxs-lookup"><span data-stu-id="74809-317">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="74809-318">启用 SSPR 后，Microsoft 托管桌面服务帐户无法按预期工作。</span><span class="sxs-lookup"><span data-stu-id="74809-318">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="74809-319">标准用户角色</span><span class="sxs-lookup"><span data-stu-id="74809-319">Standard user role</span></span>

<span data-ttu-id="74809-320">除了分配有全局管理员和设备管理员的 Azure AD 角色的用户之外，Microsoft 托管桌面用户将是没有本地管理员权限的标准用户。</span><span class="sxs-lookup"><span data-stu-id="74809-320">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="74809-321">在启动 Microsoft 托管桌面设备时，将为所有其他用户分配一个标准用户角色。</span><span class="sxs-lookup"><span data-stu-id="74809-321">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="74809-322">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-322">**Advisory**</span></span>

<span data-ttu-id="74809-323">Microsoft 托管桌面用户在注册后将不具有对其 Microsoft 托管桌面设备的本地管理员权限。</span><span class="sxs-lookup"><span data-stu-id="74809-323">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="74809-324">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="74809-324">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="74809-325">OneDrive</span><span class="sxs-lookup"><span data-stu-id="74809-325">OneDrive</span></span>

<span data-ttu-id="74809-326">" **仅允许在加入特定域的电脑上进行同步** " 设置将与 Microsoft 托管桌面发生冲突。</span><span class="sxs-lookup"><span data-stu-id="74809-326">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="74809-327">**欲**</span><span class="sxs-lookup"><span data-stu-id="74809-327">**Advisory**</span></span>

<span data-ttu-id="74809-328">您正在使用 " **仅允许在加入特定域的 pc 上同步** " 设置。</span><span class="sxs-lookup"><span data-stu-id="74809-328">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="74809-329">此设置不适用于 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="74809-329">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="74809-330">禁用此设置，而将 OneDrive 设置为使用条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="74809-330">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="74809-331">请参阅 [规划条件访问部署](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 以获取帮助。</span><span class="sxs-lookup"><span data-stu-id="74809-331">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

