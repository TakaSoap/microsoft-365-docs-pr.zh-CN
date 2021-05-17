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
description: 本文将了解如何在邮件中发送受 S/MIME Office 365邮件之前，将相应的证书发布到Exchange Online。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 387f9f405afd45254c6568aa92334a7ee5b4171f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203820"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="e2d83-103">出于 S/MIME 目的将用户证书同步到 Office 365</span><span class="sxs-lookup"><span data-stu-id="e2d83-103">Sync user certificates to Office 365 for S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e2d83-104">必须先设置适当的证书，然后任何人都可以在 Exchange Online 中发送受 S/MIME 保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="e2d83-104">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="e2d83-105">若要通过邮件Exchange Online，发件人的电子邮件应用程序会使用收件人的公共证书对邮件进行加密。</span><span class="sxs-lookup"><span data-stu-id="e2d83-105">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="e2d83-106">此公用 X.509 证书必须向 Office 365 发布。</span><span class="sxs-lookup"><span data-stu-id="e2d83-106">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="e2d83-107">对支持 S/MIME 的证书进行同步</span><span class="sxs-lookup"><span data-stu-id="e2d83-107">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="e2d83-108">首先，通过颁发证书并在本地 Active Directory 域服务中发布证书来设置 S/MIME。</span><span class="sxs-lookup"><span data-stu-id="e2d83-108">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="e2d83-109">有关详细信息，请参阅 [Active Directory 证书服务概述](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="e2d83-109">For more information, see [Active Directory Certificate Services Overview](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="e2d83-110">发布证书后，使用 Azure AD 连接 工具将本地部署环境中的用户数据Exchange同步到Office 365。</span><span class="sxs-lookup"><span data-stu-id="e2d83-110">After your certificates are published, use the Azure AD Connect tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="e2d83-111">有关此过程详细信息，请参阅 Azure [AD 连接同步：了解并自定义同步](/azure/active-directory/hybrid/how-to-connect-sync-whatis)。</span><span class="sxs-lookup"><span data-stu-id="e2d83-111">For more information on this process, see [Azure AD Connect sync: Understand and customize synchronization](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="e2d83-112">除了同步其他目录数据，出于 S/MIME 目的，该工具还将同步每个用户对象的  **userCertificate** 和 **userSMIMECertificate** 属性，以便数据可用于对邮件进行签名和加密。</span><span class="sxs-lookup"><span data-stu-id="e2d83-112">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="e2d83-113">更多信息</span><span class="sxs-lookup"><span data-stu-id="e2d83-113">More Information</span></span>

[<span data-ttu-id="e2d83-114">将 S/MIME 用于邮件签名和加密</span><span class="sxs-lookup"><span data-stu-id="e2d83-114">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="e2d83-115">什么是 Azure AD Connect？</span><span class="sxs-lookup"><span data-stu-id="e2d83-115">What is Azure AD Connect?</span></span>](/azure/active-directory/hybrid/whatis-azure-ad-connect)