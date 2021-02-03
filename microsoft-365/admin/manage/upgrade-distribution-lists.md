---
title: 在 Outlook 中将通讯组列表升级到 Microsoft 365 组
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: 了解如何在 Outlook 中将一个或多个通讯组列表升级到 Microsoft 365 组，以及如何使用 PowerShell 同时升级多个通讯组列表。
ms.openlocfilehash: 95f887b4386b349dc9d8bb471deab19b5425f6f5
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080523"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="d8084-103">在 Outlook 中将通讯组列表升级到 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="d8084-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="d8084-104">可以使用 Outlook 将通讯组列表升级到 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="d8084-104">You can upgrade distribution lists to Microsoft 365 Groups with Outlook.</span></span> <span data-ttu-id="d8084-105">这是为组织的通讯组列表提供 Microsoft 365 组的所有特性和功能很好的方法。</span><span class="sxs-lookup"><span data-stu-id="d8084-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="d8084-106">为什么应将通讯组列表升级至 Outlook 中的组</span><span class="sxs-lookup"><span data-stu-id="d8084-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="d8084-107">可以一次升级一个 DLS，也可以同时升级多个 DLS。</span><span class="sxs-lookup"><span data-stu-id="d8084-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="d8084-108">在 Outlook 中将一个或多个通讯组列表升级到 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="d8084-108">Upgrade one or many distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="d8084-109">您必须是全局管理员或 Exchange 管理员才能升级通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="d8084-109">You must be a global admin or Exchange admin to upgrade a distribution list.</span></span> <span data-ttu-id="d8084-110">若要升级到 Microsoft 365 组，通讯组必须具有具有邮箱的所有者。</span><span class="sxs-lookup"><span data-stu-id="d8084-110">To upgrade to Microsoft 365 Groups, a distribution group must have an owner with a mailbox.</span></span>

1. <span data-ttu-id="d8084-111">转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="d8084-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="d8084-112">在 Exchange 管理中心，转到 **"收件人** \> **组"。**</span><span class="sxs-lookup"><span data-stu-id="d8084-112">In the Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="d8084-113">你将看到一条通知，指示你拥有一个 (也称为通讯组) 有资格升级到Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="d8084-113">You'll see a notice indicating you have distribution lists (also called **distribution groups** ) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="d8084-114">![选择"开始"按钮](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="d8084-114">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="d8084-115">Select one or more distribution lists (called a **distribution group )** from the **groups** page.</span><span class="sxs-lookup"><span data-stu-id="d8084-115">Select one or more distribution lists (also called a **distribution group** ) from the **groups** page.</span></span><br/><span data-ttu-id="d8084-116">![选择通讯组](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="d8084-116">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="d8084-117">选择升级图标。</span><span class="sxs-lookup"><span data-stu-id="d8084-117">Select the upgrade icon.</span></span><br/>![升级到 Microsoft 365 组图标](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="d8084-119">在信息对话框中，选择 **"是** "以确认升级。</span><span class="sxs-lookup"><span data-stu-id="d8084-119">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="d8084-120">该过程立即开始。</span><span class="sxs-lookup"><span data-stu-id="d8084-120">The process begins immediately.</span></span> <span data-ttu-id="d8084-121">根据要升级的 DLL 的大小和数量，此过程可能需要几分钟或数小时。</span><span class="sxs-lookup"><span data-stu-id="d8084-121">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="d8084-122">如果通讯组列表无法升级，则会显示一个对话框，</span><span class="sxs-lookup"><span data-stu-id="d8084-122">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="d8084-123">查看[哪些通讯组列表无法升级？。](#which-distribution-lists-cant-be-upgraded)</span><span class="sxs-lookup"><span data-stu-id="d8084-123">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cant-be-upgraded).</span></span>

6. <span data-ttu-id="d8084-124">如果要升级多个通讯组列表，请使用下拉列表筛选已升级的通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="d8084-124">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="d8084-125">如果列表不完整，请稍等一会，然后选择"刷新"以查看已成功升级哪些项。</span><span class="sxs-lookup"><span data-stu-id="d8084-125">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="d8084-126">系统不会通知你已完成所选所有 DLS 的升级过程。</span><span class="sxs-lookup"><span data-stu-id="d8084-126">There's no notice that tells you when the upgrade process has completed for all DLs you selected.</span></span> <span data-ttu-id="d8084-127">可以通过查看"可用于升级或升级的 DLS"下列出的项来 **了解这一点**。</span><span class="sxs-lookup"><span data-stu-id="d8084-127">You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="d8084-128">如果选择了 DL 进行升级，但仍在页面上显示为"可供升级"，则升级失败。</span><span class="sxs-lookup"><span data-stu-id="d8084-128">If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade.</span></span> <span data-ttu-id="d8084-129">请参阅 [升级不起作用时要执行哪些操作](#what-to-do-if-the-upgrade-doesnt-work)。</span><span class="sxs-lookup"><span data-stu-id="d8084-129">See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="d8084-130">如果你收到组摘要电子邮件，你可能会在底部注意到，有时它将提供，让你升级你作为所有者的任何符合条件的通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="d8084-130">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of.</span></span> <span data-ttu-id="d8084-131">有关 [摘要电子邮件详细信息](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) ，请参阅 Outlook 中的组对话。</span><span class="sxs-lookup"><span data-stu-id="d8084-131">See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span></span>

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="d8084-132">如果升级不起作用，该怎么办</span><span class="sxs-lookup"><span data-stu-id="d8084-132">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="d8084-133">无法升级的通讯组列表保持不变。</span><span class="sxs-lookup"><span data-stu-id="d8084-133">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="d8084-134">如果一个或多个符合条件的 **通讯** 组列表无法升级，请打开支持 [票证](../contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="d8084-134">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md).</span></span> <span data-ttu-id="d8084-135">需要将问题上报给组工程团队，让他们找出问题。</span><span class="sxs-lookup"><span data-stu-id="d8084-135">The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="d8084-136">由于服务中断，通讯组列表可能不会升级，但不太可能升级。</span><span class="sxs-lookup"><span data-stu-id="d8084-136">It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely.</span></span> <span data-ttu-id="d8084-137">如果需要，请稍等一下，然后再次尝试升级 DL。</span><span class="sxs-lookup"><span data-stu-id="d8084-137">If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="d8084-138">如何使用 PowerShell 同时升级多个通讯组列表</span><span class="sxs-lookup"><span data-stu-id="d8084-138">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="d8084-139">如果你在使用 PowerShell 方面有经验的，你可能希望转到此路由，而不是使用 UI。</span><span class="sxs-lookup"><span data-stu-id="d8084-139">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="d8084-140">我们具有一组 cmdlet，可帮助您升级通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="d8084-140">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="d8084-141">请参阅下文。</span><span class="sxs-lookup"><span data-stu-id="d8084-141">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="d8084-142">升级单个 DL</span><span class="sxs-lookup"><span data-stu-id="d8084-142">Upgrade a single DL</span></span>

<span data-ttu-id="d8084-143">若要升级单个 DL，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d8084-143">To upgrade a single DL run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
```

<span data-ttu-id="d8084-144">例如，如果要升级 SMTP 地址为 dl1@contoso.com的 DLS，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d8084-144">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
```

> [!NOTE]
> <span data-ttu-id="d8084-145">您还可以使用 [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet 将单个通讯组列表升级到 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="d8084-145">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="d8084-146">批量升级多个 DLL</span><span class="sxs-lookup"><span data-stu-id="d8084-146">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="d8084-147">还可以将多个 DLL 作为批处理传递并一起升级：</span><span class="sxs-lookup"><span data-stu-id="d8084-147">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="d8084-148">例如，如果要升级五个 SMTP 地址为 AND 的 DLS，并运行 `dl1@contoso.com` `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` 以下命令：</span><span class="sxs-lookup"><span data-stu-id="d8084-148">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="d8084-149">升级所有符合条件的 DLS</span><span class="sxs-lookup"><span data-stu-id="d8084-149">Upgrade all eligible DLs</span></span>

<span data-ttu-id="d8084-150">有两种方法可以升级所有符合条件的 DLS。</span><span class="sxs-lookup"><span data-stu-id="d8084-150">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="d8084-151">Upgrade-DistributionGroup cmdlet 不会从管道接收数据，因此，需要使用"foreach-object"运算符才能 {} 成功运行。</span><span class="sxs-lookup"><span data-stu-id="d8084-151">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="d8084-152">获取租户中的符合条件的 DLL，然后使用升级命令进行升级：</span><span class="sxs-lookup"><span data-stu-id="d8084-152">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="d8084-153">获取所有 DLL 的列表，并仅升级符合条件的 DLS：</span><span class="sxs-lookup"><span data-stu-id="d8084-153">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="d8084-154">有关在 Outlook 中将通讯组列表升级到 Microsoft 365 组的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="d8084-154">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cant-be-upgraded"></a><span data-ttu-id="d8084-155">哪些通讯组列表无法升级？</span><span class="sxs-lookup"><span data-stu-id="d8084-155">Which distribution lists can't be upgraded?</span></span>

<span data-ttu-id="d8084-156">只能升级云托管的简单非嵌套通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="d8084-156">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="d8084-157">下表列出了无法 **升级的** 通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="d8084-157">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="d8084-158">**属性**</span><span class="sxs-lookup"><span data-stu-id="d8084-158">**Property**</span></span>|<span data-ttu-id="d8084-159">**符合条件的？**</span><span class="sxs-lookup"><span data-stu-id="d8084-159">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d8084-160">本地托管通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="d8084-160">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="d8084-161">否</span><span class="sxs-lookup"><span data-stu-id="d8084-161">No</span></span>  <br/> |
|<span data-ttu-id="d8084-162">嵌套通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="d8084-162">Nested distribution lists.</span></span> <span data-ttu-id="d8084-163">通讯组列表有子组，或者是另一个组的成员。</span><span class="sxs-lookup"><span data-stu-id="d8084-163">Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="d8084-164">否</span><span class="sxs-lookup"><span data-stu-id="d8084-164">No</span></span>  <br/> |
|<span data-ttu-id="d8084-165">具有 **UserMailbox、SharedMailbox、TeamMailbox** **、MailUser** 的成员 **RecipientTypeDetails** 的通讯组列表</span><span class="sxs-lookup"><span data-stu-id="d8084-165">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="d8084-166">否</span><span class="sxs-lookup"><span data-stu-id="d8084-166">No</span></span>  <br/> |
|<span data-ttu-id="d8084-167">拥有 100 多个所有者的通讯组列表</span><span class="sxs-lookup"><span data-stu-id="d8084-167">Distribution list which has more than 100 owners</span></span>  <br/> |<span data-ttu-id="d8084-168">否</span><span class="sxs-lookup"><span data-stu-id="d8084-168">No</span></span>  <br/> |
|<span data-ttu-id="d8084-169">仅包含成员但没有所有者的通讯组列表</span><span class="sxs-lookup"><span data-stu-id="d8084-169">Distribution list which only has members but no owner</span></span>  <br/> |<span data-ttu-id="d8084-170">否</span><span class="sxs-lookup"><span data-stu-id="d8084-170">No</span></span>  <br/> |
|<span data-ttu-id="d8084-171">别名包含特殊字符的通讯组列表</span><span class="sxs-lookup"><span data-stu-id="d8084-171">Distribution list which has alias containing special characters</span></span>  <br/> |<span data-ttu-id="d8084-172">否</span><span class="sxs-lookup"><span data-stu-id="d8084-172">No</span></span>  <br/> |
|<span data-ttu-id="d8084-173">如果通讯组列表配置为共享邮箱的转发地址</span><span class="sxs-lookup"><span data-stu-id="d8084-173">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="d8084-174">否</span><span class="sxs-lookup"><span data-stu-id="d8084-174">No</span></span>  <br/> |
|<span data-ttu-id="d8084-175">如果 DL 是其他 DL **中的发件人限制的** 一部分。</span><span class="sxs-lookup"><span data-stu-id="d8084-175">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="d8084-176">否</span><span class="sxs-lookup"><span data-stu-id="d8084-176">No</span></span>  <br/> |
|<span data-ttu-id="d8084-177">安全组</span><span class="sxs-lookup"><span data-stu-id="d8084-177">Security groups</span></span>  <br/> |<span data-ttu-id="d8084-178">否</span><span class="sxs-lookup"><span data-stu-id="d8084-178">No</span></span>  <br/> |
|<span data-ttu-id="d8084-179">动态通讯组列表</span><span class="sxs-lookup"><span data-stu-id="d8084-179">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="d8084-180">否</span><span class="sxs-lookup"><span data-stu-id="d8084-180">No</span></span>  <br/> |
|<span data-ttu-id="d8084-181">已转换为 **RoomLists 的通讯组列表**</span><span class="sxs-lookup"><span data-stu-id="d8084-181">Distribution lists which were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="d8084-182">否</span><span class="sxs-lookup"><span data-stu-id="d8084-182">No</span></span>  <br/> |
|<span data-ttu-id="d8084-183">**MemberJoinRestriction** 和/或 **MemberDepartRestriction** 已关闭的 **通讯组列表**</span><span class="sxs-lookup"><span data-stu-id="d8084-183">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="d8084-184">否</span><span class="sxs-lookup"><span data-stu-id="d8084-184">No</span></span>  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="d8084-185">检查哪些 DLL 符合升级条件</span><span class="sxs-lookup"><span data-stu-id="d8084-185">Check which DLs are eligible for upgrade</span></span>

<span data-ttu-id="d8084-186">如果要检查 DL 是否符合条件，可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d8084-186">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="d8084-187">如果要检查哪些 DLL 符合升级条件，只需运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d8084-187">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="d8084-188">谁可以运行升级脚本？</span><span class="sxs-lookup"><span data-stu-id="d8084-188">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="d8084-189">具有全局管理员或 Exchange 管理员权限的用户。</span><span class="sxs-lookup"><span data-stu-id="d8084-189">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="d8084-190">为什么联系人卡片仍显示通讯组列表？</span><span class="sxs-lookup"><span data-stu-id="d8084-190">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="d8084-191">我应该如何阻止升级的通讯组列表显示在我的自动建议列表中？</span><span class="sxs-lookup"><span data-stu-id="d8084-191">What should I do to prevent a upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="d8084-192">对于 Outlook：当有人尝试在 Outlook 中发送电子邮件时，在迁移后键入 Microsoft 365 组名称，收件人将解析为通讯组列表而不是组。</span><span class="sxs-lookup"><span data-stu-id="d8084-192">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="d8084-193">收件人的联系人卡片将是通讯组列表联系人卡片。</span><span class="sxs-lookup"><span data-stu-id="d8084-193">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="d8084-194">这是因为 Outlook 中的收件人缓存或昵称缓存。</span><span class="sxs-lookup"><span data-stu-id="d8084-194">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="d8084-195">电子邮件将成功发送到组，但可能会导致发件人混淆。</span><span class="sxs-lookup"><span data-stu-id="d8084-195">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="d8084-196">可以执行本主题（Outlook 自动完成列表[](https://go.microsoft.com/fwlink/?LinkID=798736)信息）中的步骤来重置缓存，这将修复此问题。</span><span class="sxs-lookup"><span data-stu-id="d8084-196">You can perform the steps in this topic, [Information about the Outlook AutoComplete list](https://go.microsoft.com/fwlink/?LinkID=798736) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="d8084-197">对于 Outlook 网页：对于 Web 上的 Outlook，通讯组列表收件人仍将保留在缓存中。</span><span class="sxs-lookup"><span data-stu-id="d8084-197">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="d8084-198">可以按照"从自动完成[](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58)列表中删除建议的名称或电子邮件地址"中的步骤刷新缓存以查看组联系人卡片。</span><span class="sxs-lookup"><span data-stu-id="d8084-198">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="d8084-199">新组的成员是否收到收件箱中的欢迎电子邮件？</span><span class="sxs-lookup"><span data-stu-id="d8084-199">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="d8084-200">否。</span><span class="sxs-lookup"><span data-stu-id="d8084-200">No.</span></span> <span data-ttu-id="d8084-201">默认情况下，启用欢迎消息的设置设置为 false。</span><span class="sxs-lookup"><span data-stu-id="d8084-201">The setting to enable welcome messages is set to false by default.</span></span> <span data-ttu-id="d8084-202">此设置会影响迁移完成后可加入的现有和新的组的成员。</span><span class="sxs-lookup"><span data-stu-id="d8084-202">This setting affects both existing and new group members who may join after the migration is complete.</span></span> <span data-ttu-id="d8084-203">如果组所有者稍后允许来宾用户，来宾用户不会在收件箱中收到欢迎电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d8084-203">If the group owner later allows guest users, guest users won't receive a welcome email in their inbox.</span></span> <span data-ttu-id="d8084-204">来宾成员可以继续使用组。</span><span class="sxs-lookup"><span data-stu-id="d8084-204">Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="d8084-205">如果未升级一个或多个 DLL，将如何？</span><span class="sxs-lookup"><span data-stu-id="d8084-205">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="d8084-206">在某些情况下，虽然 DL 符合条件，但无法升级。</span><span class="sxs-lookup"><span data-stu-id="d8084-206">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="d8084-207">DL 不会升级并保留为 DL。</span><span class="sxs-lookup"><span data-stu-id="d8084-207">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="d8084-208">如果 **管理员为组织中** 各组应用了组电子邮件地址策略，并且他们尝试升级不满足条件的 DLS，则 DL 将不会升级</span><span class="sxs-lookup"><span data-stu-id="d8084-208">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs which doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="d8084-209">**MemberJoinRestriction 或** **MemberDepartRestriction** 设置为 **Closed** 的 DLS 无法升级</span><span class="sxs-lookup"><span data-stu-id="d8084-209">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="d8084-210">如果从 EAC 升级失败，DL 会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="d8084-210">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="d8084-211">只有在将呼叫提交到服务器时，才能进行升级。</span><span class="sxs-lookup"><span data-stu-id="d8084-211">The upgrade will happen only when the call is submitted to the server.</span></span> <span data-ttu-id="d8084-212">如果升级失败，则 DLL 将保持不变。</span><span class="sxs-lookup"><span data-stu-id="d8084-212">If the upgrade fails, your DLs will be intact.</span></span> <span data-ttu-id="d8084-213">他们将像以前一样工作。</span><span class="sxs-lookup"><span data-stu-id="d8084-213">They will work like they used to.</span></span>
