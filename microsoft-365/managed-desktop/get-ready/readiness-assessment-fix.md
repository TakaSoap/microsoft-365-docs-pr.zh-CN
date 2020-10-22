---
title: 解决准备情况评估工具发现的问题
description: 对工具找到的每个问题执行的详细操作
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2c9638dc7b8c6d095b87cf81114f3812c8362597
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656126"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="d0931-104">解决准备情况评估工具发现的问题</span><span class="sxs-lookup"><span data-stu-id="d0931-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="d0931-105">对于每个检查，该工具将报告三个可能的结果之一：</span><span class="sxs-lookup"><span data-stu-id="d0931-105">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="d0931-106">结果</span><span class="sxs-lookup"><span data-stu-id="d0931-106">Result</span></span>  |<span data-ttu-id="d0931-107">含义</span><span class="sxs-lookup"><span data-stu-id="d0931-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="d0931-108">Ready</span><span class="sxs-lookup"><span data-stu-id="d0931-108">Ready</span></span>     | <span data-ttu-id="d0931-109">完成注册前不需要执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="d0931-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="d0931-110">欲</span><span class="sxs-lookup"><span data-stu-id="d0931-110">Advisory</span></span>    | <span data-ttu-id="d0931-111">按照工具或本文中的步骤操作，以获取注册和用户的最佳体验。</span><span class="sxs-lookup"><span data-stu-id="d0931-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="d0931-112">你 *可以* 完成注册，但必须先解决这些问题，然后再部署你的第一个设备。</span><span class="sxs-lookup"><span data-stu-id="d0931-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="d0931-113">未就绪</span><span class="sxs-lookup"><span data-stu-id="d0931-113">Not ready</span></span> | <span data-ttu-id="d0931-114">*如果不解决这些问题，注册将失败。*</span><span class="sxs-lookup"><span data-stu-id="d0931-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="d0931-115">按照工具或本文中的步骤进行操作，以解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="d0931-115">Follow the steps in the tool or this article to resolve them.</span></span>        |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="d0931-116">Microsoft Intune 设置</span><span class="sxs-lookup"><span data-stu-id="d0931-116">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="d0931-117">Autopilot 部署配置文件</span><span class="sxs-lookup"><span data-stu-id="d0931-117">Autopilot deployment profile</span></span>

<span data-ttu-id="d0931-118">您不应具有任何目标为分配的或 Microsoft 托管桌面使用的动态组的现有 Autopilot 配置文件。</span><span class="sxs-lookup"><span data-stu-id="d0931-118">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="d0931-119">Microsoft 托管桌面使用 Autopilot 配置新设备。</span><span class="sxs-lookup"><span data-stu-id="d0931-119">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="d0931-120">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="d0931-120">**Not ready**</span></span>

<span data-ttu-id="d0931-121">您有一个分配给所有设备的 Autopilot 配置文件。</span><span class="sxs-lookup"><span data-stu-id="d0931-121">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="d0931-122">有关步骤，请参阅 [使用 Windows Autopilot 在 Intune 中注册 Windows 设备](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="d0931-122">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="d0931-123">在 Microsoft 托管桌面注册之后，将您的 Autopilot 策略设置为排除 **新式工作区设备-所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="d0931-123">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="d0931-124">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-124">**Advisory**</span></span>

<span data-ttu-id="d0931-125">确保您的 Autopilot 配置文件面向不包含将在注册中创建的 Microsoft 托管桌面设备的已分配或动态 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="d0931-125">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="d0931-126">有关步骤，请参阅 [使用 Windows Autopilot 在 Intune 中注册 Windows 设备](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="d0931-126">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="d0931-127">在 Microsoft 托管桌面注册之后，将您的 Autopilot 策略设置为排除 **新式工作区设备-所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="d0931-127">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="d0931-128">证书连接器</span><span class="sxs-lookup"><span data-stu-id="d0931-128">Certificate connectors</span></span>

<span data-ttu-id="d0931-129">如果你有要在 Microsoft 托管桌面中注册的设备使用的任何证书连接器，连接器将不能包含任何错误。</span><span class="sxs-lookup"><span data-stu-id="d0931-129">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="d0931-130">以下建议仅适用于你的情况，因此请仔细检查。</span><span class="sxs-lookup"><span data-stu-id="d0931-130">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="d0931-131">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-131">**Advisory**</span></span>

<span data-ttu-id="d0931-132">不存在任何证书连接器。</span><span class="sxs-lookup"><span data-stu-id="d0931-132">No certificate connectors are present.</span></span> <span data-ttu-id="d0931-133">您可能不需要任何连接器，但应评估是否需要对 Microsoft 托管桌面设备进行网络连接。</span><span class="sxs-lookup"><span data-stu-id="d0931-133">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d0931-134">有关详细信息，请参阅 [为 Microsoft 托管桌面准备证书和网络配置文件](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="d0931-134">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="d0931-135">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-135">**Advisory**</span></span>

<span data-ttu-id="d0931-136">至少一个证书连接器有错误。</span><span class="sxs-lookup"><span data-stu-id="d0931-136">At least one certificate connector has an error.</span></span> <span data-ttu-id="d0931-137">如果需要此连接器连接到 Microsoft 托管桌面设备，则必须解决该错误。</span><span class="sxs-lookup"><span data-stu-id="d0931-137">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="d0931-138">有关详细信息，请参阅 [为 Microsoft 托管桌面准备证书和网络配置文件](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="d0931-138">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="d0931-139">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-139">**Advisory**</span></span>

<span data-ttu-id="d0931-140">您至少有一个证书连接器，并且未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="d0931-140">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="d0931-141">但是，您可能需要创建一个配置文件以重用 Microsoft 托管桌面设备的连接器。</span><span class="sxs-lookup"><span data-stu-id="d0931-141">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d0931-142">有关详细信息，请参阅 [为 Microsoft 托管桌面准备证书和网络配置文件](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="d0931-142">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="d0931-143">条件访问策略</span><span class="sxs-lookup"><span data-stu-id="d0931-143">Conditional access policies</span></span>

<span data-ttu-id="d0931-144">Azure AD 组织中的条件访问策略不得以任何 Microsoft 管理桌面用户为目标。</span><span class="sxs-lookup"><span data-stu-id="d0931-144">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="d0931-145">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="d0931-145">**Not ready**</span></span>

<span data-ttu-id="d0931-146">您至少具有一个面向所有用户的条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="d0931-146">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="d0931-147">将策略重置为面向不包含将在注册时创建的 Microsoft 托管桌面服务帐户的 Azure AD 组的特定 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="d0931-147">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="d0931-148">有关步骤，请参阅 [条件访问：用户和组](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。</span><span class="sxs-lookup"><span data-stu-id="d0931-148">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="d0931-149">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-149">**Advisory**</span></span>

<span data-ttu-id="d0931-150">请确保您已排除了所有条件访问 **策略 "AZURE** AD 组"。</span><span class="sxs-lookup"><span data-stu-id="d0931-150">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="d0931-151">有关步骤，请参阅 [调整条件访问](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="d0931-151">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="d0931-152">**新式 Workplace Service 帐户**Azure AD 组是我们在注册时为服务创建的动态组。</span><span class="sxs-lookup"><span data-stu-id="d0931-152">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="d0931-153">注册后，必须返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="d0931-153">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="d0931-154">有关这些服务帐户的详细信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="d0931-154">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="d0931-155">设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="d0931-155">Device Compliance policies</span></span>

<span data-ttu-id="d0931-156">Azure AD 组织中的 Intune 设备合规性策略不得以任何 Microsoft 托管桌面用户为目标。</span><span class="sxs-lookup"><span data-stu-id="d0931-156">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="d0931-157">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="d0931-157">**Not ready**</span></span>

<span data-ttu-id="d0931-158">您至少具有一个面向所有用户的合规性策略。</span><span class="sxs-lookup"><span data-stu-id="d0931-158">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="d0931-159">将策略重置为面向不包含任何 Microsoft 托管桌面用户的特定 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="d0931-159">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="d0931-160">有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="d0931-160">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="d0931-161">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-161">**Advisory**</span></span>

<span data-ttu-id="d0931-162">确保任何不包含任何 Microsoft 托管桌面用户的合规性策略。</span><span class="sxs-lookup"><span data-stu-id="d0931-162">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="d0931-163">有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="d0931-163">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="d0931-164">设备配置策略</span><span class="sxs-lookup"><span data-stu-id="d0931-164">Device Configuration policies</span></span>

<span data-ttu-id="d0931-165">Azure AD 组织中的 Intune 设备配置策略不得以任何 Microsoft 管理桌面设备或用户为目标。</span><span class="sxs-lookup"><span data-stu-id="d0931-165">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="d0931-166">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="d0931-166">**Not ready**</span></span>

<span data-ttu-id="d0931-167">至少有一个针对所有用户、所有设备或同时针对这两者的配置策略。</span><span class="sxs-lookup"><span data-stu-id="d0931-167">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="d0931-168">将策略重置为面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="d0931-168">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d0931-169">有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="d0931-169">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="d0931-170">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-170">**Advisory**</span></span>

<span data-ttu-id="d0931-171">确保任何不包含任何 Microsoft 托管桌面设备或用户的合规性策略。</span><span class="sxs-lookup"><span data-stu-id="d0931-171">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="d0931-172">有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="d0931-172">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="d0931-173">设备类型限制</span><span class="sxs-lookup"><span data-stu-id="d0931-173">Device type restrictions</span></span>

<span data-ttu-id="d0931-174">必须允许 Microsoft 托管桌面设备在 Intune 中注册。</span><span class="sxs-lookup"><span data-stu-id="d0931-174">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="d0931-175">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="d0931-175">**Not ready**</span></span>

<span data-ttu-id="d0931-176">按照 " [设置注册限制](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) " 中的步骤将设置更改为 " **允许**"。</span><span class="sxs-lookup"><span data-stu-id="d0931-176">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="d0931-177">"注册状态" 页</span><span class="sxs-lookup"><span data-stu-id="d0931-177">Enrollment Status Page</span></span>

<span data-ttu-id="d0931-178">您当前已启用 "注册状态" 页面 (ESP) 。</span><span class="sxs-lookup"><span data-stu-id="d0931-178">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="d0931-179">如果你参与此功能的公开预览，则可以忽略此项。</span><span class="sxs-lookup"><span data-stu-id="d0931-179">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="d0931-180">有关详细信息，请参阅 [首次运行体验 With Autopilot 和注册状态页](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="d0931-180">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="d0931-181">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="d0931-181">**Not ready**</span></span>

<span data-ttu-id="d0931-182">您已将 ESP 默认配置文件设置为 **显示应用和配置文件配置进度**。</span><span class="sxs-lookup"><span data-stu-id="d0931-182">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="d0931-183">按照 " [设置注册状态" 页](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)中的步骤禁用此设置。</span><span class="sxs-lookup"><span data-stu-id="d0931-183">Disable this setting by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="d0931-184">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-184">**Advisory**</span></span>

<span data-ttu-id="d0931-185">确保具有 " **显示应用程序" 和 "配置文件配置进度** " 设置的任何配置文件未分配给任何包含 Microsoft 托管桌面设备的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="d0931-185">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d0931-186">有关详细信息，请参阅 [设置注册状态页](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="d0931-186">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="d0931-187">Intune 注册</span><span class="sxs-lookup"><span data-stu-id="d0931-187">Intune enrollment</span></span>

<span data-ttu-id="d0931-188">Azure AD 组织中的 Windows 10 设备必须在 Intune 中自动注册。</span><span class="sxs-lookup"><span data-stu-id="d0931-188">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="d0931-189">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="d0931-189">**Not ready**</span></span>

<span data-ttu-id="d0931-190">Azure AD 组织中的用户不会在 Microsoft Intune 中自动注册。</span><span class="sxs-lookup"><span data-stu-id="d0931-190">Users in your Azure AD organization aren't automatically enrolled in Microsoft Intune.</span></span> <span data-ttu-id="d0931-191">将 MDM 用户作用域更改为 **部分** 或 **全部**。</span><span class="sxs-lookup"><span data-stu-id="d0931-191">Change the MDM User scope to **Some** or **All**.</span></span> <span data-ttu-id="d0931-192">如果选择 ""。</span><span class="sxs-lookup"><span data-stu-id="d0931-192">If you choose.</span></span> <span data-ttu-id="d0931-193">某些 \* \* 会在注册后返回，并选择 **新式的工作场所-** **组**的所有 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="d0931-193">Some\*\*, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="d0931-194">适用于企业的 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="d0931-194">Microsoft Store for Business</span></span>

<span data-ttu-id="d0931-195">我们使用 Microsoft Store for Business，以便您可以下载公司门户，以部署一些应用程序，如 Microsoft Project 和 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="d0931-195">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="d0931-196">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="d0931-196">**Not ready**</span></span>

<span data-ttu-id="d0931-197">适用于企业的 Microsoft Store 不是已启用或未与 Intune 同步。</span><span class="sxs-lookup"><span data-stu-id="d0931-197">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="d0931-198">有关详细信息，请参阅 [如何使用 Microsoft Intune 在 Microsoft Store For Business 中管理批量购买的应用](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) ，并 [在设备上安装 Intune 公司门户](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="d0931-198">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="d0931-199">多重身份验证</span><span class="sxs-lookup"><span data-stu-id="d0931-199">Multi-factor authentication</span></span>

<span data-ttu-id="d0931-200">多因素身份验证不能意外应用于 Microsoft 托管桌面服务帐户。</span><span class="sxs-lookup"><span data-stu-id="d0931-200">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="d0931-201">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="d0931-201">**Not ready**</span></span>

<span data-ttu-id="d0931-202">您有一些多重身份验证 (MFA) 策略设置为分配给所有用户的条件访问策略的 "必需"。</span><span class="sxs-lookup"><span data-stu-id="d0931-202">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="d0931-203">将策略更改为使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的工作分配。</span><span class="sxs-lookup"><span data-stu-id="d0931-203">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d0931-204">有关详细信息，请参阅 [条件访问策略](#conditional-access-policies) 和 [条件访问：要求对所有用户进行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。</span><span class="sxs-lookup"><span data-stu-id="d0931-204">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="d0931-205">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-205">**Advisory**</span></span>

<span data-ttu-id="d0931-206">请确保任何需要 MFA 的条件访问策略排除 **新式工作区-所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="d0931-206">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="d0931-207">有关详细信息，请参阅 [条件访问策略](#conditional-access-policies) 和 [条件访问：要求对所有用户进行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。</span><span class="sxs-lookup"><span data-stu-id="d0931-207">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="d0931-208">**新式工作区-所有**Azure AD 组是在注册 Microsoft 托管桌面时创建的动态组，因此你必须在注册后返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="d0931-208">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>



### <a name="powershell-scripts"></a><span data-ttu-id="d0931-209">PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="d0931-209">PowerShell scripts</span></span>

<span data-ttu-id="d0931-210">无法以 Microsoft 托管桌面设备的目标方式分配 Windows PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="d0931-210">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="d0931-211">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-211">**Advisory**</span></span>

<span data-ttu-id="d0931-212">请确保 Azure AD 组织中的 Windows PowerShell 脚本不会针对任何 Microsoft 管理桌面设备或用户。</span><span class="sxs-lookup"><span data-stu-id="d0931-212">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="d0931-213">有关详细信息，请参阅在 [Intune 中使用 Windows 10 设备上的 PowerShell 脚本](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)。</span><span class="sxs-lookup"><span data-stu-id="d0931-213">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="d0931-214">区域</span><span class="sxs-lookup"><span data-stu-id="d0931-214">Region</span></span>

<span data-ttu-id="d0931-215">Microsoft 托管桌面必须支持你的区域。</span><span class="sxs-lookup"><span data-stu-id="d0931-215">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="d0931-216">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="d0931-216">**Not ready**</span></span>

<span data-ttu-id="d0931-217">Microsoft 托管桌面目前不支持 Azure AD 组织区域。</span><span class="sxs-lookup"><span data-stu-id="d0931-217">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="d0931-218">有关详细信息，请参阅 [Microsoft 托管桌面支持的区域和语言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="d0931-218">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="d0931-219">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-219">**Advisory**</span></span>

<span data-ttu-id="d0931-220">Microsoft 托管桌面不支持 Azure AD 组织所在的一个或多个国家/地区。</span><span class="sxs-lookup"><span data-stu-id="d0931-220">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="d0931-221">有关详细信息，请参阅 [Microsoft 托管桌面支持的区域和语言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="d0931-221">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="d0931-222">安全基准</span><span class="sxs-lookup"><span data-stu-id="d0931-222">Security baselines</span></span>

<span data-ttu-id="d0931-223">安全基准策略不应以任何 Microsoft 托管桌面设备为目标。</span><span class="sxs-lookup"><span data-stu-id="d0931-223">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="d0931-224">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="d0931-224">**Not ready**</span></span>

<span data-ttu-id="d0931-225">您有一个面向所有用户、所有设备或两者的安全基准配置文件。</span><span class="sxs-lookup"><span data-stu-id="d0931-225">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="d0931-226">将策略更改为使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的工作分配。</span><span class="sxs-lookup"><span data-stu-id="d0931-226">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d0931-227">有关步骤，请参阅 [使用安全基准在 Intune 中配置 Windows 10 设备](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="d0931-227">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="d0931-228">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-228">**Advisory**</span></span>

<span data-ttu-id="d0931-229">请确保任何安全基准策略都已排除 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="d0931-229">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d0931-230">有关步骤，请参阅 [使用安全基准在 Intune 中配置 Windows 10 设备](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="d0931-230">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="d0931-231">**新式工作区设备-所有**Azure AD 组是在注册 Microsoft 托管桌面时创建的动态组，因此你必须在注册后返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="d0931-231">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="d0931-232">Windows 应用</span><span class="sxs-lookup"><span data-stu-id="d0931-232">Windows apps</span></span>

<span data-ttu-id="d0931-233">查看你希望 Microsoft 托管桌面用户拥有的应用。</span><span class="sxs-lookup"><span data-stu-id="d0931-233">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="d0931-234">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-234">**Advisory**</span></span>

<span data-ttu-id="d0931-235">应准备您希望 Microsoft 托管桌面用户拥有的应用程序的清单。</span><span class="sxs-lookup"><span data-stu-id="d0931-235">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="d0931-236">请确保这些应用程序可由 Intune 部署。</span><span class="sxs-lookup"><span data-stu-id="d0931-236">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="d0931-237">有关详细信息，请参阅 [Microsoft 托管桌面中的应用程序](apps.md)。</span><span class="sxs-lookup"><span data-stu-id="d0931-237">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="d0931-238">可以在 Microsoft 终结点配置管理器中向 Microsoft 帐户代表查询，以确定那些准备迁移到 Intune 或需要调整的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d0931-238">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="d0931-239">Windows Hello 企业版</span><span class="sxs-lookup"><span data-stu-id="d0931-239">Windows Hello for Business</span></span>

<span data-ttu-id="d0931-240">Microsoft 托管桌面要求启用 Windows Hello 企业版。</span><span class="sxs-lookup"><span data-stu-id="d0931-240">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="d0931-241">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="d0931-241">**Not ready**</span></span>

<span data-ttu-id="d0931-242">Windows Hello 企业版已禁用。</span><span class="sxs-lookup"><span data-stu-id="d0931-242">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="d0931-243">按照[创建 Windows Hello 企业版策略](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)中的步骤启用它</span><span class="sxs-lookup"><span data-stu-id="d0931-243">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="d0931-244">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-244">**Advisory**</span></span>

<span data-ttu-id="d0931-245">Windows Hello 企业版尚未设置。</span><span class="sxs-lookup"><span data-stu-id="d0931-245">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="d0931-246">按照 [创建 Windows Hello 企业版策略](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)中的步骤启用它。</span><span class="sxs-lookup"><span data-stu-id="d0931-246">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="d0931-247">Windows 10 更新环</span><span class="sxs-lookup"><span data-stu-id="d0931-247">Windows 10 update rings</span></span>

<span data-ttu-id="d0931-248">Intune 中的 "Windows 10 更新循环" 策略不得以任何 Microsoft 托管桌面设备为目标。</span><span class="sxs-lookup"><span data-stu-id="d0931-248">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="d0931-249">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="d0931-249">**Not ready**</span></span>

<span data-ttu-id="d0931-250">您有一个面向所有设备和/或所有用户的 "更新循环" 策略。</span><span class="sxs-lookup"><span data-stu-id="d0931-250">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="d0931-251">将策略更改为使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的工作分配。</span><span class="sxs-lookup"><span data-stu-id="d0931-251">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d0931-252">有关步骤，请参阅 [在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="d0931-252">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="d0931-253">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-253">**Advisory**</span></span>

<span data-ttu-id="d0931-254">确保任何更新环策略均已排除 **新式工作区-所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="d0931-254">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="d0931-255">有关步骤，请参阅 [在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="d0931-255">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="d0931-256">**新式工作区设备-所有**Azure AD 组是在注册 Microsoft 托管桌面时创建的动态组，因此你必须在注册后返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="d0931-256">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="d0931-257">Azure Active Directory 设置</span><span class="sxs-lookup"><span data-stu-id="d0931-257">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="d0931-258">临时订阅</span><span class="sxs-lookup"><span data-stu-id="d0931-258">Ad hoc subscriptions</span></span>

<span data-ttu-id="d0931-259">建议如何检查 (如果设置为 "false" 的设置 ) 可能会阻止企业状态漫游正常工作。</span><span class="sxs-lookup"><span data-stu-id="d0931-259">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="d0931-260">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-260">**Advisory**</span></span>

<span data-ttu-id="d0931-261">确保将 **AllowAdHocSubscriptions** 设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="d0931-261">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="d0931-262">否则，企业状态漫游可能无法工作。</span><span class="sxs-lookup"><span data-stu-id="d0931-262">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="d0931-263">有关详细信息，请参阅 [set-msolcompanysettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="d0931-263">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="d0931-264">企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="d0931-264">Enterprise State Roaming</span></span>

<span data-ttu-id="d0931-265">应启用企业状态漫游。</span><span class="sxs-lookup"><span data-stu-id="d0931-265">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="d0931-266">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-266">**Advisory**</span></span>

<span data-ttu-id="d0931-267">确保为 **所有** 或 **选定** 的组启用了企业状态漫游。</span><span class="sxs-lookup"><span data-stu-id="d0931-267">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="d0931-268">有关详细信息，请参阅 [在 Azure Active Directory 中启用企业状态漫游](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)。</span><span class="sxs-lookup"><span data-stu-id="d0931-268">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="d0931-269">许可证</span><span class="sxs-lookup"><span data-stu-id="d0931-269">Licenses</span></span>

<span data-ttu-id="d0931-270">需要许多许可证才能使用 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="d0931-270">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="d0931-271">**未准备就绪**</span><span class="sxs-lookup"><span data-stu-id="d0931-271">**Not Ready**</span></span>

<span data-ttu-id="d0931-272">你没有使用 Microsoft 托管桌面所需的所有许可证。</span><span class="sxs-lookup"><span data-stu-id="d0931-272">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="d0931-273">有关详细信息，请参阅 [Microsoft 托管桌面技术](../intro/technologies.md) 和 [有关许可证的详细](prerequisites.md#more-about-licenses)信息。</span><span class="sxs-lookup"><span data-stu-id="d0931-273">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="d0931-274">安全帐户名称</span><span class="sxs-lookup"><span data-stu-id="d0931-274">Security account names</span></span>

<span data-ttu-id="d0931-275">某些安全帐户名称与 Microsoft 托管桌面创建的名称相冲突。</span><span class="sxs-lookup"><span data-stu-id="d0931-275">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="d0931-276">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="d0931-276">**Not ready**</span></span>

<span data-ttu-id="d0931-277">至少有一个帐户名称与 Microsoft 托管桌面创建的帐户名称冲突。</span><span class="sxs-lookup"><span data-stu-id="d0931-277">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="d0931-278">与你的 Microsoft 帐户代表合作，以排除这些帐户名称。</span><span class="sxs-lookup"><span data-stu-id="d0931-278">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="d0931-279">安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="d0931-279">Security administrator roles</span></span>

<span data-ttu-id="d0931-280">具有特定安全角色的用户必须在 Microsoft Defender for Endpoint 中分配这些角色。</span><span class="sxs-lookup"><span data-stu-id="d0931-280">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="d0931-281">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-281">**Advisory**</span></span>

<span data-ttu-id="d0931-282">如果你在 Azure AD 组织中分配了这些角色中的任何角色，请确保他们还在 Microsoft Defender for Endpoint 中分配了这些角色。</span><span class="sxs-lookup"><span data-stu-id="d0931-282">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="d0931-283">否则，拥有这些角色的管理员将无法访问管理门户。</span><span class="sxs-lookup"><span data-stu-id="d0931-283">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="d0931-284">安全读取者</span><span class="sxs-lookup"><span data-stu-id="d0931-284">Security Reader</span></span>
- <span data-ttu-id="d0931-285">安全操作员</span><span class="sxs-lookup"><span data-stu-id="d0931-285">Security Operator</span></span>
- <span data-ttu-id="d0931-286">全局读取者</span><span class="sxs-lookup"><span data-stu-id="d0931-286">Global Reader</span></span>

<span data-ttu-id="d0931-287">有关详细信息，请参阅 [创建和管理基于角色的访问控制的角色](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)。</span><span class="sxs-lookup"><span data-stu-id="d0931-287">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="d0931-288">安全性默认</span><span class="sxs-lookup"><span data-stu-id="d0931-288">Security default</span></span>

<span data-ttu-id="d0931-289">Azure Active Directory 中的安全性默认值将阻止 Microsoft 托管桌面管理设备。</span><span class="sxs-lookup"><span data-stu-id="d0931-289">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="d0931-290">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="d0931-290">**Not ready**</span></span>

<span data-ttu-id="d0931-291">您启用了安全默认设置。</span><span class="sxs-lookup"><span data-stu-id="d0931-291">You have Security defaults turned on.</span></span> <span data-ttu-id="d0931-292">关闭安全默认设置并设置条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="d0931-292">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="d0931-293">有关详细信息，请参阅 [常见条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。</span><span class="sxs-lookup"><span data-stu-id="d0931-293">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="d0931-294">自助服务密码重置</span><span class="sxs-lookup"><span data-stu-id="d0931-294">Self-service Password Reset</span></span>

<span data-ttu-id="d0931-295">必须启用自助密码重置 (SSPR) 。</span><span class="sxs-lookup"><span data-stu-id="d0931-295">Self-service Password Reset (SSPR) must be enabled.</span></span>

<span data-ttu-id="d0931-296">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="d0931-296">**Not ready**</span></span>

<span data-ttu-id="d0931-297">必须为所有用户启用 SSPR。</span><span class="sxs-lookup"><span data-stu-id="d0931-297">SSPR must be enabled for all users.</span></span> <span data-ttu-id="d0931-298">如果不是，Microsoft 托管桌面服务帐户将无法工作。</span><span class="sxs-lookup"><span data-stu-id="d0931-298">If it isn't, the Microsoft Managed Desktop service accounts can't work.</span></span> <span data-ttu-id="d0931-299">有关详细信息，请参阅 [教程：使用户能够解锁其帐户或使用 Azure Active Directory 自助服务密码重置重置密码](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)。</span><span class="sxs-lookup"><span data-stu-id="d0931-299">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="d0931-300">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-300">**Advisory**</span></span>

<span data-ttu-id="d0931-301">请确保 SSPR **选择** 的设置包括 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="d0931-301">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices.</span></span>

### <a name="standard-user-role"></a><span data-ttu-id="d0931-302">标准用户角色</span><span class="sxs-lookup"><span data-stu-id="d0931-302">Standard user role</span></span>

<span data-ttu-id="d0931-303">Microsoft 托管桌面用户应是没有本地管理员权限的标准用户。</span><span class="sxs-lookup"><span data-stu-id="d0931-303">Microsoft Managed Desktop users should be standard users without local administrator privileges.</span></span> <span data-ttu-id="d0931-304">他们将在启动 Microsoft 托管桌面设备时为其分配一个标准用户角色。</span><span class="sxs-lookup"><span data-stu-id="d0931-304">They'll be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="d0931-305">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-305">**Advisory**</span></span>

<span data-ttu-id="d0931-306">Microsoft 托管桌面用户在注册前不应具有本地管理员权限。</span><span class="sxs-lookup"><span data-stu-id="d0931-306">Microsoft Managed Desktop users shouldn't have local administrator privileges prior to enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="d0931-307">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="d0931-307">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="d0931-308">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d0931-308">OneDrive for Business</span></span>

<span data-ttu-id="d0931-309">" **仅允许在加入特定域的电脑上进行同步** " 设置将与 Microsoft 托管桌面发生冲突。</span><span class="sxs-lookup"><span data-stu-id="d0931-309">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="d0931-310">**欲**</span><span class="sxs-lookup"><span data-stu-id="d0931-310">**Advisory**</span></span>

<span data-ttu-id="d0931-311">您正在使用 " **仅允许在加入特定域的 pc 上同步** " 设置。</span><span class="sxs-lookup"><span data-stu-id="d0931-311">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="d0931-312">此设置不适用于 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="d0931-312">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="d0931-313">禁用此设置，而将 OneDrive for business 设置为使用条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="d0931-313">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="d0931-314">请参阅 [规划条件访问部署](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 以获取帮助。</span><span class="sxs-lookup"><span data-stu-id="d0931-314">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

