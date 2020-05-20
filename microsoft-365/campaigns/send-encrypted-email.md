---
title: 发送加密电子邮件
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: 了解如何使用 Outlook 发送加密电子邮件。
ms.openlocfilehash: 5318fbe045c909e3b7f81d195a8e6b4d5eb96dc1
ms.sourcegitcommit: 5c43e89ed94ad9fd1db049446383c65e548189b7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322143"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>加密或标记敏感电子邮件

您的数据和市场活动信息非常重要且通常是保密信息。 使用加密和敏感度标签帮助保护这些敏感信息，以便您和您的电子邮件收件人按照所需的敏感度对待信息。


## <a name="best-practices"></a>最佳做法

在发送包含机密或敏感信息的电子邮件之前，请考虑启用：

- **加密：** 您可以加密您的电子邮件以保护电子邮件中的信息的隐私。 加密电子邮件时，会将其从可读纯文本转换为已编码的 cypher 文本。 只有具有与用于加密邮件的公钥相匹配的私钥的收件人才能解密邮件以进行读取。 但是，如果没有对应私钥的任何收件人，则会看到无法破译的文本。 您的管理员可以定义规则以自动对满足特定条件的邮件进行加密。 例如，您的管理员可以创建一个规则来加密在组织外部发送的所有邮件或提及特定字词或短语的所有邮件。 将自动应用任何加密规则。
- **敏感度标签：** 你的市场活动还可以设置可应用于文件和电子邮件的敏感度标签，以使其符合你的市场活动的信息保护策略。 在设置标签时，标签会随电子邮件一起保留，即使发送时也是如此，例如，通过在邮件中显示为标头。

![包含标签和加密标注的电子邮件的关系图](../media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a>设置

如果要对不符合预定义规则的邮件进行加密，或管理员未设置任何规则，则可以在发送邮件之前应用各种不同的加密规则。 若要从 Outlook 2013 或2016或 Outlook 2016 for Mac 发送加密邮件，请选择 "选项" " **> 权限**"，然后选择所需的保护选项。 您还可以通过在 Outlook 网页网站中选择 "**保护**" 按钮发送加密邮件。 有关详细信息，请参阅[Outlook FOR PC 中的发送、查看和回复加密邮件](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)。

## <a name="admin-settings"></a>管理设置

您可以在[Office 365 中](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)了解有关设置电子邮件加密的电子邮件加密的所有信息。

### <a name="automatically-encrypt-email-messages"></a>自动加密电子邮件

管理员可以创建邮件流规则，以自动保护从您的市场活动中发送和接收的电子邮件。 设置用于加密任何传出电子邮件的规则，并删除来自组织内部或从您的组织发送的加密邮件的答复的加密邮件的加密。 

您可以创建邮件流规则，以使用新的 Office 365 邮件加密（OME）功能对电子邮件进行加密。 使用 Exchange 管理中心（EAC）定义用于触发邮件加密的邮件流规则，这些规则使用新的 OME 功能。 

1. 在 web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户，登录到 Office 365。 
2. 选择 "管理" 磁贴。 
3. 在 "管理中心" 中，选择 "**管理中心" > Exchange**。 

有关详细信息，请参阅[在 Office 365 中定义用于加密电子邮件的邮件流规则](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)。

### <a name="brand-your-encryption-messages"></a>对加密邮件进行品牌打造

您还可以应用您的市场活动品牌来自定义电子邮件中的外观和文本。 有关详细信息，请参阅[将组织的品牌添加到加密邮件](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)。

