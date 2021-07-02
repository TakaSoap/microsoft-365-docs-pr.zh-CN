---
title: 管理许可证请求
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- MACBillingLicensesRequests
- AdminSurgePortfolio
- commerce_licensing
search.appverid: MET150
description: 了解如何查看和批准或拒绝用户针对企业版订阅Microsoft 365请求。
ms.date: 06/07/2021
ms.openlocfilehash: 23258d21ebb413c56323aa4dab25cee60baf2be0
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256803"
---
# <a name="manage-license-requests"></a><span data-ttu-id="24878-103">管理许可证请求</span><span class="sxs-lookup"><span data-stu-id="24878-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="24878-104">本文中的信息仅适用于自助购买的产品。</span><span class="sxs-lookup"><span data-stu-id="24878-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="24878-105">若要了解更多信息，请参阅 [自助服务购买常见问题解答](../subscriptions/self-service-purchase-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="24878-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.yml).</span></span>

<span data-ttu-id="24878-106">如果在组织中禁用自助服务购买，可以使用许可证请求来管理用户的许可证请求过程。</span><span class="sxs-lookup"><span data-stu-id="24878-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="24878-107">当用户尝试为已阻止的产品进行自助购买时，他们可以向管理员提交许可证请求。当他们提出请求时，他们可以添加还需要产品许可证的其他用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="24878-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="24878-108">如果阻止用户进行自助购买，Microsoft 不会向用户发送营销电子邮件。</span><span class="sxs-lookup"><span data-stu-id="24878-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="24878-109">此外，如果他们使用的是产品的试用版，则他们不会看到购买它的提示。</span><span class="sxs-lookup"><span data-stu-id="24878-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="24878-110">若要了解更多信息，请参阅[管理管理员 (自助服务) 。 ](../subscriptions/manage-self-service-purchases-admins.md)</span><span class="sxs-lookup"><span data-stu-id="24878-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="24878-111">若要查看和管理许可证请求，管理员使用"许可"页上的"请求 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="24878-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="24878-112">该列表显示所请求的产品的名称、请求许可证的人的姓名、请求的日期以及请求的状态。</span><span class="sxs-lookup"><span data-stu-id="24878-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="24878-113">管理员可以筛选列表以显示挂起或已完成的请求。</span><span class="sxs-lookup"><span data-stu-id="24878-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="24878-114">请求将进行 30 天。</span><span class="sxs-lookup"><span data-stu-id="24878-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="24878-115">开始之前</span><span class="sxs-lookup"><span data-stu-id="24878-115">Before you begin</span></span>

<span data-ttu-id="24878-116">你必须是全局管理员才能执行本文中的任务。</span><span class="sxs-lookup"><span data-stu-id="24878-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="24878-117">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="24878-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="24878-118">使用自己的请求过程</span><span class="sxs-lookup"><span data-stu-id="24878-118">Use your own request process</span></span>

<span data-ttu-id="24878-119">如果您的组织有自己的请求流程，您可以改为使用它。</span><span class="sxs-lookup"><span data-stu-id="24878-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="24878-120">创建在用户请求许可证时向用户显示的消息。</span><span class="sxs-lookup"><span data-stu-id="24878-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24878-121">如果您使用自己的请求过程，则"请求"选项卡上不会 **显示任何** 请求。添加邮件之前的现有请求将继续显示，直到您批准或拒绝它们。</span><span class="sxs-lookup"><span data-stu-id="24878-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="24878-122">在管理中心中，转到"帐单 **""**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>"页面，然后选择"**请求"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="24878-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="24878-123">选择 **"改为使用现有请求进程"。**</span><span class="sxs-lookup"><span data-stu-id="24878-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="24878-124">在右侧窗格的" **消息** "框中，键入您希望用户在请求许可证时看到的消息。</span><span class="sxs-lookup"><span data-stu-id="24878-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="24878-125">如果要同时包含指向组织策略或其他文档的链接，请在"指向文档的链接"文本框中输入 (**可选**) URL。</span><span class="sxs-lookup"><span data-stu-id="24878-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="24878-126">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="24878-126">Select **Save**.</span></span>

<span data-ttu-id="24878-127">返回到"请求 **"列表时**，会看到消息"**正在使用自己的许可证请求流程"。**</span><span class="sxs-lookup"><span data-stu-id="24878-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="24878-128">若要更改发送给用户的邮件，请选择"**改为使用现有请求进程"。**</span><span class="sxs-lookup"><span data-stu-id="24878-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="24878-129">停止使用自己的请求过程</span><span class="sxs-lookup"><span data-stu-id="24878-129">Stop using your own request process</span></span>

1. <span data-ttu-id="24878-130">在管理中心中，转到"帐单 **""**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>"页面，然后选择"**请求"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="24878-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="24878-131">选择 **"改为使用现有请求进程"。**</span><span class="sxs-lookup"><span data-stu-id="24878-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="24878-132">在右窗格中，清除" **使用我的组织的请求流程"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="24878-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="24878-133">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="24878-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="24878-134">批准或拒绝许可证请求</span><span class="sxs-lookup"><span data-stu-id="24878-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="24878-135">在管理中心中，转到"帐单 **""**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>"页面，然后选择"**请求"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="24878-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="24878-136">选择包含要审阅的请求的行。</span><span class="sxs-lookup"><span data-stu-id="24878-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="24878-137">右窗格显示有关哪些用户希望获得产品许可证的详细信息。</span><span class="sxs-lookup"><span data-stu-id="24878-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="24878-138">若要拒绝整个请求，请选择 **"不批准"，** 在对话框中选择"**不批准"。**</span><span class="sxs-lookup"><span data-stu-id="24878-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="24878-139">若要拒绝某些用户的请求，但批准其他用户，请按要删除的用户的名称选择 X。</span><span class="sxs-lookup"><span data-stu-id="24878-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="24878-140">他们的名称在"不 **分配给这些用户"下移动**。</span><span class="sxs-lookup"><span data-stu-id="24878-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="24878-141">如果你有多个产品，请在"选择产品"下，选择要用于为其分配许可证的产品。</span><span class="sxs-lookup"><span data-stu-id="24878-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="24878-142">若要拒绝用户访问某些应用和服务，请展开打开或关闭应用和服务，然后清除要排除的应用和服务复选框。</span><span class="sxs-lookup"><span data-stu-id="24878-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="24878-143">在窗格底部，在文本框中键入可选邮件。</span><span class="sxs-lookup"><span data-stu-id="24878-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="24878-144">完成后，选择"批准 **"。**</span><span class="sxs-lookup"><span data-stu-id="24878-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="24878-145">右窗格显示请求的详细信息。</span><span class="sxs-lookup"><span data-stu-id="24878-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="24878-146">关闭右窗格。</span><span class="sxs-lookup"><span data-stu-id="24878-146">Close the right pane.</span></span>
    <span data-ttu-id="24878-147">用户收到一封电子邮件，指出其请求已获得批准或拒绝。</span><span class="sxs-lookup"><span data-stu-id="24878-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="24878-148">相关内容</span><span class="sxs-lookup"><span data-stu-id="24878-148">Related content</span></span>

<span data-ttu-id="24878-149">[向用户分配许可证](../../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="24878-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)\</span></span>
<span data-ttu-id="24878-150">[将用户移动到其他订阅 (](../subscriptions/move-users-different-subscription.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="24878-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="24878-151">[购买或删除订阅许可证](buy-licenses.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="24878-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>
