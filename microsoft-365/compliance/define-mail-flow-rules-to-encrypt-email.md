---
title: 定义用于加密电子邮件的邮件流规则
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
description: 管理员可以了解如何创建邮件流规则 (传输规则) 加密和解密邮件Office 365 邮件加密。
ms.openlocfilehash: 5274c2368de9825bd0568b7abd4e060e22fe9c70
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430452"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a><span data-ttu-id="956d8-103">定义用于加密电子邮件的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="956d8-103">Define mail flow rules to encrypt email messages</span></span>

<span data-ttu-id="956d8-104">作为管理邮件Exchange Online，您可以创建邮件流规则 (也称为传输规则) 传输规则，以帮助保护您发送和接收的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="956d8-104">As an administrator that manages Exchange Online, you can create mail flow rules (also known as transport rules) to help protect email messages you send and receive.</span></span> <span data-ttu-id="956d8-105">您可以设置规则来加密任何传出电子邮件，并从来自组织内部的加密邮件或对从组织发送的加密邮件的答复中删除加密。</span><span class="sxs-lookup"><span data-stu-id="956d8-105">You can set up rules to encrypt any outgoing email messages and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> <span data-ttu-id="956d8-106">可以使用 EAC Exchange管理 (中心) 或Exchange Online PowerShell 创建这些规则。</span><span class="sxs-lookup"><span data-stu-id="956d8-106">You can use the Exchange admin center (EAC) or Exchange Online PowerShell to create these rules.</span></span> <span data-ttu-id="956d8-107">除了整体的加密规则，您还可以针对最终用户选择启用或禁用个人邮件加密选项。</span><span class="sxs-lookup"><span data-stu-id="956d8-107">In addition to overall encryption rules, you can also choose to enable or disable individual message encryption options for end users.</span></span>

<span data-ttu-id="956d8-108">无法加密来自组织外部发件人的入站邮件。</span><span class="sxs-lookup"><span data-stu-id="956d8-108">You can't encrypt inbound mail from senders outside of your organization.</span></span>

<span data-ttu-id="956d8-109">如果最近从 Active Directory RMS 迁移到 Azure 信息保护，则需要查看现有的邮件流规则，以确保它们继续在新环境中工作。</span><span class="sxs-lookup"><span data-stu-id="956d8-109">If you recently migrated from Active Directory RMS to Azure Information Protection, you'll need to review your existing mail flow rules to ensure that they continue to work in your new environment.</span></span> <span data-ttu-id="956d8-110">此外，如果你想要利用 Azure 信息保护Office 365 邮件加密 (OME) 功能，则需要更新现有的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="956d8-110">Also, if you want to take advantage of the new Office 365 Message Encryption (OME) capabilities available to you through Azure Information Protection, you need to update your existing mail flow rules.</span></span> <span data-ttu-id="956d8-111">否则，您的用户将继续接收使用以前的 HTML 附件格式的加密邮件，而不是新的无缝 OME 体验。</span><span class="sxs-lookup"><span data-stu-id="956d8-111">Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience.</span></span> <span data-ttu-id="956d8-112">如果尚未设置 OME，请参阅设置新的 Office 365 邮件加密[功能](set-up-new-message-encryption-capabilities.md)了解相关信息。</span><span class="sxs-lookup"><span data-stu-id="956d8-112">If you haven't set up OME yet, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md) for information.</span></span>

<span data-ttu-id="956d8-113">有关组成邮件流规则的组件以及邮件流规则如何工作的信息，请参阅邮件流规则 ([中的](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)) 规则Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="956d8-113">For information about the components that make up mail flow rules and how mail flow rules work, see [Mail flow rules (transport rules) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span> <span data-ttu-id="956d8-114">有关邮件流规则如何与 Azure 信息保护一起运行的其他信息，请参阅为 Azure 信息Exchange Online配置[邮件流规则](/azure/information-protection/deploy-use/configure-exo-rules)。</span><span class="sxs-lookup"><span data-stu-id="956d8-114">For additional information about how mail flow rules work with Azure Information Protection, see [Configuring Exchange Online mail flow rules for Azure Information Protection labels](/azure/information-protection/deploy-use/configure-exo-rules).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="956d8-115">对于混合Exchange环境，只有当电子邮件通过 OME 路由时，本地用户才能使用 OME 发送和接收Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="956d8-115">For hybrid Exchange environments, on-premises users can send and receive encrypted mail using OME only if email is routed through Exchange Online.</span></span> <span data-ttu-id="956d8-116">若要在混合 Exchange 环境中配置 OME，您需要首先使用混合配置[](/Exchange/exchange-hybrid)向导配置混合，然后将邮件配置为从[Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server)流向您的电子邮件服务器，然后将邮件配置为从您的电子邮件服务器流向[Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。</span><span class="sxs-lookup"><span data-stu-id="956d8-116">To configure OME in a hybrid Exchange environment, you need to first [configure hybrid using the Hybrid Configuration wizard](/Exchange/exchange-hybrid) and then [configure mail to flow from Office 365 to your email server](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server) and [configure mail to flow from your email server to Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365).</span></span> <span data-ttu-id="956d8-117">将邮件配置为通过 Office 365 后，可以使用本指南为 OME 配置邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="956d8-117">Once you've configured mail to flow through Office 365, then you can configure mail flow rules for OME by using this guidance.</span></span>

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="956d8-118">创建邮件流规则以使用新的 OME 功能加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="956d8-118">Create mail flow rules to encrypt email messages with the new OME capabilities</span></span>

<span data-ttu-id="956d8-119">可以使用 EAC 定义邮件流规则，以使用新的 OME 功能触发邮件加密。</span><span class="sxs-lookup"><span data-stu-id="956d8-119">You can define mail flow rules for triggering message encryption with the new OME capabilities by using the EAC.</span></span>

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="956d8-120">使用 EAC 创建使用新的 OME 功能加密电子邮件的规则</span><span class="sxs-lookup"><span data-stu-id="956d8-120">Use the EAC to create a rule for encrypting email messages with the new OME capabilities</span></span>

1. <span data-ttu-id="956d8-121">在 Web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户登录[Office 365。](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)</span><span class="sxs-lookup"><span data-stu-id="956d8-121">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="956d8-122">选择" **管理"** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="956d8-122">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="956d8-123">In the Microsoft 365 管理中心， choose **Admin centers** \> **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="956d8-123">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="956d8-124">在 EAC 中，**转到"邮件** 流 \> ""规则"，然后选择"**新建**" ![ 图标 ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **"创建新规则"。**</span><span class="sxs-lookup"><span data-stu-id="956d8-124">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="956d8-125">有关使用 EAC 的信息，请参阅 Exchange[中的管理Exchange Online。](/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="956d8-125">For more information about using the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="956d8-126">在 **"** 名称"中，键入规则的名称，如加密邮件 DrToniRamos@hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="956d8-126">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="956d8-127">在 **"在应用此规则的条件**"中，选择一个条件，并在必要时输入一个值。</span><span class="sxs-lookup"><span data-stu-id="956d8-127">In **Apply this rule if**, select a condition, and enter a value if necessary.</span></span> <span data-ttu-id="956d8-128">例如，若要加密发送到 DrToniRamos@hotmail.com 的邮件：</span><span class="sxs-lookup"><span data-stu-id="956d8-128">For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="956d8-129">在“在以下情况应用此规则”中，选择“收件人为”。</span><span class="sxs-lookup"><span data-stu-id="956d8-129">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="956d8-130">从联系人列表中选择一个现有名称，或在“检查名称”框中键入一个新的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="956d8-130">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="956d8-131">若要选择一个现有名称，可以从列表中进行选择，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="956d8-131">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="956d8-132">若要输入新名称，请在"检查名称"框中键入电子邮件地址，然后选择"**检查名称** \> **""确定"。**</span><span class="sxs-lookup"><span data-stu-id="956d8-132">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="956d8-133">若要添加更多条件，请选择" **更多选项** "，然后选择" **添加** 条件"，然后从列表中选择。</span><span class="sxs-lookup"><span data-stu-id="956d8-133">To add more conditions, choose **More options** and then choose **add condition** and select from the list.</span></span>

   <span data-ttu-id="956d8-134">例如，若要仅在收件人在组织外部时应用规则，请选择"添加条件"，然后选择"收件人在组织外部 **/** 内部 \> **""** 确定 \> **"。**</span><span class="sxs-lookup"><span data-stu-id="956d8-134">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="956d8-135">若要使用新的 OME 功能启用加密，请从"执行以下操作"中选择"修改邮件安全性"，然后选择"应用Office 365 邮件加密 **权限保护"。**</span><span class="sxs-lookup"><span data-stu-id="956d8-135">To enable encryption using the new OME capabilities, from **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="956d8-136">从列表中选择 RMS 模板，选择"保存 **"，** 然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="956d8-136">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
  <span data-ttu-id="956d8-137">模板列表包括所有默认模板和选项，以及已创建供用户Office 365。</span><span class="sxs-lookup"><span data-stu-id="956d8-137">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="956d8-138">如果列表为空，请确保你已Office 365 邮件加密设置新功能，如设置新的Office 365 邮件加密[功能中所述](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="956d8-138">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="956d8-139">有关默认模板的信息，请参阅 [配置和管理 Azure 信息保护的模板](/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="956d8-139">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="956d8-140">有关"不要转发 **"选项的信息** ，请参阅电子邮件 [的"不要转发"选项](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="956d8-140">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="956d8-141">有关仅 **加密选项的信息** ，请参阅电子邮件的仅 [加密选项](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="956d8-141">For information about the **encrypt-only** option, see [Encrypt-only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

  <span data-ttu-id="956d8-142">如果要指定 **其他操作** ，可以选择"添加操作"。</span><span class="sxs-lookup"><span data-stu-id="956d8-142">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a><span data-ttu-id="956d8-143">使用 EAC 更新现有邮件流规则以使用新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="956d8-143">Use the EAC to update an existing mail flow rule to use the new OME capabilities</span></span>

1. <span data-ttu-id="956d8-144">在 Web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户登录[Office 365。](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)</span><span class="sxs-lookup"><span data-stu-id="956d8-144">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="956d8-145">选择" **管理"** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="956d8-145">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="956d8-146">In the Microsoft 365 管理中心， choose **Admin centers** \> **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="956d8-146">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="956d8-147">In the EAC, go to **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="956d8-147">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

5. <span data-ttu-id="956d8-148">在邮件流规则列表中，选择要修改的规则以使用新的 OME 功能，然后选择"编辑 **编辑** ![ "图标 ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。</span><span class="sxs-lookup"><span data-stu-id="956d8-148">In the list of mail flow rules, select the rule you want to modify to use the new OME capabilities and then choose **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>

6. <span data-ttu-id="956d8-149">若要使用新的 OME 功能启用加密，请从"执行以下操作"中选择"修改邮件安全性"，然后选择"应用Office 365 邮件加密 **和权限保护"。**</span><span class="sxs-lookup"><span data-stu-id="956d8-149">To enable encryption using the new OME capabilities, from **Do the following**, choose **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="956d8-150">从列表中选择 RMS 模板，选择"**保存"，** 然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="956d8-150">Select an RMS template from the list, choose **Save** and then choose **OK**.</span></span>

   <span data-ttu-id="956d8-151">模板列表包括所有默认模板和选项，以及已创建供用户Office 365。</span><span class="sxs-lookup"><span data-stu-id="956d8-151">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="956d8-152">如果列表为空，请确保你已Office 365 邮件加密设置新功能，如设置基于 Azure 信息保护构建的新 Office 365 邮件加密[功能中所述](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="956d8-152">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="956d8-153">有关默认模板的信息，请参阅 [配置和管理 Azure 信息保护的模板](/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="956d8-153">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="956d8-154">有关"不要转发"选项的信息，请参阅电子邮件 [的"不要转发"选项](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="956d8-154">For information about the Do Not Forward option, see [Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="956d8-155">有关仅加密选项的信息，请参阅加密 [仅电子邮件选项](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="956d8-155">For information about the encrypt-only option, see [Encrypt Only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="956d8-156">如果要指定 **其他操作** ，可以选择"添加操作"。</span><span class="sxs-lookup"><span data-stu-id="956d8-156">You can choose **add action** if you want to specify another action.</span></span>

7. <span data-ttu-id="956d8-157">从 **"执行以下操作"列表中**，删除分配给"修改邮件安全性""应用以前版本的 \> **OME"的任何操作**。</span><span class="sxs-lookup"><span data-stu-id="956d8-157">From the **Do the following** list, remove any actions that are assigned to **Modify the message security** \> **Apply the previous version of OME**.</span></span>

8. <span data-ttu-id="956d8-158">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="956d8-158">Choose **Save**.</span></span>

## <a name="create-mail-flow-rules-to-remove-encryption-for-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="956d8-159">创建邮件流规则以使用新的 OME 功能删除电子邮件的加密</span><span class="sxs-lookup"><span data-stu-id="956d8-159">Create mail flow rules to remove encryption for email messages with the new OME capabilities</span></span>

<span data-ttu-id="956d8-160">可以使用 EAC 定义邮件流规则，以使用新的 OME 功能触发删除邮件加密。</span><span class="sxs-lookup"><span data-stu-id="956d8-160">You can define mail flow rules for triggering remove message encryption with the new OME capabilities by using the EAC.</span></span>

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="956d8-161">使用 EAC 创建规则以使用新的 OME 功能从电子邮件中删除加密</span><span class="sxs-lookup"><span data-stu-id="956d8-161">Use the EAC to create a rule to remove encryption from email messages with the new OME capabilities</span></span>

<span data-ttu-id="956d8-162">可以删除组织应用的加密。</span><span class="sxs-lookup"><span data-stu-id="956d8-162">You can remove encryption that is applied by your organization.</span></span>

1. <span data-ttu-id="956d8-163">在 Web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户登录[Office 365。](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)</span><span class="sxs-lookup"><span data-stu-id="956d8-163">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="956d8-164">选择" **管理"** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="956d8-164">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="956d8-165">In the Microsoft 365 管理中心， choose **Admin centers** \> **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="956d8-165">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="956d8-166">在 EAC 中，**转到"邮件** 流 \> ""规则"，然后选择"**新建**" ![ 图标 ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **"创建新规则"。**</span><span class="sxs-lookup"><span data-stu-id="956d8-166">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="956d8-167">有关使用 EAC 的信息，请参阅 Exchange[中的管理Exchange Online。](/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="956d8-167">For more information about using the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="956d8-168">在 **"** 名称"中，键入规则的名称，例如"从传出邮件中删除加密"。</span><span class="sxs-lookup"><span data-stu-id="956d8-168">In **Name**, type a name for the rule, such as Remove encryption from outgoing mail.</span></span>

6. <span data-ttu-id="956d8-169">在 **"在应用此规则的条件**"中，选择应从邮件中删除加密的条件。</span><span class="sxs-lookup"><span data-stu-id="956d8-169">In **Apply this rule if**, select the conditions where encryption should be removed from messages.</span></span> <span data-ttu-id="956d8-170">添加 **发件人位于用于发送邮件** 的组织内部，或收件人位于用于接收邮件 \>  \> 的组织内部。</span><span class="sxs-lookup"><span data-stu-id="956d8-170">Add **The sender is located** \> **Inside the organization** for sending mail _or_ **The recipient is located** \> **Inside the organization** for receiving mail.</span></span>

7. <span data-ttu-id="956d8-171">在 **"执行以下操作"中\*\*\*\*，选择"修改邮件安全** \> **""删除Office 365 邮件加密和权限保护"。**</span><span class="sxs-lookup"><span data-stu-id="956d8-171">In **Do the following**, select **Modify the message security** \> **Remove Office 365 Message Encryption and rights protection**.</span></span>

8. <span data-ttu-id="956d8-172">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="956d8-172">Select **Save**.</span></span>

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a><span data-ttu-id="956d8-173">为没有新功能Office 365 邮件加密邮件流规则</span><span class="sxs-lookup"><span data-stu-id="956d8-173">Create mail flow rules for Office 365 Message Encryption without the new capabilities</span></span>

<span data-ttu-id="956d8-174">如果你尚未将组织移动到新的 OME 功能，Microsoft 建议你制定一个计划，在组织合理时尽快移动到新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="956d8-174">If you haven't yet moved your organization to the new OME capabilities, Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="956d8-175">有关说明，请参阅[设置基于](set-up-new-message-encryption-capabilities.md)Azure Office 365 邮件加密构建的新功能。</span><span class="sxs-lookup"><span data-stu-id="956d8-175">For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="956d8-176">否则，请参阅为不使用新[OME 功能Office 365 邮件加密定义邮件流规则](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="956d8-176">Otherwise, see [Defining mail flow rules for Office 365 Message Encryption that don't use the new OME capabilities](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities).</span></span>

## <a name="related-topics"></a><span data-ttu-id="956d8-177">相关主题</span><span class="sxs-lookup"><span data-stu-id="956d8-177">Related Topics</span></span>

[<span data-ttu-id="956d8-178">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="956d8-178">Encryption in Office 365</span></span>](encryption.md)

[<span data-ttu-id="956d8-179">设置全新的 Office 365 邮件加密功能</span><span class="sxs-lookup"><span data-stu-id="956d8-179">Set up new Office 365 Message Encryption capabilities</span></span>](set-up-new-message-encryption-capabilities.md)

[<span data-ttu-id="956d8-180">将品牌添加到加密邮件</span><span class="sxs-lookup"><span data-stu-id="956d8-180">Add branding to encrypted messages</span></span>](add-your-organization-brand-to-encrypted-messages.md)

[<span data-ttu-id="956d8-181">Exchange Online 中的邮件流规则（传输规则）</span><span class="sxs-lookup"><span data-stu-id="956d8-181">Mail flow rules (transport rules) in Exchange Online</span></span>](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
