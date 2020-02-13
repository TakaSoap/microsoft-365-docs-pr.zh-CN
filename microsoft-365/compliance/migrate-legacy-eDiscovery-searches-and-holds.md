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
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 356330b4282fe9dc0aa211d48e452ad04a1bbe74
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957187"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a>将旧式电子数据展示搜索和保留迁移到 Microsoft 365 合规性中心

Microsoft 365 合规性中心提供了改进的电子数据展示使用体验，其中包括：更高的可靠性、更佳的性能以及针对电子数据展示工作流量身定制的多种功能，包括用于按事务组织内容的案例，审阅集可用于查看内容和分析，以帮助精选数据以供查看，如接近重复的分组、电子邮件线程、主题分析和预测编码。

为帮助客户利用新的和改进的功能，本文提供了有关如何将就地电子数据展示搜索和保留从 Exchange 管理中心迁移到 Microsoft 365 合规中心的基本指南。

> [!NOTE]
> 由于存在许多不同的方案，本文提供了在 Microsoft 365 合规性中心中将搜索和保留转换为核心电子数据展示事例的一般指导。 不总是需要使用电子数据展示事例，而是通过允许您分配权限来控制对组织中的电子数据展示事例的访问权限，从而添加额外的安全层。

## <a name="before-you-begin"></a>准备工作

- 您必须是 Office 365 Security & 合规性中心中的电子数据展示管理器角色组的成员，才能运行本文中所述的 PowerShell 命令。 此外，您还必须是 Exchange 管理中心中 "发现管理" 角色组的成员。

- 本文提供了有关如何创建电子数据展示保留的指南。 保留策略将通过异步过程应用于邮箱。 创建电子数据展示保留时，必须同时创建 CaseHoldPolicy 和 New-caseholdrule，否则将不会创建保留，并且不会将内容位置置于保留状态。

## <a name="step-1-connect-to-exchange-online-powershell-and-office-365-security--compliance-center-powershell"></a>步骤1：连接到 Exchange Online PowerShell 和 Office 365 安全 & 合规性中心 PowerShell

第一步是连接到 Exchange Online PowerShell 和 Office 365 安全 & 合规性中心 PowerShell。 您可以复制以下脚本，将其粘贴到 PowerShell 窗口中，然后运行它。 系统将提示你输入要连接到的组织的凭据。 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $sccSession -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

您需要在此 PowerShell 会话中的以下步骤中运行命令。

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a>步骤2：使用 New-mailboxsearch 获取就地电子数据展示搜索的列表

经过身份验证后，可以通过运行**new-mailboxsearch** Cmdlet 获取就地电子数据展示搜索的列表。 将以下命令复制并粘贴到 PowerShell 中，然后运行它。 将列出搜索的列表及其名称和任何就地保留的状态。

```powershell
Get-MailboxSearch
```

Cmdlet 输出将类似于以下内容：

![PowerShell 示例 New-mailboxsearch](media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a>步骤3：获取有关要迁移的就地电子数据展示搜索和就地保留的信息

同样，您将使用**new-mailboxsearch** cmdlet，但这次是为了获取搜索的属性。 您可以将这些属性存储在变量中供以后使用。 下面的示例将**new-mailboxsearch** cmdlet 的结果存储在一个变量中，然后显示该搜索的属性。

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

这两个命令的输出将类似于以下内容：

![使用 New-mailboxsearch 进行单个搜索的 PowerShell 输出示例](media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> 此示例中就地保留的持续时间不定（*ItemHoldPeriod：无限制*）。 这对于电子数据展示和法律调查方案来说是典型的。 如果保留期的值与不定的值不同，原因可能是由于保留正在用于保留方案中的内容。 我们建议您使用[new-retentioncompliancepolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy)和[New-retentioncompliancerule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule)的电子数据展示 cmdlet 来保留方案，而不是在 Office 365 安全性 & 合规性中心 PowerShell 中使用它来保留内容。 使用这些 cmdlet 的结果将类似于使用**CaseHoldPolicy**和**new-caseholdrule**，但您可以指定保留期和保留操作，例如，在保留期过期后删除内容。 此外，使用保留 cmdlet 不需要将保留挂起与电子数据展示事例相关联。

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a>步骤4：在 Microsoft 365 合规性中心中创建事例

若要创建电子数据展示保留，必须创建电子数据展示事例以将保留与保留关联。 下面的示例使用您选择的名称创建电子数据展示事例。 我们将在变量中存储新事例的属性以供以后使用。 您可以通过在创建事例后运行`$case | FL`命令来查看这些属性。

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```

## <a name="step-5-create-the-ediscovery-hold"></a>步骤5：创建电子数据展示保留

创建案例后，可以创建保留并将其与在上一步骤中创建的事例相关联。 务必要记住，必须创建事例保留策略和事例保留规则。 如果创建事例保留策略后未创建事例保留规则，则不会创建电子数据展示保留，并且不会将任何内容置于保留状态。

运行以下命令以重新创建要迁移的电子数据展示保留。 这些示例使用要迁移的步骤3中的就地保留中的属性。 第一个命令创建新的事例保留策略并将属性保存到变量中。 第二个命令创建对应的事例保留规则。

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

## <a name="step-6-verify-the-ediscovery-hold"></a>步骤6：验证电子数据展示保留

若要确保创建保留时没有问题，最好检查保留分发状态是否为 "成功"。 "分布" 表示已将保留应用于上一步中的*ExchangeLocation*参数中指定的所有内容位置。 若要执行此操作，您可以运行**CaseHoldPolicy** cmdlet。 由于保存到您在上一步中创建的 *$policy*变量的属性不会自动更新到变量中，因此您需要重新运行 cmdlet 以验证分发是否成功。 若要成功分发事例保留策略，可能需要5分钟到24小时。

运行以下命令以验证是否已成功分发电子数据展示保留。

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

*DistributionStatus*属性的**Success**值指示已成功将保留放在内容位置上。 如果分发尚未完成，则会显示 "**挂起**" 的值。

![PowerShell CaseHoldPolicy 示例](media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a>步骤7：创建搜索

最后一步是重新创建您在步骤3中确定的搜索，并将其与事例相关联。 创建搜索后，可以使用**new-compliancesearch** cmdlet 运行它，也可以稍后运行它。

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![PowerShell New-compliancesearch 示例](media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a>步骤8：确认在 Microsoft 365 合规性中心中的案例、保留和搜索

若要确保一切都已正确设置，请转到 Microsoft 365 合规性中心[https://compliance.microsoft.com](https://compliance.microsoft.com)，然后单击 "**电子数据展示 > 核心**"。

![Microsoft 365 合规性中心电子数据展示](media/MigrateLegacyeDiscovery7.png)

您在步骤3中创建的事例将列在**核心电子数据展示**页面中。 打开该事例，然后注意您在 "**保留**" 选项卡上列出的步骤4中创建的保留。可以单击 "保留" 查看详细信息，包括应用了保留的邮箱数和分发状态。

![Microsoft 365 合规性中心中的电子数据展示保留](media/MigrateLegacyeDiscovery8.png)

您在步骤7中创建的搜索将列在电子数据展示事例的 "**搜索**" 选项卡上列出的列表中。

![Microsoft 365 合规性中心中的电子数据展示案例搜索](media/MigrateLegacyeDiscovery9.png)

如果您迁移就地电子数据展示搜索但不将其与电子数据展示事例关联，则它将列在 Microsoft 365 合规性中心的内容搜索页中。

## <a name="more-information"></a>详细信息

- 有关在 Exchange 管理中心中就地电子数据展示 & 保留的详细信息，请参阅：
  
  - [就地电子数据展示](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [就地保留和诉讼保留](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)

- 有关本文中使用的 PowerShell cmdlet 的详细信息，请参阅：

  - [New-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch)
  
  - [新 Get-compliancecase](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-compliancecase)

  - [新 CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-caseholdpolicy)
  
  - [新 New-caseholdrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-caseholdrule)

  - [CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)
  
  - [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)

  - [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)

- 有关 Microsoft 365 合规性中心的详细信息，请参阅[microsoft 365 合规性中心概述](microsoft-365-compliance-center.md)。
