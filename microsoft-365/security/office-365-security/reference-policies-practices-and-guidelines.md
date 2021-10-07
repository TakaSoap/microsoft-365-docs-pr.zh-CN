---
title: 参考：策略、实践和指南
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft 已制定各种策略、过程，并采用多个行业最佳做法来帮助保护我们的用户免受滥用、不需要或恶意电子邮件的干扰。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 21b1918155755d7786f7b797ae7c705ca8c0ec39
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211989"
---
# <a name="reference-policies-practices-and-guidelines"></a>参考：策略、实践和指南

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 致力于在 Web 上提供最可信赖的用户体验。 因此，Microsoft 已开发了多种策略、过程并采用多个行业的最佳实践，以保护我们的用户免受滥用、不必要或恶意的电子邮件的侵扰。 尝试向用户发送电子邮件的发件人应确保他们完全理解并遵循本文中的指导，以帮助进行此工作并帮助避免潜在的传递问题。

如果您不遵从这些策略和指南，我们的支持小组可能无法协助您。 如果您遵循本文中介绍的指南、实践和策略，但基于您的发送 IP 地址仍然遇到传送问题，请按步骤提交除名请求。 有关说明 [，请参阅使用除名门户将自己从阻止的发件人名单中删除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。

## <a name="general-microsoft-policies"></a>Microsoft 一般性策略

发送给用户Microsoft 365用户的电子邮件必须遵守管理电子邮件传输和使用电子邮件传输Microsoft 365。

- 适用于服务条款Microsoft 365;特别是，禁止使用服务发送垃圾邮件或分发恶意软件。

- [Microsoft 服务协议](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>政府法规

发送给用户Microsoft 365必须遵守在适用管辖下管理电子邮件通信的所有适用法律和法规。

- [CAN-SPAM Act:A Compliance Guide for Business](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- ["Remove Me" Responses and Responsibilities:Email Marketers Must Honor "Unsubscribe" Claims](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a>技术指南

发送到 Microsoft 365 的电子邮件应符合以下文档中所列的适用建议 (某些链接仅提供英文) 。

- [RFC 2505:Anti-Spam Recommendations for SMTP MTAs](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920:SMTP Service Extension for Command Pipelining](https://www.ietf.org/rfc/rfc2920.txt)

此外，连接到 Microsoft 365 服务器必须遵守以下要求：

- 发件人应符合互联网电子邮件传输的所有技术标准，该标准由互联网协会的互联网工程任务组 (IETF) 发布，包括 RFC 5321、RFC 5322 和其他。

- 在给出 500 和 599 之间的数值 SMTP 错误响应代码后（也称为永久未送达响应或 NDR），发件人不得再次向该收件人传输邮件。

- 多个未送达响应后，发件人必须停止进一步向该收件人发送邮件的操作。

- 邮件不得通过不安全的电子邮件中继或代理服务器传输。

- 从单个列表或从由发件人托管的所有列表取消订阅的机制，必须清楚地说明，且易于供收件人查找使用。

- 来自动态的 IP 空间的连接可能不被接受。

- 电子邮件服务器必须具有有效的反向 DNS 记录。

## <a name="reputation-management"></a>信誉管理

发件人、ISP 和其他服务提供商应主动管理出站 IP 地址的信誉。

## <a name="microsoft-365-limits"></a>Microsoft 365限制

发件人必须遵守Microsoft 365限制中列出的Exchange Online Protection[限制](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)。

## <a name="email-delivery-resources-and-organizations"></a>电子邮件传送资源和组织

Microsoft 积极与行业机构和服务提供商合作，以改善互联网和电子邮件的生态系统。这些组织已经发布了我们支持并建议发件人遵循的最佳实践的文档。这提高了您在世界各地的多个电子邮件服务提供商直接传送邮件的能力。

- [信息传送、恶意软件和移动反滥用工作组](https://www.m3aawg.org/)

- [在线信任联盟](https://www.internetsociety.org/ota/)

- [电子邮件发件人&提供商联盟](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>滥用和垃圾邮件报告

若要报告非法、滥用、不需要或恶意的电子邮件，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。 发送这些类型的通信违反 Microsoft 策略，将针对已确认的报告采取适当的措施。

## <a name="law-enforcement"></a>法律执行

如果您是执法机构的成员，想就 Office 365 相关法律文档为 Microsoft Corportation 服务，或如果您对提交给 Microsoft 的法律文档有任何问题，请拨打 (1) (425) 722-1299。