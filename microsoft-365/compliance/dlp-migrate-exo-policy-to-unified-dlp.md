---
title: 将 Exchange Online 数据丢失防护策略迁移到合规中心
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: 了解如何在 DLP 中计划和Exchange联机数据丢失防护策略Microsoft 365策略。
ms.openlocfilehash: c1929af423259de770d561421945d471c9022ab4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201873"
---
# <a name="migrate-exchange-online-data-loss-prevention-policies-to-compliance-center"></a>将 Exchange Online 数据丢失防护策略迁移到合规中心

[Exchange Online DLP (策略) ](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)数据丢失防护。 [更丰富的 DLP 功能](dlp-learn-about-dlp.md)（Exchange Online DLP）在 Microsoft 365[中心提供](https://compliance.microsoft.com/datalossprevention?viewid=policies)。 您可以使用 DLP 策略迁移向导来帮助将 Exchange Online DLP 策略带到您将管理这些策略的合规性中心。

迁移向导的工作方式是阅读 DLP 策略的配置，Exchange然后在合规性中心创建重复的策略。 默认情况下，该向导在测试模式下创建新版本的策略，以便你可以查看它们对环境的影响，而无需强制执行任何操作。 准备好完全过渡到合规中心版本后，**_你必须：_**

1. 在 EAC 管理中心Exchange停用或删除 (源) 。
1. 编辑策略的合规中心版本，将状态从"测试"**更改为****"强制"。** 

> [!WARNING]
> 如果在将合规中心版本设置为"强制"之前未在 EAC 中删除或停用源策略，这两组策略都将尝试强制执行操作，并且您将收到重复事件。 **_这是不受支持的配置。_**


迁移向导仅迁移 EXO 策略和关联的邮件流规则。 不Exchange独立邮件流规则。

## <a name="migration-workflow"></a>迁移工作流

将 DLP 策略从统一管理中心Exchange统一 DLP 管理控制台分为四个阶段。  

1. 准备迁移
    1. 评估和比较 EXO Exchange Online (DLP 策略) 合规性中心 DLP 策略是否重复。
    1. 确定要完全按照它们显示哪些 EXO DLP 策略，可以使用向导迁移这些策略。
    1. 确定要合并哪些 EXO DLP 策略并合并到 Exchange 管理中心，然后使用迁移向导将其引入合规中心。
1. 执行迁移 - 使用向导
1. 测试和验证 - 检查结果
1. 激活迁移的策略

## <a name="before-you-begin"></a>准备工作

### <a name="licensing-and-versions"></a>许可和版本

在开始迁移 DLP 策略之前，应该先确认Microsoft 365[订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)和任何加载项。 

若要访问和使用策略迁移向导，必须拥有以下订阅或加载项之一

- Microsoft 365 E3
- Microsoft 365 E5
- Microsoft 365 A5 (EDU)
- Microsoft 365 E5 合规
- Microsoft 365 A5 合规
- Microsoft 365 E5 信息保护和治理
- Microsoft 365 A5 信息保护和治理

有关 DLP 许可要求的详细列表，请参阅Microsoft 365合规性、数据丢失防护&[许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)


### <a name="permissions"></a>权限

用于运行迁移向导的帐户必须具有对管理控制台 DLP Exchange和合规性中心统一 DLP 控制台的访问权限。

## <a name="prepare-for-migration"></a>准备迁移

1. 如果您不熟悉 DLP、合规性中心 DLP 控制台或 Exchange管理中心 DLP 控制台，您应该在尝试策略迁移之前熟悉一下。
    1. [Exchange Online DLP 策略 (数据丢失) 防护](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
    1. [了解 Microsoft 365 终结点数据丢失防护](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
    1. [创建、测试和调整 DLP 策略](create-test-tune-dlp-policy.md)
1. 通过提出Exchange来评估您的 DLP 和合规中心策略：


|问题  |操作  | 迁移过程|
|---------|---------|---------|
|是否仍然需要该策略？    |如果不是，请删除或停用它 |不迁移|
|是否与任何其他策略或Exchange DLP 策略重叠？     |如果是，可以合并重叠策略吗？         |- 如果与另一Exchange策略重叠，请手动在管理中心Exchange合并 DLP 策略，然后使用迁移向导。 </br> - 如果与现有合规中心策略重叠，可以修改现有合规中心策略以匹配，不要迁移Exchange版本|
|DLP Exchange是否具有严格的作用域，并且是否具有明确定义的条件、操作、包含和排除？     |如果是，这是使用向导迁移的良好候选项，请记下该策略，以便以后记住返回以将其删除         | 使用向导进行迁移|

## <a name="migration"></a>迁移

在评估所有 Exchange 和合规中心 DLP 策略的需要和兼容性后，可以使用迁移向导。

1. 打开 Microsoft 365[合规中心](https://compliance.microsoft.com/datalossprevention?viewid=policies)DLP 控制台。
2. 如果存在可Exchange DLP 策略，页面顶部将显示一个横幅，让您知道。
3. 选择 **横幅中的** "迁移策略"以打开迁移向导。 列出了Exchange DLP 策略。 无法选择以前迁移的策略。
4. 选择要迁移的策略。 可以单独迁移它们，或者使用分阶段方法分组迁移它们，也可以一次全部迁移。 选择“**下一步**”。
5. 查看飞出窗格，查看是否有警告或消息。 在继续操作之前解决任何问题。
6. 选择您希望在 中创建的新合规性中心策略的模式，即 **"活动****"、"测试**"或"**已禁用"。**  默认值为 **测试**。 选择“**下一步**”。
7. 如果需要，可以创建基于其他统一 DLP 位置的 Exchange DLP 策略的其他策略。 这将为迁移的部署策略创建一个新的统一 DLP 策略Exchange一个新的统一 DLP 策略，以及您在此处选取的其他任何位置的一个新的统一 DLP 策略。

> [!IMPORTANT]
> Exchange DLP 位置（如设备、SharePoint、OneDrive、本地、MCAS 或 Teams 聊天和频道消息）不支持的任何 DLP 策略条件和操作都将从其他策略中删除。 此外，还必须为其他位置执行预工作。 请参阅：
>- [了解 Microsoft 365 终结点数据丢失防护](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
>- [终结点数据丢失防护入门](endpoint-dlp-getting-started.md#get-started-with-endpoint-data-loss-prevention)
>- [使用端点数据丢失防护](endpoint-dlp-using.md#using-endpoint-data-loss-prevention)
>- [了解本地扫描程序Microsoft 365数据丢失防护](dlp-on-premises-scanner-learn.md#learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner)
>- [本地扫描程序数据丢失防护入门](dlp-on-premises-scanner-get-started.md#get-started-with-the-data-loss-prevention-on-premises-scanner)
>- [使用Microsoft 365本地扫描程序数据丢失防护](dlp-on-premises-scanner-use.md#use-the-microsoft-365-data-loss-prevention-on-premises-scanner)
>- [对非 Microsoft 云应用使用数据丢失防护策略](dlp-use-policies-non-microsoft-cloud-apps.md#use-data-loss-prevention-policies-for-non-microsoft-cloud-apps)
 
8. 查看迁移向导会话设置。 选择“**下一步**”。
9. 查看迁移报告。 请注意涉及邮件流规则Exchange故障。 您可以修复它们，然后重新迁移关联的策略。

迁移的策略现在将显示在合规性中心 DLP 控制台中的 DLP 策略列表中。 

## <a name="testing-and-validation---prateek-and-aakash-to-provide-a-list-of-supported-predicates-and-known-issues-before-publishing--"></a>测试和验证 <!--PRATEEK AND AAKASH TO PROVIDE A LIST OF SUPPORTED PREDICATES AND KNOWN ISSUES BEFORE PUBLISHING-->

测试和查看策略。

1. 按照测试 [DLP 策略](create-test-tune-dlp-policy.md#test-a-dlp-policy) 过程操作。
2. 查看活动资源管理器中的策略 [创建的事件](data-classification-activity-explorer.md)。

## <a name="review-the-policy-matches-between-exchange-admin-center-dlp-and-microsoft-365-unified-dlp"></a>查看管理中心 DLP Exchange统一 DLP Microsoft 365策略匹配

若要确保迁移的策略按预期方式运行，可以从两个管理中心导出报告，并比较策略匹配项。

1. 连接到 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。
2. 导出 [EAC DLP 报告](/powershell/module/exchange/get-maildetaildlppolicyreport?view=exchange-ps)。 您可以复制此 cmdlet 并插入适当的值：

```powershell
Get-MailDetailDlpPolicyReport -StartDate <dd/mm/yyyy -EndDate <dd/mm/yyyy> -PageSize 5000 | select Date, MessageId, DlpPolicy, TransportRule -Unique | Export-CSV <"C:\path\filename.csv"> 
```
3. 导出统 [一 DLP 报告](/powershell/module/exchange/get-dlpdetailreport?view=exchange-ps)。 您可以复制此 cmdlet 并插入适当的值：

```powershell
Get-DlpDetailReport -StartDate <dd/mm/yyyy> -EndDate <dd/mm/yyyy> -PageSize 5000 | select Date, Location, DlpCompliancePolicy, DlpComplianceRule -Unique | Export-CSV <"C:\path\filename.csv">  
```

## <a name="activate-your-migrated-policies"></a>激活迁移的策略

对迁移的策略的运行方式感到满意后，可以将其设置为"强制 **"。**

1. 打开Exchange管理中心 DLP 控制台。
2. 停用或删除源策略。
3. 打开[Microsoft 365 合规中心](https://compliance.microsoft.com/datalossprevention?viewid=policies)DLP 控制台，选择要使其处于活动状态的策略进行编辑。
4. 将状态更改为 **"打开"。**

## <a name="related-articles"></a>相关文章

- [Exchange Online DLP 策略 (数据丢失) 防护](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
- [了解数据丢失防护](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [活动资源管理器入门](data-classification-activity-explorer.md)
- [创建、测试和调整 DLP 策略](create-test-tune-dlp-policy.md)
- [根据模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
- [Exchange Online DLP 策略 (数据丢失) 防护](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)