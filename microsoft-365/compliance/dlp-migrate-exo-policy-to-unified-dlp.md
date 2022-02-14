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
description: 了解如何计划和将联机数据丢失防护Exchange迁移到 Microsoft 365 DLP。
ms.openlocfilehash: 07d0eb19155a7f91b30feb8d7938ea574b0e75f9
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2022
ms.locfileid: "62806152"
---
# <a name="migrate-exchange-online-data-loss-prevention-policies-to-compliance-center"></a>将 Exchange Online 数据丢失防护策略迁移到合规中心

[Exchange Online DLP (策略) 数据丢失](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)防护。 [Microsoft 365](dlp-learn-about-dlp.md)中心提供了更丰富的 DLP 功能，Exchange Online [DLP。](https://compliance.microsoft.com/datalossprevention?viewid=policies) 您可以使用 DLP 策略迁移向导，帮助您将 Exchange Online DLP 策略带到您将管理这些策略的合规性中心。

迁移向导的工作方式是阅读 DLP 策略的配置，Exchange然后在合规性中心创建重复的策略。 默认情况下，该向导在测试模式下创建新版本的策略，以便你可以查看它们对环境的影响，而无需强制执行任何操作。 准备好完全过渡到合规中心版本后，必须 **_：_**

1. 在 EAC 管理中心Exchange停用 (源) 。
1. 编辑策略的合规中心版本，将状态从 **"测试"更改为****"强制"**。 

> [!WARNING]
> 如果在将合规中心版本设置为"强制"之前未在 EAC 中删除或停用源策略，这两组策略都将尝试强制执行操作，并且您将收到重复事件。 **_这是不受支持的配置。_**


迁移向导仅迁移 EXO 策略和关联的邮件流规则。 不Exchange独立邮件流规则。

## <a name="migration-workflow"></a>迁移工作流

将 DLP 策略从 Exchange到合规性中心的统一 DLP 管理控制台分为四个阶段。  

1. 准备迁移
    1. 评估和比较 EXO Exchange Online (DLP 策略) 合规性中心 DLP 策略，了解重复功能。
    1. 确定要完全按照它们显示哪些 EXO DLP 策略，可以使用向导迁移这些策略。
    1. 确定要合并哪些 EXO DLP 策略，并Exchange管理中心中，然后使用迁移向导将其引入合规中心。
1. 执行迁移 - 使用向导
1. 测试和验证 - 检查结果
1. 激活迁移的策略

## <a name="before-you-begin"></a>开始之前

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

有关 DLP 许可要求的详细列表，请参阅Microsoft 365安全与合规、数据丢失防护&[许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)


### <a name="permissions"></a>权限

用于运行迁移向导的帐户必须具有对管理控制台 DLP Exchange和合规性中心统一 DLP 控制台的访问权限。

## <a name="prepare-for-migration"></a>准备迁移

1. 如果您不熟悉 DLP、合规性中心 DLP 控制台或 Exchange管理中心 DLP 控制台，您应该在尝试策略迁移之前熟悉一下。
    1. [Exchange Online DLP 策略 (数据丢失) 防护](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
    1. [了解 Microsoft 365 终结点数据丢失防护](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
    1. [创建、测试和调整 DLP 策略](create-test-tune-dlp-policy.md)
1. 通过提出Exchange来评估您的 DLP 和合规中心策略：


|问题  |Action  | 迁移过程|
|---------|---------|---------|
|是否仍然需要该策略？    |如果不是，请删除或停用它 |不迁移|
|是否与任何其他策略或Exchange DLP 策略重叠？     |如果是，可以合并重叠策略吗？         |- 如果与另一个Exchange策略重叠，请手动在管理中心Exchange合并 DLP 策略，然后使用迁移向导。 </br> - 如果与现有合规中心策略重叠，可以修改现有合规中心策略以匹配，不要迁移Exchange版本|
|DLP Exchange是否严格，并且其是否具有明确定义的条件、操作、包含和排除？     |如果是，则使用向导进行迁移是一个不错的选择，请记下该策略，以便你记住稍后返回以将其删除         | 使用向导进行迁移|

## <a name="migration"></a>迁移

在评估所有 Exchange 和合规中心 DLP 策略的需要和兼容性后，可以使用迁移向导。

1. 打开 Microsoft 365 [合规中心](https://compliance.microsoft.com/datalossprevention?viewid=policies) DLP 控制台。
2. 如果存在可Exchange DLP 策略，页面顶部将显示一个横幅，让您知道。
3. 选择 **横幅中的** "迁移策略"以打开迁移向导。 列出了Exchange DLP 策略。 无法选择以前迁移的策略。
4. 选择要迁移的策略。 可以单独迁移它们，或者使用分阶段方法分组迁移它们，也可以一次全部迁移。 选择“**下一步**”。
5. 查看飞出窗格，查看是否有警告或消息。 在继续操作之前解决任何问题。
6. 选择要在"活动"、"测试"或"已禁用"中创建 **新合规中心****策略的模式**。  默认值为 **Test**。 选择“**下一步**”。
7. 如果需要，可以创建基于其他统一 DLP 位置的 Exchange DLP 策略的更多策略。 这将为迁移的部署策略创建一个新的统一 DLP 策略Exchange一个新的统一 DLP 策略，为您在此处选取的其他任何位置创建一个新的统一 DLP 策略。

> [!IMPORTANT]
> Exchange DLP 位置（如设备、SharePoint、OneDrive、本地、MCAS 或 Teams 聊天和频道消息）不支持的任何 DLP 策略条件和操作都将从其他策略中删除。 此外，还必须为其他位置执行预工作。 请参阅：
>- [了解 Microsoft 365 终结点数据丢失防护](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
>- [终结点数据丢失防护入门](endpoint-dlp-getting-started.md#get-started-with-endpoint-data-loss-prevention)
>- [使用终结点数据丢失防护](endpoint-dlp-using.md#using-endpoint-data-loss-prevention)
>- [了解本地扫描程序Microsoft 365数据丢失防护](dlp-on-premises-scanner-learn.md#learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner)
>- [本地扫描程序数据丢失防护入门](dlp-on-premises-scanner-get-started.md#get-started-with-the-data-loss-prevention-on-premises-scanner)
>- [使用Microsoft 365本地扫描程序数据丢失防护](dlp-on-premises-scanner-use.md#use-the-microsoft-365-data-loss-prevention-on-premises-scanner)
>- [对非 Microsoft 云应用使用数据丢失防护策略](dlp-use-policies-non-microsoft-cloud-apps.md#use-data-loss-prevention-policies-for-non-microsoft-cloud-apps)
 
8. 查看迁移向导会话设置。 选择“**下一步**”。
9. 查看迁移报告。 注意涉及邮件流规则Exchange故障。 您可以修复它们并重新mimirate the associated policies。

迁移的策略现在将显示在合规性中心 DLP 控制台中的 DLP 策略列表中。 

## <a name="common-errors-and-mitigation"></a>常见错误和缓解
|错误消息  |Reason  | 缓解/建议步骤|
|---------|---------|---------|
|方案中已存在具有 `<Name of the policy>` 名称的合规性 () `Dlp`。    |此策略迁移可能在之前完成，然后在同一会话中重新尝试 |刷新会话以更新可用于迁移的策略列表。 所有以前迁移的策略都应在状态 `Already migrated` 中。|
|方案中已存在具有 `<Name of the policy>` 名称的合规性 () `Hold`。     |同一租户中存在同名的保留策略。       |- 将 EAC 中的 DLP 策略重命名为其他名称。 </br> - 重试迁移受影响的策略。 |
|`DLP-group@contoso.com` 不能用作"共享者"条件的值，因为它是通讯组或已启用邮件的安全组。 使用"由谓词的成员共享"来检测某些组的成员的活动。     |传输规则允许在条件中使用的 `sender is` 组，但统一 DLP 不允许这样做。         | 更新传输规则以从 `sender is` 条件中删除所有组电子邮件地址，并在必要时 `sender is a member of` 将组添加到条件。 重试迁移受影响的策略|
|找不到收件人 `DLP-group@contoso.com`。 如果新建，请在某个时间后重试该操作。 如果已删除或已过期，请使用有效值重置，然后重试。     |或 条件中使用的`sender is a member of``recipient is a member of`组地址可能已过期或无效。         | - 删除/替换管理中心传输规则中所有无效Exchange电子邮件地址。 </br> - 重试迁移受影响的策略。|
|谓词中指定的 `FromMemberOf` 值必须是启用邮件的安全组。     |传输规则允许在条件中使用的 `sender is a member of` 单个用户，但统一 DLP 不允许它。         | - 更新传输规则以从`sender is a member of``sender is`条件中删除所有用户电子邮件地址，如有必要，将用户添加到条件。 </br> - 重试迁移受影响的策略。|
|谓词中指定的 `SentToMemberOf` 值必须是启用邮件的安全组。    |传输规则允许在条件下使用单个用户 `recipient is a member of` ，但统一 DLP 不允许它。         | - 更新传输规则以从`recipient is a member of``recipient is`条件中删除所有用户电子邮件地址，如有必要，将用户添加到条件。 </br> - 重试迁移受影响的策略。|
|仅支持`<Name of condition>`将 参数用于Exchange。 删除此参数或仅打开Exchange位置。         | 合规性中心很可能存在另一个同名策略，其中的其他位置（如 SPO/ODB/Teams SPO/ODB/Teams不支持上述条件）。 | 在管理中心重命名 DLP Exchange并重试迁移。|

## <a name="testing-and-validation---prateek-and-aakash-to-provide-a-list-of-supported-predicates-and-known-issues-before-publishing--"></a>测试和验证 <!--PRATEEK AND AAKASH TO PROVIDE A LIST OF SUPPORTED PREDICATES AND KNOWN ISSUES BEFORE PUBLISHING-->

测试和查看策略。

1. 按照测试 [DLP 策略](create-test-tune-dlp-policy.md#test-a-dlp-policy) 过程操作。
2. 在"活动资源管理器"中查看策略 [创建的事件](data-classification-activity-explorer.md)。

## <a name="review-the-policy-matches-between-exchange-admin-center-dlp-and-microsoft-365-unified-dlp"></a>查看管理中心 DLP Exchange统一 DLP Microsoft 365策略匹配

若要确保迁移的策略按预期方式运行，可以从两个管理中心导出报告，并比较策略匹配项。

1. 连接到 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。
2. 导出 [EAC DLP 报告](/powershell/module/exchange/get-maildetaildlppolicyreport)。 您可以复制此 cmdlet 并插入适当的值：

```powershell
Get-MailDetailDlpPolicyReport -StartDate <dd/mm/yyyy -EndDate <dd/mm/yyyy> -PageSize 5000 | select Date, MessageId, DlpPolicy, TransportRule -Unique | Export-CSV <"C:\path\filename.csv"> 
```

3. 导出统 [一 DLP 报告](/powershell/module/exchange/get-dlpdetailreport)。 您可以复制此 cmdlet 并插入适当的值：

```powershell
Get-DlpDetailReport -StartDate <dd/mm/yyyy> -EndDate <dd/mm/yyyy> -PageSize 5000 | select Date, Location, DlpCompliancePolicy, DlpComplianceRule -Unique | Export-CSV <"C:\path\filename.csv">  
```

## <a name="activate-your-migrated-policies"></a>激活迁移的策略

对迁移的策略的运行方式感到满意后，可以将其设置为 **"强制"**。

1. 打开Exchange管理中心 DLP 控制台。
2. 停用或删除源策略。
3. 打开 [Microsoft 365 合规中心](https://compliance.microsoft.com/datalossprevention?viewid=policies) DLP 控制台，选择要使其处于活动状态的策略进行编辑。
4. 将状态更改为 **"打开"**。

## <a name="related-articles"></a>相关文章

- [Exchange Online DLP 策略 (数据丢失) 防护](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
- [了解数据丢失防护](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [活动资源管理器入门](data-classification-activity-explorer.md)
- [创建、测试和调整 DLP 策略](create-test-tune-dlp-policy.md)
- [从模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
- [Exchange Online DLP 策略 (数据丢失) 防护](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
