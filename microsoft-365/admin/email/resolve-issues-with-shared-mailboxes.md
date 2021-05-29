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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 设置共享邮箱时可能会出错。 如果遇到共享邮箱问题，请尝试这些解决方案。
ms.openlocfilehash: 89cdfbe29ab035b1eb6c3a0183629eef59d67477
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706126"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="29440-104">解决共享邮箱问题</span><span class="sxs-lookup"><span data-stu-id="29440-104">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="29440-105">如果在创建和使用共享邮箱时看到错误消息，请尝试这些可能的解决方案。</span><span class="sxs-lookup"><span data-stu-id="29440-105">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="29440-106">创建共享邮箱时出错</span><span class="sxs-lookup"><span data-stu-id="29440-106">Error when creating shared mailboxes</span></span>
<span data-ttu-id="29440-107"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="29440-107"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="29440-108">如果看到错误消息，代理地址 **"smtp：<shared mailbox name"已被代理地址或" "的 \> LegacyExchangeDN \<name> 使用。请选择其他代理地址**，这意味着你要尝试为共享邮箱指定一个已在使用的名称。</span><span class="sxs-lookup"><span data-stu-id="29440-108">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="29440-109">例如，假设希望共享邮箱命名为 info@domain1 和 info@domain2。</span><span class="sxs-lookup"><span data-stu-id="29440-109">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="29440-110">可以通过两种方式来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="29440-110">There are two ways to do this:</span></span>

  - <span data-ttu-id="29440-111">使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="29440-111">Use Windows PowerShell.</span></span> <span data-ttu-id="29440-112">有关说明，请参阅此博客文章 [：在不同域中创建同名别名的共享邮箱](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="29440-112">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="29440-113">将第二个共享邮箱的名称从一开始不同，以绕开错误。</span><span class="sxs-lookup"><span data-stu-id="29440-113">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="29440-114">然后在管理中心中，将共享邮箱重命名为您希望它的名称。</span><span class="sxs-lookup"><span data-stu-id="29440-114">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="29440-115">使用共享邮箱时没有发送权限的错误</span><span class="sxs-lookup"><span data-stu-id="29440-115">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="29440-116">如果您创建了共享邮箱，然后尝试从该邮箱发送邮件，您可能会收到以下消息：</span><span class="sxs-lookup"><span data-stu-id="29440-116">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="29440-117">**无法发送此消息。您没有代表指定用户发送邮件的权限。**</span><span class="sxs-lookup"><span data-stu-id="29440-117">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="29440-118">当用户遇到Microsoft 365延迟问题时，将出现此消息。</span><span class="sxs-lookup"><span data-stu-id="29440-118">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="29440-119">在一小时左右的时间，当有关新共享邮箱或已添加 (用户邮箱的信息) 我们的所有数据中心进行复制时，该邮箱应该会消失。</span><span class="sxs-lookup"><span data-stu-id="29440-119">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="29440-120">等待一小时，然后再次尝试发送邮件。</span><span class="sxs-lookup"><span data-stu-id="29440-120">Wait an hour and then try again to send a message.</span></span>

## <a name="related-content"></a><span data-ttu-id="29440-121">相关内容</span><span class="sxs-lookup"><span data-stu-id="29440-121">Related content</span></span>

<span data-ttu-id="29440-122">[关于共享邮箱](about-shared-mailboxes.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="29440-122">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="29440-123">[Create a shared mailbox (](create-a-shared-mailbox.md) article) </span><span class="sxs-lookup"><span data-stu-id="29440-123">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="29440-124">[配置共享邮箱](configure-a-shared-mailbox.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="29440-124">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="29440-125">[将用户邮箱转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="29440-125">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="29440-126">[从共享邮箱删除许可证](remove-license-from-shared-mailbox.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="29440-126">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>


    

