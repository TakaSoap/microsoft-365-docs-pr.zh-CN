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
ms.openlocfilehash: d50a0f02dd3d65b8576261fc2332aba86d55df56
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616786"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>使用邮件流规则来查看用户向 Microsoft 报告的内容

在没有 Exchange Online 邮箱的 Exchange Online 或独立 Exchange Online 保护（EOP）组织中具有邮箱的 Microsoft 365 组织中，用户可以通过多种方式将邮件报告给 Microsoft 进行分析，如[报告消息和文件到 microsoft](report-junk-email-messages-to-microsoft.md)中所述。

您可以创建邮件流规则（也称为传输规则），查找用户向 Microsoft 报告的邮件，并且您可以配置密件抄送收件人以接收这些报告的邮件的副本。

您可以在 exchange 管理中心（EAC）和 PowerShell （exchange Online PowerShell for Microsoft 365 组织中使用邮箱在 Exchange Online 中创建邮件流规则; 独立 EOP PowerShell for 组织，无需 Exchange Online 邮箱）。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 您需要在 Exchange Online 或 EOP 中分配权限，然后才能执行这些过程。 具体来说，您需要分配 "**传输规则**" 角色，默认情况下会将其分配给 "**组织管理**"、"**合规性管理**" 和 "**记录管理**" 角色。 有关详细信息，请参阅[在 Exchange Online 中管理角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。

- 若要打开 EAC，请参阅 exchange [Online 中的 exchange 管理中心](https://docs.microsoft.com/Exchange/exchange-admin-center)或[独立 EOP 中的 exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立的 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 有关 Exchange Online 和独立 EOP 中的邮件流规则的详细信息，请参阅下列主题：

  - [Exchange Online 中的邮件流规则（传输规则）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Online 中的邮件流规则条件和例外（谓词）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online 中的邮件流规则操作](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>使用 EAC 创建邮件流规则以接收报告的邮件的副本

1. In the EAC, go to **Mail flow** \> **Rules**.

2. 单击 "**添加**" "添加" ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) ，然后选择 "**创建新规则**"。

3. 在打开的" **新规则**"窗口中，配置以下设置：

   - **名称**：输入规则的唯一描述性名称。 例如，向 Microsoft 报告的密件抄送邮件。

   - 单击“其他选项”****。

   - **在以下情况下应用此规则**：选择**收件人** \> **地址包括以下任何词语**：在显示的 "**指定字词或短语**" 对话框中，输入以下值之一，单击 "**添加**" "添加" ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) ，然后重复此步骤，直到您输入所有值为止。

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     若要编辑条目，请选择该条目，然后单击 "**编辑**" "编辑" ![ 图标 ](../../media/ITPro-EAC-EditIcon.png) 。 若要删除条目，请将其选中，然后单击 "**删除** ![ 删除图标" ](../../media/ITPro-EAC-DeleteIcon.png) 。

     完成后，请单击 **"确定"**。

   - **执行下列**操作：选择 "**将收件人添加** \> **到密件抄送" 框**。 在出现的对话框中，查找并选择要添加的收件人。 完成后，请单击 **"确定"**。

4. 您可以进行其他选择来审核规则、测试规则、在特定时间段内激活规则，以及其他设置。 建议在强制执行规则之前对其进行测试。

5. 完成时，请单击“保存”****。

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>使用 PowerShell 创建邮件流规则以接收报告的邮件的副本

本示例将新建一个名为 "密件抄送给 Microsoft" 的邮件流规则，该规则将查找通过使用本主题中所述方法报告给 Microsoft 的电子邮件，并将用户 laura@contoso.com 和 julia@contoso.com 添加为密件抄送收件人。

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)。

## <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证是否已将邮件流规则配置为接收报告的邮件的副本，请执行以下任一步骤：

- 在 EAC 中，转到 "**邮件流** \> **规则**"。 \> 选择该规则 \> ，然后单击 "**编辑** ![ 编辑 ](../../media/ITPro-EAC-EditIcon.png) " 图标，并验证设置。

- 在 PowerShell 中，运行以下命令来验证设置：

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- 将测试邮件发送到其中一个报告电子邮件地址，并验证结果。
