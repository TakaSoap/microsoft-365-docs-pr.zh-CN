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
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>在 EOP 中使用邮件流规则筛选批量电子邮件

在具有 Exchange Online 邮箱的 Microsoft 365 组织中或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 使用反垃圾邮件策略 (也称为垃圾邮件筛选器策略或内容筛选器策略) 来扫描入站邮件中的垃圾邮件和大量邮件 (也称为灰色邮件) 。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

如果需要更多选项筛选批量邮件，可以创建邮件流规则 (也称为传输规则) 来搜索批量邮件中经常找到的文本模式或短语，并将这些邮件标记为垃圾邮件。 有关批量邮件的详细信息，请参阅[垃圾邮件和批量邮件](what-s-the-difference-between-junk-email-and-bulk-email.md)之间有什么差异？以及批量校准级别[（EOP (BCL) 。](bulk-complaint-level-values.md)

本主题介绍了如何在 Exchange 管理中心 (EAC) 和在具有 Exchange Online 邮箱的 Microsoft 365 组织的 Exchange 管理中心 (PowerShell 中创建这些邮件流规则;独立 EOP PowerShell 适用于没有 Exchange Online 邮箱和站点) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 您必须先拥有权限，然后才能执行以下过程：

  - 在 Exchange Online 中，请参阅 Exchange Online 功能权限中的 ["邮件流"条目](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions)。
  
  - 在独立 EOP 中，您必需的是，该角色默认分配到 OrganizationManagement、ComplianceManagement 和 RecordsManagement 角色。 有关详细信息，请参阅独立[EOP 中的"权限](feature-permissions-in-eop.md)["和"使用 EAC 修改角色组中的成员列表"。](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- 若要在 Exchange Online 中打开 EAC，请参阅[Exchange Online 中的"Exchange 管理中心"。](https://docs.microsoft.com/Exchange/exchange-admin-center) 若要在独立 EOP 中打开 EAC，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 若要详细了解 Exchange Online 和独立 EOP 中的邮件流规则，请参阅下列主题：

  - [Exchange Online 中的邮件流规则（传输规则）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [在 Exchange Online 中预测 (邮件流规则) 条件和异常](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online 中的邮件流规则操作](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- 用于识别示例中的批量邮件的字词和文本模式列表并不具有任何特色;您可以根据需要添加和删除条目。 但是，它们是一个很好的起点。

- 在邮件已通过 MIME 内容传输编码方法（用于以 ACSII 文本方式在 SMTP 服务器之间传输二进制消息）解码*后*，搜索邮件中主题或其他头字段中的字词或文本模式。不能使用条件或例外来搜索邮件中主题或其他头字段的原始（通常为 Base64）编码值。

- 下面的步骤为您的整个组织将批量邮件标记为垃圾邮件。 但是，您可以添加其他条件以仅将这些规则应用于特定收件人，因此，你可以针对针对高度针对性较高的用户进行积累筛选，同时又重大限于这些用户注册了) 的批量电子邮件的其余 (不受影响。

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>使用 EAC 创建对批量电子邮件进行筛选的邮件流规则

1. In the EAC, go to **Mail flow** \> **Rules**.

2. 单击 **"添加** ![ " ](../../media/ITPro-EAC-AddIcon.png) 图标，然后选择"**创建新规则"。**

3. 在打开的" **新规则**"窗口中，配置以下设置：

   - **名称**：输入规则的唯一描述性名称。

   - 单击“其他选项”****。

   - **在以下情况应用此**规则：配置以下设置之一以使用正则表达式或字词或短语)  (查找邮件中的内容：

     - **主题或正文** \>**主题或正文与这些文本模式**匹配：在**显示的"指定词语或短**语"对话框中，输入下列值之一，单击**Add** ![ "添加图标 ](../../media/ITPro-EAC-AddIcon.png) "，重复执行，直到您输入所有值。

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

      若要编辑条目，请将其选中，然后单击**Edit**"编辑 ![ "图标 ](../../media/ITPro-EAC-EditIcon.png) 。 若要删除条目，请选中它，并单击" **删除"** ![ 图标 ](../../media/ITPro-EAC-DeleteIcon.png) 。

       完成后，单击"确定 **"。**

     - **主题或正文** \>**主题或正文包括以下任何词**语：在**显示的"指定词语或短**语"对话框中，输入下列值之一，再单击**Add** ![ "添加图标 ](../../media/ITPro-EAC-AddIcon.png) "，重复执行，直到您输入所有值。

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

      若要编辑条目，请将其选中，然后单击**Edit**"编辑 ![ "图标 ](../../media/ITPro-EAC-EditIcon.png) 。 若要删除条目，请选中它，并单击" **删除"** ![ 图标 ](../../media/ITPro-EAC-DeleteIcon.png) 。

       完成后，单击"确定 **"。**

   - **执行以下操作：** 选择 **"修改邮件属性** \> **"，然后将垃圾邮件可信度设为 (SCL) 。 ** 在出现 **的"指定 SCL"** 对话框中，配置下列设置之一：

     - 要将邮件标记为**垃圾邮件，** 请选择 **"6"。** 您在反垃圾邮件策略中为 **垃圾邮件** 筛选欺词配置的操作将应用于邮件 (默认值为 **将邮件移动到垃圾邮件文件夹** 的) 。

     - 要将邮件标记为 **"高可信度垃圾邮件"，****请选择 9。** 您在反垃圾邮件策略中为 **高可信度垃圾邮件** 筛选反应器配置的操作适用于邮件 (默认值为 **将邮件移至垃圾邮件文件夹**) 。

    有关 SCL 值的详细信息，请参阅 ["垃圾邮件可信度 (EOP 中) SCL 策略](spam-confidence-levels.md)。

   完成后，请单击"保存 **"**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>使用 PowerShell 创建筛选批量电子邮件的邮件流规则

使用以下语法创建一个或多个由正则表达式与单词 (或多个单词) ：

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

本示例创建名为"批量电子邮件筛选 - RegEx"的新规则，该规则使用与本主题前面介绍的正则表达式相同的列表来将邮件设置为 **垃圾邮件**。

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

本示例创建名为"Bulk email filtering - Words"的新规则，该规则使用与本主题前面的单词相同的单词列表来将邮件设置为 **高可信度垃圾邮件**。

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)。

## <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

要验证是否已配置邮件流规则以筛选批量电子邮件，请执行以下任一步骤：

- 在 EAC 中，转到"**邮件流规则** \> **"** \> 后，选择规则 \> ，单击"**Edit** ![ 编辑" ](../../media/ITPro-EAC-EditIcon.png) 图标，然后验证设置。

- 在 PowerShell \<Rule Name\> 中，将规则名称替换为规则，并运行以下命令来验证设置：

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- 从外部帐户向受影响的收件人发送包含短语或文本模式之一的测试邮件，然后验证结果。
