---
title: Office 365 邮件加密的旧信息
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 05/22/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解如何为组织将旧文件转换为 Office 365 (OME) OME 加密。
ms.openlocfilehash: 23f287fd01949d710c5cc5c65f0c36c6055d3a57
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688429"
---
# <a name="legacy-information-for-office-365-message-encryption"></a><span data-ttu-id="b1c1c-103">Office 365 邮件加密的旧信息</span><span class="sxs-lookup"><span data-stu-id="b1c1c-103">Legacy information for Office 365 Message Encryption</span></span>

<span data-ttu-id="b1c1c-104">如果尚未将组织移动到新的 OME 功能，但已部署 OME，则本文中的信息适用于您的组织。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-104">If you haven't yet moved your organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization.</span></span> <span data-ttu-id="b1c1c-105">Microsoft 建议在组织合理时制定移动到新 OME 功能的计划。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-105">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="b1c1c-106">有关说明，请参阅设置基于 Azure 信息保护构建的新 [Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-106">For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="b1c1c-107">若要详细了解新功能首先如何工作，请参阅 [Office 365 邮件加密](ome.md)。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-107">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span> <span data-ttu-id="b1c1c-108">本文的其余部分将介绍 OME 在发布新 OME 功能之前的行为。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-108">The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>
  
<span data-ttu-id="b1c1c-109">借助 Office 365 邮件加密，组织可以在组织内外人员之间发送和接收加密的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-109">With Office 365 Message Encryption, your organization can send and receive encrypted email messages between people inside and outside your organization.</span></span> <span data-ttu-id="b1c1c-110">Office 365 邮件加密适用于 Outlook.com、Yahoo、Gmail 和其他电子邮件服务。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-110">Office 365 Message Encryption works with Outlook.com, Yahoo, Gmail, and other email services.</span></span> <span data-ttu-id="b1c1c-111">电子邮件加密有助于确保只有预期收件人才能查看邮件内容。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-111">Email message encryption helps ensure that only intended recipients can view message content.</span></span>
  
<span data-ttu-id="b1c1c-112">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="b1c1c-112">Here are some examples:</span></span>
  
- <span data-ttu-id="b1c1c-113">银行员工将信用卡对帐单发送给客户</span><span class="sxs-lookup"><span data-stu-id="b1c1c-113">A bank employee sends credit card statements to customers</span></span>

- <span data-ttu-id="b1c1c-114">保险公司代表为客户提供策略详细信息</span><span class="sxs-lookup"><span data-stu-id="b1c1c-114">An insurance company representative provides policy details to customers</span></span>

- <span data-ttu-id="b1c1c-115">贷款代理从客户请求贷款申请的财务信息</span><span class="sxs-lookup"><span data-stu-id="b1c1c-115">A mortgage broker requests financial information from a customer for a loan application</span></span>

- <span data-ttu-id="b1c1c-116">医疗保健提供商向患者发送医疗保健信息</span><span class="sxs-lookup"><span data-stu-id="b1c1c-116">A health care provider sends health care information to patients</span></span>

- <span data-ttu-id="b1c1c-117">律师将机密信息发送给客户或其他律师</span><span class="sxs-lookup"><span data-stu-id="b1c1c-117">An attorney sends confidential information to a customer or another attorney</span></span>

## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a><span data-ttu-id="b1c1c-118">Office 365 邮件加密在没有新功能的情况下的工作方式</span><span class="sxs-lookup"><span data-stu-id="b1c1c-118">How Office 365 Message Encryption works without the new capabilities</span></span>

<span data-ttu-id="b1c1c-119">Office 365 邮件加密是一种基于 Microsoft Azure 权限管理或 Azure RMS (的联机) 。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-119">Office 365 Message Encryption is an online service that's built on Microsoft Azure Rights Management (Azure RMS).</span></span> <span data-ttu-id="b1c1c-120">使用 Azure RMS，管理员可以定义邮件流规则以确定加密条件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-120">With Azure RMS, administrators can define mail flow rules to determine the conditions for encryption.</span></span> <span data-ttu-id="b1c1c-121">例如，规则可以要求对发送给特定收件人的所有邮件进行加密。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-121">For example, a rule can require the encryption of all messages addressed to a specific recipient.</span></span>
  
<span data-ttu-id="b1c1c-122">观看此简短视频，了解 Office 365 邮件加密在没有新功能的情况下的工作方式。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-122">Watch this short video to see how Office 365 Message Encryption works without the new capabilities.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c55540e7-f7f0-42f5-b254-4b2d2fbb1d63?autoplay=false]
  
<span data-ttu-id="b1c1c-123">当某人在 Exchange Online 中发送与加密规则匹配的电子邮件时，该邮件会随 HTML 附件一起发送。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-123">When someone sends an email message in Exchange Online that matches an encryption rule, the message is sent with an HTML attachment.</span></span> <span data-ttu-id="b1c1c-124">收件人打开 HTML 附件，然后按照说明查看 Office 365 邮件加密门户上的加密邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-124">The recipient opens the HTML attachment and follows instructions to view the encrypted message on the Office 365 Message Encryption portal.</span></span> <span data-ttu-id="b1c1c-125">收件人可以选择通过使用 Microsoft 帐户或与 Office 365 关联的工作或学校登录，或者使用一次通过代码查看邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-125">The recipient can choose to view the message by signing in with a Microsoft account or a work or school associated with Office 365, or by using a one-time pass code.</span></span> <span data-ttu-id="b1c1c-126">两个选项均可以确保只有目标收件人可以查看加密邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-126">Both options help ensure that only the intended recipient can view the encrypted message.</span></span> <span data-ttu-id="b1c1c-127">对于新的 OME 功能，此过程非常不同。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-127">This process is very different for the new OME capabilities.</span></span>
  
<span data-ttu-id="b1c1c-128">下方的图表总结了电子邮件是如何通过加密和解密过程的。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-128">The following diagram summarizes the passage of an email message through the encryption and decryption process.</span></span>
  
![显示加密电子邮件路径的图表](../media/O365-Office365MessageEncryption-Concept.png)
  
<span data-ttu-id="b1c1c-130">有关详细信息，请参阅新 OME 功能发布之前旧版 [Office 365](legacy-information-for-message-encryption.md#LegacyServiceInfo)邮件加密的服务信息。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-130">For more information, see [Service information for legacy Office 365 Message Encryption prior to the release of the new OME capabilities](legacy-information-for-message-encryption.md#LegacyServiceInfo).</span></span>
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a><span data-ttu-id="b1c1c-131">定义不使用新 OME 功能的 Office 365 邮件加密的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="b1c1c-131">Defining mail flow rules for Office 365 Message Encryption that don't use the new OME capabilities</span></span>

<span data-ttu-id="b1c1c-132">若要在没有新功能的情况下启用 Office 365 邮件加密，Exchange Online 和 Exchange Online Protection 管理员定义 Exchange 邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-132">To enable Office 365 Message Encryption without the new capabilities, Exchange Online and Exchange Online Protection administrators define Exchange mail flow rules.</span></span> <span data-ttu-id="b1c1c-133">这些规则确定应在哪些条件下加密电子邮件，以及删除邮件加密的条件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-133">These rules determine under what conditions email messages should be encrypted, as well as conditions for removing message encryption.</span></span> <span data-ttu-id="b1c1c-134">为规则设置加密操作时，该服务在发送邮件之前对符合规则条件的任何邮件执行该操作。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-134">When an encryption action is set for a rule, the service performs the action on any messages that match the rule conditions before sending the messages.</span></span>

<span data-ttu-id="b1c1c-135">邮件流规则非常灵活，可让你组合条件，以便可以在单个规则中满足特定安全要求。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-135">Mail flow rules are flexible, letting you combine conditions so you can meet specific security requirements in a single rule.</span></span> <span data-ttu-id="b1c1c-136">例如，您可以创建一个规则，对包含特定关键字且发送给外部收件人的所有邮件进行加密。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-136">For example, you can create a rule to encrypt all messages that contain specified keywords and are addressed to external recipients.</span></span> <span data-ttu-id="b1c1c-137">Office 365 邮件加密还对加密邮件的收件人的回复进行加密；您可以创建一个规则来对这些回复进行解密，为您的电子邮件用户提供方便。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-137">Office 365 Message Encryption also encrypts replies from recipients of encrypted email, and you can create a rule that decrypts those replies as a convenience for your email users.</span></span> <span data-ttu-id="b1c1c-138">这样，您组织的用户就不需要登录加密门户来查看回复。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-138">That way, users in your organization won't have to sign in to the encryption portal to view replies.</span></span>
  
<span data-ttu-id="b1c1c-139">若要详细了解如何创建 Exchange 邮件流规则，请参阅["定义 Office 365 邮件加密的规则"。](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="b1c1c-139">For more information about how to create Exchange mail flow rules, see [Define Rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="b1c1c-140">使用 EAC 创建用于加密电子邮件的邮件流规则，而不使用新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="b1c1c-140">Use the EAC to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="b1c1c-141">在 Web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户登录[Office 365。](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)</span><span class="sxs-lookup"><span data-stu-id="b1c1c-141">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="b1c1c-142">选择" **管理"** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-142">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="b1c1c-143">在 Microsoft 365 管理中心中，选择 **管理中心** \> **Exchange。**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-143">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="b1c1c-144">在 EAC 中，转到"**邮件流** \> **规则**"，然后选择 **"新建** ![ "图标 ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **"创建新规则"。**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-144">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="b1c1c-145">有关使用 EAC 的信息，请参阅 Exchange Online 中的 [Exchange 管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-145">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="b1c1c-146">在 **"名称**"中，键入规则的名称，例如加密邮件DrToniRamos@hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-146">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="b1c1c-p108">在“在以下情况应用此规则”中，选择一个条件，并根据需要输入值。例如，若要加密发送到 DrToniRamos@hotmail.com 的邮件：</span><span class="sxs-lookup"><span data-stu-id="b1c1c-p108">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="b1c1c-149">在“在以下情况应用此规则”中，选择“收件人为”。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-149">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="b1c1c-150">从联系人列表中选择一个现有名称，或在“检查名称”框中键入一个新的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-150">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="b1c1c-151">若要选择一个现有名称，可以从列表中进行选择，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-151">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="b1c1c-152">若要输入新名称，请在复选框名称框中键入电子邮件地址，然后选择 **"确定"检查** \> **名称**。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-152">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="b1c1c-153">若要添加更多条件，请选择 **"更多选项** "，然后选择 **"添加条件** "，然后从列表中选择。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-153">To add more conditions, choose **More options** and then select **add condition** and select from the list.</span></span>

   <span data-ttu-id="b1c1c-154">例如，若要仅在收件人在组织外部应用规则，请选择"添加条件"，然后选择"收件人在组织外部 **/** 内部 \> **正常** \> "。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-154">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="b1c1c-155">若要启用加密而不使用新的 OME 功能，请在"执行以下操作"中，选择"修改邮件安全性 \> **应用以前版本的 OME"，** 然后选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-155">To enable encryption without using the new OME capabilities, in **Do the following**, select **Modify the message security** \> **Apply the previous version of OME**, and then choose **Save**.</span></span>

   <span data-ttu-id="b1c1c-156">如果您收到 IRM 许可未启用的错误，则表明您没有使用旧版 OME。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-156">If you receive an error that IRM licensing isn't enabled, then you're not using legacy OME.</span></span>

9. <span data-ttu-id="b1c1c-157"> (可选) **选择添加操作以** 指定其他操作。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-157">(Optional) Choose **add action** to specify another action.</span></span>

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="b1c1c-158">使用 Exchange Online PowerShell 创建用于加密电子邮件的邮件流规则，而不使用新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="b1c1c-158">Use Exchange Online PowerShell to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="b1c1c-159">连接到 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-159">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="b1c1c-160">有关详细信息，请参阅[使用远程 PowerShell 连接到 Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-160">For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="b1c1c-161">使用 **New-TransportRule** cmdlet 创建规则，将 _ApplyOME_ 参数设置为 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-161">Create a rule by using the **New-TransportRule** cmdlet and set the _ApplyOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="b1c1c-162">本示例要求发送到该邮箱的所有DrToniRamos@hotmail.com必须加密。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-162">This example requires that all email messages sent to DrToniRamos@hotmail.com must be encrypted.</span></span>

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   <span data-ttu-id="b1c1c-163">其中：</span><span class="sxs-lookup"><span data-stu-id="b1c1c-163">Where,</span></span>

   - <span data-ttu-id="b1c1c-164">新规则的唯一名称是"Encrypt rule for Dr Toni Ramos"。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-164">The unique name of the new rule is "Encrypt rule for Dr Toni Ramos".</span></span>
   - <span data-ttu-id="b1c1c-165">_SentTo_ 参数指定由 (电子邮件地址、可分辨名称等标识的邮件) 。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-165">The _SentTo_ parameter specifies the message recipients (identified by name, email address, distinguished name, etc.).</span></span> <span data-ttu-id="b1c1c-166">本示例中，收件人由电子邮件地址"DrToniRamos@hotmail.com"标识。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-166">In this example, the recipient is identified by the email address "DrToniRamos@hotmail.com".</span></span>
   - <span data-ttu-id="b1c1c-167">_SentToScope_ 参数指定邮件收件人的位置。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-167">The _SentToScope_ parameter specifies the location of the message recipients.</span></span> <span data-ttu-id="b1c1c-168">本示例中，收件人的邮箱位于 hotmail 中，并且不是组织的一部分，因此使用 `NotInOrganization` 该值。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-168">In this example, the recipient's mailbox is in hotmail and is not part of the organization, so the value `NotInOrganization` is used.</span></span>

   <span data-ttu-id="b1c1c-169">有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule)。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-169">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule).</span></span>

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="b1c1c-170">从加密的电子邮件回复中删除加密，而无需新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="b1c1c-170">Remove encryption from email replies encrypted without the new OME capabilities</span></span>

<span data-ttu-id="b1c1c-171">您的电子邮件用户发送加密邮件后，这些邮件的收件人可以使用加密答复回复。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-171">When your email users send encrypted messages, recipients of those messages can respond with encrypted replies.</span></span> <span data-ttu-id="b1c1c-172">您可以创建邮件流规则，以自动从回复中删除加密，以便您的组织中的电子邮件用户不必登录加密门户来查看它们。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-172">You can create mail flow rules to automatically remove encryption from replies so email users in your organization don't have to sign in to the encryption portal to view them.</span></span> <span data-ttu-id="b1c1c-173">可以使用 EAC 或 Windows PowerShell cmdlet 定义这些规则。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-173">You can use the EAC or Windows PowerShell cmdlets to define these rules.</span></span> <span data-ttu-id="b1c1c-174">您可以解密从组织内部发送的邮件，或对从组织内部发送的邮件的答复邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-174">You can decrypt messages that are sent from within your organization or messages that are replies to messages sent from within your organization.</span></span> <span data-ttu-id="b1c1c-175">无法解密来自组织外部的加密邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-175">You cannot decrypt encrypted messages originating from outside of your organization.</span></span>

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="b1c1c-176">使用 EAC 创建一个规则，用于从加密的电子邮件回复中删除加密，而无需新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="b1c1c-176">Use the EAC to create a rule for removing encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="b1c1c-177">在 Web 浏览器中，使用已被授予管理员权限的工作或学校帐户登录[Office 365。](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)</span><span class="sxs-lookup"><span data-stu-id="b1c1c-177">In a web browser, using a work or school account that has been granted admin permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="b1c1c-178">选择" **管理"** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-178">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="b1c1c-179">在 Microsoft 365 管理中心中，选择 **管理中心** \> **Exchange。**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-179">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="b1c1c-180">在 EAC 中，转到"**邮件流** \> **规则**"，然后选择 **"新建** ![ "图标 ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **"创建新规则"。**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-180">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="b1c1c-181">有关使用 EAC 的信息，请参阅 Exchange Online 中的 [Exchange 管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-181">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="b1c1c-182">在 **"名称**"中，键入规则的名称，例如从传入邮件中删除加密。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-182">In **Name**, type a name for the rule, such as Remove encryption from incoming mail.</span></span>

6. <span data-ttu-id="b1c1c-183">在 **"应用此规则"中** ，选择应从邮件中删除加密的条件，例如收件人 **位于** \> **组织内部**。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-183">In **Apply this rule if** select the conditions where encryption should be removed from messages, such as **The recipient is located** \> **Inside the organization**.</span></span>

7. <span data-ttu-id="b1c1c-184">在 **"执行以下操作"** 中，**选择"修改邮件安全性** \> **"删除以前版本的 OME。**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-184">In **Do the following**, select **Modify the message security** \> **Remove the previous version of OME**.</span></span>

8. <span data-ttu-id="b1c1c-185">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-185">Select **Save**.</span></span>

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="b1c1c-186">使用 Exchange Online PowerShell 创建一个规则，以从加密的电子邮件回复中删除加密，而无需新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="b1c1c-186">Use Exchange Online PowerShell to create a rule to remove encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="b1c1c-187">连接到 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-187">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="b1c1c-188">有关详细信息，请参阅[使用远程 PowerShell 连接到 Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-188">For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="b1c1c-189">使用 **New-TransportRule** cmdlet 创建规则，将 _RemoveOME_ 参数设置为 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-189">Create a rule by using the **New-TransportRule** cmdlet and set the _RemoveOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="b1c1c-190">本示例从发送给组织收件人的所有邮件中删除加密。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-190">This example removes the encryption from all mail sent to recipients in the organization.</span></span>

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   <span data-ttu-id="b1c1c-191">其中：</span><span class="sxs-lookup"><span data-stu-id="b1c1c-191">Where,</span></span>

   - <span data-ttu-id="b1c1c-192">新规则的唯一名称是"从传入邮件中删除加密"。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-192">The unique name of the new rule is "Remove encryption from incoming mail".</span></span>
   - <span data-ttu-id="b1c1c-193">_SentToScope_ 参数指定邮件收件人的位置。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-193">The _SentToScope_ parameter specifies the location of the message recipients.</span></span> <span data-ttu-id="b1c1c-194">此示例使用值 `InOrganization` 值，该值指示下列值之一：</span><span class="sxs-lookup"><span data-stu-id="b1c1c-194">In this example, the value `InOrganization` value is used, which indicates one of the following:</span></span>
     - <span data-ttu-id="b1c1c-195">收件人是组织中邮箱、邮件用户、组或已启用邮件的公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-195">The recipient is a mailbox, mail user, group, or mail-enabled public folder in your organization.</span></span>
     - <span data-ttu-id="b1c1c-196">收件人的电子邮件地址位于组织中配置为权威域或内部中继域的接受域中，并且邮件已通过身份验证的连接发送或接收。 </span><span class="sxs-lookup"><span data-stu-id="b1c1c-196">The recipient's email address is in an accepted domain that's configured as an authoritative domain or an internal relay domain in your organization, _and_ the message was sent or received over an authenticated connection.</span></span>

<span data-ttu-id="b1c1c-197">有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule)。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-197">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule).</span></span>

## <a name="sending-viewing-and-replying-to-messages-encrypted-without-the-new-capabilities"></a><span data-ttu-id="b1c1c-198">发送、查看和答复未新功能加密的邮件</span><span class="sxs-lookup"><span data-stu-id="b1c1c-198">Sending, viewing, and replying to messages encrypted without the new capabilities</span></span>

<span data-ttu-id="b1c1c-199">使用 Office 365 邮件加密，电子邮件根据管理员定义的规则自动加密。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-199">With Office 365 Message Encryption, email messages are encrypted automatically, based on administrator-defined rules.</span></span> <span data-ttu-id="b1c1c-200">包含加密邮件的电子邮件会通过附加的 HTML 文件到达收件人的收件箱。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-200">An email that bears an encrypted message arrives in the recipient's Inbox with an attached HTML file.</span></span>
  
<span data-ttu-id="b1c1c-201">收件人按照邮件中的说明打开附件，然后使用 Microsoft 帐户或与 Office 365 关联的工作或学校进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-201">Recipients follow instructions in the message to open the attachment and authenticate by using a Microsoft account or a work or school associated with Office 365.</span></span> <span data-ttu-id="b1c1c-202">如果收件人没有任一帐户，则指示他们创建一个 Microsoft 帐户，以便他们登录以查看加密邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-202">If recipients don't have either account, they're directed to create a Microsoft account that will let them sign in to view the encrypted message.</span></span> <span data-ttu-id="b1c1c-203">或者，收件人可以选择获取一次传递代码来查看邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-203">Alternatively, recipients can choose to get a one-time pass code to view the message.</span></span> <span data-ttu-id="b1c1c-204">登录或使用一次传递代码后，收件人可以查看解密的邮件并发送加密回复。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-204">After signing in or using a one-time pass code, recipients can view the decrypted message and send an encrypted reply.</span></span>
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a><span data-ttu-id="b1c1c-205">使用 Office 365 邮件加密自定义加密邮件</span><span class="sxs-lookup"><span data-stu-id="b1c1c-205">Customize encrypted messages with Office 365 Message Encryption</span></span>

<span data-ttu-id="b1c1c-206">作为 Exchange Online 和 Exchange Online Protection 管理员，您可以自定义加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-206">As an Exchange Online and Exchange Online Protection administrator, you can customize your encrypted messages.</span></span> <span data-ttu-id="b1c1c-207">例如，您可以添加公司的品牌和徽标，指定简介，并添加加密邮件和收件人查看加密邮件的门户中的免责声明文本。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-207">For example, you can add your company's brand and logo, specify an introduction, and add disclaimer text in encrypted messages and in the portal where recipients view your encrypted messages.</span></span> <span data-ttu-id="b1c1c-208">您可以使用 Windows PowerShell cmdlet 为加密的电子邮件的收件人自定义视觉体验的以下方面：</span><span class="sxs-lookup"><span data-stu-id="b1c1c-208">Using Windows PowerShell cmdlets, you can customize the following aspects of the viewing experience for recipients of encrypted email messages:</span></span>

- <span data-ttu-id="b1c1c-209">包含加密邮件的电子邮件介绍性文本</span><span class="sxs-lookup"><span data-stu-id="b1c1c-209">Introductory text of the email that contains the encrypted message</span></span>

- <span data-ttu-id="b1c1c-210">包含加密邮件的电子邮件免责声明文本</span><span class="sxs-lookup"><span data-stu-id="b1c1c-210">Disclaimer text of the email that contains the encrypted message</span></span>

- <span data-ttu-id="b1c1c-211">显示在邮件查看门户中的门户文本</span><span class="sxs-lookup"><span data-stu-id="b1c1c-211">Portal text that will appear in the message viewing portal</span></span>

- <span data-ttu-id="b1c1c-212">显示在电子邮件和查看门户中的徽标</span><span class="sxs-lookup"><span data-stu-id="b1c1c-212">Logo that will appear in the email message and viewing portal</span></span>

<span data-ttu-id="b1c1c-213">您也可以随时还原到默认的外观。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-213">You can also revert back to the default look and feel at any time.</span></span>
  
<span data-ttu-id="b1c1c-214">以下示例显示电子邮件附件中的 ContosoPharma 的自定义徽标：</span><span class="sxs-lookup"><span data-stu-id="b1c1c-214">The following example shows a custom logo for ContosoPharma in the email attachment:</span></span>
  
![查看加密消息页面的示例](../media/TA-OME-3attachment2.jpg)
  
<span data-ttu-id="b1c1c-216">**使用组织的品牌自定义加密电子邮件和加密门户**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-216">**To customize encryption email messages and the encryption portal with your organization's brand**</span></span>
  
1. <span data-ttu-id="b1c1c-217">使用远程 PowerShell 连接到 Exchange Online，如使用远程 [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)连接到 Exchange Online 中所述。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-217">Connect to Exchange Online using Remote PowerShell, as described in [Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="b1c1c-218">使用 Set-OMEConfiguration cmdlet，如下所述 [：Set-OMEConfiguration](https://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b) 或使用下表提供指导。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-218">Use the Set-OMEConfiguration cmdlet as described here: [Set-OMEConfiguration](https://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b) or use the following table for guidance.</span></span>

   <span data-ttu-id="b1c1c-219">**加密自定义选项**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-219">**Encryption customization options**</span></span>

<span data-ttu-id="b1c1c-220">**自定义加密体验的这一功能**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-220">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="b1c1c-221">**使用这些 Windows PowerShell 命令**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-221">**Use these Windows PowerShell commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b1c1c-222">加密电子邮件随附的默认文本</span><span class="sxs-lookup"><span data-stu-id="b1c1c-222">Default text that accompanies encrypted email messages</span></span>  <br/> <span data-ttu-id="b1c1c-223">默认文本显示在说明的上方，以查看加密邮件</span><span class="sxs-lookup"><span data-stu-id="b1c1c-223">The default text appears above the instructions for viewing encrypted messages</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> <span data-ttu-id="b1c1c-224">**示例：** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"`</span><span class="sxs-lookup"><span data-stu-id="b1c1c-224">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"`</span></span> <br/> |
|<span data-ttu-id="b1c1c-225">包含加密邮件的电子邮件中的免责声明</span><span class="sxs-lookup"><span data-stu-id="b1c1c-225">Disclaimer statement in the email that contains the encrypted message</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> <span data-ttu-id="b1c1c-226">**示例：** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"`</span><span class="sxs-lookup"><span data-stu-id="b1c1c-226">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"`</span></span> <br/> |
|<span data-ttu-id="b1c1c-227">显示在加密邮件查看门户顶部的文本</span><span class="sxs-lookup"><span data-stu-id="b1c1c-227">Text that appears at the top of the encrypted mail viewing portal</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> <span data-ttu-id="b1c1c-228">**示例：** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"`</span><span class="sxs-lookup"><span data-stu-id="b1c1c-228">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"`</span></span> <br/> |
|<span data-ttu-id="b1c1c-229">徽标</span><span class="sxs-lookup"><span data-stu-id="b1c1c-229">Logo</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> <span data-ttu-id="b1c1c-230">**示例：** `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)`</span><span class="sxs-lookup"><span data-stu-id="b1c1c-230">**Example:** `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)`</span></span> <br/> <span data-ttu-id="b1c1c-231">支持的文件格式：.png、.jpg、.bmp 或 .tiff</span><span class="sxs-lookup"><span data-stu-id="b1c1c-231">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="b1c1c-232">徽标文件的最佳大小：小于 40 KB</span><span class="sxs-lookup"><span data-stu-id="b1c1c-232">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="b1c1c-233">徽标图像的最佳大小：170x70 像素</span><span class="sxs-lookup"><span data-stu-id="b1c1c-233">Optimal size of logo image: 170x70 pixels</span></span>  <br/> |

<span data-ttu-id="b1c1c-234">**从加密电子邮件和加密门户中删除品牌自定义**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-234">**To remove brand customizations from encryption email messages and the encryption portal**</span></span>
  
1. <span data-ttu-id="b1c1c-235">使用远程 PowerShell 连接到 Exchange Online，如使用远程 [PowerShell 连接到 Exchange Online 中所述](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-235">Connect to Exchange Online using Remote PowerShell, as described in [Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="b1c1c-236">使用 Set-OMEConfiguration cmdlet，如下所述 [：Set-OMEConfiguration](https://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b)。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-236">Use the Set-OMEConfiguration cmdlet as described here: [Set-OMEConfiguration](https://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b).</span></span> <span data-ttu-id="b1c1c-237">若要从 DisclaimerText、EmailText 和 PortalText 值中删除组织的品牌自定义项，请将其设置为空字符串  `""` 。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-237">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string,  `""`.</span></span> <span data-ttu-id="b1c1c-238">对于所有图像值（如徽标），将值设置为  `"$null"` 。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-238">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

   <span data-ttu-id="b1c1c-239">**加密自定义选项**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-239">**Encryption customization options**</span></span>

|<span data-ttu-id="b1c1c-240">**将加密体验的此功能还原到默认的文本和图片**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-240">**To revert this feature of the encryption experience back to the default text and image**</span></span>|<span data-ttu-id="b1c1c-241">**使用这些 Windows PowerShell 命令**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-241">**Use these Windows PowerShell commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b1c1c-242">加密电子邮件随附的默认文本</span><span class="sxs-lookup"><span data-stu-id="b1c1c-242">Default text that accompanies encrypted email messages</span></span>  <br/> <span data-ttu-id="b1c1c-243">默认文本显示在说明的上方，以查看加密邮件</span><span class="sxs-lookup"><span data-stu-id="b1c1c-243">The default text appears above the instructions for viewing encrypted messages</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> <span data-ttu-id="b1c1c-244">**示例：** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`</span><span class="sxs-lookup"><span data-stu-id="b1c1c-244">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`</span></span> <br/> |
|<span data-ttu-id="b1c1c-245">包含加密邮件的电子邮件中的免责声明</span><span class="sxs-lookup"><span data-stu-id="b1c1c-245">Disclaimer statement in the email that contains the encrypted message</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> <span data-ttu-id="b1c1c-246">**示例：** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`</span><span class="sxs-lookup"><span data-stu-id="b1c1c-246">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`</span></span> <br/> |
|<span data-ttu-id="b1c1c-247">显示在加密邮件查看门户顶部的文本</span><span class="sxs-lookup"><span data-stu-id="b1c1c-247">Text that appears at the top of the encrypted mail viewing portal</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> <span data-ttu-id="b1c1c-248">**恢复为默认值的示例：**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`</span><span class="sxs-lookup"><span data-stu-id="b1c1c-248">**Example reverting back to default:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`</span></span> <br/> |
|<span data-ttu-id="b1c1c-249">徽标</span><span class="sxs-lookup"><span data-stu-id="b1c1c-249">Logo</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> <span data-ttu-id="b1c1c-250">**恢复为默认值的示例：**`Set-OMEConfiguration -Identity "OME configuration" -Image $null`</span><span class="sxs-lookup"><span data-stu-id="b1c1c-250">**Example reverting back to default:** `Set-OMEConfiguration -Identity "OME configuration" -Image $null`</span></span> <br/> |

## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a><span data-ttu-id="b1c1c-251">新 OME 功能发布之前旧版 Office 365 邮件加密的服务信息</span><span class="sxs-lookup"><span data-stu-id="b1c1c-251">Service information for legacy Office 365 Message Encryption prior to the release of the new OME capabilities</span></span>
<span data-ttu-id="b1c1c-252"><a name="LegacyServiceInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="b1c1c-252"><a name="LegacyServiceInfo"> </a></span></span>

<span data-ttu-id="b1c1c-253">下表提供了新 OME 功能发布之前 Office 365 邮件加密服务的技术详细信息。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-253">The following table provides technical details for the Office 365 Message Encryption service prior to the release of the new OME capabilities.</span></span>
  
|<span data-ttu-id="b1c1c-254">**服务详细信息**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-254">**Service details**</span></span>|<span data-ttu-id="b1c1c-255">**说明**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-255">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b1c1c-256">客户端设备要求</span><span class="sxs-lookup"><span data-stu-id="b1c1c-256">Client device requirements</span></span>  <br/> |<span data-ttu-id="b1c1c-257">只要 HTML 附件可以在支持窗体发布的现代浏览器中打开，就可以在任何客户端设备上查看加密邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-257">Encrypted messages can be viewed on any client device, as long as the HTML attachment can be opened in a modern browser that supports Form Post.</span></span>  <br/> |
|<span data-ttu-id="b1c1c-258">加密算法和美国联邦信息处理标准 (FIPS) 合规性</span><span class="sxs-lookup"><span data-stu-id="b1c1c-258">Encryption algorithm and Federal Information Processing Standards (FIPS) compliance</span></span>  <br/> |<span data-ttu-id="b1c1c-259">Office 365 邮件加密使用与 Windows Azure 信息权限管理 (IRM) 相同的加密密钥，并支持加密模式 2（对于 RSA 是 2K 密钥，对于 SHA-1 系统是 256 位密钥）。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-259">Office 365 Message Encryption uses the same encryption keys as Windows Azure Information Rights Management (IRM) and supports Cryptographic Mode 2 (2K key for RSA and 256 bits key for SHA-1 systems).</span></span> <span data-ttu-id="b1c1c-260">有关基础 IRM 加密模式的信息，请参阅 [AD RMS 加密模式](https://technet.microsoft.com/library/hh867439%28WS.10%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-260">For more information about the underlying IRM cryptographic modes, see [AD RMS Cryptographic Modes](https://technet.microsoft.com/library/hh867439%28WS.10%29.aspx).</span></span>  <br/> |
|<span data-ttu-id="b1c1c-261">支持的邮件类型</span><span class="sxs-lookup"><span data-stu-id="b1c1c-261">Supported message types</span></span>  <br/> |<span data-ttu-id="b1c1c-262">如果是针对那些具有 **IPM.Note** 的邮件类 ID 项，才支持使用 Office 365 邮件加密。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-262">Office 365 Message Encryption is only supported for items that have a message class ID of **IPM.Note**.</span></span> <span data-ttu-id="b1c1c-263">有关详细信息，请参阅 [项目类型和邮件类](https://msdn.microsoft.com/library/office/ff861573.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-263">For more information, see [Item types and message classes](https://msdn.microsoft.com/library/office/ff861573.aspx).</span></span>  <br/> |
|<span data-ttu-id="b1c1c-264">邮件大小限制</span><span class="sxs-lookup"><span data-stu-id="b1c1c-264">Message size limits</span></span>  <br/> |<span data-ttu-id="b1c1c-265">Office 365 邮件加密可以加密最多 25 兆字节的邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-265">Office 365 Message Encryption can encrypt messages of up to 25 megabytes.</span></span> <span data-ttu-id="b1c1c-266">有关邮件大小限制的更多详细信息，请参阅 [Exchange Online 限制](https://technet.microsoft.com/library/exchange-online-limits.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-266">For more details about message size limits, see [Exchange Online Limits](https://technet.microsoft.com/library/exchange-online-limits.aspx).</span></span>  <br/> |
|<span data-ttu-id="b1c1c-267">Exchange Online 电子邮件保留策略</span><span class="sxs-lookup"><span data-stu-id="b1c1c-267">Exchange Online email retention policies</span></span>  <br/> |<span data-ttu-id="b1c1c-268">Exchange Online 不存储加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-268">Exchange Online doesn't store the encrypted messages.</span></span>  <br/> |
|<span data-ttu-id="b1c1c-269">Office 365 邮件加密的语言支持</span><span class="sxs-lookup"><span data-stu-id="b1c1c-269">Language support for Office 365 Message Encryption</span></span>  <br/> | <span data-ttu-id="b1c1c-270">Office 365 邮件加密支持 Microsoft 365 语言，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1c1c-270">Office 365 Message encryption supports Microsoft 365 languages, as follows:</span></span>  <br/>  <span data-ttu-id="b1c1c-271">传入电子邮件和附加的 HTML 文件根据发件人的语言设置进行本地化。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-271">Incoming email messages and attached HTML files are localized based on the sender's language settings.</span></span>  <br/>  <span data-ttu-id="b1c1c-272">查看门户根据收件人的浏览器设置进行本地化。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-272">The viewing portal is localized based on the recipient's browser settings.</span></span>  <br/>  <span data-ttu-id="b1c1c-273">加密邮件的正文（内容）不进行本地化。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-273">The body (content) of the encrypted message isn't localized.</span></span>  <br/> |
|<span data-ttu-id="b1c1c-274">OME 门户和 OME 查看器应用的隐私信息</span><span class="sxs-lookup"><span data-stu-id="b1c1c-274">Privacy information for OME Portal and OME Viewer App</span></span>  <br/> |<span data-ttu-id="b1c1c-275">[Office 365 Messaging Encryption Portal privacy statement](https://privacy.microsoft.com/privacystatement)提供了有关 Microsoft 如何处理您的隐私信息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-275">The [Office 365 Messaging Encryption Portal privacy statement](https://privacy.microsoft.com/privacystatement) provides detailed information about what Microsoft does and doesn't do with your private information.</span></span>  <br/> |

## <a name="frequently-asked-questions-about-legacy-ome"></a><span data-ttu-id="b1c1c-276">有关旧 OME 的常见问题</span><span class="sxs-lookup"><span data-stu-id="b1c1c-276">Frequently Asked Questions about legacy OME</span></span>
<span data-ttu-id="b1c1c-277"><a name="LegacyServiceInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="b1c1c-277"><a name="LegacyServiceInfo"> </a></span></span>

<span data-ttu-id="b1c1c-278">对 Office 365 邮件加密有疑问？</span><span class="sxs-lookup"><span data-stu-id="b1c1c-278">Got questions about Office 365 Message Encryption?</span></span> <span data-ttu-id="b1c1c-279">下面对一些问题进行了解答。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-279">Here are some answers.</span></span> <span data-ttu-id="b1c1c-280">如果找不到所需的信息，请查看 [Office 365 的 Microsoft 技术社区论坛](https://techcommunity.microsoft.com/t5/Office-365/ct-p/Office365)。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-280">If you can't find what you need, check the [Microsoft Tech Community forums for Office 365](https://techcommunity.microsoft.com/t5/Office-365/ct-p/Office365).</span></span>
  
 <span data-ttu-id="b1c1c-281">**问：我的用户向组织外部的收件人发送加密的电子邮件。外部收件人是否必须执行任何操作才能读取和答复使用 Office 365 邮件加密加密的电子邮件？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-281">**Q. My users send encrypted email messages to recipients outside our organization. Is there anything that external recipients have to do in order to read and reply to email messages that are encrypted with Office 365 Message Encryption?**</span></span>
  
<span data-ttu-id="b1c1c-282">组织外部接收 Microsoft 365 加密邮件的收件人可以通过两种方式之一查看：</span><span class="sxs-lookup"><span data-stu-id="b1c1c-282">Recipients outside your organization who receive Microsoft 365 encrypted messages can view them in one of two ways:</span></span>
  
- <span data-ttu-id="b1c1c-283">通过使用 Microsoft 帐户或与 Office 365 关联的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-283">By signing in with a Microsoft account or a work or school account associated with Office 365.</span></span>

- <span data-ttu-id="b1c1c-284">通过使用一次传递代码。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-284">By using a one-time pass code.</span></span>

 <span data-ttu-id="b1c1c-285">**问：Microsoft 365 加密邮件是否存储在云中或 Microsoft 服务器上？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-285">**Q. Are Microsoft 365 encrypted messages stored in the cloud or on Microsoft servers?**</span></span>
  
<span data-ttu-id="b1c1c-286">否，加密的邮件保留在收件人的电子邮件系统中，当收件人打开邮件时，会临时发布邮件，以便查看 Microsoft 服务器。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-286">No, the encrypted messages are kept on the recipient's email system, and when the recipient opens the message, it is temporarily posted for viewing on Microsoft servers.</span></span> <span data-ttu-id="b1c1c-287">邮件并不存储在其中。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-287">The messages are not stored there.</span></span>
  
 <span data-ttu-id="b1c1c-288">**问：能否使用我的品牌自定义加密电子邮件？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-288">**Q. Can I customize encrypted email messages with my brand?**</span></span>
  
<span data-ttu-id="b1c1c-289">是。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-289">Yes.</span></span> <span data-ttu-id="b1c1c-290">您可以使用 Windows PowerShell cmdlet 自定义显示在加密电子邮件顶部的默认文本、免责声明文本以及要用于电子邮件和加密门户的徽标。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-290">You can use Windows PowerShell cmdlets to customize the default text that appears at the top of encrypted email messages, the disclaimer text, and the logo that you want to use for the email message and the encryption portal.</span></span> <span data-ttu-id="b1c1c-291">此功能现已在 OMEv2 中提供。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-291">This feature is now available in OMEv2.</span></span> <span data-ttu-id="b1c1c-292">有关详细信息，请参阅["向加密邮件添加品牌"。](add-your-organization-brand-to-encrypted-messages.md)</span><span class="sxs-lookup"><span data-stu-id="b1c1c-292">For details, see [Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
 <span data-ttu-id="b1c1c-293">**问：该服务是否要求我的组织中的每个用户都有许可证？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-293">**Q. Does the service require a license for every user in my organization?**</span></span>
  
<span data-ttu-id="b1c1c-294">组织中发送加密电子邮件的每个用户都必须有许可证。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-294">A license is required for every user in the organization who sends encrypted email.</span></span>
  
 <span data-ttu-id="b1c1c-295">**问：外部收件人是否需要订阅？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-295">**Q. Do external recipients require subscriptions?**</span></span>
  
<span data-ttu-id="b1c1c-296">否，外部收件人不需要订阅即可阅读或回复加密邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-296">No, external recipients do not require a subscription to read or reply to encrypted messages.</span></span>
  
 <span data-ttu-id="b1c1c-297">**问：Office 365 邮件加密与权限管理服务与 RMS (之间) ？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-297">**Q. How is Office 365 Message Encryption different from Rights Management Services (RMS)?**</span></span>
  
<span data-ttu-id="b1c1c-298">RMS 通过提供内置模板（例如：不要转发和公司机密）为组织的内部电子邮件提供信息权限保护功能。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-298">RMS provides Information Rights Protection capabilities for an organization's internal emails by providing built-in templates, such as: Do not forward and Company Confidential.</span></span> <span data-ttu-id="b1c1c-299">Office 365 邮件加密支持对发送给外部以及内部收件人的邮件进行加密。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-299">Office 365 Message Encryption supports email message encryption for messages that are sent to external recipients as well as internal recipients.</span></span>
  
 <span data-ttu-id="b1c1c-300">**问：Office 365 邮件加密与 S/MIME 如何不同？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-300">**Q. How is Office 365 Message Encryption different from S/MIME?**</span></span>
  
<span data-ttu-id="b1c1c-301">S/MIME 实质上是一种客户端加密技术，需要复杂的证书管理和发布基础结构。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-301">S/MIME is essentially a client-side encryption technology, and requires complicated certificate management and publishing infrastructure.</span></span> <span data-ttu-id="b1c1c-302">Office 365 邮件加密使用邮件流规则 (也称为传输) 规则，不依赖于证书发布。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-302">Office 365 Message Encryption uses mail flow rules (also known as transport rules) and does not depend on certificate publishing.</span></span>
  
 <span data-ttu-id="b1c1c-303">**问：能否通过移动设备阅读加密邮件？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-303">**Q. Can I read the encrypted messages over mobile devices?**</span></span>
  
<span data-ttu-id="b1c1c-304">可以，可以通过从 Google Play 应用商店和 Apple App Store 下载 OME 查看器应用，在 Android 和 iOS 上查看消息。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-304">Yes, you can view messages on Android and iOS by downloading the OME Viewer apps from the Google Play store and the Apple App store.</span></span> <span data-ttu-id="b1c1c-305">在 OME 查看器应用中打开 HTML 附件，然后按照说明打开加密邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-305">Open the HTML attachment in the OME Viewer app and then follow the instructions to open your encrypted message.</span></span> <span data-ttu-id="b1c1c-306">对于其他移动设备，您可以打开 HTML 附件，只要您的邮件客户端支持表单发布。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-306">For other mobile devices, you can open the HTML attachment as long as your mail client supports Form Post.</span></span>
  
 <span data-ttu-id="b1c1c-307">**问：是否对回复和转发的邮件进行加密？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-307">**Q. Are replies and forwarded messages encrypted?**</span></span>
  
<span data-ttu-id="b1c1c-p129">是，在整个线程期限内，响应都会继续进行加密。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-p129">Yes. Responses continue to be encrypted throughout the duration of the thread.</span></span>
  
 <span data-ttu-id="b1c1c-310">**问：Office 365 邮件加密是否提供本地化？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-310">**Q. Does Office 365 Message Encryption provide localization?**</span></span>
  
<span data-ttu-id="b1c1c-p130">传入电子邮件和 HTML 内容会进行本地化，具体取决于发件人电子邮件设置。查看门户根据收件人的浏览器设置进行本地化。不过，加密邮件的实际正文（内容）不会进行本地化。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-p130">Incoming email and HTML content is localized based on sender email settings. The viewing portal is localized based on recipient's browser settings. However, the actual body (content) of encrypted message isn't localized.</span></span>
  
 <span data-ttu-id="b1c1c-314">**问：Office 365 邮件加密使用哪种加密方法？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-314">**Q. What encryption method is used for Office 365 Message Encryption?**</span></span>
  
<span data-ttu-id="b1c1c-315">Office 365 邮件加密使用权限管理服务 (RMS) 作为加密基础结构。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-315">Office 365 Message Encryption uses Rights Management Services (RMS) as its encryption infrastructure.</span></span> <span data-ttu-id="b1c1c-316">所使用的加密方法取决于从何处获取用来加密和解密邮件的 RMS 密钥。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-316">The encryption method used depends on where you obtain the RMS keys used to encrypt and decrypt messages.</span></span>
  
- <span data-ttu-id="b1c1c-317">如果使用 Microsoft Azure RMS 获取密钥，则使用加密模式 2。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-317">If you use Microsoft Azure RMS to obtain the keys, Cryptographic Mode 2 is used.</span></span> <span data-ttu-id="b1c1c-318">加密模式 2 是更新和增强的 AD RMS 加密实现。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-318">Cryptographic Mode 2 is an updated and enhanced AD RMS cryptographic implementation.</span></span> <span data-ttu-id="b1c1c-319">它支持 RSA 2048 签名和加密，并支持 sha-256 签名。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-319">It supports RSA 2048 for signature and encryption, and supports SHA-256 for signature.</span></span>

- <span data-ttu-id="b1c1c-p133">如果您使用 Active Directory (AD) RMS 获取这些密钥，则可以使用加密模式 1，也可以使用加密模式 2。使用的方法取决于您的本地 AD RMS 部署。加密模式 1 是原始的 AD RMS 加密实现。它支持 RSA 1024 签名和加密，并支持 sha-1 签名。该模式继续支持 RMS 的所有当前版本。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-p133">If you use Active Directory (AD) RMS to obtain the keys, either Cryptographic Mode 1 or Cryptographic Mode 2 is used. The method used depends on your on-premises AD RMS deployment. Cryptographic Mode 1 is the original AD RMS cryptographic implementation. It supports RSA 1024 for signature and encryption, and supports SHA-1 for signature. This mode continues to be supported by all current versions of RMS.</span></span>

<span data-ttu-id="b1c1c-325">有关详细信息，请参阅 [AD RMS 加密模式](https://go.microsoft.com/fwlink/p/?LinkId=398616)。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-325">For more information, see [AD RMS Cryptographic Modes](https://go.microsoft.com/fwlink/p/?LinkId=398616).</span></span>
  
<span data-ttu-id="b1c1c-326">**问：为什么有些加密邮件说它们来自Office365@messaging.microsoft.com？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-326">**Q. Why do some encrypted messages say they come from** Office365@messaging.microsoft.com?</span></span>
  
<span data-ttu-id="b1c1c-p134">当加密回复从加密门户或通过 OME 查看器应用发送时，发送电子邮件地址将设为 Office365@messaging.microsoft.com，因为该加密邮件是通过 Microsoft 终结点发送的。这有助于防止加密邮件被标记为垃圾邮件。电子邮件上显示的名称和加密门户内的地址不会因为这个标签而更改。此外，该标签仅适用于通过门户而不是通过任何其他电子邮件客户端发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-p134">When an encrypted reply is sent from the encryption portal or through the OME Viewer app, the sending email address is set to Office365@messaging.microsoft.com because the encrypted message is sent through a Microsoft endpoint. This helps to prevent encrypted messages from being marked as spam. The displayed name on the email and the address within the encryption portal aren't changed because of this labeling. Also, this labeling only applies to messages sent through the portal, not through any other email client.</span></span>
  
 <span data-ttu-id="b1c1c-331">**问：我是 EHE 订阅者 (Exchange) 加密。在哪里可以了解有关升级到 Office 365 邮件加密的信息？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-331">**Q. I am an Exchange Hosted Encryption (EHE) subscriber. Where can I learn more about the upgrade to Office 365 Message Encryption?**</span></span>
  
<span data-ttu-id="b1c1c-332">所有 EHE 客户已升级为 Office 365 邮件加密客户。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-332">All EHE customers have been upgraded to Office 365 Message Encryption.</span></span> <span data-ttu-id="b1c1c-333">有关详细信息，请访问 Exchange [托管加密升级中心](https://go.microsoft.com/fwlink/p/?LinkID=511077)。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-333">For more information, visit the [Exchange Hosted Encryption Upgrade Center](https://go.microsoft.com/fwlink/p/?LinkID=511077).</span></span>
  
 <span data-ttu-id="b1c1c-334">**问：是否需要打开组织防火墙中任何 URL、IP 地址或端口以支持 Office 365 邮件加密？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-334">**Q. Do I need to open any URLs, IP addresses, or ports in my organization's firewall to support Office 365 Message Encryption?**</span></span>
  
<span data-ttu-id="b1c1c-335">是。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-335">Yes.</span></span> <span data-ttu-id="b1c1c-336">您必须将 Exchange Online 的 URL 添加到组织的允许列表中，才能对由 Office 365 邮件加密加密的邮件启用身份验证。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-336">You have to add URLs for Exchange Online to the allow list for your organization to enable authentication for messages encrypted by Office 365 Message Encryption.</span></span> <span data-ttu-id="b1c1c-337">有关 Exchange Online URL 的列表，请参阅 [Microsoft 365 URL 和 IP 地址范围](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-337">For a list of Exchange Online URLs, see [Microsoft 365 URLs and IP address ranges](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span>
  
 <span data-ttu-id="b1c1c-338">**问：我可以向多少个收件人发送 Microsoft 365 加密邮件？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-338">**Q. How many recipients can I send an Microsoft 365 encrypted message to?**</span></span>
  
<span data-ttu-id="b1c1c-339">收件人限制为每封邮件 500 个收件人，或在通讯组列表展开后合并时，邮件的"收件人"字段中包含 11，980 个字符，以先发生者为准。 </span><span class="sxs-lookup"><span data-stu-id="b1c1c-339">The recipient limit is 500 recipients per message, or, when combined after distribution list expansion, 11,980 characters in the message's **To** field, whichever comes first.</span></span>
  
 <span data-ttu-id="b1c1c-340">**问：是否可以取消发送给特定收件人的邮件？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-340">**Q. Is it possible to revoke a message sent to a particular recipient?**</span></span>
  
<span data-ttu-id="b1c1c-341">否。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-341">No.</span></span> <span data-ttu-id="b1c1c-342">在邮件发送后，无法撤消发送给特定人员的邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-342">You can't revoke a message to a particular person after it's sent.</span></span>
  
 <span data-ttu-id="b1c1c-343">**问：是否可以查看已接收和阅读的加密邮件报告吗？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-343">**Q. Can I view a report of encrypted messages that have been received and read?**</span></span>
  
<span data-ttu-id="b1c1c-344">没有显示是否查看过加密邮件的报告，但可以使用 Microsoft 365 报告来确定匹配特定邮件流规则 (也称为传输规则) （例如）的邮件数量。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-344">There isn't a report that shows if an encrypted message has been viewed, but there are Microsoft 365 reports available that you can leverage to determine the number of messages that matched a specific mail flow rule (also known as a transport rule), for instance.</span></span>
  
 <span data-ttu-id="b1c1c-345">**问：Microsoft 会如何处理我通过 OME 门户和 OME 查看器应用提供的信息？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-345">**Q. What does Microsoft do with the information I provide through the OME Portal and the OME Viewer App?**</span></span>
  
<span data-ttu-id="b1c1c-346">[Office 365](https://privacy.microsoft.com/privacystatement)邮件加密门户隐私声明提供有关 Microsoft 对专用信息执行哪些操作和不执行哪些操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-346">The [Office 365 Messaging Encryption Portal privacy statement](https://privacy.microsoft.com/privacystatement) provides detailed information about what Microsoft does and doesn't do with your private information.</span></span>

<span data-ttu-id="b1c1c-347">**问：如果我在请求一次传递代码后没有收到该代码，该怎么办？**</span><span class="sxs-lookup"><span data-stu-id="b1c1c-347">**Q. What do I do if I don’t receive the one-time pass code after I requested it?**</span></span>

<span data-ttu-id="b1c1c-348">首先，检查电子邮件客户端中的垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-348">First, check the junk or spam folder in your email client.</span></span> <span data-ttu-id="b1c1c-349">组织的 DKIM 和 DMARC 设置可能会导致这些电子邮件最终被筛选为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-349">DKIM and DMARC settings for your organization may cause these emails to end up filtered as spam.</span></span>

<span data-ttu-id="b1c1c-350">接下来，在安全与合规中心&隔离。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-350">Next, check quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="b1c1c-351">通常，包含一次传递代码的邮件（尤其是组织收到的第一批邮件）最终被隔离。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-351">Often, messages containing a one-time pass code, especially the first ones your organization receives, end up in quarantine.</span></span>
