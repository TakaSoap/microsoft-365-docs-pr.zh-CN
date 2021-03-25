---
title: 使用邮件流规则筛选批量电子邮件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何使用邮件流规则 (传输规则) Exchange Online Protection (EOP) 中的批量邮件 (邮件) 。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c86f229d6c7371854878a67937cc38374ed00961
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203703"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="210b8-103">在 EOP 中使用邮件流规则筛选批量电子邮件</span><span class="sxs-lookup"><span data-stu-id="210b8-103">Use mail flow rules to filter bulk email in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="210b8-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="210b8-104">**Applies to**</span></span>
- [<span data-ttu-id="210b8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="210b8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="210b8-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="210b8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="210b8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="210b8-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="210b8-108">在邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱的 Microsoft 365 组织中，EOP 使用反垃圾邮件策略 (也称为垃圾邮件筛选器策略或内容筛选器策略) 扫描入站邮件中的垃圾邮件和批量邮件 (也称为灰色邮件) 。</span><span class="sxs-lookup"><span data-stu-id="210b8-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="210b8-109">有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="210b8-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="210b8-110">如果您希望更多选项来筛选批量邮件，可以创建邮件流规则 (也称为传输规则) 以搜索批量邮件中经常发现的文本模式或短语，并标记这些邮件为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="210b8-110">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="210b8-111">有关批量邮件详细信息，请参阅垃圾邮件和批量邮件之间有什么区别 [？](what-s-the-difference-between-junk-email-and-bulk-email.md) 和批量投诉级别 (BCL) [EOP 中](bulk-complaint-level-values.md)。</span><span class="sxs-lookup"><span data-stu-id="210b8-111">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="210b8-112">本主题介绍如何在 Exchange 管理中心 (EAC) 和 PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的 Microsoft 365 组织创建这些邮件流规则;适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="210b8-112">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="210b8-113">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="210b8-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="210b8-114">您需在 Exchange Online 或 Exchange Online Protection 中分配权限，然后才能执行本文中的过程。</span><span class="sxs-lookup"><span data-stu-id="210b8-114">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="210b8-115">具体来说，您需要传输规则角色，默认情况下，该角色分配给组织管理、合规性 **管理 (全局** 管理员) 角色组和 **记录** 管理角色组。</span><span class="sxs-lookup"><span data-stu-id="210b8-115">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="210b8-116">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="210b8-116">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="210b8-117">Exchange Online 中的权限</span><span class="sxs-lookup"><span data-stu-id="210b8-117">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="210b8-118">独立 EOP 中的权限</span><span class="sxs-lookup"><span data-stu-id="210b8-118">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="210b8-119">使用 EAC 修改角色组的成员列表</span><span class="sxs-lookup"><span data-stu-id="210b8-119">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="210b8-120">若要在 Exchange Online 中打开 EAC，请参阅 [Exchange Online 中的 Exchange 管理中心](/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="210b8-120">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="210b8-121">若要在独立 EOP 中打开 EAC，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="210b8-121">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="210b8-122">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="210b8-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="210b8-123">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="210b8-123">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="210b8-124">有关 Exchange Online 和独立 EOP 中的邮件流规则详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="210b8-124">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="210b8-125">Exchange Online 中的邮件流规则（传输规则）</span><span class="sxs-lookup"><span data-stu-id="210b8-125">Mail flow rules (transport rules) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="210b8-126">Exchange Online 中的邮件流规则 (和) 谓词</span><span class="sxs-lookup"><span data-stu-id="210b8-126">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="210b8-127">Exchange Online 中的邮件流规则操作</span><span class="sxs-lookup"><span data-stu-id="210b8-127">Mail flow rule actions in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="210b8-128">示例中用于标识批量邮件的字词和文本模式列表并不详尽;可以根据需要添加和删除条目。</span><span class="sxs-lookup"><span data-stu-id="210b8-128">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="210b8-129">但是，它们是一个很好的起点。</span><span class="sxs-lookup"><span data-stu-id="210b8-129">However, they are a good starting point.</span></span>

- <span data-ttu-id="210b8-p107">在邮件已通过 MIME 内容传输编码方法（用于以 ACSII 文本方式在 SMTP 服务器之间传输二进制消息）解码 *后*，搜索邮件中主题或其他头字段中的字词或文本模式。不能使用条件或例外来搜索邮件中主题或其他头字段的原始（通常为 Base64）编码值。</span><span class="sxs-lookup"><span data-stu-id="210b8-p107">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="210b8-132">以下过程将整个组织的批量邮件标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="210b8-132">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="210b8-133">但是，您可以添加另一个条件以仅将这些规则应用于特定收件人，以便您可以对一些高度目标用户使用积极筛选，而其余主要获得注册) 的批量电子邮件的 (则不会影响这些用户。</span><span class="sxs-lookup"><span data-stu-id="210b8-133">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="210b8-134">使用 EAC 创建筛选批量电子邮件的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="210b8-134">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="210b8-135">In the EAC, go to **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="210b8-135">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="210b8-136">单击 **添加** ![ 添加图标 ](../../media/ITPro-EAC-AddIcon.png) ，然后选择 **创建新规则**。</span><span class="sxs-lookup"><span data-stu-id="210b8-136">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="210b8-137">在打开的" **新规则**"窗口中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="210b8-137">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="210b8-138">**名称**：输入规则的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="210b8-138">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="210b8-139">单击“其他选项”。</span><span class="sxs-lookup"><span data-stu-id="210b8-139">Click **More Options**.</span></span>

   - <span data-ttu-id="210b8-140">**在 以下情况** 应用此规则：配置以下设置之一，以使用正则表达式 (RegEx) 或短语查找邮件中的内容：</span><span class="sxs-lookup"><span data-stu-id="210b8-140">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="210b8-141">**主题或正文** \>**主题或正文** 匹配这些文本模式：在出现的"指定字词或短语"对话框中，输入下列值之一，单击"添加添加图标"，然后重复，直到输入所有 ![ ](../../media/ITPro-EAC-AddIcon.png) 值。</span><span class="sxs-lookup"><span data-stu-id="210b8-141">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      <span data-ttu-id="210b8-142">若要编辑条目，请选择它，然后单击编辑 **编辑** ![ 图标 ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="210b8-142">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="210b8-143">若要删除条目，请选择它，然后单击删除 **删除** ![ 图标 ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="210b8-143">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="210b8-144">完成后，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="210b8-144">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="210b8-145">**主题或正文** \>**subject 或 body** 包含以下任何词语：在出现的"指定字词或短语"对话框中，输入下列值之一，单击"添加添加图标"，然后重复，直到输入所有 ![ ](../../media/ITPro-EAC-AddIcon.png) 值。</span><span class="sxs-lookup"><span data-stu-id="210b8-145">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="210b8-146">若要编辑条目，请选择它，然后单击编辑 **编辑** ![ 图标 ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="210b8-146">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="210b8-147">若要删除条目，请选择它，然后单击删除 **删除** ![ 图标 ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="210b8-147">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="210b8-148">完成后，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="210b8-148">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="210b8-149">**执行以下操作：选择\*\*\*\*"修改邮件属性** \> **"设置 SCL (垃圾邮件可信度) 。**</span><span class="sxs-lookup"><span data-stu-id="210b8-149">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="210b8-150">在出现的 **"指定 SCL"** 对话框中，配置以下设置之一：</span><span class="sxs-lookup"><span data-stu-id="210b8-150">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="210b8-151">若要将邮件标记为 **"垃圾邮件"，** 请选择 **"6"。**</span><span class="sxs-lookup"><span data-stu-id="210b8-151">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="210b8-152">为反垃圾邮件策略中的垃圾邮件筛选裁定配置的操作将应用于 (默认值为"将邮件移动到垃圾邮件文件夹") 。 </span><span class="sxs-lookup"><span data-stu-id="210b8-152">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="210b8-153">若要将邮件标记为 **"高可信度垃圾邮件"，** 请选择 **"9"。**</span><span class="sxs-lookup"><span data-stu-id="210b8-153">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="210b8-154">为反垃圾邮件策略中的高可信度垃圾邮件筛选裁定配置的操作将应用于邮件 (默认值为"将邮件移动到垃圾邮件文件夹") 。 </span><span class="sxs-lookup"><span data-stu-id="210b8-154">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="210b8-155">有关 SCL 值详细信息，请参阅 EOP 中的垃圾邮件 [ (SCL](spam-confidence-levels.md)) 级别。</span><span class="sxs-lookup"><span data-stu-id="210b8-155">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="210b8-156">完成后，单击"保存 **"**</span><span class="sxs-lookup"><span data-stu-id="210b8-156">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="210b8-157">使用 PowerShell 创建筛选批量电子邮件的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="210b8-157">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="210b8-158">使用以下语法创建正则表达式中的一个或两个邮件流规则 (与单词) ：</span><span class="sxs-lookup"><span data-stu-id="210b8-158">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="210b8-159">本示例创建一个名为"Bulk email filtering - RegEx"的新规则，该规则使用本主题前面部分中的同一正则表达式列表将邮件设置为 **"垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="210b8-159">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="210b8-160">本示例创建一个名为"批量电子邮件筛选 - 单词"的新规则，该规则使用本主题前面部分中的相同单词列表将邮件设置为 **高可信度垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="210b8-160">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="210b8-161">有关语法和参数的详细信息，请参阅 [New-TransportRule](/powershell/module/exchange/new-transportrule)。</span><span class="sxs-lookup"><span data-stu-id="210b8-161">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="210b8-162">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="210b8-162">How do you know this worked?</span></span>

<span data-ttu-id="210b8-163">若要验证是否配置了邮件流规则以筛选批量电子邮件，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="210b8-163">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="210b8-164">在 EAC 中，转到"**邮件** 流""规则 \>  \> "选择规则单击" \> **编辑** ![ 编辑"图标 ](../../media/ITPro-EAC-EditIcon.png) ，然后验证设置。</span><span class="sxs-lookup"><span data-stu-id="210b8-164">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="210b8-165">在 PowerShell 中， \<Rule Name\> 将 替换为规则名称，然后运行以下命令来验证设置：</span><span class="sxs-lookup"><span data-stu-id="210b8-165">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="210b8-166">从外部帐户向包含短语或文本模式之一的受影响收件人发送测试邮件，并验证结果。</span><span class="sxs-lookup"><span data-stu-id="210b8-166">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>