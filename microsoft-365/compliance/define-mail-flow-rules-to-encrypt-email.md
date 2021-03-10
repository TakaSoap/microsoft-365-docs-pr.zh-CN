---
title: 定义邮件流规则以加密电子邮件
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何创建邮件流规则 (传输规则) Office 365 邮件加密加密和解密邮件。
ms.openlocfilehash: 8060309f350b50c2aadc9a703e7a57a4caf8808c
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597224"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a><span data-ttu-id="0aac6-103">定义邮件流规则以加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="0aac6-103">Define mail flow rules to encrypt email messages</span></span>

<span data-ttu-id="0aac6-104">作为管理 Exchange Online 的管理员，您可以创建邮件流规则 (也称为传输) 规则，以帮助保护发送和接收的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0aac6-104">As an administrator that manages Exchange Online, you can create mail flow rules (also known as transport rules) to help protect email messages you send and receive.</span></span> <span data-ttu-id="0aac6-105">您可以设置规则来加密任何传出电子邮件，并从来自组织内部的加密邮件或对从组织发送的加密邮件的答复中删除加密。</span><span class="sxs-lookup"><span data-stu-id="0aac6-105">You can set up rules to encrypt any outgoing email messages and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> <span data-ttu-id="0aac6-106">可以使用 Exchange 管理中心 (EAC) 或 Exchange Online PowerShell 创建这些规则。</span><span class="sxs-lookup"><span data-stu-id="0aac6-106">You can use the Exchange admin center (EAC) or Exchange Online PowerShell to create these rules.</span></span> <span data-ttu-id="0aac6-107">除了整体的加密规则，您还可以针对最终用户选择启用或禁用个人邮件加密选项。</span><span class="sxs-lookup"><span data-stu-id="0aac6-107">In addition to overall encryption rules, you can also choose to enable or disable individual message encryption options for end users.</span></span>

<span data-ttu-id="0aac6-108">无法加密来自组织外部发件人的入站邮件。</span><span class="sxs-lookup"><span data-stu-id="0aac6-108">You can't encrypt inbound mail from senders outside of your organization.</span></span>

<span data-ttu-id="0aac6-109">如果你最近从 Active Directory RMS 迁移到 Azure 信息保护，你将需要查看现有的邮件流规则，以确保它们继续在新环境中工作。</span><span class="sxs-lookup"><span data-stu-id="0aac6-109">If you recently migrated from Active Directory RMS to Azure Information Protection, you'll need to review your existing mail flow rules to ensure that they continue to work in your new environment.</span></span> <span data-ttu-id="0aac6-110">此外，如果要利用通过 Azure 信息保护提供的新 Office 365 邮件加密 (OME) 功能，则需要更新现有的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="0aac6-110">Also, if you want to take advantage of the new Office 365 Message Encryption (OME) capabilities available to you through Azure Information Protection, you need to update your existing mail flow rules.</span></span> <span data-ttu-id="0aac6-111">否则，用户将继续接收使用以前的 HTML 附件格式而不是新的无缝 OME 体验的加密邮件。</span><span class="sxs-lookup"><span data-stu-id="0aac6-111">Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience.</span></span> <span data-ttu-id="0aac6-112">如果尚未设置 OME，请参阅"设置新的 [Office 365](set-up-new-message-encryption-capabilities.md) 邮件加密功能"了解相关信息。</span><span class="sxs-lookup"><span data-stu-id="0aac6-112">If you haven't set up OME yet, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md) for information.</span></span>

<span data-ttu-id="0aac6-113">有关组成邮件流规则的组件以及邮件流规则如何工作的信息，请参阅邮件流规则 ([Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)中的) 规则。</span><span class="sxs-lookup"><span data-stu-id="0aac6-113">For information about the components that make up mail flow rules and how mail flow rules work, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span> <span data-ttu-id="0aac6-114">有关邮件流规则如何与 Azure 信息保护一起工作的其他信息，请参阅为 Azure 信息保护标签配置 Exchange Online 邮件 [流规则](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)。</span><span class="sxs-lookup"><span data-stu-id="0aac6-114">For additional information about how mail flow rules work with Azure Information Protection, see [Configuring Exchange Online mail flow rules for Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0aac6-115">对于混合 Exchange 环境，本地用户只有在通过 Exchange Online 路由电子邮件时，才能使用 OME 发送和接收加密邮件。</span><span class="sxs-lookup"><span data-stu-id="0aac6-115">For hybrid Exchange environments, on-premises users can send and receive encrypted mail using OME only if email is routed through Exchange Online.</span></span> <span data-ttu-id="0aac6-116">若要在混合 Exchange 环境中配置 OME，您需要首先[](https://docs.microsoft.com/Exchange/exchange-hybrid)使用混合配置向导配置混合，然后将邮件配置为从[Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server)流向您的电子邮件服务器，并配置邮件以从您的电子邮件服务器流向[Office 365。](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)</span><span class="sxs-lookup"><span data-stu-id="0aac6-116">To configure OME in a hybrid Exchange environment, you need to first [configure hybrid using the Hybrid Configuration wizard](https://docs.microsoft.com/Exchange/exchange-hybrid) and then [configure mail to flow from Office 365 to your email server](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server) and [configure mail to flow from your email server to Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365).</span></span> <span data-ttu-id="0aac6-117">将邮件配置为通过 Office 365 流动后，可以使用本指南为 OME 配置邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="0aac6-117">Once you've configured mail to flow through Office 365, then you can configure mail flow rules for OME by using this guidance.</span></span>

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="0aac6-118">创建邮件流规则以使用新的 OME 功能加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="0aac6-118">Create mail flow rules to encrypt email messages with the new OME capabilities</span></span>

<span data-ttu-id="0aac6-119">可以使用 EAC 定义邮件流规则，以使用新的 OME 功能触发邮件加密。</span><span class="sxs-lookup"><span data-stu-id="0aac6-119">You can define mail flow rules for triggering message encryption with the new OME capabilities by using the EAC.</span></span>

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="0aac6-120">使用 EAC 创建使用新的 OME 功能加密电子邮件的规则</span><span class="sxs-lookup"><span data-stu-id="0aac6-120">Use the EAC to create a rule for encrypting email messages with the new OME capabilities</span></span>

1. <span data-ttu-id="0aac6-121">在 Web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户登录[Office 365。](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)</span><span class="sxs-lookup"><span data-stu-id="0aac6-121">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="0aac6-122">选择 **"管理"** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="0aac6-122">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="0aac6-123">在 Microsoft 365 管理中心中，选择 **"管理中心** \> **Exchange"。**</span><span class="sxs-lookup"><span data-stu-id="0aac6-123">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="0aac6-124">在 EAC 中，转到"**邮件流** 规则 \> "，然后选择 **"新建**" ![ 图标 ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **"创建新规则"。**</span><span class="sxs-lookup"><span data-stu-id="0aac6-124">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="0aac6-125">有关使用 EAC 的信息，请参阅 [Exchange Online 中的 Exchange 管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="0aac6-125">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="0aac6-126">在 **"名称**"中，键入规则的名称，例如加密邮件DrToniRamos@hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="0aac6-126">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="0aac6-127">在 **"如果应用此规则"中**，选择一个条件，并在必要时输入一个值。</span><span class="sxs-lookup"><span data-stu-id="0aac6-127">In **Apply this rule if**, select a condition, and enter a value if necessary.</span></span> <span data-ttu-id="0aac6-128">例如，若要加密发送到 DrToniRamos@hotmail.com 的邮件：</span><span class="sxs-lookup"><span data-stu-id="0aac6-128">For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="0aac6-129">在“在以下情况应用此规则”中，选择“收件人为”。</span><span class="sxs-lookup"><span data-stu-id="0aac6-129">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="0aac6-130">从联系人列表中选择一个现有名称，或在“检查名称”框中键入一个新的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0aac6-130">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="0aac6-131">若要选择一个现有名称，可以从列表中进行选择，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="0aac6-131">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="0aac6-132">若要输入新名称，请在复选框名称框中键入电子邮件地址，然后选择 **"确定"检查** \> **名称**。</span><span class="sxs-lookup"><span data-stu-id="0aac6-132">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="0aac6-133">若要添加更多条件，请选择 **"更多选项** "，然后选择 **"添加** 条件"，然后从列表中选择。</span><span class="sxs-lookup"><span data-stu-id="0aac6-133">To add more conditions, choose **More options** and then choose **add condition** and select from the list.</span></span>

   <span data-ttu-id="0aac6-134">例如，若要仅在收件人位于组织外部时应用规则，请选择"添加条件"，然后选择"收件人在组织外部 **/** 内部正常 \>  \> **"。**</span><span class="sxs-lookup"><span data-stu-id="0aac6-134">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="0aac6-135">若要使用新的 OME 功能启用加密，请从"执行以下操作"中选择"修改邮件 **安全性**"，然后选择"应用 **Office 365 邮件加密和权限保护"。**</span><span class="sxs-lookup"><span data-stu-id="0aac6-135">To enable encryption using the new OME capabilities, from **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="0aac6-136">从列表中选择 RMS 模板 **，选择"** 保存"，然后选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="0aac6-136">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
  <span data-ttu-id="0aac6-137">模板列表包括所有默认模板和选项，以及你创建供 Office 365 使用的任何自定义模板。</span><span class="sxs-lookup"><span data-stu-id="0aac6-137">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="0aac6-138">如果列表为空，请确保已使用新功能设置 Office 365 邮件加密，如"设置新的 Office [365](set-up-new-message-encryption-capabilities.md)邮件加密功能"中所述。</span><span class="sxs-lookup"><span data-stu-id="0aac6-138">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="0aac6-139">有关默认模板的信息，请参阅 [配置和管理 Azure 信息保护的模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="0aac6-139">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="0aac6-140">有关"不要 **转发"选项的信息** ，请参阅电子邮件 [的"不要转发"选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="0aac6-140">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="0aac6-141">有关仅加密 **选项的信息** ，请参阅电子邮件 [的"仅加密"选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="0aac6-141">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

  <span data-ttu-id="0aac6-142">如果要指定 **其他操作** ，可以选择添加操作。</span><span class="sxs-lookup"><span data-stu-id="0aac6-142">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a><span data-ttu-id="0aac6-143">使用 EAC 更新现有邮件流规则以使用新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="0aac6-143">Use the EAC to update an existing mail flow rule to use the new OME capabilities</span></span>

1. <span data-ttu-id="0aac6-144">在 Web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户登录[Office 365。](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)</span><span class="sxs-lookup"><span data-stu-id="0aac6-144">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="0aac6-145">选择 **"管理"** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="0aac6-145">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="0aac6-146">在 Microsoft 365 管理中心中，选择 **"管理中心** \> **Exchange"。**</span><span class="sxs-lookup"><span data-stu-id="0aac6-146">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="0aac6-147">In the EAC, go to **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="0aac6-147">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

5. <span data-ttu-id="0aac6-148">在邮件流规则列表中，选择要修改的规则以使用新的 OME 功能，然后选择"编辑 ![ 编辑"图标 ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。</span><span class="sxs-lookup"><span data-stu-id="0aac6-148">In the list of mail flow rules, select the rule you want to modify to use the new OME capabilities and then choose **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>

6. <span data-ttu-id="0aac6-149">若要使用新的 OME 功能启用加密，请从"执行以下操作"中选择"修改邮件 **安全性**"，然后选择"应用 **Office 365 邮件加密和权限保护"。**</span><span class="sxs-lookup"><span data-stu-id="0aac6-149">To enable encryption using the new OME capabilities, from **Do the following**, choose **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="0aac6-150">从列表中选择 RMS 模板 **，选择"** 保存"，然后选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="0aac6-150">Select an RMS template from the list, choose **Save** and then choose **OK**.</span></span>

   <span data-ttu-id="0aac6-151">模板列表包括所有默认模板和选项，以及你创建供 Office 365 使用的任何自定义模板。</span><span class="sxs-lookup"><span data-stu-id="0aac6-151">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="0aac6-152">如果列表为空，请确保你已使用新功能设置 Office 365 邮件加密，如在 Azure 信息保护顶部构建的新 [Office 365](set-up-new-message-encryption-capabilities.md)邮件加密功能中所述。</span><span class="sxs-lookup"><span data-stu-id="0aac6-152">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="0aac6-153">有关默认模板的信息，请参阅 [配置和管理 Azure 信息保护的模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="0aac6-153">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="0aac6-154">有关"不要 **转发"选项的信息** ，请参阅电子邮件 [的"不要转发"选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="0aac6-154">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="0aac6-155">有关仅加密 **选项的信息** ，请参阅电子邮件 [的"仅加密"选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="0aac6-155">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="0aac6-156">如果要指定 **其他操作** ，可以选择添加操作。</span><span class="sxs-lookup"><span data-stu-id="0aac6-156">You can choose **add action** if you want to specify another action.</span></span>

7. <span data-ttu-id="0aac6-157">从 **"执行以下操作"列表中**，删除分配给"修改邮件安全性 \> **应用以前版本的 OME"的任何操作**。</span><span class="sxs-lookup"><span data-stu-id="0aac6-157">From the **Do the following** list, remove any actions that are assigned to **Modify the message security** \> **Apply the previous version of OME**.</span></span>

8. <span data-ttu-id="0aac6-158">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="0aac6-158">Choose **Save**.</span></span>

## <a name="create-mail-flow-rules-to-remove-encryption-for-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="0aac6-159">创建邮件流规则以使用新的 OME 功能删除电子邮件的加密</span><span class="sxs-lookup"><span data-stu-id="0aac6-159">Create mail flow rules to remove encryption for email messages with the new OME capabilities</span></span>

<span data-ttu-id="0aac6-160">可以使用 EAC 定义邮件流规则，以使用新的 OME 功能触发删除邮件加密。</span><span class="sxs-lookup"><span data-stu-id="0aac6-160">You can define mail flow rules for triggering remove message encryption with the new OME capabilities by using the EAC.</span></span>

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="0aac6-161">使用 EAC 创建规则以使用新的 OME 功能从电子邮件中删除加密</span><span class="sxs-lookup"><span data-stu-id="0aac6-161">Use the EAC to create a rule to remove encryption from email messages with the new OME capabilities</span></span>

<span data-ttu-id="0aac6-162">可以删除组织可访问的加密。</span><span class="sxs-lookup"><span data-stu-id="0aac6-162">You can remove encryption that is accessible by your organization.</span></span> <span data-ttu-id="0aac6-163">这意味着组织应用的任何加密或任何邮件都只有加密。</span><span class="sxs-lookup"><span data-stu-id="0aac6-163">This means any encryption that is applied by the organization or any mail has encrypt-only.</span></span>

1. <span data-ttu-id="0aac6-164">在 Web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户登录[Office 365。](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)</span><span class="sxs-lookup"><span data-stu-id="0aac6-164">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="0aac6-165">选择 **"管理"** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="0aac6-165">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="0aac6-166">在 Microsoft 365 管理中心中，选择 **"管理中心** \> **Exchange"。**</span><span class="sxs-lookup"><span data-stu-id="0aac6-166">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="0aac6-167">在 EAC 中，转到"**邮件流** 规则 \> "，然后选择 **"新建**" ![ 图标 ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **"创建新规则"。**</span><span class="sxs-lookup"><span data-stu-id="0aac6-167">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="0aac6-168">有关使用 EAC 的信息，请参阅 [Exchange Online 中的 Exchange 管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="0aac6-168">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="0aac6-169">在 **"名称**"中，键入规则的名称，例如从传出邮件中删除加密。</span><span class="sxs-lookup"><span data-stu-id="0aac6-169">In **Name**, type a name for the rule, such as Remove encryption from outgoing mail.</span></span>

6. <span data-ttu-id="0aac6-170">在 **"如果应用此规则"中**，选择应从邮件中删除加密的条件。</span><span class="sxs-lookup"><span data-stu-id="0aac6-170">In **Apply this rule if**, select the conditions where encryption should be removed from messages.</span></span> <span data-ttu-id="0aac6-171">添加 **收件人位于组织** 外部 \> **或\*\*\*\*组织内部**。</span><span class="sxs-lookup"><span data-stu-id="0aac6-171">Add **The recipient is located** \> **Outside the organization** or **Inside the organization**.</span></span>

7. <span data-ttu-id="0aac6-172">在 **"执行以下操作"中**，**选择"修改邮件安全** \> **删除 Office 365 邮件加密和权限保护"。**</span><span class="sxs-lookup"><span data-stu-id="0aac6-172">In **Do the following**, select **Modify the message security** \> **Remove Office 365 Message Encryption and rights protection**.</span></span>

8. <span data-ttu-id="0aac6-173">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="0aac6-173">Select **Save**.</span></span>

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a><span data-ttu-id="0aac6-174">创建没有新功能的 Office 365 邮件加密的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="0aac6-174">Create mail flow rules for Office 365 Message Encryption without the new capabilities</span></span>

<span data-ttu-id="0aac6-175">如果尚未将组织移动到新的 OME 功能，Microsoft 建议在组织合理时制定移动到新 OME 功能的计划。</span><span class="sxs-lookup"><span data-stu-id="0aac6-175">If you haven't yet moved your organization to the new OME capabilities, Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="0aac6-176">有关说明，请参阅设置基于 Azure 信息保护构建的新 [Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="0aac6-176">For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="0aac6-177">否则， [请参阅定义不使用新 OME 功能的 Office 365](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities)邮件加密的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="0aac6-177">Otherwise, see [Defining mail flow rules for Office 365 Message Encryption that don't use the new OME capabilities](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0aac6-178">相关主题</span><span class="sxs-lookup"><span data-stu-id="0aac6-178">Related Topics</span></span>

[<span data-ttu-id="0aac6-179">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="0aac6-179">Encryption in Office 365</span></span>](encryption.md)

[<span data-ttu-id="0aac6-180">设置全新的 Office 365 邮件加密功能</span><span class="sxs-lookup"><span data-stu-id="0aac6-180">Set up new Office 365 Message Encryption capabilities</span></span>](set-up-new-message-encryption-capabilities.md)

[<span data-ttu-id="0aac6-181">将品牌添加到加密邮件</span><span class="sxs-lookup"><span data-stu-id="0aac6-181">Add branding to encrypted messages</span></span>](add-your-organization-brand-to-encrypted-messages.md)

[<span data-ttu-id="0aac6-182">Exchange Online 中的邮件流规则（传输规则）</span><span class="sxs-lookup"><span data-stu-id="0aac6-182">Mail flow rules (transport rules) in Exchange Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[<span data-ttu-id="0aac6-183">Exchange Online Protection (传输) 规则</span><span class="sxs-lookup"><span data-stu-id="0aac6-183">Mail flow rules (transport rules) in Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506708)
