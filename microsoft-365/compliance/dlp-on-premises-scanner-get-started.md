---
title: 本地扫描程序Microsoft 365数据丢失防护入门
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
description: 设置 Microsoft 365 本地扫描仪数据丢失防护
ms.openlocfilehash: 1154a565f286cfafb5f1f03fdefbf3740b6e9907
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61942964"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner"></a>本地扫描程序数据丢失防护入门

本文将引导你完成 Microsoft 365 本地扫描仪数据丢失防护的先决条件和配置。

## <a name="before-you-begin"></a>准备工作

### <a name="skusubscriptions-licensing"></a>SKU/订阅许可

在开始使用终结点 DLP 之前，应该先确认 [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)以及任何加载项。 必须为设置 DLP 规则的管理员帐户分配以下许可证之一：

- Microsoft 365 E5
- Microsoft 365 E5 合规
- Microsoft 365 E5 信息保护和管控 


有关许可的详细信息，请参阅[适用于安全与合规性的 Microsoft 365 许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

### <a name="permissions"></a>权限

可在[活动资源管理器](data-classification-activity-explorer.md)中查看终结点 DLP 中的数据。 有四个角色可向活动资源管理器授予权限，用于访问数据的帐户必须是其中任何一个的成员。

- 全局管理员
- 合规性管理员
- 安全管理员
- 合规性数据管理员

#### <a name="roles-and-role-groups-in-preview"></a>预览版中的角色和角色组

预览版中有角色和角色组，你可以测试这些角色和角色组以微调访问控制。

下面是预览版中Microsoft 信息保护 （MIP） 角色的列表。 若要了解有关它们的详细信息，请参阅[安全与合规中心](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)中的角色

- 信息保护管理员
- 信息保护分析师
- 信息保护调查员
- 信息保护读者

下面是处于预览状态的 MIP 角色组的列表。 若要了解有关 的详细信息，请参阅[安全与合规中心](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#role-groups-in-the-security--compliance-center)中的角色组

- 信息保护
- 信息保护管理员
- 信息保护分析师
- 信息保护调查员
- 信息保护读者

### <a name="dlp-on-premises-scanner-prerequisites"></a>DLP 本地扫描仪先决条件

- Azure 信息保护 （AIP） 扫描仪实现 DLP 策略匹配和策略执行。将扫描仪作为 AIP 客户端一部分进行安装，因此安装必须满足 AIP、AIP 客户端和 AIP 统一标签扫描仪的所有先决条件。
- 部署 AIP 客户端和扫描程序。有关[安装 AIP 统一标记客户端](/azure/information-protection/rms-client/install-unifiedlabelingclient-app)和 [] 的详细信息，请参阅[配置和安装Azure 信息保护统一标签扫描程序](/azure/information-protection/deploy-aip-scanner-configure-install)。
- 必须至少在租户中发布一个标签和策略，即使所有检测规则都只基于敏感信息类型。

## <a name="deploy-the-dlp-on-premises-scanner"></a>部署 DLP 本地扫描仪

1. 请按照 [安装AIP统一标签客户端](/azure/information-protection/rms-client/install-unifiedlabelingclient-app)中的过程。 
2. 按照以下过程 [安装 Azure 信息保护统一标签扫描仪](/azure/information-protection/deploy-aip-scanner-configure-install) 完成扫描仪安装。
    1. 网络发现作业配置是一个可选步骤。 可以跳过它，并定义要扫描内容扫描作业的特定存储库。
    2. 必须创建内容扫描作业，并指定 DLP 引擎需要评估的托管文件的存储库。
    3. 在已创建的内容扫描作业中启用 DLP 规则，将 **强制** 选项设置为 **关闭**，除非想要直接进入 DLP 强制阶段。
3. 验证是否已将内容扫描作业分配到正确的群集。如果仍未创建内容扫描作业，请创建一个新作业，并将其分配给包含扫描程序节点的群集。

4. 连接到 Azure 门户 [Azure 信息保护扩展](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) 将存储库添加到将执行扫描的内容扫描作业。

5. 执行下列操作之一以运行扫描：
    1. 设置扫描仪计划
    1. 在门户 **手动** 立即扫描"选项
    1. 或运行 **-AIPScan** PowerShell cmdlet

   > [!IMPORTANT]
   > 请记住，默认情况下，扫描仪运行存储库的增量扫描，并且会跳过在上一扫描周期中扫描的文件，除非文件发生更改或启动完全重新扫描。可以通过使用UI中的 **“重新扫描所有文件”** 选项或通过运行 **Start-AIPScan-Reset** 来启动完全重新扫描。

6.  在 Microsoft 365 合规性管理中心中，打开“[数据丢失防护页面](https://compliance.microsoft.com/datalossprevention?viewid=policies)”。

7. 选择 **创建策略** 并创建测试 DLP 策略。 如果你需要 [帮助创建策略，请参阅](create-a-dlp-policy-from-a-template.md) 模板创建 DLP 策略。 请务必在测试中运行它，直到熟悉此功能。 将以下参数用于策略：
    1. 如有必要，将 DLP 本地扫描仪规则的范围设置到特定位置。 如果将扫描 **的位置****所有**，则通过扫描仪扫描的所有文件将受制于 DLP 规则匹配和强制。
    1. 指定位置时，可以使用排除列表或包含列表。 可定义规则仅与包含列表中列出的其中一个模式相匹配的路径相关，与包含列表中列出的所有文件（与包含列表中列出的模式相匹配的文件除外）的所有文件除外。 不支持任何本地路径。 以下是一些有效路径的示例：
      - \\\server\share
      - \\\server\share\folder1\subfolderabc
      - \*\\folder1
      - \*secret\*.docx
      - \*secret\*.\*
      - https:// sp2010.local/sites/HR
      - https://\*/HR 
    3. 以下是使用不可接受的值的一些示例：
      - \*
      - \*\\a
      - Aaa
      - c:\
      - C:\test

> [!IMPORTANT]
> 排除列表优先于包含项列表。

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a>在 DLP Alerts 管理仪表板中查看 DLP 本地扫描仪警报

1. 在 Microsoft 365 合规 [打开](https://compliance.microsoft.com/datalossprevention?viewid=policies) 数据丢失防护"页面，然后选择 **警报**。

2. 请参阅 [如何配置和查看 DLP 策略的警报](dlp-configure-view-alerts-policies.md) 中的过程，以查看你的终结点 DLP 策略警报。

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a>在活动资源管理器中查看 DLP 本地扫描仪和审核日志

> [!NOTE]
> 需要启用审核。本地扫描仪需要启用审核。 在 Microsoft 365 中，默认启用审核。

1. 在 Microsoft 365 合规 [打开域](https://compliance.microsoft.com/dataclassification?viewid=overview) 数据分类页面，然后选择活动资源管理器。

2. 请参阅活动 [工具入门](data-classification-activity-explorer.md) 中的过程，以访问和筛选本地扫描仪位置的所有数据。

3. 在合规 [中打开"审核"](https://security.microsoft.com/auditlogsearch)。 DLP 规则匹配项在审核日志 UI 中可用，或可通过 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell 访问 


## <a name="next-steps"></a>后续步骤
现在，你已载入设备，并且可以在“活动资源管理器”中查看活动数据，那么就可以继续下一步，在其中创建保护敏感项目的 DLP 策略。

- [使用 DLP 本地](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>另请参阅

- [了解 DLP 本地扫描程序](dlp-on-premises-scanner-learn.md)
- [使用 DLP 本地扫描程序](dlp-on-premises-scanner-use.md)
- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [活动资源管理器入门](data-classification-activity-explorer.md)
- [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)