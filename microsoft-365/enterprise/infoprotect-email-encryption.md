---
title: 步骤 6：配置电子邮件加密
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: 了解并配置 Office 365 的特权访问管理。
ms.openlocfilehash: 252a5f76197deb1034d200553308a281ef079957
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600919"
---
# <a name="step-6-configure-email-encryption"></a><span data-ttu-id="519df-103">步骤 6：配置电子邮件加密</span><span class="sxs-lookup"><span data-stu-id="519df-103">Step 6: Configure email encryption</span></span>

<span data-ttu-id="519df-104">*此步骤可选，它适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="519df-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![第 6 阶段：信息保护](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="519df-106">Microsoft 365 中有三种类型的电子邮件加密。</span><span class="sxs-lookup"><span data-stu-id="519df-106">There are three types of email encryption in Microsoft 365.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="519df-107">Office 邮件加密 (OME)</span><span class="sxs-lookup"><span data-stu-id="519df-107">Office Message Encryption (OME)</span></span> | <span data-ttu-id="519df-108">在组织外部发送的 Exchange Online 电子邮件的加密。</span><span class="sxs-lookup"><span data-stu-id="519df-108">Encryption for Exchange Online email sent outside your organization.</span></span> |
| <span data-ttu-id="519df-109">信息权限管理 (IRM)</span><span class="sxs-lookup"><span data-stu-id="519df-109">Information Rights Management (IRM)</span></span> | <span data-ttu-id="519df-110">随电子邮件一起携带的加密和权限。</span><span class="sxs-lookup"><span data-stu-id="519df-110">Encryption and permissions that travel with the email.</span></span> |
| <span data-ttu-id="519df-111">安全/多用途 Internet 邮件扩展 (S/MIME)</span><span class="sxs-lookup"><span data-stu-id="519df-111">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span> | <span data-ttu-id="519df-112">使用加密和数字签名的电子邮件保护。</span><span class="sxs-lookup"><span data-stu-id="519df-112">Email protection with encryption and digital signatures.</span></span> |
|||

## <a name="office-365-message-encryption"></a><span data-ttu-id="519df-113">Office 365 邮件加密</span><span class="sxs-lookup"><span data-stu-id="519df-113">Office 365 Message Encryption</span></span>

<span data-ttu-id="519df-114">通过 OME，您的组织可以在组织内部和外部的人员之间发送和接收加密的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="519df-114">With OME, your organization can send and receive encrypted email messages between people inside and outside your organization.</span></span> <span data-ttu-id="519df-115">OME 适用于 Outlook.com、Yahoo！、Gmail 和其他电子邮件服务。</span><span class="sxs-lookup"><span data-stu-id="519df-115">OME works with Outlook.com, Yahoo!, Gmail, and other email services.</span></span> <span data-ttu-id="519df-116">电子邮件加密有助于确保只有预期的收件人可以查看邮件。</span><span class="sxs-lookup"><span data-stu-id="519df-116">Email message encryption helps ensure that only intended recipients can view the message.</span></span>

![电子邮件的 OME 加密](./media/infoprotect-email-encryption/ome-encryption.png)

<span data-ttu-id="519df-118">您设置用于定义加密条件的传输规则。</span><span class="sxs-lookup"><span data-stu-id="519df-118">You set up transport rules that define the conditions for encryption.</span></span> <span data-ttu-id="519df-119">当用户发送的邮件与规则匹配时，则自动应用加密。</span><span class="sxs-lookup"><span data-stu-id="519df-119">When a user sends a message that matches a rule, encryption is applied automatically.</span></span>

<span data-ttu-id="519df-120">若要查看加密邮件，收件人可以获取一次性密码，使用 Microsoft 帐户登录，或使用与 Microsoft 365 关联的工作或学校帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="519df-120">To view encrypted messages, recipients can either get a one-time passcode, sign in with a Microsoft account, or sign in with a work or school account associated with Microsoft 365.</span></span> <span data-ttu-id="519df-121">此外，收件人也可发送加密回复。</span><span class="sxs-lookup"><span data-stu-id="519df-121">Recipients can also send encrypted replies.</span></span> <span data-ttu-id="519df-122">他们不需要自己的 Microsoft 365 订阅即可查看加密的邮件或发送加密的答复。</span><span class="sxs-lookup"><span data-stu-id="519df-122">They don't need their own Microsoft 365 subscription to view encrypted messages or send encrypted replies.</span></span>

<span data-ttu-id="519df-123">有关详细信息，请参阅 [Office 365 邮件加密](https://docs.microsoft.com/Office365/SecurityCompliance/ome)。</span><span class="sxs-lookup"><span data-stu-id="519df-123">For more information, see [Office 365 Message Encryption](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span></span>

## <a name="irm"></a><span data-ttu-id="519df-124">IRM</span><span class="sxs-lookup"><span data-stu-id="519df-124">IRM</span></span>

<span data-ttu-id="519df-125">Microsoft 365 中的 IRM 可帮助您通过其他加密保护信息，并通过应用智能策略来指定谁有权访问他们可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="519df-125">IRM in Microsoft 365 helps you secure your information with additional encryption and by applying an intelligent policy that specifies who has access what they can do.</span></span> <span data-ttu-id="519df-126">对于电子邮件，您可以使用 IRM 进行加密并应用使用限制。</span><span class="sxs-lookup"><span data-stu-id="519df-126">For email messages, you can use IRM for encryption and to apply usage restrictions.</span></span> <span data-ttu-id="519df-127">例如，可以指定某些收件人具有管理电子邮件的所有功能，并且某些收件人无法打印或转发电子邮件。</span><span class="sxs-lookup"><span data-stu-id="519df-127">For example, you can specify that some recipients have all abilities to manage the email and some do not have the ability to print or forward the email.</span></span> 

<span data-ttu-id="519df-128">IRM 策略在 Microsoft 365 中配置，并可应用于 SharePoint Online 和电子邮件中的文档。</span><span class="sxs-lookup"><span data-stu-id="519df-128">IRM policies are configured within Microsoft 365 and can apply to documents in SharePoint Online and email messages.</span></span> <span data-ttu-id="519df-129">受 IRM 保护的电子邮件包含应用的应用的策略设置并与之一起移动。</span><span class="sxs-lookup"><span data-stu-id="519df-129">An IRM-protected email includes the applied policy settings applied and travel with it.</span></span> 

![电子邮件的 IRM 保护](./media/infoprotect-email-encryption/irm-protection.png)

<span data-ttu-id="519df-131">当收件人使用包含的策略打开电子邮件时，策略设置将用于解密邮件，并确定收件人可对邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="519df-131">When the recipient opens the email with the included policy, the policy settings are used to decrypt the message and determine what the recipient can do with it.</span></span> 

<span data-ttu-id="519df-132">有关详细信息，请参阅 [Exchange Online 中的信息权限管理]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online)。</span><span class="sxs-lookup"><span data-stu-id="519df-132">For more information, see [Information Rights Management in Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span></span>

## <a name="smime"></a><span data-ttu-id="519df-133">S/MIME</span><span class="sxs-lookup"><span data-stu-id="519df-133">S/MIME</span></span>

<span data-ttu-id="519df-134">S/MIME 是基于数字证书的基于电子邮件的保护解决方案，使您可以对邮件进行加密和数字签名。</span><span class="sxs-lookup"><span data-stu-id="519df-134">S/MIME is a digital certificate-based email-based protection solution that allows you to both encrypt and digitally sign a message.</span></span> <span data-ttu-id="519df-135">邮件加密有助于确保只有预期收件人可以打开并阅读该邮件。</span><span class="sxs-lookup"><span data-stu-id="519df-135">The message encryption helps ensure that only the intended recipient can open and read the message.</span></span> <span data-ttu-id="519df-136">数字签名可帮助收件人验证发件人的身份，并确定只有发件人可以发送它。</span><span class="sxs-lookup"><span data-stu-id="519df-136">A digital signature helps the recipient validate the identity of the sender and determine that only the sender could have sent it.</span></span>

![电子邮件的 S/MIME 保护](./media/infoprotect-email-encryption/smime-protection.png)

<span data-ttu-id="519df-138">S/MIME 可用于向 Microsoft 365 订阅中的其他邮箱或向外部用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="519df-138">S/MIME can be used for email to other mailboxes in your Microsoft 365 subscription or to external users.</span></span>
<span data-ttu-id="519df-139">通过使用包含用于加密或解密邮件的公钥和私钥的数字证书以及创建和验证数字签名，可以进行邮件加密和数字签名。</span><span class="sxs-lookup"><span data-stu-id="519df-139">Both message encryption and digital signatures are made possible through the use of digital certificates that contain the public and private keys for encrypting or decrypting messages and creating and verifying digital signatures.</span></span>
<span data-ttu-id="519df-140">若要使用 S/MIME，您必须具有每个收件人的公钥。</span><span class="sxs-lookup"><span data-stu-id="519df-140">To use S/MIME, you must have the public keys for each recipient.</span></span> <span data-ttu-id="519df-141">收件人维护自己的私钥，它们必须保持安全。</span><span class="sxs-lookup"><span data-stu-id="519df-141">Recipients maintain their own private keys, which must remain secure.</span></span> <span data-ttu-id="519df-142">如果私钥受到威胁，您需要获取新的数字证书，并将公钥重新分发给所有潜在的发件人。</span><span class="sxs-lookup"><span data-stu-id="519df-142">If your private key is compromised, you need to get a new digital certificate and redistribute public keys to all potential senders.</span></span>

<span data-ttu-id="519df-143">有关详细信息，请参阅[邮件签名和加密的 S/MIME](https://docs.microsoft.com/Exchange/policy-and-compliance/smime)。</span><span class="sxs-lookup"><span data-stu-id="519df-143">For more information, see [S/MIME for message signing and encryption](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).</span></span>


<span data-ttu-id="519df-144">作为临时检查点，请查看对应于此步骤的[退出条件](infoprotect-exit-criteria.md#crit-infoprotect-step6)。</span><span class="sxs-lookup"><span data-stu-id="519df-144">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="519df-145">后续步骤</span><span class="sxs-lookup"><span data-stu-id="519df-145">Next step</span></span>

|||
|:-------|:-----|
|![第 7 步](./media/stepnumbers/Step7.png)|[<span data-ttu-id="519df-147">配置 Office 365 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="519df-147">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
