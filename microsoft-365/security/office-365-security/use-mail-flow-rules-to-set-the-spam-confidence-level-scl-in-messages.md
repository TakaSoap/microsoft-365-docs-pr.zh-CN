---
title: 在邮件中将邮件流规则用于 SCL
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: 了解如何创建邮件流规则 (传输规则) 标识邮件，以及如何在 Exchange Online Protection 中设置邮件的垃圾邮件可信度 (SCL) 。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: aa2893214543f77114d517dc38f874d6172a920a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287553"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>使用邮件流规则在 EOP 中的 (SCL) 设置垃圾邮件可信度

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

在具有 Exchange Online 邮箱的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 使用反垃圾邮件策略 (也称为垃圾邮件筛选器策略或内容筛选器策略) 扫描入站邮件中的垃圾邮件。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

如果要在垃圾邮件筛选扫描特定邮件之前将其标记为垃圾邮件，或将邮件标记为跳过垃圾邮件筛选，可以创建邮件流规则 (也称为传输规则) 来标识邮件，并设置垃圾邮件可信度 (SCL) 。 有关 SCL 详细信息，请参阅 [EOP](spam-confidence-levels.md)中 SCL (的) 可信度。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 您需要在 Exchange Online 或 Exchange Online Protection 中分配权限，然后才能执行本文中的过程。 具体来说，您需要传输规则角色，该角色默认分配给组织管理、合规性 **管理 (全局** 管理员) 和 **记录** 管理角色组。

  有关详细信息，请参阅下列主题：

  - [Exchange Online 中的权限](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [独立 EOP 中的权限](feature-permissions-in-eop.md)
  - [使用 EAC 修改角色组的成员列表](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- 若要在 Exchange Online 中打开 EAC，请参阅 [Exchange Online 中的 Exchange 管理中心](https://docs.microsoft.com/Exchange/exchange-admin-center)。 若要在独立 EOP 中打开 EAC，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 有关 Exchange Online 和 Exchange Online Protection 中的邮件流规则详细信息，请参阅 Exchange Online 中的邮件流规则 ([传输) 规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>使用 EAC 创建设置邮件 SCL 的邮件流规则

1. In the EAC, go to **Mail flow** \> **Rules**.

2. 单击 **"添加** ![ " ](../../media/ITPro-EAC-AddIcon.png) 图标，然后选择 **"创建新规则"。**

3. 在打开的" **新规则**"窗口中，配置以下设置：

   - **名称**：为规则输入唯一的描述性名称。

   - 单击“其他选项”。

   - **如果：选择一** 个或多个条件来标识邮件，则应用此规则。 有关详细信息，请参阅 Exchange Online 中的邮件流 [规则 (和) 例外](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。

   - **执行以下操作：** 选择 **"修改邮件属性** \> **"设置 SCL (垃圾邮件可信度) 。** 在 **出现的"指定 SCL"** 对话框中，配置下列值之一：

   - **绕过垃圾邮件筛选**：邮件将跳过垃圾邮件筛选。

     > [!CAUTION]
     > 在允许邮件跳过垃圾邮件筛选时要非常小心。 攻击者可以使用此漏洞向组织发送网络钓鱼邮件和其他恶意邮件。 邮件流规则需要的不仅仅是发件人的电子邮件地址或域。 有关详细信息，请参阅在 [EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。

   - **0 到 4：** 邮件通过垃圾邮件筛选进行发送，进行其他处理。

   - **5 或 6：** 邮件被标记为"**垃圾邮件"。** 为反垃圾邮件策略中的垃圾邮件筛选裁定配置的操作将应用于邮件 (默认值为"将邮件移动到垃圾邮件"文件夹) 。 

   - **7 到 9：** 邮件标记为 **高可信度垃圾邮件**。 为反垃圾邮件策略中的高可信度垃圾邮件筛选裁定配置的操作将应用于邮件 (默认值为"将邮件移动到垃圾邮件"文件夹) 。 

4. 指定规则需要的任何其他属性。 完成时，请单击“保存”。

## <a name="how-do-you-know-this-worked"></a>您如何知道操作成功？

要验证此步骤是否能正常工作，请发送电子邮件至组织中的某位同事，并验证是否对该邮件执行预期的操作。 例如，如果将垃圾邮件可信度设置为 **(SCL)****绕过垃圾邮件筛选**，则邮件应发送到指定收件人的收件箱。 但是，如果将垃圾邮件可信度 **(SCL)** 设置为 **9，** 并且适用的反垃圾邮件策略的高可信度垃圾邮件操作是将邮件移动到"垃圾邮件"文件夹，则邮件应发送到指定收件人的"垃圾邮件"文件夹。
