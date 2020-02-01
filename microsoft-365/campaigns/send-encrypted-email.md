---
title: 发送加密电子邮件
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: 了解如何使用 Outlook 发送加密电子邮件。
ms.openlocfilehash: 1a450a9891d47a136798432fdb919349fb82e097
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594733"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="f5076-103">加密或标记敏感电子邮件</span><span class="sxs-lookup"><span data-stu-id="f5076-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="f5076-104">您的数据和市场活动信息非常重要且通常是保密信息。</span><span class="sxs-lookup"><span data-stu-id="f5076-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="f5076-105">使用加密和敏感度标签帮助保护这些敏感信息，以便您和您的电子邮件收件人按照所需的敏感度对待信息。</span><span class="sxs-lookup"><span data-stu-id="f5076-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>


## <a name="best-practices"></a><span data-ttu-id="f5076-106">最佳做法</span><span class="sxs-lookup"><span data-stu-id="f5076-106">Best practices</span></span>

<span data-ttu-id="f5076-107">在发送包含机密或敏感信息的电子邮件之前，请考虑启用：</span><span class="sxs-lookup"><span data-stu-id="f5076-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="f5076-108">**加密：** 您可以加密您的电子邮件以保护电子邮件中的信息的隐私。</span><span class="sxs-lookup"><span data-stu-id="f5076-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="f5076-109">加密电子邮件时，会将其从可读纯文本转换为已编码的 cypher 文本。</span><span class="sxs-lookup"><span data-stu-id="f5076-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="f5076-110">只有具有与用于加密邮件的公钥相匹配的私钥的收件人才能解密邮件以进行读取。</span><span class="sxs-lookup"><span data-stu-id="f5076-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="f5076-111">但是，如果没有对应私钥的任何收件人，则会看到无法破译的文本。</span><span class="sxs-lookup"><span data-stu-id="f5076-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="f5076-112">您的管理员可以定义规则以自动对满足特定条件的邮件进行加密。</span><span class="sxs-lookup"><span data-stu-id="f5076-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="f5076-113">例如，您的管理员可以创建一个规则来加密在组织外部发送的所有邮件或提及特定字词或短语的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="f5076-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="f5076-114">将自动应用任何加密规则。</span><span class="sxs-lookup"><span data-stu-id="f5076-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="f5076-115">**敏感度标签：** 你的市场活动还可以设置可应用于文件和电子邮件的敏感度标签，以使其符合你的市场活动的信息保护策略。</span><span class="sxs-lookup"><span data-stu-id="f5076-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="f5076-116">在设置标签时，标签会随电子邮件一起保留，即使发送时也是如此，例如，通过在邮件中显示为标头。</span><span class="sxs-lookup"><span data-stu-id="f5076-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![包含标签和加密标注的电子邮件的关系图](media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a><span data-ttu-id="f5076-118">设置</span><span class="sxs-lookup"><span data-stu-id="f5076-118">Set it up</span></span>

<span data-ttu-id="f5076-119">如果要对不符合预定义规则的邮件进行加密，或管理员未设置任何规则，则可以在发送邮件之前应用各种不同的加密规则。</span><span class="sxs-lookup"><span data-stu-id="f5076-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="f5076-120">若要从 Outlook 2013 或2016或 Outlook 2016 for Mac 发送加密邮件，请选择 "选项" " **> 权限**"，然后选择所需的保护选项。</span><span class="sxs-lookup"><span data-stu-id="f5076-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="f5076-121">您还可以通过在 Outlook 网页网站中选择 "**保护**" 按钮发送加密邮件。</span><span class="sxs-lookup"><span data-stu-id="f5076-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="f5076-122">有关详细信息，请参阅[Outlook FOR PC 中的发送、查看和回复加密邮件](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-US&rs=en-US&ad=US)。</span><span class="sxs-lookup"><span data-stu-id="f5076-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-US&rs=en-US&ad=US).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="f5076-123">管理设置</span><span class="sxs-lookup"><span data-stu-id="f5076-123">Admin settings</span></span>

<span data-ttu-id="f5076-124">您可以在[Office 365 中](https://docs.microsoft.com/office365/securitycompliance/email-encryption)了解有关设置电子邮件加密的电子邮件加密的所有信息。</span><span class="sxs-lookup"><span data-stu-id="f5076-124">You can learn all about setting up email encryption at [Email encryption in Office 365](https://docs.microsoft.com/office365/securitycompliance/email-encryption).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="f5076-125">自动加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="f5076-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="f5076-126">管理员可以创建邮件流规则，以自动保护从您的市场活动中发送和接收的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f5076-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="f5076-127">设置用于加密任何传出电子邮件的规则，并删除来自组织内部或从您的组织发送的加密邮件的答复的加密邮件的加密。</span><span class="sxs-lookup"><span data-stu-id="f5076-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> 

<span data-ttu-id="f5076-128">您可以创建邮件流规则，以使用新的 Office 365 邮件加密（OME）功能对电子邮件进行加密。</span><span class="sxs-lookup"><span data-stu-id="f5076-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="f5076-129">使用 Exchange 管理中心（EAC）定义用于触发邮件加密的邮件流规则，这些规则使用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="f5076-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="f5076-130">在 web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户，登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f5076-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in to Office 365.</span></span> 
2. <span data-ttu-id="f5076-131">选择 "管理" 磁贴。</span><span class="sxs-lookup"><span data-stu-id="f5076-131">Choose the Admin tile.</span></span> 
3. <span data-ttu-id="f5076-132">在 "管理中心" 中，选择 "**管理中心" > Exchange**。</span><span class="sxs-lookup"><span data-stu-id="f5076-132">In the admin center, choose **Admin centers > Exchange**.</span></span> 

<span data-ttu-id="f5076-133">有关详细信息，请参阅[在 Office 365 中定义用于加密电子邮件的邮件流规则](https://docs.microsoft.com/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email)。</span><span class="sxs-lookup"><span data-stu-id="f5076-133">For more information, see [Define mail flow rules to encrypt email messages in Office 365](https://docs.microsoft.com/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="f5076-134">对加密邮件进行品牌打造</span><span class="sxs-lookup"><span data-stu-id="f5076-134">Brand your encryption messages</span></span>

<span data-ttu-id="f5076-135">您还可以应用您的市场活动品牌来自定义电子邮件中的外观和文本。</span><span class="sxs-lookup"><span data-stu-id="f5076-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="f5076-136">有关详细信息，请参阅[将组织的品牌添加到加密邮件](https://docs.microsoft.com/office365/securitycompliance/email-encryption)。</span><span class="sxs-lookup"><span data-stu-id="f5076-136">For more information, see [Add your organization's brand to your encrypted messages](https://docs.microsoft.com/office365/securitycompliance/email-encryption).</span></span>

