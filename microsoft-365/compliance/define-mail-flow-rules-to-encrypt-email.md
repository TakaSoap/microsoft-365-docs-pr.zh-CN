---
title: 定义用于加密电子邮件的邮件流规则
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何创建邮件流规则 (传输规则) 使用 Office 365 邮件加密对邮件进行加密和解密。
ms.openlocfilehash: 28486f601a79e294550bbceb48ad57069024fd5a
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408602"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>定义用于加密电子邮件的邮件流规则

作为全局管理员，您可以创建邮件流规则 (也称为传输规则) ，以帮助保护您发送和接收的电子邮件。 您可以设置规则来加密任何传出的电子邮件，并删除来自组织内部或从组织发送的加密邮件的答复的加密邮件的加密。 您可以使用 Exchange 管理中心 (EAC) 或 Exchange Online PowerShell 创建这些规则。 除了整体的加密规则，您还可以针对最终用户选择启用或禁用个人邮件加密选项。

无法对组织外部的发件人的入站邮件进行加密。

如果你最近从 Active Directory RMS 迁移到 Azure 信息保护，你将需要查看现有的邮件流规则，以确保它们在你的新环境中继续有效。 此外，如果您想利用新的 Office 365 邮件加密 (通过 Azure 信息保护为您提供的 OME) 功能，则需要更新现有的邮件流规则。 否则，您的用户将继续接收使用以前的 HTML 附件格式的加密邮件，而不是新的无缝 OME 体验。 如果尚未设置 OME，请参阅为信息 [设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md) 。

有关组成邮件流规则的组件和邮件流规则的工作方式的信息，请参阅 [mail flow rules (transport rules) In Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。 有关邮件流规则如何使用 Azure 信息保护的其他信息，请参阅 [为 Azure 信息保护标签配置 Exchange Online 邮件流规则](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)。

> [!IMPORTANT]
> 对于混合 Exchange 环境，只有在通过 Exchange Online 路由电子邮件的情况下，本地用户才能使用 OME 发送和接收加密邮件。 若要在混合 Exchange 环境中配置 OME，需要先 [使用 "混合配置" 向导配置混合](https://docs.microsoft.com/Exchange/exchange-hybrid) ，然后 [将邮件配置为从 Office 365 传输到您的电子邮件服务器](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server) ，并 [将邮件配置为从您的电子邮件服务器传递到 Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。 将邮件配置为通过 Office 365 传输之后，可以使用本指南配置 OME 的邮件流规则。

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>创建邮件流规则，以使用新的 OME 功能对电子邮件进行加密

您可以使用 EAC 定义邮件流规则，以使用新的 OME 功能触发邮件加密。

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>使用 EAC 创建使用新的 OME 功能对电子邮件进行加密的规则

1. 在 web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户， [登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 选择 " **管理** " 磁贴。

3. 在 Microsoft 365 管理中心，选择 " **管理中心**" " \> **Exchange**"。

4. 在 EAC 中，转到 " **邮件流** \> **规则** "，然后选择 " **新建**" ![ 图标 ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **创建新规则**。 有关使用 EAC 的详细信息，请参阅 exchange [Online 中的 exchange 管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 " **名称**" 中，键入规则的名称，例如 "为 DrToniRamos@hotmail.com 加密邮件"。

6. 在 "在 **以下情况应用此规则**" 中，选择一个条件，并根据需要输入一个值。 例如，若要加密发送到 DrToniRamos@hotmail.com 的邮件：

   1. 在“在以下情况应用此规则”**** 中，选择“收件人为”****。

   2. 从联系人列表中选择一个现有名称，或在“检查名称”**** 框中键入一个新的电子邮件地址。

      - 若要选择一个现有名称，可以从列表中进行选择，然后单击“确定”****。

      - 若要输入新名称，请在 " **检查名称** " 框中键入电子邮件地址，然后选择 " **检查名称** \> **" "确定"**。

7. 若要添加更多条件，请选择 " **更多选项** "，然后选择 " **添加条件** "，然后从列表中选择。

   例如，若要仅在收件人在组织外部时应用规则，请选择 "**添加条件**"，然后选择 "在组织外部 **/内部的收件人是外部/内部** \> **Outside the organization** \> **"**。

8. 若要使用新的 OME 功能启用加密，请从 **执行以下操作**，选择 " **修改邮件安全性"** ，然后选择 " **应用 Office 365 邮件加密和权限保护**"。 从列表中选择一个 RMS 模板，选择 " **保存**"，然后选择 **"确定"**。
  
  模板列表包含所有默认模板和选项，以及您创建的用于 Office 365 的任何自定义模板。 如果列表为空，请确保已使用新功能设置了 Office 365 邮件加密，如 [设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)中所述。 有关默认模板的信息，请参阅 [配置和管理 Azure 信息保护的模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。 有关 " **不要转发** " 选项的信息，请参阅 [电子邮件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)的 "不要转发" 选项。 有关 **仅加密** 选项的信息，请参阅 [仅加密电子邮件选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

  如果要指定另一个操作，可以选择 " **添加操作** "。

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>使用 EAC 更新现有的邮件流规则，以使用新的 OME 功能

1. 在 web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户， [登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 选择 " **管理** " 磁贴。

3. 在 Microsoft 365 管理中心，选择 " **管理中心**" " \> **Exchange**"。

4. In the EAC, go to **Mail flow** \> **Rules**.

5. 在邮件流规则的列表中，选择要修改的规则以使用新的 OME 功能，然后选择 " **编辑**" "编辑" ![ 图标 ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。

6. 若要使用新的 OME 功能启用加密，请从 **执行以下操作**，选择 " **修改邮件安全性"** ，然后选择 " **应用 Office 365 邮件加密和权限保护**"。 从列表中选择一个 RMS 模板，选择 " **保存** "，然后选择 **"确定"**。

   模板列表包含所有默认模板和选项，以及您创建的用于 Office 365 的任何自定义模板。 如果列表为空，请确保已使用新功能设置了 Office 365 邮件加密，如 [设置新的 office 365 邮件加密功能（基于 Azure 信息保护的基础之上](set-up-new-message-encryption-capabilities.md)）中所述。 有关默认模板的信息，请参阅 [配置和管理 Azure 信息保护的模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。 有关 " **不要转发** " 选项的信息，请参阅 [电子邮件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)的 "不要转发" 选项。 有关 **仅加密** 选项的信息，请参阅 [仅加密电子邮件选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

   如果要指定另一个操作，可以选择 " **添加操作** "。

7. 从 " **执行以下** 操作" 列表中，删除为 **修改邮件安全性**而分配的所有操作 \> **应用早期版本的 OME**。

8. 选择“**保存**”。

## <a name="create-mail-flow-rules-to-remove-encryption-for-outgoing-email-messages-with-the-new-ome-capabilities"></a>创建邮件流规则，以使用新的 OME 功能删除传出电子邮件的加密

您可以使用 EAC 定义邮件流规则，以使用新的 OME 功能触发删除邮件加密。

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>使用 EAC 创建一个规则，以使用新的 OME 功能从电子邮件中删除加密

1. 在 web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户， [登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 选择 " **管理** " 磁贴。

3. 在 Microsoft 365 管理中心，选择 " **管理中心**" " \> **Exchange**"。

4. 在 EAC 中，转到 " **邮件流** \> **规则** "，然后选择 " **新建**" ![ 图标 ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **创建新规则**。 有关使用 EAC 的详细信息，请参阅 exchange [Online 中的 exchange 管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 " **名称**" 中，键入规则的名称，例如 "从传出邮件中删除加密"。

6. 在 "在 **以下情况应用此规则**" 中，选择应从邮件中删除加密的条件。 添加 **发件人位于** \> **组织内部**。 现在，添加其他条件以面向特定的收件人，例如 **收件人位于** \> **组织外部**。

7. 在 **"执行以下操作**" 中，选择 " **修改邮件安全** \> **删除 Office 365 邮件加密和权限保护**"。

8. 选择“**保存**”。

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>创建不带新功能的 Office 365 邮件加密的邮件流规则

如果尚未将组织移动到新的 OME 功能，Microsoft 建议您制定一个计划，尽快移动到新的 OME 功能，因为它对您的组织而言是合理的。 有关说明，请参阅 [设置基于 Azure 信息保护基础构建的新 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。 否则，请参阅 [定义不使用新 OME 功能的 Office 365 邮件加密的邮件流规则](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities)。

## <a name="related-topics"></a>相关主题

[Office 365 中的加密](encryption.md)

[设置全新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)

[将品牌添加到加密邮件](add-your-organization-brand-to-encrypted-messages.md)

[Exchange Online 中的邮件流规则（传输规则）](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[Exchange Online Protection 中) 的邮件流规则 (传输规则](https://go.microsoft.com/fwlink/p/?LinkId=506708)
