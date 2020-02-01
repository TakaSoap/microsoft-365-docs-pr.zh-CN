---
title: 出于 S/MIME 目的将用户证书同步到 Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: 必须先设置适当的证书，然后才能够发送受 S/MIME 保护的邮件。发件人的电子邮件程序使用收件人的公用证书对邮件进行加密，以通过 Exchange Online 发送加密邮件。此公用 X.509 证书必须向 Office 365 发布。
ms.openlocfilehash: a62af3b176f29ec2bd8c97ae02178c87b7a63544
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598189"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>出于 S/MIME 目的将用户证书同步到 Office 365

在任何人可以在 Exchange Online 中发送受 S/MIME 保护的邮件之前，必须设置相应的证书。 若要通过 Exchange Online 发送加密邮件，发件人的电子邮件应用程序将使用收件人的公共证书来加密邮件。 此公用 X.509 证书必须向 Office 365 发布。

## <a name="to-sync-certificates-that-support-smime"></a>对支持 S/MIME 的证书进行同步

首先，通过颁发证书并在本地 Active Directory 域服务中发布证书来设置 S/MIME。 有关详细信息，请参阅 [Active Directory 证书服务概述](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))。

发布证书后，使用 Azure AD Connect 工具将用户数据从内部部署 Exchange 环境同步到 Office 365。 有关此过程的详细信息，请参阅[AZURE AD Connect sync：了解并自定义同步](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)。

除了同步其他目录数据之外，出于 S/MIME 目的，该工具还会同步每个用户对象的**userCertificate**和**userSMIMECertificate**属性，以便数据可用于对邮件进行签名和加密。

## <a name="more-information"></a>详细信息

[将 S/MIME 用于邮件签名和加密](s-mime-for-message-signing-and-encryption.md)

[什么是 Azure AD Connect？](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
