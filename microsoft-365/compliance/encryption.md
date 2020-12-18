---
title: Microsoft 365 中的加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365solution-mip
- m365initiative-compliance
description: 使用 Office 365，内容将静态加密，并采用可用的最强加密、协议和技术进行传输。 获取 Office 365 中加密的概述。
ms.openlocfilehash: 1aee9d401891e807f572c1eed2bc22a54f39e534
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709565"
---
# <a name="encryption"></a>加密

加密是文件保护和信息保护策略的重要组成部分。 本文概述了 Office 365 的加密。 获取有关加密任务的帮助，例如如何为组织设置加密以及如何对 Office 文档进行密码保护。
  
- 有关证书和技术（如 TLS）的信息，请参阅有关 [Office 365 中加密的技术参考详细信息](technical-reference-details-about-encryption.md)。

- 若要了解如何为组织配置或设置加密，请参阅"在 Office [365](set-up-encryption.md)企业版中设置加密"。

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>什么是加密？它在 Office 365 中如何工作？

加密过程将称为纯 (的数据编码为) 加密图文集。 与纯文本不同，除非解密 ciphertext，否则用户或计算机无法使用 ciphertext。 解密需要只有授权用户的加密密钥。 加密有助于确保只有经过授权的收件人才能解密您的内容。 内容包括文件、电子邮件、日历条目等。
  
加密本身不会阻止内容拦截。 加密是组织的更大信息保护策略的一部分。 通过使用加密，有助于确保只有授权方才能使用加密数据。
  
可以同时具有多个加密层。 例如，您可以加密电子邮件以及电子邮件流通过的通信通道。 使用 Office 365，数据将静态加密和传输，使用多种强加密协议，以及包括传输层安全性/安全套接字层 (TLS/SSL) 、Internet 协议安全性 (IPSec) 和高级加密标准 (AES) 的技术。
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>静态数据和传输数据加密

 其余数据的示例包括已上传到 SharePoint 库的文件、Project Online 数据、你在 Skype for Business 会议上载的文档、存储在邮箱文件夹中的电子邮件和附件，以及已上传到 OneDrive for Business 的文件。
  
 **传输数据的示例包括** 正在传递的邮件或联机会议进行的对话。 在 Office 365 中，每当用户的设备与 Microsoft 服务器通信时，或者当 Microsoft 服务器与另一台服务器通信时，数据都会在传输中。
  
使用 Office 365，多层和多种加密可以协同工作，保护您的数据。 下表包含一些示例，其中包含指向其他信息的链接。
  
|**内容类型**|**加密技术**|**了解详细信息的资源**|
|:-----|:-----|:-----|
|设备上的文件。 这些文件可能包括保存在文件夹中的电子邮件、保存在计算机、平板电脑或手机上的 Office 文档或保存到 Microsoft 云的数据。  <br/> |Microsoft 数据中心中的 BitLocker。 BitLocker 还可以在客户端计算机（如 Windows 计算机和平板电脑）上使用  <br/> Microsoft 数据中心 (DKM) 的分布式密钥管理器  <br/> Microsoft 365 的客户密钥  <br/> |[Windows IT 中心：BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Microsoft 信任中心：加密](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [云安全控制系列：加密 Rest 数据](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Exchange Online 如何进行电子邮件保密](exchange-online-secures-email-secrets.md) <br/> [使用客户密钥执行服务加密](customer-key-overview.md) <br/> |
|用户之间传输的文件。 这些文件可以包括在用户之间共享的 Office 文档或 SharePoint 列表项。  <br/> |传输中的文件的 TLS  <br/> |[OneDrive for Business 和 SharePoint Online 中的数据加密](data-encryption-in-odb-and-spo.md) <br/> [Skype for Business Online：安全性和存档](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|收件人之间传输的电子邮件。 此电子邮件包括由 Exchange Online 托管的电子邮件。  <br/> |使用 Azure 权限管理、S/MIME 和 TLS 对传输中的电子邮件进行 Office 365 邮件加密  <br/> |[Office 365 邮件加密 (OME)](ome.md) <br/> [Office 365 中的电子邮件加密](email-encryption.md) <br/> [Exchange Online 如何使用 TLS 保护 Office 365 中的电子邮件连接](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|使用 Microsoft Teams 在收件人之间传输的聊天、消息和文件。 <br/> |Teams 使用 TLS 和 MTLS 加密即时消息。 媒体流量使用安全 RTP (SRTP) 。 Teams 使用 FIPS (美国联邦信息处理标准) 加密密钥交换的兼容算法。 <br/> |[Teams 加密](https://docs.microsoft.com/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>如果我需要对加密进行更多控制以满足安全性和合规性要求，该做什么？

Microsoft 365 为 Office 365 中的卷加密、文件加密和邮箱加密提供 Microsoft 托管的解决方案。 此外，Microsoft 还提供您可以管理和控制的加密解决方案。 这些加密解决方案基于 Azure 构建。
  
若要了解详细信息，请参阅以下资源：
  
- [什么是 Azure 权限管理？](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

- [在管理中心激活权限管理](https://docs.microsoft.com/microsoft-365/enterprise/activate-rms-in-microsoft-365)

- [在 SharePoint 管理中心设置信息权限管理 (IRM)](set-up-irm-in-sp-admin-center.md)

- [使用 Office 365 中的客户密钥执行服务加密](customer-key-overview.md)

- [Microsoft 365 的双密钥加密](double-key-encryption.md)

## <a name="how-do-i"></a>我如何...

|**执行此任务**|**请参阅这些资源**|
|:-----|:-----|
|为组织设置加密  <br/> |[设置 Office 365 企业版中的加密](set-up-encryption.md) <br/> |
|查看有关证书、技术和 TLS 密码套件的详细信息 <br/> |[有关加密的技术详细信息](technical-reference-details-about-encryption.md) <br/> |
|在移动设备上处理加密邮件  <br/> |[在 Android 设备上查看加密邮件](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [在 iPhone 或 iPad 上查看加密邮件](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|使用密码保护加密文档  <br/><br/>  浏览器不支持密码保护。 使用桌面版本的 Word、Excel 和 PowerPoint 进行密码保护。 |[在文档、工作簿或演示文稿中添加或删除保护](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> 选择"**添加保护"** 部分，然后查看 **"使用密码加密"。**  |
|从文档中删除加密  <br/> |[在文档、工作簿或演示文稿中添加或删除保护](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> 选择"**删除保护"** 部分，然后查看 **"删除密码加密"。**  |


## <a name="related-topics"></a>相关主题

[规划 Microsoft 365 安全和信息保护功能](plan-for-security-and-compliance.md)

[保护 Microsoft 365 商业版计划的十大方法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)

[Microsoft Stream 视频级别加密和播放流](https://docs.microsoft.com/stream/network-overview#video-level-encryption-and-playback-flow)
