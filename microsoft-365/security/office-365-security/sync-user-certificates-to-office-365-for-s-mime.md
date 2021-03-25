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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: 本文将介绍在 Exchange Online 中发送受 S/MIME 保护的邮件之前，如何向 Office 365 发布相应的证书。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 387f9f405afd45254c6568aa92334a7ee5b4171f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203820"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>出于 S/MIME 目的将用户证书同步到 Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


必须先设置适当的证书，然后才能在 Exchange Online 中发送受 S/MIME 保护的邮件。 若要通过 Exchange Online 发送加密邮件，发件人的电子邮件应用使用收件人的公共证书加密邮件。 此公用 X.509 证书必须向 Office 365 发布。

## <a name="to-sync-certificates-that-support-smime"></a>对支持 S/MIME 的证书进行同步

首先，通过颁发证书并在本地 Active Directory 域服务中发布证书来设置 S/MIME。 有关详细信息，请参阅 [Active Directory 证书服务概述](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))。

发布证书后，使用 Azure AD Connect 工具将用户数据从本地 Exchange 环境同步到 Office 365。 有关此过程详细信息，请参阅 Azure [AD Connect 同步：了解并自定义同步](/azure/active-directory/hybrid/how-to-connect-sync-whatis)。

除了同步其他目录数据，出于 S/MIME 目的，该工具还将同步每个用户对象的  **userCertificate** 和 **userSMIMECertificate** 属性，以便数据可用于对邮件进行签名和加密。

## <a name="more-information"></a>更多信息

[将 S/MIME 用于邮件签名和加密](s-mime-for-message-signing-and-encryption.md)

[什么是 Azure AD Connect？](/azure/active-directory/hybrid/whatis-azure-ad-connect)