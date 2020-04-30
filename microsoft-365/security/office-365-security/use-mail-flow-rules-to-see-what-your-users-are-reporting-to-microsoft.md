---
title: 使用邮件流规则来查看用户向 Microsoft 报告的内容
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
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何使用邮件流规则（也称为传输规则）接收用户向 Microsoft 报告的邮件的副本。
ms.openlocfilehash: 2b1e82ece936551c48e5617955f546cf851a8913
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939495"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>使用邮件流规则来查看用户向 Microsoft 报告的内容

用户可通过多种方式将邮件报告给 Microsoft 进行分析，如[报告消息和文件到 microsoft](report-junk-email-messages-to-microsoft.md)中所述。

您可以创建邮件流规则（也称为传输规则），查找用户向 Microsoft 报告的邮件，并且您可以配置密件抄送收件人以接收这些报告的邮件的副本。

您可以在 Exchange 管理中心（EAC）和 PowerShell （Exchange Online PowerShell for Microsoft 365 客户中创建邮件流规则;适用于独立 EOP 客户的 Exchange Online Protection PowerShell）。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 您需要在 Exchange Online 或 EOP 中分配权限，然后才能执行这些过程。 具体来说，您需要分配 "**传输规则**" 角色，默认情况下会将其分配给 "**组织管理**"、"**合规性管理**" 和 "**记录管理**" 角色。 有关详细信息，请参阅[在 Exchange Online 中管理角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。

- 若要打开 EAC，请参阅 exchange [online 中的 exchange 管理中心](https://docs.microsoft.com/Exchange/exchange-admin-center)或 Exchange [online Protection 中的 exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要连接到独立 Exchange Online Protection，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 有关 Exchange Online 和独立 EOP 中的邮件流规则的详细信息，请参阅下列主题：

  - [Exchange Online 中的邮件流规则（传输规则）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Online 中的邮件流规则条件和例外（谓词）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online 中的邮件流规则操作](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>使用 EAC 创建邮件流规则以接收报告的邮件的副本

1. In the EAC, go to **Mail flow** \> **Rules**.

2. 单击 "**添加** !["](../../media/ITPro-EAC-AddIcon.png) "添加" 图标，然后选择 "**创建新规则**"。

3. 在打开的" **新规则**"窗口中，配置以下设置：

   - **名称**：输入规则的唯一描述性名称。 例如，向 Microsoft 报告的密件抄送邮件。

   - 单击“其他选项”****。

   - **在以下情况下应用此规则**：选择**收件人** \> **地址包括以下任何词语**：在显示的 "**指定字词或短语**" 对话框中，输入以下值之一， **Add** ![单击 "添加](../../media/ITPro-EAC-AddIcon.png)" "添加" 图标，然后重复此步骤，直到您输入所有值为止。

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     若要编辑条目，请选择该条目**Edit** ![，然后单击](../../media/ITPro-EAC-EditIcon.png)"编辑" "编辑" 图标。 若要删除条目，请将其选中**Remove** ![，然后单击](../../media/ITPro-EAC-DeleteIcon.png)"删除删除图标"。

     完成后，请单击 **"确定"**。

   - **执行下列**操作：选择 "**将收件人** \>添加**到密件抄送" 框**。 在出现的对话框中，查找并选择要添加的收件人。 完成后，请单击 **"确定"**。

4. 您可以进行其他选择来审核规则、测试规则、在特定时间段内激活规则，以及其他设置。 建议在强制执行规则之前对其进行测试。

5. 完成后，单击 **“保存”**。

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>使用 PowerShell 创建邮件流规则以接收报告的邮件的副本

本示例将新建一个名为 "密件抄送给 Microsoft" 的邮件流规则，该规则将查找通过使用本主题中所述方法报告给 Microsoft 的电子邮件，并将用户 laura@contoso.com 和 julia@contoso.com 添加为密件抄送收件人。

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)。

## <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证是否已将邮件流规则配置为接收报告的邮件的副本，请执行以下任一步骤：

- 在 EAC 中，转到 **"邮件流** \> **规则** \> "。 \>选择该规则，](../../media/ITPro-EAC-EditIcon.png)然后单击 "**编辑** ![编辑" 图标，并验证设置。

- 在 PowerShell 中，运行以下命令来验证设置：

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- 将测试邮件发送到其中一个报告电子邮件地址，并验证结果。
