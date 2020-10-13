---
title: 解决共享邮箱问题
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 如果您在使用共享邮箱时遇到问题，请尝试这些解决方案。
ms.openlocfilehash: c889d3aa2fab8c2dce4cc2a8a00ef49a905363a1
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445503"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="741c5-103">解决共享邮箱问题</span><span class="sxs-lookup"><span data-stu-id="741c5-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="741c5-104">如果您在创建或使用共享邮箱时看到错误消息，请尝试这些可能的解决方案。</span><span class="sxs-lookup"><span data-stu-id="741c5-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="741c5-105">创建共享邮箱时出错</span><span class="sxs-lookup"><span data-stu-id="741c5-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="741c5-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="741c5-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="741c5-107">如果您看到错误消息，则 **代理地址 "smtp： <共享邮箱名称 \> " 已由代理地址或 "" LegacyExchangeDN 使用 \<name> 。请选择其他代理地址**，这表示你尝试为共享邮箱提供一个已在使用中的名称。</span><span class="sxs-lookup"><span data-stu-id="741c5-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="741c5-108">例如，假设希望共享邮箱命名为 info@domain1 和 info@domain2。</span><span class="sxs-lookup"><span data-stu-id="741c5-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="741c5-109">可通过 2 种方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="741c5-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="741c5-110">使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="741c5-110">Use Windows PowerShell.</span></span> <span data-ttu-id="741c5-111">有关说明，请参阅以下博客文章： [在不同的域中创建具有相同别名的共享邮箱](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="741c5-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="741c5-112">将第二个共享邮箱命名为不同于开头的内容，以避免出现此错误。</span><span class="sxs-lookup"><span data-stu-id="741c5-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="741c5-113">然后在管理中心内，将共享邮箱重命名为您想要的。</span><span class="sxs-lookup"><span data-stu-id="741c5-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="741c5-114">有关使用共享邮箱时不具有发送权限的错误</span><span class="sxs-lookup"><span data-stu-id="741c5-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="741c5-115">如果您创建了一个共享邮箱，然后尝试从该邮箱发送邮件，则可能会出现以下情况：</span><span class="sxs-lookup"><span data-stu-id="741c5-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="741c5-116">**无法发送此邮件。您没有代表指定用户发送邮件的权限。**</span><span class="sxs-lookup"><span data-stu-id="741c5-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="741c5-117">当 Microsoft 365 遇到复制延迟问题时，将出现此消息。</span><span class="sxs-lookup"><span data-stu-id="741c5-117">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="741c5-118">当您的新共享邮箱的信息 (或添加的用户) 在我们的所有数据中心之间进行复制时，它会在一小时后消失。</span><span class="sxs-lookup"><span data-stu-id="741c5-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="741c5-119">请等待一小时，然后再尝试发送一封邮件。</span><span class="sxs-lookup"><span data-stu-id="741c5-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="741c5-120">相关文章</span><span class="sxs-lookup"><span data-stu-id="741c5-120">Related articles</span></span>

[<span data-ttu-id="741c5-121">关于共享邮箱</span><span class="sxs-lookup"><span data-stu-id="741c5-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="741c5-122">创建共享邮箱</span><span class="sxs-lookup"><span data-stu-id="741c5-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="741c5-123">配置共享邮箱</span><span class="sxs-lookup"><span data-stu-id="741c5-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="741c5-124">将用户邮箱转换为共享邮箱</span><span class="sxs-lookup"><span data-stu-id="741c5-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="741c5-125">从共享邮箱删除许可证</span><span class="sxs-lookup"><span data-stu-id="741c5-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

