---
title: 删除以前的员工 - 概述
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 按照此解决方案中的步骤从员工Microsoft 365并保护组织的数据。
ms.openlocfilehash: 4b4cf59fdce81b3098ee333095daa8e1af1cd5c5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241732"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a><span data-ttu-id="c288f-103">概述：删除以前的员工和安全数据</span><span class="sxs-lookup"><span data-stu-id="c288f-103">Overview: Remove a former employee and secure data</span></span>

<span data-ttu-id="c288f-104">我们经常收到一个问题："当员工离开我的组织时，我应该如何保护数据和保护访问？"</span><span class="sxs-lookup"><span data-stu-id="c288f-104">A question we often get is, "What should I do to secure data and protect access when an employee leaves my organization?"</span></span> <span data-ttu-id="c288f-105">本系列文章介绍如何阻止访问Microsoft 365、保护数据应执行的步骤以及如何允许其他员工访问数据。</span><span class="sxs-lookup"><span data-stu-id="c288f-105">This article series explains how to block access to Microsoft 365, the steps you should take to secure your data, and how to allow other employees to access the data.</span></span>

<span data-ttu-id="c288f-106">观看有关删除员工的简短视频。</span><span class="sxs-lookup"><span data-stu-id="c288f-106">Watch a short video about removing an employee.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

<span data-ttu-id="c288f-107">如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](../../business-video/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="c288f-107">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

<span data-ttu-id="c288f-108">防止员工登录：</span><span class="sxs-lookup"><span data-stu-id="c288f-108">To prevent an employee from logging in:</span></span>

1. <span data-ttu-id="c288f-109">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="c288f-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c288f-110">选择用户名旁边的框，然后选择重置 **密码**。</span><span class="sxs-lookup"><span data-stu-id="c288f-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="c288f-111">输入新密码，然后选择"重置 **"。**</span><span class="sxs-lookup"><span data-stu-id="c288f-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="c288f-112"> (不要将其发送给他们。) </span><span class="sxs-lookup"><span data-stu-id="c288f-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="c288f-113">选择要转到其属性窗格的用户名称，在"帐户"选项卡上，选择"**启动注销"。**</span><span class="sxs-lookup"><span data-stu-id="c288f-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

> [!NOTE]
> <span data-ttu-id="c288f-114">你需要是全局管理员才能启动注销。</span><span class="sxs-lookup"><span data-stu-id="c288f-114">You need to be a global administrator to initiate sign-out.</span></span>

<span data-ttu-id="c288f-115">在一小时内（或离开当前Microsoft 365页面后）将提示他们重新登录。</span><span class="sxs-lookup"><span data-stu-id="c288f-115">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="c288f-116">访问令牌适合一小时，因此时间线取决于该令牌所剩的时间，以及他们是否导航到当前网页。</span><span class="sxs-lookup"><span data-stu-id="c288f-116">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c288f-117">尽管我们已对此解决方案中的步骤进行编号，并且不必按确切顺序完成解决方案，但我们建议采用这种方法执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="c288f-117">Although we've numbered the steps in this solution and you don't have to complete the solution using the exact order, we do recommend doing the steps this way.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c288f-118">准备工作</span><span class="sxs-lookup"><span data-stu-id="c288f-118">Before you begin</span></span>

<span data-ttu-id="c288f-119">您需要是全局管理员才能完成此解决方案中的步骤。</span><span class="sxs-lookup"><span data-stu-id="c288f-119">You need to be a global administrator to complete the steps in this solution.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c288f-120">**步骤**</span><span class="sxs-lookup"><span data-stu-id="c288f-120">**Step**</span></span> <br/> |<span data-ttu-id="c288f-121">**为什么执行此操作**</span><span class="sxs-lookup"><span data-stu-id="c288f-121">**Why do this**</span></span> <br/> |
|[<span data-ttu-id="c288f-122">步骤 1 - 阻止以前的员工登录并阻止对 Microsoft 365 服务的访问</span><span class="sxs-lookup"><span data-stu-id="c288f-122">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>](remove-former-employee-step-1.md) <br/> |<span data-ttu-id="c288f-123">这会阻止以前的员工登录Microsoft 365并阻止该员工访问Microsoft 365服务。</span><span class="sxs-lookup"><span data-stu-id="c288f-123">This blocks your former employee from logging in to Microsoft 365 and prevents the person from accessing Microsoft 365 services.</span></span> <br/> |
|[<span data-ttu-id="c288f-124">步骤 2 - 保存以前员工的邮箱的内容</span><span class="sxs-lookup"><span data-stu-id="c288f-124">Step 2 - Save the contents of a former employee's mailbox</span></span>](remove-former-employee-step-2.md) <br/> |<span data-ttu-id="c288f-125">这对将要接管员工工作或者存在诉讼的人很有用。</span><span class="sxs-lookup"><span data-stu-id="c288f-125">This is useful for the person who is going to take over the employee's work, or if there is litigation.</span></span> <br/> |
|[<span data-ttu-id="c288f-126">步骤 3 - 将前员工的电子邮件转发给其他员工或转换为共享邮箱</span><span class="sxs-lookup"><span data-stu-id="c288f-126">Step 3 - Forward a former employee's email to another employee or convert to a shared mailbox</span></span>](remove-former-employee-step-3.md) <br/> |<span data-ttu-id="c288f-p104">这可保证前员工的电子邮件地址处于活动状态。如果客户或合作伙伴仍向以前员工的地址发送电子邮件，此功能可让他们发送给接管该工作的员工。</span><span class="sxs-lookup"><span data-stu-id="c288f-p104">This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.</span></span> <br/> |
|[<span data-ttu-id="c288f-129">步骤 4 - 向另一名员工授予OneDrive和Outlook权限</span><span class="sxs-lookup"><span data-stu-id="c288f-129">Step 4 - Give another employee access to OneDrive and Outlook data</span></span>](remove-former-employee-step-6.md) <br/> |<span data-ttu-id="c288f-130">如果仅删除用户的许可证但不删除其帐户，则甚至 30 天后仍可访问该用户的 OneDrive 中的内容。</span><span class="sxs-lookup"><span data-stu-id="c288f-130">If you only remove a user's license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.</span></span> <br/><br/> <span data-ttu-id="c288f-131">在删除帐户之前，应该向其他用户授予OneDrive Outlook访问权限。</span><span class="sxs-lookup"><span data-stu-id="c288f-131">Before you delete the account, you should give access of their OneDrive and Outlook to another user.</span></span> <span data-ttu-id="c288f-132">删除员工帐户后，其OneDrive Outlook内容将保留 **30** 天。</span><span class="sxs-lookup"><span data-stu-id="c288f-132">After you delete an employee's account, the content in their OneDrive and Outlook is retained for **30** days.</span></span> <span data-ttu-id="c288f-133">但是，在这 30 天内，您可以还原用户帐户并访问其内容。</span><span class="sxs-lookup"><span data-stu-id="c288f-133">During that 30 days, however, you can restore the user's account, and gain access to their content.</span></span> <span data-ttu-id="c288f-134">如果还原用户帐户，OneDrive Outlook 30 天后仍可供你访问。</span><span class="sxs-lookup"><span data-stu-id="c288f-134">If you restore the user's account, the OneDrive and Outlook content will remain accessible to you even after 30 days.</span></span> <br/> |
|[<span data-ttu-id="c288f-135">步骤 5 - 擦除和阻止前员工的移动设备</span><span class="sxs-lookup"><span data-stu-id="c288f-135">Step 5 - Wipe and block a former employee's mobile device</span></span>](remove-former-employee-step-4.md) <br/> |<span data-ttu-id="c288f-136">从手机或平板电脑删除业务数据。</span><span class="sxs-lookup"><span data-stu-id="c288f-136">Removes your business data from the phone or tablet.</span></span>  <br/> |
|[<span data-ttu-id="c288f-137">步骤 6 - 删除Microsoft 365员工的许可证</span><span class="sxs-lookup"><span data-stu-id="c288f-137">Step 6 - Remove and delete the Microsoft 365 license from a former employee</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="c288f-p106">移除许可证后，可将许可证分配给其他人。也可删除许可证，以便在聘用其他人员之前，无需为其付费。  </span><span class="sxs-lookup"><span data-stu-id="c288f-p106">When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person. </span></span><br/><br/> <span data-ttu-id="c288f-p107">移除或删除许可证时，用户的旧电子邮件、联系人和日历将保留 **30 days** ，然后永久删除。如果删除许可证但不删除其帐户，则在 30 天后仍可以访问该用户的 OneDrive 中的内容。  </span><span class="sxs-lookup"><span data-stu-id="c288f-p107">When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  </span></span><br/> |
|[<span data-ttu-id="c288f-142">步骤 7 - 删除以前员工的用户帐户</span><span class="sxs-lookup"><span data-stu-id="c288f-142">Step 7 - Delete a former employee's user account</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="c288f-143">这将从管理中心中删除帐户。</span><span class="sxs-lookup"><span data-stu-id="c288f-143">This removes the account from your admin center.</span></span> <span data-ttu-id="c288f-144">进行清除，保持干净。</span><span class="sxs-lookup"><span data-stu-id="c288f-144">Keeps things clean.</span></span> <br/> |

## <a name="related-articles"></a><span data-ttu-id="c288f-145">相关文章</span><span class="sxs-lookup"><span data-stu-id="c288f-145">Related articles</span></span>

[<span data-ttu-id="c288f-146">还原用户</span><span class="sxs-lookup"><span data-stu-id="c288f-146">Restore a user</span></span>](restore-user.md)
