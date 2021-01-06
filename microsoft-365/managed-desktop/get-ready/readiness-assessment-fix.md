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
ms.openlocfilehash: 3c3c0d21ca93c0d93d17cefbc6ce630d00a16d09
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760120"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="4a6aa-104">修复准备情况评估工具发现的问题</span><span class="sxs-lookup"><span data-stu-id="4a6aa-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="4a6aa-105">对于每个检查，该工具将报告四个可能的结果之一：</span><span class="sxs-lookup"><span data-stu-id="4a6aa-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="4a6aa-106">结果</span><span class="sxs-lookup"><span data-stu-id="4a6aa-106">Result</span></span>  |<span data-ttu-id="4a6aa-107">含义</span><span class="sxs-lookup"><span data-stu-id="4a6aa-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="4a6aa-108">Ready</span><span class="sxs-lookup"><span data-stu-id="4a6aa-108">Ready</span></span>     | <span data-ttu-id="4a6aa-109">完成注册前无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="4a6aa-110">公告</span><span class="sxs-lookup"><span data-stu-id="4a6aa-110">Advisory</span></span>    | <span data-ttu-id="4a6aa-111">按照工具或本文中的步骤操作，实现注册和用户的最佳体验。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="4a6aa-112">*你可以完成* 注册，但在部署第一台设备之前必须解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="4a6aa-113">未就绪</span><span class="sxs-lookup"><span data-stu-id="4a6aa-113">Not ready</span></span> | <span data-ttu-id="4a6aa-114">*如果不解决这些问题，注册将失败。*</span><span class="sxs-lookup"><span data-stu-id="4a6aa-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="4a6aa-115">按照工具或本文中的步骤进行解析。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="4a6aa-116">错误</span><span class="sxs-lookup"><span data-stu-id="4a6aa-116">Error</span></span> | <span data-ttu-id="4a6aa-117">Azure Active Director (AD) 你使用的角色没有足够的权限来运行此检查。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

> [!NOTE]
> <span data-ttu-id="4a6aa-118">此工具报告的结果仅在运行设置的特定时间点反映设置的状态。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-118">The results reported by this tool reflect the status of your settings only at the specific point in time that you ran it.</span></span> <span data-ttu-id="4a6aa-119">如果稍后对 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的策略进行了任何更改，则"就绪"的项目可能会变为"未准备就绪"。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-119">If you later make any changes to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, items that were "Ready" can become "Not ready."</span></span> <span data-ttu-id="4a6aa-120">为了避免 Microsoft 托管桌面操作出现问题，请在更改任何策略之前检查本文中描述的特定设置。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-120">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in this article before you change any policies.</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="4a6aa-121">Microsoft Intune 设置</span><span class="sxs-lookup"><span data-stu-id="4a6aa-121">Microsoft Intune settings</span></span>

<span data-ttu-id="4a6aa-122">可以在 Microsoft Endpoint Manager 管理中心访问 Intune [设置](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-122">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="4a6aa-123">Autopilot 部署配置文件</span><span class="sxs-lookup"><span data-stu-id="4a6aa-123">Autopilot deployment profile</span></span>

<span data-ttu-id="4a6aa-124">你不应具有任何面向 Microsoft 托管桌面所分配或动态组的现有 Autopilot 配置文件。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-124">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="4a6aa-125">Microsoft 托管桌面使用 Autopilot 预配新设备。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-125">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="4a6aa-126">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-126">**Not ready**</span></span>

<span data-ttu-id="4a6aa-127">你拥有分配给所有设备的 Autopilot 配置文件。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-127">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="4a6aa-128">有关步骤，请参阅 [使用 Windows Autopilot 在 Intune 中注册 Windows 设备](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="4a6aa-129">注册 Microsoft 托管桌面后，设置 Autopilot 策略以排除 **现代工作区设备 -所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="4a6aa-130">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-130">**Advisory**</span></span>

<span data-ttu-id="4a6aa-131">确保 Autopilot 配置文件面向分配或动态的 Azure AD 组，该组不包括将在注册时创建的 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-131">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="4a6aa-132">有关步骤，请参阅 [使用 Windows Autopilot 在 Intune 中注册 Windows 设备](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-132">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="4a6aa-133">注册 Microsoft 托管桌面后，设置 Autopilot 策略以排除 **现代工作区设备 -所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-133">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="4a6aa-134">证书连接器</span><span class="sxs-lookup"><span data-stu-id="4a6aa-134">Certificate connectors</span></span>

<span data-ttu-id="4a6aa-135">如果要在 Microsoft 托管桌面中注册的设备使用了任何证书连接器，则连接器不能有任何错误。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-135">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="4a6aa-136">只有下列公告之一适用于你的情况，因此请仔细检查。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-136">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="4a6aa-137">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-137">**Advisory**</span></span>

<span data-ttu-id="4a6aa-138">不存在证书连接器。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-138">No certificate connectors are present.</span></span> <span data-ttu-id="4a6aa-139">你可能不需要任何连接器，但应评估是否需要一些连接器来建立与 Microsoft 托管桌面设备的网络连接。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-139">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4a6aa-140">有关详细信息，请参阅为 [Microsoft 托管桌面准备证书和网络配置文件](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="4a6aa-141">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-141">**Advisory**</span></span>

<span data-ttu-id="4a6aa-142">至少有一个证书连接器出错。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-142">At least one certificate connector has an error.</span></span> <span data-ttu-id="4a6aa-143">如果需要此连接器才能连接到 Microsoft 托管桌面设备，则必须解决此错误。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-143">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="4a6aa-144">有关详细信息，请参阅为 [Microsoft 托管桌面准备证书和网络配置文件](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="4a6aa-145">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-145">**Advisory**</span></span>

<span data-ttu-id="4a6aa-146">您至少有一个证书连接器，并且未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-146">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="4a6aa-147">但是，您可能需要创建配置文件以重用 Microsoft 托管桌面设备的连接器。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-147">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4a6aa-148">有关详细信息，请参阅为 [Microsoft 托管桌面准备证书和网络配置文件](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-148">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="4a6aa-149">条件访问策略</span><span class="sxs-lookup"><span data-stu-id="4a6aa-149">Conditional access policies</span></span>

<span data-ttu-id="4a6aa-150">Azure AD 组织中的条件访问策略不得面向任何 Microsoft 管理桌面用户。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-150">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="4a6aa-151">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-151">**Not ready**</span></span>

<span data-ttu-id="4a6aa-152">您至少有一个面向所有用户的条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-152">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="4a6aa-153">将策略重置为面向特定的 Azure AD 组，该组不包括将在注册时创建的 Microsoft 托管桌面服务帐户的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-153">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="4a6aa-154">有关步骤，请参阅 [条件访问：用户和组](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-154">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="4a6aa-155">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-155">**Advisory**</span></span>

<span data-ttu-id="4a6aa-156">确保已排除新式 **工作区** 服务帐户 Azure AD 组的任何条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-156">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="4a6aa-157">有关步骤，请参阅["调整条件访问"。](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)</span><span class="sxs-lookup"><span data-stu-id="4a6aa-157">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="4a6aa-158">新式 **工作区服务帐户** Azure AD 组是我们在注册时为服务创建的动态组。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-158">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="4a6aa-159">注册后，必须返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-159">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="4a6aa-160">有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-160">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="4a6aa-161">**错误**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-161">**Error**</span></span>

<span data-ttu-id="4a6aa-162">Intune 管理员角色没有足够的权限进行此检查。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-162">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="4a6aa-163">你还需要分配有以下任一 Azure AD 角色来运行此检查：</span><span class="sxs-lookup"><span data-stu-id="4a6aa-163">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="4a6aa-164">安全读取者</span><span class="sxs-lookup"><span data-stu-id="4a6aa-164">Security Reader</span></span>
- <span data-ttu-id="4a6aa-165">安全管理员</span><span class="sxs-lookup"><span data-stu-id="4a6aa-165">Security Administrator</span></span>
- <span data-ttu-id="4a6aa-166">条件访问管理员</span><span class="sxs-lookup"><span data-stu-id="4a6aa-166">Conditional Access Administrator</span></span>
- <span data-ttu-id="4a6aa-167">全局读取者</span><span class="sxs-lookup"><span data-stu-id="4a6aa-167">Global Reader</span></span>
- <span data-ttu-id="4a6aa-168">设备管理员</span><span class="sxs-lookup"><span data-stu-id="4a6aa-168">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="4a6aa-169">设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="4a6aa-169">Device Compliance policies</span></span>

<span data-ttu-id="4a6aa-170">Azure AD 组织的 Intune 设备合规性策略不得面向任何 Microsoft 托管桌面用户。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-170">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="4a6aa-171">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-171">**Not ready**</span></span>

<span data-ttu-id="4a6aa-172">您至少有一个面向所有用户的合规性策略。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-172">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="4a6aa-173">将策略重置为面向不包含任何 Microsoft 托管桌面用户的特定 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-173">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="4a6aa-174">有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-174">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="4a6aa-175">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-175">**Advisory**</span></span>

<span data-ttu-id="4a6aa-176">确保你拥有的任何合规性策略不包括任何 Microsoft 托管桌面用户。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-176">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="4a6aa-177">有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-177">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="4a6aa-178">设备配置策略</span><span class="sxs-lookup"><span data-stu-id="4a6aa-178">Device Configuration policies</span></span>

<span data-ttu-id="4a6aa-179">Azure AD 组织的 Intune 设备配置策略不得面向任何 Microsoft 管理桌面设备或用户。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-179">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="4a6aa-180">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-180">**Not ready**</span></span>

<span data-ttu-id="4a6aa-181">你至少具有一个面向所有用户、所有设备或两者的配置策略。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-181">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="4a6aa-182">将策略重置为面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-182">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4a6aa-183">有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-183">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="4a6aa-184">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-184">**Advisory**</span></span>

<span data-ttu-id="4a6aa-185">确保你拥有的任何合规性策略不包括任何 Microsoft 托管桌面设备或用户。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-185">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="4a6aa-186">有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-186">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="4a6aa-187">设备类型限制</span><span class="sxs-lookup"><span data-stu-id="4a6aa-187">Device type restrictions</span></span>

<span data-ttu-id="4a6aa-188">必须允许 Microsoft 托管桌面设备在 Intune 中注册。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-188">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="4a6aa-189">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-189">**Not ready**</span></span>

<span data-ttu-id="4a6aa-190">按照"设置注册 [限制"中的](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set)步骤将设置更改为 **"允许"。**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-190">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="4a6aa-191">注册状态页</span><span class="sxs-lookup"><span data-stu-id="4a6aa-191">Enrollment Status Page</span></span>

<span data-ttu-id="4a6aa-192">你当前已启用 ESP (注册) 页。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-192">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="4a6aa-193">如果参与此功能的公共预览版，可以忽略此项。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-193">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="4a6aa-194">有关详细信息，请参阅 [Autopilot 的首次运行体验和注册状态页](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-194">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="4a6aa-195">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-195">**Not ready**</span></span>

<span data-ttu-id="4a6aa-196">YOU have the ESP default profile set to **Show app and profile configuration progress.**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-196">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="4a6aa-197">通过按照"设置注册状态"页中的步骤操作，禁用此设置或确保任何 Azure AD 组的工作分配不包括 Microsoft 托管 [桌面设备](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-197">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="4a6aa-198">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-198">**Advisory**</span></span>

<span data-ttu-id="4a6aa-199">确保未将具有"显示应用"和配置文件配置进度设置的任何配置文件分配给任何包含 Microsoft 托管桌面设备的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-199">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4a6aa-200">有关详细信息，请参阅" [设置注册状态"页](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-200">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="4a6aa-201">Intune 注册</span><span class="sxs-lookup"><span data-stu-id="4a6aa-201">Intune enrollment</span></span>

<span data-ttu-id="4a6aa-202">必须在 Intune 中自动注册 Azure AD 组织中 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-202">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="4a6aa-203">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-203">**Advisory**</span></span>

<span data-ttu-id="4a6aa-204">确保 MDM 用户作用域设置为"部分"或 **"全部**"，而不是 **"无"。**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-204">Make sure the MDM User scope is set to **Some** or **All**, not **None**.</span></span> <span data-ttu-id="4a6aa-205">如果你选择 **"一些**"，请在注册后返回，然后为组选择 **新式工作区 -所有** Azure AD **组**。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-205">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="4a6aa-206">适用于企业的 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="4a6aa-206">Microsoft Store for Business</span></span>

<span data-ttu-id="4a6aa-207">我们使用适用于 Business 的 Microsoft Store，以便你可以下载公司门户来部署一些应用，如 Microsoft Project 和 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-207">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="4a6aa-208">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-208">**Not ready**</span></span>

<span data-ttu-id="4a6aa-209">适用于 Business 的 Microsoft Store 未启用或未与 Intune 同步。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-209">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="4a6aa-210">有关详细信息，请参阅如何使用 [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) 管理从适用于企业 Microsoft Store 购买的批量应用，以及如何在设备上安装 [Intune 公司门户](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-210">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multifactor-authentication"></a><span data-ttu-id="4a6aa-211">多重身份验证</span><span class="sxs-lookup"><span data-stu-id="4a6aa-211">Multifactor authentication</span></span>

<span data-ttu-id="4a6aa-212">多重身份验证不得意外应用于 Microsoft 托管桌面服务帐户。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-212">Multifactor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="4a6aa-213">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-213">**Not ready**</span></span>

<span data-ttu-id="4a6aa-214">对于分配给所有用户的条件访问 (，) MFA 身份验证策略设置为"必需"的多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-214">You have some multifactor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="4a6aa-215">更改策略以使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的工作分配。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-215">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4a6aa-216">有关详细信息，请参阅条件[访问策略](#conditional-access-policies)和[条件访问：要求所有用户使用 MFA。](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="4a6aa-216">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="4a6aa-217">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-217">**Advisory**</span></span>

<span data-ttu-id="4a6aa-218">确保任何需要 MFA 的条件访问策略都排除 **现代工作区 -所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-218">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="4a6aa-219">有关详细信息，请参阅条件[访问策略](#conditional-access-policies)和[条件访问：要求所有用户使用 MFA。](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="4a6aa-219">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="4a6aa-220">新式 **工作区 -所有** Azure AD 组是我们在注册 Microsoft 托管桌面时创建的动态组，因此你必须在注册后返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-220">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="4a6aa-221">**错误**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-221">**Error**</span></span>

<span data-ttu-id="4a6aa-222">Intune 管理员角色没有足够的权限进行此检查。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-222">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="4a6aa-223">你还需要分配有以下任一 Azure AD 角色来运行此检查：</span><span class="sxs-lookup"><span data-stu-id="4a6aa-223">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="4a6aa-224">安全读取者</span><span class="sxs-lookup"><span data-stu-id="4a6aa-224">Security Reader</span></span>
- <span data-ttu-id="4a6aa-225">安全管理员</span><span class="sxs-lookup"><span data-stu-id="4a6aa-225">Security Administrator</span></span>
- <span data-ttu-id="4a6aa-226">条件访问管理员</span><span class="sxs-lookup"><span data-stu-id="4a6aa-226">Conditional Access Administrator</span></span>
- <span data-ttu-id="4a6aa-227">全局读取者</span><span class="sxs-lookup"><span data-stu-id="4a6aa-227">Global Reader</span></span>
- <span data-ttu-id="4a6aa-228">设备管理员</span><span class="sxs-lookup"><span data-stu-id="4a6aa-228">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="4a6aa-229">PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="4a6aa-229">PowerShell scripts</span></span>

<span data-ttu-id="4a6aa-230">Windows PowerShell无法以面向 Microsoft 托管桌面设备的方式分配脚本。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-230">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="4a6aa-231">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-231">**Advisory**</span></span>

<span data-ttu-id="4a6aa-232">请确保 Azure AD Windows PowerShell中的脚本不面向任何 Microsoft 管理桌面设备或用户。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-232">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="4a6aa-233">不要将 PowerShell 脚本分配给所有用户、所有设备或两者。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-233">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="4a6aa-234">更改策略以使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的工作分配。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-234">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4a6aa-235">有关详细信息，请参阅 Intune 中的 [Windows 10 设备上使用 PowerShell 脚本](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-235">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="4a6aa-236">地区</span><span class="sxs-lookup"><span data-stu-id="4a6aa-236">Region</span></span>

<span data-ttu-id="4a6aa-237">你的区域必须受 Microsoft 托管桌面支持。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-237">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="4a6aa-238">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-238">**Not ready**</span></span>

<span data-ttu-id="4a6aa-239">你的 Azure AD 组织区域当前不受 Microsoft 托管桌面支持。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-239">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="4a6aa-240">有关详细信息，请参阅 [Microsoft 托管桌面支持的地区和语言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-240">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="4a6aa-241">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-241">**Advisory**</span></span>

<span data-ttu-id="4a6aa-242">Microsoft 托管桌面不支持 Azure AD 组织所在的一个或多个国家/地区。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-242">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="4a6aa-243">有关详细信息，请参阅 [Microsoft 托管桌面支持的地区和语言](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-243">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="4a6aa-244">安全基线</span><span class="sxs-lookup"><span data-stu-id="4a6aa-244">Security baselines</span></span>

<span data-ttu-id="4a6aa-245">安全基线策略不应面向任何 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-245">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="4a6aa-246">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-246">**Not ready**</span></span>

<span data-ttu-id="4a6aa-247">你有一个面向所有用户、所有设备或两者的安全基线配置文件。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-247">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="4a6aa-248">更改策略以使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的工作分配。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-248">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4a6aa-249">有关步骤，请参阅 [使用安全基线在 Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)中配置 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-249">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="4a6aa-250">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-250">**Advisory**</span></span>

<span data-ttu-id="4a6aa-251">确保已排除 Microsoft 托管桌面设备的任何安全基线策略。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-251">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4a6aa-252">有关步骤，请参阅 [使用安全基线在 Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)中配置 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-252">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="4a6aa-253">现代 **工作区设备 -所有** Azure AD 组是我们在注册 Microsoft 托管桌面时创建的动态组，因此你必须在注册后返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-253">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="4a6aa-254">Windows 应用</span><span class="sxs-lookup"><span data-stu-id="4a6aa-254">Windows apps</span></span>

<span data-ttu-id="4a6aa-255">查看希望 Microsoft 托管桌面用户拥有的应用。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-255">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="4a6aa-256">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-256">**Advisory**</span></span>

<span data-ttu-id="4a6aa-257">应准备希望 Microsoft 托管桌面用户拥有的应用清单。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-257">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="4a6aa-258">由于这些应用必须由 Intune 部署，因此请评估是否重新使用现有 Intune 应用。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-258">Since these apps must be deployed by Intune, evaluate re-using existing Intune apps.</span></span> <span data-ttu-id="4a6aa-259">请考虑使用公司门户 (请参阅"在设备上安装 [Intune](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) 公司门户"和"注册状态"页 (ESP) 将应用分发给用户。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-259">Consider using Company Portal (see [Install Intune Company Portal on devices](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="4a6aa-260">有关详细信息，请参阅 [Microsoft 托管桌面中的应用](apps.md) 和 Autopilot 首次运行体验和 [注册状态页](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-260">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run).</span></span>

<span data-ttu-id="4a6aa-261">你可以让 Microsoft 帐户代表在 Microsoft Endpoint Configuration Manager 中查询，以确定准备迁移到 Intune 或需要调整的应用。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-261">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="4a6aa-262">Windows Hello 企业版</span><span class="sxs-lookup"><span data-stu-id="4a6aa-262">Windows Hello for Business</span></span>

<span data-ttu-id="4a6aa-263">Microsoft 托管桌面需要启用 Windows Hello 企业版。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-263">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="4a6aa-264">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-264">**Not ready**</span></span>

<span data-ttu-id="4a6aa-265">Windows Hello 企业应用已禁用。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-265">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="4a6aa-266">按照"创建 Windows Hello 企业应用"策略 [中的步骤启用它](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="4a6aa-266">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="4a6aa-267">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-267">**Advisory**</span></span>

<span data-ttu-id="4a6aa-268">未设置 Windows Hello 企业应用。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-268">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="4a6aa-269">按照创建 Windows Hello 企业策略 [中的步骤启用它](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-269">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="4a6aa-270">Windows 10 更新圈</span><span class="sxs-lookup"><span data-stu-id="4a6aa-270">Windows 10 update rings</span></span>

<span data-ttu-id="4a6aa-271">Intune 中的"Windows 10 更新圈"策略不得面向任何 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-271">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="4a6aa-272">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-272">**Not ready**</span></span>

<span data-ttu-id="4a6aa-273">你有一个面向所有设备、所有用户或两者同时面向的"更新圈"策略。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-273">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="4a6aa-274">更改策略以使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的工作分配。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-274">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4a6aa-275">有关步骤，请参阅 [在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-275">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="4a6aa-276">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-276">**Advisory**</span></span>

<span data-ttu-id="4a6aa-277">确保你已排除任何更新圈策略，不包括 **现代工作区设备 -所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-277">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="4a6aa-278">如果你向这些策略分配了 Azure AD 用户组，请确保你已排除所有更新圈策略，其中还包括 Microsoft 托管桌面用户的现代 **工作区 -所有** Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-278">If you have assigned Azure AD user group to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group which includes your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="4a6aa-279">有关步骤，请参阅 [在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-279">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="4a6aa-280">现代 **工作区设备-全部** 和现代工作区 **-** 所有 Azure AD 组均分配有你在 Microsoft 托管桌面中注册时创建的组，因此你必须在注册后返回以排除此组。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-280">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are assigned groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="4a6aa-281">Azure Active Directory 设置</span><span class="sxs-lookup"><span data-stu-id="4a6aa-281">Azure Active Directory settings</span></span>

<span data-ttu-id="4a6aa-282">可以在 Azure 门户访问 Azure Active Directory [设置](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-282">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="4a6aa-283">临时订阅</span><span class="sxs-lookup"><span data-stu-id="4a6aa-283">Ad hoc subscriptions</span></span>

<span data-ttu-id="4a6aa-284">建议如何检查设置为 (false"的设置) 可能会阻止企业状态漫游正常工作。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-284">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="4a6aa-285">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-285">**Advisory**</span></span>

<span data-ttu-id="4a6aa-286">确保 **AllowAdHocSubscriptions** 设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-286">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="4a6aa-287">否则，企业状态漫游可能无法工作。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-287">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="4a6aa-288">有关详细信息，请参阅 [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-288">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="4a6aa-289">企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="4a6aa-289">Enterprise State Roaming</span></span>

<span data-ttu-id="4a6aa-290">应启用企业状态漫游。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-290">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="4a6aa-291">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-291">**Advisory**</span></span>

<span data-ttu-id="4a6aa-292">确保为"所有"或"所选 **"组启用了\*\*\*\*企业状态漫游**。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-292">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="4a6aa-293">有关详细信息，请参阅在 [Azure Active Directory 中启用企业状态漫游](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-293">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="4a6aa-294">许可证</span><span class="sxs-lookup"><span data-stu-id="4a6aa-294">Licenses</span></span>

<span data-ttu-id="4a6aa-295">使用 Microsoft 托管桌面需要大量许可证。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-295">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="4a6aa-296">**未准备就绪**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-296">**Not Ready**</span></span>

<span data-ttu-id="4a6aa-297">你没有使用 Microsoft 托管桌面所需的全部许可证。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-297">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="4a6aa-298">有关详细信息，请参阅[Microsoft 托管桌面技术和](../intro/technologies.md)[有关许可证的更多内容](prerequisites.md#more-about-licenses)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-298">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="4a6aa-299">安全帐户名称</span><span class="sxs-lookup"><span data-stu-id="4a6aa-299">Security account names</span></span>

<span data-ttu-id="4a6aa-300">某些安全帐户名称可能会与 Microsoft 托管桌面创建的帐户名冲突。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-300">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="4a6aa-301">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-301">**Not ready**</span></span>

<span data-ttu-id="4a6aa-302">你至少具有一个与 Microsoft 托管桌面创建的帐户名称相冲突的帐户名称。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-302">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="4a6aa-303">与 Microsoft 帐户代表合作，排除这些帐户名。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-303">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="4a6aa-304">安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="4a6aa-304">Security administrator roles</span></span>

<span data-ttu-id="4a6aa-305">具有特定安全角色的用户必须在 Microsoft Defender for Endpoint 中分配这些角色。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-305">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="4a6aa-306">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-306">**Advisory**</span></span>

<span data-ttu-id="4a6aa-307">如果你的用户已分配到 Azure AD 组织中任何这些角色，请确保他们在 Microsoft Defender for Endpoint 中也分配了这些角色。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-307">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="4a6aa-308">否则，具有这些角色的管理员将无法访问管理门户。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-308">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="4a6aa-309">安全操作员</span><span class="sxs-lookup"><span data-stu-id="4a6aa-309">Security Operator</span></span>
- <span data-ttu-id="4a6aa-310">全局读取者</span><span class="sxs-lookup"><span data-stu-id="4a6aa-310">Global Reader</span></span>

<span data-ttu-id="4a6aa-311">有关详细信息，请参阅为基于角色 [的访问控制创建和管理角色](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-311">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="4a6aa-312">安全默认值</span><span class="sxs-lookup"><span data-stu-id="4a6aa-312">Security default</span></span>

<span data-ttu-id="4a6aa-313">Azure Active Directory 中的安全默认值将阻止 Microsoft 托管桌面管理设备。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-313">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="4a6aa-314">**未就绪**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-314">**Not ready**</span></span>

<span data-ttu-id="4a6aa-315">你已打开安全默认值。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-315">You have Security defaults turned on.</span></span> <span data-ttu-id="4a6aa-316">关闭安全默认值并设置条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-316">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="4a6aa-317">有关详细信息，请参阅 [常见条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-317">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="4a6aa-318">自助服务密码重置</span><span class="sxs-lookup"><span data-stu-id="4a6aa-318">Self-service Password Reset</span></span>

<span data-ttu-id="4a6aa-319">SSPR (应) Microsoft 托管桌面用户（Microsoft 托管桌面服务帐户除外）启用 SSPR 密码重置功能。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-319">Self-service Password Reset (SSPR) should be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="4a6aa-320">有关详细信息，请参阅 [教程：允许用户使用 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)自助服务密码重置解锁其帐户或重置密码。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-320">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="4a6aa-321">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-321">**Advisory**</span></span>

<span data-ttu-id="4a6aa-322">确保"SSPR **选择** "设置包括 Microsoft 托管桌面设备，但不包括 Microsoft 托管桌面服务帐户。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-322">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="4a6aa-323">启用 SSPR 后，Microsoft 托管桌面服务帐户无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-323">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="4a6aa-324">标准用户角色</span><span class="sxs-lookup"><span data-stu-id="4a6aa-324">Standard user role</span></span>

<span data-ttu-id="4a6aa-325">除了分配了全局管理员和设备管理员的 Azure AD 角色的用户外，Microsoft 托管桌面用户将是没有本地管理员权限的标准用户。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-325">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="4a6aa-326">当所有其他用户启动其 Microsoft 托管桌面设备时，将为其分配标准用户角色。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-326">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="4a6aa-327">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-327">**Advisory**</span></span>

<span data-ttu-id="4a6aa-328">注册后，Microsoft 托管桌面用户不会拥有其 Microsoft 托管桌面设备的本地管理员权限。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-328">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="4a6aa-329">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="4a6aa-329">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="4a6aa-330">OneDrive</span><span class="sxs-lookup"><span data-stu-id="4a6aa-330">OneDrive</span></span>

<span data-ttu-id="4a6aa-331">" **仅在加入特定域** 的 PC 上允许同步"设置与 Microsoft 托管桌面冲突。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-331">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="4a6aa-332">可以在 OneDrive 管理中心访问 OneDrive [设置](https://admin.onedrive.com)。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-332">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="4a6aa-333">**公告**</span><span class="sxs-lookup"><span data-stu-id="4a6aa-333">**Advisory**</span></span>

<span data-ttu-id="4a6aa-334">仅在加入到特定域的 PC 上使用 **"仅允许同步"** 设置。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-334">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="4a6aa-335">此设置将不能用于 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-335">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="4a6aa-336">禁用此设置，并改为将 OneDrive 设置为使用条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-336">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="4a6aa-337">有关 [帮助，请参阅"规划条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 部署"。</span><span class="sxs-lookup"><span data-stu-id="4a6aa-337">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

