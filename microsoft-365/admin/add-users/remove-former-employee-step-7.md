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
ms.openlocfilehash: 0afa9b112919d2668d7553ac5bcf08e664bc1749
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244169"
---
# <a name="step-7---delete-a-former-employees-user-account"></a><span data-ttu-id="0b1d7-103">步骤 7 - 删除以前员工的用户帐户</span><span class="sxs-lookup"><span data-stu-id="0b1d7-103">Step 7 - Delete a former employee's user account</span></span>

<span data-ttu-id="0b1d7-104">保存并访问以前员工的所有用户数据之后，可以删除以前员工的帐户。</span><span class="sxs-lookup"><span data-stu-id="0b1d7-104">After you've saved and accessed all the former employee's user data, you can delete the former employee's account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0b1d7-p101">如果设置了电子邮件转发或将帐户转换成共享邮箱，则不要删除该帐户。这两项都需要帐户来定位转发或共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="0b1d7-p101">Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.</span></span>

1. <span data-ttu-id="0b1d7-107">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="0b1d7-107">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="0b1d7-108">选择要删除的员工的姓名。</span><span class="sxs-lookup"><span data-stu-id="0b1d7-108">Select the name of the employee that you want to delete.</span></span>
3. <span data-ttu-id="0b1d7-109">在用户名称下，选择"删除 **用户"。**</span><span class="sxs-lookup"><span data-stu-id="0b1d7-109">Under the user's name, select **Delete user**.</span></span> <span data-ttu-id="0b1d7-110">选择此用户需要的选项，然后选择"删除 **用户"。**</span><span class="sxs-lookup"><span data-stu-id="0b1d7-110">Choose the options you want for this user, and then select **Delete user**.</span></span> <span data-ttu-id="0b1d7-111">如果已向其他用户提供访问此用户的电子邮件和OneDrive，则不必在此处再次执行。</span><span class="sxs-lookup"><span data-stu-id="0b1d7-111">If you've already given another user access to this user's email and OneDrive, you don't have to do it again here.</span></span>

<span data-ttu-id="0b1d7-p103">删除用户后，其帐户将在大约 30 天内处于非活动状态。在永久删除用户之前，可还原帐户。</span><span class="sxs-lookup"><span data-stu-id="0b1d7-p103">When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.</span></span>
  
## <a name="does-your-organization-use-active-directory"></a><span data-ttu-id="0b1d7-114">组织是否使用 Active Directory？</span><span class="sxs-lookup"><span data-stu-id="0b1d7-114">Does your organization use Active Directory?</span></span>

<span data-ttu-id="0b1d7-115">如果组织将用户帐户与本地 Active Directory Microsoft 365同步，则必须在本地 Active Directory 服务中删除和还原这些用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0b1d7-115">If your organization synchronizes user accounts to Microsoft 365 from a local Active Directory environment, you must delete and restore those user accounts in your local Active Directory service.</span></span> <span data-ttu-id="0b1d7-116">你无法在 Office 365 中删除或还原它们。</span><span class="sxs-lookup"><span data-stu-id="0b1d7-116">You can't delete or restore them in Office 365.</span></span>

<span data-ttu-id="0b1d7-117">若要了解如何删除和还原 Active Directory 中的用户帐户，请参阅删除 [用户帐户](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="0b1d7-117">To learn how to delete and restore user account in Active Directory, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>
  
<span data-ttu-id="0b1d7-118">如果您使用的是 Azure Active Directory，请参阅[Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0b1d7-118">If you're using Azure Active Directory, see the [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell cmdlet.</span></span>
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a><span data-ttu-id="0b1d7-119">终止员工电子邮件会话须知事项</span><span class="sxs-lookup"><span data-stu-id="0b1d7-119">What you need to know about terminating an employee's email session</span></span>

<span data-ttu-id="0b1d7-120">下面的内容介绍了如何阻止员工继续使用电子邮件 (Exchange)。</span><span class="sxs-lookup"><span data-stu-id="0b1d7-120">Here's information about how to get an employee out of email (Exchange).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0b1d7-121">**可执行的操作**</span><span class="sxs-lookup"><span data-stu-id="0b1d7-121">**What you can do**</span></span> <br/> |<span data-ttu-id="0b1d7-122">**实现方式**</span><span class="sxs-lookup"><span data-stu-id="0b1d7-122">**How you do it**</span></span> <br/> |
|<span data-ttu-id="0b1d7-123">终止会话（如 Outlook 网页版、Outlook、Exchange Active Sync 等）并强制打开一个新的会话</span><span class="sxs-lookup"><span data-stu-id="0b1d7-123">Terminate a session (such as Outlook on the web, Outlook, Exchange active sync, etc.) and force to open a new session</span></span>  <br/> |<span data-ttu-id="0b1d7-124">重置密码</span><span class="sxs-lookup"><span data-stu-id="0b1d7-124">Reset password</span></span>  <br/> |
|<span data-ttu-id="0b1d7-125">终止会话并阻止对未来会话的访问（针对所有协议）</span><span class="sxs-lookup"><span data-stu-id="0b1d7-125">Terminate a session and block access to future sessions (for all protocols)</span></span>  <br/> |<span data-ttu-id="0b1d7-126">禁用帐户。</span><span class="sxs-lookup"><span data-stu-id="0b1d7-126">Disable the account.</span></span> <span data-ttu-id="0b1d7-127">例如， (管理Exchange使用 PowerShell) ：</span><span class="sxs-lookup"><span data-stu-id="0b1d7-127">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|<span data-ttu-id="0b1d7-128">针对特定协议终止会话（如 ActiveSync）</span><span class="sxs-lookup"><span data-stu-id="0b1d7-128">Terminate the session for a particular protocol (such as ActiveSync)</span></span>  <br/> |<span data-ttu-id="0b1d7-129">禁用协议。</span><span class="sxs-lookup"><span data-stu-id="0b1d7-129">Disable the protocol.</span></span> <span data-ttu-id="0b1d7-130">例如， (管理Exchange使用 PowerShell) ：</span><span class="sxs-lookup"><span data-stu-id="0b1d7-130">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

<span data-ttu-id="0b1d7-131">可在三处完成上述操作：</span><span class="sxs-lookup"><span data-stu-id="0b1d7-131">The above operations can be done in three places:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0b1d7-132">**如果在此处终止会话**</span><span class="sxs-lookup"><span data-stu-id="0b1d7-132">**If you terminate the session here**</span></span> <br/> |<span data-ttu-id="0b1d7-133">**所需时长**</span><span class="sxs-lookup"><span data-stu-id="0b1d7-133">**How long it takes**</span></span> <br/> |
|<span data-ttu-id="0b1d7-134">在 Exchange 管理中心或使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b1d7-134">In the Exchange admin center or using PowerShell</span></span>  <br/> |<span data-ttu-id="0b1d7-135">预期的延迟为 30 分钟以内</span><span class="sxs-lookup"><span data-stu-id="0b1d7-135">Expected delay is within 30 min</span></span>  <br/> |
|<span data-ttu-id="0b1d7-136">在 Azure Active Directory 管理中心中</span><span class="sxs-lookup"><span data-stu-id="0b1d7-136">In the Azure Active Directory admin center</span></span>  <br/> |<span data-ttu-id="0b1d7-137">预期的延迟为 60 分钟</span><span class="sxs-lookup"><span data-stu-id="0b1d7-137">Expected delay is 60 min</span></span>  <br/> |
|<span data-ttu-id="0b1d7-138">在本地环境中</span><span class="sxs-lookup"><span data-stu-id="0b1d7-138">In an on-premises environment</span></span>  <br/> |<span data-ttu-id="0b1d7-139">预期的延迟为 3 小时或以上</span><span class="sxs-lookup"><span data-stu-id="0b1d7-139">Expected delay is 3 hours or more</span></span>  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a><span data-ttu-id="0b1d7-140">如何最迅速地响应帐户终止</span><span class="sxs-lookup"><span data-stu-id="0b1d7-140">How to get fastest response for account termination</span></span>

 <span data-ttu-id="0b1d7-p107">**最快** ：使用 Exchange 管理中心（使用 PowerShell）或 Azure Active Directory 管理中心。在本地环境中可能需要数小时才能通过 DirSync 同步更改。</span><span class="sxs-lookup"><span data-stu-id="0b1d7-p107">**Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync.</span></span>
  
 <span data-ttu-id="0b1d7-p108">**对于本地和 Exchange 数据中心中的用户最快** ：使用 Azure Active Directory 管理中心/Exchange 管理中心终止会话，同时在本地环境中进行更改。否则，DirSync 将覆盖 Azure Active Directory 管理中心/Exchange 管理中心中的更改。</span><span class="sxs-lookup"><span data-stu-id="0b1d7-p108">**Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="0b1d7-145">相关文章</span><span class="sxs-lookup"><span data-stu-id="0b1d7-145">Related articles</span></span>

[<span data-ttu-id="0b1d7-146">还原用户</span><span class="sxs-lookup"><span data-stu-id="0b1d7-146">Restore a user</span></span>](restore-user.md)
