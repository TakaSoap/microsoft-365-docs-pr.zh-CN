---
title: 在混合环境中配置 EOP 到垃圾邮件
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 管理员可以了解在混合环境中使用独立 Exchange Online Protection （EOP）时，如何将内部部署 Exchange 环境配置为将垃圾邮件路由到本地用户的垃圾邮件文件夹。
ms.openlocfilehash: f2964324c6d9104719fc79ff31f14b4b94c627cc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43621278"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="b765b-103">将独立 EOP 配置为将垃圾邮件传递到混合环境中的 "垃圾邮件" 文件夹</span><span class="sxs-lookup"><span data-stu-id="b765b-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b765b-104">本主题仅适用于混合环境中的独立 EOP 客户。</span><span class="sxs-lookup"><span data-stu-id="b765b-104">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="b765b-105">本主题不适用于使用 Exchange Online 邮箱的 Microsoft 365 客户。</span><span class="sxs-lookup"><span data-stu-id="b765b-105">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="b765b-106">如果您是混合环境中的独立 Exchange Online Protection （EOP）客户，您需要将内部部署 Exchange 组织配置为识别和翻译 EOP 的垃圾邮件筛选 verdicts，以便内部部署邮箱中的垃圾邮件规则可以将邮件移动到 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="b765b-106">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="b765b-107">具体来说，您需要在内部部署 Exchange 组织中创建邮件流规则（也称为传输规则），条件是查找带有以下任一 EOP 反垃圾邮件头和值的邮件，以及将这些邮件的垃圾邮件可信度（SCL）设置为6的操作：</span><span class="sxs-lookup"><span data-stu-id="b765b-107">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="b765b-108">`X-Forefront-Antispam-Report: SFV:SPM`（通过垃圾邮件筛选功能标记为垃圾邮件）</span><span class="sxs-lookup"><span data-stu-id="b765b-108">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="b765b-109">`X-Forefront-Antispam-Report: SFV:SKS`（通过垃圾邮件筛选前 EOP 中的邮件流规则标记为垃圾邮件的邮件）</span><span class="sxs-lookup"><span data-stu-id="b765b-109">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="b765b-110">`X-Forefront-Antispam-Report: SFV:SKB`（由于发件人的电子邮件地址或电子邮件域位于阻止的发件人列表或 EOP 中的阻止域列表中，由垃圾邮件筛选标记为垃圾邮件的邮件）</span><span class="sxs-lookup"><span data-stu-id="b765b-110">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="b765b-111">有关这些标头值的详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="b765b-111">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="b765b-112">本主题介绍如何在内部部署 Exchange 组织中的 exchange 管理中心（EAC）和 Exchange 命令行管理程序（Exchange PowerShell）中创建这些邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="b765b-112">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="b765b-113">您可以在 EOP 中配置反垃圾邮件策略以隔离 EOP 中的垃圾邮件，而不是将邮件传递到本地用户的 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="b765b-113">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="b765b-114">有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b765b-114">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b765b-115">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="b765b-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b765b-116">您需要在本地 Exchange 环境中分配权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="b765b-116">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="b765b-117">具体来说，您需要分配 "**传输规则**" 角色，默认情况下会将其分配给 "**组织管理**"、"**合规性管理**" 和 "**记录管理**" 角色。</span><span class="sxs-lookup"><span data-stu-id="b765b-117">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="b765b-118">有关详细信息，请参阅[向角色组添加成员](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group)。</span><span class="sxs-lookup"><span data-stu-id="b765b-118">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="b765b-119">如果将邮件传递到本地 Exchange 组织中的 "垃圾邮件" 文件夹，则将通过以下设置的组合来控制邮件：</span><span class="sxs-lookup"><span data-stu-id="b765b-119">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="b765b-120">Exchange 命令行管理程序中的[set-organizationconfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) cmdlet 上的_SCLJunkThreshold_参数值。</span><span class="sxs-lookup"><span data-stu-id="b765b-120">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="b765b-121">默认值为4，表示 SCL 为5或更高应将邮件传递到用户的 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="b765b-121">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="b765b-122">Exchange 命令行管理程序中的[设置邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)cmdlet 上的_SCLJunkThreshold_参数值。</span><span class="sxs-lookup"><span data-stu-id="b765b-122">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="b765b-123">默认值为空（$null），这意味着使用组织设置。</span><span class="sxs-lookup"><span data-stu-id="b765b-123">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="b765b-124">有关详细信息，请参阅[Exchange 垃圾邮件可信度级别（SCL）阈值](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)。</span><span class="sxs-lookup"><span data-stu-id="b765b-124">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="b765b-125">是否在邮箱上启用垃圾邮件规则（_启用_的参数值将在 Exchange 命令行管理[程序的 set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) cmdlet 中 $true）。</span><span class="sxs-lookup"><span data-stu-id="b765b-125">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="b765b-126">它是传递邮件后实际将邮件移动到 "垃圾邮件" 文件夹的垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="b765b-126">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="b765b-127">默认情况下，在邮箱上启用垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="b765b-127">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="b765b-128">有关详细信息，请参阅[在邮箱上配置 Exchange 反垃圾邮件设置](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)。</span><span class="sxs-lookup"><span data-stu-id="b765b-128">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>
  
- <span data-ttu-id="b765b-129">若要在 Exchange 服务器上打开 EAC，请参阅 exchange [administration center In Exchange server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="b765b-129">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="b765b-130">若要打开 Exchange 命令行管理程序[https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell)，请参阅。</span><span class="sxs-lookup"><span data-stu-id="b765b-130">To open the Exchange Management Shell, see [https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="b765b-131">有关本地 Exchange 中的邮件流规则的详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="b765b-131">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="b765b-132">Exchange Server 中的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="b765b-132">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="b765b-133">Exchange Server 中的邮件流规则条件和例外（谓词）</span><span class="sxs-lookup"><span data-stu-id="b765b-133">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="b765b-134">Exchange Server 中的邮件流规则操作</span><span class="sxs-lookup"><span data-stu-id="b765b-134">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="b765b-135">使用 EAC 创建邮件流规则，以设置 EOP 垃圾邮件的 SCL</span><span class="sxs-lookup"><span data-stu-id="b765b-135">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="b765b-136">In the EAC, go to **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="b765b-136">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="b765b-137">单击 "**添加** !["](../../media/ITPro-EAC-AddIcon.png) "添加" 图标，然后在出现的下拉对话框中选择 "**创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="b765b-137">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="b765b-138">在打开的" **新规则**"窗口中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="b765b-138">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="b765b-139">**名称**：输入规则的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="b765b-139">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="b765b-140">例如：</span><span class="sxs-lookup"><span data-stu-id="b765b-140">For example:</span></span>

     - <span data-ttu-id="b765b-141">EOP SFV： SPM 至 SCL 6</span><span class="sxs-lookup"><span data-stu-id="b765b-141">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="b765b-142">EOP SFV： SKS 到 SCL 6</span><span class="sxs-lookup"><span data-stu-id="b765b-142">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="b765b-143">EOP SFV： SKB 到 SCL 6</span><span class="sxs-lookup"><span data-stu-id="b765b-143">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="b765b-144">单击“其他选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b765b-144">Click **More Options**.</span></span>

   - <span data-ttu-id="b765b-145">**在以下情况应用此规则**：选择**邮件标头** \>中**包含这些词语中的任何一个**。</span><span class="sxs-lookup"><span data-stu-id="b765b-145">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="b765b-146">在 "**输入文本头包含**所显示的输入词" 句子中，执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="b765b-146">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="b765b-147">单击 "**输入文本**"。</span><span class="sxs-lookup"><span data-stu-id="b765b-147">Click **Enter text**.</span></span> <span data-ttu-id="b765b-148">在出现的 "**指定头名称**" 对话框中，输入**X-Forefront-反垃圾邮件报告**，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="b765b-148">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="b765b-149">单击 "**输入词**"。</span><span class="sxs-lookup"><span data-stu-id="b765b-149">Click  **Enter words**.</span></span> <span data-ttu-id="b765b-150">在出现的 "**指定字词或短语**" 对话框中，输入一个 EOP 垃圾邮件标头值（**SFV： SPM**， **SFV： SKS**，或**SFV： SKB**） **Add** ![，单击 "](../../media/ITPro-EAC-AddIcon.png)添加" "添加" 图标，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="b765b-150">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="b765b-151">**执行以下**操作：选择 "**修改邮件属性** \> **" 设置垃圾邮件可信度（SCL）**。</span><span class="sxs-lookup"><span data-stu-id="b765b-151">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="b765b-152">在出现的 "**指定 SCL** " 对话框中，选择 " **6** " （默认值为**5**）。</span><span class="sxs-lookup"><span data-stu-id="b765b-152">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="b765b-153">完成后，请单击 "**保存**"</span><span class="sxs-lookup"><span data-stu-id="b765b-153">When you're finished, click **Save**</span></span>

<span data-ttu-id="b765b-154">对余下的 EOP 垃圾邮件结论值（**SFV： SPM**、 **SFV： SKS**或**SFV： SKB**）重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="b765b-154">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="b765b-155">使用 Exchange 命令行管理程序创建邮件流规则，以设置 EOP 垃圾邮件的 SCL</span><span class="sxs-lookup"><span data-stu-id="b765b-155">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="b765b-156">使用以下语法创建三个邮件流规则：</span><span class="sxs-lookup"><span data-stu-id="b765b-156">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="b765b-157">例如：</span><span class="sxs-lookup"><span data-stu-id="b765b-157">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="b765b-158">有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)。</span><span class="sxs-lookup"><span data-stu-id="b765b-158">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="b765b-159">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="b765b-159">How do you know this worked?</span></span>

<span data-ttu-id="b765b-160">若要验证是否已成功将独立 EOP 配置为将垃圾邮件传递到混合环境中的 "垃圾邮件" 文件夹，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="b765b-160">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="b765b-161">在 EAC 中，转到 "**邮件流** \> **规则**"，选择规则，然后单击 "**编辑** ![编辑](../../media/ITPro-EAC-EditIcon.png)图标" 以验证设置。</span><span class="sxs-lookup"><span data-stu-id="b765b-161">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="b765b-162">在 Exchange 命令行管理程序中\<，\>将 RuleName 替换为邮件流规则的名称，并 rul 以下命令以验证设置：</span><span class="sxs-lookup"><span data-stu-id="b765b-162">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="b765b-163">在**不扫描出站邮件中的垃圾**邮件的外部电子邮件系统中，向受影响的收件人发送未经请求的批量电子邮件（GTUBE）邮件的一般测试，并确认它已传递到其 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="b765b-163">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="b765b-164">GTUBE 邮件类似于用于测试恶意软件设置的欧洲反计算机病毒协会 (EICAR) 文本文件。</span><span class="sxs-lookup"><span data-stu-id="b765b-164">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="b765b-165">若要发送 GTUBE 邮件，请将电子邮件正文中的以下文本包含在一行中，不含空格或换行符：</span><span class="sxs-lookup"><span data-stu-id="b765b-165">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
