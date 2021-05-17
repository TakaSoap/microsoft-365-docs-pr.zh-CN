---
title: 安全电子邮件建议策略 - Microsoft 365策略|Microsoft Docs
description: 介绍针对有关如何应用电子邮件策略和配置的 Microsoft 建议的策略。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: c5f5837f4e4069a67bc080178fefd10bd2a08629
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599847"
---
# <a name="policy-recommendations-for-securing-email"></a><span data-ttu-id="2fee8-103">用于保护电子邮件的策略建议</span><span class="sxs-lookup"><span data-stu-id="2fee8-103">Policy recommendations for securing email</span></span>

<span data-ttu-id="2fee8-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="2fee8-104">**Applies to**</span></span>
- [<span data-ttu-id="2fee8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2fee8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2fee8-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="2fee8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="2fee8-107">本文介绍如何实施推荐的标识和设备访问策略，以保护支持新式身份验证和条件访问的组织电子邮件和电子邮件客户端。</span><span class="sxs-lookup"><span data-stu-id="2fee8-107">This article describes how to implement the recommended identity and device access policies to protect organizational email and email clients that support modern authentication and conditional access.</span></span> <span data-ttu-id="2fee8-108">本指南基于通用 [标识和设备](identity-access-policies.md) 访问策略，还包含一些其他建议。</span><span class="sxs-lookup"><span data-stu-id="2fee8-108">This guidance builds on the [Common identity and device access policies](identity-access-policies.md) and also includes a few additional recommendations.</span></span>

<span data-ttu-id="2fee8-109">这些建议基于三种不同的安全和保护层，可基于你的需求粒度应用：**基线**、敏感和 **高度管控**。 </span><span class="sxs-lookup"><span data-stu-id="2fee8-109">These recommendations are based on three different tiers of security and protection that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="2fee8-110">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="2fee8-110">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="2fee8-111">这些建议要求用户使用新式电子邮件客户端，包括Outlook适用于 iOS 和 Android 的客户端。</span><span class="sxs-lookup"><span data-stu-id="2fee8-111">These recommendations require your users to use modern email clients, including Outlook for iOS and Android on mobile devices.</span></span> <span data-ttu-id="2fee8-112">Outlook for iOS 和 Android 的移动设备支持 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2fee8-112">Outlook for iOS and Android provide support for the best features of Office 365.</span></span> <span data-ttu-id="2fee8-113">这些Outlook应用还构建了支持移动使用的管理功能，并与其他 Microsoft 云安全性功能协同工作。</span><span class="sxs-lookup"><span data-stu-id="2fee8-113">These mobile Outlook apps are also architected with security capabilities that support mobile use and work together with other Microsoft cloud security capabilities.</span></span> <span data-ttu-id="2fee8-114">有关详细信息，请参阅适用于[iOS Outlook Android 常见问题解答](/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)。</span><span class="sxs-lookup"><span data-stu-id="2fee8-114">For more information, see [Outlook for iOS and Android FAQ](/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).</span></span>

## <a name="update-common-policies-to-include-email"></a><span data-ttu-id="2fee8-115">更新常见策略以包括电子邮件</span><span class="sxs-lookup"><span data-stu-id="2fee8-115">Update common policies to include email</span></span>

<span data-ttu-id="2fee8-116">为了保护电子邮件，下图说明了从通用标识和设备访问策略更新的策略。</span><span class="sxs-lookup"><span data-stu-id="2fee8-116">To protect email, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="2fee8-117">[![用于保护对服务及其依赖Teams的访问的策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span><span class="sxs-lookup"><span data-stu-id="2fee8-117">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span></span>

<span data-ttu-id="2fee8-118">请注意添加用于阻止 ActiveSync Exchange Online的新策略。</span><span class="sxs-lookup"><span data-stu-id="2fee8-118">Note the addition of a new policy for Exchange Online to block ActiveSync clients.</span></span> <span data-ttu-id="2fee8-119">这将强制使用移动Outlook。</span><span class="sxs-lookup"><span data-stu-id="2fee8-119">This forces the use of Outlook mobile.</span></span>

<span data-ttu-id="2fee8-120">如果在设置Exchange Online策略Outlook策略作用域中包含了策略和策略，则只需创建新策略以阻止 ActiveSync 客户端。</span><span class="sxs-lookup"><span data-stu-id="2fee8-120">If you included Exchange Online and Outlook in the scope of the policies when you set them up, you only need to create the new policy to block ActiveSync clients.</span></span> <span data-ttu-id="2fee8-121">查看下表中列出的策略，并添加建议的策略，或确认已包含这些策略。</span><span class="sxs-lookup"><span data-stu-id="2fee8-121">Review the policies listed in the following table and either make the recommended additions, or confirm that these are already included.</span></span> <span data-ttu-id="2fee8-122">每个策略链接到常见标识和设备访问策略中的 [关联配置说明](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2fee8-122">Each policy links to the associated configuration instructions in [Common identity and device access policies](identity-access-policies.md).</span></span>

|<span data-ttu-id="2fee8-123">保护级别</span><span class="sxs-lookup"><span data-stu-id="2fee8-123">Protection level</span></span>|<span data-ttu-id="2fee8-124">策略</span><span class="sxs-lookup"><span data-stu-id="2fee8-124">Policies</span></span>|<span data-ttu-id="2fee8-125">详细信息</span><span class="sxs-lookup"><span data-stu-id="2fee8-125">More information</span></span>|
|---|---|---|
|<span data-ttu-id="2fee8-126">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="2fee8-126">**Baseline**</span></span>|[<span data-ttu-id="2fee8-127">当登录风险为中或高 *时需要* MFA</span><span class="sxs-lookup"><span data-stu-id="2fee8-127">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="2fee8-128">将Exchange Online包括在云应用的分配中</span><span class="sxs-lookup"><span data-stu-id="2fee8-128">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="2fee8-129">阻止不支持新式身份验证的客户端</span><span class="sxs-lookup"><span data-stu-id="2fee8-129">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="2fee8-130">将Exchange Online包括在云应用的分配中</span><span class="sxs-lookup"><span data-stu-id="2fee8-130">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="2fee8-131">应用 APP 数据保护策略</span><span class="sxs-lookup"><span data-stu-id="2fee8-131">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="2fee8-132">请确保Outlook包含在应用列表中。</span><span class="sxs-lookup"><span data-stu-id="2fee8-132">Be sure Outlook is included in the list of apps.</span></span> <span data-ttu-id="2fee8-133">请务必为 iOS、Android 和 (平台更新Windows) </span><span class="sxs-lookup"><span data-stu-id="2fee8-133">Be sure to update the policy for each platform (iOS, Android, Windows)</span></span>|
||[<span data-ttu-id="2fee8-134">需要批准的应用和应用保护</span><span class="sxs-lookup"><span data-stu-id="2fee8-134">Require approved apps and APP protection</span></span>](identity-access-policies.md#require-approved-apps-and-app-protection)|<span data-ttu-id="2fee8-135">将Exchange Online包括在云应用列表中</span><span class="sxs-lookup"><span data-stu-id="2fee8-135">Include Exchange Online in the list of cloud apps</span></span>|
||[<span data-ttu-id="2fee8-136">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="2fee8-136">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="2fee8-137">将Exchange Online包括在云应用列表中</span><span class="sxs-lookup"><span data-stu-id="2fee8-137">Include Exchange Online in list of cloud apps</span></span>|
||[<span data-ttu-id="2fee8-138">阻止 ActiveSync 客户端</span><span class="sxs-lookup"><span data-stu-id="2fee8-138">Block ActiveSync clients</span></span>](#block-activesync-clients)|<span data-ttu-id="2fee8-139">添加新策略</span><span class="sxs-lookup"><span data-stu-id="2fee8-139">Add this new policy</span></span>|
|<span data-ttu-id="2fee8-140">**敏感**</span><span class="sxs-lookup"><span data-stu-id="2fee8-140">**Sensitive**</span></span>|[<span data-ttu-id="2fee8-141">登录风险低、中或高 *时需要* MFA</span><span class="sxs-lookup"><span data-stu-id="2fee8-141">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="2fee8-142">将Exchange Online包括在云应用的分配中</span><span class="sxs-lookup"><span data-stu-id="2fee8-142">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="2fee8-143">要求兼容电脑 *和* 移动设备</span><span class="sxs-lookup"><span data-stu-id="2fee8-143">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="2fee8-144">将Exchange Online包括在云应用列表中</span><span class="sxs-lookup"><span data-stu-id="2fee8-144">Include Exchange Online in the list of cloud apps</span></span>|
|<span data-ttu-id="2fee8-145">**高度管控**</span><span class="sxs-lookup"><span data-stu-id="2fee8-145">**Highly regulated**</span></span>|[<span data-ttu-id="2fee8-146">*始终* 需要 MFA</span><span class="sxs-lookup"><span data-stu-id="2fee8-146">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="2fee8-147">将Exchange Online包括在云应用的分配中</span><span class="sxs-lookup"><span data-stu-id="2fee8-147">Include Exchange Online in the assignment of cloud apps</span></span>|
|

## <a name="block-activesync-clients"></a><span data-ttu-id="2fee8-148">阻止 ActiveSync 客户端</span><span class="sxs-lookup"><span data-stu-id="2fee8-148">Block ActiveSync clients</span></span>

<span data-ttu-id="2fee8-149">此策略阻止 ActiveSync 客户端绕过其他条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="2fee8-149">This policy prevents ActiveSync clients from bypassing other Conditional Access policies.</span></span> <span data-ttu-id="2fee8-150">策略配置仅适用于 ActiveSync 客户端。</span><span class="sxs-lookup"><span data-stu-id="2fee8-150">The policy configuration applies only to ActiveSync clients.</span></span> <span data-ttu-id="2fee8-151">通过选择 **["需要应用保护策略"，](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** 此策略将阻止 ActiveSync 客户端。</span><span class="sxs-lookup"><span data-stu-id="2fee8-151">By selecting **[Require app protection policy](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**, this policy blocks ActiveSync clients.</span></span> <span data-ttu-id="2fee8-152">有关创建此策略的详细信息，请参阅使用条件访问要求 [云应用访问的应用保护策略](/azure/active-directory/conditional-access/app-protection-based-conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="2fee8-152">Details on creating this policy can be found in [Require app protection policy for cloud app access with Conditional Access](/azure/active-directory/conditional-access/app-protection-based-conditional-access).</span></span>

- <span data-ttu-id="2fee8-153">按照方案[1：Office 365](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)应用需要具有应用保护策略的已批准应用（这将阻止利用基本身份验证的 Exchange ActiveSync 客户端连接到 Exchange Online）中的"步骤 2：使用 ActiveSync (EAS) 为 Exchange Online 配置 Azure AD 条件访问策略"。</span><span class="sxs-lookup"><span data-stu-id="2fee8-153">Follow "Step 2: Configure an Azure AD Conditional Access policy for Exchange Online with ActiveSync (EAS)" in [Scenario 1: Office 365 apps require approved apps with app protection policies](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.</span></span>

<span data-ttu-id="2fee8-154">您还可以使用身份验证策略禁用 [基本身份验证](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)，这将强制所有客户端访问请求使用新式验证。</span><span class="sxs-lookup"><span data-stu-id="2fee8-154">You can also use authentication policies to [disable Basic authentication](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), which forces all client access requests to use modern authentication.</span></span>

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a><span data-ttu-id="2fee8-155">限制对Exchange Online网页Outlook访问</span><span class="sxs-lookup"><span data-stu-id="2fee8-155">Limit access to Exchange Online from Outlook on the web</span></span>

<span data-ttu-id="2fee8-156">您可以限制用户从 web 上的Outlook下载附件的能力。</span><span class="sxs-lookup"><span data-stu-id="2fee8-156">You can restrict the ability for users to download attachments from Outlook on the web on umnanaged devices.</span></span> <span data-ttu-id="2fee8-157">这些设备上的用户可以使用 Office Online 查看和编辑这些文件，而无需泄露和存储设备上的文件。</span><span class="sxs-lookup"><span data-stu-id="2fee8-157">Users on these devices can view and edit these files using Office Online without leaking and storing the files on the device.</span></span> <span data-ttu-id="2fee8-158">还可以阻止用户在非托管设备上看到附件。</span><span class="sxs-lookup"><span data-stu-id="2fee8-158">You can also block users from seeing attachments on an unmanaged device.</span></span>

<span data-ttu-id="2fee8-159">步骤如下：</span><span class="sxs-lookup"><span data-stu-id="2fee8-159">Here are the steps:</span></span>

1. <span data-ttu-id="2fee8-160">[连接远程 PowerShell 会话Exchange Online远程 PowerShell 会话](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2fee8-160">[Connect to an Exchange Online Remote PowerShell session](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>
2. <span data-ttu-id="2fee8-161">如果还没有 OWA 邮箱策略，则使用 [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy) cmdlet 创建一个。</span><span class="sxs-lookup"><span data-stu-id="2fee8-161">If you don't already have an OWA mailbox policy, create one with the [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy) cmdlet.</span></span>
3. <span data-ttu-id="2fee8-162">如果要允许查看附件但不允许下载，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="2fee8-162">If you want to allow viewing of attachments but no downloading, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. <span data-ttu-id="2fee8-163">如果要阻止附件，请使用此命令：</span><span class="sxs-lookup"><span data-stu-id="2fee8-163">If you want to block attachments, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. <span data-ttu-id="2fee8-164">在 Azure 门户中，使用这些设置创建新的条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="2fee8-164">In the Azure portal, create a new Conditional Access policy with these settings:</span></span>

   <span data-ttu-id="2fee8-165">**工作分配** \>**用户和组**：选择要包括和排除的适当用户和组。</span><span class="sxs-lookup"><span data-stu-id="2fee8-165">**Assignments** \> **Users and groups**: Select appropriate users and groups to include and exclude.</span></span>

   <span data-ttu-id="2fee8-166">**工作分配** \>**云应用或操作** \>**云应用** \>**Include** \>**选择应用**：选择 **Office 365 Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="2fee8-166">**Assignments** \> **Cloud apps or actions** \> **Cloud apps** \> **Include** \> **Select apps**: Select **Office 365 Exchange Online**</span></span>

   <span data-ttu-id="2fee8-167">**访问控制** \>**会话**：**选择"使用应用强制的限制"**</span><span class="sxs-lookup"><span data-stu-id="2fee8-167">**Access controls** \> **Session**: Select **Use app enforced restrictions**</span></span>

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a><span data-ttu-id="2fee8-168">要求 iOS 和 Android 设备必须使用Outlook</span><span class="sxs-lookup"><span data-stu-id="2fee8-168">Require that iOS and Android devices must use Outlook</span></span>

<span data-ttu-id="2fee8-169">若要确保 iOS 和 Android 设备的用户只能使用 Outlook for iOS 和 Android 访问工作或学校内容，你需要一个面向这些潜在用户的条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="2fee8-169">To ensure that users of iOS and Android devices can only access work or school content using Outlook for iOS and Android, you need a Conditional Access policy that targets those potential users.</span></span>

<span data-ttu-id="2fee8-170">请参阅使用适用于 iOS 和 Android 的 Outlook 管理邮件[协作访问中配置此策略的步骤](/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="2fee8-170">See the steps to configure this policy in [Manage messaging collaboration access by using Outlook for iOS and Android](/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access).</span></span>

## <a name="set-up-message-encryption"></a><span data-ttu-id="2fee8-171">设置邮件加密</span><span class="sxs-lookup"><span data-stu-id="2fee8-171">Set up message encryption</span></span>

<span data-ttu-id="2fee8-172">借助 OME Office 365 邮件加密 (OME) 功能（利用 Azure 信息保护中的保护功能）你的组织可以轻松地与任何设备上的任何用户共享受保护的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2fee8-172">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device.</span></span> <span data-ttu-id="2fee8-173">用户可以与其他 Microsoft 365 组织以及使用 Outlook.com、Gmail 和其他电子邮件服务的非客户一起发送和接收受保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="2fee8-173">Users can send and receive protected messages with other Microsoft 365 organizations as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="2fee8-174">有关详细信息，请参阅设置[新的Office 365 邮件加密功能](../../compliance/set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="2fee8-174">For more information, see [Set up new Office 365 Message Encryption capabilities](../../compliance/set-up-new-message-encryption-capabilities.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2fee8-175">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2fee8-175">Next steps</span></span>

![步骤 4：云Microsoft 365策略](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="2fee8-177">为：配置条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="2fee8-177">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="2fee8-178">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2fee8-178">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="2fee8-179">SharePoint</span><span class="sxs-lookup"><span data-stu-id="2fee8-179">SharePoint</span></span>](sharepoint-file-access-policies.md)
