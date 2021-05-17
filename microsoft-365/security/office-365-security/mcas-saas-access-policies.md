---
title: SaaS Microsoft Cloud App Security的建议策略 - Microsoft 365 企业版 |Microsoft Docs
description: 介绍用于与 Microsoft Cloud App Security 集成的建议策略。
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: Admin
ms.author: bcarter
ms.date: 03/22/2021
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 414d6ae0586078551c737e45763ea665d5eec4e6
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939550"
---
# <a name="recommended-microsoft-cloud-app-security-policies-for-saas-apps"></a><span data-ttu-id="1b509-103">SaaS Microsoft Cloud App Security的建议策略</span><span class="sxs-lookup"><span data-stu-id="1b509-103">Recommended Microsoft Cloud App Security policies for SaaS apps</span></span>
<span data-ttu-id="1b509-104">Microsoft Cloud App Security基于 Azure AD 条件访问策略构建，支持使用 SaaS 应用实时监视和控制粒度操作，例如阻止下载、上传、复制和粘贴以及打印。</span><span class="sxs-lookup"><span data-stu-id="1b509-104">Microsoft Cloud App Security builds on Azure AD conditional access policies to enable real-time monitoring and control of granular actions with SaaS apps, such as blocking downloads, uploads, copy and paste, and printing.</span></span> <span data-ttu-id="1b509-105">此功能为具有固有风险的会话添加安全性，例如，当非托管设备或来宾用户访问公司资源时。</span><span class="sxs-lookup"><span data-stu-id="1b509-105">This feature adds security to sessions that carry inherent risk, such as when corporate resources are accessed from unmanaged devices or by guest users.</span></span>

<span data-ttu-id="1b509-106">Microsoft Cloud App Security与 Microsoft 信息保护本地集成，提供实时内容检查，以根据敏感信息类型和敏感度标签查找敏感数据，并采取适当的措施。</span><span class="sxs-lookup"><span data-stu-id="1b509-106">Microsoft Cloud App Security also integrates natively with Microsoft Information Protection, providing real-time content inspection to find sensitive data based on sensitive information types and sensitivity labels and to take appropriate action.</span></span>

<span data-ttu-id="1b509-107">本指南包括针对以下方案的建议：</span><span class="sxs-lookup"><span data-stu-id="1b509-107">This guidance includes recommendations for these scenarios:</span></span>

- <span data-ttu-id="1b509-108">将 SaaS 应用引入 IT 管理</span><span class="sxs-lookup"><span data-stu-id="1b509-108">Bring SaaS apps into IT management</span></span>
- <span data-ttu-id="1b509-109">优化对特定 SaaS 应用的保护</span><span class="sxs-lookup"><span data-stu-id="1b509-109">Tune protection for specific SaaS apps</span></span>
- <span data-ttu-id="1b509-110">配置 DLP (数据丢失) 以帮助遵守数据保护法规</span><span class="sxs-lookup"><span data-stu-id="1b509-110">Configure data loss prevention (DLP) to help comply with data protection regulations</span></span>

## <a name="bring-saas-apps-into-it-management"></a><span data-ttu-id="1b509-111">将 SaaS 应用引入 IT 管理</span><span class="sxs-lookup"><span data-stu-id="1b509-111">Bring SaaS apps into IT management</span></span>

<span data-ttu-id="1b509-112">使用 Microsoft Cloud App Security管理 SaaS 应用的第一步是发现它们，然后将其添加到 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="1b509-112">The first step in using Microsoft Cloud App Security to manage SaaS apps is to discover these and then add them to your Azure AD tenant.</span></span> <span data-ttu-id="1b509-113">如果需要发现帮助，请参阅 [发现和管理网络中 SaaS 应用](/cloud-app-security/tutorial-shadow-it)。</span><span class="sxs-lookup"><span data-stu-id="1b509-113">If you need help with discovery, see [Discover and manage SaaS apps in your network](/cloud-app-security/tutorial-shadow-it).</span></span> <span data-ttu-id="1b509-114">发现应用后， [将其添加到 Azure AD 租户](/azure/active-directory/manage-apps/add-application-portal)。</span><span class="sxs-lookup"><span data-stu-id="1b509-114">After you've discovered apps, [add these to your Azure AD tenant](/azure/active-directory/manage-apps/add-application-portal).</span></span>

<span data-ttu-id="1b509-115">可以通过执行以下操作开始管理这些操作：</span><span class="sxs-lookup"><span data-stu-id="1b509-115">You can begin to manage these by doing the following:</span></span>

1. <span data-ttu-id="1b509-116">首先，在 Azure AD 中，创建新的条件访问策略，并配置为"使用条件访问应用控制"。</span><span class="sxs-lookup"><span data-stu-id="1b509-116">First, in Azure AD, create a new conditional access policy and configure it to "Use Conditional Access App Control."</span></span> <span data-ttu-id="1b509-117">这会将请求重定向到云应用安全。</span><span class="sxs-lookup"><span data-stu-id="1b509-117">This redirects the request to Cloud App Security.</span></span> <span data-ttu-id="1b509-118">你可以创建一个策略，并添加所有 SaaS 应用到此策略。</span><span class="sxs-lookup"><span data-stu-id="1b509-118">You can create one policy and add all SaaS apps to this policy.</span></span>
1. <span data-ttu-id="1b509-119">接下来，在云应用安全，创建会话策略。</span><span class="sxs-lookup"><span data-stu-id="1b509-119">Next, in Cloud App Security, create session policies.</span></span> <span data-ttu-id="1b509-120">为要应用的每个控件创建一个策略。</span><span class="sxs-lookup"><span data-stu-id="1b509-120">Create one policy for each control you want to apply.</span></span>

<span data-ttu-id="1b509-121">对 SaaS 应用的权限通常基于对应用的访问权限的业务需求。</span><span class="sxs-lookup"><span data-stu-id="1b509-121">Permissions to SaaS apps are typically based on business need for access to the app.</span></span> <span data-ttu-id="1b509-122">这些权限可以是高度动态的。</span><span class="sxs-lookup"><span data-stu-id="1b509-122">These permissions can be highly dynamic.</span></span> <span data-ttu-id="1b509-123">使用云应用安全策略可确保保护应用数据，无论用户被分配到与基线、敏感或高度管控保护相关联的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="1b509-123">Using Cloud App Security policies ensures protection to app data, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span>

<span data-ttu-id="1b509-124">为了跨 SaaS 应用集合保护数据，下图说明了必要的 Azure AD 条件访问策略，以及可在 云应用安全 创建的建议策略。</span><span class="sxs-lookup"><span data-stu-id="1b509-124">To protect data across your collection of SaaS apps, the following diagram illustrates the necessary Azure AD conditional access policy plus suggested policies you can create in Cloud App Security.</span></span> <span data-ttu-id="1b509-125">此示例中，在 云应用安全 创建的策略将应用于你正在管理的所有 SaaS 应用。</span><span class="sxs-lookup"><span data-stu-id="1b509-125">In this example, the policies created in Cloud App Security apply to all SaaS apps you are managing.</span></span> <span data-ttu-id="1b509-126">这些控件旨在根据设备是否受管理以及已应用于文件的敏感度标签来应用适当的控件。</span><span class="sxs-lookup"><span data-stu-id="1b509-126">These are designed to apply appropriate controls based on whether devices are managed as well as sensitivity labels that are already applied to files.</span></span>

![用于管理 SaaS 应用中云应用安全](../../media/microsoft-365-policies-configurations/mcas-manage-saas-apps-2.png)

<span data-ttu-id="1b509-128">下表列出了必须在 Azure AD 中创建的新条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="1b509-128">The following table lists the new conditional access policy you must create in Azure AD.</span></span>

|<span data-ttu-id="1b509-129">保护级别</span><span class="sxs-lookup"><span data-stu-id="1b509-129">Protection level</span></span>|<span data-ttu-id="1b509-130">策略</span><span class="sxs-lookup"><span data-stu-id="1b509-130">Policy</span></span>|<span data-ttu-id="1b509-131">详细信息</span><span class="sxs-lookup"><span data-stu-id="1b509-131">More information</span></span>|
|---|---|---|
|<span data-ttu-id="1b509-132">所有保护级别</span><span class="sxs-lookup"><span data-stu-id="1b509-132">All protection levels</span></span>|[<span data-ttu-id="1b509-133">在应用程序中使用条件访问云应用安全</span><span class="sxs-lookup"><span data-stu-id="1b509-133">Use Conditional Access App Control in Cloud App Security</span></span>](/cloud-app-security/proxy-deployment-aad#configure-integration-with-azure-ad)|<span data-ttu-id="1b509-134">这将配置你的 IdP (Azure AD) 以使用 云应用安全。</span><span class="sxs-lookup"><span data-stu-id="1b509-134">This configures your IdP (Azure AD) to work with Cloud App Security.</span></span>|
||||

<span data-ttu-id="1b509-135">下表列出了上面说明的示例策略，你可以创建这些策略来保护所有 SaaS 应用。</span><span class="sxs-lookup"><span data-stu-id="1b509-135">This next table lists the example policies illustrated above that you can create to protect all SaaS apps.</span></span> <span data-ttu-id="1b509-136">请务必评估自己的业务、安全性和合规性目标，然后创建为环境提供最合适的保护的策略。</span><span class="sxs-lookup"><span data-stu-id="1b509-136">Be sure to evaluate your own business, security, and compliance objectives and then create policies that provide the most appropriate protection for your environment.</span></span>

|<span data-ttu-id="1b509-137">保护级别</span><span class="sxs-lookup"><span data-stu-id="1b509-137">Protection level</span></span>|<span data-ttu-id="1b509-138">策略</span><span class="sxs-lookup"><span data-stu-id="1b509-138">Policy</span></span>|
|---|---|
|<span data-ttu-id="1b509-139">基线</span><span class="sxs-lookup"><span data-stu-id="1b509-139">Baseline</span></span>|<span data-ttu-id="1b509-140">监视来自非托管设备的流量</span><span class="sxs-lookup"><span data-stu-id="1b509-140">Monitor traffic from unmanaged devices</span></span> <p> <span data-ttu-id="1b509-141">向从非托管设备下载文件添加保护</span><span class="sxs-lookup"><span data-stu-id="1b509-141">Add protection to file downloads from unmanaged devices</span></span>|
|<span data-ttu-id="1b509-142">敏感</span><span class="sxs-lookup"><span data-stu-id="1b509-142">Sensitive</span></span>|<span data-ttu-id="1b509-143">阻止从非托管设备下载标记为敏感或分类的文件 (这将仅提供浏览器) </span><span class="sxs-lookup"><span data-stu-id="1b509-143">Block download of files labeled with sensitive or classified from unmanaged devices (this provides browser only access)</span></span>|
|<span data-ttu-id="1b509-144">高度管控</span><span class="sxs-lookup"><span data-stu-id="1b509-144">Highly regulated</span></span>|<span data-ttu-id="1b509-145">阻止从所有设备下载标记为已分类 (这将提供浏览器仅) </span><span class="sxs-lookup"><span data-stu-id="1b509-145">Block download of files labeled with classified from all devices (this provides browser only access)</span></span>|
|||

<span data-ttu-id="1b509-146">有关设置条件访问应用控件的端到端说明，请参阅为特色应用部署条件 [访问应用控制](/cloud-app-security/proxy-deployment-aad)。</span><span class="sxs-lookup"><span data-stu-id="1b509-146">For end-to-end instructions for setting up Conditional Access App Control, see [Deploy Conditional Access App Control for featured apps](/cloud-app-security/proxy-deployment-aad).</span></span> <span data-ttu-id="1b509-147">本文将引导你完成在 Azure AD 中创建必要的条件访问策略和测试 SaaS 应用的过程。</span><span class="sxs-lookup"><span data-stu-id="1b509-147">This article walks you through the process of creating the necessary conditional access policy in Azure AD and testing your SaaS apps.</span></span>

<span data-ttu-id="1b509-148">有关详细信息，请参阅使用条件[访问应用Microsoft Cloud App Security保护应用](/cloud-app-security/proxy-intro-aad)。</span><span class="sxs-lookup"><span data-stu-id="1b509-148">For more information, see [Protect apps with Microsoft Cloud App Security Conditional Access App Control](/cloud-app-security/proxy-intro-aad).</span></span>

## <a name="tune-protection-for-specific-saas-apps"></a><span data-ttu-id="1b509-149">优化对特定 SaaS 应用的保护</span><span class="sxs-lookup"><span data-stu-id="1b509-149">Tune protection for specific SaaS apps</span></span>

<span data-ttu-id="1b509-150">你可能想要将其他监视和控件应用到环境中的特定 SaaS 应用。</span><span class="sxs-lookup"><span data-stu-id="1b509-150">You might want to apply additional monitoring and controls to specific SaaS apps in your environment.</span></span> <span data-ttu-id="1b509-151">云应用安全可完成此操作。</span><span class="sxs-lookup"><span data-stu-id="1b509-151">Cloud App Security allows you to accomplish this.</span></span> <span data-ttu-id="1b509-152">例如，如果你的环境中大量使用 Box 等应用，则应用其他控件是有意义的。</span><span class="sxs-lookup"><span data-stu-id="1b509-152">For example, if an app like Box is used heavily in your environment, it makes sense to apply additional controls.</span></span> <span data-ttu-id="1b509-153">或者，如果你的法律或财务部门将特定 SaaS 应用用于敏感业务数据，你可以针对这些应用提供额外保护。</span><span class="sxs-lookup"><span data-stu-id="1b509-153">Or, if your legal or finance department is using a specific SaaS app for sensitive business data, you can target extra protection to these apps.</span></span>

<span data-ttu-id="1b509-154">例如，可以使用以下类型的内置异常检测策略模板保护 Box 环境：</span><span class="sxs-lookup"><span data-stu-id="1b509-154">For example, you can protect your Box environment with these types of built-in anomaly detection policy templates:</span></span>

- <span data-ttu-id="1b509-155">来自匿名 IP 地址的活动</span><span class="sxs-lookup"><span data-stu-id="1b509-155">Activity from anonymous IP addresses</span></span>
- <span data-ttu-id="1b509-156">来自不常见国家/地区的活动</span><span class="sxs-lookup"><span data-stu-id="1b509-156">Activity from infrequent country</span></span>
- <span data-ttu-id="1b509-157">来自可疑 IP 地址的活动</span><span class="sxs-lookup"><span data-stu-id="1b509-157">Activity from suspicious IP addresses</span></span>
- <span data-ttu-id="1b509-158">不可能旅行</span><span class="sxs-lookup"><span data-stu-id="1b509-158">Impossible travel</span></span>
- <span data-ttu-id="1b509-159">终止用户用户执行的活动 (AAD 作为 IdP) </span><span class="sxs-lookup"><span data-stu-id="1b509-159">Activity performed by terminated user (requires AAD as IdP)</span></span>
- <span data-ttu-id="1b509-160">恶意软件检测</span><span class="sxs-lookup"><span data-stu-id="1b509-160">Malware detection</span></span>
- <span data-ttu-id="1b509-161">多个失败登录尝试</span><span class="sxs-lookup"><span data-stu-id="1b509-161">Multiple failed login attempts</span></span>
- <span data-ttu-id="1b509-162">勒索软件活动</span><span class="sxs-lookup"><span data-stu-id="1b509-162">Ransomware activity</span></span>
- <span data-ttu-id="1b509-163">Risky Oauth App</span><span class="sxs-lookup"><span data-stu-id="1b509-163">Risky Oauth App</span></span>
- <span data-ttu-id="1b509-164">异常的文件共享活动</span><span class="sxs-lookup"><span data-stu-id="1b509-164">Unusual file share activity</span></span>

<span data-ttu-id="1b509-165">这些就是示例。</span><span class="sxs-lookup"><span data-stu-id="1b509-165">These are examples.</span></span> <span data-ttu-id="1b509-166">定期添加其他策略模板。</span><span class="sxs-lookup"><span data-stu-id="1b509-166">Additional policy templates are added on a regular basis.</span></span> <span data-ttu-id="1b509-167">有关如何将其他保护应用于特定应用的示例，请参阅 [保护已连接的应用](/cloud-app-security/protect-connected-apps)。</span><span class="sxs-lookup"><span data-stu-id="1b509-167">For examples of how to apply additional protection to specific apps, see [Protecting connected apps](/cloud-app-security/protect-connected-apps).</span></span>

<span data-ttu-id="1b509-168">[如何云应用安全](/cloud-app-security/protect-box)Box 环境的保护演示了可帮助你在 Box 和其他应用（包含敏感数据）中保护业务数据的控件类型。</span><span class="sxs-lookup"><span data-stu-id="1b509-168">[How Cloud App Security helps protect your Box environment](/cloud-app-security/protect-box) demonstrates the types of controls that can help you protect your business data in Box and other apps with sensitive data.</span></span>

## <a name="configure-data-loss-prevention-dlp-to-help-comply-with-data-protection-regulations"></a><span data-ttu-id="1b509-169">配置 DLP (数据丢失) 以帮助遵守数据保护法规</span><span class="sxs-lookup"><span data-stu-id="1b509-169">Configure data loss prevention (DLP) to help comply with data protection regulations</span></span>

<span data-ttu-id="1b509-170">云应用安全配置合规性法规保护的有用工具。</span><span class="sxs-lookup"><span data-stu-id="1b509-170">Cloud App Security can be a valuable tool for configuring protection for compliance regulations.</span></span> <span data-ttu-id="1b509-171">在这种情况下，您可以创建特定策略来查找法规适用的特定数据，并配置每个策略以采取适当措施。</span><span class="sxs-lookup"><span data-stu-id="1b509-171">In this case, you create specific policies to look for specific data that a regulation applies to and configure each policy to take appropriate action.</span></span>

<span data-ttu-id="1b509-172">下图和表提供了一些策略示例，可配置这些策略以帮助遵守 GDPR 一般 (条例) 。</span><span class="sxs-lookup"><span data-stu-id="1b509-172">The following illustration and table provide several examples of policies that can be configured to help comply with  the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="1b509-173">在这些示例中，策略查找特定数据。</span><span class="sxs-lookup"><span data-stu-id="1b509-173">In these examples, policies look for specific data.</span></span> <span data-ttu-id="1b509-174">根据数据的敏感度，每个策略都配置为采取相应的操作。</span><span class="sxs-lookup"><span data-stu-id="1b509-174">Based on the sensitivity of the data, each policy is configured to take appropriate action.</span></span>

![数据丢失云应用安全策略示例](../../media/microsoft-365-policies-configurations/mcas-dlp.png)

|<span data-ttu-id="1b509-176">保护级别</span><span class="sxs-lookup"><span data-stu-id="1b509-176">Protection level</span></span>|<span data-ttu-id="1b509-177">示例策略</span><span class="sxs-lookup"><span data-stu-id="1b509-177">Example policies</span></span>|
|---|---|
|<span data-ttu-id="1b509-178">基线</span><span class="sxs-lookup"><span data-stu-id="1b509-178">Baseline</span></span>|<span data-ttu-id="1b509-179">当包含此敏感信息类型的文件 ("信用卡号"时) 组织外部共享时发出警报</span><span class="sxs-lookup"><span data-stu-id="1b509-179">Alert when files containing this sensitive information type ("Credit Card Number") are shared outside the organization</span></span> <p> <span data-ttu-id="1b509-180">>阻止将包含此敏感信息类型的文件 ("信用卡号") 到非托管设备</span><span class="sxs-lookup"><span data-stu-id="1b509-180">>Block downloads of files containing this sensitive information type ("Credit card number") to unmanaged devices</span></span>|
|<span data-ttu-id="1b509-181">敏感</span><span class="sxs-lookup"><span data-stu-id="1b509-181">Sensitive</span></span>|<span data-ttu-id="1b509-182">保护包含此敏感信息类型的文件下载 ("信用卡号") 托管设备</span><span class="sxs-lookup"><span data-stu-id="1b509-182">Protect downloads of files containing this sensitive information type ("Credit card number") to managed devices</span></span> <p> <span data-ttu-id="1b509-183">阻止下载包含此敏感信息类型的文件 ("信用卡号") 非托管设备</span><span class="sxs-lookup"><span data-stu-id="1b509-183">Block downloads of files containing this sensitive information type ("Credit card number") to unmanaged devices</span></span> <p> <span data-ttu-id="1b509-184">当包含这些标签的文件上载到 OneDrive for Business 或 Box (客户数据、人力资源：工资数据、人力资源、员工数据) </span><span class="sxs-lookup"><span data-stu-id="1b509-184">Alert when a file with on of these labels is uploaded to OneDrive for Business or Box (Customer data, Human Resources: Salary Data,Human Resources, Employee data)</span></span>|
|<span data-ttu-id="1b509-185">高度管控</span><span class="sxs-lookup"><span data-stu-id="1b509-185">Highly regulated</span></span>|<span data-ttu-id="1b509-186">当具有此标签的文件 ("高度分类") 下载到托管设备时发出警报</span><span class="sxs-lookup"><span data-stu-id="1b509-186">Alert when files with this label ("Highly classified") are downloaded to managed devices</span></span> <p> <span data-ttu-id="1b509-187">阻止下载具有此标签的文件 ("高度分类") 非托管设备</span><span class="sxs-lookup"><span data-stu-id="1b509-187">Block downloads of files with this label ("Highly classified") to unmanaged devices</span></span>|
|||

## <a name="next-steps"></a><span data-ttu-id="1b509-188">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1b509-188">Next steps</span></span>

<span data-ttu-id="1b509-189">有关使用应用程序云应用安全，请参阅Microsoft Cloud App Security[文档](//cloud-app-security/)。</span><span class="sxs-lookup"><span data-stu-id="1b509-189">For more information about using Cloud App Security, see [Microsoft Cloud App Security documentation](//cloud-app-security/).</span></span>
