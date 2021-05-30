---
title: 从共享邮箱删除许可证
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: nicholak
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: '从共享邮箱中删除许可证以将其分配给其他用户或返回许可证，以便不支付许可证费用。 '
ms.openlocfilehash: d33487879506402c5f0de2f7942c3299c5698b73
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706282"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="c8491-103">从共享邮箱中删除许可证</span><span class="sxs-lookup"><span data-stu-id="c8491-103">Remove a license from a shared mailbox</span></span>

<span data-ttu-id="c8491-104">共享邮箱通常不需要许可证。</span><span class="sxs-lookup"><span data-stu-id="c8491-104">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="c8491-105">按照以下说明从共享邮箱中删除许可证，以便你可以将其分配给用户或返回许可证，以便无需为不需要的许可证付费。</span><span class="sxs-lookup"><span data-stu-id="c8491-105">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
>
> <span data-ttu-id="c8491-106">在下列情况下需要许可证：</span><span class="sxs-lookup"><span data-stu-id="c8491-106">A license is required in the following scenarios:</span></span>
>
> 1. <span data-ttu-id="c8491-107">共享邮箱使用的存储空间超过 50 GB。</span><span class="sxs-lookup"><span data-stu-id="c8491-107">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="c8491-108">共享邮箱使用就地存档。</span><span class="sxs-lookup"><span data-stu-id="c8491-108">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="c8491-109">共享邮箱置于诉讼保留状态。</span><span class="sxs-lookup"><span data-stu-id="c8491-109">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="c8491-110">共享邮箱分配有 Microsoft Defender 许可证。</span><span class="sxs-lookup"><span data-stu-id="c8491-110">The shared mailbox has a Microsoft Defender license assigned.</span></span>

## <a name="remove-the-license"></a><span data-ttu-id="c8491-111">删除许可证</span><span class="sxs-lookup"><span data-stu-id="c8491-111">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c8491-112">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="c8491-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="c8491-113">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="c8491-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="c8491-114">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="c8491-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

   > [!NOTE]
   > <span data-ttu-id="c8491-115">您需要从"活动用户"页中删除许可证。</span><span class="sxs-lookup"><span data-stu-id="c8491-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="c8491-116">无法从"共享邮箱"页面删除许可证，因为许可证是用户设置。</span><span class="sxs-lookup"><span data-stu-id="c8491-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>
  
2. <span data-ttu-id="c8491-117">选择共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="c8491-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="c8491-118">在" **许可证和应用"** 选项卡中，展开 **"许可证** "并取消选中要删除的许可证的框。</span><span class="sxs-lookup"><span data-stu-id="c8491-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="c8491-119">选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="c8491-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="c8491-120">返回到"**活动用户"** 页面时，共享邮箱的状态将为 **"未授权"。**</span><span class="sxs-lookup"><span data-stu-id="c8491-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="c8491-121">你仍然支付许可证费用。</span><span class="sxs-lookup"><span data-stu-id="c8491-121">You're still paying for the license.</span></span> <span data-ttu-id="c8491-122">若要停止付费， [请从订阅中删除许可证](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="c8491-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="c8491-123">相关内容</span><span class="sxs-lookup"><span data-stu-id="c8491-123">Related content</span></span>

<span data-ttu-id="c8491-124">[关于共享邮箱](about-shared-mailboxes.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="c8491-124">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="c8491-125">[Create a shared mailbox (](create-a-shared-mailbox.md) article) </span><span class="sxs-lookup"><span data-stu-id="c8491-125">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="c8491-126">[配置共享邮箱](configure-a-shared-mailbox.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="c8491-126">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="c8491-127">[将用户邮箱转换为共享邮箱](convert-user-mailbox-to-shared-mailbox.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="c8491-127">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="c8491-128">[解决共享邮箱相关问题](resolve-issues-with-shared-mailboxes.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="c8491-128">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>
