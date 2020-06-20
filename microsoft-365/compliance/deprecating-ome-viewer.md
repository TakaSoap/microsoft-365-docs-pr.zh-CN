---
title: 弃用邮件加密查看器应用程序
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
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
description: Office 365 邮件加密（OME）查看器应用已从2018中的 Android 和 Apple 存储中删除。
ms.openlocfilehash: 9aca6fa2c0e9b276b666ffa187e3d18f061e7224
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817861"
---
# <a name="deprecating-message-encryption-viewer-app"></a><span data-ttu-id="76c0d-103">弃用邮件加密查看器应用程序</span><span class="sxs-lookup"><span data-stu-id="76c0d-103">Deprecating Message Encryption Viewer App</span></span>

<span data-ttu-id="76c0d-104">在2018年8月15日，我们从 Android 和 Apple 商店中删除了 Office 365 邮件加密（OME）查看器移动应用。</span><span class="sxs-lookup"><span data-stu-id="76c0d-104">On August 15, 2018, we removed the Office 365 Message Encryption (OME) Viewer mobile app from Android and Apple stores.</span></span> <span data-ttu-id="76c0d-105">Office 365 邮件加密查看器移动应用程序需要阅读使用 Apple 和 Android 手机上的早期版本的 OME 加密的电子邮件和附件。</span><span class="sxs-lookup"><span data-stu-id="76c0d-105">The Office 365 Message Encryption Viewer mobile app was required to read email messages and attachments that were encrypted with the previous version of OME on Apple and Android phones.</span></span> <span data-ttu-id="76c0d-106">除了删除 OME Viewer 应用程序，我们不会对早期版本的 OME 进行任何其他更改。</span><span class="sxs-lookup"><span data-stu-id="76c0d-106">Apart from removing the OME Viewer app, we are not making any other changes to the previous version of OME.</span></span>
  
## <a name="changes-from-august-2018"></a><span data-ttu-id="76c0d-107">2018年8月的更改</span><span class="sxs-lookup"><span data-stu-id="76c0d-107">Changes from August 2018</span></span>

<span data-ttu-id="76c0d-108">为2017年9月宣布，我们发布了[Office 365 邮件加密](https://aka.ms/ome2017)的新版本，以便用户可以向组织内外的任何人发送加密和受保护的邮件，而不需要移动应用。</span><span class="sxs-lookup"><span data-stu-id="76c0d-108">As announced September 2017, we have released a new version of [Office 365 Message Encryption](https://aka.ms/ome2017) so that users can send encrypted and protected messages to anyone inside or outside the organization without the requirement of the mobile app.</span></span> <span data-ttu-id="76c0d-109">从那时起，我们添加了其他功能：</span><span class="sxs-lookup"><span data-stu-id="76c0d-109">Since then, we've added additional capabilities:</span></span>
  
- [<span data-ttu-id="76c0d-110">仅加密模板</span><span class="sxs-lookup"><span data-stu-id="76c0d-110">Encrypt-only template</span></span>](https://aka.ms/encryptonly)

- [<span data-ttu-id="76c0d-111">用于解密附件的控件</span><span class="sxs-lookup"><span data-stu-id="76c0d-111">Control to decrypt attachments</span></span>](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)
    
<span data-ttu-id="76c0d-112">进行此更改后，用户将不再能够从8月1日开始下载 Office 365 邮件加密查看器移动应用。</span><span class="sxs-lookup"><span data-stu-id="76c0d-112">With this change, users will no longer be able to download the Office 365 Message Encryption Viewer mobile app beginning August 1.</span></span> <span data-ttu-id="76c0d-113">因此，邮件收件人可能无法读取在某些 Android 和 Apple 移动设备上使用 OME 的早期版本加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="76c0d-113">As a result, mail recipients may not be able to read messages encrypted with the previous version of OME on some Android and Apple mobile devices.</span></span> <span data-ttu-id="76c0d-114">但是，他们仍可以在个人计算机上读取这些邮件（通过桌面浏览器）。</span><span class="sxs-lookup"><span data-stu-id="76c0d-114">However, they will still be able to read these messages on personal computers (via desktop browsers).</span></span> <span data-ttu-id="76c0d-115">已下载应用程序的用户将继续能够使用它。</span><span class="sxs-lookup"><span data-stu-id="76c0d-115">Users who have already downloaded the app will continue to be able to use it.</span></span>
  
## <a name="why-this-change-was-made"></a><span data-ttu-id="76c0d-116">为什么要进行此更改</span><span class="sxs-lookup"><span data-stu-id="76c0d-116">Why this change was made</span></span>

<span data-ttu-id="76c0d-117">新版本的 OME 不再需要移动应用读取受保护的电子邮件和附件。</span><span class="sxs-lookup"><span data-stu-id="76c0d-117">The new version of OME no longer requires a mobile app to read protected email messages and attachments.</span></span> <span data-ttu-id="76c0d-118">使用新 OME 功能的客户可以在 Outlook mobile 中查看受保护的邮件，而非客户可以在浏览器中查看受保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="76c0d-118">Customers using the new OME capabilities can view the protected message in Outlook mobile and non-customers can view protected messages in a browser.</span></span>
  
<span data-ttu-id="76c0d-119">要求用户下载移动应用是客户查看受保护邮件的另一个障碍。</span><span class="sxs-lookup"><span data-stu-id="76c0d-119">Requiring users to download a mobile app is another hurdle for customers to view protected messages.</span></span> <span data-ttu-id="76c0d-120">新的 Office 365 邮件加密功能可提供更好的移动体验。</span><span class="sxs-lookup"><span data-stu-id="76c0d-120">The new Office 365 Message Encryption capabilities provide a better mobile experience.</span></span>
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="76c0d-121">我仍然可以使用以前版本的 Office 365 邮件加密</span><span class="sxs-lookup"><span data-stu-id="76c0d-121">Can I still use the previous version of Office 365 Message Encryption</span></span>

<span data-ttu-id="76c0d-122">早期版本的 Office 365 邮件加密目前不会被弃用。但是，我们对 Office 365 邮件加密的新版本进行了重要的增强，这使得加密和权限保护对任何设备的敏感数据更加简单，包括用户能够直接在 Outlook 中阅读受保护的邮件（桌面、移动和 web）。</span><span class="sxs-lookup"><span data-stu-id="76c0d-122">The previous version of Office 365 Message Encryption will not be deprecated at this time, however, we have made significant enhancements to the new version of Office 365 Message Encryption, which make it easier to encrypt and rights protect sensitive data to anyone and on any device - including the ability for users to read protected messages directly in Outlook (desktop, mobile, and web).</span></span> 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="76c0d-123">需要执行哪些操作才能为此更改做准备</span><span class="sxs-lookup"><span data-stu-id="76c0d-123">What do I need to do to prepare for this change</span></span>

<span data-ttu-id="76c0d-124">如果您的组织当前向需要 OME 查看器应用程序的收件人发送了加密附件，则应更新您的文档和培训资源。</span><span class="sxs-lookup"><span data-stu-id="76c0d-124">If your organization currently sends encrypted attachments to recipients that require the OME Viewer app, you should update your documentation and training resources.</span></span>
  
<span data-ttu-id="76c0d-125">我们建议您更新现有的 Exchange 邮件流规则，以使用当前版本的 OME，以便您的组织可以利用新的和改进的功能。</span><span class="sxs-lookup"><span data-stu-id="76c0d-125">We recommend updating existing Exchange mail flow rules to use the current version of OME so that your organization can take advantage of the new and improved capabilities.</span></span> <span data-ttu-id="76c0d-126">一旦设置了新的 OME 功能，收件人就不需要 OME 查看器应用来在移动设备上阅读加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="76c0d-126">Once you have set up the new OME capabilities, recipients won't need the OME Viewer app to read encrypted messages on mobile devices.</span></span>
  
<span data-ttu-id="76c0d-127">Microsoft 建议您制定一个计划，尽快移动到新的 OME 功能，因为它对您的组织合理。</span><span class="sxs-lookup"><span data-stu-id="76c0d-127">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="76c0d-128">有关说明，请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="76c0d-128">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="76c0d-129">如果您想要详细了解新功能的工作方式，请参阅[Office 365 邮件加密](ome.md)。</span><span class="sxs-lookup"><span data-stu-id="76c0d-129">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span>
  

