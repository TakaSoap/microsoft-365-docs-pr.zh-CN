---
title: 使用邮件流规则来查看用户向 Microsoft 报告的内容
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
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何使用邮件流规则 (也称为传输规则) 接收用户报告给 Microsoft 的邮件的副本。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e6428a228ae64562f0b529f6aa90ddc3be46fdc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203714"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>使用邮件流规则来查看用户向 Microsoft 报告的内容

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在 Microsoft 365 组织中，邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱，用户有多种方法将邮件报告给 Microsoft 进行分析，如将邮件和文件报告给[Microsoft](report-junk-email-messages-to-microsoft.md)中所述。

您可以创建邮件流规则 (也称为传输规则) ，用于查找用户报告给 Microsoft 的邮件，还可以将"Bcc"收件人配置为接收这些报告的邮件的副本。

您可以在 Exchange 管理中心 (EAC) 和 Power (Exchange Online Shell PowerShell 中为 Microsoft 365 组织创建邮件流规则Exchange Online;适用于没有邮箱或邮箱Exchange Online的独立 EOP PowerShell) 。

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

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>使用 EAC 创建邮件流规则以接收报告的邮件副本

1. In the EAC, go to **Mail flow** \> **Rules**.

2. 单击 **添加** ![ 添加图标 ](../../media/ITPro-EAC-AddIcon.png) ，然后选择 **创建新规则**。

3. 在打开的" **新规则**"窗口中，配置以下设置：

   - **名称**：输入规则的唯一描述性名称。 例如，报告给 Microsoft 的"Bcc 邮件"。

   - 单击“其他选项”。

   - 在 以下情况应用此规则：选择"收件人地址包含以下任何词语"：在出现的"指定词语或短语"对话框中，输入下列值之一，单击"添加添加图标"，重复此操作，直到输入所有值。 \>    ![ ](../../media/ITPro-EAC-AddIcon.png)

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     若要编辑条目，请选择它，然后单击编辑 **编辑** ![ 图标 ](../../media/ITPro-EAC-EditIcon.png) 。 若要删除条目，请选择它，然后单击删除 **删除** ![ 图标 ](../../media/ITPro-EAC-DeleteIcon.png) 。

     完成后，单击"确定 **"。**

   - **执行以下操作：** 选择 **"将收件人** \> **添加到"抄送"框**。 在出现的对话框中，查找并选择要添加的收件人。 完成后，单击"确定 **"。**

4. 您可以进行其他选择，以审核规则、测试规则、激活特定时间段的规则以及其他设置。 建议在强制执行规则之前测试它。

5. 完成后，单击“**保存**”。

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>使用 PowerShell 创建邮件流规则以接收报告的邮件副本

本示例创建一个名为"Bcc Messages Reported to Microsoft"的新邮件流规则，该规则查找使用本文中所述的方法报告给 Microsoft 的电子邮件，并将用户 laura@contoso.com 和 julia@contoso.com 添加为"Bcc"收件人。

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

有关语法和参数的详细信息，请参阅 [New-TransportRule](/powershell/module/exchange/new-transportrule)。

## <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证您是否已配置邮件流规则以接收报告的邮件副本，请执行下列任一步骤：

- 在 EAC 中，转到"**邮件** 流""规则 \>  \> "选择规则单击" \> **编辑** ![ 编辑"图标 ](../../media/ITPro-EAC-EditIcon.png) ，然后验证设置。

- 在 PowerShell 中，运行以下命令来验证设置：

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- 将测试邮件发送到其中一个报告电子邮件地址并验证结果。