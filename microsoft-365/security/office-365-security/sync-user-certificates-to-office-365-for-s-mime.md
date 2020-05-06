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
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您将了解在 Exchange Online 中发送受 S/MIME 保护的邮件之前，如何将相应的证书发布到 Office 365。
ms.openlocfilehash: f9e0bef2f7d2125e2daeb86b3cf44ae433aae117
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035208"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="ca245-103">出于 S/MIME 目的将用户证书同步到 Office 365</span><span class="sxs-lookup"><span data-stu-id="ca245-103">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="ca245-104">在任何人可以在 Exchange Online 中发送受 S/MIME 保护的邮件之前，必须设置相应的证书。</span><span class="sxs-lookup"><span data-stu-id="ca245-104">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="ca245-105">若要通过 Exchange Online 发送加密邮件，发件人的电子邮件应用程序将使用收件人的公共证书来加密邮件。</span><span class="sxs-lookup"><span data-stu-id="ca245-105">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="ca245-106">此公用 X.509 证书必须向 Office 365 发布。</span><span class="sxs-lookup"><span data-stu-id="ca245-106">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="ca245-107">对支持 S/MIME 的证书进行同步</span><span class="sxs-lookup"><span data-stu-id="ca245-107">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="ca245-108">首先，通过颁发证书并在本地 Active Directory 域服务中发布证书来设置 S/MIME。</span><span class="sxs-lookup"><span data-stu-id="ca245-108">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="ca245-109">有关详细信息，请参阅 [Active Directory 证书服务概述](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="ca245-109">For more information, see [Active Directory Certificate Services Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="ca245-110">发布证书后，使用 Azure AD Connect 工具将用户数据从内部部署 Exchange 环境同步到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="ca245-110">After your certificates are published, use the Azure AD Connect tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="ca245-111">有关此过程的详细信息，请参阅[AZURE AD Connect sync：了解并自定义同步](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)。</span><span class="sxs-lookup"><span data-stu-id="ca245-111">For more information on this process, see [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="ca245-112">除了同步其他目录数据之外，出于 S/MIME 目的，该工具还会同步每个用户对象的**userCertificate**和**userSMIMECertificate**属性，以便数据可用于对邮件进行签名和加密。</span><span class="sxs-lookup"><span data-stu-id="ca245-112">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="ca245-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="ca245-113">More Information</span></span>

[<span data-ttu-id="ca245-114">将 S/MIME 用于邮件签名和加密</span><span class="sxs-lookup"><span data-stu-id="ca245-114">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="ca245-115">什么是 Azure AD Connect？</span><span class="sxs-lookup"><span data-stu-id="ca245-115">What is Azure AD Connect?</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
