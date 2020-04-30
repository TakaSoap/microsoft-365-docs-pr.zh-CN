---
title: 将旧式电子数据展示搜索和保留迁移到 Microsoft 365 合规性中心
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 409afed8ea927f1bdfc602264bbff7bce34e8533
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943331"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="078fa-102">将旧式电子数据展示搜索和保留迁移到 Microsoft 365 合规性中心</span><span class="sxs-lookup"><span data-stu-id="078fa-102">Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="078fa-103">Microsoft 365 合规性中心提供了改进的电子数据展示使用体验，其中包括：更高可靠性、更好的性能以及针对电子数据展示工作流量身定制的许多功能，包括对内容进行整理的案例，审阅设置以查看内容和分析，以帮助精选数据进行审核，如接近重复的分组、电子邮件线程、主题分析和预测编码。</span><span class="sxs-lookup"><span data-stu-id="078fa-103">The Microsoft 365 compliance center provides an improved experience for eDiscovery usage, including: higher reliability, better performance and many features tailored to eDiscovery workflows including cases to organize your content by matter, review sets to review content and analytics to help cull data for review such as near-duplicate grouping, email threading, themes analysis, and predictive coding.</span></span>

<span data-ttu-id="078fa-104">为帮助客户利用新的和改进的功能，本文提供了有关如何将就地电子数据展示搜索和保留从 Exchange 管理中心迁移到 Microsoft 365 合规中心的基本指南。</span><span class="sxs-lookup"><span data-stu-id="078fa-104">To help customers take advantage of the new and improved functionality, this article provides basic guidance on how to migrate In-Place eDiscovery searches and holds from the Exchange admin center to the Microsoft 365 compliance center.</span></span>

> [!NOTE]
> <span data-ttu-id="078fa-105">由于存在许多不同的方案，本文提供了在 Microsoft 365 合规性中心中将搜索和保留转换为核心电子数据展示事例的一般指导。</span><span class="sxs-lookup"><span data-stu-id="078fa-105">Because there are many different scenarios, this article provides general guidance to transition searches and holds to a core eDiscovery case in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="078fa-106">不总是需要使用电子数据展示事例，而是通过允许您分配权限来控制对组织中的电子数据展示事例的访问权限，从而添加额外的安全层。</span><span class="sxs-lookup"><span data-stu-id="078fa-106">Using eDiscovery cases aren't always required, but they add an extra layer of security by letting you assign permissions to control who has access to the eDiscovery cases in your organization.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="078fa-107">准备工作</span><span class="sxs-lookup"><span data-stu-id="078fa-107">Before you begin</span></span>

- <span data-ttu-id="078fa-108">您必须是 Security & 合规性中心中的电子数据展示管理器角色组的成员，才能运行本文中所述的 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="078fa-108">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the PowerShell commands described in this article.</span></span> <span data-ttu-id="078fa-109">此外，您还必须是 Exchange 管理中心中 "发现管理" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="078fa-109">You also have to be a member of the Discovery Management role group in the Exchange admin center.</span></span>

- <span data-ttu-id="078fa-110">本文提供了有关如何创建电子数据展示保留的指南。</span><span class="sxs-lookup"><span data-stu-id="078fa-110">This article provides guidance on how to create an eDiscovery hold.</span></span> <span data-ttu-id="078fa-111">保留策略将通过异步过程应用于邮箱。</span><span class="sxs-lookup"><span data-stu-id="078fa-111">The hold policy will be applied to mailboxes through an asynchronous process.</span></span> <span data-ttu-id="078fa-112">创建电子数据展示保留时，必须同时创建 CaseHoldPolicy 和 New-caseholdrule，否则将不会创建保留，并且不会将内容位置置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="078fa-112">When creating an eDiscovery hold, you must create both a CaseHoldPolicy and CaseHoldRule, otherwise the hold will not be created and content locations will not be placed on hold.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell-and-security--compliance-center-powershell"></a><span data-ttu-id="078fa-113">步骤1：连接到 Exchange Online PowerShell 和安全性 & 合规性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="078fa-113">Step 1: Connect to Exchange Online PowerShell and Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="078fa-114">第一步是连接到 Exchange Online PowerShell 和安全 & 合规性中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="078fa-114">The first step is to connect to Exchange Online PowerShell and Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="078fa-115">您可以复制以下脚本，将其粘贴到 PowerShell 窗口中，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="078fa-115">You can copy the following script, paste it into a PowerShell window and then run it.</span></span> <span data-ttu-id="078fa-116">系统将提示你输入要连接到的组织的凭据。</span><span class="sxs-lookup"><span data-stu-id="078fa-116">You'll be prompted for credentials for the organization that you want to connect to.</span></span> 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $sccSession -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

<span data-ttu-id="078fa-117">您需要在此 PowerShell 会话中的以下步骤中运行命令。</span><span class="sxs-lookup"><span data-stu-id="078fa-117">You need to run the commands in the following steps in this PowerShell session.</span></span>

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a><span data-ttu-id="078fa-118">步骤2：使用 New-mailboxsearch 获取就地电子数据展示搜索的列表</span><span class="sxs-lookup"><span data-stu-id="078fa-118">Step 2: Get a list of In-Place eDiscovery searches by using Get-MailboxSearch</span></span>

<span data-ttu-id="078fa-119">经过身份验证后，可以通过运行**new-mailboxsearch** Cmdlet 获取就地电子数据展示搜索的列表。</span><span class="sxs-lookup"><span data-stu-id="078fa-119">After you've authenticated, you can get a list of In-Place eDiscovery searches by running the **Get-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="078fa-120">将以下命令复制并粘贴到 PowerShell 中，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="078fa-120">Copy and paste the following command into PowerShell and then run it.</span></span> <span data-ttu-id="078fa-121">将列出搜索的列表及其名称和任何就地保留的状态。</span><span class="sxs-lookup"><span data-stu-id="078fa-121">A list of searches will be listed with their names and the status of any In-Place Holds.</span></span>

```powershell
Get-MailboxSearch
```

<span data-ttu-id="078fa-122">Cmdlet 输出将类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="078fa-122">The cmdlet output will be similar to the following:</span></span>

![PowerShell 示例 New-mailboxsearch](../media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a><span data-ttu-id="078fa-124">步骤3：获取有关要迁移的就地电子数据展示搜索和就地保留的信息</span><span class="sxs-lookup"><span data-stu-id="078fa-124">Step 3: Get information about the In-Place eDiscovery searches and In-Place Holds you want to migrate</span></span>

<span data-ttu-id="078fa-125">同样，您将使用**new-mailboxsearch** cmdlet，但这次是为了获取搜索的属性。</span><span class="sxs-lookup"><span data-stu-id="078fa-125">Again you will use the **Get-MailboxSearch** cmdlet, but this time to get the properties of the search.</span></span> <span data-ttu-id="078fa-126">您可以将这些属性存储在变量中供以后使用。</span><span class="sxs-lookup"><span data-stu-id="078fa-126">You can store these properties in a variable for use later.</span></span> <span data-ttu-id="078fa-127">下面的示例将**new-mailboxsearch** cmdlet 的结果存储在一个变量中，然后显示该搜索的属性。</span><span class="sxs-lookup"><span data-stu-id="078fa-127">The following example stores the results of the **Get-MailboxSearch** cmdlet in a variable and then displays the properties of the search.</span></span>

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

<span data-ttu-id="078fa-128">这两个命令的输出将类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="078fa-128">The output of these two commands will be similar to the following:</span></span>

![使用 New-mailboxsearch 进行单个搜索的 PowerShell 输出示例](../media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> <span data-ttu-id="078fa-130">此示例中就地保留的持续时间不定（*ItemHoldPeriod：无限制*）。</span><span class="sxs-lookup"><span data-stu-id="078fa-130">The duration of the In-Place Hold in this example is indefinite (*ItemHoldPeriod: Unlimited*).</span></span> <span data-ttu-id="078fa-131">这对于电子数据展示和法律调查方案来说是典型的。</span><span class="sxs-lookup"><span data-stu-id="078fa-131">This is typical for eDiscovery and legal investigation scenarios.</span></span> <span data-ttu-id="078fa-132">如果保留期的值与不定的值不同，原因可能是由于保留正在用于保留方案中的内容。</span><span class="sxs-lookup"><span data-stu-id="078fa-132">If the hold duration has is different value than indefinite, the reason is likely because the hold is being used to retain content in a retention scenario.</span></span> <span data-ttu-id="078fa-133">我们建议您使用[new-retentioncompliancepolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy)和[New-retentioncompliancerule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule)的安全电子数据展示 cmdlet 来保留方案，而不是在安全 & 合规中心 PowerShell 中使用电子数据展示 cmdlet 来保留内容。</span><span class="sxs-lookup"><span data-stu-id="078fa-133">Instead of using the eDiscovery cmdlets in Security & Compliance Center PowerShell for retention scenarios, we recommend that you use [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy) and [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule) to retain content.</span></span> <span data-ttu-id="078fa-134">使用这些 cmdlet 的结果将类似于使用**CaseHoldPolicy**和**new-caseholdrule**，但您可以指定保留期和保留操作，例如，在保留期过期后删除内容。</span><span class="sxs-lookup"><span data-stu-id="078fa-134">The result of using these cmdlets will be similar to using **New-CaseHoldPolicy** and **New-CaseHoldRule**, but you'll able to specify a retention period and a retention action, such as deleting content after the retention period expires.</span></span> <span data-ttu-id="078fa-135">此外，使用保留 cmdlet 不需要将保留挂起与电子数据展示事例相关联。</span><span class="sxs-lookup"><span data-stu-id="078fa-135">Also, using the retention cmdlets don't require you to associate the retention holds with an eDiscovery case.</span></span>

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="078fa-136">步骤4：在 Microsoft 365 合规性中心中创建事例</span><span class="sxs-lookup"><span data-stu-id="078fa-136">Step 4: Create a case in the Microsoft 365 Compliance center</span></span>

<span data-ttu-id="078fa-137">若要创建电子数据展示保留，必须创建电子数据展示事例以将保留与保留关联。</span><span class="sxs-lookup"><span data-stu-id="078fa-137">To create an eDiscovery hold, you have to create an eDiscovery case to associate the hold with.</span></span> <span data-ttu-id="078fa-138">下面的示例使用您选择的名称创建电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="078fa-138">The following example creates an eDiscovery case using a name of your choice.</span></span> <span data-ttu-id="078fa-139">我们将在变量中存储新事例的属性以供以后使用。</span><span class="sxs-lookup"><span data-stu-id="078fa-139">We will store the properties of the new case in a variable for use later.</span></span> <span data-ttu-id="078fa-140">您可以通过在创建事例后运行`$case | FL`命令来查看这些属性。</span><span class="sxs-lookup"><span data-stu-id="078fa-140">You can view those properties by running the `$case | FL` command after you create the case.</span></span>

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```
![运行 Get-compliancecase 命令的示例](../media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a><span data-ttu-id="078fa-142">步骤5：创建电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="078fa-142">Step 5: Create the eDiscovery hold</span></span>

<span data-ttu-id="078fa-143">创建案例后，可以创建保留并将其与在上一步骤中创建的事例相关联。</span><span class="sxs-lookup"><span data-stu-id="078fa-143">After the case is created, you can create the hold and associate it with the case that you created in the previous step.</span></span> <span data-ttu-id="078fa-144">务必要记住，必须创建事例保留策略和事例保留规则。</span><span class="sxs-lookup"><span data-stu-id="078fa-144">It's important to remember that you must create both a case hold policy and a case hold rule.</span></span> <span data-ttu-id="078fa-145">如果创建事例保留策略后未创建事例保留规则，则不会创建电子数据展示保留，并且不会将任何内容置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="078fa-145">If the case hold rule isn't created after you created case hold policy, the eDiscovery hold will not be created and any content won't be placed on hold.</span></span>

<span data-ttu-id="078fa-146">运行以下命令以重新创建要迁移的电子数据展示保留。</span><span class="sxs-lookup"><span data-stu-id="078fa-146">Run the following commands to re-create the eDiscovery hold that you want to migrate.</span></span> <span data-ttu-id="078fa-147">这些示例使用要迁移的步骤3中的就地保留中的属性。</span><span class="sxs-lookup"><span data-stu-id="078fa-147">These examples use the properties from In-Place Hold from Step 3 that you want to migrate.</span></span> <span data-ttu-id="078fa-148">第一个命令创建新的事例保留策略并将属性保存到变量中。</span><span class="sxs-lookup"><span data-stu-id="078fa-148">The first command creates a new case hold policy and saves the properties to a variable.</span></span> <span data-ttu-id="078fa-149">第二个命令创建对应的事例保留规则。</span><span class="sxs-lookup"><span data-stu-id="078fa-149">The second command creates the corresponding case hold rule.</span></span>

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![使用 NewCaseHoldPolicy 和 NewCaseHoldRule cmdlet 的示例](../media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a><span data-ttu-id="078fa-151">步骤6：验证电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="078fa-151">Step 6: Verify the eDiscovery hold</span></span>

<span data-ttu-id="078fa-152">若要确保创建保留时没有问题，最好检查保留分发状态是否为 "成功"。</span><span class="sxs-lookup"><span data-stu-id="078fa-152">To make sure there were no issues in creating the hold, it's good to check that the hold distribution status is successful.</span></span> <span data-ttu-id="078fa-153">"分布" 表示已将保留应用于上一步中的*ExchangeLocation*参数中指定的所有内容位置。</span><span class="sxs-lookup"><span data-stu-id="078fa-153">Distribution means that the hold has been applied to all the content locations specified in the *ExchangeLocation* parameter in the previous step.</span></span> <span data-ttu-id="078fa-154">若要执行此操作，您可以运行**CaseHoldPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="078fa-154">To do this, you can run the **Get-CaseHoldPolicy** cmdlet.</span></span> <span data-ttu-id="078fa-155">由于保存到您在上一步中创建的 *$policy*变量的属性不会在变量中自动更新，因此您需要重新运行 cmdlet 以验证分发是否成功。</span><span class="sxs-lookup"><span data-stu-id="078fa-155">Because the properties saved to the *$policy* variable that you created in the previous step aren't automatically updated in the variable, you need to rerun the cmdlet to verify that distribution is successful.</span></span> <span data-ttu-id="078fa-156">若要成功分发事例保留策略，可能需要5分钟到24小时。</span><span class="sxs-lookup"><span data-stu-id="078fa-156">It can take between 5 minutes and 24 hours for case hold policies to be successfully distributed.</span></span>

<span data-ttu-id="078fa-157">运行以下命令以验证是否已成功分发电子数据展示保留。</span><span class="sxs-lookup"><span data-stu-id="078fa-157">Run the following command to verify that the eDiscovery hold has been successfully distributed.</span></span>

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

<span data-ttu-id="078fa-158">*DistributionStatus*属性的**Success**值指示已成功将保留放在内容位置上。</span><span class="sxs-lookup"><span data-stu-id="078fa-158">The value of **Success** for the *DistributionStatus* property indicates the hold was successfully placed on the content locations.</span></span> <span data-ttu-id="078fa-159">如果分发尚未完成，则会显示 "**挂起**" 的值。</span><span class="sxs-lookup"><span data-stu-id="078fa-159">If the distribution is not yet complete, a value of **Pending** is displayed.</span></span>

![PowerShell CaseHoldPolicy 示例](../media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a><span data-ttu-id="078fa-161">步骤7：创建搜索</span><span class="sxs-lookup"><span data-stu-id="078fa-161">Step 7: Create the search</span></span>

<span data-ttu-id="078fa-162">最后一步是重新创建您在步骤3中确定的搜索，并将其与事例相关联。</span><span class="sxs-lookup"><span data-stu-id="078fa-162">The last step is to re-create the search that you identified in Step 3 and associate it with the case.</span></span> <span data-ttu-id="078fa-163">创建搜索后，可以使用**new-compliancesearch** cmdlet 运行它，也可以稍后运行它。</span><span class="sxs-lookup"><span data-stu-id="078fa-163">After you create the search, you can run it by using the **Start-ComplianceSearch** cmdlet or run at a later time.</span></span>

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![PowerShell New-compliancesearch 示例](../media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="078fa-165">步骤8：确认在 Microsoft 365 合规性中心中的案例、保留和搜索</span><span class="sxs-lookup"><span data-stu-id="078fa-165">Step 8: Verify the case, hold, and search in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="078fa-166">若要确保一切都已正确设置，请转到 Microsoft 365 合规性中心[https://compliance.microsoft.com](https://compliance.microsoft.com)，然后单击 "**电子数据展示 > 核心**"。</span><span class="sxs-lookup"><span data-stu-id="078fa-166">To make sure that everything is set up correctly, go to the Microsoft 365 compliance center at [https://compliance.microsoft.com](https://compliance.microsoft.com), and click **eDiscovery > Core**.</span></span>

![Microsoft 365 合规性中心电子数据展示](../media/MigrateLegacyeDiscovery7.png)

<span data-ttu-id="078fa-168">您在步骤3中创建的事例将列在**核心电子数据展示**页面中。</span><span class="sxs-lookup"><span data-stu-id="078fa-168">The case that you created in Step 3 is listed on the **Core eDiscovery** page.</span></span> <span data-ttu-id="078fa-169">打开该事例，然后注意您在 "**保留**" 选项卡上列出的步骤4中创建的保留。可以单击 "保留" 查看详细信息，包括应用了保留的邮箱数和分发状态。</span><span class="sxs-lookup"><span data-stu-id="078fa-169">Open the case and then notice the hold that you created in Step 4 in listed on the **Holds** tab. You can click the hold to see details, including the number of mailboxes the hold is applied to and the distribution status.</span></span>

![Microsoft 365 合规性中心中的电子数据展示保留](../media/MigrateLegacyeDiscovery8.png)

<span data-ttu-id="078fa-171">您在步骤7中创建的搜索将列在电子数据展示事例的 "**搜索**" 选项卡上列出的列表中。</span><span class="sxs-lookup"><span data-stu-id="078fa-171">The search that you created in Step 7 is listed on the listed on the **Searches** tab of the eDiscovery case.</span></span>

![Microsoft 365 合规性中心中的电子数据展示案例搜索](../media/MigrateLegacyeDiscovery9.png)

<span data-ttu-id="078fa-173">如果您迁移就地电子数据展示搜索但不将其与电子数据展示事例关联，则它将列在 Microsoft 365 合规性中心的内容搜索页中。</span><span class="sxs-lookup"><span data-stu-id="078fa-173">If you migrate an In-Place eDiscovery search but don't associate it with an eDiscovery case, it will be listed on the Content search page in the Microsoft 365 compliance center.</span></span>

## <a name="more-information"></a><span data-ttu-id="078fa-174">更多信息</span><span class="sxs-lookup"><span data-stu-id="078fa-174">More information</span></span>

- <span data-ttu-id="078fa-175">有关在 Exchange 管理中心中就地电子数据展示 & 保留的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="078fa-175">For more information about In-Place eDiscovery & Holds in the Exchange admin center, see:</span></span>
  
  - [<span data-ttu-id="078fa-176">就地电子数据展示</span><span class="sxs-lookup"><span data-stu-id="078fa-176">In-Place eDiscovery</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [<span data-ttu-id="078fa-177">就地保留和诉讼保留</span><span class="sxs-lookup"><span data-stu-id="078fa-177">In-Place Hold and Litigation Hold</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)

- <span data-ttu-id="078fa-178">有关本文中使用的 PowerShell cmdlet 的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="078fa-178">For more information about the PowerShell cmdlets used in the article, see:</span></span>

  - [<span data-ttu-id="078fa-179">New-mailboxsearch</span><span class="sxs-lookup"><span data-stu-id="078fa-179">Get-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch)
  
  - [<span data-ttu-id="078fa-180">新 Get-compliancecase</span><span class="sxs-lookup"><span data-stu-id="078fa-180">New-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-compliancecase)

  - [<span data-ttu-id="078fa-181">新 CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="078fa-181">New-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-caseholdpolicy)
  
  - [<span data-ttu-id="078fa-182">新 New-caseholdrule</span><span class="sxs-lookup"><span data-stu-id="078fa-182">New-CaseHoldRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-caseholdrule)

  - [<span data-ttu-id="078fa-183">CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="078fa-183">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)
  
  - [<span data-ttu-id="078fa-184">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="078fa-184">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)

  - [<span data-ttu-id="078fa-185">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="078fa-185">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)

- <span data-ttu-id="078fa-186">有关 Microsoft 365 合规性中心的详细信息，请参阅[microsoft 365 合规性中心概述](microsoft-365-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="078fa-186">For more information about the Microsoft 365 compliance center, see [Overview of the Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>
