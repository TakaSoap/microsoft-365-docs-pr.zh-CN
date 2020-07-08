---
title: 配置和控制外部电子邮件转发、自动转发、5.7.520 访问被拒绝、禁用外部转发、管理员已禁用外部转发、出站反垃圾邮件策略
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 88c3dae4f5a6786fe4eddea0d5e1c61dda837a87
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080109"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a>在 Office 365 中配置外部电子邮件转发

外部转发由*出站反垃圾邮件策略*控制，并根据配置的设置范围限定给用户。 当前支持3个设置：

- **自动**–在此模式下，系统负责确定是否允许转发的邮件。  这是默认模式，在此模式下，系统将阻止自动外部转发。

- **启用**–允许和不限制自动外部转发。

- **关**-自动外部转发被禁用，并将导致向最终用户发送未送达报告（NDR）。

有关如何配置这些设置的详细信息，请参阅[配置 EOP 中的出站垃圾邮件筛选](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide)。

## <a name="controlling-external-email-forwarding"></a>控制外部电子邮件转发

作为组织的管理员，你可能需要对公司要求进行限制或控制能够在组织外部使用收件箱规则或 SMTP 转发自动转发电子邮件的用户。 电子邮件转发可能是一项非常有用的功能，但也可以通过可能泄露的信息带来风险，即使是向攻击者提供的信息可以被利用来攻击组织或其合作伙伴也是如此。

Office 365 不允许通过 "收件箱" 规则或 "邮箱" 配置自动进行外部转发，这将提供安全的默认策略。 但是，管理员可以为组织中的所有用户或部分用户修改这些设置。 内部用户之间的转发邮件不受此类修改的影响。

> [!NOTE]
> 在 Office 365 中禁用自动转发外部地址的过程分阶段进行，详细信息通过[消息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter)发布进行通信。 若要帮助管理员准备这些更改，请提前修改策略以确保用户不会中断他们的用户。

可在 "[自动转发的邮件" 报告](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide)中找到有关在组织中使用自动转发（收件箱规则或 SMTP 转发）的用户的详细信息。

## <a name="the-blocked-email-forwarding-message"></a>阻止的电子邮件转发邮件

当一封邮件被检测为自动转发，并且组织策略*阻止*将向最终用户生成**未送达报告（NDR）** 的活动。 报告将指示邮件未送达。 NDR 将具有以下格式： 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
