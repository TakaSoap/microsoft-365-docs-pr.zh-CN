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
- m365solution-smb
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
ms.openlocfilehash: d17abccd645b4dfdf933906dc90175be51f95c9a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044212"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="d80a8-103">加密或标记敏感电子邮件</span><span class="sxs-lookup"><span data-stu-id="d80a8-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="d80a8-104">你的数据和市场活动信息非常重要，并且通常是机密的。</span><span class="sxs-lookup"><span data-stu-id="d80a8-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="d80a8-105">使用加密和敏感度标签帮助保护此敏感信息，以便你和电子邮件收件人使用所需的敏感度处理信息。</span><span class="sxs-lookup"><span data-stu-id="d80a8-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>

## <a name="best-practices"></a><span data-ttu-id="d80a8-106">最佳做法</span><span class="sxs-lookup"><span data-stu-id="d80a8-106">Best practices</span></span>

<span data-ttu-id="d80a8-107">在发送包含机密或敏感信息的电子邮件之前，请考虑打开：</span><span class="sxs-lookup"><span data-stu-id="d80a8-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="d80a8-108">**加密：** 您可以加密电子邮件以保护电子邮件中信息的隐私。</span><span class="sxs-lookup"><span data-stu-id="d80a8-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="d80a8-109">加密电子邮件时，电子邮件会从可读纯文本转换为加密的cypher 文本。</span><span class="sxs-lookup"><span data-stu-id="d80a8-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="d80a8-110">只有具有与用于加密邮件的公钥匹配的私钥的收件人才能解密邮件进行阅读。</span><span class="sxs-lookup"><span data-stu-id="d80a8-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="d80a8-111">但是，任何没有相应私钥的收件人都可以看到无法解密的文本。</span><span class="sxs-lookup"><span data-stu-id="d80a8-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="d80a8-112">管理员可以定义规则以自动加密符合特定条件的邮件。</span><span class="sxs-lookup"><span data-stu-id="d80a8-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="d80a8-113">例如，管理员可以创建一个规则，对发送到组织外部的所有邮件或提及特定字词或短语的所有邮件进行加密。</span><span class="sxs-lookup"><span data-stu-id="d80a8-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="d80a8-114">将自动应用任何加密规则。</span><span class="sxs-lookup"><span data-stu-id="d80a8-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="d80a8-115">**敏感度标签：** 市场活动还可以设置可应用于文件和电子邮件的敏感度标签，以使它们符合市场活动的信息保护策略。</span><span class="sxs-lookup"><span data-stu-id="d80a8-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="d80a8-116">设置标签时，即使电子邮件已发送，标签也一直保留，例如，显示为邮件头。</span><span class="sxs-lookup"><span data-stu-id="d80a8-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![包含标签和加密标注的电子邮件关系图](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a><span data-ttu-id="d80a8-118">设置</span><span class="sxs-lookup"><span data-stu-id="d80a8-118">Set it up</span></span>

<span data-ttu-id="d80a8-119">如果要加密不满足预定义规则的邮件，或者管理员未设置任何规则，可以在发送邮件之前应用各种不同的加密规则。</span><span class="sxs-lookup"><span data-stu-id="d80a8-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="d80a8-120">若要从 Outlook 2013 或 2016 或 Outlook 2016 for Mac 发送加密邮件，请选择"选项> **权限**"，然后选择所需的保护选项。</span><span class="sxs-lookup"><span data-stu-id="d80a8-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="d80a8-121">您还可以通过选择 Outlook 网页中的"保护"按钮发送加密邮件。</span><span class="sxs-lookup"><span data-stu-id="d80a8-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="d80a8-122">有关详细信息，请参阅 Outlook for PC 中的发送、查看和回复 [加密邮件](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)。</span><span class="sxs-lookup"><span data-stu-id="d80a8-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="d80a8-123">管理员设置</span><span class="sxs-lookup"><span data-stu-id="d80a8-123">Admin settings</span></span>

<span data-ttu-id="d80a8-124">你可以了解有关在 [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)中设置电子邮件加密的所有信息。</span><span class="sxs-lookup"><span data-stu-id="d80a8-124">You can learn all about setting up email encryption at [Email encryption in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="d80a8-125">自动加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="d80a8-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="d80a8-126">管理员可以创建邮件流规则，以自动保护从市场活动发送和接收的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d80a8-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="d80a8-127">设置规则以加密任何传出电子邮件，并从来自组织内部的加密邮件或对从组织发送的加密邮件的答复中删除加密。</span><span class="sxs-lookup"><span data-stu-id="d80a8-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span>

<span data-ttu-id="d80a8-128">创建邮件流规则，以使用新的 Office 365 邮件加密和 OME (加密) 电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d80a8-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="d80a8-129">定义邮件流规则，以使用 Exchange 管理中心或 EAC (OME 功能触发) 。</span><span class="sxs-lookup"><span data-stu-id="d80a8-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="d80a8-130">在 Web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d80a8-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in.</span></span>
2. <span data-ttu-id="d80a8-131">选择"管理"磁贴。</span><span class="sxs-lookup"><span data-stu-id="d80a8-131">Choose the Admin tile.</span></span>
3. <span data-ttu-id="d80a8-132">在管理中心中，选择 **Exchange >管理中心**。</span><span class="sxs-lookup"><span data-stu-id="d80a8-132">In the admin center, choose **Admin centers > Exchange**.</span></span>

<span data-ttu-id="d80a8-133">有关详细信息，请参阅 [定义用于加密电子邮件的邮件流规则](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)。</span><span class="sxs-lookup"><span data-stu-id="d80a8-133">For more information, see [Define mail flow rules to encrypt email messages](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="d80a8-134">为加密邮件打造品牌</span><span class="sxs-lookup"><span data-stu-id="d80a8-134">Brand your encryption messages</span></span>

<span data-ttu-id="d80a8-135">还可以应用市场活动品牌以自定义电子邮件的外观和文本。</span><span class="sxs-lookup"><span data-stu-id="d80a8-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="d80a8-136">有关详细信息，请参阅 [将组织的品牌添加到加密邮件中](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)。</span><span class="sxs-lookup"><span data-stu-id="d80a8-136">For more information, see [Add your organization's brand to your encrypted messages](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>
