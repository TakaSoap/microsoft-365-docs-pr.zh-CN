---
title: 将通讯组列表Microsoft 365组Outlook
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: 了解如何将一个或多个通讯组列表升级到 Microsoft 365 中的Outlook，以及如何使用 PowerShell 同时升级多个通讯组列表。
ms.openlocfilehash: 8179937cafa26a2258f67baee29fcec65bd60632
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332446"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="dece1-103">将通讯组列表Microsoft 365组Outlook</span><span class="sxs-lookup"><span data-stu-id="dece1-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="dece1-104">可以将通讯组列表升级到Microsoft 365组Outlook。</span><span class="sxs-lookup"><span data-stu-id="dece1-104">You can upgrade distribution lists to Microsoft 365 Groups in Outlook.</span></span> <span data-ttu-id="dece1-105">这是为组织的通讯组列表提供组组的所有特性Microsoft 365方式。</span><span class="sxs-lookup"><span data-stu-id="dece1-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="dece1-106">为什么应将通讯组列表升级至 Outlook 中的组</span><span class="sxs-lookup"><span data-stu-id="dece1-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="dece1-107">可以一次升级一个 DLL，也可以同时升级多个 DLS。</span><span class="sxs-lookup"><span data-stu-id="dece1-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="dece1-108">将一个或多个通讯组列表组升级到Microsoft 365组Outlook</span><span class="sxs-lookup"><span data-stu-id="dece1-108">Upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="dece1-109">您必须是全局管理员或Exchange才能升级通讯组列表组。</span><span class="sxs-lookup"><span data-stu-id="dece1-109">You must be a global admin or Exchange admin to upgrade a distribution list group.</span></span> <span data-ttu-id="dece1-110">若要升级到Microsoft 365组，通讯组列表组必须具有具有邮箱的所有者。</span><span class="sxs-lookup"><span data-stu-id="dece1-110">To upgrade to Microsoft 365 Groups, the distribution list group must have an owner with a mailbox.</span></span>

### <a name="use-the-new-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="dece1-111">使用新的 EAC 将一个或多个通讯组列表组升级到Microsoft 365组Outlook</span><span class="sxs-lookup"><span data-stu-id="dece1-111">Use the new EAC to upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

1. <span data-ttu-id="dece1-112">转到新的"Exchange [管理中心"，](https://admin.exchange.microsoft.com)然后导航到"**收件人组** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="dece1-112">Go to the new [Exchange admin center](https://admin.exchange.microsoft.com), and navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="dece1-113">Select the distribution list group (also called a **distribution group**) that you want to upgrade to Microsoft 365 group from the **Groups** page.</span><span class="sxs-lookup"><span data-stu-id="dece1-113">Select the distribution list group (also called a **distribution group**) that you want to upgrade to Microsoft 365 group from the **Groups** page.</span></span>

3. <span data-ttu-id="dece1-114">从 **工具栏中选择"升级** 通讯组"。</span><span class="sxs-lookup"><span data-stu-id="dece1-114">Select the **Upgrade distribution group** from the tool bar.</span></span>

4. <span data-ttu-id="dece1-115">在"准备好升级 **？"对话框中，单击**"升级 **"。**</span><span class="sxs-lookup"><span data-stu-id="dece1-115">In the dialog box **Ready to upgrade?**, click **Upgrade**.</span></span> <span data-ttu-id="dece1-116">该过程立即开始。</span><span class="sxs-lookup"><span data-stu-id="dece1-116">The process begins immediately.</span></span> <span data-ttu-id="dece1-117">根据要升级的通讯组列表组的大小和数量，此过程可能需要几分钟或数小时。</span><span class="sxs-lookup"><span data-stu-id="dece1-117">Depending on the size and number of distribution list groups you're upgrading, the process can take minutes or hours.</span></span>

> [!NOTE]
> <span data-ttu-id="dece1-118">顶部的横幅表示升级，例如，通讯 (*组) 已升级。需要 5 分钟才能反映更改。按Microsoft 365组筛选，以查看* 已升级的 (组) 。</span><span class="sxs-lookup"><span data-stu-id="dece1-118">A banner at the top indicates the upgrade, for example, *Distribution group(s) has been upgraded. It will take 5 minutes to reflect the changes. Filter by Microsoft 365 groups to see the upgraded distrubtion groups(s)*.</span></span>

### <a name="use-the-classic-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="dece1-119">使用经典 EAC 将一个或多个通讯组列表组升级到Microsoft 365组Outlook</span><span class="sxs-lookup"><span data-stu-id="dece1-119">Use the Classic EAC to upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

1. <span data-ttu-id="dece1-120">转到经典Exchange<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="dece1-120">Go to the Classic <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="dece1-121">In the Classic Exchange admin center， go to **Recipients** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="dece1-121">In the Classic Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="dece1-122">你将看到一条通知，指示你拥有一 (也称为"通讯组"的) 有资格升级到"Microsoft 365组"。</span><span class="sxs-lookup"><span data-stu-id="dece1-122">You'll see a notice indicating you have distribution lists (also called **distribution groups**) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="dece1-123">![选择"开始"按钮](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="dece1-123">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="dece1-124">Select one or more distribution lists (also called a **distribution group**) from the **groups** page.</span><span class="sxs-lookup"><span data-stu-id="dece1-124">Select one or more distribution lists (also called a **distribution group**) from the **groups** page.</span></span><br/><span data-ttu-id="dece1-125">![选择通讯组](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="dece1-125">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="dece1-126">选择升级图标。</span><span class="sxs-lookup"><span data-stu-id="dece1-126">Select the upgrade icon.</span></span><br/>![升级到"Microsoft 365组"图标](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="dece1-128">在信息对话框中，选择 **"是** "以确认升级。</span><span class="sxs-lookup"><span data-stu-id="dece1-128">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="dece1-129">该过程立即开始。</span><span class="sxs-lookup"><span data-stu-id="dece1-129">The process begins immediately.</span></span> <span data-ttu-id="dece1-130">根据您升级的 DLL 的大小和数量，此过程可能需要几分钟或数小时。</span><span class="sxs-lookup"><span data-stu-id="dece1-130">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="dece1-131">如果通讯组列表无法升级，则会出现一个对话框，显示此对话框。</span><span class="sxs-lookup"><span data-stu-id="dece1-131">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="dece1-132">请参阅[哪些通讯组列表无法升级？。](#which-distribution-lists-cant-be-upgraded)</span><span class="sxs-lookup"><span data-stu-id="dece1-132">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cant-be-upgraded).</span></span>

6. <span data-ttu-id="dece1-133">如果要升级多个通讯组列表，请使用下拉列表筛选已升级的通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="dece1-133">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="dece1-134">如果列表不完整，请稍等一会，然后选择"刷新"以查看已成功升级哪些项。</span><span class="sxs-lookup"><span data-stu-id="dece1-134">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="dece1-135">不会发出通知，告知您所选所有 DLL 的升级过程何时完成。</span><span class="sxs-lookup"><span data-stu-id="dece1-135">There's no notice that tells you when the upgrade process has completed for all DLs you selected.</span></span> <span data-ttu-id="dece1-136">可以通过查看"可用于升级或升级的 DCL"下列出 **的内容来\*\*\*\*了解这一点**。</span><span class="sxs-lookup"><span data-stu-id="dece1-136">You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="dece1-137">如果选择 DL 进行升级，但仍在页面上显示"可供升级"，则升级失败。</span><span class="sxs-lookup"><span data-stu-id="dece1-137">If you selected a DL for upgrade, but it's still appeared on the page as Available to upgrade, then it failed to upgrade.</span></span> <span data-ttu-id="dece1-138">请参阅 [升级不起作用时要执行哪些操作](#what-to-do-if-the-upgrade-doesnt-work)。</span><span class="sxs-lookup"><span data-stu-id="dece1-138">See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="dece1-139">如果您收到组摘要电子邮件，您可能会在底部注意到，有时它将提供，用于升级您作为所有者的任何符合条件的通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="dece1-139">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of.</span></span> <span data-ttu-id="dece1-140">有关[摘要电子邮件](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22)Outlook请参阅在电子邮件中进行组对话。</span><span class="sxs-lookup"><span data-stu-id="dece1-140">See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span></span>

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="dece1-141">升级不起作用时要执行哪些操作</span><span class="sxs-lookup"><span data-stu-id="dece1-141">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="dece1-142">无法升级的通讯组列表保持不变。</span><span class="sxs-lookup"><span data-stu-id="dece1-142">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="dece1-143">如果一个或多个符合条件的 **通讯** 组列表无法升级，请打开支持 [票证](../../business-video/get-help-support.md)。</span><span class="sxs-lookup"><span data-stu-id="dece1-143">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../../business-video/get-help-support.md).</span></span> <span data-ttu-id="dece1-144">需要将问题上报给组工程团队，让他们找出问题。</span><span class="sxs-lookup"><span data-stu-id="dece1-144">The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="dece1-145">由于服务中断，通讯组列表可能不会升级，但不太可能升级。</span><span class="sxs-lookup"><span data-stu-id="dece1-145">It's possible that the distribution list didn't get upgraded because of a service outage, but unlikely.</span></span> <span data-ttu-id="dece1-146">如果需要，请稍等一下，然后再次尝试升级 DL。</span><span class="sxs-lookup"><span data-stu-id="dece1-146">If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="dece1-147">如何使用 PowerShell 同时升级多个通讯组列表</span><span class="sxs-lookup"><span data-stu-id="dece1-147">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="dece1-148">如果你在使用 PowerShell 方面有经验的，你可能希望转到此路由，而不是使用 UI。</span><span class="sxs-lookup"><span data-stu-id="dece1-148">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="dece1-149">我们有一组 cmdlet，可帮助您升级通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="dece1-149">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="dece1-150">请参阅下文。</span><span class="sxs-lookup"><span data-stu-id="dece1-150">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="dece1-151">升级单个 DL</span><span class="sxs-lookup"><span data-stu-id="dece1-151">Upgrade a single DL</span></span>

<span data-ttu-id="dece1-152">若要升级单个 DL，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="dece1-152">To upgrade a single DL, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>
```

<span data-ttu-id="dece1-153">例如，如果要升级 SMTP 地址为 dl1@contoso.com，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="dece1-153">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com
```

> [!NOTE]
> <span data-ttu-id="dece1-154">您还可以使用[New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell cmdlet 将单个通讯组列表Microsoft 365组</span><span class="sxs-lookup"><span data-stu-id="dece1-154">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="dece1-155">在一个批次中升级多个 DLL</span><span class="sxs-lookup"><span data-stu-id="dece1-155">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="dece1-156">还可以将多个 DLL 作为批处理传递，并一起升级它们：</span><span class="sxs-lookup"><span data-stu-id="dece1-156">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="dece1-157">例如，如果要升级五个 SMTP 地址为 、、 和 的 DLL， `dl1@contoso.com` `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` 请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="dece1-157">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="dece1-158">升级所有符合条件的 DLL</span><span class="sxs-lookup"><span data-stu-id="dece1-158">Upgrade all eligible DLs</span></span>

<span data-ttu-id="dece1-159">有两种方法可以升级所有符合条件的 DLL。</span><span class="sxs-lookup"><span data-stu-id="dece1-159">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="dece1-160">Upgrade-DistributionGroup cmdlet 不会从管道接收数据，因此，需要使用"foreach-object"运算符 {} 才能成功运行。</span><span class="sxs-lookup"><span data-stu-id="dece1-160">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="dece1-161">获取租户中符合条件的 DLL，然后使用升级命令升级它们：</span><span class="sxs-lookup"><span data-stu-id="dece1-161">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="dece1-162">获取所有 DLL 的列表，并仅升级符合条件的 DLL：</span><span class="sxs-lookup"><span data-stu-id="dece1-162">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="dece1-163">有关将通讯组列表升级到 Microsoft 365 组的常见问题Outlook</span><span class="sxs-lookup"><span data-stu-id="dece1-163">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cant-be-upgraded"></a><span data-ttu-id="dece1-164">哪些通讯组列表无法升级？</span><span class="sxs-lookup"><span data-stu-id="dece1-164">Which distribution lists can't be upgraded?</span></span>

<span data-ttu-id="dece1-165">只能升级云托管的简单非嵌套通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="dece1-165">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="dece1-166">下表列出了无法升级 **的** 通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="dece1-166">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="dece1-167">**Property**</span><span class="sxs-lookup"><span data-stu-id="dece1-167">**Property**</span></span>|<span data-ttu-id="dece1-168">**符合条件的？**</span><span class="sxs-lookup"><span data-stu-id="dece1-168">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dece1-169">本地托管通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="dece1-169">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="dece1-170">否</span><span class="sxs-lookup"><span data-stu-id="dece1-170">No</span></span>  <br/> |
|<span data-ttu-id="dece1-171">嵌套通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="dece1-171">Nested distribution lists.</span></span> <span data-ttu-id="dece1-172">通讯组列表有子组，或者是另一个组的成员。</span><span class="sxs-lookup"><span data-stu-id="dece1-172">Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="dece1-173">否</span><span class="sxs-lookup"><span data-stu-id="dece1-173">No</span></span>  <br/> |
|<span data-ttu-id="dece1-174">具有 **UserMailbox、SharedMailbox、TeamMailbox、MailUser** 的成员 **RecipientTypeDetails** 的 **通讯组列表**</span><span class="sxs-lookup"><span data-stu-id="dece1-174">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="dece1-175">否</span><span class="sxs-lookup"><span data-stu-id="dece1-175">No</span></span>  <br/> |
|<span data-ttu-id="dece1-176">拥有 100 多个所有者的通讯组列表</span><span class="sxs-lookup"><span data-stu-id="dece1-176">Distribution list that has more than 100 owners</span></span>  <br/> |<span data-ttu-id="dece1-177">否</span><span class="sxs-lookup"><span data-stu-id="dece1-177">No</span></span>  <br/> |
|<span data-ttu-id="dece1-178">仅包含成员但没有所有者的通讯组列表</span><span class="sxs-lookup"><span data-stu-id="dece1-178">Distribution list that only has members but no owner</span></span>  <br/> |<span data-ttu-id="dece1-179">否</span><span class="sxs-lookup"><span data-stu-id="dece1-179">No</span></span>  <br/> |
|<span data-ttu-id="dece1-180">别名包含特殊字符的通讯组列表</span><span class="sxs-lookup"><span data-stu-id="dece1-180">Distribution list that has alias containing special characters</span></span>  <br/> |<span data-ttu-id="dece1-181">否</span><span class="sxs-lookup"><span data-stu-id="dece1-181">No</span></span>  <br/> |
|<span data-ttu-id="dece1-182">如果通讯组列表配置为共享邮箱的转发地址</span><span class="sxs-lookup"><span data-stu-id="dece1-182">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="dece1-183">否</span><span class="sxs-lookup"><span data-stu-id="dece1-183">No</span></span>  <br/> |
|<span data-ttu-id="dece1-184">如果 DL 是其他 DL **中的发件人限制** 的一部分。</span><span class="sxs-lookup"><span data-stu-id="dece1-184">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="dece1-185">否</span><span class="sxs-lookup"><span data-stu-id="dece1-185">No</span></span>  <br/> |
|<span data-ttu-id="dece1-186">安全组</span><span class="sxs-lookup"><span data-stu-id="dece1-186">Security groups</span></span>  <br/> |<span data-ttu-id="dece1-187">否</span><span class="sxs-lookup"><span data-stu-id="dece1-187">No</span></span>  <br/> |
|<span data-ttu-id="dece1-188">动态通讯组列表</span><span class="sxs-lookup"><span data-stu-id="dece1-188">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="dece1-189">否</span><span class="sxs-lookup"><span data-stu-id="dece1-189">No</span></span>  <br/> |
|<span data-ttu-id="dece1-190">已转换为 **RoomLists 的通讯组列表**</span><span class="sxs-lookup"><span data-stu-id="dece1-190">Distribution lists that were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="dece1-191">否</span><span class="sxs-lookup"><span data-stu-id="dece1-191">No</span></span>  <br/> |
|<span data-ttu-id="dece1-192">**MemberJoinRestriction** 和/或 **MemberDepartRestriction 已关闭的\*\*\*\*通讯组列表**</span><span class="sxs-lookup"><span data-stu-id="dece1-192">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="dece1-193">否</span><span class="sxs-lookup"><span data-stu-id="dece1-193">No</span></span>  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="dece1-194">检查哪些 DLL 有资格升级</span><span class="sxs-lookup"><span data-stu-id="dece1-194">Check which DLs are eligible for upgrade</span></span>

<span data-ttu-id="dece1-195">如果要检查 DL 是否符合条件，可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="dece1-195">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="dece1-196">如果要检查哪些 DLL 符合升级条件，只需运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="dece1-196">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="dece1-197">Who可以运行升级脚本吗？</span><span class="sxs-lookup"><span data-stu-id="dece1-197">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="dece1-198">具有全局管理员或Exchange管理员权限的用户。</span><span class="sxs-lookup"><span data-stu-id="dece1-198">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-an-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="dece1-199">为什么联系人卡片仍显示通讯组列表？</span><span class="sxs-lookup"><span data-stu-id="dece1-199">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="dece1-200">我应该如何阻止升级的通讯组列表显示在我的自动建议列表中？</span><span class="sxs-lookup"><span data-stu-id="dece1-200">What should I do to prevent an upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="dece1-201">例如Outlook：当有人尝试在 Outlook 中通过键入 Microsoft 365 组名称在迁移后发送电子邮件时，收件人将解析为通讯组列表而不是组。</span><span class="sxs-lookup"><span data-stu-id="dece1-201">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="dece1-202">收件人的联系人卡片将是通讯组列表联系人卡片。</span><span class="sxs-lookup"><span data-stu-id="dece1-202">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="dece1-203">这是因为收件人缓存或名称缓存位于Outlook。</span><span class="sxs-lookup"><span data-stu-id="dece1-203">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="dece1-204">电子邮件将成功发送到组，但可能会导致发件人混淆。</span><span class="sxs-lookup"><span data-stu-id="dece1-204">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="dece1-205">可以执行本文中有关自动完成Outlook[重置](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list)缓存的信息，这将修复此问题。</span><span class="sxs-lookup"><span data-stu-id="dece1-205">You can perform the steps in this article, [Information about the Outlook AutoComplete list](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="dece1-206">For Outlook on the web： In case Outlook on the web， the distribution list recipient will still remain in the cache.</span><span class="sxs-lookup"><span data-stu-id="dece1-206">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="dece1-207">你可以按照从自动完成列表中[](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58)删除建议的名称或电子邮件地址中的步骤刷新缓存以查看组联系人卡片。</span><span class="sxs-lookup"><span data-stu-id="dece1-207">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="dece1-208">新组的成员是否收到收件箱中的欢迎电子邮件？</span><span class="sxs-lookup"><span data-stu-id="dece1-208">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="dece1-209">错误。</span><span class="sxs-lookup"><span data-stu-id="dece1-209">No.</span></span> <span data-ttu-id="dece1-210">默认情况下，启用欢迎消息的设置设置为 false。</span><span class="sxs-lookup"><span data-stu-id="dece1-210">The setting to enable welcome messages is set to false by default.</span></span> <span data-ttu-id="dece1-211">此设置会影响在迁移完成后可加入的现有和新的组的成员。</span><span class="sxs-lookup"><span data-stu-id="dece1-211">This setting affects both existing and new group members who may join after the migration is complete.</span></span> <span data-ttu-id="dece1-212">如果组所有者稍后允许来宾用户，则来宾用户不会在收件箱中收到欢迎电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dece1-212">If the group owner later allows guest users, guest users won't receive a welcome email in their inbox.</span></span> <span data-ttu-id="dece1-213">来宾成员可以继续使用组。</span><span class="sxs-lookup"><span data-stu-id="dece1-213">Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="dece1-214">如果未升级一个或多个 DLL，将如何？</span><span class="sxs-lookup"><span data-stu-id="dece1-214">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="dece1-215">在某些情况下，虽然 DL 符合条件，但无法升级。</span><span class="sxs-lookup"><span data-stu-id="dece1-215">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="dece1-216">DL 不会升级，仍保持为 DL。</span><span class="sxs-lookup"><span data-stu-id="dece1-216">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="dece1-217">如果 **管理员为组织中** 各组应用了组电子邮件地址策略，并且他们尝试升级不满足条件的 DLL，则 DLL 将不会升级</span><span class="sxs-lookup"><span data-stu-id="dece1-217">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs that doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="dece1-218">**MemberJoinRestriction 或** **MemberDepartRestriction** 设置为 **Closed** 的 DLL 无法升级</span><span class="sxs-lookup"><span data-stu-id="dece1-218">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="dece1-219">如果从 EAC 升级失败，DL 会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="dece1-219">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="dece1-220">只有在将呼叫提交到服务器时，才能进行升级。</span><span class="sxs-lookup"><span data-stu-id="dece1-220">The upgrade will happen only when the call is submitted to the server.</span></span> <span data-ttu-id="dece1-221">如果升级失败，DLL 将保持不变。</span><span class="sxs-lookup"><span data-stu-id="dece1-221">If the upgrade fails, your DLs will be intact.</span></span> <span data-ttu-id="dece1-222">他们将像以前一样工作。</span><span class="sxs-lookup"><span data-stu-id="dece1-222">They will work like they used to.</span></span>
