---
title: 设置 Office 365 企业版中的加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: 使用Office 365，默认情况下会启用某些加密功能;其他功能可以配置为满足某些合规性或法律要求。
ms.openlocfilehash: 00035af0049abedff8a794710649f162576dc46c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152918"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>设置 Office 365 企业版中的加密

加密可保护内容免遭未经授权的用户读取。 由于[Office 365](encryption.md)中的加密可以使用各种技术和方法完成，因此没有一个地方可以打开或设置加密。 本文提供有关在信息保护策略中设置或配置加密的各种方法的信息。

> [!TIP]
> 如果要查找有关加密的更多技术详细信息[，请参阅有关](technical-reference-details-about-encryption.md)加密技术Office 365。

使用 Office 365，默认情况下提供了多种加密功能。 可以配置其他加密功能以满足某些合规性或法律要求。 下表描述了适用于不同方案的多种加密方法。

<br>

****

|应用场景|加密方法|
|---|---|
|文件保存在Windows计算机上|可以在任何设备上使用 BitLocker 在计算机Windows加密。 作为企业管理员或 IT Pro，可以使用 Microsoft Deployment Toolkit (MDT) 。 请参阅[为 BitLocker 设置 MDT。](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker)|
|文件保存在移动设备上|某些类型的移动设备对默认情况下保存到这些设备的文件进行加密。 通过[内置功能Office 365 移动设备管理，](https://support.microsoft.com/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)您可以设置确定是否允许移动设备访问 Office 365。 例如，你可以设置仅允许加密内容的设备访问数据Office 365策略。 请参阅 [创建和部署设备安全策略](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)。 <p> 要进一步控制移动设备与移动设备Office 365，你可以[考虑添加](/mem/intune/fundamentals/setup-steps)Microsoft Intune。|
|你需要控制用于加密 Microsoft 数据中心数据的加密密钥|作为Office 365管理员，您可以控制组织的加密密钥，然后将 Office 365 配置为使用这些密钥加密 Microsoft 数据中心中的静态数据。 <p> [使用 Office 365 中的客户密钥执行服务加密](customer-key-overview.md)|
|人们通过电子邮件通信 (Exchange Online) |作为Exchange Online管理员，您具有多个用于配置电子邮件加密的选项。 包括： <ul><li>将[Office 365 OME](set-up-new-message-encryption-capabilities.md) (OME) Azure 权限管理 (Azure RMS) ，使用户能够在组织内部或外部发送加密邮件</li><li>使用 [S/MIME](/exchange/security-and-compliance/smime-exo/smime-exo) 对电子邮件进行加密和数字签名</li><li>使用 TLS [设置连接器以确保与另一个组织的安全邮件流](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)</li></ul> <p> 请参阅[电子邮件加密Office 365。](./email-encryption.md)|
|文件从团队网站或文档库 (OneDrive for Business或SharePoint Online) |当用户使用保存到 OneDrive for Business 或 SharePoint Online 的文件时，使用 TLS 连接。 This is built into Office 365 automatically. 请参阅[OneDrive for Business 和 SharePoint Online 中的数据加密](./data-encryption-in-odb-and-spo.md)。|
|文件在联机会议和 IM 对话中共享 (Skype for Business Online) |当用户使用 Skype for Business Online 处理文件时，TLS 将用于连接。 This is built into Office 365 automatically. 请参阅[Security and Archiving (Skype for Business Online) ](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)。|
|在联机会议和 IM 对话中共享 (Microsoft Teams) |当用户使用 TLS 处理Microsoft Teams时，TLS 将用于连接。 This is built into Office 365 automatically. Microsoft Teams当前不支持加密电子邮件的内联呈现。 若要防止加密电子邮件以加密Microsoft Teams登录，请参阅邮件[加密常见问题](./ome-faq.yml#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail-)解答。|
|

## <a name="additional-information"></a>其他信息

若要了解有关包含加密选项的文件保护解决方案的详细信息，请参阅文件保护解决方案[Office 365。](https://www.microsoft.com/download/details.aspx?id=55523)
