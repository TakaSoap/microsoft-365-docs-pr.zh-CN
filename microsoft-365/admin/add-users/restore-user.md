---
title: 还原用户
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: 在删除用户帐户后的 30 天内，可以还原该帐户以及所有数据，并且用户可以使用同一帐户登录。
ms.openlocfilehash: 83852136ee22ab3f63d8ada6a5a7290883c392e5
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623817"
---
# <a name="restore-a-user"></a><span data-ttu-id="76160-103">还原用户</span><span class="sxs-lookup"><span data-stu-id="76160-103">Restore a user</span></span>
   
<span data-ttu-id="76160-p101">如果在删除用户帐户后 30 天内还原用户帐户，则该用户帐户及其关联的所有数据都将还原。用户可使用相同的 工作或学校帐户 进行登录。其邮箱将完全还原。如果需要了解某个特定用户帐户还有多长时间便无法再还原，请[联系我们](../../business-video/get-help-support.md)。</span><span class="sxs-lookup"><span data-stu-id="76160-p101">When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../../business-video/get-help-support.md).</span></span>
  
<span data-ttu-id="76160-108">下面是一些提示︰</span><span class="sxs-lookup"><span data-stu-id="76160-108">Here are a couple of tips:</span></span>
  
- <span data-ttu-id="76160-109">确保许可证可用于分配给帐户。</span><span class="sxs-lookup"><span data-stu-id="76160-109">Make sure licenses are available to assign to the account.</span></span>
    
- <span data-ttu-id="76160-110">如果你的公司使用 Active Directory，请参阅[如何解决 Office 365 中已删除的用户帐户问题](/office365/troubleshoot/active-directory/restore-deleted-user-accounts.md)以获取有关还原用户帐户的说明。</span><span class="sxs-lookup"><span data-stu-id="76160-110">If your business uses Active Directory, see [How to troubleshoot deleted user accounts in Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts.md) for instructions on restoring a user account.</span></span> 
    
## <a name="restore-one-or-more-user-accounts"></a><span data-ttu-id="76160-111">还原一个或多个用户帐户</span><span class="sxs-lookup"><span data-stu-id="76160-111">Restore one or more user accounts</span></span>

<span data-ttu-id="76160-112">你必须是全局Microsoft 365管理员或用户管理管理员才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="76160-112">You must be a Microsoft 365 global admin or user management admin to do these steps.</span></span> 

1. <span data-ttu-id="76160-113">在管理中心，转到 **"用户** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">""已删除用户"</a> 页面。</span><span class="sxs-lookup"><span data-stu-id="76160-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="76160-114">在 **"已删除用户"** 页上，选择要还原的用户的名称，然后选择"还原 **"。**</span><span class="sxs-lookup"><span data-stu-id="76160-114">On the **Deleted users** page, select the names of the users who you want to restore, and then select **Restore**.</span></span>
    
3. <span data-ttu-id="76160-115">按照提示设置其密码，然后选择"还原 **"。**</span><span class="sxs-lookup"><span data-stu-id="76160-115">Follow the prompts to set their password, and then select **Restore**.</span></span>
    
4. <span data-ttu-id="76160-116">如果成功还原用户，请选择" **发送电子邮件"并关闭**。</span><span class="sxs-lookup"><span data-stu-id="76160-116">If the user is successfully restored, select **Send email and close**.</span></span> <span data-ttu-id="76160-117">如果遇到名称冲突或代理地址冲突，请参阅下述说明获取还原这些帐户的方法。</span><span class="sxs-lookup"><span data-stu-id="76160-117">If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.</span></span>
    
<span data-ttu-id="76160-118">还原用户后，请确保通知他们其密码已更改，然后跟进。</span><span class="sxs-lookup"><span data-stu-id="76160-118">After you've restored a user, make sure you notify them that their password changed and you follow up with them.</span></span>
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a><span data-ttu-id="76160-119">还原用户名有冲突的用户</span><span class="sxs-lookup"><span data-stu-id="76160-119">Restore a user that has a user name conflict</span></span>

<span data-ttu-id="76160-120">当删除用户帐户后，又创建了与该用户名相同的新用户帐户（为同一用户或具有相似名称的另一个用户），那么当稍后尝试还原已删除的帐户时会出现用户名冲突。</span><span class="sxs-lookup"><span data-stu-id="76160-120">A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.</span></span>
  
<span data-ttu-id="76160-p103">若要解决此问题，可以将活动的用户帐户替换为要还原的用户帐户，或者为要还原的帐户分配不同的用户名，这样就不会有两个用户名相同的帐户。步骤如下。</span><span class="sxs-lookup"><span data-stu-id="76160-p103">To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.</span></span>

1. <span data-ttu-id="76160-124">在管理中心，转到 **"用户** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">""已删除用户"</a> 页面。</span><span class="sxs-lookup"><span data-stu-id="76160-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>
  
2. <span data-ttu-id="76160-125">在 **"已删除用户"** 页上，选择要还原的用户的名称，然后选择"还原 **"。**</span><span class="sxs-lookup"><span data-stu-id="76160-125">On the **Deleted users** page, select the names of the users that you want to restore, and then select **Restore**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="76160-p104">如果两个或更多个用户还原失败，则会有错误消息告诉您一些用户的还原操作失败。查看日志以看看哪些用户未还原，然后逐个还原失败的帐户。</span><span class="sxs-lookup"><span data-stu-id="76160-p104">If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time.</span></span> 
  
3. <span data-ttu-id="76160-128">按照提示设置密码，然后选择"还原 **"。**</span><span class="sxs-lookup"><span data-stu-id="76160-128">Follow the prompts to set the password and select **Restore**.</span></span>
    
4. <span data-ttu-id="76160-p105">会弹出一条消息告诉你还原帐户时遇到问题。执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="76160-p105">A message pops up that says there was a problem restoring the account. Do one of the following:</span></span>
    
  - <span data-ttu-id="76160-p106">取消还原并重命名当前活动用户。然后再次尝试还原。</span><span class="sxs-lookup"><span data-stu-id="76160-p106">Cancel the restore and rename the current active user. Then attempt the restore again.</span></span>
    
  - <span data-ttu-id="76160-133">或者，键入用户的新主电子邮件地址，然后选择"还原 **"。**</span><span class="sxs-lookup"><span data-stu-id="76160-133">OR, type a new primary email address for the user and select **Restore**.</span></span>
    
5. <span data-ttu-id="76160-134">查看结果，然后选择" **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="76160-134">Review the results, and then select **Close**.</span></span>
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a><span data-ttu-id="76160-135">恢复具有代理地址冲突的用户</span><span class="sxs-lookup"><span data-stu-id="76160-135">Restore a user that has a proxy address conflict</span></span>

<span data-ttu-id="76160-p107">删除包含代理地址的用户帐户后，又将相同的代理地址分配给另一个帐户，那么当你尝试还原已删除的帐户时会出现代理地址冲突。请按照以下步骤操作以修复此问题。</span><span class="sxs-lookup"><span data-stu-id="76160-p107">A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.</span></span>
  
<span data-ttu-id="76160-138">为此，[你必须拥有](about-admin-roles.md)Microsoft 365权限。</span><span class="sxs-lookup"><span data-stu-id="76160-138">You must have [admin permissions](about-admin-roles.md) in Microsoft 365 to do this.</span></span> 

1. <span data-ttu-id="76160-139">在管理中心，转到 **"用户** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">""已删除用户"</a> 页面。</span><span class="sxs-lookup"><span data-stu-id="76160-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="76160-140">在" **已删除的用户**"页上，选择要还原的用户，然后选择" **还原**"。</span><span class="sxs-lookup"><span data-stu-id="76160-140">On the **Deleted users** page, select the user that you want to restore, and then select **Restore**.</span></span> 
    
3. <span data-ttu-id="76160-141">在"**还原**"页上，按照说明设置密码，然后选择"还原 **"。**</span><span class="sxs-lookup"><span data-stu-id="76160-141">On the **Restore** page, follow the instructions to set the password and select **Restore**.</span></span> <span data-ttu-id="76160-142">将从要还原的用户自动删除任何冲突的代理地址。</span><span class="sxs-lookup"><span data-stu-id="76160-142">Any conflicting proxy addresses are automatically removed from the user you are restoring.</span></span>
    
4. <span data-ttu-id="76160-143">查看结果，然后选择" **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="76160-143">Review the results, and then select **Close**.</span></span>

## <a name="related-content"></a><span data-ttu-id="76160-144">相关内容</span><span class="sxs-lookup"><span data-stu-id="76160-144">Related content</span></span>

<span data-ttu-id="76160-145">[删除用户 (](delete-a-user.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="76160-145">[Delete a user](delete-a-user.md) (article)</span></span>\
<span data-ttu-id="76160-146">[将管理员角色](assign-admin-roles.md) (视频) </span><span class="sxs-lookup"><span data-stu-id="76160-146">[Assign admin roles](assign-admin-roles.md) (video)</span></span>\
<span data-ttu-id="76160-147">[向用户分配许可证](../manage/assign-licenses-to-users.md) (本文) </span><span class="sxs-lookup"><span data-stu-id="76160-147">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)</span></span>
