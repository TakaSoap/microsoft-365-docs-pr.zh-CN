---
title: 将邮件流规则用于邮件中的 SCL
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Exchange Online Protection 中设置邮件的 SCL。
ms.openlocfilehash: b7ea9a0f046e5a48f0de8d4ac9ae6d53821f03c0
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895091"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a>使用邮件流规则设置邮件中的垃圾邮件可信度 (SCL)

如果您是在 Exchange Online 中使用邮箱的 Office 365 客户或没有 Exchange Online 邮箱的独立 Exchange Online Protection （EOP）客户，则 EOP 使用反垃圾邮件策略（也称为垃圾邮件筛选器策略或内容筛选器策略）进行扫描垃圾邮件的入站邮件。 有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

如果要将特定邮件标记为垃圾邮件，然后再通过垃圾邮件筛选进行扫描，或将邮件标记为跳过垃圾邮件筛选，则可以创建邮件流规则（也称为传输规则），以标识邮件并设置垃圾邮件可信度（SCL）。 有关 SCL 的详细信息，请参阅[Office 365 中的垃圾邮件可信度（SCL）](spam-confidence-levels.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 您需要先在 Exchange Online 中分配权限，然后才能执行这些过程。 具体来说，您需要分配 "**传输规则**" 角色，默认情况下会将其分配给 "**组织管理**"、"**合规性管理**" 和 "**记录管理**" 角色。 有关详细信息，请参阅[在 Exchange Online 中管理角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。

- 若要在 Exchange Online 中打开 EAC，请参阅 exchange [online 中的 exchange 管理中心](https://docs.microsoft.com/Exchange/exchange-admin-center)。

- 有关 Exchange Online 中的邮件流规则的详细信息，请参阅[Exchange online 中的邮件流规则（传输规则）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>使用 EAC 创建邮件流规则，以设置邮件的 SCL

1. In the EAC, go to **Mail flow** \> **Rules**.

2. 单击 "**添加** !["](../../media/ITPro-EAC-AddIcon.png) "添加" 图标，然后选择 "**创建新规则**"。

3. 在打开的" **新规则**"窗口中，配置以下设置：

   - **名称**：输入规则的唯一描述性名称。

   - 单击“其他选项”****。

   - **在以下情况应用此规则**：选择一个或多个条件来标识邮件。 有关详细信息，请参阅[Exchange Online 中的邮件流规则条件和例外（谓词）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。

   - **执行以下**操作：选择 "**修改邮件属性** \> **" 设置垃圾邮件可信度（SCL）**。 在出现的 "**指定 SCL** " 对话框中，配置下列值之一：

   - **绕过垃圾邮件筛选**：这会将 SCL 设置为-1，这意味着邮件将跳过垃圾邮件筛选。

     > [!CAUTION]
     > 务必小心允许邮件跳过垃圾邮件筛选。 攻击者可以利用此漏洞将网络钓鱼和其他恶意邮件发送到您的组织中。 邮件流规则需要的不仅仅是发件人的电子邮件地址或域。 有关详细信息，请参阅[在 Office 365 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。

   - **0 到 4**：通过垃圾邮件筛选发送邮件以进行其他处理。

   - **5 或 6**：邮件被标记为**垃圾**邮件。 您为反垃圾邮件策略中的**垃圾**邮件筛选 verdicts 配置的操作将应用于该邮件（默认值为 "**将邮件移动到垃圾邮件" 文件夹**）。

   - **7 至 9**：将邮件标记为**高可信度垃圾邮件**。 您为**高可信度垃圾**邮件筛选 verdicts 配置的操作将应用于该邮件（默认值为 "**将邮件移动到垃圾邮件" 文件夹**）。

4. 为规则指定所需的任何其他属性。 完成后，单击“保存”****。

## <a name="how-do-you-know-this-worked"></a>您如何知道操作成功？

要验证此步骤是否能正常工作，请发送电子邮件至组织中的某位同事，并验证是否对该邮件执行预期的操作。 例如，如果**将垃圾邮件可信度（SCL）设置**为 "**绕过垃圾邮件筛选**"，则应将邮件发送到指定收件人的收件箱。 但是，如果您**将垃圾邮件可信度（SCL）设置**为**9**，并且适用的内容筛选器策略的**高可信度垃圾邮件**操作是将邮件移至 "垃圾邮件" 文件夹，则邮件应发送到指定收件人的 "垃圾邮件" 文件夹。
