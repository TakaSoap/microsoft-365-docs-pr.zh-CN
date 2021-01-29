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
- m365solution-smb
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
ms.openlocfilehash: d17abccd645b4dfdf933906dc90175be51f95c9a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044212"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>加密或标记敏感电子邮件

你的数据和市场活动信息非常重要，并且通常是机密的。 使用加密和敏感度标签帮助保护此敏感信息，以便你和电子邮件收件人使用所需的敏感度处理信息。

## <a name="best-practices"></a>最佳做法

在发送包含机密或敏感信息的电子邮件之前，请考虑打开：

- **加密：** 您可以加密电子邮件以保护电子邮件中信息的隐私。 加密电子邮件时，电子邮件会从可读纯文本转换为加密的cypher 文本。 只有具有与用于加密邮件的公钥匹配的私钥的收件人才能解密邮件进行阅读。 但是，任何没有相应私钥的收件人都可以看到无法解密的文本。 管理员可以定义规则以自动加密符合特定条件的邮件。 例如，管理员可以创建一个规则，对发送到组织外部的所有邮件或提及特定字词或短语的所有邮件进行加密。 将自动应用任何加密规则。
- **敏感度标签：** 市场活动还可以设置可应用于文件和电子邮件的敏感度标签，以使它们符合市场活动的信息保护策略。 设置标签时，即使电子邮件已发送，标签也一直保留，例如，显示为邮件头。

![包含标签和加密标注的电子邮件关系图](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a>设置

如果要加密不满足预定义规则的邮件，或者管理员未设置任何规则，可以在发送邮件之前应用各种不同的加密规则。 若要从 Outlook 2013 或 2016 或 Outlook 2016 for Mac 发送加密邮件，请选择"选项> **权限**"，然后选择所需的保护选项。 您还可以通过选择 Outlook 网页中的"保护"按钮发送加密邮件。 有关详细信息，请参阅 Outlook for PC 中的发送、查看和回复 [加密邮件](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)。

## <a name="admin-settings"></a>管理员设置

你可以了解有关在 [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)中设置电子邮件加密的所有信息。

### <a name="automatically-encrypt-email-messages"></a>自动加密电子邮件

管理员可以创建邮件流规则，以自动保护从市场活动发送和接收的电子邮件。 设置规则以加密任何传出电子邮件，并从来自组织内部的加密邮件或对从组织发送的加密邮件的答复中删除加密。

创建邮件流规则，以使用新的 Office 365 邮件加密和 OME (加密) 电子邮件。 定义邮件流规则，以使用 Exchange 管理中心或 EAC (OME 功能触发) 。 

1. 在 Web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户登录。
2. 选择"管理"磁贴。
3. 在管理中心中，选择 **Exchange >管理中心**。

有关详细信息，请参阅 [定义用于加密电子邮件的邮件流规则](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)。

### <a name="brand-your-encryption-messages"></a>为加密邮件打造品牌

还可以应用市场活动品牌以自定义电子邮件的外观和文本。 有关详细信息，请参阅 [将组织的品牌添加到加密邮件中](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)。
