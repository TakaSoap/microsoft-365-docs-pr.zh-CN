---
title: 在 Office 365 中还原用户
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: 了解如何还原已删除的 Office 365 用户帐户以及所有关联的数据。
ms.openlocfilehash: 385f7938f5e0ce1f3a580d40830124f77454f64d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238142"
---
# <a name="restore-a-user-in-office-365"></a><span data-ttu-id="8502d-103">在 Office 365 中还原用户</span><span class="sxs-lookup"><span data-stu-id="8502d-103">Restore a user in Office 365</span></span>
   
<span data-ttu-id="8502d-p101">如果在删除用户帐户后 30 天内还原用户帐户，则该用户帐户及其关联的所有数据都将还原。用户可使用相同的 工作或学校帐户 进行登录。其邮箱将完全还原。如果需要了解某个特定用户帐户还有多长时间便无法再还原，请[联系我们](../contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="8502d-p101">When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../contact-support-for-business-products.md).</span></span>
  
<span data-ttu-id="8502d-108">下面是一些提示︰</span><span class="sxs-lookup"><span data-stu-id="8502d-108">Here are a couple of tips:</span></span>
  
- <span data-ttu-id="8502d-109">确保有可分配到帐户的 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="8502d-109">Make sure there are Office 365 licenses available that you can assign to the account.</span></span>
    
- <span data-ttu-id="8502d-110">如果你的公司使用 Active Directory，请参阅[如何解决 Office 365 中已删除的用户帐户问题](https://support.microsoft.com/kb/2619308)以获取有关还原用户帐户的说明。</span><span class="sxs-lookup"><span data-stu-id="8502d-110">If your business uses Active Directory, see [How to troubleshoot deleted user accounts in Office 365](https://support.microsoft.com/kb/2619308) for instructions on restoring a user account.</span></span> 
    
## <a name="restore-one-or-more-user-accounts"></a><span data-ttu-id="8502d-111">还原一个或多个用户帐户</span><span class="sxs-lookup"><span data-stu-id="8502d-111">Restore one or more user accounts</span></span>

<span data-ttu-id="8502d-112">您必须是 Office 365 中的全局管理员或用户管理管理员才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="8502d-112">You must be a global admin or user management admin in Office 365 to do these steps.</span></span> 
  
 
::: moniker range="o365-worldwide"

1. <span data-ttu-id="8502d-113">在管理中心中，转到 "**用户** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">已删除用户</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="8502d-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8502d-114">转到 "[管理中心](https://go.microsoft.com/fwlink/p/?linkid=848041)"，然后选择 "**用户** \> **已删除的用户**"。</span><span class="sxs-lookup"><span data-stu-id="8502d-114">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8502d-115">转到 "[管理中心](https://go.microsoft.com/fwlink/p/?linkid=850627)"，然后选择 "**用户** \> **已删除的用户**"。</span><span class="sxs-lookup"><span data-stu-id="8502d-115">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

2. <span data-ttu-id="8502d-116">在 "**已删除的用户**" 页上，选择要还原的用户的名称，然后选择 "**还原**"。</span><span class="sxs-lookup"><span data-stu-id="8502d-116">On the **Deleted users** page, select the names of the users who you want to restore, and then select **Restore**.</span></span>
    
 
3. <span data-ttu-id="8502d-117">按照提示设置其密码，然后选择 "**还原**"。</span><span class="sxs-lookup"><span data-stu-id="8502d-117">Follow the prompts to set their password, and then select **Restore**.</span></span>
    
4. <span data-ttu-id="8502d-118">如果用户已成功还原，请选择 "**发送电子邮件并关闭**"。</span><span class="sxs-lookup"><span data-stu-id="8502d-118">If the user is successfully restored, select **Send email and close**.</span></span> <span data-ttu-id="8502d-119">如果遇到名称冲突或代理地址冲突，请参阅下述说明获取还原这些帐户的方法。</span><span class="sxs-lookup"><span data-stu-id="8502d-119">If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.</span></span>
    
<span data-ttu-id="8502d-120">还原用户后，请确保通知他们密码已更改，并跟踪它们。</span><span class="sxs-lookup"><span data-stu-id="8502d-120">After you've restored a user, make sure you notify them that their password changed and you follow up with them.</span></span>
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a><span data-ttu-id="8502d-121">还原用户名有冲突的用户</span><span class="sxs-lookup"><span data-stu-id="8502d-121">Restore a user that has a user name conflict</span></span>
<span data-ttu-id="8502d-122"><a name="RestoreUserNameConflict"> </a></span><span class="sxs-lookup"><span data-stu-id="8502d-122"><a name="RestoreUserNameConflict"> </a></span></span>

<span data-ttu-id="8502d-123">当删除用户帐户后，又创建了与该用户名相同的新用户帐户（为同一用户或具有相似名称的另一个用户），那么当稍后尝试还原已删除的帐户时会出现用户名冲突。</span><span class="sxs-lookup"><span data-stu-id="8502d-123">A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.</span></span>
  
<span data-ttu-id="8502d-p103">若要解决此问题，可以将活动的用户帐户替换为要还原的用户帐户，或者为要还原的帐户分配不同的用户名，这样就不会有两个用户名相同的帐户。步骤如下。</span><span class="sxs-lookup"><span data-stu-id="8502d-p103">To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.</span></span>
  

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8502d-127">在管理中心中，转到 "**用户** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">已删除用户</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="8502d-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8502d-128">转到 "[管理中心](https://go.microsoft.com/fwlink/p/?linkid=848041)"，然后选择 "**用户** \> **已删除的用户**"。</span><span class="sxs-lookup"><span data-stu-id="8502d-128">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8502d-129">转到 "[管理中心](https://go.microsoft.com/fwlink/p/?linkid=850627)"，然后选择 "**用户** \> **已删除的用户**"。</span><span class="sxs-lookup"><span data-stu-id="8502d-129">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

  
2. <span data-ttu-id="8502d-130">在 "**已删除的用户**" 页上，选择要还原的用户的名称，然后选择 "**还原**"。</span><span class="sxs-lookup"><span data-stu-id="8502d-130">On the **Deleted users** page, select the names of the users that you want to restore, and then select **Restore**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8502d-p104">如果两个或更多个用户还原失败，则会有错误消息告诉您一些用户的还原操作失败。查看日志以看看哪些用户未还原，然后逐个还原失败的帐户。</span><span class="sxs-lookup"><span data-stu-id="8502d-p104">If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time.</span></span> 
  
3. <span data-ttu-id="8502d-133">按照提示设置密码，然后选择 "**还原**"。</span><span class="sxs-lookup"><span data-stu-id="8502d-133">Follow the prompts to set the password and select **Restore**.</span></span>
    
4. <span data-ttu-id="8502d-p105">会弹出一条消息告诉你还原帐户时遇到问题。执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="8502d-p105">A message pops up that says there was a problem restoring the account. Do one of the following:</span></span>
    
  - <span data-ttu-id="8502d-p106">取消还原并重命名当前活动用户。然后再次尝试还原。</span><span class="sxs-lookup"><span data-stu-id="8502d-p106">Cancel the restore and rename the current active user. Then attempt the restore again.</span></span>
    
  - <span data-ttu-id="8502d-138">或者，为用户键入一个新的主电子邮件地址，然后选择 "**还原**"。</span><span class="sxs-lookup"><span data-stu-id="8502d-138">OR, type a new primary email address for the user and select **Restore**.</span></span>
    
5. <span data-ttu-id="8502d-139">查看结果，然后选择" **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="8502d-139">Review the results, and then select **Close**.</span></span>
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a><span data-ttu-id="8502d-140">恢复具有代理地址冲突的用户</span><span class="sxs-lookup"><span data-stu-id="8502d-140">Restore a user that has a proxy address conflict</span></span>

<span data-ttu-id="8502d-p107">删除包含代理地址的用户帐户后，又将相同的代理地址分配给另一个帐户，那么当你尝试还原已删除的帐户时会出现代理地址冲突。请按照以下步骤操作以修复此问题。</span><span class="sxs-lookup"><span data-stu-id="8502d-p107">A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.</span></span>
  
<span data-ttu-id="8502d-143">只有 Office 365 的[管理员权限](about-admin-roles.md)才能执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8502d-143">You must have [admin permissions](about-admin-roles.md) in Office 365 to do this.</span></span> 
  

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8502d-144">在管理中心中，转到 "**用户** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">已删除用户</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="8502d-144">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="8502d-145">转到 "[管理中心](https://go.microsoft.com/fwlink/p/?linkid=848041)"，然后选择 "**用户** \> **已删除的用户**"。</span><span class="sxs-lookup"><span data-stu-id="8502d-145">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8502d-146">转到 "[管理中心](https://go.microsoft.com/fwlink/p/?linkid=850627)"，然后选择 "**用户** \> **已删除的用户**"。</span><span class="sxs-lookup"><span data-stu-id="8502d-146">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

2. <span data-ttu-id="8502d-147">在" **已删除的用户**"页上，选择要还原的用户，然后选择" **还原**"。</span><span class="sxs-lookup"><span data-stu-id="8502d-147">On the **Deleted users** page, select the user that you want to restore, and then select **Restore**.</span></span> 
    
3. <span data-ttu-id="8502d-148">在 "**还原**" 页上，按照说明设置密码并选择 "**还原**"。</span><span class="sxs-lookup"><span data-stu-id="8502d-148">On the **Restore** page, follow the instructions to set the password and select **Restore**.</span></span> <span data-ttu-id="8502d-149">将从要还原的用户自动删除任何冲突的代理地址。</span><span class="sxs-lookup"><span data-stu-id="8502d-149">Any conflicting proxy addresses are automatically removed from the user you are restoring.</span></span>
    
4. <span data-ttu-id="8502d-150">查看结果，然后选择" **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="8502d-150">Review the results, and then select **Close**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8502d-151">相关文章</span><span class="sxs-lookup"><span data-stu-id="8502d-151">Related articles</span></span>

[<span data-ttu-id="8502d-152">删除用户</span><span class="sxs-lookup"><span data-stu-id="8502d-152">Delete a user</span></span>](delete-a-user.md)
  

