---
title: S/MIME for encryption in Exchange Online - Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: 管理员可以了解如何在 Exchange Online (安全/多用途 Internet 邮件) S/MIME 加密电子邮件并对其进行数字签名。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d189bf7f52dd6f9fb11dc360c17d5fe15729c9fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908778"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a><span data-ttu-id="c35c1-103">Exchange Online 中邮件签名和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="c35c1-103">S/MIME for message signing and encryption in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c35c1-104">S/MIME (安全/多用途 Internet 邮件扩展) 是一种广泛使用的方法 (更确切地说是一种协议) ，用于发送数字签名和加密邮件。</span><span class="sxs-lookup"><span data-stu-id="c35c1-104">S/MIME (Secure/Multipurpose Internet Mail Extensions) is a widely accepted method (or more precisely, a protocol) for sending digitally signed and encrypted messages.</span></span> <span data-ttu-id="c35c1-105">S/MIME 允许你加密电子邮件，并对它们进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="c35c1-105">S/MIME allows you to encrypt emails and digitally sign them.</span></span> <span data-ttu-id="c35c1-106">当您将 S/MIME 与电子邮件一同使用时，它可以帮助接收该邮件的人确定其收件箱中显示的邮件与发件人一起启动的确切邮件。</span><span class="sxs-lookup"><span data-stu-id="c35c1-106">When you use S/MIME with an email message, it helps the people who receive that message to be certain that what they see in their inbox is the exact message that started with the sender.</span></span> <span data-ttu-id="c35c1-107">它还可以帮助接收邮件的人确保邮件来自特定发件人，而不是冒充发件人的人。</span><span class="sxs-lookup"><span data-stu-id="c35c1-107">It will also help people who receive messages to be certain that the message came from the specific sender and not from someone pretending to be the sender.</span></span> <span data-ttu-id="c35c1-108">为此，S/MIME 提供了加密安全服务，例如身份验证、邮件完整性和防发送方抵赖（使用数字签名）。</span><span class="sxs-lookup"><span data-stu-id="c35c1-108">To do this, S/MIME provides for cryptographic security services such as authentication, message integrity, and non-repudiation of origin (using digital signatures).</span></span> <span data-ttu-id="c35c1-109">它还有助于增强使用加密技术 (电子邮件) 隐私和数据安全性。</span><span class="sxs-lookup"><span data-stu-id="c35c1-109">It also helps enhance privacy and data security (using encryption) for electronic messaging.</span></span> <span data-ttu-id="c35c1-110">有关电子邮件上下文中 S/MIME 的历史记录和体系结构的更多完整背景，请参阅[了解 S/MIMEE](/previous-versions/tn-archive/aa995740(v=exchg.65))。</span><span class="sxs-lookup"><span data-stu-id="c35c1-110">For a more complete background about the history and architecture of S/MIME in the context of email, see [Understanding S/MIME](/previous-versions/tn-archive/aa995740(v=exchg.65)).</span></span>

<span data-ttu-id="c35c1-111">作为 Exchange Online 管理员，您可以为组织中邮箱启用基于 S/MIME 的安全性。</span><span class="sxs-lookup"><span data-stu-id="c35c1-111">As an Exchange Online admin, you can enable S/MIME-based security for the mailboxes in your organization.</span></span> <span data-ttu-id="c35c1-112">使用此处链接的主题中的指南以及 Exchange Online PowerShell 设置 S/MIME。</span><span class="sxs-lookup"><span data-stu-id="c35c1-112">Use the guidance in the topics linked here along with Exchange Online PowerShell to set up S/MIME.</span></span> <span data-ttu-id="c35c1-113">若要在受支持的电子邮件客户端中使用 S/MIME，组织中用户必须具有颁发用于签名和加密目的的证书，以及发布到本地 Active Directory 域服务 (AD DS) 的数据。</span><span class="sxs-lookup"><span data-stu-id="c35c1-113">To use S/MIME in supported email clients, the users in your organization must have certificates issued for signing and encryption purposes and data published to your on-premises Active Directory Domain Service (AD DS).</span></span> <span data-ttu-id="c35c1-114">AD DS 必须位于你控制的物理位置的计算机上，而不是位于 Internet 上的远程设施或基于云的服务上。</span><span class="sxs-lookup"><span data-stu-id="c35c1-114">Your AD DS must be located on computers at a physical location that you control and not at a remote facility or cloud-based service somewhere on the internet.</span></span> <span data-ttu-id="c35c1-115">有关 AD DS 详细信息，请参阅 [Active Directory 域服务概述](/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)。</span><span class="sxs-lookup"><span data-stu-id="c35c1-115">For more information about AD DS, see [Active Directory Domain Services Overview](/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview).</span></span>

## <a name="supported-scenarios-and-technical-considerations"></a><span data-ttu-id="c35c1-116">支持的方案和技术注意事项</span><span class="sxs-lookup"><span data-stu-id="c35c1-116">Supported scenarios and technical considerations</span></span>

<span data-ttu-id="c35c1-117">可以将 S/MIME 设置为用于以下任一终结点：</span><span class="sxs-lookup"><span data-stu-id="c35c1-117">You can set up S/MIME to work with any of the following end points:</span></span>

- <span data-ttu-id="c35c1-118">Outlook 2010 或更高版本</span><span class="sxs-lookup"><span data-stu-id="c35c1-118">Outlook 2010 or later</span></span>
- <span data-ttu-id="c35c1-119">Web 上的 Outlook（以前称为 Outlook Web App）</span><span class="sxs-lookup"><span data-stu-id="c35c1-119">Outlook on the web (formerly known as Outlook Web App)</span></span>
- <span data-ttu-id="c35c1-120">Exchange ActiveSync (EAS)</span><span class="sxs-lookup"><span data-stu-id="c35c1-120">Exchange ActiveSync (EAS)</span></span>

<span data-ttu-id="c35c1-121">使用上述每个结束点设置 S/MIME 的步骤略有不同。</span><span class="sxs-lookup"><span data-stu-id="c35c1-121">The steps that you follow to set up S/MIME with each of these end points is slightly different.</span></span> <span data-ttu-id="c35c1-122">通常，您需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c35c1-122">Generally, you will need to do the following steps:</span></span>

1. <span data-ttu-id="c35c1-123">安装基于 Windows 的证书颁发 (CA) 并设置公钥基础结构以颁发 S/MIME 证书。</span><span class="sxs-lookup"><span data-stu-id="c35c1-123">Install a Windows-based Certification Authority (CA) and set up a public key infrastructure to issue S/MIME certificates.</span></span> <span data-ttu-id="c35c1-124">还支持第三方证书提供商颁发的证书。</span><span class="sxs-lookup"><span data-stu-id="c35c1-124">Certificates issued by third-party certificate providers are also supported.</span></span> <span data-ttu-id="c35c1-125">有关详细信息，请参阅 [Active Directory 证书服务概述](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="c35c1-125">For details, see [Active Directory Certificate Services Overview](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11)).</span></span>

   <span data-ttu-id="c35c1-126">**注意**：</span><span class="sxs-lookup"><span data-stu-id="c35c1-126">**Notes**:</span></span>

   - <span data-ttu-id="c35c1-127">由第三方 CA 颁发的证书具有自动受所有客户端和设备信任的优势。</span><span class="sxs-lookup"><span data-stu-id="c35c1-127">Certificates issued by a third-party CA have the advantage of being automatically trusted by all clients and devices.</span></span> <span data-ttu-id="c35c1-128">客户端和设备不会自动信任由内部私有 CA 颁发的证书，并且并非所有设备 (例如，可以将电话) 配置为信任专用证书。</span><span class="sxs-lookup"><span data-stu-id="c35c1-128">Certificates that are issued by an internal, private CA aren't automatically trusted by clients and devices, and not all devices (for example, phones) can be configured to trust private certificates.</span></span>

   - <span data-ttu-id="c35c1-129">请考虑使用中间证书而不是根证书向用户颁发证书。</span><span class="sxs-lookup"><span data-stu-id="c35c1-129">Consider using an intermediate certificate instead of the root certificate to issue certificates to users.</span></span> <span data-ttu-id="c35c1-130">这样，如果需要撤销和重新颁发证书，根证书将保持不变。</span><span class="sxs-lookup"><span data-stu-id="c35c1-130">That way, if you ever need to revoke and reissue certificates, the root certificate is still intact.</span></span>

2. <span data-ttu-id="c35c1-131">在 **UserSMIMECertificate** 和/或 **UserCertificate** 属性中的本地 AD DS 帐户中发布用户证书。</span><span class="sxs-lookup"><span data-stu-id="c35c1-131">Publish the user certificate in an on-premises AD DS account in the **UserSMIMECertificate** and/or **UserCertificate** attributes.</span></span>

3. <span data-ttu-id="c35c1-132">对于 Exchange Online 组织，使用适当版本的 Azure AD Connect 将用户证书从 AD DS 同步到 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="c35c1-132">For Exchange Online organizations, synchronize the user certificates from AD DS to Azure Active Directory by using an appropriate version of Azure AD Connect.</span></span> <span data-ttu-id="c35c1-133">这些证书随后会从 Azure Active Directory 同步到 Exchange Online 目录，并且将在加密发送给收件人的邮件时使用。</span><span class="sxs-lookup"><span data-stu-id="c35c1-133">These certificates will then get synchronized from Azure Active Directory to Exchange Online directory and will be used when encrypting a message to a recipient.</span></span>

4. <span data-ttu-id="c35c1-p108">设置虚拟证书集合以验证 S/MIME。此信息供 Web 上的 Outlook 用于验证电子邮件的签名并确保它是由可信证书签名的。</span><span class="sxs-lookup"><span data-stu-id="c35c1-p108">Set up a virtual certificate collection in order to validate S/MIME. This information is used by Outlook on the web when validating the signature of an email and ensuring that it was signed by a trusted certificate.</span></span>

5. <span data-ttu-id="c35c1-136">将 Outlook 或 EAS 终结点设置为使用 S/MIME。</span><span class="sxs-lookup"><span data-stu-id="c35c1-136">Set up the Outlook or EAS end point to use S/MIME.</span></span>

> [!NOTE]
> <span data-ttu-id="c35c1-137">你不能在 Mac、iOS、Android 或其他非 Windows 设备上的 Outlook 网页版中安装 S/MIME 控件。</span><span class="sxs-lookup"><span data-stu-id="c35c1-137">You can't install S/MIME control in Outlook on the web on Mac, iOS, Android, or other non-Windows devices.</span></span> <span data-ttu-id="c35c1-138">有关详细信息，请参阅使用 [Outlook 网页中的 S/MIME 加密邮件](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480)。</span><span class="sxs-lookup"><span data-stu-id="c35c1-138">For more information, see [Encrypt messages by using S/MIME in Outlook on the web](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480).</span></span>

## <a name="set-up-smime-with-outlook-on-the-web"></a><span data-ttu-id="c35c1-139">设置 Web 上的 Outlook 的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="c35c1-139">Set up S/MIME with Outlook on the web</span></span>

<span data-ttu-id="c35c1-140">使用 Outlook 网页版为 Exchange Online 设置 S/MIME 涉及以下关键步骤：</span><span class="sxs-lookup"><span data-stu-id="c35c1-140">Setting up S/MIME for Exchange Online with Outlook on the web involves the following key steps:</span></span>

1. [<span data-ttu-id="c35c1-141">配置 Outlook 网页版的 S/MIME 设置</span><span class="sxs-lookup"><span data-stu-id="c35c1-141">Configure S/MIME settings for Outlook on the web</span></span>](configure-s-mime-settings-for-outlook-web-app.md)
2. [<span data-ttu-id="c35c1-142">设置虚拟证书集合以验证 S/MIME</span><span class="sxs-lookup"><span data-stu-id="c35c1-142">Set up virtual certificate collection to validate S/MIME</span></span>](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [<span data-ttu-id="c35c1-143">出于 S/MIME 目的将用户证书同步到 Office 365</span><span class="sxs-lookup"><span data-stu-id="c35c1-143">Sync user certificates to Office 365 for S/MIME</span></span>](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a><span data-ttu-id="c35c1-144">相关邮件加密技术</span><span class="sxs-lookup"><span data-stu-id="c35c1-144">Related message encryption technologies</span></span>

<span data-ttu-id="c35c1-145">随着邮件安全变得更加重要，管理员需要了解安全邮件的原则和概念。</span><span class="sxs-lookup"><span data-stu-id="c35c1-145">As message security becomes more important, admins need to understand the principles and concepts of secure messaging.</span></span> <span data-ttu-id="c35c1-146">这种了解尤为重要，因为可用的保护相关技术 (S/MIME) 也不断增加。</span><span class="sxs-lookup"><span data-stu-id="c35c1-146">This understanding is especially important because of the growing variety of protection-related technologies (including S/MIME) that are available.</span></span> <span data-ttu-id="c35c1-147">若要了解有关 S/MIME 及其在电子邮件上下文中的工作方式的更多信息，请参阅[了解 S/MIME。](/previous-versions/tn-archive/aa995740(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="c35c1-147">To understand more about S/MIME and how it works in context of email, see [Understanding S/MIME](/previous-versions/tn-archive/aa995740(v=exchg.65)).</span></span> <span data-ttu-id="c35c1-148">各种加密技术协同工作，为处于静态和传输状态的邮件提供保护。</span><span class="sxs-lookup"><span data-stu-id="c35c1-148">A variety of encryption technologies work together to provide protection for messages at rest and in-transit.</span></span> <span data-ttu-id="c35c1-149">S/MIME 可以同时与以下技术一起工作，但不依赖于这些技术：</span><span class="sxs-lookup"><span data-stu-id="c35c1-149">S/MIME can work simultaneously with the following technologies but is not dependent on them:</span></span>

- <span data-ttu-id="c35c1-150">**传输层 (TLS**) 加密电子邮件服务器之间的隧道或路由，以帮助防止窃听和窃听。</span><span class="sxs-lookup"><span data-stu-id="c35c1-150">**Transport Layer Security (TLS)** encrypts the tunnel or the route between email servers in order to help prevent snooping and eavesdropping.</span></span>

- <span data-ttu-id="c35c1-151">**安全套接字层 (SSL)** 加密电子邮件客户端和 Microsoft 365 服务器之间的连接。</span><span class="sxs-lookup"><span data-stu-id="c35c1-151">**Secure Sockets Layer (SSL)** encrypts the connection between email clients and Microsoft 365 servers.</span></span>

- <span data-ttu-id="c35c1-152">**BitLocker** 对数据中心中硬盘驱动器上的数据进行加密，以便如果有人获得未经授权的访问，他们无法读取数据。</span><span class="sxs-lookup"><span data-stu-id="c35c1-152">**BitLocker** encrypts the data on a hard drive in a datacenter so that if someone gets unauthorized access, they can't read it.</span></span>

### <a name="smime-compared-with-office-365-message-encryption"></a><span data-ttu-id="c35c1-153">S/MIME 与 Office 365 邮件加密比较</span><span class="sxs-lookup"><span data-stu-id="c35c1-153">S/MIME compared with Office 365 Message Encryption</span></span>

<span data-ttu-id="c35c1-154">S/MIME 需要证书和发布基础结构，通常用于企业到企业和企业到消费者的情况。</span><span class="sxs-lookup"><span data-stu-id="c35c1-154">S/MIME requires a certificate and publishing infrastructure that is often used in business-to-business and business-to-consumer situations.</span></span> <span data-ttu-id="c35c1-155">用户控制 S/MIME 中的加密密钥，并且可以选择是否为他们发送的每封邮件使用密钥。</span><span class="sxs-lookup"><span data-stu-id="c35c1-155">The user controls the cryptographic keys in S/MIME and can choose whether to use them for each message they send.</span></span> <span data-ttu-id="c35c1-156">Outlook 等电子邮件程序搜索可信任根证书颁发机构位置，以执行数字签名和签名验证。</span><span class="sxs-lookup"><span data-stu-id="c35c1-156">Email programs such as Outlook search a trusted root certificate authority location to perform digital signing and verification of the signature.</span></span> <span data-ttu-id="c35c1-157">Office 365 邮件加密是一种基于策略的加密服务，管理员（而不是单个用户）可配置该服务，以加密发送到组织内部或外部的任何人员的邮件。</span><span class="sxs-lookup"><span data-stu-id="c35c1-157">Office 365 Message Encryption is a policy-based encryption service that can be configured by an administrator, and not an individual user, to encrypt mail sent to anyone inside or outside of the organization.</span></span> <span data-ttu-id="c35c1-158">它是基于 Azure 权限管理 (RMS) 构建的联机服务，不依赖于公钥基础结构。</span><span class="sxs-lookup"><span data-stu-id="c35c1-158">It's an online service that's built on Azure Rights Management (RMS) and does not rely on a public key infrastructure.</span></span> <span data-ttu-id="c35c1-159">Office 365 邮件加密还提供其他功能，例如使用组织品牌自定义邮件的功能。</span><span class="sxs-lookup"><span data-stu-id="c35c1-159">Office 365 Message Encryption also provides additional capabilities, such as the capability to customize the mail with organization's brand.</span></span> <span data-ttu-id="c35c1-160">有关 Office 365 邮件加密详细信息，请参阅 [Office 365 中的加密](../../compliance/encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="c35c1-160">For more information about Office 365 Message Encryption, see [Encryption in Office 365](../../compliance/encryption.md).</span></span>

## <a name="more-information"></a><span data-ttu-id="c35c1-161">更多信息</span><span class="sxs-lookup"><span data-stu-id="c35c1-161">More information</span></span>

[<span data-ttu-id="c35c1-162">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="c35c1-162">Outlook on the web</span></span>](/exchange/exchange-admin-center)

<span data-ttu-id="c35c1-163">[Secure Mail (2000) ](/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="c35c1-163">[Secure Mail (2000)](/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))</span></span>