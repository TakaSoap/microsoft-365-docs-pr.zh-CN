---
title: 管理 Office 365 邮件加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 完成设置 Office 365 邮件加密（OME）后，了解如何通过多种方式自定义您的部署。
ms.openlocfilehash: 83fa620852ea9b2e0cd50d50b6715742658b7239
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815429"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="38239-103">管理 Office 365 邮件加密</span><span class="sxs-lookup"><span data-stu-id="38239-103">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="38239-104">完成设置 Office 365 邮件加密（OME）后，您可以通过多种方式自定义部署的配置。</span><span class="sxs-lookup"><span data-stu-id="38239-104">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="38239-105">例如，您可以配置是否启用一次性传递代码，在 Outlook 网页版中显示 "**加密**" 按钮，等等。</span><span class="sxs-lookup"><span data-stu-id="38239-105">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="38239-106">本文中的任务介绍了如何。</span><span class="sxs-lookup"><span data-stu-id="38239-106">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="38239-107">管理 Google、Yahoo 和 Microsoft 帐户收件人是否可以使用这些帐户登录 Office 365 邮件加密门户</span><span class="sxs-lookup"><span data-stu-id="38239-107">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="38239-108">当您设置新的 Office 365 邮件加密功能时，组织中的用户可以向组织外部的收件人发送邮件。</span><span class="sxs-lookup"><span data-stu-id="38239-108">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your organization.</span></span> <span data-ttu-id="38239-109">如果收件人使用的是 Google 帐户、Yahoo 帐户或 Microsoft 帐户等*社会 id* ，则收件人可以使用社会 id 登录到 OME 门户。</span><span class="sxs-lookup"><span data-stu-id="38239-109">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="38239-110">如果需要，您可以选择不允许收件人使用社交 Id 登录到 OME 门户。</span><span class="sxs-lookup"><span data-stu-id="38239-110">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="38239-111">管理收件人是否可以使用社交 Id 登录到 OME 门户</span><span class="sxs-lookup"><span data-stu-id="38239-111">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="38239-112">[使用远程 PowerShell 连接到 Exchange Online](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="38239-112">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="38239-113">使用 SocialIdSignIn 参数运行 Set-omeconfiguration cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="38239-113">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="38239-114">例如，若要禁用社会 Id，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="38239-114">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="38239-115">若要启用社交 Id，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="38239-115">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="38239-116">管理 Office 365 邮件加密门户的一次性传递代码的使用</span><span class="sxs-lookup"><span data-stu-id="38239-116">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="38239-117">如果由 OME 加密的邮件的收件人不使用 Outlook，而不管收件人使用的帐户如何，收件人都会收到一个限制的 web 查看链接，让他们能够阅读邮件。</span><span class="sxs-lookup"><span data-stu-id="38239-117">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="38239-118">该链接包括一次性的 pass 代码。</span><span class="sxs-lookup"><span data-stu-id="38239-118">This link includes a one-time pass code.</span></span> <span data-ttu-id="38239-119">作为管理员，你可以决定收件人是否可以使用一次性传递代码登录到 OME 门户。</span><span class="sxs-lookup"><span data-stu-id="38239-119">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="38239-120">管理 OME 是否生成一次性传递代码</span><span class="sxs-lookup"><span data-stu-id="38239-120">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="38239-121">使用组织中具有全局管理员权限的工作或学校帐户，并启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="38239-121">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="38239-122">有关说明，请参阅[连接 PowerShell Exchange Online](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="38239-122">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="38239-123">使用 OTPEnabled 参数运行 Set-omeconfiguration cmdlet：</span><span class="sxs-lookup"><span data-stu-id="38239-123">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="38239-124">例如，若要禁用一次性传递代码，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="38239-124">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="38239-125">若要启用一次性传递代码，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="38239-125">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="38239-126">管理 web 上的 Outlook 中的 "加密" 按钮的显示</span><span class="sxs-lookup"><span data-stu-id="38239-126">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="38239-127">作为管理员，您可以管理是否将此按钮显示给最终用户。</span><span class="sxs-lookup"><span data-stu-id="38239-127">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="38239-128">管理 "加密" 按钮是否出现在 web 上的 Outlook 中</span><span class="sxs-lookup"><span data-stu-id="38239-128">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="38239-129">使用组织中具有全局管理员权限的工作或学校帐户，并启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="38239-129">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="38239-130">有关说明，请参阅[连接 PowerShell Exchange Online](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="38239-130">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="38239-131">运行带-SimplifiedClientAccessEnabled 参数的 Get-irmconfiguration cmdlet：</span><span class="sxs-lookup"><span data-stu-id="38239-131">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="38239-132">例如，要禁用 "**加密**" 按钮，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="38239-132">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="38239-133">启用 "**加密**" 按钮：</span><span class="sxs-lookup"><span data-stu-id="38239-133">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="38239-134">为 iOS 邮件应用程序用户启用电子邮件的服务端解密</span><span class="sxs-lookup"><span data-stu-id="38239-134">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="38239-135">IOS 邮件应用程序无法解密受 Office 365 邮件加密保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="38239-135">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="38239-136">作为 Microsoft 365 管理员，您可以对传递到 iOS 邮件应用程序的邮件应用服务端解密。</span><span class="sxs-lookup"><span data-stu-id="38239-136">As a Microsoft 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="38239-137">当您选择使用服务端解密时，该服务会将邮件的解密副本发送到 iOS 设备。</span><span class="sxs-lookup"><span data-stu-id="38239-137">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="38239-138">客户端设备存储邮件的解密副本。</span><span class="sxs-lookup"><span data-stu-id="38239-138">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="38239-139">即使 iOS 邮件应用程序不会对用户应用客户端使用权限，该邮件也会保留有关使用权限的信息。</span><span class="sxs-lookup"><span data-stu-id="38239-139">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="38239-140">用户可以复制或打印邮件，即使他们最初未具有这样做的权限也是如此。</span><span class="sxs-lookup"><span data-stu-id="38239-140">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="38239-141">但是，如果用户尝试完成需要 Microsoft 365 邮件服务器的操作（如转发邮件），则如果用户最初没有使用此功能，则服务器将不允许该操作。</span><span class="sxs-lookup"><span data-stu-id="38239-141">However, if the user attempts to complete an action that requires the Microsoft 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="38239-142">但是，最终用户可以通过从 iOS 邮件应用程序中的不同帐户转发邮件来解决 "不转发" 使用限制。</span><span class="sxs-lookup"><span data-stu-id="38239-142">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="38239-143">无论您是否设置了邮件的服务端解密，在 iOS 邮件应用中无法查看加密的附件和受权限保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="38239-143">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="38239-144">如果选择不允许向 iOS 邮件应用程序用户发送解密邮件，则用户会收到一条消息，指出他们没有查看邮件的权限。</span><span class="sxs-lookup"><span data-stu-id="38239-144">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="38239-145">默认情况下，不会启用电子邮件的服务端解密。</span><span class="sxs-lookup"><span data-stu-id="38239-145">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="38239-146">有关详细信息以及客户端体验的视图，请参阅[在 iPhone 或 iPad 上查看加密的邮件](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)。</span><span class="sxs-lookup"><span data-stu-id="38239-146">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="38239-147">管理 iOS 邮件应用程序用户是否可以查看受 Office 365 邮件加密保护的邮件</span><span class="sxs-lookup"><span data-stu-id="38239-147">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="38239-148">使用组织中具有全局管理员权限的工作或学校帐户，并启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="38239-148">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="38239-149">有关说明，请参阅[连接 PowerShell Exchange Online](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="38239-149">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="38239-150">使用 AllowRMSSupportForUnenlightenedApps 参数运行 ActiveSyncOrganizations cmdlet：</span><span class="sxs-lookup"><span data-stu-id="38239-150">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="38239-151">例如，配置服务以在将邮件发送到 unenlightened 应用程序（如 iOS 邮件应用程序）之前对这些邮件进行解密：</span><span class="sxs-lookup"><span data-stu-id="38239-151">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="38239-152">或者，将该服务配置为不将解密的邮件发送到 unenlightened 应用程序：</span><span class="sxs-lookup"><span data-stu-id="38239-152">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="38239-153">单个邮箱策略（OWA/ActiveSync）替代这些设置（即，如果在各自的 OWA 邮箱策略或 ActiveSync 邮箱策略中将 IRMEnabled 设置为 False），则不会应用这些配置。</span><span class="sxs-lookup"><span data-stu-id="38239-153">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="38239-154">启用 web 浏览器邮件客户端的电子邮件附件的服务端解密</span><span class="sxs-lookup"><span data-stu-id="38239-154">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="38239-155">通常情况下，当您使用 Office 365 邮件加密时，附件会自动加密。</span><span class="sxs-lookup"><span data-stu-id="38239-155">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="38239-156">作为管理员，您可以对用户从 web 浏览器下载的电子邮件附件应用服务端解密。</span><span class="sxs-lookup"><span data-stu-id="38239-156">As an administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="38239-157">当您使用服务端解密时，服务会将文件的解密副本发送到设备。</span><span class="sxs-lookup"><span data-stu-id="38239-157">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="38239-158">邮件仍加密。</span><span class="sxs-lookup"><span data-stu-id="38239-158">The message is still encrypted.</span></span> <span data-ttu-id="38239-159">即使浏览器不会对用户应用客户端使用权限，电子邮件附件也会保留有关使用权限的信息。</span><span class="sxs-lookup"><span data-stu-id="38239-159">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="38239-160">用户可以复制或打印电子邮件附件，即使他们最初未提供这样做的权限。</span><span class="sxs-lookup"><span data-stu-id="38239-160">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="38239-161">但是，如果用户尝试完成需要 Microsoft 365 邮件服务器的操作（如转发附件），则如果用户最初未使用此功能，则服务器将不允许该操作。</span><span class="sxs-lookup"><span data-stu-id="38239-161">However, if the user tries to complete an action that requires the Microsoft 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="38239-162">无论您是否设置了附件的服务端解密，用户都无法在 iOS 邮件应用中查看加密和受权限保护的邮件的任何附件。</span><span class="sxs-lookup"><span data-stu-id="38239-162">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="38239-163">如果选择不允许解密的电子邮件附件（默认情况下），用户将收到一条消息，指出他们没有查看附件的权限。</span><span class="sxs-lookup"><span data-stu-id="38239-163">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="38239-164">有关 Microsoft 365 如何使用仅加密选项为电子邮件和电子邮件附件实现加密的详细信息，请参阅[用于电子邮件的仅加密选项。](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="38239-164">For more information about how Microsoft 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="38239-165">管理在从 web 浏览器下载时是否解密电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="38239-165">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="38239-166">使用组织中具有全局管理员权限的工作或学校帐户，并启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="38239-166">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="38239-167">有关说明，请参阅[连接 PowerShell Exchange Online](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="38239-167">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="38239-168">使用 DecryptAttachmentForEncryptOnly 参数运行 Get-irmconfiguration cmdlet：</span><span class="sxs-lookup"><span data-stu-id="38239-168">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentForEncryptOnly parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   <span data-ttu-id="38239-169">例如，将服务配置为在用户从 web 浏览器下载电子邮件附件时对其进行解密：</span><span class="sxs-lookup"><span data-stu-id="38239-169">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   <span data-ttu-id="38239-170">将服务配置为在下载时保留加密的电子邮件附件：</span><span class="sxs-lookup"><span data-stu-id="38239-170">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a><span data-ttu-id="38239-171">确保所有外部收件人使用 OME 门户阅读加密邮件</span><span class="sxs-lookup"><span data-stu-id="38239-171">Ensure all external recipients use the OME Portal to read encrypted mail</span></span>

<span data-ttu-id="38239-172">您可以使用自定义品牌打造模板来强制收件人接收到一个包装邮件，以使收件人能够在 OME 门户中阅读加密电子邮件，而不是使用 Outlook 或 web 上的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="38239-172">You can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="38239-173">如果您使用希望更好地控制收件人如何使用其接收的邮件，则可能需要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="38239-173">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="38239-174">例如，如果外部收件人在 web 门户中查看电子邮件，您可以为电子邮件设置到期日期，并且可以撤销电子邮件。</span><span class="sxs-lookup"><span data-stu-id="38239-174">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="38239-175">仅在 OME 门户中支持这些功能。</span><span class="sxs-lookup"><span data-stu-id="38239-175">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="38239-176">创建邮件流规则时，可以使用 "加密" 选项和 "不转发" 选项。</span><span class="sxs-lookup"><span data-stu-id="38239-176">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a><span data-ttu-id="38239-177">使用自定义模板强制所有外部收件人使用 OME 门户和加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="38239-177">Use a custom template to force all external recipients to use the OME Portal and for encrypted email</span></span>

1. <span data-ttu-id="38239-178">使用组织中具有全局管理员权限的工作或学校帐户，并启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="38239-178">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="38239-179">有关说明，请参阅[连接 PowerShell Exchange Online](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="38239-179">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="38239-180">运行 New-transportrule cmdlet：</span><span class="sxs-lookup"><span data-stu-id="38239-180">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="38239-181">其中：</span><span class="sxs-lookup"><span data-stu-id="38239-181">where:</span></span>

   - <span data-ttu-id="38239-182">`mail flow rule name`是要用于新邮件流规则的名称。</span><span class="sxs-lookup"><span data-stu-id="38239-182">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="38239-183">`option name`可以是 `Encrypt` 或 `Do Not Forward` 。</span><span class="sxs-lookup"><span data-stu-id="38239-183">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="38239-184">`template name`是您赋予自定义品牌打造模板的名称，例如 `OME Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="38239-184">`template name` is the name you gave the custom branding template, for example `OME Configuration`.</span></span>

   <span data-ttu-id="38239-185">若要使用 "OME 配置" 模板对所有外部电子邮件进行加密，并应用 "仅加密" 选项，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="38239-185">To encrypt all external email with the "OME Configuration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   <span data-ttu-id="38239-186">若要使用 "OME Configuration" 模板对所有外部电子邮件进行加密并应用 "不转发" 选项，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="38239-186">To encrypt all external email with the "OME Configuration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="38239-187">自定义电子邮件和 OME 门户的外观</span><span class="sxs-lookup"><span data-stu-id="38239-187">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="38239-188">有关如何为组织自定义 OME 的详细信息，请参阅[将组织的品牌添加到加密邮件](add-your-organization-brand-to-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="38239-188">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="38239-189">禁用 OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="38239-189">Disable the new capabilities for OME</span></span>

<span data-ttu-id="38239-190">我们希望它不会到达它，但如果需要，禁用 OME 的新功能非常简单。</span><span class="sxs-lookup"><span data-stu-id="38239-190">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="38239-191">首先，您需要删除您创建的任何使用新 OME 功能的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="38239-191">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="38239-192">有关删除邮件流规则的信息，请参阅[管理邮件流规则](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="38239-192">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="38239-193">然后，在 Exchange Online PowerShell 中完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="38239-193">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="38239-194">禁用 OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="38239-194">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="38239-195">使用组织中具有全局管理员权限的工作或学校帐户，启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="38239-195">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="38239-196">有关说明，请参阅[连接 PowerShell Exchange Online](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="38239-196">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="38239-197">如果您在 web 上的 Outlook 中启用了 "**加密**" 按钮，请通过运行 get-irmconfiguration Cmdlet 和 SimplifiedClientAccessEnabled 参数来禁用它。</span><span class="sxs-lookup"><span data-stu-id="38239-197">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="38239-198">否则，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="38239-198">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="38239-199">通过运行 Get-irmconfiguration cmdlet 并将 AzureRMSLicensingEnabled 参数设置为 false 来禁用 OME 的新功能：</span><span class="sxs-lookup"><span data-stu-id="38239-199">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
