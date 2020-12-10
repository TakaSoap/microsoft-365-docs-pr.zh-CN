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
description: 管理员可以了解如何使用邮件流规则 (传输规则) 在 Exchange Online Protection (EOP) 中标识和筛选批量邮件 (灰色邮件) 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1f88358973648846d650700bb5939c052851c789
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615632"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>在 EOP 中使用邮件流规则筛选批量电子邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在使用 Exchange Online 或独立 Exchange online Protection 中的邮箱的 Microsoft 365 组织中 (EOP) 不含 Exchange Online 邮箱的组织中，EOP 使用反垃圾邮件 (策略（也称为垃圾邮件筛选器策略或内容筛选器策略）) 扫描入站邮件中的垃圾邮件和批量邮件 (也称为灰色邮件) 。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

如果您希望更多的选项筛选批量邮件，可以创建邮件流规则 (也称为传输规则) ，以搜索批量邮件中经常找到的文本模式或短语，并将这些邮件标记为垃圾邮件。 有关批量邮件的详细信息，请参阅 EOP 中的 [垃圾邮件和批量电子邮件之间的区别是什么？](what-s-the-difference-between-junk-email-and-bulk-email.md) 和 [批量投诉级别 (BCL) ](bulk-complaint-level-values.md)。

本主题介绍如何使用 Exchange Online 中的邮箱，在 Exchange 管理中心中创建这些邮件流规则 (EAC) 和 PowerShell (Exchange Online PowerShell for Microsoft 365 组织。没有 Exchange Online 邮箱) 组织的独立 EOP PowerShell。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 您需要先分配权限，然后才能执行这些过程：

  - 在 Exchange Online 中，请参阅在 Exchange Online 中的 [功能权限](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions)中的 "邮件流" 条目。

  - 在独立 EOP 中，您需要 "传输规则" 角色，默认情况下该角色分配给 OrganizationManagement、ComplianceManagement 和 Ecm.recordsmanagement 角色。 有关详细信息，请参阅 [独立 EOP 中的权限](feature-permissions-in-eop.md) 和 [使用 EAC 修改角色组中的成员列表](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- 若要在 Exchange Online 中打开 EAC，请参阅 exchange [online 中的 exchange 管理中心](https://docs.microsoft.com/Exchange/exchange-admin-center)。 若要在独立 EOP 中打开 EAC，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 有关 Exchange Online 和独立 EOP 中的邮件流规则的详细信息，请参阅下列主题：

  - [Exchange Online 中的邮件流规则（传输规则）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Online 中) 的邮件流规则条件和例外 (谓词](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online 中的邮件流规则操作](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- 用于标识示例中的批量邮件的单词和文本模式列表不详尽;您可以根据需要添加和删除条目。 但是，它们是一个很棒的起点。

- 在邮件已通过 MIME 内容传输编码方法（用于以 ACSII 文本方式在 SMTP 服务器之间传输二进制消息）解码 *后*，搜索邮件中主题或其他头字段中的字词或文本模式。不能使用条件或例外来搜索邮件中主题或其他头字段的原始（通常为 Base64）编码值。

- 下面的过程将批量邮件标记为您的整个组织的垃圾邮件。 但是，您可以添加另一个条件，以便仅将这些规则应用于特定的收件人，以便您可以对一些高度目标的用户使用严格筛选，而其余用户 (大多数用户在其注册) 的批量电子邮件不会受到影响。

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>使用 EAC 创建筛选批量电子邮件的邮件流规则

1. In the EAC, go to **Mail flow** \> **Rules**.

2. 单击 " **添加**" "添加" ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) ，然后选择 " **创建新规则**"。

3. 在打开的" **新规则**"窗口中，配置以下设置：

   - **名称**：输入规则的唯一描述性名称。

   - 单击“其他选项”。

   - **在以下情况下应用此规则**：配置以下设置之一，以使用正则表达式 (RegEx) 或字词或短语查找邮件中的内容：

     - **主题或正文** \>**主题或正文与这些文本模式匹配**：在显示的 "**指定字词或短语**" 对话框中，输入以下值之一，单击 "**添加** ![ " "添加 ](../../media/ITPro-EAC-AddIcon.png) " 图标，然后重复此步骤，直到您输入所有值。

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

      若要编辑条目，请选择该条目，然后单击 " **编辑**" "编辑" ![ 图标 ](../../media/ITPro-EAC-EditIcon.png) 。 若要删除条目，请将其选中，然后单击 " **删除** ![ 删除图标" ](../../media/ITPro-EAC-DeleteIcon.png) 。

       完成后，请单击 **"确定"**。

     - **主题或正文** \>**主题或正文包含以下任何词语**：在显示的 "**指定字词或短语**" 对话框中，输入以下值之一，单击 "**添加**" "添加" ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) ，然后重复此步骤，直到您输入所有值。

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

      若要编辑条目，请选择该条目，然后单击 " **编辑**" "编辑" ![ 图标 ](../../media/ITPro-EAC-EditIcon.png) 。 若要删除条目，请将其选中，然后单击 " **删除** ![ 删除图标" ](../../media/ITPro-EAC-DeleteIcon.png) 。

       完成后，请单击 **"确定"**。

   - **执行以下** 操作：选择 " **修改邮件属性** \> **"。 (SCL) 设置垃圾邮件可信度级别**。 在出现的 " **指定 SCL** " 对话框中，配置以下设置之一：

     - 若要将邮件标记为 **垃圾** 邮件，请选择 " **6**"。 您为反垃圾邮件策略中的 **垃圾** 邮件筛选 verdicts 配置的操作将应用于邮件， (默认值将 **邮件移动到 "垃圾邮件" 文件夹**) 。

     - 若要将邮件标记为 **高可信度垃圾邮件** ，请选择 **9**。 您为 **高可信度垃圾** 邮件筛选 verdicts 配置的操作将应用于您的反垃圾邮件策略中的邮件， (默认值将 **邮件移动到 "垃圾邮件" 文件夹**) 。

    有关 SCL 值的详细信息，请参阅 [EOP 中的垃圾邮件可信度级别 (SCL) ](spam-confidence-levels.md)。

   完成后，请单击 "**保存**"

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>使用 PowerShell 创建筛选批量电子邮件的邮件流规则

使用以下语法创建一个或两个邮件流规则 (正则表达式与词) ：

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

本示例创建一个名为 "批量电子邮件筛选-RegEx" 的新规则，该规则使用本主题前面的相同列表中的正则表达式将邮件设置为 **垃圾** 邮件。

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

本示例将创建一个名为 "批量电子邮件筛选-词" 的新规则，该规则使用主题中前面的相同单词列表将邮件设置为 **高可信度垃圾** 邮件。

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)。

## <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证是否已配置邮件流规则以筛选批量电子邮件，请执行以下任一步骤：

- 在 EAC 中，转到 " **邮件流** \> **规则**"。 \> 选择该规则 \> ，然后单击 " **编辑** ![ 编辑 ](../../media/ITPro-EAC-EditIcon.png) " 图标，并验证设置。

- 在 PowerShell 中，将替换 \<Rule Name\> 为规则名称，然后运行以下命令来验证设置：

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- 从外部帐户向受影响的收件人发送一封测试邮件，其中包含一个短语或文本模式，并验证结果。
