---
title: 出于 S/MIME 目的将用户证书同步到 Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您将了解到在 Exchange Online 中发送受 S/MIME 保护的邮件之前，如何将相应的证书发布到 Office 365。
ms.openlocfilehash: 634b65e45b01186a27f9ae61c91d4b27f1a11635
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826477"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>出于 S/MIME 目的将用户证书同步到 Office 365

必须先设置适当的证书，然后才能够在 Exchange Online 中发送受 S/MIME 保护的邮件。 若要通过 Exchange Online 发送加密邮件，发件人的电子邮件应用使用收件人的公用证书对邮件进行加密。 此公用 X.509 证书必须向 Office 365 发布。

## <a name="to-sync-certificates-that-support-smime"></a>对支持 S/MIME 的证书进行同步

首先，通过颁发证书并在本地 Active Directory 域服务中发布证书来设置 S/MIME。 有关详细信息，请参阅 [Active Directory 证书服务概述](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))。

发布证书之后，使用 Azure AD Connect 工具将本地 Exchange 环境中的用户数据同步至 Office 365。 有关此过程的详细信息，请参阅 Azure [AD Connect 同步：了解和自定义同步](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)。

在（出于 S/MIME 目的）同步其他目录数据的过程中，该工具还会  **同步每个用户对象的 userCertificate** 和 **userSMIMECertificate** 属性，以便这些数据可用于签名和加密邮件。

## <a name="more-information"></a>更多信息

[将 S/MIME 用于邮件签名和加密](s-mime-for-message-signing-and-encryption.md)

[什么是 Azure AD Connect？](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
