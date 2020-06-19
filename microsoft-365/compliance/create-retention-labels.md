---
title: 创建、发布和自动应用保留标签
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 有关创建、发布和自动应用保留标签以保留所需内容、删除不需要的内容，并在 Office 365 环境中将项目声明为记录的说明。
ms.openlocfilehash: 035038c90179354e0497813326b1fdad01693bec
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761648"
---
# <a name="create-publish-and-auto-apply-retention-labels"></a>创建、发布和自动应用保留标签

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

使用以下信息可帮助你创建[保留标签](labels.md)，然后将其自动应用到文档和电子邮件，或发布它们以便用户可以手动应用。

保留标签可帮助你保留所需内容并删除不需要的内容。 它们还用于将项目声明为记录，作为 Microsoft 365 数据的[记录管理](records-management.md)解决方案的一部分。

创建和配置保留标签的位置取决于你是否使用记录管理。 针对这两种情况提供了说明。

## <a name="before-you-begin"></a>准备工作

负责创建保留标签的合规性团队成员必须有权访问安全&amp;合规中心。 默认情况下，租户管理员有权访问此位置，并可向合规部主管及其他人员授予对安全&amp;合规中心的访问权限，而不授予租户管理员的所有权限。为此，建议转到安全&amp;合规中心内的“**权限**”页，编辑“**合规性管理员**”角色组，再向此角色组添加成员。 
  
有关详细信息，请参阅[向用户授予对 Office 365 安全与合规中心的访问权限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。
  
These permissions are required only to create and apply retention labels and a label policy. Policy enforcement does not require access to the content.

## <a name="create-and-configure-retention-labels"></a>创建和配置保留标签

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到以下位置之一：
    
    - 如果你正在使用记录管理：
        - “**解决方案**” > “**记录管理**” > “**文件计划**”选项卡 > + “**创建标签**” > “**保留标签**”
        
    - 如果你没有使用记录管理：
       - “**解决方案**” > “**信息治理**” > “**标签**”选项卡 > +“**创建标签**”
    
    没有立即看到你的选项？ 首先选择“**全部显示**”。 

2. 按照向导中的提示进行操作。 如果你正在使用记录管理：
    
    - 有关文件计划描述符的信息，请参阅[使用文件计划管理保留标签](file-plan-manager.md)
    
    - 要使用保留标签将内容声明为记录，请启用“**使用标签将内容分类为“记录”**”复选框。

3. 重复这些步骤以创建更多标签。

若要编辑现有标签，请将其选中，然后选择“**编辑标签**”启动同一向导，以便在步骤 2 中更改标签说明和任何[符合条件的设置](#updating-retention-labels-and-their-policies)。 或者，选择任意可用的**编辑**选项，直接转到相关页面进行更新。

## <a name="publish-retention-labels-by-creating-a-retention-label-policy"></a>通过创建保留标签策略发布保留标签

发布保留标签，以便用户可以可以手动应用它们。

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到以下位置之一：
    
    - 如果你正在使用记录管理：
        - “**解决方案**” > “**记录管理**”> >“**标签策略**”选项卡 >“**发布标签**”
    
    - 如果你没有使用记录管理：
        - “**解决方案**” > “**信息治理**” > “**标签策略**”选项卡 >“**发布标签**”
    
    没有立即看到你的选项？ 首先选择“**全部显示**”。 

2. 按照向导中的提示进行操作。
    
    有关保留标签支持的位置的信息，请参阅[保留标签和位置](labels.md#retention-label-policies-and-locations)部分。 

若要编辑现有保留标签策略，请将其选中，然后选择“**编辑策略**”启动同一向导，以便在步骤 2 中更改策略描述和任何[符合条件的设置](#updating-retention-labels-and-their-policies)。 或者，选择任意可用的**编辑**选项，直接转到相关页面进行更新。

## <a name="auto-apply-a-retention-label"></a>自动应用保留标签

根据指定的条件自动应用保留标签。

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到以下位置之一：
    
    - 如果你正在使用记录管理：“**信息治理**”：
        - “**解决方案**” > “**记录管理**” > “**标签策略**”选项卡 >“**自动应用标签**”
    
    - 如果你没有使用记录管理：
        - “**解决方案**” > “**信息治理**” > “**标签策略**”选项卡 >“**自动应用标签**”
    
    没有立即看到你的选项？ 首先选择“**全部显示**”。 

2. 按照向导中的提示进行操作。
    
    有关配置自动应用保留标签的条件的信息，请参阅此页面上的[配置自动应用保留标签的条件](#configuring-conditions-for-auto-apply-retention-labels)部分。
    
    有关保留标签支持的位置的信息，请参阅[保留标签和位置](labels.md#retention-label-policies-and-locations)部分。

若要编辑现有自动应用标签策略，请将其选中，然后选择“**编辑策略**”启动同一向导，以便在步骤 2 中更改策略描述和任何[符合条件的设置](#updating-retention-labels-and-their-policies)。 或者，选择任意可用的**编辑**选项，直接转到相关页面进行更新。


## <a name="configuring-conditions-for-auto-apply-retention-labels"></a>配置自动应用保留标签的条件

可将保留标签自动应用于包含以下各项的内容：
  
- [特定类型敏感信息](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [与你创建的查询匹配的特定关键字](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [可训练分类器的匹配项](#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![自动应用标签的“选择条件”页](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

自动应用保留标签最多可能需要 7 天才会应用到与你配置的条件相匹配的所有内容。

### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a>将标签自动应用于包含特定类型敏感信息的内容

为敏感信息创建自动应用保留标签时，可看到与创建数据丢失防护 (DLP) 策略时相同的策略模板列表。 预配置每个策略模板以查找特定类型的敏感信息。 例如，此处显示的模板用于查找美国 ITIN、SSN 和护照号码。 若要深入了解 DLP，请参阅[数据丢失防护策略概述](data-loss-prevention-policies.md)。
  
![包含敏感信息类型的策略模板](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:
  
- The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.
    
- The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75. Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence. Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition. 
    
要详细了解这些选项，请参阅[微调规则以增加或降低匹配的难度](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。
    
![用于确定敏感信息类型的选项](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a>将标签自动应用于包含关键字或可搜索属性的内容

You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.

有关查询语法的详细信息，请参阅：

- [关键字查询语言 (KQL) 语法参考](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

Query-based labels use the search index to identify content. For more information on valid searchable properties, see:

- [内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)
- [已爬网和托管属性在 SharePoint Server 中的概述](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

示例查询：

- Exchange
    - subject:"Quarterly Financials"
    - recipients:garthf<!--nolink-->@contoso.com
- SharePoint 和 OneDrive
    - contenttype:contract
    - site:https<!--nolink-->://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract

![查询编辑器](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a>使用可训练分类器向内容自动应用标签

选择可训练分类器的选项后，可选择其中一个内置分类器或选择自定义分类器。 内置分类器包含**简历**、**源代码**、**有针对性的骚扰**、**侮辱**和**威胁**：

![选择可训练分类器](../media/retention-label-classifers.png)

要通过此选项自动应用标签，SharePoint Online 网站和邮箱必须至少有 10 MB 的数据。

有关可训练分类器的详细信息，请参阅[可训练分类器（预览版）入门](classifier-getting-started-with.md)。

有关示例配置，请参阅[如何做好准备并使用内置分类器](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs)。

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a>保留标签需要多长时间才能生效

保留标签在发布或自动应用后不会立即生效：
  
1. 首先，需要将标签策略从管理中心同步到策略中的位置。
    
2. 然后，该位置可能需要一段时间才能使已发布的保留标签对最终用户可用或将标签自动应用到内容。 所需时间长短取决于保留标签的位置和类型。
    
### <a name="published-retention-labels"></a>已发布的保留标签

If you publish retention labels to SharePoint or OneDrive, those labels  typically appear for end users to select within one day. However, allow up to seven days. If you publish retention labels to Exchange, it can take up to seven days for those retention labels to appear for end users, and the mailbox must contain at least 10 MB of data.

例如：
  
![手动标签生效时间关系图](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a>自动应用保留标签

如果将保留标签自动应用于符合特定条件的内容，可能需要等待长达 7 天，才能将保留标签应用于与条件匹配的所有现有内容。
  
![自动应用标签生效时间关系图](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a>如何检查发布到 Exchange 的保留标签的状态

在 Exchange Online 中，保留标签通过每 7 天运行一次的进程向最终用户提供。 通过 Powershell，可看到此进程上次运行的时间，并进而确定其再次运行的时间。
  
1. [连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773)。
    
2. 运行下面这些命令。
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}   ```

In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox. If it has not happened since the time you created the policy, the labels are not going to appear. To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.
    
If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).
    

## Updating retention labels and their policies

When you edit a retention label, retention label policy, or auto-apply policy, and the retention label or policy is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.

Some settings can't be changed after the label or policy is created and saved, which include:
- The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.
- The option to classify as a record.

## Find the PowerShell cmdlets for retention labels

To use the retention label cmdlets:
  
1. [Connect to the Office 365 Security & Compliance Center Powershell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. Use these Office 365 Security & Compliance Center cmdlets:
    
    - [Get-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)
    
    - [New-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)
    
    - [Remove-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)
    
    - [Set-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)
    
    - [Enable-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)
    
    - [Get-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)
    
    - [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)
