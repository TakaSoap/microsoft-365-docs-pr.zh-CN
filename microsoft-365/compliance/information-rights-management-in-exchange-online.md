---
title: 带 AD RMS 的 Exchange Online 邮件加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
ms.custom:
- seo-marvel-apr2020
description: 了解如何将 Exchange Online IRM 配置为使用内部部署 Active Directory 权限管理服务 (AD RMS) 以满足组织要求。
ms.openlocfilehash: 867293d5afa29242409cc92702ff8b505ed21196
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60175151"
---
# <a name="exchange-online-mail-encryption-with-ad-rms"></a>带 AD RMS 的 Exchange Online 邮件加密

为了帮助防止信息泄露，Exchange Online 的信息权限管理 (IRM) 功能可为电子邮件和附件提供联机和脱机保护。 您可以配置 Exchange Online IRM 以使用内部部署 Active Directory 权限管理服务 (AD RMS) ，以满足组织要求。 这并不常见。 如果不需要使用 AD RMS，[请改为](ome.md)Office 365 邮件加密。 

Microsoft Outlook 或 Outlook 网页版 用户可以应用 IRM 保护，并且管理员可以使用传输保护规则或Outlook规则应用 IRM 保护。 IRM 可帮助您和您的用户控制谁可以访问、转发、打印或复制电子邮件中的敏感数据。
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>更改 IRM 与 OME Office 365 邮件加密 (OME) Azure Active Directory

自 2017 年 9 月开始，当你为组织设置新的 Office 365 邮件加密 功能时，你还会设置 IRM 以用于 Azure 权限管理 (Azure RMS) 。 你不再单独使用 Azure RMS 设置 IRM。 相反，OME 和权限管理可以无缝协作。 有关新功能的更多详细信息，请参阅Office 365 邮件加密[常见问题](./ome-faq.yml)。 如果你已准备好在组织中开始使用新的 OME 功能，请参阅设置基于 Azure 信息保护Office 365 邮件加密构建的新 OME[功能](./set-up-new-message-encryption-capabilities.md)。
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>IRM 如何与 Exchange Online 和 Active Directory Rights Management Services

Exchange OnlineIRM 使用本地 Active Directory Rights Management Services (AD RMS) ，这是 Windows Server 2008 及更高版本中的一种信息保护技术。 通过将 AD RMS 权限策略模板应用于电子邮件，可将 IRM 保护应用于电子邮件。 权限附加到邮件本身，以便联机和脱机以及组织防火墙内外进行保护。
  
用户可以将模板应用于电子邮件，以控制收件人对邮件拥有的权限。 通过对邮件应用 AD RMS 权限策略，您可以控制转发、从邮件提取信息、保存邮件或打印邮件等操作。
  
可以将 IRM 配置为使用运行 Windows Server 2008 或更高版本的 AD RMS 服务器。 您可以使用此 AD RMS 服务器为基于云的组织管理 AD RMS 权限策略模板。 Outlook 还依靠 AD RMS 服务器来使用户可以向他们发送的邮件应用 IRM 保护。 有关详细信息，请参阅 [将 IRM 配置为使用内部部署 AD RMS 服务器](configure-irm-to-use-an-on-premises-ad-rms-server.md)。 
  
启用后，IRM 保护可以应用于邮件，如下所示：
  
- **用户可以使用自定义模板和模板Outlook Outlook 网页版。** 用户可以通过从"设置权限"列表中选择模板，将 AD RMS 权限 **策略模板应用于** 电子邮件。 当用户发送受 IRM 保护的邮件时，任何使用支持格式的附加文件也会受到与邮件相同的 IRM 保护。 IRM 保护会应用于与 Word、Excel 和 PowerPoint 相关联的文件以及 .xps 文件和附加的电子邮件。 
    
- **管理员可以使用传输保护规则将 IRM 保护自动应用于Outlook Outlook 网页版。** 可以创建传输保护规则以使用 IRM 保护邮件。 将传输保护规则操作配置为将 AD RMS 权限策略模板应用于符合规则条件的邮件。 启用 IRM 后，组织的 AD RMS 权限策略模板可用于名为 将权限保护应用于邮件的传输保护规则 **操作**。
    
- **管理员可以创建Outlook规则。** Outlook保护规则自动将 IRM 保护应用于 Outlook 2010 (而不是 Outlook 网页版) 中的邮件，这些邮件条件包括发件人的部门、邮件的收件人以及收件人是组织内部还是外部。 有关详细信息，请参阅[Create an Outlook Protection Rule](/exchange/create-an-outlook-protection-rule-exchange-2013-help)。
