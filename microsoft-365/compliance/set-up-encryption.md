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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: 使用 Office 365，默认情况下会启用某些加密功能;其他功能可以配置为满足某些合规性或法律要求。
ms.openlocfilehash: e153c1e322adaea000cf686e857387d671b18a28
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051674"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>设置 Office 365 企业版中的加密

加密可保护内容免遭未经授权的用户读取。 因为 [Office 365](encryption.md) 中的加密可以使用各种技术和方法完成，所以没有一个地方可以打开或设置加密。 本文提供有关在信息保护策略中设置或配置加密的各种方法的信息。
  
> [!TIP]
> 如果要查找有关加密的更多技术详细信息，请参阅有关 [Office 365 中加密的技术参考详细信息](technical-reference-details-about-encryption.md)。
  
在 Office 365 中，默认情况下提供了多种加密功能。 可以配置其他加密功能以满足某些合规性或法律要求。 下表描述了适用于不同方案的多种加密方法。
  
|**应用场景**|**加密方法**|
|:-----|:-----|
|文件保存在 Windows 计算机上  <br/> |可以在 Windows 设备上使用 BitLocker 完成计算机级别的加密。 作为企业管理员或 IT 专业人员，可以使用 Microsoft Deployment Toolkit (MDT) 。 请参阅[为 BitLocker 设置 MDT。](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker)  <br/> |
|文件保存在移动设备上  <br/> |某些类型的移动设备对默认情况下保存到这些设备的文件进行加密。 借助 [内置的 Office 365](https://support.microsoft.com/en-us/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)移动设备管理功能，可以设置确定是否允许移动设备访问 Office 365 数据的策略。 例如，可以设置仅允许加密内容的设备访问 Office 365 数据的策略。 请参阅 [创建和部署设备安全策略](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)。  <br/> 要进一步控制移动设备与 Office 365 的交互方式，可考虑添加 [Microsoft Intune](/mem/intune/fundamentals/setup-steps)。  <br/> |
|你需要控制用于加密 Microsoft 数据中心数据的加密密钥  <br/> | 作为 Office 365 管理员，你可以控制组织的加密密钥，然后配置 Office 365 以使用它们加密 Microsoft 数据中心中的静态数据。  <br/> [使用 Office 365 中的客户密钥执行服务加密](customer-key-overview.md) <br/> |
|人们通过电子邮件与 Exchange Online (通信)   <br/> | 作为 Exchange Online 管理员，您具有多个用于配置电子邮件加密的选项。 具体包括：  <br/>  将 [Office 365 ](set-up-new-message-encryption-capabilities.md) 邮件加密 (OME) 与 Azure 权限管理 (Azure RMS) 一起，使用户能够在组织内部或外部发送加密邮件  <br/>  将 [S/MIME 用于邮件签名和加密](../security/defender-365-security/s-mime-for-message-signing-and-encryption.md) ，对电子邮件进行加密和数字签名  <br/>  使用 TLS [设置连接器以确保与另一个组织的安全邮件流](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner) <br/>  请参阅 [Office 365 中的电子邮件加密](./email-encryption.md)。  <br/> |
|文件从 OneDrive for Business 或 SharePoint Online (团队网站或文档库)   <br/> |当用户使用保存到 OneDrive for Business 或 SharePoint Online 的文件时，会使用 TLS 连接。 此功能内置于 Office 365 中。 请参阅 [OneDrive for Business 和 SharePoint Online 中的数据加密](./data-encryption-in-odb-and-spo.md)。  <br/> |
|文件在 Skype for Business Online (联机会议和 IM 对话)   <br/> |当用户使用 Skype for Business Online 处理文件时，TLS 将用于连接。 此功能内置于 Office 365 中。 请参阅 [Security and Archiving (Skype for Business Online) ](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)。  <br/> |
|在 Microsoft Teams (联机会议和 IM 对话中)   <br/> |当用户使用 Microsoft Teams 处理文件时，TLS 将用于连接。 此功能内置于 Office 365 中。 Microsoft Teams 当前不支持加密电子邮件的内联呈现。 若要阻止加密的电子邮件以加密方式登录 Microsoft Teams，请参阅邮件 [加密常见问题](./ome-faq.md?view=o365-worldwide#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail)解答。  <br/> 

## <a name="additional-information"></a>其他信息

若要了解有关包含加密选项的文件保护解决方案的详细信息，请参阅 [Office 365](https://www.microsoft.com/download/details.aspx?id=55523)中的文件保护解决方案。
