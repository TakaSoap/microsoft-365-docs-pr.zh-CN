---
title: Exchange Online 如何进行电子邮件保密
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: 除了为 Microsoft 365 提供安全、隐私和合规性信息的 Office 365 信任中心外，你可能还希望了解 Microsoft 如何帮助保护存储在其数据中心内机密。 我们使用名为分布式密钥管理器技术 (DKM) 。
ms.openlocfilehash: 2f6e51b7fe9cd75cbd265c3135050a08130f34d8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906958"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a><span data-ttu-id="baa5b-104">Exchange Online 如何进行电子邮件保密</span><span class="sxs-lookup"><span data-stu-id="baa5b-104">How Exchange Online secures your email secrets</span></span>

<span data-ttu-id="baa5b-105">本文介绍了 Microsoft 如何保护其数据中心中的电子邮件密码。</span><span class="sxs-lookup"><span data-stu-id="baa5b-105">This article describes how Microsoft secures your email secrets in its datacenters.</span></span>
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a><span data-ttu-id="baa5b-106">我们如何保护你提供的机密信息？</span><span class="sxs-lookup"><span data-stu-id="baa5b-106">How do we secure secret information provided by you?</span></span>

<span data-ttu-id="baa5b-107">除了 [为 Office 365](./get-started-with-service-trust-portal.md)提供安全、隐私和合规性信息的 Office 365 信任中心外，你可能还想知道 Microsoft 如何帮助保护你在数据中心中提供机密。</span><span class="sxs-lookup"><span data-stu-id="baa5b-107">In addition to the Office 365 Trust Center which provides [Security, Privacy and Compliance Information for Office 365](./get-started-with-service-trust-portal.md), you might want to know how Microsoft helps protects secrets you provide in its datacenters.</span></span> <span data-ttu-id="baa5b-108">我们使用名为分布式密钥管理器技术 (DKM) 。</span><span class="sxs-lookup"><span data-stu-id="baa5b-108">We use a technology called Distributed Key Manager (DKM).</span></span>
  
<span data-ttu-id="baa5b-109">[分布式密钥](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) 是一项客户端功能，它使用一组密钥加密和解密信息。</span><span class="sxs-lookup"><span data-stu-id="baa5b-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) is a client-side functionality that uses a set of secret keys to encrypt and decrypt information.</span></span> <span data-ttu-id="baa5b-110">只有 Active Directory 域服务中特定安全组的成员可以访问这些密钥，以便解密由 DKM 加密的数据。</span><span class="sxs-lookup"><span data-stu-id="baa5b-110">Only members of a specific security group in Active Directory Domain Services can access those keys in order to decrypt the data that is encrypted by DKM.</span></span> <span data-ttu-id="baa5b-111">在 Exchange Online 中，只有运行 Exchange 进程的某些服务帐户是该安全组的一部分。</span><span class="sxs-lookup"><span data-stu-id="baa5b-111">In Exchange Online, only certain service accounts under which the Exchange processes run are part of that security group.</span></span> <span data-ttu-id="baa5b-112">作为数据中心中标准操作过程一部分，不会向人员提供属于此安全组的凭据，因此，人员无法访问可解密这些密钥的密钥。</span><span class="sxs-lookup"><span data-stu-id="baa5b-112">As part of standard operating procedure in the datacenter, no human is given credentials that are part of this security group and therefore no human has access to the keys that can decrypt these secrets.</span></span>
  
<span data-ttu-id="baa5b-113">为了进行调试、故障排除或审核，数据中心管理员必须请求提升的访问权限，以获得属于安全组的临时凭据。</span><span class="sxs-lookup"><span data-stu-id="baa5b-113">For debugging, troubleshooting, or auditing purposes, a datacenter administrator must request elevated access to gain temporary credentials that are part of the security group.</span></span> <span data-ttu-id="baa5b-114">此过程需要多个级别的法律审批。</span><span class="sxs-lookup"><span data-stu-id="baa5b-114">This process requires multiple levels of legal approval.</span></span> <span data-ttu-id="baa5b-115">如果授予访问权限，将记录并审核所有活动。</span><span class="sxs-lookup"><span data-stu-id="baa5b-115">If access is granted, all activity is logged and audited.</span></span> <span data-ttu-id="baa5b-116">此外，仅在一组时间间隔内授予访问权限，在此时间间隔后，该时间间隔将自动过期。</span><span class="sxs-lookup"><span data-stu-id="baa5b-116">In addition access is only granted for a set interval of time after which it automatically expires.</span></span>
  
<span data-ttu-id="baa5b-117">为了提供额外的保护，DKM 技术包括自动密钥滚动和存档。</span><span class="sxs-lookup"><span data-stu-id="baa5b-117">For extra protection, DKM technology includes automated key rollover and archiving.</span></span> <span data-ttu-id="baa5b-118">这还可确保您可以继续访问旧内容，而无需无限期地依赖同一密钥。</span><span class="sxs-lookup"><span data-stu-id="baa5b-118">This also ensures that you can continue to access your older content without having to rely on the same key indefinitely.</span></span>
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a><span data-ttu-id="baa5b-119">Exchange Online 在何处使用 DKM？</span><span class="sxs-lookup"><span data-stu-id="baa5b-119">Where does Exchange Online make use of DKM?</span></span>

<span data-ttu-id="baa5b-120">Microsoft 使用 [分布式密钥管理器](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) 加密 Exchange Online 数据中心中的密钥。</span><span class="sxs-lookup"><span data-stu-id="baa5b-120">Microsoft uses [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) to encrypt your secrets in Exchange Online datacenters.</span></span> <span data-ttu-id="baa5b-121">例如：</span><span class="sxs-lookup"><span data-stu-id="baa5b-121">For example:</span></span>
  
- <span data-ttu-id="baa5b-122">已连接帐户的电子邮件帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="baa5b-122">Email account credentials for connected accounts.</span></span> <span data-ttu-id="baa5b-123">连接帐户是 Hotmail、Gmail 和 Yahoo！</span><span class="sxs-lookup"><span data-stu-id="baa5b-123">Connected accounts are third-party accounts such as Hotmail, Gmail, and Yahoo!</span></span> <span data-ttu-id="baa5b-124">邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="baa5b-124">mail accounts.</span></span>

- <span data-ttu-id="baa5b-125">客户密钥。</span><span class="sxs-lookup"><span data-stu-id="baa5b-125">Customer key.</span></span> <span data-ttu-id="baa5b-126">如果你将服务加密与客户密钥一同 [使用](customer-key-overview.md)，你将使用 [Azure 密钥](/azure/key-vault/key-vault-whatis) 保管库来保护你的密钥。</span><span class="sxs-lookup"><span data-stu-id="baa5b-126">If you are using [Service encryption with Customer Key](customer-key-overview.md), you'll use [Azure Key Vault](/azure/key-vault/key-vault-whatis) to safeguard your secrets.</span></span>

## <a name="related-topics"></a><span data-ttu-id="baa5b-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="baa5b-127">Related topics</span></span>

[<span data-ttu-id="baa5b-128">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="baa5b-128">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="baa5b-129">有关加密的技术参考详情</span><span class="sxs-lookup"><span data-stu-id="baa5b-129">Technical reference details about encryption</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="baa5b-130">安全与合规中心 &amp; 中的服务保证</span><span class="sxs-lookup"><span data-stu-id="baa5b-130">Service assurance in the Security &amp; Compliance Center</span></span>](./service-assurance.md)
