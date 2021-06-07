---
title: 步骤 7 - 删除以前员工的用户帐户
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
description: 按照以下步骤删除以前员工的用户帐户。
ms.openlocfilehash: 735821c9c4d6edf3d23fa3535ed9fa6b3d294b8c
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782377"
---
# <a name="step-7---delete-a-former-employees-user-account"></a><span data-ttu-id="0746c-103">步骤 7 - 删除以前员工的用户帐户</span><span class="sxs-lookup"><span data-stu-id="0746c-103">Step 7 - Delete a former employee's user account</span></span>

<span data-ttu-id="0746c-104">保存并访问以前员工的所有用户数据之后，可以删除以前员工的帐户。</span><span class="sxs-lookup"><span data-stu-id="0746c-104">After you've saved and accessed all the former employee's user data, you can delete the former employee's account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0746c-p101">如果设置了电子邮件转发或将帐户转换成共享邮箱，则不要删除该帐户。这两项都需要帐户来定位转发或共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="0746c-p101">Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.</span></span>

1. <span data-ttu-id="0746c-107">在管理中心，转到“**用户**\><a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="0746c-107">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="0746c-108">选择要删除的员工的姓名。</span><span class="sxs-lookup"><span data-stu-id="0746c-108">Select the name of the employee that you want to delete.</span></span>
3. <span data-ttu-id="0746c-109">在用户名称下，选择"删除 **用户"。**</span><span class="sxs-lookup"><span data-stu-id="0746c-109">Under the user's name, select **Delete user**.</span></span> <span data-ttu-id="0746c-110">选择此用户需要的选项，然后选择"删除 **用户"。**</span><span class="sxs-lookup"><span data-stu-id="0746c-110">Choose the options you want for this user, and then select **Delete user**.</span></span> <span data-ttu-id="0746c-111">如果已向其他用户提供访问此用户的电子邮件和OneDrive，则不必在此处再次执行。</span><span class="sxs-lookup"><span data-stu-id="0746c-111">If you've already given another user access to this user's email and OneDrive, you don't have to do it again here.</span></span>

<span data-ttu-id="0746c-p103">删除用户后，其帐户将在大约 30 天内处于非活动状态。在永久删除用户之前，可还原帐户。</span><span class="sxs-lookup"><span data-stu-id="0746c-p103">When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.</span></span>

## <a name="watch-delete-a-former-employees-user-account"></a><span data-ttu-id="0746c-114">观看：删除以前员工的用户帐户</span><span class="sxs-lookup"><span data-stu-id="0746c-114">Watch: Delete a former employee's user account</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR]

<span data-ttu-id="0746c-115">如果你觉得这段视频有用，请查看[适用于小型企业和 Microsoft 365 新手的完整培训系列](../../business-video/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="0746c-115">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="does-your-organization-use-active-directory"></a><span data-ttu-id="0746c-116">组织是否使用 Active Directory？</span><span class="sxs-lookup"><span data-stu-id="0746c-116">Does your organization use Active Directory?</span></span>

<span data-ttu-id="0746c-117">如果组织将用户帐户与本地 Active Directory Microsoft 365同步，则必须在本地 Active Directory 服务中删除和还原这些用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0746c-117">If your organization synchronizes user accounts to Microsoft 365 from a local Active Directory environment, you must delete and restore those user accounts in your local Active Directory service.</span></span> <span data-ttu-id="0746c-118">你无法在 Office 365 中删除或还原它们。</span><span class="sxs-lookup"><span data-stu-id="0746c-118">You can't delete or restore them in Office 365.</span></span>

<span data-ttu-id="0746c-119">若要了解如何删除和还原 Active Directory 中的用户帐户，请参阅删除 [用户帐户](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="0746c-119">To learn how to delete and restore user account in Active Directory, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>
  
<span data-ttu-id="0746c-120">如果您使用的是 Azure Active Directory，请参阅[Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0746c-120">If you're using Azure Active Directory, see the [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet.</span></span>
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a><span data-ttu-id="0746c-121">终止员工电子邮件会话须知事项</span><span class="sxs-lookup"><span data-stu-id="0746c-121">What you need to know about terminating an employee's email session</span></span>

<span data-ttu-id="0746c-122">下面的内容介绍了如何阻止员工继续使用电子邮件 (Exchange)。</span><span class="sxs-lookup"><span data-stu-id="0746c-122">Here's information about how to get an employee out of email (Exchange).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0746c-123">**可执行的操作**</span><span class="sxs-lookup"><span data-stu-id="0746c-123">**What you can do**</span></span> <br/> |<span data-ttu-id="0746c-124">**实现方式**</span><span class="sxs-lookup"><span data-stu-id="0746c-124">**How you do it**</span></span> <br/> |
|<span data-ttu-id="0746c-125">终止会话（如 Outlook 网页版、Outlook、Exchange Active Sync 等）并强制打开一个新的会话</span><span class="sxs-lookup"><span data-stu-id="0746c-125">Terminate a session (such as Outlook on the web, Outlook, Exchange active sync, etc.) and force to open a new session</span></span>  <br/> |<span data-ttu-id="0746c-126">重置密码</span><span class="sxs-lookup"><span data-stu-id="0746c-126">Reset password</span></span>  <br/> |
|<span data-ttu-id="0746c-127">终止会话并阻止对未来会话的访问（针对所有协议）</span><span class="sxs-lookup"><span data-stu-id="0746c-127">Terminate a session and block access to future sessions (for all protocols)</span></span>  <br/> |<span data-ttu-id="0746c-128">禁用帐户。</span><span class="sxs-lookup"><span data-stu-id="0746c-128">Disable the account.</span></span> <span data-ttu-id="0746c-129">例如， (管理Exchange使用 PowerShell) ：</span><span class="sxs-lookup"><span data-stu-id="0746c-129">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|<span data-ttu-id="0746c-130">针对特定协议终止会话（如 ActiveSync）</span><span class="sxs-lookup"><span data-stu-id="0746c-130">Terminate the session for a particular protocol (such as ActiveSync)</span></span>  <br/> |<span data-ttu-id="0746c-131">禁用协议。</span><span class="sxs-lookup"><span data-stu-id="0746c-131">Disable the protocol.</span></span> <span data-ttu-id="0746c-132">例如， (管理Exchange使用 PowerShell) ：</span><span class="sxs-lookup"><span data-stu-id="0746c-132">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

<span data-ttu-id="0746c-133">可在三处完成上述操作：</span><span class="sxs-lookup"><span data-stu-id="0746c-133">The above operations can be done in three places:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0746c-134">**如果在此处终止会话**</span><span class="sxs-lookup"><span data-stu-id="0746c-134">**If you terminate the session here**</span></span> <br/> |<span data-ttu-id="0746c-135">**所需时长**</span><span class="sxs-lookup"><span data-stu-id="0746c-135">**How long it takes**</span></span> <br/> |
|<span data-ttu-id="0746c-136">在 Exchange 管理中心或使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0746c-136">In the Exchange admin center or using PowerShell</span></span>  <br/> |<span data-ttu-id="0746c-137">预期的延迟为 30 分钟以内</span><span class="sxs-lookup"><span data-stu-id="0746c-137">Expected delay is within 30 min</span></span>  <br/> |
|<span data-ttu-id="0746c-138">在 Azure Active Directory 管理中心中</span><span class="sxs-lookup"><span data-stu-id="0746c-138">In the Azure Active Directory admin center</span></span>  <br/> |<span data-ttu-id="0746c-139">预期的延迟为 60 分钟</span><span class="sxs-lookup"><span data-stu-id="0746c-139">Expected delay is 60 min</span></span>  <br/> |
|<span data-ttu-id="0746c-140">在本地环境中</span><span class="sxs-lookup"><span data-stu-id="0746c-140">In an on-premises environment</span></span>  <br/> |<span data-ttu-id="0746c-141">预期的延迟为 3 小时或以上</span><span class="sxs-lookup"><span data-stu-id="0746c-141">Expected delay is 3 hours or more</span></span>  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a><span data-ttu-id="0746c-142">如何最迅速地响应帐户终止</span><span class="sxs-lookup"><span data-stu-id="0746c-142">How to get fastest response for account termination</span></span>

 <span data-ttu-id="0746c-p107">**最快** ：使用 Exchange 管理中心（使用 PowerShell）或 Azure Active Directory 管理中心。在本地环境中可能需要数小时才能通过 DirSync 同步更改。</span><span class="sxs-lookup"><span data-stu-id="0746c-p107">**Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync.</span></span>
  
 <span data-ttu-id="0746c-p108">**对于本地和 Exchange 数据中心中的用户最快** ：使用 Azure Active Directory 管理中心/Exchange 管理中心终止会话，同时在本地环境中进行更改。否则，DirSync 将覆盖 Azure Active Directory 管理中心/Exchange 管理中心中的更改。</span><span class="sxs-lookup"><span data-stu-id="0746c-p108">**Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="0746c-147">相关内容</span><span class="sxs-lookup"><span data-stu-id="0746c-147">Related content</span></span>

<span data-ttu-id="0746c-148">[Restore a user (](restore-user.md) article) / [Reset passwords](reset-passwords.md) (article) </span><span class="sxs-lookup"><span data-stu-id="0746c-148">[Restore a user](restore-user.md) (article)/ [Reset passwords](reset-passwords.md) (article)</span></span>
