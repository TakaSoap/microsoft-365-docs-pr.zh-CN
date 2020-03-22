---
title: 使用邮件流规则在 Office 365 中筛选批量电子邮件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何使用 Exchange Online Protection 中的邮件流规则进行批量电子邮件筛选。
ms.openlocfilehash: 2ac81d798af957f23f95b92f633b93bdda677991
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895043"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-office-365"></a><span data-ttu-id="10730-103">使用邮件流规则在 Office 365 中筛选批量电子邮件</span><span class="sxs-lookup"><span data-stu-id="10730-103">Use mail flow rules to filter bulk email in Office 365</span></span>

<span data-ttu-id="10730-104">如果您是在 Exchange Online 中使用邮箱的 Office 365 客户或没有 Exchange Online 邮箱的独立 Exchange Online Protection （EOP）客户，则 EOP 使用反垃圾邮件策略（也称为垃圾邮件筛选器策略或内容筛选器策略）进行扫描垃圾邮件和批量邮件的入站邮件（也称为 "灰色邮件"）。</span><span class="sxs-lookup"><span data-stu-id="10730-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="10730-105">有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="10730-105">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="10730-106">如果您希望更多的选项筛选批量邮件，可以创建邮件流规则（也称为传输规则），以搜索批量邮件中经常找到的文本模式或短语，并将这些邮件标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="10730-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="10730-107">有关批量邮件的详细信息，请参阅 Office 365 中的[垃圾邮件和批量电子邮件之间的区别是什么？](what-s-the-difference-between-junk-email-and-bulk-email.md)和[批量投诉级别（BCL）](bulk-complaint-level-values.md)。</span><span class="sxs-lookup"><span data-stu-id="10730-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="10730-108">本主题介绍如何在 Exchange 管理中心（EAC）和 PowerShell （Office 365 客户的 Exchange Online PowerShell 中创建这些邮件流规则;适用于独立 EOP 客户的 Exchange Online Protection PowerShell）。</span><span class="sxs-lookup"><span data-stu-id="10730-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="10730-109">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="10730-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="10730-110">您需要先在 Exchange Online 中分配权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="10730-110">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="10730-111">具体来说，您需要分配 "**传输规则**" 角色，默认情况下会将其分配给 "**组织管理**"、"**合规性管理**" 和 "**记录管理**" 角色。</span><span class="sxs-lookup"><span data-stu-id="10730-111">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="10730-112">有关详细信息，请参阅[在 Exchange Online 中管理角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="10730-112">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="10730-113">若要在 Exchange Online 中打开 EAC，请参阅 exchange [online 中的 exchange 管理中心](https://docs.microsoft.com/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="10730-113">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="10730-114">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="10730-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="10730-115">若要连接到独立的 Exchange Online Protection PowerShell，请参阅[连接到 Exchange Online Protection powershell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="10730-115">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="10730-116">有关 Exchange Online 和独立 EOP 中的邮件流规则的详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="10730-116">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="10730-117">Exchange Online 中的邮件流规则（传输规则）</span><span class="sxs-lookup"><span data-stu-id="10730-117">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="10730-118">Exchange Online 中的邮件流规则条件和例外（谓词）</span><span class="sxs-lookup"><span data-stu-id="10730-118">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="10730-119">Exchange Online 中的邮件流规则操作</span><span class="sxs-lookup"><span data-stu-id="10730-119">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="10730-120">用于标识示例中的批量邮件的单词和文本模式列表不详尽;您可以根据需要添加和删除条目。</span><span class="sxs-lookup"><span data-stu-id="10730-120">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="10730-121">但是，它们是一个很棒的起点。</span><span class="sxs-lookup"><span data-stu-id="10730-121">However, they are a good starting point.</span></span>

- <span data-ttu-id="10730-p106">在邮件已通过 MIME 内容传输编码方法（用于以 ACSII 文本方式在 SMTP 服务器之间传输二进制消息）解码*后*，搜索邮件中主题或其他头字段中的字词或文本模式。不能使用条件或例外来搜索邮件中主题或其他头字段的原始（通常为 Base64）编码值。</span><span class="sxs-lookup"><span data-stu-id="10730-p106">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="10730-124">下面的过程将批量邮件标记为您的整个组织的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="10730-124">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="10730-125">但是，您可以添加另一个条件，以便仅将这些规则应用于特定的收件人，以便您可以对一些高度目标的用户使用严格筛选，而其余用户（大多数人都会收到其注册的批量电子邮件）不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="10730-125">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="10730-126">使用 EAC 创建筛选批量电子邮件的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="10730-126">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="10730-127">In the EAC, go to **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="10730-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="10730-128">单击 "**添加** !["](../../media/ITPro-EAC-AddIcon.png) "添加" 图标，然后选择 "**创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="10730-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="10730-129">在打开的" **新规则**"窗口中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="10730-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="10730-130">**名称**：输入规则的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="10730-130">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="10730-131">单击“其他选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="10730-131">Click **More Options**.</span></span>

   - <span data-ttu-id="10730-132">**在以下情况下应用此规则**：配置以下设置之一，以使用正则表达式（RegEx）或字词或短语查找邮件中的内容：</span><span class="sxs-lookup"><span data-stu-id="10730-132">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="10730-133">**主题** \>或正文**主题或正文与这些文本模式匹配**：在显示的 "**指定字词或短语**" 对话框中，输入以下值之一，单击 "**添加** !["](../../media/ITPro-EAC-AddIcon.png)"添加" 图标，然后根据需要重复任意次数。</span><span class="sxs-lookup"><span data-stu-id="10730-133">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat as many times as necessary.</span></span>

       - `If you are unable to view the content of this email\, please`

       - `\>(safe )?unsubscribe( here)?\</a\>`

       - `If you do not wish to receive further communications like this\, please`

       - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`

       - `To stop receiving these+emails\:http\://`

       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`

       - `no longer (wish )?(to )?(be sent|receive) w+ email`

       - `If you are unable to view the content of this email\, please click here`

       - `To ensure you receive (your daily deals|our e-?mails)\, add`

       - `If you no longer wish to receive these emails`

       - `to change your (subscription preferences|preferences or unsubscribe)`

       - `click (here to|the) unsubscribe`

      <span data-ttu-id="10730-134">若要编辑条目，请选择该条目**Edit** ![，然后单击](../../media/ITPro-EAC-EditIcon.png)"编辑" "编辑" 图标。</span><span class="sxs-lookup"><span data-stu-id="10730-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="10730-135">若要删除条目，请将其选中**Remove** ![，然后单击](../../media/ITPro-EAC-DeleteIcon.png)"删除删除图标"。</span><span class="sxs-lookup"><span data-stu-id="10730-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="10730-136">完成后，请单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="10730-136">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="10730-137">**主题** \>或正文**主题或正文包含以下任何词语**：在显示的 "**指定字词或短语**" 对话框中，输入以下值之一，单击 "**添加** ![" "添加](../../media/ITPro-EAC-AddIcon.png)" 图标，然后根据需要重复任意次数。</span><span class="sxs-lookup"><span data-stu-id="10730-137">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat as many times as necessary.</span></span>

       - `to change your preferences or unsubscribe`

       - `Modify email preferences or unsubscribe`

       - `This is a promotional email`

       - `You are receiving this email because you requested a subscription`

       - `click here to unsubscribe`

       - `You have received this email because you are subscribed`

       - `If you no longer wish to receive our email newsletter`

       - `to unsubscribe from this newsletter`

       - `If you have trouble viewing this email`

       - `This is an advertisement`

       - `you would like to unsubscribe or change your`

       - `view this email as a webpage`

       - `You are receiving this email because you are subscribed`

      <span data-ttu-id="10730-138">若要编辑条目，请选择该条目**Edit** ![，然后单击](../../media/ITPro-EAC-EditIcon.png)"编辑" "编辑" 图标。</span><span class="sxs-lookup"><span data-stu-id="10730-138">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="10730-139">若要删除条目，请将其选中**Remove** ![，然后单击](../../media/ITPro-EAC-DeleteIcon.png)"删除删除图标"。</span><span class="sxs-lookup"><span data-stu-id="10730-139">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="10730-140">完成后，请单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="10730-140">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="10730-141">**执行以下**操作：选择 "**修改邮件属性** \> **" 设置垃圾邮件可信度（SCL）**。</span><span class="sxs-lookup"><span data-stu-id="10730-141">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="10730-142">在出现的 "**指定 SCL** " 对话框中，配置以下设置之一：</span><span class="sxs-lookup"><span data-stu-id="10730-142">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="10730-143">若要将邮件标记为**垃圾**邮件，请选择 " **6**"。</span><span class="sxs-lookup"><span data-stu-id="10730-143">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="10730-144">您为反垃圾邮件策略中的**垃圾**邮件筛选 verdicts 配置的操作将应用于邮件（默认值为 "**将邮件移动到垃圾邮件" 文件夹**）。</span><span class="sxs-lookup"><span data-stu-id="10730-144">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="10730-145">若要将邮件标记为**高可信度垃圾邮件**，请选择**9**。</span><span class="sxs-lookup"><span data-stu-id="10730-145">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="10730-146">您为**高可信度垃圾**邮件筛选 verdicts 配置的操作将应用于这些邮件（默认值为 "**将邮件移动到垃圾邮件" 文件夹**）。</span><span class="sxs-lookup"><span data-stu-id="10730-146">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="10730-147">有关 SCL 值的详细信息，请参阅[Office 365 中的垃圾邮件可信度（SCL）](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="10730-147">For more information about SCL values, see [Spam confidence level (SCL) in Office 365](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="10730-148">完成后，请单击 "**保存**"</span><span class="sxs-lookup"><span data-stu-id="10730-148">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="10730-149">使用 PowerShell 创建筛选批量电子邮件的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="10730-149">Use PowerShell to create a mail flow rules that filter bulk email</span></span>

<span data-ttu-id="10730-150">使用以下语法创建一个或两个邮件流规则（正则表达式与词）：</span><span class="sxs-lookup"><span data-stu-id="10730-150">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="10730-151">本示例创建一个名为 "批量电子邮件筛选-RegEx" 的新规则，该规则使用本主题前面的相同列表中的正则表达式将邮件设置为**垃圾**邮件。</span><span class="sxs-lookup"><span data-stu-id="10730-151">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="10730-152">本示例将创建一个名为 "批量电子邮件筛选-词" 的新规则，该规则使用主题中前面的相同单词列表将邮件设置为**高可信度垃圾**邮件。</span><span class="sxs-lookup"><span data-stu-id="10730-152">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="10730-153">有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)。</span><span class="sxs-lookup"><span data-stu-id="10730-153">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="10730-154">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="10730-154">How do you know this worked?</span></span>

<span data-ttu-id="10730-155">若要验证是否已配置邮件流规则以筛选批量电子邮件，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="10730-155">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="10730-156">在 EAC 中，转到 **"邮件流** \> **规则** \> "。 \>选择该规则，](../../media/ITPro-EAC-EditIcon.png)然后单击 "**编辑** ![编辑" 图标，并验证设置。</span><span class="sxs-lookup"><span data-stu-id="10730-156">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="10730-157">在 PowerShell 中， \<将规则\>名称替换为规则名称，然后运行以下命令来验证设置：</span><span class="sxs-lookup"><span data-stu-id="10730-157">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="10730-158">从外部帐户向受影响的收件人发送一封测试邮件，其中包含一个短语或文本模式，并验证结果。</span><span class="sxs-lookup"><span data-stu-id="10730-158">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
