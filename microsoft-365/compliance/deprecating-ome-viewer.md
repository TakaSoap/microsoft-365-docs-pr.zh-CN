---
title: 弃用邮件加密查看器应用
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 邮件加密 (OME) Viewer 应用于 2018 年从 Android 和 Apple 应用商店中删除。
ms.openlocfilehash: bb96601a8a542d53f6732ab9316051c1a820ba46
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741519"
---
# <a name="deprecating-message-encryption-viewer-app"></a><span data-ttu-id="79636-103">弃用邮件加密查看器应用</span><span class="sxs-lookup"><span data-stu-id="79636-103">Deprecating Message Encryption Viewer App</span></span>

<span data-ttu-id="79636-104">2018 年 8 月 15 日，我们从 Android 和 Apple 应用商店中删除了 Office 365 邮件加密 (OME) Viewer 移动应用。</span><span class="sxs-lookup"><span data-stu-id="79636-104">On August 15, 2018, we removed the Office 365 Message Encryption (OME) Viewer mobile app from Android and Apple stores.</span></span> <span data-ttu-id="79636-105">需要 Office 365 邮件加密查看器移动应用才能读取在 Apple 和 Android 手机上使用以前版本的 OME 加密的电子邮件和附件。</span><span class="sxs-lookup"><span data-stu-id="79636-105">The Office 365 Message Encryption Viewer mobile app was required to read email messages and attachments that were encrypted with the previous version of OME on Apple and Android phones.</span></span> <span data-ttu-id="79636-106">除了删除 OME 查看器应用外，我们不会对以前版本的 OME 进行任何其他更改。</span><span class="sxs-lookup"><span data-stu-id="79636-106">Apart from removing the OME Viewer app, we are not making any other changes to the previous version of OME.</span></span>
  
## <a name="changes-from-august-2018"></a><span data-ttu-id="79636-107">2018 年 8 月更改</span><span class="sxs-lookup"><span data-stu-id="79636-107">Changes from August 2018</span></span>

<span data-ttu-id="79636-108">正如 2017 年 9 月发布的公告，我们发布了 [新版本的 Office 365](https://aka.ms/ome2017) 邮件加密，以便用户可以向组织内部或外部的任何人发送加密和受保护的邮件，而无需使用移动应用。</span><span class="sxs-lookup"><span data-stu-id="79636-108">As announced September 2017, we have released a new version of [Office 365 Message Encryption](https://aka.ms/ome2017) so that users can send encrypted and protected messages to anyone inside or outside the organization without the requirement of the mobile app.</span></span> <span data-ttu-id="79636-109">此后，我们添加了其他功能：</span><span class="sxs-lookup"><span data-stu-id="79636-109">Since then, we've added additional capabilities:</span></span>
  
- [<span data-ttu-id="79636-110">仅加密模板</span><span class="sxs-lookup"><span data-stu-id="79636-110">Encrypt-only template</span></span>](https://aka.ms/encryptonly)

- [<span data-ttu-id="79636-111">用于解密附件的控件</span><span class="sxs-lookup"><span data-stu-id="79636-111">Control to decrypt attachments</span></span>](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)

<span data-ttu-id="79636-112">通过此更改，用户将不再能够从 8 月 1 开始下载 Office 365 邮件加密查看器移动应用。</span><span class="sxs-lookup"><span data-stu-id="79636-112">With this change, users will no longer be able to download the Office 365 Message Encryption Viewer mobile app beginning August 1.</span></span> <span data-ttu-id="79636-113">因此，邮件收件人可能无法在某些 Android 和 Apple 移动设备上读取使用以前版本的 OME 加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="79636-113">As a result, mail recipients may not be able to read messages encrypted with the previous version of OME on some Android and Apple mobile devices.</span></span> <span data-ttu-id="79636-114">但是，他们仍然能够在个人计算机上读取这些消息， (桌面浏览器) 。</span><span class="sxs-lookup"><span data-stu-id="79636-114">However, they will still be able to read these messages on personal computers (via desktop browsers).</span></span> <span data-ttu-id="79636-115">已下载应用的用户将继续能够使用它。</span><span class="sxs-lookup"><span data-stu-id="79636-115">Users who have already downloaded the app will continue to be able to use it.</span></span>
  
## <a name="why-this-change-was-made"></a><span data-ttu-id="79636-116">为何进行此更改</span><span class="sxs-lookup"><span data-stu-id="79636-116">Why this change was made</span></span>

<span data-ttu-id="79636-117">新版本的 OME 不再需要移动应用来读取受保护的电子邮件和附件。</span><span class="sxs-lookup"><span data-stu-id="79636-117">The new version of OME no longer requires a mobile app to read protected email messages and attachments.</span></span> <span data-ttu-id="79636-118">使用新的 OME 功能的客户可以在 Outlook 移动版中查看受保护的邮件，非客户可以在浏览器中查看受保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="79636-118">Customers using the new OME capabilities can view the protected message in Outlook mobile and non-customers can view protected messages in a browser.</span></span>
  
<span data-ttu-id="79636-119">要求用户下载移动应用是客户查看受保护邮件的另一障碍。</span><span class="sxs-lookup"><span data-stu-id="79636-119">Requiring users to download a mobile app is another hurdle for customers to view protected messages.</span></span> <span data-ttu-id="79636-120">新的 Office 365 邮件加密功能提供更好的移动体验。</span><span class="sxs-lookup"><span data-stu-id="79636-120">The new Office 365 Message Encryption capabilities provide a better mobile experience.</span></span>
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="79636-121">我是否仍可以使用 Office 365 邮件加密的以前版本</span><span class="sxs-lookup"><span data-stu-id="79636-121">Can I still use the previous version of Office 365 Message Encryption</span></span>

<span data-ttu-id="79636-122">目前不会弃用早期版本的 Office 365 邮件加密，但是，我们对新版本的 Office 365 邮件加密进行了重大增强，使对任何人以及任何设备上敏感数据进行加密和权限保护变得更加简单，包括用户直接在 Outlook (桌面版、移动版和 Web) 中读取受保护邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="79636-122">The previous version of Office 365 Message Encryption will not be deprecated at this time, however, we have made significant enhancements to the new version of Office 365 Message Encryption, which make it easier to encrypt and rights protect sensitive data to anyone and on any device - including the ability for users to read protected messages directly in Outlook (desktop, mobile, and web).</span></span> 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="79636-123">我需要做什么来准备此更改</span><span class="sxs-lookup"><span data-stu-id="79636-123">What do I need to do to prepare for this change</span></span>

<span data-ttu-id="79636-124">如果组织当前向需要 OME 查看器应用的收件人发送加密附件，应更新文档和培训资源。</span><span class="sxs-lookup"><span data-stu-id="79636-124">If your organization currently sends encrypted attachments to recipients that require the OME Viewer app, you should update your documentation and training resources.</span></span>
  
<span data-ttu-id="79636-125">我们建议更新现有的 Exchange 邮件流规则以使用当前版本的 OME，以便您的组织可以利用新增和改进的功能。</span><span class="sxs-lookup"><span data-stu-id="79636-125">We recommend updating existing Exchange mail flow rules to use the current version of OME so that your organization can take advantage of the new and improved capabilities.</span></span> <span data-ttu-id="79636-126">设置新的 OME 功能后，收件人无需 OME 查看器应用在移动设备上读取加密邮件。</span><span class="sxs-lookup"><span data-stu-id="79636-126">Once you have set up the new OME capabilities, recipients won't need the OME Viewer app to read encrypted messages on mobile devices.</span></span>
  
<span data-ttu-id="79636-127">Microsoft 建议你在组织合理时制定移动到新 OME 功能的计划。</span><span class="sxs-lookup"><span data-stu-id="79636-127">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="79636-128">有关说明，请参阅 [设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="79636-128">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="79636-129">若要详细了解新功能如何首先工作，请参阅 [Office 365 邮件加密](ome.md)。</span><span class="sxs-lookup"><span data-stu-id="79636-129">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span>
  

