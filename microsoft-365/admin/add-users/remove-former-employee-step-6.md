---
title: 步骤 6 - 从以前的员工删除和删除 Microsoft 365 许可证
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
description: 按照以下步骤从以前的员工删除 Microsoft 365 许可证。
ms.openlocfilehash: ed86eb28cc6d4996f7def8cb567f0e4085e67624
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244164"
---
# <a name="step-6---remove-the-microsoft-365-license-from-a-former-employee"></a><span data-ttu-id="b9d3e-103">步骤 6 - 从以前的员工删除 Microsoft 365 许可证</span><span class="sxs-lookup"><span data-stu-id="b9d3e-103">Step 6 - Remove the Microsoft 365 license from a former employee</span></span>

<span data-ttu-id="b9d3e-104">如果某人离开组织后不想支付许可证费用，则需要删除其 Microsoft 365 许可证，然后从订阅中删除它。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-104">If you don't want to pay for a license after someone leaves your organization, you need to remove their Microsoft 365 license and then delete it from your subscription.</span></span> <span data-ttu-id="b9d3e-105">如果不删除许可证，可以将许可证分配给其他用户。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-105">You can assign a license to another user if you don't delete it.</span></span>
  
<span data-ttu-id="b9d3e-106">删除许可证后，该用户的所有数据将保留 30 天。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-106">When you remove the license, all that user's data is held for 30 days.</span></span> <span data-ttu-id="b9d3e-107">可[访问](get-access-to-and-back-up-a-former-user-s-data.md)该数据，或在用户返回时[还原](restore-user.md)该帐户。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-107">You can [access](get-access-to-and-back-up-a-former-user-s-data.md) the data, or [restore](restore-user.md) the account if the user comes back.</span></span> <span data-ttu-id="b9d3e-108">30 天后，用户的所有数据 (存储在 SharePoint Online) 上的文档除外）将从 Microsoft 365 中永久删除，并且无法恢复。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-108">After 30 days, all the user's data (except for documents stored on SharePoint Online) is permanently deleted from Microsoft 365 and can't be recovered.</span></span>

1. <span data-ttu-id="b9d3e-109">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="b9d3e-110">选择要阻止的员工的姓名，然后选择"许可证 **和应用"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-110">Select the name of the employee that you want to block, and then select the **Licenses and Apps** tab.</span></span>
3. <span data-ttu-id="b9d3e-111">清除要删除 (许可证) 复选框，然后选择"保存 **更改"。**</span><span class="sxs-lookup"><span data-stu-id="b9d3e-111">Clear the check boxes for the license(s) you want to remove, and then select **Save changes**.</span></span>

<span data-ttu-id="b9d3e-112">**若要在聘用** 其他人之前减少你支付的许可证数量，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b9d3e-112">**To reduce the number of licenses you're paying for** until you hire another person, do the following steps:</span></span>

1. <span data-ttu-id="b9d3e-113">在管理中心，转到" **帐单** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">""产品"页面</a> ，然后选择" **产品"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-113">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page, and select the **Products** tab.</span></span>
2. <span data-ttu-id="b9d3e-114">选择要从中删除许可证的订阅。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-114">Select the subscription from which you want to remove licenses.</span></span>
3. <span data-ttu-id="b9d3e-115">在详细信息页面上，选择删除 **许可证**。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-115">On the details page, select **Remove licenses**.</span></span>
4. <span data-ttu-id="b9d3e-116">在"**删除许可证"** 窗格中的"新数量"下的"许可证总数"框中，输入此订阅的许可证总数。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-116">In the **Remove licenses** pane, under New quantity, in the **Total licenses** box, enter the total number of licenses that you want for this subscription.</span></span> <span data-ttu-id="b9d3e-117">例如，如果你有 25 个许可证，并且想要删除其中一个许可证，请输入 24。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-117">For example, if you have 25 licenses and you want to remove one of them, enter 24.</span></span>
5. <span data-ttu-id="b9d3e-118">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-118">Select **Save**.</span></span>

<span data-ttu-id="b9d3e-119">向 [企业添加其他人](add-users.md) 时，系统会提示你同时购买许可证，只需一个步骤！</span><span class="sxs-lookup"><span data-stu-id="b9d3e-119">When you [add another person](add-users.md) to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

<span data-ttu-id="b9d3e-120">有关管理 Microsoft 365 商业版用户许可证的信息，请参阅在 [Microsoft 365](../manage/assign-licenses-to-users.md)商业版 中向用户分配许可证和取消分配 [Microsoft 365](../manage/remove-licenses-from-users.md)商业版中的用户许可证。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-120">For more information about managing user licenses for Microsoft 365 for business, see [Assign licenses to users in Microsoft 365 for business](../manage/assign-licenses-to-users.md), and [Unassign licenses from users in Microsoft 365 for business](../manage/remove-licenses-from-users.md).</span></span>
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a><span data-ttu-id="b9d3e-121">已删除的员工帐户如何影响 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b9d3e-121">How the deleted employee account affects Skype for Business</span></span>

<span data-ttu-id="b9d3e-p104">从 Office 365 删除用户许可证时，与该用户相关联的 PSTN 呼叫号码将被释放。可将其分配给其他用户。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-p104">When you remove a user's license from Office 365, the PSTN calling number associated with the user will be released. You can assign it to another user.</span></span>
  
<span data-ttu-id="b9d3e-p105">如果用户属于队列组，则他不再是呼叫队列代理的可行目标。因此，我们还建议将该用户从与呼叫队列相关联的组中删除。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-p105">If the user belongs to a queue group, they will no longer be a viable target of the call queue agents. So, we recommend also removing the user from the groups associated with the call queue.</span></span>

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a><span data-ttu-id="b9d3e-126">设置呼叫转发给组织人员</span><span class="sxs-lookup"><span data-stu-id="b9d3e-126">Set up call forwarding to people in your organization</span></span>

<span data-ttu-id="b9d3e-127">如果需要为离职员工的电话号码设置呼叫转发，呼叫策略下的呼叫转发设置可以设置转发，其中传入呼叫可以转发给其他用户，也可以同时呼叫其他人。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-127">If you need to set up call forwarding for the terminated employee's phone number, the call forwarding setting under calling policies can set up forwarding where incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> <span data-ttu-id="b9d3e-128">有关详细信息，请参阅 [Microsoft Teams 中的通话策略](/microsoftteams/teams-calling-policy)。</span><span class="sxs-lookup"><span data-stu-id="b9d3e-128">For more information, see [Calling policies in Microsoft Teams](/microsoftteams/teams-calling-policy).</span></span>
