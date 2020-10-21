---
title: 安全电子邮件推荐策略-适用于企业的 Microsoft 365 |Microsoft 文档
description: 介绍针对有关如何应用电子邮件策略和配置的 Microsoft 建议的策略。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
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
ms.openlocfilehash: c8a1609bed124789229c6ae6d1f80b7d9c70bb66
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646807"
---
# <a name="policy-recommendations-for-securing-email"></a><span data-ttu-id="87b4b-103">用于保护电子邮件的策略建议</span><span class="sxs-lookup"><span data-stu-id="87b4b-103">Policy recommendations for securing email</span></span>

<span data-ttu-id="87b4b-104">本文介绍如何实现建议的标识和设备访问策略，以保护支持新式身份验证和条件访问的组织电子邮件和电子邮件客户端。</span><span class="sxs-lookup"><span data-stu-id="87b4b-104">This article describes how to implement the recommended identity and device access policies to protect organizational email and email clients that support modern authentication and conditional access.</span></span> <span data-ttu-id="87b4b-105">本指南建立在 [通用标识和设备访问策略](identity-access-policies.md) 之上，还包括一些其他建议。</span><span class="sxs-lookup"><span data-stu-id="87b4b-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md) and also includes a few additional recommendations.</span></span>

<span data-ttu-id="87b4b-106">这些建议基于三种不同的安全性和保护层，可根据您需求的粒度进行应用： **比较基准**、 **敏感**和 **高度管控**。</span><span class="sxs-lookup"><span data-stu-id="87b4b-106">These recommendations are based on three different tiers of security and protection that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="87b4b-107">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="87b4b-107">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="87b4b-108">这些建议要求用户使用新式电子邮件客户端，包括移动设备上的 Outlook for iOS 和 Outlook for Android。</span><span class="sxs-lookup"><span data-stu-id="87b4b-108">These recommendations require your users to use modern email clients, including Outlook for iOS and Android on mobile devices.</span></span> <span data-ttu-id="87b4b-109">适用于 iOS 和 Android 的 Outlook 提供了对 Office 365 最佳功能的支持。</span><span class="sxs-lookup"><span data-stu-id="87b4b-109">Outlook for iOS and Android provide support for the best features of Office 365.</span></span> <span data-ttu-id="87b4b-110">这些移动 Outlook 应用程序还使用支持移动使用的安全功能以及与其他 Microsoft 云安全功能配合使用的安全功能。</span><span class="sxs-lookup"><span data-stu-id="87b4b-110">These mobile Outlook apps are also architected with security capabilities that support mobile use and work together with other Microsoft cloud security capabilities.</span></span> <span data-ttu-id="87b4b-111">有关详细信息，请参阅 [Outlook For iOS 和 ANDROID FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)。</span><span class="sxs-lookup"><span data-stu-id="87b4b-111">For more information, see [Outlook for iOS and Android FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).</span></span>

## <a name="update-common-policies-to-include-email"></a><span data-ttu-id="87b4b-112">更新常见策略以包含电子邮件</span><span class="sxs-lookup"><span data-stu-id="87b4b-112">Update common policies to include email</span></span>

<span data-ttu-id="87b4b-113">为了保护电子邮件，下图说明了要从通用标识和设备访问策略中更新的策略。</span><span class="sxs-lookup"><span data-stu-id="87b4b-113">To protect email, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="87b4b-114">[![用于保护对团队及其依赖服务的访问权限的策略更新的摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span><span class="sxs-lookup"><span data-stu-id="87b4b-114">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span></span>

[<span data-ttu-id="87b4b-115">查看此图像的更大版本</span><span class="sxs-lookup"><span data-stu-id="87b4b-115">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

<span data-ttu-id="87b4b-116">请注意，为 Exchange Online 添加新策略以阻止 ActiveSync 客户端。</span><span class="sxs-lookup"><span data-stu-id="87b4b-116">Note the addition of a new policy for Exchange Online to block ActiveSync clients.</span></span> <span data-ttu-id="87b4b-117">这将强制使用 Outlook mobile。</span><span class="sxs-lookup"><span data-stu-id="87b4b-117">This forces the use of Outlook mobile.</span></span>

<span data-ttu-id="87b4b-118">如果在设置 Exchange Online 和 Outlook 时将其包含在策略范围中，则只需创建新策略来阻止 ActiveSync 客户端。</span><span class="sxs-lookup"><span data-stu-id="87b4b-118">If you included Exchange Online and Outlook in the scope of the policies when you set them up, you only need to create the new policy to block ActiveSync clients.</span></span> <span data-ttu-id="87b4b-119">查看下表中列出的策略，并执行建议的添加项，或者确认是否已包含这些策略。</span><span class="sxs-lookup"><span data-stu-id="87b4b-119">Review the policies listed in the following table and either make the recommended additions, or confirm that these are already included.</span></span> <span data-ttu-id="87b4b-120">每个策略链接到 [常见标识和设备访问策略](identity-access-policies.md)中的关联配置说明。</span><span class="sxs-lookup"><span data-stu-id="87b4b-120">Each policy links to the associated configuration instructions in [Common identity and device access policies](identity-access-policies.md).</span></span>

|<span data-ttu-id="87b4b-121">保护级别</span><span class="sxs-lookup"><span data-stu-id="87b4b-121">Protection level</span></span>|<span data-ttu-id="87b4b-122">策略</span><span class="sxs-lookup"><span data-stu-id="87b4b-122">Policies</span></span>|<span data-ttu-id="87b4b-123">更多信息</span><span class="sxs-lookup"><span data-stu-id="87b4b-123">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="87b4b-124">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="87b4b-124">**Baseline**</span></span>|[<span data-ttu-id="87b4b-125">当登录风险为 "*中*" 或 "*高*" 时，需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="87b4b-125">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="87b4b-126">在云应用的分配中包括 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="87b4b-126">Include Exchange Online in the assignment of cloud apps</span></span>|
|        |[<span data-ttu-id="87b4b-127">阻止不支持新式身份验证的客户端</span><span class="sxs-lookup"><span data-stu-id="87b4b-127">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="87b4b-128">在云应用的分配中包括 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="87b4b-128">Include Exchange Online in the assignment of cloud apps</span></span>|
|        |[<span data-ttu-id="87b4b-129">应用应用数据保护策略</span><span class="sxs-lookup"><span data-stu-id="87b4b-129">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="87b4b-130">确保 Outlook 包含在应用程序列表中。</span><span class="sxs-lookup"><span data-stu-id="87b4b-130">Be sure Outlook is included in the list of apps.</span></span> <span data-ttu-id="87b4b-131">请务必为每个平台 (iOS、Android、Windows) 更新策略</span><span class="sxs-lookup"><span data-stu-id="87b4b-131">Be sure to update the policy for each platform (iOS, Android, Windows)</span></span>|
|        |[<span data-ttu-id="87b4b-132">需要经批准的应用和应用保护</span><span class="sxs-lookup"><span data-stu-id="87b4b-132">Require approved apps and APP protection</span></span>](identity-access-policies.md#require-approved-apps-and-app-protection)|<span data-ttu-id="87b4b-133">在云应用列表中包括 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="87b4b-133">Include Exchange Online in the list of cloud apps</span></span>|
|        |[<span data-ttu-id="87b4b-134">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="87b4b-134">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="87b4b-135">在云应用列表中加入 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="87b4b-135">Include Exchange Online in list of cloud apps</span></span>|
|        |[<span data-ttu-id="87b4b-136">阻止 ActiveSync 客户端</span><span class="sxs-lookup"><span data-stu-id="87b4b-136">Block ActiveSync clients</span></span>](#block-activesync-clients)|<span data-ttu-id="87b4b-137">添加此新策略</span><span class="sxs-lookup"><span data-stu-id="87b4b-137">Add this new policy</span></span>| 
|<span data-ttu-id="87b4b-138">**敏感**</span><span class="sxs-lookup"><span data-stu-id="87b4b-138">**Sensitive**</span></span>|[<span data-ttu-id="87b4b-139">当登录风险为*低*、*中*或*高*时，需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="87b4b-139">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| <span data-ttu-id="87b4b-140">在云应用的分配中包括 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="87b4b-140">Include Exchange Online in the assignment of cloud apps</span></span>|
|         |[<span data-ttu-id="87b4b-141">需要符合要求 *的 pc 和* 移动设备</span><span class="sxs-lookup"><span data-stu-id="87b4b-141">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="87b4b-142">在云应用列表中包括 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="87b4b-142">Include Exchange Online in the list of cloud apps</span></span>|
|<span data-ttu-id="87b4b-143">**高度管控**</span><span class="sxs-lookup"><span data-stu-id="87b4b-143">**Highly regulated**</span></span>|[<span data-ttu-id="87b4b-144">*始终* 要求进行 MFA</span><span class="sxs-lookup"><span data-stu-id="87b4b-144">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="87b4b-145">在云应用的分配中包括 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="87b4b-145">Include Exchange Online in the assignment of cloud apps</span></span>|

## <a name="block-activesync-clients"></a><span data-ttu-id="87b4b-146">阻止 ActiveSync 客户端</span><span class="sxs-lookup"><span data-stu-id="87b4b-146">Block ActiveSync clients</span></span>

<span data-ttu-id="87b4b-147">此策略将阻止 ActiveSync 客户端绕过其他条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="87b4b-147">This policy prevents ActiveSync clients from bypassing other Conditional Access policies.</span></span> <span data-ttu-id="87b4b-148">策略配置仅适用于 ActiveSync 客户端。</span><span class="sxs-lookup"><span data-stu-id="87b4b-148">The policy configuration applies only to ActiveSync clients.</span></span> <span data-ttu-id="87b4b-149">通过选择 " **[需要应用保护策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**"，此策略将阻止 ActiveSync 客户端。</span><span class="sxs-lookup"><span data-stu-id="87b4b-149">By selecting **[Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**, this policy blocks ActiveSync clients.</span></span> <span data-ttu-id="87b4b-150">有关创建此策略的详细信息，请参阅 [需要使用条件访问的云应用访问的应用保护策略](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="87b4b-150">Details on creating this policy can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).</span></span>

- <span data-ttu-id="87b4b-151">按照 "第2步：为 Exchange Online 配置 Azure AD 条件访问策略" 中的 "应用 ActiveSync (EAS) " 中的 [方案1： Office 365 应用程序需要批准的应用程序使用应用保护策略](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)，这会阻止 Exchange ActiveSync 客户端利用基本身份验证连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="87b4b-151">Follow "Step 2: Configure an Azure AD Conditional Access policy for Exchange Online with ActiveSync (EAS)" in [Scenario 1: Office 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.</span></span>

<span data-ttu-id="87b4b-152">您还可以使用身份验证策略 [禁用基本身份验证](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)，这将强制所有客户端访问请求使用新式验证。</span><span class="sxs-lookup"><span data-stu-id="87b4b-152">You can also use authentication policies to [disable Basic authentication](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), which forces all client access requests to use modern authentication.</span></span>

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a><span data-ttu-id="87b4b-153">限制从 web 上的 Outlook 访问 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="87b4b-153">Limit access to Exchange Online from Outlook on the web</span></span>

<span data-ttu-id="87b4b-154">您可以限制用户在 umnanaged 设备上的 Outlook 网页版上下载附件的功能。</span><span class="sxs-lookup"><span data-stu-id="87b4b-154">You can restrict the ability for users to download attachments from Outlook on the web on umnanaged devices.</span></span> <span data-ttu-id="87b4b-155">这些设备上的用户可以使用 Office Online 查看和编辑这些文件，而无需将文件泄露和存储在设备上。</span><span class="sxs-lookup"><span data-stu-id="87b4b-155">Users on these devices can view and edit these files using Office Online without leaking and storing the files on the device.</span></span> <span data-ttu-id="87b4b-156">您还可以阻止用户查看非托管设备上的附件。</span><span class="sxs-lookup"><span data-stu-id="87b4b-156">You can also block users from seeing attachments on an unmanaged device.</span></span>

<span data-ttu-id="87b4b-157">步骤如下：</span><span class="sxs-lookup"><span data-stu-id="87b4b-157">Here are the steps:</span></span>

1. <span data-ttu-id="87b4b-158">[连接到 Exchange Online 远程 PowerShell 会话](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="87b4b-158">[Connect to an Exchange Online Remote PowerShell session](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>
2. <span data-ttu-id="87b4b-159">如果尚不具有 OWA 邮箱策略，请使用 [set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) cmdlet 创建一个。</span><span class="sxs-lookup"><span data-stu-id="87b4b-159">If you don't already have an OWA mailbox policy, create one with the [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) cmdlet.</span></span>
3. <span data-ttu-id="87b4b-160">如果要允许查看附件但不下载，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="87b4b-160">If you want to allow viewing of attachments but no downloading, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. <span data-ttu-id="87b4b-161">如果要阻止附件，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="87b4b-161">If you want to block attachments, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

4. <span data-ttu-id="87b4b-162">在 Azure 门户中，使用以下设置创建新的条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="87b4b-162">In the Azure portal, create a new Conditional Access policy with these settings:</span></span>

   <span data-ttu-id="87b4b-163">**> 用户和组的工作分配**：选择合适的用户和组以包含和排除。</span><span class="sxs-lookup"><span data-stu-id="87b4b-163">**Assignments > Users and groups**: Select appropriate users and groups to include and exclude.</span></span>

   <span data-ttu-id="87b4b-164">**> 云应用或操作 > 云应用的工作分配 > 包括 > 选择应用程序**：选择 **Office 365 Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="87b4b-164">**Assignments > Cloud apps or actions > Cloud apps > Include > Select apps**: Select **Office 365 Exchange Online**</span></span>

   <span data-ttu-id="87b4b-165">**访问控制 > 会话**：选择 "**使用应用强制限制**"</span><span class="sxs-lookup"><span data-stu-id="87b4b-165">**Access controls > Session**: Select **Use app enforced restrictions**</span></span>

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a><span data-ttu-id="87b4b-166">要求 iOS 和 Android 设备必须使用 Outlook</span><span class="sxs-lookup"><span data-stu-id="87b4b-166">Require that iOS and Android devices must use Outlook</span></span>

<span data-ttu-id="87b4b-167">若要确保 iOS 和 Android 设备的用户只能使用 Outlook for iOS 和 Outlook for Android 来访问工作或学校内容，您需要针对这些潜在用户的条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="87b4b-167">To ensure that users of iOS and Android devices can only access work or school content using Outlook for iOS and Android, you need a Conditional Access policy that targets those potential users.</span></span>

<span data-ttu-id="87b4b-168">请参阅 [使用 Outlook For iOS 和 Outlook For Android 管理邮件协作访问]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)中的配置此策略的步骤。</span><span class="sxs-lookup"><span data-stu-id="87b4b-168">See the steps to configure this policy in [Manage messaging collaboration access by using Outlook for iOS and Android]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access).</span></span>


## <a name="set-up-message-encryption"></a><span data-ttu-id="87b4b-169">设置邮件加密</span><span class="sxs-lookup"><span data-stu-id="87b4b-169">Set up message encryption</span></span>

<span data-ttu-id="87b4b-170">使用新的 Office 365 邮件加密 (OME) 功能，利用 Azure 信息保护中的保护功能，您的组织可以轻松地与任何设备上的任何人共享受保护的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="87b4b-170">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device.</span></span> <span data-ttu-id="87b4b-171">用户可以使用 Outlook.com、Gmail 和其他电子邮件服务发送和接收与其他 Microsoft 365 组织以及非客户的受保护邮件。</span><span class="sxs-lookup"><span data-stu-id="87b4b-171">Users can send and receive protected messages with other Microsoft 365 organizations as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="87b4b-172">有关详细信息，请参阅 [设置新的 Office 365 邮件加密功能](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="87b4b-172">For more information, see [Set up new Office 365 Message Encryption capabilities](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="87b4b-173">后续步骤</span><span class="sxs-lookup"><span data-stu-id="87b4b-173">Next steps</span></span>

![步骤4： Microsoft 365 云应用的策略](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="87b4b-175">为以下项配置条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="87b4b-175">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="87b4b-176">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="87b4b-176">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="87b4b-177">SharePoint</span><span class="sxs-lookup"><span data-stu-id="87b4b-177">SharePoint</span></span>](sharepoint-file-access-policies.md)
