---
title: 定义用于加密 Office 365 中的电子邮件的邮件流规则
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
description: 管理员可以了解如何创建邮件流规则（传输规则），以使用 Office 365 邮件加密对邮件进行加密和解密。
ms.openlocfilehash: 17a04941d7132dbe50f8a79ec3b8879b300b414e
ms.sourcegitcommit: fa9d24aae563727fc8d67c4054c8d307a1a540ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "38685048"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a><span data-ttu-id="18094-103">定义用于加密 Office 365 中的电子邮件的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="18094-103">Define mail flow rules to encrypt email messages in Office 365</span></span>

<span data-ttu-id="18094-104">作为 Office 365 全局管理员，您可以创建邮件流规则（也称为传输规则），以帮助保护您发送和接收的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="18094-104">As an Office 365 global administrator, you can create mail flow rules (also known as transport rules) to help protect email messages you send and receive.</span></span> <span data-ttu-id="18094-105">您可以设置规则来加密任何传出的电子邮件，并删除来自组织内部或从组织发送的加密邮件的答复的加密邮件的加密。</span><span class="sxs-lookup"><span data-stu-id="18094-105">You can set up rules to encrypt any outgoing email messages and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> <span data-ttu-id="18094-106">您可以使用 Exchange 管理中心（EAC）或 Exchange Online PowerShell 创建这些规则。</span><span class="sxs-lookup"><span data-stu-id="18094-106">You can use the Exchange admin center (EAC) or Exchange Online PowerShell to create these rules.</span></span> <span data-ttu-id="18094-107">除了整体的加密规则，你还可以针对最终用户选择启用或禁用单个邮件加密选项。</span><span class="sxs-lookup"><span data-stu-id="18094-107">In addition to overall encryption rules, you can also choose to enable or disable individual message encryption options for end-users.</span></span>

<span data-ttu-id="18094-108">如果你最近从 AD RMS 迁移到 Azure 信息保护，你将需要查看现有的邮件流规则，以确保它们可以在你的新环境中继续工作。</span><span class="sxs-lookup"><span data-stu-id="18094-108">If you recently migrated from AD RMS to Azure Information Protection, you'll need to review your existing mail flow rules to ensure that they continue to work in your new environment.</span></span> <span data-ttu-id="18094-109">此外，如果您想利用新的 Office 365 邮件加密（OME）功能通过 Azure 信息保护来使用，则需要更新现有的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="18094-109">Additionally, if you want to take advantage of the new Office 365 Message Encryption (OME) capabilities available to you through Azure Information Protection, you need to update your existing mail flow rules.</span></span> <span data-ttu-id="18094-110">否则，您的用户将继续接收使用以前的 HTML 附件格式的加密邮件，而不是新的无缝 OME 体验。</span><span class="sxs-lookup"><span data-stu-id="18094-110">Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience.</span></span> <span data-ttu-id="18094-111">如果尚未设置 OME，请参阅为信息[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="18094-111">If you haven't set up OME yet, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md) for information.</span></span>

<span data-ttu-id="18094-112">有关组成邮件流规则的组件和邮件流规则的工作方式的信息，请参阅[Exchange Online 中的邮件流规则（传输规则）](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="18094-112">For information about the components that make up mail flow rules and how mail flow rules work, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span> <span data-ttu-id="18094-113">有关邮件流规则如何使用 Azure 信息保护的其他信息，请参阅[为 Azure 信息保护标签配置 Exchange Online 邮件流规则](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)。</span><span class="sxs-lookup"><span data-stu-id="18094-113">For additional information about how mail flow rules work with Azure Information Protection, see [Configuring Exchange Online mail flow rules for Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18094-114">对于混合 Exchange 环境，只有在通过 Exchange Online 路由电子邮件的情况下，本地用户才能使用 OME 发送加密邮件。</span><span class="sxs-lookup"><span data-stu-id="18094-114">For hybrid Exchange environments, on-premises users can send encrypted mail using OME only if email is routed through Exchange Online.</span></span> <span data-ttu-id="18094-115">若要在混合 Exchange 环境中配置 OME，需要先[使用 "混合配置" 向导配置混合](https://docs.microsoft.com/Exchange/exchange-hybrid)，然后[将邮件配置为从您的电子邮件服务器传递到 Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。</span><span class="sxs-lookup"><span data-stu-id="18094-115">To configure OME in a hybrid Exchange environment, you need to first [configure hybrid using the Hybrid Configuration wizard](https://docs.microsoft.com/Exchange/exchange-hybrid) and then [configure mail to flow from your email server to Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365).</span></span> <span data-ttu-id="18094-116">将邮件配置为通过 Office 365 传输之后，可以使用本指南配置 OME 的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="18094-116">Once you've configured mail to flow through Office 365, then you can configure mail flow rules for OME by using this guidance.</span></span>

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="18094-117">创建邮件流规则，以使用新的 OME 功能对电子邮件进行加密</span><span class="sxs-lookup"><span data-stu-id="18094-117">Create mail flow rules to encrypt email messages with the new OME capabilities</span></span>

<span data-ttu-id="18094-118">您可以使用 EAC 定义邮件流规则，以使用新的 OME 功能触发邮件加密。</span><span class="sxs-lookup"><span data-stu-id="18094-118">You can define mail flow rules for triggering message encryption with the new OME capabilities by using the EAC.</span></span>

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="18094-119">使用 EAC 创建使用新的 OME 功能对电子邮件进行加密的规则</span><span class="sxs-lookup"><span data-stu-id="18094-119">Use the EAC to create a rule for encrypting email messages with the new OME capabilities</span></span>

1. <span data-ttu-id="18094-120">在 web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="18094-120">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="18094-121">选择 "**管理**" 磁贴。</span><span class="sxs-lookup"><span data-stu-id="18094-121">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="18094-122">在 Microsoft 365 管理中心，选择 "**管理中心** \> " " **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="18094-122">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="18094-123">在 EAC 中，转到 "**邮件流** \> **规则**"，然后选择 "**新建** ![" 图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **创建新规则**。</span><span class="sxs-lookup"><span data-stu-id="18094-123">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="18094-124">有关使用 EAC 的详细信息，请参阅 exchange [Online 中的 exchange 管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="18094-124">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="18094-125">在 "**名称**" 中，键入规则的名称，例如 "为 DrToniRamos@hotmail.com 加密邮件"。</span><span class="sxs-lookup"><span data-stu-id="18094-125">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="18094-p106">在“在以下情况应用此规则”\*\*\*\* 中，选择一个条件，并根据需要输入值。例如，若要加密发送到 DrToniRamos@hotmail.com 的邮件：</span><span class="sxs-lookup"><span data-stu-id="18094-p106">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="18094-128">在“在以下情况应用此规则”\*\*\*\* 中，选择“收件人为”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18094-128">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="18094-129">从联系人列表中选择一个现有名称，或在“检查名称”\*\*\*\* 框中键入一个新的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="18094-129">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="18094-130">若要选择一个现有名称，可以从列表中进行选择，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18094-130">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="18094-131">若要输入新名称，请在 "**检查名称**" 框中键入电子邮件地址，然后选择 "**检查名称** \> **" "确定"**。</span><span class="sxs-lookup"><span data-stu-id="18094-131">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="18094-132">若要添加更多条件，请选择 "**更多选项**"，然后选择 "**添加条件**"，然后从列表中选择。</span><span class="sxs-lookup"><span data-stu-id="18094-132">To add more conditions, choose **More options** and then choose **add condition** and select from the list.</span></span>

   <span data-ttu-id="18094-133">例如，若要仅在收件人在组织外部时应用规则，请选择 "**添加条件**"，然后选择 "在**组织** \>外部 **/内部的收件人是外部/内部** \> **"**。</span><span class="sxs-lookup"><span data-stu-id="18094-133">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="18094-134">若要使用新的 OME 功能启用加密，请从**执行以下操作**，选择 "**修改邮件安全性"** ，然后选择 "**应用 Office 365 邮件加密和权限保护**"。</span><span class="sxs-lookup"><span data-stu-id="18094-134">To enable encryption using the new OME capabilities, from **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="18094-135">从列表中选择一个 RMS 模板，选择 "**保存**"，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="18094-135">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
  <span data-ttu-id="18094-136">模板列表包含所有默认模板和选项，以及您创建的用于 Office 365 的任何自定义模板。</span><span class="sxs-lookup"><span data-stu-id="18094-136">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="18094-137">如果列表为空，请确保已使用新功能设置了 Office 365 邮件加密，如[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="18094-137">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="18094-138">有关默认模板的信息，请参阅[配置和管理 Azure 信息保护的模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="18094-138">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="18094-139">有关 "**不要转发**" 选项的信息，请参阅[电子邮件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)的 "不要转发" 选项。</span><span class="sxs-lookup"><span data-stu-id="18094-139">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="18094-140">有关**仅加密**选项的信息，请参阅[仅加密电子邮件选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="18094-140">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

  <span data-ttu-id="18094-141">如果要指定另一个操作，可以选择 "**添加操作**"。</span><span class="sxs-lookup"><span data-stu-id="18094-141">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a><span data-ttu-id="18094-142">使用 EAC 更新现有的邮件流规则，以使用新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="18094-142">Use the EAC to update an existing mail flow rule to use the new OME capabilities</span></span>

1. <span data-ttu-id="18094-143">在 web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="18094-143">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="18094-144">选择 "**管理**" 磁贴。</span><span class="sxs-lookup"><span data-stu-id="18094-144">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="18094-145">在 Microsoft 365 管理中心，选择 "**管理中心** \> " " **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="18094-145">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="18094-146">In the EAC, go to **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="18094-146">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

5. <span data-ttu-id="18094-147">在邮件流规则的列表中，选择要修改的规则以使用新的 OME 功能，然后选择 "**编辑** ![" "编辑](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)" 图标。</span><span class="sxs-lookup"><span data-stu-id="18094-147">In the list of mail flow rules, select the rule you want to modify to use the new OME capabilities and then choose **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>

6. <span data-ttu-id="18094-148">若要使用新的 OME 功能启用加密，请从**执行以下操作**，选择 "**修改邮件安全性"** ，然后选择 "**应用 Office 365 邮件加密和权限保护**"。</span><span class="sxs-lookup"><span data-stu-id="18094-148">To enable encryption using the new OME capabilities, from **Do the following**, choose **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="18094-149">从列表中选择一个 RMS 模板，选择 "**保存**"，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="18094-149">Select an RMS template from the list, choose **Save** and then choose **OK**.</span></span>

   <span data-ttu-id="18094-150">模板列表包含所有默认模板和选项，以及您创建的用于 Office 365 的任何自定义模板。</span><span class="sxs-lookup"><span data-stu-id="18094-150">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="18094-151">如果列表为空，请确保已使用新功能设置了 Office 365 邮件加密，如[设置新的 office 365 邮件加密功能（基于 Azure 信息保护的基础之上](set-up-new-message-encryption-capabilities.md)）中所述。</span><span class="sxs-lookup"><span data-stu-id="18094-151">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="18094-152">有关默认模板的信息，请参阅[配置和管理 Azure 信息保护的模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="18094-152">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="18094-153">有关 "**不要转发**" 选项的信息，请参阅[电子邮件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)的 "不要转发" 选项。</span><span class="sxs-lookup"><span data-stu-id="18094-153">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="18094-154">有关**仅加密**选项的信息，请参阅[仅加密电子邮件选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="18094-154">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="18094-155">如果要指定另一个操作，可以选择 "**添加操作**"。</span><span class="sxs-lookup"><span data-stu-id="18094-155">You can choose **add action** if you want to specify another action.</span></span>

7. <span data-ttu-id="18094-156">从 "**执行以下**操作" 列表中，删除为**修改邮件安全性** \>而分配的所有操作**应用早期版本的 OME**。</span><span class="sxs-lookup"><span data-stu-id="18094-156">From the **Do the following** list, remove any actions that are assigned to **Modify the message security** \> **Apply the previous version of OME**.</span></span>

8. <span data-ttu-id="18094-157">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="18094-157">Choose **Save**.</span></span>

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a><span data-ttu-id="18094-158">创建不带新功能的 Office 365 邮件加密的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="18094-158">Create mail flow rules for Office 365 Message Encryption without the new capabilities</span></span>

<span data-ttu-id="18094-159">如果您尚未将 Office 365 组织移动到新的 OME 功能，请使用这些任务定义邮件流规则，以对组织的邮件进行加密。</span><span class="sxs-lookup"><span data-stu-id="18094-159">If you haven't yet moved your Office 365 organization to the new OME capabilities, use these tasks to define mail flow rules to encrypt messages for your organization.</span></span> <span data-ttu-id="18094-160">Microsoft 建议您制定一个计划，尽快移动到新的 OME 功能，因为它对您的组织合理。</span><span class="sxs-lookup"><span data-stu-id="18094-160">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="18094-161">有关说明，请参阅[设置基于 Azure 信息保护基础构建的新 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="18094-161">For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span>

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="18094-162">使用 EAC 创建邮件流规则，以在不使用新的 OME 功能的情况下加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="18094-162">Use the EAC to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="18094-163">在 web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="18094-163">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="18094-164">选择 "**管理**" 磁贴。</span><span class="sxs-lookup"><span data-stu-id="18094-164">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="18094-165">在 Microsoft 365 管理中心，选择 "**管理中心** \> " " **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="18094-165">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="18094-166">在 EAC 中，转到 "**邮件流** \> **规则**"，然后选择 "**新建** ![" 图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **创建新规则**。</span><span class="sxs-lookup"><span data-stu-id="18094-166">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="18094-167">有关使用 EAC 的详细信息，请参阅 exchange [Online 中的 exchange 管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="18094-167">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="18094-168">在 "**名称**" 中，键入规则的名称，例如 "为 DrToniRamos@hotmail.com 加密邮件"。</span><span class="sxs-lookup"><span data-stu-id="18094-168">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="18094-p113">在“在以下情况应用此规则”\*\*\*\* 中，选择一个条件，并根据需要输入值。例如，若要加密发送到 DrToniRamos@hotmail.com 的邮件：</span><span class="sxs-lookup"><span data-stu-id="18094-p113">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="18094-171">在“在以下情况应用此规则”\*\*\*\* 中，选择“收件人为”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18094-171">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="18094-172">从联系人列表中选择一个现有名称，或在“检查名称”\*\*\*\* 框中键入一个新的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="18094-172">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="18094-173">若要选择一个现有名称，可以从列表中进行选择，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="18094-173">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="18094-174">若要输入新名称，请在 "**检查名称**" 框中键入电子邮件地址，然后选择 "**检查名称** \> **" "确定"**。</span><span class="sxs-lookup"><span data-stu-id="18094-174">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="18094-175">若要添加更多条件，请选择 "**更多选项**"，然后选择 "**添加条件**"，然后从列表中选择。</span><span class="sxs-lookup"><span data-stu-id="18094-175">To add more conditions, choose **More options** and then select **add condition** and select from the list.</span></span>

   <span data-ttu-id="18094-176">例如，若要仅在收件人在组织外部时应用规则，请选择 "**添加条件**"，然后选择 "在**组织** \>外部 **/内部的收件人是外部/内部** \> **"**。</span><span class="sxs-lookup"><span data-stu-id="18094-176">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="18094-177">若要在不使用新的 OME 功能的情况下启用加密，请在**执行以下操作**中，选择 **"修改邮件安全性** \> **应用以前版本的 OME**"，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="18094-177">To enable encryption without using the new OME capabilities, in **Do the following**, select **Modify the message security** \> **Apply the previous version of OME**, and then choose **Save**.</span></span>

  <span data-ttu-id="18094-178">如果您收到未启用 IRM 许可的错误，则您还没有为您的组织设置 OME。</span><span class="sxs-lookup"><span data-stu-id="18094-178">If you receive an error that IRM licensing isn't enabled, then you haven't set up OME for your organization yet.</span></span> <span data-ttu-id="18094-179">如果想要立即设置 OME，则必须将其设置为使用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="18094-179">If you'd like to set up OME now, you must set it up to use the new OME capabilities.</span></span> <span data-ttu-id="18094-180">有关详细信息，请参阅建立[基于 Azure 信息保护基础之上的新 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="18094-180">For information, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="18094-181">Microsoft 不再支持在没有新功能的情况下设置新的 OME 部署。</span><span class="sxs-lookup"><span data-stu-id="18094-181">Microsoft no longer supports setting up new deployments of OME without the new capabilities.</span></span>

  <span data-ttu-id="18094-182">如果要指定另一个操作，可以选择 "**添加操作**"。</span><span class="sxs-lookup"><span data-stu-id="18094-182">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="18094-183">使用 Exchange Online PowerShell 创建邮件流规则，以在不提供新 OME 功能的情况下加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="18094-183">Use Exchange Online PowerShell to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="18094-184">连接到 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="18094-184">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="18094-185">有关详细信息，请参阅[使用远程 PowerShell 连接到 Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="18094-185">For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="18094-186">使用**new-transportrule** cmdlet 创建一个规则，并将_ApplyOME_参数设置为`$true`。</span><span class="sxs-lookup"><span data-stu-id="18094-186">Create a rule by using the **New-TransportRule** cmdlet and set the _ApplyOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="18094-187">此示例要求发送到 DrToniRamos@hotmail.com 的所有电子邮件都必须加密。</span><span class="sxs-lookup"><span data-stu-id="18094-187">This example requires that all email messages sent to DrToniRamos@hotmail.com must be encrypted.</span></span>

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   <span data-ttu-id="18094-188">**注意：**</span><span class="sxs-lookup"><span data-stu-id="18094-188">**Notes**:</span></span>

   - <span data-ttu-id="18094-189">新规则的唯一名称是 "加密 Dr Toni Ramos" 的规则。</span><span class="sxs-lookup"><span data-stu-id="18094-189">The unique name of the new rule is "Encrypt rule for Dr Toni Ramos".</span></span>

   - <span data-ttu-id="18094-190">_SentTo_参数指定邮件收件人（由姓名、电子邮件地址、可分辨名称等）。</span><span class="sxs-lookup"><span data-stu-id="18094-190">The _SentTo_ parameter specifies the message recipients (identified by name, email address, distinguished name, etc.).</span></span> <span data-ttu-id="18094-191">在此示例中，收件人由电子邮件地址 "DrToniRamos@hotmail.com" 标识。</span><span class="sxs-lookup"><span data-stu-id="18094-191">In this example, the recipient is identified by the email address "DrToniRamos@hotmail.com".</span></span>

   - <span data-ttu-id="18094-192">_SentToScope_参数指定邮件收件人的位置。</span><span class="sxs-lookup"><span data-stu-id="18094-192">The _SentToScope_ parameter specifies the location of the message recipients.</span></span> <span data-ttu-id="18094-193">在此示例中，收件人的邮箱在 hotmail 中，而不是 Office 365 组织的一部分，因此使用此`NotInOrganization`值。</span><span class="sxs-lookup"><span data-stu-id="18094-193">In this example, the recipient's mailbox is in hotmail and is not part of the Office 365 organization, so the value `NotInOrganization` is used.</span></span>

   <span data-ttu-id="18094-194">有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)。</span><span class="sxs-lookup"><span data-stu-id="18094-194">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).</span></span>

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="18094-195">从加密的电子邮件答复中删除加密，而不具有新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="18094-195">Remove encryption from email replies encrypted without the new OME capabilities</span></span>

<span data-ttu-id="18094-196">您的电子邮件用户发送加密邮件后，这些邮件的收件人可以使用加密答复回复。</span><span class="sxs-lookup"><span data-stu-id="18094-196">When your email users send encrypted messages, recipients of those messages can respond with encrypted replies.</span></span> <span data-ttu-id="18094-197">您可以创建邮件流规则以自动删除答复的加密，以便组织中的电子邮件用户无需登录到加密门户即可查看加密门户。</span><span class="sxs-lookup"><span data-stu-id="18094-197">You can create mail flow rules to automatically remove encryption from replies so email users in your organization don't have to sign in to the encryption portal to view them.</span></span> <span data-ttu-id="18094-198">您可以使用 EAC 或 Windows PowerShell cmdlet 来定义这些规则。</span><span class="sxs-lookup"><span data-stu-id="18094-198">You can use the EAC or Windows PowerShell cmdlets to define these rules.</span></span> <span data-ttu-id="18094-199">如果尚未使用新的 OME 功能，则只能对从组织内部发送的邮件或从组织内部发送的邮件答复邮件进行解密。</span><span class="sxs-lookup"><span data-stu-id="18094-199">If you are not yet using the new OME capabilities, you can only decrypt messages that are either sent from within your organization or messages that are replies to messages sent from within your organization.</span></span> <span data-ttu-id="18094-200">无法对源自组织外部的加密邮件进行解密。</span><span class="sxs-lookup"><span data-stu-id="18094-200">You cannot decrypt encrypted messages originating from outside of your organization.</span></span>

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="18094-201">使用 EAC 创建一个规则，用于从加密的电子邮件答复中删除加密，而不使用新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="18094-201">Use the EAC to create a rule for removing encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="18094-202">在 web 浏览器中，使用已被授予管理员权限的工作或学校帐户，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="18094-202">In a web browser, using a work or school account that has been granted admin permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="18094-203">选择 "**管理**" 磁贴。</span><span class="sxs-lookup"><span data-stu-id="18094-203">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="18094-204">在 Microsoft 365 管理中心，选择 "**管理中心** \> " " **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="18094-204">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="18094-205">在 EAC 中，转到 "**邮件流** \> **规则**"，然后选择 "**新建** ![" 图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **创建新规则**。</span><span class="sxs-lookup"><span data-stu-id="18094-205">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="18094-206">有关使用 EAC 的详细信息，请参阅 exchange [Online 中的 exchange 管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="18094-206">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="18094-207">在 "**名称**" 中，键入规则的名称，例如 "从传入邮件中删除加密"。</span><span class="sxs-lookup"><span data-stu-id="18094-207">In **Name**, type a name for the rule, such as Remove encryption from incoming mail.</span></span>

6. <span data-ttu-id="18094-208">在 "**应用此规则**" 中，如果选择应从邮件中删除加密的条件，例如**收件人位于** \> **组织内部**。</span><span class="sxs-lookup"><span data-stu-id="18094-208">In **Apply this rule if** select the conditions where encryption should be removed from messages, such as **The recipient is located** \> **Inside the organization**.</span></span>

7. <span data-ttu-id="18094-209">在 **"执行以下操作**" 中，选择 "**修改邮件安全性** \> **" 删除 OME 的早期版本**。</span><span class="sxs-lookup"><span data-stu-id="18094-209">In **Do the following**, select **Modify the message security** \> **Remove the previous version of OME**.</span></span>

8. <span data-ttu-id="18094-210">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="18094-210">Select **Save**.</span></span>

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="18094-211">使用 Exchange Online PowerShell 创建一个规则，以从加密的电子邮件答复中删除加密，而不使用新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="18094-211">Use Exchange Online PowerShell to create a rule to remove encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="18094-212">连接到 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="18094-212">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="18094-213">有关详细信息，请参阅[使用远程 PowerShell 连接到 Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="18094-213">For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="18094-214">使用**new-transportrule** cmdlet 创建一个规则，并将_RemoveOME_参数设置为`$true`。</span><span class="sxs-lookup"><span data-stu-id="18094-214">Create a rule by using the **New-TransportRule** cmdlet and set the _RemoveOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="18094-215">本示例将从所有发送到 Office 365 组织中的收件人的邮件中删除加密。</span><span class="sxs-lookup"><span data-stu-id="18094-215">This example removes the encryption from all mail sent to recipients in the Office 365 organization.</span></span>

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   <span data-ttu-id="18094-216">**注意：**</span><span class="sxs-lookup"><span data-stu-id="18094-216">**Notes**:</span></span>

   - <span data-ttu-id="18094-217">新规则的唯一名称是 "从传入邮件中删除加密"。</span><span class="sxs-lookup"><span data-stu-id="18094-217">The unique name of the new rule is "Remove encryption from incoming mail".</span></span>

   - <span data-ttu-id="18094-218">_SentToScope_参数指定邮件收件人的位置。</span><span class="sxs-lookup"><span data-stu-id="18094-218">The _SentToScope_ parameter specifies the location of the message recipients.</span></span> <span data-ttu-id="18094-219">在此示例中，使用`InOrganization`了值值，该值指示：</span><span class="sxs-lookup"><span data-stu-id="18094-219">In this example, the value `InOrganization` value is used, which indicates:</span></span>

     - <span data-ttu-id="18094-220">收件人是组织中的邮箱、邮件用户、组或已启用邮件的公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="18094-220">The recipient is a mailbox, mail user, group, or mail-enabled public folder in your organization.</span></span>

       <span data-ttu-id="18094-221">或</span><span class="sxs-lookup"><span data-stu-id="18094-221">or</span></span>

     - <span data-ttu-id="18094-222">收件人的电子邮件地址位于您的组织中配置为权威域或内部中继域的接受域中，_并且_邮件是通过经过身份验证的连接发送或接收的。</span><span class="sxs-lookup"><span data-stu-id="18094-222">The recipient's email address is in an accepted domain that's configured as an authoritative domain or an internal relay domain in your organization, _and_ the message was sent or received over an authenticated connection.</span></span>

<span data-ttu-id="18094-223">有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)。</span><span class="sxs-lookup"><span data-stu-id="18094-223">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).</span></span>

## <a name="related-topics"></a><span data-ttu-id="18094-224">相关主题</span><span class="sxs-lookup"><span data-stu-id="18094-224">Related Topics</span></span>

[<span data-ttu-id="18094-225">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="18094-225">Encryption in Office 365</span></span>](encryption.md)

[<span data-ttu-id="18094-226">设置全新的 Office 365 邮件加密功能</span><span class="sxs-lookup"><span data-stu-id="18094-226">Set up new Office 365 Message Encryption capabilities</span></span>](set-up-new-message-encryption-capabilities.md)

[<span data-ttu-id="18094-227">将品牌添加到加密邮件</span><span class="sxs-lookup"><span data-stu-id="18094-227">Add branding to encrypted messages</span></span>](add-your-organization-brand-to-encrypted-messages.md)

[<span data-ttu-id="18094-228">Exchange Online 中的邮件流规则（传输规则）</span><span class="sxs-lookup"><span data-stu-id="18094-228">Mail flow rules (transport rules) in Exchange Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[<span data-ttu-id="18094-229">Exchange Online Protection 中的邮件流规则（传输规则）</span><span class="sxs-lookup"><span data-stu-id="18094-229">Mail flow rules (transport rules) in Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506708)
