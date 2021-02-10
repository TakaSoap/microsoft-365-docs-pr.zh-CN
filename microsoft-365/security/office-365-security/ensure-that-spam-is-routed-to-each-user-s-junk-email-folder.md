---
title: 在混合环境中将 EOP 配置为垃圾邮件
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何将垃圾邮件路由到 Exchange Online Protection 混合环境中的用户垃圾邮件文件夹。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 926ac6dec33bf00fc8f0dcd292229e20ccc2b93f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167115"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="bd635-103">配置独立 EOP 以将垃圾邮件发送到混合环境中垃圾邮件文件夹</span><span class="sxs-lookup"><span data-stu-id="bd635-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bd635-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="bd635-104">**Applies to**</span></span>
-  [<span data-ttu-id="bd635-105">独立 Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bd635-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

> [!IMPORTANT]
> <span data-ttu-id="bd635-106">本主题仅适用于混合环境中的独立 EOP 客户。</span><span class="sxs-lookup"><span data-stu-id="bd635-106">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="bd635-107">本主题不适用于具有 Exchange Online 邮箱的 Microsoft 365 客户。</span><span class="sxs-lookup"><span data-stu-id="bd635-107">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="bd635-108">如果您是混合环境中的独立 Exchange Online Protection (EOP) 客户，则需要将内部部署 Exchange 组织配置为识别和转换 EOP 的垃圾邮件筛选裁定，以便内部部署邮箱中的垃圾邮件规则可以将邮件移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="bd635-108">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="bd635-109">具体来说，您需要在本地 Exchange 组织中创建邮件流规则 (也称为传输规则) ，这些规则的条件是查找具有以下任何 EOP 反垃圾邮件标头和值的邮件，以及将这些邮件的垃圾邮件可信度 (SCL) 设置为 6 的操作：</span><span class="sxs-lookup"><span data-stu-id="bd635-109">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="bd635-110">`X-Forefront-Antispam-Report: SFV:SPM` (垃圾邮件筛选功能将邮件标记为) </span><span class="sxs-lookup"><span data-stu-id="bd635-110">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="bd635-111">`X-Forefront-Antispam-Report: SFV:SKS` (筛选垃圾邮件之前，由 EOP 中的邮件流规则标记为垃圾邮件的邮件) </span><span class="sxs-lookup"><span data-stu-id="bd635-111">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="bd635-112">`X-Forefront-Antispam-Report: SFV:SKB` (发件人的电子邮件地址或电子邮件域位于 EOP 发件人阻止的发件人列表或阻止的域列表中，被垃圾邮件筛选标记为垃圾邮件的邮件) </span><span class="sxs-lookup"><span data-stu-id="bd635-112">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="bd635-113">有关这些邮件头值的信息，请参阅 ["反垃圾邮件"邮件头](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="bd635-113">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="bd635-114">本主题介绍如何在本地 Exchange 组织的 Exchange 管理中心 (EAC) 和 Exchange 命令行管理程序 (Exchange PowerShell) 创建这些邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="bd635-114">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="bd635-115">您可以在 EOP 中配置反垃圾邮件策略以隔离 EOP 中的垃圾邮件，而不是将邮件发送到本地用户的"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="bd635-115">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="bd635-116">有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bd635-116">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bd635-117">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="bd635-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bd635-118">您需在本地 Exchange 环境中获得权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="bd635-118">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="bd635-119">具体来说，您需要分配有传输规则角色，默认情况下，该角色将分配给组织管理、合规性管理和 **记录管理** 角色。 </span><span class="sxs-lookup"><span data-stu-id="bd635-119">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="bd635-120">有关详细信息，请参阅"[将成员添加到角色组"。](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group)</span><span class="sxs-lookup"><span data-stu-id="bd635-120">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="bd635-121">如果将邮件传递到内部部署 Exchange 组织的"垃圾邮件"文件夹，则当邮件通过以下设置的组合控制时：</span><span class="sxs-lookup"><span data-stu-id="bd635-121">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="bd635-122">Exchange 命令行管理程序 [中 Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet 上的 _SCLJunkThreshold_ 参数值。</span><span class="sxs-lookup"><span data-stu-id="bd635-122">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="bd635-123">默认值为 4，这意味着 SCL 为 5 或更高值时，应该将邮件发送到用户的"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="bd635-123">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="bd635-124">Exchange 命令行管理程序 [中 Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) cmdlet 上的 _SCLJunkThreshold_ 参数值。</span><span class="sxs-lookup"><span data-stu-id="bd635-124">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="bd635-125">默认值为空值 ($null) ，这意味着使用组织设置。</span><span class="sxs-lookup"><span data-stu-id="bd635-125">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="bd635-126">有关详细信息，请参阅 [Exchange 垃圾邮件可信度 (SCL](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)) 阈值。</span><span class="sxs-lookup"><span data-stu-id="bd635-126">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="bd635-127">是否对邮箱启用垃圾邮件规则 (Exchange 命令行管理程序 $true [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet 上的 _Enabled_ 参数值) 。</span><span class="sxs-lookup"><span data-stu-id="bd635-127">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="bd635-128">垃圾邮件规则实际上是在邮件传递后将邮件移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="bd635-128">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="bd635-129">默认情况下，对邮箱启用垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="bd635-129">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="bd635-130">有关详细信息，请参阅 [配置邮箱上的 Exchange 反垃圾邮件设置](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)。</span><span class="sxs-lookup"><span data-stu-id="bd635-130">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>

- <span data-ttu-id="bd635-131">若要在邮件上打开 EAC Exchange Server，请参阅[exchange 管理中心Exchange Server。](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="bd635-131">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="bd635-132">若要打开 EAC，请参阅 Exchange Server 中的 Exchange 管理中心中。若要打开 Exchange 命令行管理程序，请参阅[打开 Exchange 命令行管理程序](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell)。</span><span class="sxs-lookup"><span data-stu-id="bd635-132">To open the Exchange Management Shell, see [Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="bd635-133">有关内部部署 Exchange 中的邮件流规则详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="bd635-133">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="bd635-134">邮件流规则Exchange Server</span><span class="sxs-lookup"><span data-stu-id="bd635-134">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="bd635-135">邮件流规则条件和例外 () Exchange Server</span><span class="sxs-lookup"><span data-stu-id="bd635-135">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="bd635-136">邮件流规则操作Exchange Server</span><span class="sxs-lookup"><span data-stu-id="bd635-136">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="bd635-137">使用 EAC 创建设置 EOP 垃圾邮件 SCL 的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="bd635-137">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="bd635-138">In the EAC, go to **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="bd635-138">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="bd635-139">单击 **"** ![ 添加" ](../../media/ITPro-EAC-AddIcon.png) 图标，在出现的下拉列表中选择"创建新规则"。</span><span class="sxs-lookup"><span data-stu-id="bd635-139">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="bd635-140">在打开的" **新规则**"窗口中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="bd635-140">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="bd635-141">**名称**：为规则输入唯一的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="bd635-141">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="bd635-142">例如：</span><span class="sxs-lookup"><span data-stu-id="bd635-142">For example:</span></span>

     - <span data-ttu-id="bd635-143">EOP SFV：SPM 到 SCL 6</span><span class="sxs-lookup"><span data-stu-id="bd635-143">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="bd635-144">EOP SFV：SKS 到 SCL 6</span><span class="sxs-lookup"><span data-stu-id="bd635-144">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="bd635-145">EOP SFV：SKB 到 SCL 6</span><span class="sxs-lookup"><span data-stu-id="bd635-145">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="bd635-146">单击“其他选项”。</span><span class="sxs-lookup"><span data-stu-id="bd635-146">Click **More Options**.</span></span>

   - <span data-ttu-id="bd635-147">**如果：选择包含** 以下 **任何词语的邮件** 头 \> **，则应用此规则**。</span><span class="sxs-lookup"><span data-stu-id="bd635-147">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="bd635-148">In the **Enter text header includes Enter words** sentence that appears， do the following steps：</span><span class="sxs-lookup"><span data-stu-id="bd635-148">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="bd635-149">单击 **"输入文本"。**</span><span class="sxs-lookup"><span data-stu-id="bd635-149">Click **Enter text**.</span></span> <span data-ttu-id="bd635-150">在出现的 **"指定标头名称**"对话框中，输入 **X-Forefront-Antispam-Report，** 然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="bd635-150">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="bd635-151">单击 **"输入单词"。**</span><span class="sxs-lookup"><span data-stu-id="bd635-151">Click  **Enter words**.</span></span> <span data-ttu-id="bd635-152">在出现的"指定词语或短语"对话框中，输入 EOP 垃圾邮件头值 (**SFV：SPM、SFV：SKS** 或 **SFV：SKB**) ，单击"添加"图标，然后单击"确定 ![ ](../../media/ITPro-EAC-AddIcon.png) "。 </span><span class="sxs-lookup"><span data-stu-id="bd635-152">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="bd635-153">**执行以下操作：** 选择 **"修改邮件属性** \> **设置 SCL (垃圾邮件可信度) 。**</span><span class="sxs-lookup"><span data-stu-id="bd635-153">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="bd635-154">在 **出现的"指定 SCL"** 对话框中，选择 **6** (默认值 **为 5**) 。</span><span class="sxs-lookup"><span data-stu-id="bd635-154">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="bd635-155">完成后，单击"保存 **"**</span><span class="sxs-lookup"><span data-stu-id="bd635-155">When you're finished, click **Save**</span></span>

<span data-ttu-id="bd635-156">对 **SFV：SPM、SFV：SKS** 或 **SFV：SKB** (剩余 EOP 垃圾邮件裁定值重复) 。</span><span class="sxs-lookup"><span data-stu-id="bd635-156">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="bd635-157">使用 Exchange 命令行管理程序 创建设置 EOP 垃圾邮件 SCL 的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="bd635-157">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="bd635-158">使用以下语法创建三个邮件流规则：</span><span class="sxs-lookup"><span data-stu-id="bd635-158">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="bd635-159">例如：</span><span class="sxs-lookup"><span data-stu-id="bd635-159">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="bd635-160">有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)。</span><span class="sxs-lookup"><span data-stu-id="bd635-160">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="bd635-161">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="bd635-161">How do you know this worked?</span></span>

<span data-ttu-id="bd635-162">若要验证您是否已成功配置独立 EOP 以将垃圾邮件发送到混合环境中垃圾邮件文件夹，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="bd635-162">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="bd635-163">在 EAC 中，转到"**邮件流** 规则"，选择规则，然后单击"编辑编辑"图标 \>  ![ ](../../media/ITPro-EAC-EditIcon.png) 以验证设置。</span><span class="sxs-lookup"><span data-stu-id="bd635-163">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="bd635-164">在 Exchange 命令行管理程序 中，替换为邮件流规则的名称，并运行以下命令 \<RuleName\> 来验证设置：</span><span class="sxs-lookup"><span data-stu-id="bd635-164">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="bd635-165">在未扫描出站邮件的垃圾邮件的外部电子邮件系统中，向受影响的收件人发送未经请求的批量电子邮件 (GTUBE) 邮件的通用测试，并确认邮件已传递到其"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="bd635-165">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="bd635-166">GTUBE 邮件类似于用于测试恶意软件设置的欧洲反计算机病毒协会 (EICAR) 文本文件。</span><span class="sxs-lookup"><span data-stu-id="bd635-166">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="bd635-167">若要发送 GTUBE 邮件，请将以下文本包括在单行电子邮件的正文中，不带任何空格或换行符：</span><span class="sxs-lookup"><span data-stu-id="bd635-167">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
