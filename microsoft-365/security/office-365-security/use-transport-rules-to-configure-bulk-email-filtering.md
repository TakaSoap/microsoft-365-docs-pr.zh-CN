---
title: 使用邮件流规则筛选批量电子邮件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何使用邮件流规则 (传输规则)  (在 Exchange Online Protection 和 EOP) 中标识和筛选批量) 邮件 粒度 (邮件) 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfe841d3e80efc50d6ffbc702faefa1c9a971b13
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826749"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="800fc-103">在 EOP 中使用邮件流规则筛选批量电子邮件</span><span class="sxs-lookup"><span data-stu-id="800fc-103">Use mail flow rules to filter bulk email in EOP</span></span>

<span data-ttu-id="800fc-104">在具有 Exchange Online 邮箱的 Microsoft 365 组织中或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 使用反垃圾邮件策略 (也称为垃圾邮件筛选器策略或内容筛选器策略) 来扫描入站邮件中的垃圾邮件和大量邮件 (也称为灰色邮件) 。</span><span class="sxs-lookup"><span data-stu-id="800fc-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="800fc-105">有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="800fc-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="800fc-106">如果需要更多选项筛选批量邮件，可以创建邮件流规则 (也称为传输规则) 来搜索批量邮件中经常找到的文本模式或短语，并将这些邮件标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="800fc-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="800fc-107">有关批量邮件的详细信息，请参阅[垃圾邮件和批量邮件](what-s-the-difference-between-junk-email-and-bulk-email.md)之间有什么差异？以及批量校准级别[（EOP (BCL) 。](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="800fc-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="800fc-108">本主题介绍了如何在 Exchange 管理中心 (EAC) 和在具有 Exchange Online 邮箱的 Microsoft 365 组织的 Exchange 管理中心 (PowerShell 中创建这些邮件流规则;独立 EOP PowerShell 适用于没有 Exchange Online 邮箱和站点) 。</span><span class="sxs-lookup"><span data-stu-id="800fc-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="800fc-109">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="800fc-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="800fc-110">您必须先拥有权限，然后才能执行以下过程：</span><span class="sxs-lookup"><span data-stu-id="800fc-110">You need to be assigned permissions before you can do these procedures:</span></span>

  - <span data-ttu-id="800fc-111">在 Exchange Online 中，请参阅 Exchange Online 功能权限中的 ["邮件流"条目](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions)。</span><span class="sxs-lookup"><span data-stu-id="800fc-111">In Exchange Online, see the "Mail flow" entry in [Feature Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).</span></span>
  
  - <span data-ttu-id="800fc-112">在独立 EOP 中，您必需的是，该角色默认分配到 OrganizationManagement、ComplianceManagement 和 RecordsManagement 角色。</span><span class="sxs-lookup"><span data-stu-id="800fc-112">In standalone EOP, you need the Transport Rules role, which is assigned to the OrganizationManagement, ComplianceManagement, and RecordsManagement roles by default.</span></span> <span data-ttu-id="800fc-113">有关详细信息，请参阅独立[EOP 中的"权限](feature-permissions-in-eop.md)["和"使用 EAC 修改角色组中的成员列表"。](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="800fc-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="800fc-114">若要在 Exchange Online 中打开 EAC，请参阅[Exchange Online 中的"Exchange 管理中心"。](https://docs.microsoft.com/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="800fc-114">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="800fc-115">若要在独立 EOP 中打开 EAC，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="800fc-115">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="800fc-116">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="800fc-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="800fc-117">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="800fc-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="800fc-118">若要详细了解 Exchange Online 和独立 EOP 中的邮件流规则，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="800fc-118">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="800fc-119">Exchange Online 中的邮件流规则（传输规则）</span><span class="sxs-lookup"><span data-stu-id="800fc-119">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="800fc-120">在 Exchange Online 中预测 (邮件流规则) 条件和异常</span><span class="sxs-lookup"><span data-stu-id="800fc-120">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="800fc-121">Exchange Online 中的邮件流规则操作</span><span class="sxs-lookup"><span data-stu-id="800fc-121">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="800fc-122">用于识别示例中的批量邮件的字词和文本模式列表并不具有任何特色;您可以根据需要添加和删除条目。</span><span class="sxs-lookup"><span data-stu-id="800fc-122">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="800fc-123">但是，它们是一个很好的起点。</span><span class="sxs-lookup"><span data-stu-id="800fc-123">However, they are a good starting point.</span></span>

- <span data-ttu-id="800fc-p107">在邮件已通过 MIME 内容传输编码方法（用于以 ACSII 文本方式在 SMTP 服务器之间传输二进制消息）解码*后*，搜索邮件中主题或其他头字段中的字词或文本模式。不能使用条件或例外来搜索邮件中主题或其他头字段的原始（通常为 Base64）编码值。</span><span class="sxs-lookup"><span data-stu-id="800fc-p107">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="800fc-126">下面的步骤为您的整个组织将批量邮件标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="800fc-126">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="800fc-127">但是，您可以添加其他条件以仅将这些规则应用于特定收件人，因此，你可以针对针对高度针对性较高的用户进行积累筛选，同时又重大限于这些用户注册了) 的批量电子邮件的其余 (不受影响。</span><span class="sxs-lookup"><span data-stu-id="800fc-127">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="800fc-128">使用 EAC 创建对批量电子邮件进行筛选的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="800fc-128">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="800fc-129">In the EAC, go to **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="800fc-129">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="800fc-130">单击 **"添加** ![ " ](../../media/ITPro-EAC-AddIcon.png) 图标，然后选择"**创建新规则"。**</span><span class="sxs-lookup"><span data-stu-id="800fc-130">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="800fc-131">在打开的" **新规则**"窗口中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="800fc-131">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="800fc-132">**名称**：输入规则的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="800fc-132">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="800fc-133">单击“其他选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="800fc-133">Click **More Options**.</span></span>

   - <span data-ttu-id="800fc-134">**在以下情况应用此**规则：配置以下设置之一以使用正则表达式或字词或短语)  (查找邮件中的内容：</span><span class="sxs-lookup"><span data-stu-id="800fc-134">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="800fc-135">**主题或正文** \>**主题或正文与这些文本模式**匹配：在**显示的"指定词语或短**语"对话框中，输入下列值之一，单击**Add** ![ "添加图标 ](../../media/ITPro-EAC-AddIcon.png) "，重复执行，直到您输入所有值。</span><span class="sxs-lookup"><span data-stu-id="800fc-135">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="800fc-136">若要编辑条目，请将其选中，然后单击**Edit**"编辑 ![ "图标 ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="800fc-136">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="800fc-137">若要删除条目，请选中它，并单击" **删除"** ![ 图标 ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="800fc-137">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="800fc-138">完成后，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="800fc-138">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="800fc-139">**主题或正文** \>**主题或正文包括以下任何词**语：在**显示的"指定词语或短**语"对话框中，输入下列值之一，再单击**Add** ![ "添加图标 ](../../media/ITPro-EAC-AddIcon.png) "，重复执行，直到您输入所有值。</span><span class="sxs-lookup"><span data-stu-id="800fc-139">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="800fc-140">若要编辑条目，请将其选中，然后单击**Edit**"编辑 ![ "图标 ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="800fc-140">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="800fc-141">若要删除条目，请选中它，并单击" **删除"** ![ 图标 ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="800fc-141">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="800fc-142">完成后，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="800fc-142">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="800fc-143">**执行以下操作：** 选择 **"修改邮件属性** \> \*\*"，然后将垃圾邮件可信度设为 (SCL) 。 \*\*</span><span class="sxs-lookup"><span data-stu-id="800fc-143">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="800fc-144">在出现 **的"指定 SCL"** 对话框中，配置下列设置之一：</span><span class="sxs-lookup"><span data-stu-id="800fc-144">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="800fc-145">要将邮件标记为**垃圾邮件，** 请选择 **"6"。**</span><span class="sxs-lookup"><span data-stu-id="800fc-145">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="800fc-146">您在反垃圾邮件策略中为 **垃圾邮件** 筛选欺词配置的操作将应用于邮件 (默认值为 **将邮件移动到垃圾邮件文件夹** 的) 。</span><span class="sxs-lookup"><span data-stu-id="800fc-146">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="800fc-147">要将邮件标记为 **"高可信度垃圾邮件"，\*\*\*\*请选择 9。**</span><span class="sxs-lookup"><span data-stu-id="800fc-147">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="800fc-148">您在反垃圾邮件策略中为 **高可信度垃圾邮件** 筛选反应器配置的操作适用于邮件 (默认值为 **将邮件移至垃圾邮件文件夹**) 。</span><span class="sxs-lookup"><span data-stu-id="800fc-148">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="800fc-149">有关 SCL 值的详细信息，请参阅 ["垃圾邮件可信度 (EOP 中) SCL 策略](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="800fc-149">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="800fc-150">完成后，请单击"保存 **"**</span><span class="sxs-lookup"><span data-stu-id="800fc-150">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="800fc-151">使用 PowerShell 创建筛选批量电子邮件的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="800fc-151">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="800fc-152">使用以下语法创建一个或多个由正则表达式与单词 (或多个单词) ：</span><span class="sxs-lookup"><span data-stu-id="800fc-152">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="800fc-153">本示例创建名为"批量电子邮件筛选 - RegEx"的新规则，该规则使用与本主题前面介绍的正则表达式相同的列表来将邮件设置为 **垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="800fc-153">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="800fc-154">本示例创建名为"Bulk email filtering - Words"的新规则，该规则使用与本主题前面的单词相同的单词列表来将邮件设置为 **高可信度垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="800fc-154">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="800fc-155">有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)。</span><span class="sxs-lookup"><span data-stu-id="800fc-155">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="800fc-156">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="800fc-156">How do you know this worked?</span></span>

<span data-ttu-id="800fc-157">要验证是否已配置邮件流规则以筛选批量电子邮件，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="800fc-157">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="800fc-158">在 EAC 中，转到"**邮件流规则** \> **"** \> 后，选择规则 \> ，单击"**Edit** ![ 编辑" ](../../media/ITPro-EAC-EditIcon.png) 图标，然后验证设置。</span><span class="sxs-lookup"><span data-stu-id="800fc-158">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="800fc-159">在 PowerShell \<Rule Name\> 中，将规则名称替换为规则，并运行以下命令来验证设置：</span><span class="sxs-lookup"><span data-stu-id="800fc-159">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="800fc-160">从外部帐户向受影响的收件人发送包含短语或文本模式之一的测试邮件，然后验证结果。</span><span class="sxs-lookup"><span data-stu-id="800fc-160">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
