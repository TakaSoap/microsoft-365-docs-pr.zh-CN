---
title: 使用邮件流规则来查看用户向 Microsoft 报告的内容
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
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何使用邮件流规则和 (也称为传输规则，) 以接收用户向 Microsoft 报告的邮件副本。
ms.openlocfilehash: 1612adeefff21fa9f149de6537917dd9b8c50b00
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827381"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>使用邮件流规则来查看用户向 Microsoft 报告的内容

在有 Exchange Online 邮箱的 Microsoft 365 组织中，或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，如"向 Microsoft 报告邮件和文件"中所述，用户可以通过多种方式向 Microsoft 报告邮件以 [供分析](report-junk-email-messages-to-microsoft.md)。

你可以创建邮件流规则 (也称为传输规则) 后者，用于查找用户向 Microsoft 报告的邮件，还可以将"抄送"收件人配置为接收这些报告的邮件的副本。

你可以在 Exchange 管理中心 (EAC) 和 PowerShell (Exchange Online PowerShell 为具有 Exchange Online 邮箱的 Exchange Online PowerShell 创建邮件流规则;独立 EOP PowerShell 适用于没有 Exchange Online 邮箱和站点) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 必须先在 Exchange Online 或 EOP 中分配有权限，才能执行这些步骤。 具体而下，您需分配 **Transport Rules** role， which is assigned to the **Organization Management**， Compliance **Management，** and **Records Management** roles by default. 有关详细信息，请参阅[在 Exchange Online 中管理角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。

- 要打开 EAC，请参阅 [Exchange Online 中的 Exchange](https://docs.microsoft.com/Exchange/exchange-admin-center) 管理中心 [或独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 若要详细了解 Exchange Online 和独立 EOP 中的邮件流规则，请参阅下列主题：

  - [Exchange Online 中的邮件流规则（传输规则）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [在 Exchange Online 中预测 (邮件流规则) 条件和异常](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online 中的邮件流规则操作](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>使用 EAC 创建邮件流规则以接收报告的邮件的副本

1. In the EAC, go to **Mail flow** \> **Rules**.

2. 单击 **"添加** ![ " ](../../media/ITPro-EAC-AddIcon.png) 图标，然后选择"**创建新规则"。**

3. 在打开的" **新规则**"窗口中，配置以下设置：

   - **名称**：输入规则的唯一描述性名称。 例如，报告给 Microsoft 的"邮件"。

   - 单击“其他选项”****。

   - **在以下条件下应用**此规则：**选择收件人** \> **地址包括以下**任何词语：在出现的"指定词语或**短语**"对话框中，输入以下值之一，单击"**Add** ![ 添加图标"，然后在输入所有所有值 ](../../media/ITPro-EAC-AddIcon.png) 后重复发送操作。

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     若要编辑条目，请将其选中，然后单击**Edit**"编辑 ![ "图标 ](../../media/ITPro-EAC-EditIcon.png) 。 若要删除条目，请选中它，并单击" **删除"** ![ 图标 ](../../media/ITPro-EAC-DeleteIcon.png) 。

     完成后，单击"确定 **"。**

   - **执行下列操作：** 选择 **"将收件人** \> **添加到"送件抄送"框**。 在出现的对话框中，找到并选择要添加的收件人。 完成后，单击"确定 **"。**

4. 您可以进行其他选择，在特定时间内审核规则、测试规则及激活规则以及其他设置。 我们建议您在强制执行规则之前测试规则。

5. 完成时，请单击“保存”****。

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>使用 PowerShell 创建邮件流规则以接收报告的邮件的副本

此示例创建一个名为"送给 Microsoft"的新的名为"Bcc Messages"的邮件流规则，该规则查找通过使用本主题中介绍的方法报告给 Microsoft 的电子邮件，并添加了作为"Laura@contoso.com"和"julia@contoso.com"收件人的电子邮件。

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)。

## <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证是否已配置邮件流规则以接收报告的邮件的副本，请执行以下任意步骤：

- 在 EAC 中，转到"**邮件流规则** \> **"** \> 后，选择规则 \> ，单击"**Edit** ![ 编辑" ](../../media/ITPro-EAC-EditIcon.png) 图标，然后验证设置。

- 在 PowerShell 中，运行以下命令来验证设置：

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- 向报告电子邮件地址之一发送测试邮件并验证结果。
