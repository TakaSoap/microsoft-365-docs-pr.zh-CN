---
title: 管理 EOP 中的管理员角色组权限
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 管理员可以了解如何在 Exchange Online Protection 中分配或删除 Exchange 管理中心（EAC）中的权限。
ms.openlocfilehash: 9b82836b5f9f28c3055e540890771def28382d2b
ms.sourcegitcommit: 84d88a857e82b1a8a0d466057a2e330e8b1692e4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "37306126"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a><span data-ttu-id="8bfe1-103">在 EOP 中管理管理员角色组权限</span><span class="sxs-lookup"><span data-stu-id="8bfe1-103">Manage admin role group permissions in EOP</span></span>

<span data-ttu-id="8bfe1-p101">在 Microsoft Exchange Online Protection (EOP) 中，您可以使用 Exchange 管理中心 (EAC) 让用户成为一个或多个角色组的成员，以便为他们分配执行特定管理任务所需的权限。您还可以使用 EAC 将用户从一个或多个角色组中删除。</span><span class="sxs-lookup"><span data-stu-id="8bfe1-p101">In Microsoft Exchange Online Protection (EOP), you can use the Exchange admin center (EAC) to make a user a member of a role group or groups in order to assign them permissions to perform specific administrative tasks. You can also remove a user from a role group or groups by using the EAC.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8bfe1-106">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="8bfe1-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8bfe1-107">估计完成时间：5-10 分钟</span><span class="sxs-lookup"><span data-stu-id="8bfe1-107">Estimated time to complete: 5-10 minutes</span></span>

- <span data-ttu-id="8bfe1-108">若要打开 Exchange 管理中心，请参阅 exchange [Online Protection 中的 exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="8bfe1-108">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="8bfe1-p102">您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"用户、联系人和角色组"条目。</span><span class="sxs-lookup"><span data-stu-id="8bfe1-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="8bfe1-111">有关可能适用于本主题中的过程的键盘快捷方式的信息，请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="8bfe1-111">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="8bfe1-112">是否有任何疑问？</span><span class="sxs-lookup"><span data-stu-id="8bfe1-112">Having problems?</span></span> <span data-ttu-id="8bfe1-113">在[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)论坛中寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="8bfe1-113">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a><span data-ttu-id="8bfe1-114">使用 EAC 向管理员角色组分配成员</span><span class="sxs-lookup"><span data-stu-id="8bfe1-114">Use the EAC to assign members to admin role groups</span></span>

1. <span data-ttu-id="8bfe1-115">在 EAC 中，转到 "**权限** \> " "**管理员角色**"，单击要向其添加用户的角色组，然后单击 "**编辑** ![编辑图标](../media/ITPro-EAC-EditIcon.gif)"。</span><span class="sxs-lookup"><span data-stu-id="8bfe1-115">In the EAC, go to **Permissions** \> **Admin roles**, click the role group that you want to add the user or users to, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="8bfe1-116">在 "成员" \*\*\*\* ![下，单击](../media/ITPro-EAC-AddIcon.gif)"添加" "添加" 图标。</span><span class="sxs-lookup"><span data-stu-id="8bfe1-116">Under Members, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="8bfe1-117">将显示"选择成员"窗口。</span><span class="sxs-lookup"><span data-stu-id="8bfe1-117">The Select Members window will appear.</span></span>

3. <span data-ttu-id="8bfe1-118">搜索您要添加的一个或多个用户，或从列表中选择。</span><span class="sxs-lookup"><span data-stu-id="8bfe1-118">Search for the user or users that you wish to add, or select them from the list.</span></span>

4. <span data-ttu-id="8bfe1-p105">选择您要添加的一个或多个用户后，单击“添加”\*\*\*\*，然后单击“确定”\*\*\*\*。“选择成员”窗口将会关闭。</span><span class="sxs-lookup"><span data-stu-id="8bfe1-p105">When you have selected the user or users that you want to add, click **Add**, and then click **OK**. The Select Members window will close.</span></span>

5. <span data-ttu-id="8bfe1-p106">您会看到用户已经添加到“成员”\*\*\*\* 窗格。单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8bfe1-p106">You will see that the user has been added to the **Members** pane. Click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8bfe1-123">在角色组中添加或删除成员后，用户可能必须先注销，然后重新登录才会看到其管理权限的更改。</span><span class="sxs-lookup"><span data-stu-id="8bfe1-123">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

## <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a><span data-ttu-id="8bfe1-124">使用 EAC 从管理员角色组中删除成员</span><span class="sxs-lookup"><span data-stu-id="8bfe1-124">Use the EAC to remove members from admin role groups</span></span>

1. <span data-ttu-id="8bfe1-125">在 EAC 中，转到 "**权限** \> " "**管理员角色**"，单击要从中删除一个或一组用户的角色组，然后单击 "**编辑** ![编辑图标](../media/ITPro-EAC-EditIcon.gif)"。</span><span class="sxs-lookup"><span data-stu-id="8bfe1-125">In the EAC, go to **Permissions** \> **Admin Roles**, click the role group that you want to remove a user or users from, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="8bfe1-126">在 "成员" 下，选择要删除的一个或一或一些\*\*\*\* ![用户，然后](../media/ITPro-EAC-RemoveIcon.gif)单击 "删除删除图标"。</span><span class="sxs-lookup"><span data-stu-id="8bfe1-126">Under Members, select the user or users that you want to remove and click **Remove** ![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="8bfe1-127">单击“保存”\*\*\*\* 将更改保存到角色组并返回“管理员角色”\*\*\*\* 页。</span><span class="sxs-lookup"><span data-stu-id="8bfe1-127">Click **Save** to save the change to the role group and return to the **Admin Roles** page.</span></span> <span data-ttu-id="8bfe1-128">若要验证您已成功从管理员角色组删除用户，确保该用户不会再出现在选定角色组详细信息窗格中的"成员"下。</span><span class="sxs-lookup"><span data-stu-id="8bfe1-128">To verify that you've successfully removed the user from the administrator role group, make sure the member is no longer displayed under Members in the details pane for the selected role group.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8bfe1-129">在角色组中添加或删除成员后，用户可能必须先注销，然后重新登录才会看到其管理权限的更改。</span><span class="sxs-lookup"><span data-stu-id="8bfe1-129">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="8bfe1-130">详细信息</span><span class="sxs-lookup"><span data-stu-id="8bfe1-130">For more information</span></span>

[<span data-ttu-id="8bfe1-131">EOP 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="8bfe1-131">Feature permissions in EOP</span></span>](feature-permissions-in-eop.md)
