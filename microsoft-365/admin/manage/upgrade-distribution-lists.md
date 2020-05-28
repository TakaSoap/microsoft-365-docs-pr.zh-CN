---
title: 将通讯组列表升级到 Outlook 中的 Microsoft 365 组
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
description: 了解如何将一个或多个通讯组列表升级到 Outlook 中的 Microsoft 365 组，以及如何使用 PowerShell 同时升级多个通讯组列表。
ms.openlocfilehash: cac0232b721c07ce8e07c7b101e0313eb9cd91df
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399490"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="b9a05-103">将通讯组列表升级到 Outlook 中的 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="b9a05-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="b9a05-104">您可以使用 Outlook 将通讯组列表升级到 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="b9a05-104">You can upgrade distribution lists to Microsoft 365 Groups with Outlook.</span></span> <span data-ttu-id="b9a05-105">这是为组织的通讯组提供 Microsoft 365 组的所有特性和功能的好方法。</span><span class="sxs-lookup"><span data-stu-id="b9a05-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="b9a05-106">为什么应将通讯组列表升级至 Outlook 中的组</span><span class="sxs-lookup"><span data-stu-id="b9a05-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/en-us/office/why-you-should-upgrade-your-distribution-lists-to-groups-in-outlook-7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="b9a05-107">您可以一次升级一个 DLs，也可以同时升级多个。</span><span class="sxs-lookup"><span data-stu-id="b9a05-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="b9a05-108">在 Outlook 中将一个或多个通讯组列表升级到 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="b9a05-108">Upgrade one or many distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="b9a05-109">您必须是全局管理员或 Exchange 管理员才能升级通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b9a05-109">You must be a global admin or Exchange admin to upgrade a distribution list.</span></span> <span data-ttu-id="b9a05-110">若要升级到 Microsoft 365 组，通讯组必须具有邮箱所有者。</span><span class="sxs-lookup"><span data-stu-id="b9a05-110">To upgrade to Microsoft 365 Groups, a distribution group must have an owner with a mailbox.</span></span> 

1. <span data-ttu-id="b9a05-111">转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="b9a05-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="b9a05-112">在 Exchange 管理中心中，转到 "**收件人** \> **组**"。</span><span class="sxs-lookup"><span data-stu-id="b9a05-112">In the Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="b9a05-113">你将看到一则通知，指示你具有可升级到 Microsoft 365 组的通讯组列表（也称为**通讯组**）。</span><span class="sxs-lookup"><span data-stu-id="b9a05-113">You'll see a notice indicating you have distribution lists (also called **distribution groups** ) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="b9a05-114">![选择 "开始入门" 按钮](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="b9a05-114">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="b9a05-115">从 "**组**" 页面中选择一个或多个通讯组列表（也称为**通讯组**）。</span><span class="sxs-lookup"><span data-stu-id="b9a05-115">Select one or more distribution lists (also called a **distribution group** ) from the **groups** page.</span></span><br/><span data-ttu-id="b9a05-116">![选择通讯组](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="b9a05-116">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="b9a05-117">选择 "升级" 图标。</span><span class="sxs-lookup"><span data-stu-id="b9a05-117">Select the upgrade icon.</span></span><br/>!["升级到 Microsoft 365 组" 图标](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="b9a05-119">在 "信息" 对话框中，选择 **"是"** 以确认升级。</span><span class="sxs-lookup"><span data-stu-id="b9a05-119">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="b9a05-120">该过程将立即开始。</span><span class="sxs-lookup"><span data-stu-id="b9a05-120">The process begins immediately.</span></span> <span data-ttu-id="b9a05-121">此过程可能需要几分钟或几小时，具体取决于您要升级的 Dl 的大小和数量。</span><span class="sxs-lookup"><span data-stu-id="b9a05-121">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="b9a05-122">如果无法升级通讯组列表，则会显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="b9a05-122">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="b9a05-123">查看[哪些通讯组列表无法升级？](#which-distribution-lists-cannot-be-upgraded)。</span><span class="sxs-lookup"><span data-stu-id="b9a05-123">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cannot-be-upgraded).</span></span>

6. <span data-ttu-id="b9a05-124">如果要升级多个通讯组列表，请使用下拉列表筛选已升级的通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b9a05-124">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="b9a05-125">如果列表未完成，请等待一段时间，然后选择 "**刷新**" 以查看已成功升级的内容。</span><span class="sxs-lookup"><span data-stu-id="b9a05-125">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="b9a05-126">不会通知你选择的所有 Dl 的升级过程完成后。</span><span class="sxs-lookup"><span data-stu-id="b9a05-126">There's no notice that tells you when the upgrade process has completed for all DLs you selected.</span></span> <span data-ttu-id="b9a05-127">您可以通过查看 "**可用于升级**或**升级的 dl**" 下列出的内容来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="b9a05-127">You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="b9a05-128">如果选择了 DL 进行升级，但它在页面上仍显示为可升级，则升级失败。</span><span class="sxs-lookup"><span data-stu-id="b9a05-128">If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade.</span></span> <span data-ttu-id="b9a05-129">[如果升级不起作用，请查看要执行的操作](#what-to-do-if-the-upgrade-doesnt-work)。</span><span class="sxs-lookup"><span data-stu-id="b9a05-129">See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="b9a05-130">如果你正在获取组摘要电子邮件，你可能会注意到，有时会通过它来升级你是其所有者的任何符合条件的通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b9a05-130">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of.</span></span> <span data-ttu-id="b9a05-131">有关摘要电子邮件的详细信息，请参阅[在 Outlook 中有组对话](https://support.microsoft.com/en-us/office/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22)。</span><span class="sxs-lookup"><span data-stu-id="b9a05-131">See [Have a group conversation in Outlook](https://support.microsoft.com/en-us/office/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span></span>


## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="b9a05-132">如果升级不起作用，该怎么办</span><span class="sxs-lookup"><span data-stu-id="b9a05-132">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="b9a05-133">无法升级的通讯组列表保持不变。</span><span class="sxs-lookup"><span data-stu-id="b9a05-133">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="b9a05-134">如果一个或多个**符合条件**的通讯组列表升级失败，请打开[支持票证](../contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="b9a05-134">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md).</span></span> <span data-ttu-id="b9a05-135">需要将问题升级至组工程团队，以确定问题所在。</span><span class="sxs-lookup"><span data-stu-id="b9a05-135">The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="b9a05-136">由于服务中断，通讯组列表可能未升级，但很少出现。</span><span class="sxs-lookup"><span data-stu-id="b9a05-136">It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely.</span></span> <span data-ttu-id="b9a05-137">如果需要，请等待一段时间，然后再次尝试升级 DL。</span><span class="sxs-lookup"><span data-stu-id="b9a05-137">If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="b9a05-138">如何使用 PowerShell 同时升级多个通讯组列表</span><span class="sxs-lookup"><span data-stu-id="b9a05-138">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="b9a05-139">如果您在使用 PowerShell 时遇到了经验，您可能希望转而不是使用 UI 来转到此路由。</span><span class="sxs-lookup"><span data-stu-id="b9a05-139">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="b9a05-140">我们有一组 cmdlet，可帮助您升级通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b9a05-140">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="b9a05-141">请参阅下文。</span><span class="sxs-lookup"><span data-stu-id="b9a05-141">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="b9a05-142">升级单个 DL</span><span class="sxs-lookup"><span data-stu-id="b9a05-142">Upgrade a single DL</span></span>

<span data-ttu-id="b9a05-143">若要升级单个 DL，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b9a05-143">To upgrade a single DL run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`

<span data-ttu-id="b9a05-144">例如，如果您想要使用 SMTP 地址 dl1@contoso.com 升级 Dl，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b9a05-144">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`

> [!NOTE]
> <span data-ttu-id="b9a05-145">您还可以使用[Remove-unifiedgroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet 将单个通讯组列表升级到 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="b9a05-145">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="b9a05-146">在批处理中升级多个 Dl</span><span class="sxs-lookup"><span data-stu-id="b9a05-146">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="b9a05-147">您还可以将多个 Dl 作为批处理传递，并将它们升级到一起：</span><span class="sxs-lookup"><span data-stu-id="b9a05-147">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,

\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="b9a05-148">例如，如果要升级5个使用 SMTP 地址的 dl， `dl1@contoso.com` 和、和，请 `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` 运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b9a05-148">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="b9a05-149">升级所有符合条件的 Dl</span><span class="sxs-lookup"><span data-stu-id="b9a05-149">Upgrade all eligible DLs</span></span>

<span data-ttu-id="b9a05-150">可以通过两种方式升级所有符合条件的 Dl。</span><span class="sxs-lookup"><span data-stu-id="b9a05-150">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="b9a05-151">New-distributiongroup cmdlet 不接收管道中的数据，因此，必须使用 "foreach-object {} " 运算符才能成功运行。</span><span class="sxs-lookup"><span data-stu-id="b9a05-151">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="b9a05-152">在租户中获取符合条件的 Dl 并使用升级命令对其进行升级：</span><span class="sxs-lookup"><span data-stu-id="b9a05-152">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="b9a05-153">获取所有 Dl 的列表并仅升级符合条件的 Dl：</span><span class="sxs-lookup"><span data-stu-id="b9a05-153">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="b9a05-154">有关将通讯组列表升级到 Outlook 中的 Microsoft 365 组的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="b9a05-154">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cannot-be-upgraded"></a><span data-ttu-id="b9a05-155">哪些通讯组列表无法升级？</span><span class="sxs-lookup"><span data-stu-id="b9a05-155">Which distribution lists cannot be upgraded?</span></span>

<span data-ttu-id="b9a05-156">您只能升级云管理、简单、非嵌套的通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b9a05-156">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="b9a05-157">下表列出了**无法**升级的通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b9a05-157">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="b9a05-158">**Property**</span><span class="sxs-lookup"><span data-stu-id="b9a05-158">**Property**</span></span>|<span data-ttu-id="b9a05-159">**退税?**</span><span class="sxs-lookup"><span data-stu-id="b9a05-159">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b9a05-160">内部部署管理通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b9a05-160">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="b9a05-161">否</span><span class="sxs-lookup"><span data-stu-id="b9a05-161">No</span></span>  <br/> |
|<span data-ttu-id="b9a05-162">嵌套的通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b9a05-162">Nested distribution lists.</span></span> <span data-ttu-id="b9a05-163">通讯组列表具有子组或是另一个组的成员。</span><span class="sxs-lookup"><span data-stu-id="b9a05-163">Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="b9a05-164">否</span><span class="sxs-lookup"><span data-stu-id="b9a05-164">No</span></span>  <br/> |
|<span data-ttu-id="b9a05-165">具有除**UserMailbox**、 **SharedMailbox**、 **TeamMailbox**、 **MailUser**之外的 member **RecipientTypeDetails**的通讯组列表</span><span class="sxs-lookup"><span data-stu-id="b9a05-165">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="b9a05-166">否</span><span class="sxs-lookup"><span data-stu-id="b9a05-166">No</span></span>  <br/> |
|<span data-ttu-id="b9a05-167">包含超过100个所有者的通讯组列表</span><span class="sxs-lookup"><span data-stu-id="b9a05-167">Distribution list which has more than 100 owners</span></span>  <br/> |<span data-ttu-id="b9a05-168">否</span><span class="sxs-lookup"><span data-stu-id="b9a05-168">No</span></span>  <br/> |
|<span data-ttu-id="b9a05-169">仅包含成员但没有所有者的通讯组列表</span><span class="sxs-lookup"><span data-stu-id="b9a05-169">Distribution list which only has members but no owner</span></span>  <br/> |<span data-ttu-id="b9a05-170">否</span><span class="sxs-lookup"><span data-stu-id="b9a05-170">No</span></span>  <br/> |
|<span data-ttu-id="b9a05-171">包含特殊字符别名的通讯组列表</span><span class="sxs-lookup"><span data-stu-id="b9a05-171">Distribution list which has alias containing special characters</span></span>  <br/> |<span data-ttu-id="b9a05-172">否</span><span class="sxs-lookup"><span data-stu-id="b9a05-172">No</span></span>  <br/> |
|<span data-ttu-id="b9a05-173">如果将通讯组列表配置为共享邮箱的转发地址</span><span class="sxs-lookup"><span data-stu-id="b9a05-173">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="b9a05-174">否</span><span class="sxs-lookup"><span data-stu-id="b9a05-174">No</span></span>  <br/> |
|<span data-ttu-id="b9a05-175">如果 DL 是另一个 DL 中的**发件人限制**的一部分。</span><span class="sxs-lookup"><span data-stu-id="b9a05-175">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="b9a05-176">否</span><span class="sxs-lookup"><span data-stu-id="b9a05-176">No</span></span>  <br/> |
|<span data-ttu-id="b9a05-177">安全组</span><span class="sxs-lookup"><span data-stu-id="b9a05-177">Security groups</span></span>  <br/> |<span data-ttu-id="b9a05-178">否</span><span class="sxs-lookup"><span data-stu-id="b9a05-178">No</span></span>  <br/> |
|<span data-ttu-id="b9a05-179">动态通讯组列表</span><span class="sxs-lookup"><span data-stu-id="b9a05-179">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="b9a05-180">否</span><span class="sxs-lookup"><span data-stu-id="b9a05-180">No</span></span>  <br/> |
|<span data-ttu-id="b9a05-181">转换为**RoomLists**的通讯组列表</span><span class="sxs-lookup"><span data-stu-id="b9a05-181">Distribution lists which were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="b9a05-182">否</span><span class="sxs-lookup"><span data-stu-id="b9a05-182">No</span></span>  <br/> |
|<span data-ttu-id="b9a05-183">**MemberJoinRestriction**和/或**MemberDepartRestriction** **关闭**的通讯组列表</span><span class="sxs-lookup"><span data-stu-id="b9a05-183">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="b9a05-184">否</span><span class="sxs-lookup"><span data-stu-id="b9a05-184">No</span></span>  <br/> |

### <a name="how-do-i-check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="b9a05-185">如何检查哪些 Dl 有资格进行升级？</span><span class="sxs-lookup"><span data-stu-id="b9a05-185">How do I check which DLs are eligible for upgrade?</span></span>

<span data-ttu-id="b9a05-186">如果要检查 DL 是否符合条件，可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b9a05-186">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="b9a05-187">如果要检查哪些 Dl 有资格进行升级，只需运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b9a05-187">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="b9a05-188">谁可以运行升级脚本？</span><span class="sxs-lookup"><span data-stu-id="b9a05-188">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="b9a05-189">具有全局管理员或 Exchange 管理员权限的人员。</span><span class="sxs-lookup"><span data-stu-id="b9a05-189">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="b9a05-190">为什么联系人卡片仍显示通讯组列表？</span><span class="sxs-lookup"><span data-stu-id="b9a05-190">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="b9a05-191">若要阻止已升级的通讯组列表显示在我的自动建议列表中，我该怎么办？</span><span class="sxs-lookup"><span data-stu-id="b9a05-191">What should I do to prevent a upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="b9a05-192">对于 Outlook：如果有人尝试在迁移后键入 Microsoft 365 组名称来在 Outlook 中发送电子邮件，则收件人将解析为通讯组列表，而不是组。</span><span class="sxs-lookup"><span data-stu-id="b9a05-192">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="b9a05-193">收件人的联系人卡片将是通讯组列表联系人卡片。</span><span class="sxs-lookup"><span data-stu-id="b9a05-193">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="b9a05-194">这是因为 Outlook 中的收件人缓存或 nick 名称缓存。</span><span class="sxs-lookup"><span data-stu-id="b9a05-194">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="b9a05-195">电子邮件将成功发送到组，但可能会导致发件人混淆。</span><span class="sxs-lookup"><span data-stu-id="b9a05-195">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="b9a05-196">您可以执行本主题中的步骤，[有关 Outlook 自动完成列表的信息](https://go.microsoft.com/fwlink/?LinkID=798736)，以重置缓存，这将修复此问题。</span><span class="sxs-lookup"><span data-stu-id="b9a05-196">You can perform the steps in this topic, [Information about the Outlook AutoComplete list](https://go.microsoft.com/fwlink/?LinkID=798736) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="b9a05-197">对于 web 上的 Outlook：在 Outlook 网页版中，通讯组列表收件人仍将保留在缓存中。</span><span class="sxs-lookup"><span data-stu-id="b9a05-197">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="b9a05-198">您可以按照 "[删除建议的名称" 或 "自动完成" 列表中的电子邮件地址](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx)中的步骤操作，以刷新缓存以查看组联系人卡片。</span><span class="sxs-lookup"><span data-stu-id="b9a05-198">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="b9a05-199">新组成员是否可在其收件箱中获取欢迎电子邮件？</span><span class="sxs-lookup"><span data-stu-id="b9a05-199">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="b9a05-200">否。</span><span class="sxs-lookup"><span data-stu-id="b9a05-200">No.</span></span> <span data-ttu-id="b9a05-201">默认情况下，启用欢迎邮件的设置设置为 false。</span><span class="sxs-lookup"><span data-stu-id="b9a05-201">The setting to enable welcome messages is set to false by default.</span></span> <span data-ttu-id="b9a05-202">此设置会影响在迁移完成后可能加入的现有和新组成员。</span><span class="sxs-lookup"><span data-stu-id="b9a05-202">This setting affects both existing and new group members who may join after the migration is complete.</span></span> <span data-ttu-id="b9a05-203">如果组所有者稍后允许来宾用户，则来宾用户不会在其收件箱中收到欢迎电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b9a05-203">If the group owner later allows guest users, guest users won't receive a welcome email in their inbox.</span></span> <span data-ttu-id="b9a05-204">来宾成员可以继续使用该组。</span><span class="sxs-lookup"><span data-stu-id="b9a05-204">Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="b9a05-205">如果一个或多个 Dl 未升级，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="b9a05-205">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="b9a05-206">在某些情况下，虽然 DL 符合条件，但无法升级。</span><span class="sxs-lookup"><span data-stu-id="b9a05-206">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="b9a05-207">DL 不会升级且仍保留为 DL。</span><span class="sxs-lookup"><span data-stu-id="b9a05-207">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="b9a05-208">在组织中，管理员已为组织中的组应用了**组电子邮件地址策略**，并尝试升级无法满足条件的 DLS，DL 不会进行升级</span><span class="sxs-lookup"><span data-stu-id="b9a05-208">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs which doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="b9a05-209">无法升级**MemberJoinRestriction**或**MemberDepartRestriction**设置为 "**已关闭**" 的 dl</span><span class="sxs-lookup"><span data-stu-id="b9a05-209">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="b9a05-210">如果从 EAC 升级失败，DL 会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="b9a05-210">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="b9a05-211">仅在将呼叫提交到服务器时，才会进行升级。</span><span class="sxs-lookup"><span data-stu-id="b9a05-211">The upgrade will happen only when the call is submitted to the server.</span></span> <span data-ttu-id="b9a05-212">如果升级失败，你的 Dl 将保持不变。</span><span class="sxs-lookup"><span data-stu-id="b9a05-212">If the upgrade fails, your DLs will be intact.</span></span> <span data-ttu-id="b9a05-213">它们的工作方式类似于使用它们。</span><span class="sxs-lookup"><span data-stu-id="b9a05-213">They will work like they used to.</span></span>


