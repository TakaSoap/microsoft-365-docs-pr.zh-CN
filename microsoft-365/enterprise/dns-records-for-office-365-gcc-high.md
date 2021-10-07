---
title: Office 365 GCC High DNS 记录
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 摘要：高Office 365 GCC DNS 记录
hideEdit: true
ms.openlocfilehash: 103d6157bdb11f787b46b649a048b9fdd3fde5cb
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60174875"
---
# <a name="dns-records-for-office-365-gcc-high"></a>Office 365 GCC High DNS 记录

*本文适用于 Office 365 GCC High 和 Microsoft 365 GCC High*

作为加入高Office 365 GCC的一部分，您需要将 SMTP 和 SIP 域添加到联机服务租户。  你将使用 Azure AD PowerShell 中的 New-MsolDomain cmdlet 完成此操作，或使用 [Azure](https://portal.azure.us) 政府门户启动添加域和证明所有权的过程。

将域添加到租户并进行验证后，请使用以下指南为以下服务添加相应的 DNS 记录。  您可能需要修改下表，以满足组织对入站 MX 记录 () 以及您已有的任何现有 Exchange 自动发现 () 的需求。  我们强烈建议与邮件团队协调这些 DNS 记录，以避免电子邮件出现任何中断或错误传递。

## <a name="exchange-online"></a>Exchange Online

| 类型 | 优先级 | 主机名 | 指向地址或值 | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | *tenant*.mail.protection.office365.us (请参阅下文了解其他详细信息)  | 1 Hour |
| TXT | - | @ | v=spf1 include：spf.protection.office365.us -all | 1 小时 |
| CNAME | - | autodiscover | autodiscover.office365.us | 1 Hour |

### <a name="exchange-autodiscover-record"></a>Exchange自动发现记录

如果在本地Exchange Server，建议在迁移到 Exchange Online 时保留现有记录，完成迁移后更新该记录。 

### <a name="exchange-online-mx-record"></a>Exchange OnlineMX 记录

接受域的 MX 记录值遵循上述标准格式 *：tenant*.mail.protection.office365.us，将 *租户* 替换为默认租户名称的第一部分。

例如，如果你的租户名称 contoso.onmicrosoft.us，你将使用 contoso.mail.protection.office365.us **作为** MX 记录的值。

## <a name="skype-for-business-online"></a>Skype for Business Online

### <a name="cname-records"></a>CNAME 记录

| 类型 | 主机名 | 指向地址或值 | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.gov.skypeforbusiness.us | 1 小时 |
| CNAME | lyncdiscover | webdir.online.gov.skypeforbusiness.us | 1 Hour |

### <a name="srv-records"></a>SRV 记录

| 类型 | 服务 | 协议 | 端口 | 粗细 | 优先级 | 名称 | Target | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_tls | 443 | 1 | 100 | @ | sipdir.online.gov.skypeforbusiness.us | 1 Hour |
| SRV | \_sipfederationtls | \_tcp | 5061 | 1 | 100 | @ | sipfed.online.gov.skypeforbusiness.us | 1 Hour |

## <a name="additional-dns-records"></a>其他 DNS 记录

> [!IMPORTANT]
> 如果 DNS 区域中已有 *msoid* CNAME 记录，则此时必须从 DNS 中删除该记录。  msoid 记录与以前Microsoft 365 企业版应用程序 (*应用程序* Office 365 专业增强版) ，并且将阻止激活成功。
