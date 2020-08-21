---
title: 使用邮件流规则至邮件中 SCL
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: 了解如何创建邮件流规则 (传输规则) 以标识邮件，并设置 Exchange Online Protection 中邮件的 (可信度) 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 67a4c25a1006e9b1554cf8ffbc2d5e29b4063752
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827369"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>使用邮件流规则设置 EOP 中邮件中邮件 (可信) 性

在有 Exchange Online 邮箱的 Microsoft 365 组织中或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 使用反垃圾邮件策略 (也称为垃圾邮件筛选器策略或内容筛选器策略) 来扫描入站邮件中的垃圾邮件。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

如果想要在垃圾邮件筛选被垃圾邮件筛选之前将特定邮件标记为垃圾邮件，或将邮件标记为跳过垃圾邮件筛选，可以创建邮件流规则 (也称为传输规则) 来标识邮件，并设置垃圾邮件可信度为 (SCL) 。 有关 SCL 的详细信息，请参阅["垃圾邮件可信度" (在 EOP (的") SCL"。](spam-confidence-levels.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 必须先分配有 Exchange Online 中的权限，才能执行这些过程。 具体而下，您需分配 **Transport Rules** role， which is assigned to the **Organization Management**， Compliance **Management，** and **Records Management** roles by default. 有关详细信息，请参阅[在 Exchange Online 中管理角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。

- 若要在 Exchange Online 中打开 EAC，请参阅[Exchange Online 中的"Exchange 管理中心"。](https://docs.microsoft.com/Exchange/exchange-admin-center)

- 若要详细了解 Exchange Online 中的邮件流规则，请参阅 [Exchange Online (传输规则) 邮件流规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>使用 EAC 创建设置邮件的 SCL 的邮件流规则

1. In the EAC, go to **Mail flow** \> **Rules**.

2. 单击 **"添加** ![ " ](../../media/ITPro-EAC-AddIcon.png) 图标，然后选择"**创建新规则"。**

3. 在打开的" **新规则**"窗口中，配置以下设置：

   - **名称**：输入规则的唯一描述性名称。

   - 单击“其他选项”****。

   - **在以下情况应用此**规则：选择一个或多个条件以标识邮件。 有关详细信息，请参阅 [邮件流规则条件和例外， (Exchange Online 中的谓词) 例外](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。

   - **执行以下操作：** 选择 **"修改邮件** \> **属性"，然后将垃圾邮件可信度设为 (SCL) 。 ** 在出现 **的"指定 SCL"** 对话框中，配置以下值之一：

   - **不使用垃圾邮件筛选**：邮件将跳过垃圾邮件筛选。

     > [!CAUTION]
     > 在允许邮件跳过垃圾邮件筛选时请非常细心。 攻击者可以使用此漏洞将网络钓鱼和其他恶意邮件发送到你的组织。 邮件流规则不仅需要发件人的电子邮件地址或域。 有关详细信息，请参阅"[在 EOP 中创建安全发件人列表"。](create-safe-sender-lists-in-office-365.md)

   - **0 到 4：** 邮件通过垃圾邮件筛选发送以进行其他处理。

   - **5 或 6：** 邮件被标记为 **垃圾邮件**。 您在反垃圾邮件策略中为 **垃圾邮件** 筛选欺词配置的操作将应用于邮件 (默认值为将 **邮件移至垃圾邮件** 文件夹的) 。

   - **7 到 9：** 邮件被标记**为"高可信度垃圾邮件"。** 您在反垃圾邮件策略中为 **高可信度垃圾邮件** 筛选反应器配置的操作将应用到邮件 (默认值为 **将邮件移至垃圾邮件文件夹**) 。

4. 为规则指定任何其他属性。 完成时，请单击“保存”****。

## <a name="how-do-you-know-this-worked"></a>您如何知道操作成功？

要验证此步骤是否能正常工作，请发送电子邮件至组织中的某位同事，并验证是否对该邮件执行预期的操作。 例如，如果您**将垃圾邮件可信度 (SCL) 设置为****"不使用垃圾邮件筛选**"，则该邮件应被发送至指定收件人的收件箱。 但是，如果您 **将垃圾邮件可信度 (SCL) ** 设置为 **9，** 并且 **适用的** 反垃圾邮件策略的"高可信度垃圾邮件"会将该邮件移至"垃圾邮件"文件夹，那么该邮件应被发送至指定收件人的"垃圾邮件"文件夹。
