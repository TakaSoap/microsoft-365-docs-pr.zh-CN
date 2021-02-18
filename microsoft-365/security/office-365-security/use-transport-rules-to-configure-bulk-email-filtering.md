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
description: 管理员可以了解如何使用邮件流规则 (传输规则) 来标识和筛选 Exchange Online Protection (EOP) 中的批量邮件 (邮件) 。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8030d21d414cb38769a6831391262fa3798a8838
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287289"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>在 EOP 中使用邮件流规则筛选批量电子邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

在邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱的 Microsoft 365 组织中，EOP 使用反垃圾邮件策略 (也称为垃圾邮件筛选器策略或内容筛选器策略) 扫描入站邮件中的垃圾邮件和批量邮件 (也称为灰色邮件) 。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

如果您希望更多选项来筛选批量邮件，可以创建邮件流规则 (也称为传输规则) ，以搜索批量邮件中经常找到的文本模式或短语，并标记这些邮件为垃圾邮件。 有关批量邮件详细信息，请参阅 EOP 中的[BCL](bulk-complaint-level-values.md) (批量投诉级别和批量投诉级别) 之间有什么区别。 [](what-s-the-difference-between-junk-email-and-bulk-email.md)

本主题介绍如何在 Exchange 管理中心 (EAC) 和 PowerShell (Exchange Online PowerShell（适用于在 Exchange Online 中拥有邮箱的 Microsoft 365 组织）创建这些邮件流规则;适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 您需要在 Exchange Online 或 Exchange Online Protection 中分配权限，然后才能执行本文中的过程。 具体来说，您需要传输规则角色，该角色默认分配给组织管理、合规性 **管理 (全局** 管理员) 和 **记录** 管理角色组。

  有关详细信息，请参阅下列主题：

  - [Exchange Online 中的权限](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [独立 EOP 中的权限](feature-permissions-in-eop.md)
  - [使用 EAC 修改角色组的成员列表](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- 若要在 Exchange Online 中打开 EAC，请参阅 [Exchange Online 中的 Exchange 管理中心](https://docs.microsoft.com/Exchange/exchange-admin-center)。 若要在独立 EOP 中打开 EAC，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 有关 Exchange Online 和独立 EOP 中的邮件流规则详细信息，请参阅下列主题：

  - [Exchange Online 中的邮件流规则（传输规则）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Online 中的邮件流规则 (和) 例外](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online 中的邮件流规则操作](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- 示例中用于标识批量邮件的单词和文本模式列表并不详尽;可以根据需要添加和删除条目。 但是，它们是一个很好的起点。

- 在邮件已通过 MIME 内容传输编码方法（用于以 ACSII 文本方式在 SMTP 服务器之间传输二进制消息）解码 *后*，搜索邮件中主题或其他头字段中的字词或文本模式。不能使用条件或例外来搜索邮件中主题或其他头字段的原始（通常为 Base64）编码值。

- 以下过程将批量邮件标记为整个组织的垃圾邮件。 但是，您可以添加另一个条件，以便仅将这些规则应用于特定收件人，以便对一些高度目标用户使用主动筛选，而其余用户 (他们通常收到注册为) 的批量电子邮件不会受到影响。

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>使用 EAC 创建筛选批量电子邮件的邮件流规则

1. In the EAC, go to **Mail flow** \> **Rules**.

2. 单击 **"添加** ![ " ](../../media/ITPro-EAC-AddIcon.png) 图标，然后选择 **"创建新规则"。**

3. 在打开的" **新规则**"窗口中，配置以下设置：

   - **名称**：为规则输入唯一的描述性名称。

   - 单击“其他选项”。

   - **在以下情况应用** 此规则：配置以下设置之一，以使用正则表达式或 RegEx (或字词或短语) 邮件中查找内容：

     - **主题或正文** \>**主题或** 正文与这些文本模式匹配：在出现的"指定单词或短语"对话框中，输入下列值之一，单击"添加图标"，然后重复操作，直到输入所有 ![ ](../../media/ITPro-EAC-AddIcon.png) 值。

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

      若要编辑条目，请选择它，然后单击 **"编辑编辑"** ![ 图标 ](../../media/ITPro-EAC-EditIcon.png) 。 若要删除条目，请选择它，然后单击 **"删除删除** ![ "图标 ](../../media/ITPro-EAC-DeleteIcon.png) 。

       完成后，单击"确定 **"。**

     - **主题或正文** \>**主题或正文** 包含以下任何词语：在出现的"指定单词或短语"对话框中，输入下列值之一，单击"添加图标"，然后重复操作，直到输入所有 ![ ](../../media/ITPro-EAC-AddIcon.png) 值。

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

      若要编辑条目，请选择它，然后单击 **"编辑编辑"** ![ 图标 ](../../media/ITPro-EAC-EditIcon.png) 。 若要删除条目，请选择它，然后单击 **"删除删除** ![ "图标 ](../../media/ITPro-EAC-DeleteIcon.png) 。

       完成后，单击"确定 **"。**

   - **执行以下操作：** 选择 **"修改邮件属性** \> **"设置 SCL (垃圾邮件可信度) 。** 在 **出现的"指定 SCL"** 对话框中，配置以下设置之一：

     - 若要将邮件标记为 **垃圾邮件**，请选择 **6**。 为反垃圾邮件策略中的垃圾邮件筛选裁定配置的操作将应用于 (默认值为"将邮件移动到垃圾邮件"文件夹) 。 

     - 若要将邮件标记为 **高可信度垃圾邮件，** 请选择 **9**。 为反垃圾邮件策略中的高可信度垃圾邮件筛选裁定配置的操作将应用于邮件 (默认值为"将邮件移动到垃圾邮件"文件夹) 。 

    有关 SCL 值详细信息，请参阅 EOP 中 [SCL](spam-confidence-levels.md) (的) 可信度。

   完成后，单击"保存 **"**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>使用 PowerShell 创建筛选批量电子邮件的邮件流规则

使用以下语法创建一个或两个使用正则表达式 (邮件流规则。) ：

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

本示例创建一个名为"Bulk email filtering - RegEx"的新规则，该规则使用本主题前面部分中的同一正则表达式列表将邮件设置为 **"垃圾邮件"。**

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

本示例创建一个名为"Bulk email filtering - Words"的新规则，该规则使用本主题前面部分中的相同单词列表将邮件设置为 **高可信度垃圾邮件**。

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)。

## <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证您是否已配置邮件流规则以筛选批量电子邮件，请执行下列任一步骤：

- 在 EAC 中，转到"**邮件流** \> **规则**" \> 选择规则 \> ，单击"编辑编辑" ![ 图标 ](../../media/ITPro-EAC-EditIcon.png) ，然后验证设置。

- 在 PowerShell 中 \<Rule Name\> ，替换为规则的名称，并运行以下命令来验证设置：

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- 从外部帐户向包含其中一个短语或文本模式受影响的收件人发送测试邮件，并验证结果。
