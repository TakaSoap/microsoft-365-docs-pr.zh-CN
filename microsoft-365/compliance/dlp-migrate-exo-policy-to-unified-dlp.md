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
description: 了解如何规划Exchange联机数据丢失防护策略并将其迁移到 Microsoft 365 DLP。
ms.openlocfilehash: c6b941a0dd1f66e2f44494fded9ba47e8c3d7230
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760858"
---
# <a name="migrate-exchange-online-data-loss-prevention-policies-to-compliance-center"></a>将 Exchange Online 数据丢失防护策略迁移到合规中心

[Exchange Online已弃用 DLP) 策略 (数据丢失防护](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)。 [Microsoft 365合规中心](https://compliance.microsoft.com/datalossprevention?viewid=policies)提供[更丰富的 DLP 功能](dlp-learn-about-dlp.md)，包括 Exchange Online DLP。 可以使用 DLP 策略迁移向导来帮助你将Exchange Online DLP 策略转到要管理这些策略的合规中心。

迁移向导的工作原理是在Exchange中读取 DLP 策略的配置，然后在合规中心创建重复策略。 默认情况下，向导会在 **测试** 模式下创建新版本的策略，因此，你可以在不强制执行任何操作的情况下查看这些策略在环境中会产生的影响。 准备好完全过渡到合规中心版本后， **_必须_**：

1. 停用或删除Exchange管理中心 (EAC) 中的源策略。
1. 编辑策略的合规中心版本，并将其状态从 **“测试**”更改为 **“强制”。**

> [!WARNING]
> 如果在设置合规中心版本以 **强制实施** 这两组策略之前未删除或停用 EAC 中的源策略，则会尝试强制执行操作，并且会收到重复事件。 **_这是不受支持的配置。_**

迁移向导仅迁移 EXO 策略和关联的邮件流规则。 不迁移独立Exchange邮件流规则。

## <a name="migration-workflow"></a>迁移工作流

将 DLP 策略从Exchange迁移到合规中心中的统一 DLP 管理控制台有四个阶段。

1. 准备迁移
    1. 评估和比较Exchange Online (EXO) DLP 策略和合规中心 DLP 策略的重复功能。
    1. 确定要按原样引入的 EXO DLP 策略，可以使用向导来迁移这些策略。
    1. 确定要合并哪些 EXO DLP 策略并将其合并到Exchange管理中心，然后使用迁移向导将其引入合规中心。
1. 执行迁移 - 使用向导
1. 测试和验证 - 检查结果
1. 激活迁移的策略

## <a name="before-you-begin"></a>准备工作

### <a name="licensing-and-versions"></a>许可和版本

在开始迁移 DLP 策略之前，应确认[Microsoft 365订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)和任何加载项。

若要访问和使用策略迁移向导，必须具有其中一个订阅或加载项

- Microsoft 365 E3
- Microsoft 365 E5
- Microsoft 365 A5 (EDU)
- Microsoft 365 E5 合规
- Microsoft 365 A5 合规
- Microsoft 365 E5 信息保护和治理
- Microsoft 365 A5 信息保护和治理

有关 DLP 许可要求的详细列表，请参阅[Microsoft 365有关安全&合规性、数据丢失防护的许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

### <a name="permissions"></a>权限

用于运行迁移向导的帐户必须有权访问Exchange管理控制台 DLP 页和合规中心中的统一 DLP 控制台。

## <a name="prepare-for-migration"></a>准备迁移

1. 如果不熟悉 DLP、合规中心 DLP 控制台或Exchange管理中心 DLP 控制台，应在尝试策略迁移之前熟悉自己。
    1. [Exchange Online DLP) 策略 (数据丢失防护](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
    1. [了解 Microsoft 365 终结点数据丢失防护](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
    1. [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
1. 通过提出以下问题来评估Exchange DLP 和合规中心策略：

|问题|Action|迁移过程|
|---|---|---|
|是否仍需要策略？|如果没有，请删除或停用它|请勿迁移|
|它是否与任何其他Exchange或合规中心 DLP 策略重叠？|如果是，可以合并重叠的策略吗？|- 如果它与其他Exchange策略重叠，请在Exchange管理中心手动创建合并的 DLP 策略，然后使用迁移向导。 </br> - 如果它与现有合规中心策略重叠，可以修改现有的合规中心策略以匹配，不要迁移Exchange版本|
|Exchange DLP 策略的范围是否严格，是否具有明确定义的条件、操作、包含项和排除项？|如果是，最好使用向导进行迁移，记下策略，以便您记得稍后回来删除它|使用向导进行迁移|

## <a name="migration"></a>迁移

评估所有Exchange和合规中心 DLP 策略以了解需求和兼容性后，可以使用迁移向导。

1. 打开[Microsoft 365合规中心](https://compliance.microsoft.com/datalossprevention?viewid=policies) DLP 控制台。
2. 如果有Exchange可迁移的 DLP 策略，则页面顶部会显示一个横幅，告知你。
3. 在横幅中选择 **“迁移策略** ”以打开迁移向导。 列出了所有Exchange DLP 策略。 无法选择以前迁移的策略。
4. 选择要迁移的策略。 可以单独迁移它们，也可以使用分阶段方法或一次性全部迁移到组中。 选择 **下一步**。
5. 查看浮出窗格中是否有任何警告或消息。 在继续操作之前解决任何问题。
6. 选择希望在“ **活动**”、“ **测试**”或“ **已禁用**”中创建新的合规中心策略的模式。  默认值为 **Test**。 选择 **下一步**。
7. 如果需要，可以创建更多基于其他统一 DLP 位置的 Exchange DLP 策略的策略。 这会为迁移的Exchange策略生成一个新的统一 DLP 策略，并为您在此处选择的任何其他位置生成一个新的统一 DLP 策略。

   > [!IMPORTANT]
   > 其他 DLP 位置（如设备、SharePoint、OneDrive、本地、MCAS 或Teams聊天和频道消息）不支持的任何Exchange DLP 策略条件和操作都将从其他策略中删除。 此外，还必须为其他位置执行预先工作。 请参阅：
   >
   > - [了解 Microsoft 365 终结点数据丢失防护](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
   > - [终结点数据丢失防护入门](endpoint-dlp-getting-started.md#get-started-with-endpoint-data-loss-prevention)
   > - [使用终结点数据丢失防护](endpoint-dlp-using.md#using-endpoint-data-loss-prevention)
   > - [了解本地扫描程序Microsoft 365数据丢失防护](dlp-on-premises-scanner-learn.md#learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner)
   > - [本地扫描程序数据丢失防护入门](dlp-on-premises-scanner-get-started.md#get-started-with-the-data-loss-prevention-on-premises-scanner)
   > - [使用Microsoft 365本地扫描程序数据丢失防护](dlp-on-premises-scanner-use.md#use-the-microsoft-365-data-loss-prevention-on-premises-scanner)
   > - [对非 Microsoft 云应用使用数据丢失防护策略](dlp-use-policies-non-microsoft-cloud-apps.md#use-data-loss-prevention-policies-for-non-microsoft-cloud-apps)

8. 查看迁移向导会话设置。 选择 **下一步**。
9. 查看迁移报告。 请注意涉及Exchange邮件流规则的任何故障。 可以修复它们并重新迁移关联的策略。

迁移的策略现在将显示在合规中心 DLP 控制台中的 DLP 策略列表中。

## <a name="common-errors-and-mitigation"></a>常见错误和缓解措施

|错误消息|Reason|缓解/建议的步骤|
|---|---|---|
|方案 () 中已存在具有名称 `<Name of the policy>` 的符合性策略 `Dlp`。|此策略迁移很可能提前完成，然后在同一会话中重新进行|刷新会话以更新可用于迁移的策略列表。 以前迁移的所有策略都应处于 `Already migrated` 状态。|
|方案 () 中已存在具有名称 `<Name of the policy>` 的符合性策略 `Hold`。|同一租户中存在具有相同名称的保留策略。|- 将 EAC 中的 DLP 策略重命名为其他名称。 </br> - 重试受影响策略的迁移。|
|`DLP-group@contoso.com` 不能用作共享条件的值，因为它是通讯组或启用邮件的安全组。 使用谓词成员共享来检测某些组成员的活动。|传输规则允许在条件中使用组， `sender is` 但统一 DLP 不允许使用。|更新传输规则以从 `sender is` 条件中删除所有组电子邮件地址，并在必要时将组添加到 `sender is a member of` 条件。 重试受影响策略的迁移|
|找不到收件人 `DLP-group@contoso.com`。 如果新创建，请在一段时间后重试该操作。 如果已删除或过期，请重置有效值，然后重试。|在或`recipient is a member of`条件中`sender is a member of`使用的组地址可能已过期或无效。|- 删除/替换Exchange管理中心传输规则中所有无效的组电子邮件地址。 </br> - 重试受影响策略的迁移。|
|谓词中 `FromMemberOf` 指定的值必须是启用邮件的安全组。|传输规则允许在条件中使用单个用户， `sender is a member of` 但统一的 DLP 不允许使用。|- 更新传输规则以从 `sender is a member of` 条件中删除所有单个用户电子邮件地址，并在必要时将用户添加到 `sender is` 条件。 </br> - 重试受影响策略的迁移。|
|谓词中 `SentToMemberOf` 指定的值必须是启用邮件的安全组。|传输规则允许在条件下使用单个用户， `recipient is a member of` 但统一 DLP 不允许使用。|- 更新传输规则以从 `recipient is a member of` 条件中删除所有单个用户电子邮件地址，并在必要时将用户添加到 `recipient is` 条件。 </br> - 重试受影响策略的迁移。|
|`<Name of condition>`仅支持Exchange使用该参数。 删除此参数或仅打开Exchange位置。|合规中心中可能存在另一个名称相同的策略，其他位置（例如 SPO/ODB/Teams）不支持上述条件。|在Exchange管理中心重命名 DLP 策略并重试迁移。|

## <a name="testing-and-validation---prateek-and-aakash-to-provide-a-list-of-supported-predicates-and-known-issues-before-publishing--"></a>测试和验证 <!--PRATEEK AND AAKASH TO PROVIDE A LIST OF SUPPORTED PREDICATES AND KNOWN ISSUES BEFORE PUBLISHING-->

测试和查看策略。

1. 遵循 [“测试 DLP 策略](create-test-tune-dlp-policy.md#test-a-dlp-policy) ”过程。
2. 查看策略在 [活动资源管理器](data-classification-activity-explorer.md)中创建的事件。

## <a name="review-the-policy-matches-between-exchange-admin-center-dlp-and-microsoft-365-unified-dlp"></a>查看Exchange管理中心 DLP 与Microsoft 365统一 DLP 之间的策略匹配项

若要确保迁移的策略按预期运行，可以从两个管理中心导出报表，并进行策略匹配的比较。

1. 连接到 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。
2. 导出 [EAC DLP 报表](/powershell/module/exchange/get-maildetaildlppolicyreport)。 可以复制此 cmdlet 并插入相应的值：

   ```powershell
   Get-MailDetailDlpPolicyReport -StartDate <dd/mm/yyyy -EndDate <dd/mm/yyyy> -PageSize 5000 | select Date, MessageId, DlpPolicy, TransportRule -Unique | Export-CSV <"C:\path\filename.csv">
   ```

3. 导出 [统一 DLP 报表](/powershell/module/exchange/get-dlpdetailreport)。 可以复制此 cmdlet 并插入相应的值：

   ```powershell
   Get-DlpDetailReport -StartDate <dd/mm/yyyy> -EndDate <dd/mm/yyyy> -PageSize 5000 | select Date, Location, DlpCompliancePolicy, DlpComplianceRule -Unique | Export-CSV <"C:\path\filename.csv">
   ```

## <a name="activate-your-migrated-policies"></a>激活已迁移的策略

对迁移的策略的运行方式感到满意后，可以将其设置为 **“强制”。**

1. 打开Exchange管理中心 DLP 控制台。
2. 停用或删除源策略。
3. 打开[Microsoft 365合规中心](https://compliance.microsoft.com/datalossprevention?viewid=policies) DLP 控制台，然后选择要主动进行编辑的策略。
4. 将状态更改为 **打开**。

## <a name="related-articles"></a>相关文章

- [Exchange Online DLP) 策略 (数据丢失防护](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
- [了解数据丢失防护](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [活动资源管理器入门](data-classification-activity-explorer.md)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [根据模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
- [Exchange Online DLP) 策略 (数据丢失防护](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
