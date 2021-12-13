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
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
ms.custom:
- admindeeplinkMAC
- admindeeplinkEXCHANGE
description: 管理员可以了解如何创建邮件流规则， (传输规则) 加密和解密邮件Office 365 邮件加密。
ms.openlocfilehash: c546c151b7bcb1720f9903d43b8d310650f92d35
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61421686"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>定义用于加密电子邮件的邮件流规则

作为管理电子邮件Exchange Online，您可以创建邮件流规则 (也称为传输) 规则，以帮助保护您发送和接收的电子邮件。 您可以设置规则来加密任何传出电子邮件，并从来自组织内部的加密邮件或对从组织发送的加密邮件的答复中删除加密。 可以使用<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">EAC</a> Exchange管理 (中心) 或Exchange Online PowerShell 创建这些规则。 除了整体的加密规则，您还可以针对最终用户选择启用或禁用个人邮件加密选项。

无法加密来自组织外部发件人的入站邮件。

如果你最近从 Active Directory RMS 迁移到 Azure 信息保护，则需要查看现有的邮件流规则，以确保它们继续在新环境中工作。 此外，如果你想要利用 Azure 信息保护Office 365 邮件加密 (OME) 功能，则需要更新现有的邮件流规则。 否则，您的用户将继续接收使用以前的 HTML 附件格式的加密邮件，而不是新的无缝 OME 体验。 如果尚未设置 OME，请参阅设置新的 Office 365 邮件加密[功能](set-up-new-message-encryption-capabilities.md)了解相关信息。

有关组成邮件流规则的组件以及邮件流规则如何工作的信息，请参阅邮件流规则 ([中的](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)) 规则Exchange Online。 有关邮件流规则如何与 Azure 信息保护一起运行的其他信息，请参阅为 Azure 信息Exchange Online配置[邮件流规则](/azure/information-protection/deploy-use/configure-exo-rules)。

> [!IMPORTANT]
> 对于混合Exchange环境，只有当电子邮件通过 OME 路由时，本地用户才能使用 OME 发送和接收Exchange Online。 若要在混合 Exchange 环境中配置 OME，您需要首先使用混合配置[](/Exchange/exchange-hybrid)向导配置混合，然后将邮件配置为从[Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server)流向您的电子邮件服务器，然后将邮件配置为从您的电子邮件服务器流向[Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。 将邮件配置为通过邮件流Office 365，然后可以使用本指南为 OME 配置邮件流规则。

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>创建邮件流规则以使用新的 OME 功能加密电子邮件

可以使用 EAC 定义邮件流规则，以使用新的 OME 功能触发邮件加密。

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>使用 EAC 创建使用新的 OME 功能加密电子邮件的规则

1. 在 Web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户登录[Office 365。](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. 选择" **管理"** 磁贴。

3. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心，</a>choose **Admin centers** \> **Exchange**.

4. 在 EAC 中，**转到"邮件** 流 \> ""规则"，然后选择 **"新建"** ![ 图标。](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \>**创建新规则**。 有关使用 EAC 的信息，请参阅 Exchange[中的Exchange Online。](/exchange/exchange-admin-center)

5. 在 **"** 名称"中，键入规则的名称，如加密邮件 DrToniRamos@hotmail.com。

6. 在 **"在应用此规则的条件**"中，选择一个条件，并在必要时输入一个值。 例如，若要加密发送到 DrToniRamos@hotmail.com 的邮件：

   1. 在“在以下情况应用此规则”中，选择“收件人为”。

   2. 从联系人列表中选择一个现有名称，或在“检查名称”框中键入一个新的电子邮件地址。

      - 若要选择一个现有名称，可以从列表中进行选择，然后单击“确定”。

      - 若要输入新名称，请在"检查名称"框中键入电子邮件地址，然后选择"**检查名称**"" \> **确定"。**

7. 若要添加更多条件，请选择" **更多选项** "，然后选择" **添加** 条件"，然后从列表中选择。

   例如，若要仅在收件人在组织外部时应用规则，请选择"添加条件"，然后选择"收件人在组织外部 **/** 内部 \> **""** 确定 \> **"。**

8. 若要使用新的 OME 功能启用加密，请从"执行以下操作"中选择"修改邮件安全性"，然后选择"应用Office 365 邮件加密 **和权限保护"。** 从列表中选择 RMS 模板，选择"保存 **"，** 然后选择"确定 **"。**
  
  模板列表包括所有默认模板和选项，以及已创建供用户Office 365。 如果列表为空，请确保你已Office 365 邮件加密设置新功能，如设置新的Office 365 邮件加密[功能中所述](set-up-new-message-encryption-capabilities.md)。 有关默认模板的信息，请参阅 [配置和管理 Azure 信息保护的模板](/information-protection/deploy-use/configure-policy-templates)。 有关"不要转发 **"选项的信息** ，请参阅电子邮件 [的"不要转发"选项](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。 有关仅 **加密选项的信息** ，请参阅电子邮件的仅 [加密选项](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

  如果要指定 **其他操作** ，可以选择添加操作。

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>使用 EAC 更新现有邮件流规则以使用新的 OME 功能

1. 在 Web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户登录[Office 365。](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. 选择" **管理"** 磁贴。

3. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心，</a>choose **Admin centers** \> **Exchange**.

4. In the EAC, go to **Mail flow** \> **Rules**.

5. 在邮件流规则列表中，选择要修改的规则以使用新的 OME 功能，然后选择"编辑 **编辑** ![ "图标 ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。

6. 若要使用新的 OME 功能启用加密，请从"执行以下操作"中选择"修改邮件安全性"，然后选择"应用Office 365 邮件加密 **和权限保护"。** 从列表中选择 RMS 模板，选择"**保存"，** 然后选择"确定 **"。**

   模板列表包括所有默认模板和选项，以及已创建供用户Office 365。 如果列表为空，请确保你已Office 365 邮件加密设置新功能，如设置基于 Azure 信息保护 构建的新 Office 365 邮件加密[功能中所述](set-up-new-message-encryption-capabilities.md)。 有关默认模板的信息，请参阅 [配置和管理 Azure 信息保护的模板](/information-protection/deploy-use/configure-policy-templates)。 有关"不要转发"选项的信息，请参阅电子邮件 [的"不要转发"选项](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。 有关仅加密选项的信息，请参阅加密 [仅电子邮件选项](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

   如果要指定 **其他操作** ，可以选择添加操作。

7. 从 **"执行以下操作"列表中**，删除分配给"修改邮件安全性"" \> **应用以前版本的 OME"的任何操作**。

8. 选择“**保存**”。

## <a name="create-mail-flow-rules-to-remove-encryption-for-email-messages-with-the-new-ome-capabilities"></a>创建邮件流规则以使用新的 OME 功能删除电子邮件的加密

可以使用 EAC 定义邮件流规则，以使用新的 OME 功能触发删除邮件加密。

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>使用 EAC 创建规则以使用新的 OME 功能从电子邮件中删除加密

可以删除组织应用的加密。

1. 在 Web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户登录[Office 365。](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. 选择" **管理"** 磁贴。

3. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心，</a>choose **Admin centers** \> **Exchange**.

4. 在 EAC 中，**转到"邮件** 流 \> ""规则"，然后选择 **"新建"** ![ 图标。](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \>**创建新规则**。 有关使用 EAC 的信息，请参阅 Exchange[中的Exchange Online。](/exchange/exchange-admin-center)

5. 在 **"** 名称"中，键入规则的名称，例如"从传出邮件中删除加密"。

6. 在 **"在应用此规则的条件**"中，选择应从邮件中删除加密的条件。 添加 **发件人位于用于发送邮件** 的组织内部，或收件人位于用于接收邮件 \>  \> 的组织内部。

7. 在 **"执行以下操作"中**，**选择"修改邮件安全性** \> **""删除Office 365 邮件加密和权限保护"。**

8. 选择“**保存**”。

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>为没有新功能Office 365 邮件加密邮件流规则

如果你尚未将组织移动到新的 OME 功能，Microsoft 建议你制定一个计划，在组织合理时尽快移动到新的 OME 功能。 有关说明，请参阅[设置基于 Azure 信息Office 365 邮件加密构建的新功能](set-up-new-message-encryption-capabilities.md)。 否则，[请参阅为不使用新 OME 功能Office 365 邮件加密定义邮件流规则](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities)。

## <a name="related-content"></a>相关内容

[Office 365 中的加密](encryption.md)

[设置全新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)

[将品牌添加到加密邮件](add-your-organization-brand-to-encrypted-messages.md)

[Exchange Online 中的邮件流规则（传输规则）](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
