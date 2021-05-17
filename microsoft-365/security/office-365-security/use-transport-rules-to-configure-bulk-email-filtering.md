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
description: 管理员可以了解如何使用邮件流规则 (传输规则) EOP (中的 (邮件) 邮件Exchange Online Protection (邮件) 。
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
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>在 EOP 中使用邮件流规则筛选批量电子邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在 Microsoft 365 组织中，邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱，EOP 使用反垃圾邮件策略 (也称为垃圾邮件筛选器策略或内容筛选器策略) 扫描入站邮件中的垃圾邮件和批量邮件 (也称为灰色邮件) 。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

如果您希望更多选项来筛选批量邮件，可以创建邮件流规则 (也称为传输规则) 以搜索批量邮件中经常发现的文本模式或短语，并标记这些邮件为垃圾邮件。 有关批量邮件详细信息，请参阅垃圾邮件和批量邮件之间有什么区别 [？](what-s-the-difference-between-junk-email-and-bulk-email.md) 和批量投诉级别 (BCL) [EOP 中](bulk-complaint-level-values.md)。

本主题介绍如何在 Exchange 管理中心 (EAC) 和 PowerShell (Exchange Online PowerShell 中为 Microsoft 365 组织创建这些邮件流规则，Exchange Online;适用于没有邮箱或邮箱Exchange Online的独立 EOP PowerShell) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 您需在 Exchange Online 或 Exchange Online Protection 权限，然后才能执行本文中的过程。 具体来说，您需要传输规则角色，默认情况下，该角色分配给组织管理、合规性 **管理 (全局** 管理员) 角色组和 **记录** 管理角色组。

  有关详细信息，请参阅下列主题：

  - [Exchange Online 中的权限](/exchange/permissions-exo/permissions-exo)
  - [独立 EOP 中的权限](feature-permissions-in-eop.md)
  - [使用 EAC 修改角色组的成员列表](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- 若要在管理中心中Exchange Online EAC，Exchange[管理中心Exchange Online。](/Exchange/exchange-admin-center) 若要在独立 EOP 中打开 EAC，请参阅Exchange [EOP 中的管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 有关独立 EOP 中的邮件流规则Exchange Online，请参阅下列主题：

  - [Exchange Online 中的邮件流规则（传输规则）](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Online 中的邮件流规则条件和例外（谓词）](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online 中的邮件流规则操作](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- 示例中用于标识批量邮件的字词和文本模式列表并不详尽;可以根据需要添加和删除条目。 但是，它们是一个很好的起点。

- 在邮件已通过 MIME 内容传输编码方法（用于以 ACSII 文本方式在 SMTP 服务器之间传输二进制消息）解码 *后*，搜索邮件中主题或其他头字段中的字词或文本模式。不能使用条件或例外来搜索邮件中主题或其他头字段的原始（通常为 Base64）编码值。

- 以下过程将整个组织的批量邮件标记为垃圾邮件。 但是，您可以添加另一个条件以仅将这些规则应用于特定收件人，以便您可以对一些高度目标用户使用积极筛选，而其余主要获得注册) 的批量电子邮件的 (则不会影响这些用户。

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>使用 EAC 创建筛选批量电子邮件的邮件流规则

1. In the EAC, go to **Mail flow** \> **Rules**.

2. 单击 **添加** ![ 添加图标 ](../../media/ITPro-EAC-AddIcon.png) ，然后选择 **创建新规则**。

3. 在打开的" **新规则**"窗口中，配置以下设置：

   - **名称**：输入规则的唯一描述性名称。

   - 单击“其他选项”。

   - **在 以下情况** 应用此规则：配置以下设置之一，以使用正则表达式 (RegEx) 或短语查找邮件中的内容：

     - **主题或正文** \>**主题或正文** 匹配这些文本模式：在出现的"指定字词或短语"对话框中，输入下列值之一，单击"添加添加图标"，然后重复，直到输入所有 ![ ](../../media/ITPro-EAC-AddIcon.png) 值。

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

      若要编辑条目，请选择它，然后单击编辑 **编辑** ![ 图标 ](../../media/ITPro-EAC-EditIcon.png) 。 若要删除条目，请选择它，然后单击删除 **删除** ![ 图标 ](../../media/ITPro-EAC-DeleteIcon.png) 。

       完成后，单击"确定 **"。**

     - **主题或正文** \>**subject 或 body** 包含以下任何词语：在出现的"指定字词或短语"对话框中，输入下列值之一，单击"添加添加图标"，然后重复，直到输入所有 ![ ](../../media/ITPro-EAC-AddIcon.png) 值。

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

      若要编辑条目，请选择它，然后单击编辑 **编辑** ![ 图标 ](../../media/ITPro-EAC-EditIcon.png) 。 若要删除条目，请选择它，然后单击删除 **删除** ![ 图标 ](../../media/ITPro-EAC-DeleteIcon.png) 。

       完成后，单击"确定 **"。**

   - **执行以下操作：选择****"修改邮件属性** \> **"设置 SCL (垃圾邮件可信度) 。** 在出现的 **"指定 SCL"** 对话框中，配置以下设置之一：

     - 若要将邮件标记为 **"垃圾邮件"，** 请选择 **"6"。** 为反垃圾邮件策略中的垃圾邮件筛选裁定配置的操作将应用于 (默认值为"将邮件移动到垃圾邮件文件夹") 。 

     - 若要将邮件标记为 **"高可信度垃圾邮件"，** 请选择 **"9"。** 为反垃圾邮件策略中的高可信度垃圾邮件筛选裁定配置的操作将应用于邮件 (默认值为"将邮件移动到垃圾邮件文件夹") 。 

    有关 SCL 值详细信息，请参阅 EOP 中的垃圾邮件 [ (SCL](spam-confidence-levels.md)) 级别。

   完成后，单击"保存 **"**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>使用 PowerShell 创建筛选批量电子邮件的邮件流规则

使用以下语法创建正则表达式中的一个或两个邮件流规则 (与单词) ：

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

本示例创建一个名为"Bulk email filtering - RegEx"的新规则，该规则使用本主题前面部分中的同一正则表达式列表将邮件设置为 **"垃圾邮件"。**

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

本示例创建一个名为"批量电子邮件筛选 - 单词"的新规则，该规则使用本主题前面部分中的相同单词列表将邮件设置为 **高可信度垃圾邮件**。

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

有关语法和参数的详细信息，请参阅 [New-TransportRule](/powershell/module/exchange/new-transportrule)。

## <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证是否配置了邮件流规则以筛选批量电子邮件，请执行下列任一步骤：

- 在 EAC 中，转到"**邮件** 流""规则 \>  \> "选择规则单击" \> **编辑** ![ 编辑"图标 ](../../media/ITPro-EAC-EditIcon.png) ，然后验证设置。

- 在 PowerShell 中， \<Rule Name\> 将 替换为规则名称，然后运行以下命令来验证设置：

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- 从外部帐户向包含短语或文本模式之一的受影响收件人发送测试邮件，并验证结果。