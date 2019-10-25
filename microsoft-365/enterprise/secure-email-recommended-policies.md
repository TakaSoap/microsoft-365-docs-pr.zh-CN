---
title: 保护电子邮件的推荐策略 - Microsoft 365 企业版 | Microsoft Docs
description: 介绍针对有关如何应用电子邮件策略和配置的 Microsoft 建议的策略。
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 101ebbe46b9f49a1a450c4cb22b5d5f67ce1b322
ms.sourcegitcommit: bd487d36b04b8f8caf10900e8c5237f9ccf9e072
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "37654021"
---
# <a name="policy-recommendations-for-securing-email"></a><span data-ttu-id="e0874-103">用于保护电子邮件的策略建议</span><span class="sxs-lookup"><span data-stu-id="e0874-103">Policy recommendations for securing email</span></span>

<span data-ttu-id="e0874-104">本文介绍如何实现建议的标识和设备访问策略，以保护支持新式身份验证和条件访问的组织电子邮件和电子邮件客户端。</span><span class="sxs-lookup"><span data-stu-id="e0874-104">This article describes how to implement the recommended identity and device access policies to protect organizational email and email clients that support modern authentication and conditional access.</span></span> <span data-ttu-id="e0874-105">本指南建立在[通用标识和设备访问策略](identity-access-policies.md)之上，还包括一些其他建议。</span><span class="sxs-lookup"><span data-stu-id="e0874-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md) and also includes a few additional recommendations.</span></span>

<span data-ttu-id="e0874-106">这些建议基于三种不同的安全性和保护层，可根据您需求的粒度进行应用：**比较基准**、**敏感**和**高度管控**。</span><span class="sxs-lookup"><span data-stu-id="e0874-106">These recommendations are based on three different tiers of security and protection that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="e0874-107">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="e0874-107">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="e0874-108">这些建议要求用户使用新式电子邮件客户端，包括移动设备上的 Outlook for iOS 和 Outlook for Android。</span><span class="sxs-lookup"><span data-stu-id="e0874-108">These recommendations require your users to use modern email clients, including Outlook for iOS and Android on mobile devices.</span></span> <span data-ttu-id="e0874-109">适用于 iOS 和 Android 的 Outlook 提供了对 Office 365 最佳功能的支持。</span><span class="sxs-lookup"><span data-stu-id="e0874-109">Outlook for iOS and Android provide support for the best features of Office 365.</span></span> <span data-ttu-id="e0874-110">这些移动 Outlook 应用程序还使用支持移动使用的安全功能以及与其他 Microsoft 云安全功能配合使用的安全功能。</span><span class="sxs-lookup"><span data-stu-id="e0874-110">These mobile Outlook apps are also architected with security capabilities that support mobile use and work together with other Microsoft cloud security capabilities.</span></span> <span data-ttu-id="e0874-111">有关详细信息，请参阅[Outlook For iOS 和 ANDROID FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)。</span><span class="sxs-lookup"><span data-stu-id="e0874-111">For more information, see [Outlook for iOS and Android FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).</span></span>

## <a name="updating-common-policies-to-include-email"></a><span data-ttu-id="e0874-112">更新常见策略以包含电子邮件</span><span class="sxs-lookup"><span data-stu-id="e0874-112">Updating common policies to include email</span></span>

<span data-ttu-id="e0874-113">下图说明了常见标识和设备访问策略，并指明了需要更新哪些策略来保护电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e0874-113">The following diagram illustrates the common identity and device access policies and indicates which policies need to be updated to protect email.</span></span> <span data-ttu-id="e0874-114">请注意，添加了 Exchange Online 的新规则以阻止 ActiveSync 客户端。</span><span class="sxs-lookup"><span data-stu-id="e0874-114">Note the addition of a new rule for Exchange Online to block ActiveSync clients.</span></span> <span data-ttu-id="e0874-115">这将强制使用 Outlook mobile。</span><span class="sxs-lookup"><span data-stu-id="e0874-115">This forces the use of Outlook mobile.</span></span>

![保护电子邮件的策略更新摘要](../images/identity-access-ruleset-mail.png)

<span data-ttu-id="e0874-117">如果在设置 Exchange Online 和 Outlook 时将其包含在策略范围中，则只需创建新策略来阻止 ActiveSync 客户端。</span><span class="sxs-lookup"><span data-stu-id="e0874-117">If you included Exchange Online and Outlook in the scope of the policies when you set them up, you only need to create the new policy to block ActiveSync clients.</span></span> <span data-ttu-id="e0874-118">查看下表中列出的策略，并执行建议的添加项，或者确认是否已包含这些策略。</span><span class="sxs-lookup"><span data-stu-id="e0874-118">Review the policies listed in the following table and either make the recommended additions, or confirm that these are already included.</span></span> <span data-ttu-id="e0874-119">每个规则都链接到[通用标识和设备访问策略](identity-access-policies.md)文章中相关的配置说明。</span><span class="sxs-lookup"><span data-stu-id="e0874-119">Each rule links to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="e0874-120">保护级别</span><span class="sxs-lookup"><span data-stu-id="e0874-120">Protection level</span></span>|<span data-ttu-id="e0874-121">策略</span><span class="sxs-lookup"><span data-stu-id="e0874-121">Policies</span></span>|<span data-ttu-id="e0874-122">更多信息</span><span class="sxs-lookup"><span data-stu-id="e0874-122">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="e0874-123">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="e0874-123">**Baseline**</span></span>|[<span data-ttu-id="e0874-124">当登录风险为 "*中*" 或 "*高*" 时，需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="e0874-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="e0874-125">在云应用的分配中包括 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e0874-125">Include Exchange Online in the assignment of cloud apps</span></span>|
|        |[<span data-ttu-id="e0874-126">阻止不支持新式身份验证的客户端</span><span class="sxs-lookup"><span data-stu-id="e0874-126">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="e0874-127">在云应用的分配中包括 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e0874-127">Include Exchange Online in the assignment of cloud apps</span></span>|
|        |[<span data-ttu-id="e0874-128">定义应用保护策略</span><span class="sxs-lookup"><span data-stu-id="e0874-128">Define app protection policies</span></span>](identity-access-policies.md#high-risk-users-must-change-password)|<span data-ttu-id="e0874-129">确保 Outlook 包含在应用程序列表中。</span><span class="sxs-lookup"><span data-stu-id="e0874-129">Be sure Outlook is included in the list of apps.</span></span> <span data-ttu-id="e0874-130">确保为每个平台（iOS、Android、Windows）更新策略</span><span class="sxs-lookup"><span data-stu-id="e0874-130">Be sure to update the policy for each platform (iOS, Android, Windows)</span></span>|
|        |[<span data-ttu-id="e0874-131">需要批准的应用程序</span><span class="sxs-lookup"><span data-stu-id="e0874-131">Require approved apps</span></span>](identity-access-policies.md#require-approved-apps)|<span data-ttu-id="e0874-132">在云应用列表中包括 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e0874-132">Include Exchange Online in the list of cloud apps</span></span>|
|        |[<span data-ttu-id="e0874-133">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="e0874-133">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="e0874-134">在云应用列表中加入 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e0874-134">Include Exchange Online in list of cloud apps</span></span>|
|        |[<span data-ttu-id="e0874-135">阻止 ActiveSync 客户端</span><span class="sxs-lookup"><span data-stu-id="e0874-135">Block ActiveSync clients</span></span>](#block-activesync-clients)|<span data-ttu-id="e0874-136">添加此新策略</span><span class="sxs-lookup"><span data-stu-id="e0874-136">Add this new policy</span></span>| 
|<span data-ttu-id="e0874-137">**敏感**</span><span class="sxs-lookup"><span data-stu-id="e0874-137">**Sensitive**</span></span>|[<span data-ttu-id="e0874-138">当登录风险为*低*、*中*或*高*时，需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="e0874-138">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| <span data-ttu-id="e0874-139">在云应用的分配中包括 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e0874-139">Include Exchange Online in the assignment of cloud apps</span></span>|
|         |[<span data-ttu-id="e0874-140">需要符合要求*的 pc 和*移动设备</span><span class="sxs-lookup"><span data-stu-id="e0874-140">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="e0874-141">在云应用列表中包括 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e0874-141">Include Exchange Online in the list of cloud apps</span></span>|
|<span data-ttu-id="e0874-142">**高度管控**</span><span class="sxs-lookup"><span data-stu-id="e0874-142">**Highly regulated**</span></span>|[<span data-ttu-id="e0874-143">*始终*要求进行 MFA</span><span class="sxs-lookup"><span data-stu-id="e0874-143">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="e0874-144">在云应用的分配中包括 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e0874-144">Include Exchange Online in the assignment of cloud apps</span></span>|

## <a name="block-activesync-clients"></a><span data-ttu-id="e0874-145">阻止 ActiveSync 客户端</span><span class="sxs-lookup"><span data-stu-id="e0874-145">Block ActiveSync clients</span></span>

<span data-ttu-id="e0874-146">此策略将阻止 ActiveSync 客户端绕过其他条件访问规则。</span><span class="sxs-lookup"><span data-stu-id="e0874-146">This policy prevents ActiveSync clients from bypassing other conditional access rules.</span></span> <span data-ttu-id="e0874-147">规则配置仅适用于 ActiveSync 客户端。</span><span class="sxs-lookup"><span data-stu-id="e0874-147">The rule configuration applies only to ActiveSync clients.</span></span> <span data-ttu-id="e0874-148">通过选择 "**需要批准的客户端应用程序**"，此策略将阻止 ActiveSync 客户端。</span><span class="sxs-lookup"><span data-stu-id="e0874-148">By selecting **Require approved client app**, this policy blocks ActiveSync clients.</span></span> <span data-ttu-id="e0874-149">配置此策略：</span><span class="sxs-lookup"><span data-stu-id="e0874-149">To configure this policy:</span></span>

1. <span data-ttu-id="e0874-150">转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="e0874-150">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="e0874-151">成功登录后，您将看到 "Azure 仪表板"。</span><span class="sxs-lookup"><span data-stu-id="e0874-151">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="e0874-152">从左侧菜单中选择“Azure Active Directory”。</span><span class="sxs-lookup"><span data-stu-id="e0874-152">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="e0874-153">在“安全”部分之下，选择“条件访问”。</span><span class="sxs-lookup"><span data-stu-id="e0874-153">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="e0874-154">选择“新策略”。</span><span class="sxs-lookup"><span data-stu-id="e0874-154">Choose **New policy**.</span></span>

5. <span data-ttu-id="e0874-155">输入策略名称，然后选择要应用策略的“用户和组”。</span><span class="sxs-lookup"><span data-stu-id="e0874-155">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="e0874-156">选择“云应用”。</span><span class="sxs-lookup"><span data-stu-id="e0874-156">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="e0874-157">选择 "**选择应用程序**"，选择 " **Office 365 Exchange Online**"。</span><span class="sxs-lookup"><span data-stu-id="e0874-157">Choose **Select apps**, select **Office 365 Exchange Online**.</span></span> <span data-ttu-id="e0874-158">选择 "**选择**并**完成**"。</span><span class="sxs-lookup"><span data-stu-id="e0874-158">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="e0874-159">选择 "**条件**"，然后选择 "**客户端应用**"。</span><span class="sxs-lookup"><span data-stu-id="e0874-159">Choose **Conditions**, and then choose **Client apps**.</span></span>

9. <span data-ttu-id="e0874-160">对于 "**配置**"，选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="e0874-160">For **Configure**, select **Yes**.</span></span> <span data-ttu-id="e0874-161">仅检查以下内容：**移动应用和桌面客户端**和**Exchange ActiveSync 客户端**。</span><span class="sxs-lookup"><span data-stu-id="e0874-161">Check only the following: **Mobile apps and desktop clients** and **Exchange ActiveSync clients**.</span></span> <span data-ttu-id="e0874-162">选择" **完成**"。</span><span class="sxs-lookup"><span data-stu-id="e0874-162">Choose **Done**.</span></span>

10. <span data-ttu-id="e0874-163">从“访问控制”部分选择“授予”。</span><span class="sxs-lookup"><span data-stu-id="e0874-163">Choose **Grant** from the **Access controls** section.</span></span>

11. <span data-ttu-id="e0874-164">选择 "**授予访问权限**"，选择 "**需要批准的客户端应用**"。</span><span class="sxs-lookup"><span data-stu-id="e0874-164">Choose **Grant access**, select **Require approved client app**.</span></span>  <span data-ttu-id="e0874-165">对于多个控件，选择 "**需要选定的控件**"，然后选择 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="e0874-165">For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span>

12. <span data-ttu-id="e0874-166">选择“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="e0874-166">Choose **Create**.</span></span>

## <a name="setup-office-365-message-encryption"></a><span data-ttu-id="e0874-167">设置 Office 365 邮件加密</span><span class="sxs-lookup"><span data-stu-id="e0874-167">Setup Office 365 message encryption</span></span>

<span data-ttu-id="e0874-168">使用新的 Office 365 邮件加密（OME）功能（它利用 Azure 信息保护中的保护功能），您的组织可以轻松地与任何设备上的任何人共享受保护的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e0874-168">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device.</span></span> <span data-ttu-id="e0874-169">用户可以使用 Outlook.com、Gmail 和其他电子邮件服务，通过其他 Office 365 组织以及非 Office 365 客户发送和接收受保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="e0874-169">Users can send and receive protected messages with other Office 365 organizations as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="e0874-170">有关详细信息，请参阅[设置新的 Office 365 邮件加密功能](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e)。</span><span class="sxs-lookup"><span data-stu-id="e0874-170">For more information, see [Set up new Office 365 Message Encryption capabilities](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e0874-171">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e0874-171">Next steps</span></span>

[<span data-ttu-id="e0874-172">了解用于保护 SharePoint 网站和文件的策略建议</span><span class="sxs-lookup"><span data-stu-id="e0874-172">Learn about policy recommendations for securing SharePoint Sites and files</span></span>](sharepoint-file-access-policies.md)
