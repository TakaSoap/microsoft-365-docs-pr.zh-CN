---
title: Microsoft 365 Defender中的威胁分析
ms.reviewer: ''
description: 了解新出现的威胁和攻击技术以及如何阻止它们。 评估它们对组织的影响，并评估组织复原能力。
keywords: 威胁分析、风险评估、Microsoft 365 Defender、M365D、缓解状态、安全配置、Microsoft Defender for Office 365、Microsoft Defender for Office 365 威胁分析、MDO 威胁分析、集成 MDE 和 MDO 威胁分析数据、威胁分析数据集成、集成Microsoft 365 Defender威胁分析
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 02d7a1e1d80d7891219c9bcf18076b858f4fb1b8
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663305"
---
# <a name="threat-analytics-in-microsoft-365-defender"></a>Microsoft 365 Defender中的威胁分析

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

> 想要体验 Microsoft 365 Defender？你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

威胁分析是 Microsoft 安全专家研究人员提供的产品内威胁情报解决方案。 它旨在帮助安全团队在面对新出现的威胁时尽可能高效，例如：

- 活动威胁执行组件及其活动
- 热门和新的攻击技术
- 严重漏洞
- 常见攻击面
- 流行的恶意软件

观看此简短视频，详细了解威胁分析如何帮助你跟踪最新威胁并阻止威胁。

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWwJfU]

可以从Microsoft 365安全门户导航栏的左上角或专用仪表板卡片访问威胁分析，该仪表板卡显示对组织的主要威胁（无论是在影响方面还是在暴露方面）。

:::image type="content" source="../../media/threat-analytics/ta_inlandingpage_mtp.png" alt-text="威胁分析登陆页" lightbox="../../media/threat-analytics/ta_inlandingpage_mtp.png":::

高影响威胁的最大可能造成伤害，而高暴露威胁是资产最容易受到的威胁。 了解活动或正在进行的活动以及了解如何通过威胁分析执行操作有助于为安全运营团队提供明智的决策。

_访问威胁分析的位置_

随着更复杂的对手和新威胁频繁且普遍出现，快速执行以下操作至关重要：

- 识别新出现的威胁并做出反应
- 了解当前是否受到攻击
- 评估威胁对资产的影响
- 查看抵御或暴露在威胁中的复原能力
- 确定可以采取的缓解、恢复或防护措施来阻止或包含威胁

每份报告都提供跟踪威胁的分析以及有关如何防御该威胁的广泛指导。 它还合并了网络中的数据，指示威胁是否处于活动状态，以及是否已实施适用的保护。

## <a name="view-the-threat-analytics-dashboard"></a>查看威胁分析仪表板

威胁分析仪表板 ([security.microsoft.com/threatanalytics3) ](https://security.microsoft.com/threatanalytics3) 突出显示与组织最相关的报表。 它总结了以下部分中的威胁：

- **最新威胁** - 列出最近发布的或更新的威胁报告，以及活动警报和已解决警报的数量。
- **影响最大的威胁** - 列出对组织影响最大的威胁。 本部分列出了活动和已解决警报数量最多的威胁。
- **最高曝光率** - 首先列出风险级别最高的威胁。 威胁的暴露级别是使用两条信息来计算的：与威胁关联的漏洞有多严重，以及组织中有多少设备可能被这些漏洞利用。

从仪表板中选择威胁以查看该威胁的报表。

:::image type="content" source="../../media/threat-analytics/ta_dashboard_mtp.png" alt-text="威胁分析仪表板" lightbox="../../media/threat-analytics/ta_dashboard_mtp.png":::

_威胁分析仪表板。还可以在与要读取的威胁分析报告相关的关键字中选择"搜索"字段作为键。_

## <a name="view-a-threat-analytics-report"></a>查看威胁分析报告

每个威胁分析报告提供以下几个部分的信息：

- [**概述**](#overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses)
- [**分析报告**](#analyst-report-get-expert-insight-from-microsoft-security-researchers)
- [**相关事件**](#related-incidents-view-and-manage-related-incidents)
- [**受影响的资产**](#impacted-assets-get-list-of-impacted-devices-and-mailboxes)
- [**阻止电子邮件尝试**](#prevented-email-attempts-view-blocked-or-junked-threat-emails)
- [**暴露&缓解措施**](#exposure-and-mitigations-review-list-of-mitigations-and-the-status-of-your-devices)

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a>概述：快速了解威胁、评估其影响并查看防御措施

" **概述** "部分提供详细分析师报告的预览。 它还提供了图表，其中突出显示了威胁对组织的影响，以及通过配置错误和未修补的设备公开的信息。

:::image type="content" source="../../media/threat-analytics/ta_overview_mtp.png" alt-text="威胁分析报告的概述部分" lightbox="../../media/threat-analytics/../../media/threat-analytics/ta_overview_mtp.png":::

_威胁分析报告的概述部分_

#### <a name="assess-impact-on-your-organization"></a>评估对组织的影响

每个报表都包含图表，旨在提供有关威胁对组织的影响的信息：

- **相关事件** - 使用以下数据概述跟踪的威胁对组织的影响：
  - 活动警报数及其关联的活动事件数
  - 活动事件的严重性
- **随时间推移的警报** - 显示随时间推移的相关 **活动** 警报和 **已解决** 警报数。 已解决的警报数表示组织响应与威胁关联的警报的速度。 理想情况下，图表应显示在几天内解析的警报。
- **受影响的资产** - 显示当前至少有一个与跟踪威胁关联的活动警报) 邮箱 (不同设备和电子邮件帐户的数量。 对于收到威胁电子邮件的邮箱，将触发警报。 查看组织级和用户级策略，了解导致发送威胁电子邮件的替代。
- **阻止的电子邮件尝试** - 显示过去七天内在传递前被阻止或传递到垃圾邮件文件夹的电子邮件数。

#### <a name="review-security-resilience-and-posture"></a>查看安全复原能力和态势

每个报表都包含图表，这些图表概述了组织对给定威胁的复原能力：

- **安全配置状态** - 显示配置错误的安全设置的设备数。 应用建议的安全设置来帮助缓解威胁。 如果设备已应用 _所有_ 跟踪设置，则它们被视为 **安全** 设备。
- **漏洞修补状态** - 显示易受攻击设备的数量。 应用安全更新或修补程序来解决受威胁利用的漏洞。

#### <a name="view-reports-per-threat-tags"></a>查看每个威胁标记的报表

可以根据特定的威胁标记 (类别) 或报表类型筛选威胁报告列表并查看最相关的报表。

- **威胁标记** - 帮助你根据特定的威胁类别查看最相关的报表。 例如，与勒索软件相关的所有报告。
- **报表类型** - 帮助你根据特定的报表类型查看最相关的报表。 例如，涵盖工具和技术的所有报表。
- **筛选器** - 帮助你高效地查看威胁报告列表，并根据特定的威胁标记或报表类型筛选视图。 例如，查看与勒索软件类别相关的所有威胁报告，或涵盖漏洞的威胁报告。

##### <a name="how-does-it-work"></a>它的工作原理是什么？

Microsoft 威胁情报团队已向每个威胁报告添加了威胁标记：

- 现在有四个威胁标记可用：
  - 勒索软件
  - 网络钓鱼
  - 漏洞
  - 活动组
- 威胁标记显示在威胁分析页面的顶部。 每个标记下的可用报表数都有计数器。

  :::image type="content" source="../../media/threat-analytics/ta-threattags-mtp.png" alt-text="威胁标记" lightbox="../../media/threat-analytics/ta-threattags-mtp.png":::

- 也可以按威胁标记对列表进行排序：

  :::image type="content" source="../../media/threat-analytics//ta-taglist-mtp.png" alt-text="&quot;威胁标记&quot;部分" lightbox="../../media/threat-analytics//ta-taglist-mtp.png":::

- 每个威胁标记和报表类型都提供筛选器：

  :::image type="content" source="../../media/threat-analytics/ta-threattag-filters-mtp.png" alt-text="&quot;筛选器&quot;页" lightbox="../../media/threat-analytics/ta-threattag-filters-mtp.png":::

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a>分析师报告：从 Microsoft 安全研究人员获取专家见解

在 **"分析师报告** "部分，阅读详细的专家写入。 大多数报告提供攻击链的详细说明，包括映射到 MITRE ATT&CK 框架的战术和技术、详尽的建议列表和强大的 [威胁搜寻](advanced-hunting-overview.md) 指南。

[详细了解分析师报告](threat-analytics-analyst-reports.md)

### <a name="related-incidents-view-and-manage-related-incidents"></a>相关事件：查看和管理相关事件

" **相关事件** "选项卡提供与跟踪的威胁相关的所有事件的列表。 可以分配事件或管理链接到每个事件的警报。 

:::image type="content" source="../../media/threat-analytics/ta_related_incidents_mtp.png" alt-text="威胁分析报告的相关事件部分" lightbox="../../media/threat-analytics/ta_related_incidents_mtp.png":::

_威胁分析报告的相关事件部分_

### <a name="impacted-assets-get-list-of-impacted-devices-and-mailboxes"></a>受影响的资产：获取受影响的设备和邮箱的列表

如果资产受到当前未解析的警报的影响，则会将其视为受影响。 " **受影响的资产** "选项卡列出了以下受影响的资产类型：

- **受影响的设备** - 未解析的终结点Microsoft Defender for Endpoint警报。 这些警报通常在看到已知的威胁指示器和活动时触发。
- **受影响的邮箱** - 已收到已触发Microsoft Defender for Office 365警报的电子邮件的邮箱。 虽然触发警报的大多数消息通常会被阻止，但用户或组织级别的策略可以替代筛选器。

:::image type="content" source="../../media/threat-analytics/ta_impacted_assets_mtp.png" alt-text="威胁分析报表中受影响的资产部分" lightbox="../../media/threat-analytics/ta_impacted_assets_mtp.png":::

_威胁分析报表中受影响的资产部分_

### <a name="prevented-email-attempts-view-blocked-or-junked-threat-emails"></a>阻止的电子邮件尝试：查看被阻止或被垃圾的威胁电子邮件

Microsoft Defender for Office 365通常会阻止具有已知威胁指示器的电子邮件，包括恶意链接或附件。 在某些情况下，检查可疑内容的主动筛选机制会将威胁电子邮件发送到垃圾邮件文件夹。 在任一情况下，威胁在设备上启动恶意软件代码的几率都会降低。

"**阻止的电子邮件尝试**"选项卡列出了在送达之前被阻止或通过Microsoft Defender for Office 365发送到垃圾邮件文件夹的所有电子邮件。

:::image type="content" source="../../media/threat-analytics/ta_prevented_email_attempts_mtp.png" alt-text="威胁分析报告的阻止电子邮件尝试部分" lightbox="../../media/threat-analytics/ta_prevented_email_attempts_mtp.png":::

_威胁分析报告的阻止电子邮件尝试部分_

### <a name="exposure-and-mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a>曝光和缓解措施：查看缓解措施列表和设备状态

在" **曝光&缓解** "部分中，查看可帮助你提高组织抵御威胁能力的特定可操作建议列表。 跟踪的缓解措施列表包括：

- **安全更新** - 部署在载入设备上发现的漏洞支持的软件安全更新
- **支持的安全配置**
  - 云端保护  
  - 可能不需要的应用程序 (PUA) 保护
  - 实时保护

本部分中的缓解信息包含来自[危险和漏洞管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)的数据，其中还提供了报表中各个链接的详细向下钻取信息。

:::image type="content" source="../../media/threat-analytics/ta_mitigations_mtp.png" alt-text="威胁分析报告的缓解部分，其中显示了安全配置详细信息" lightbox="../../media/threat-analytics/ta_mitigations_mtp.png":::

:::image type="content" source="../../media/threat-analytics/ta_mitigations_mtp2.png" alt-text="威胁分析报告的缓解部分，其中显示了漏洞详细信息" lightbox="../../media/threat-analytics/ta_mitigations_mtp2.png":::

_威胁分析报告&缓解部分曝光_

## <a name="set-up-email-notifications-for-report-updates"></a>设置报表更新的电子邮件通知

可以设置电子邮件通知，以便向你发送有关威胁分析报告的更新。

若要为威胁分析报告设置电子邮件通知，请执行以下步骤：

1. 在 **Microsoft 365 Defender** 边栏中选择设置。 从设置列表中选择 **Microsoft 365 Defender**。
 
!["设置"和"Microsoft 365 Defender"均以红色突出显示的屏幕截图](../../media/threat-analytics/ta_create_notification_0.png)

2. 选择 **"电子邮件通知** > **"，** 然后选择按钮 **"+ 创建通知规则**"。 将显示浮出控件。

!["+ 创建通知规则"以红色突出显示的屏幕截图](../../media/threat-analytics/ta_create_notification_1.png)

3. 按照浮出控件中列出的步骤进行操作。 首先，为新规则命名。 说明字段是可选的，但需要名称。 可以使用说明字段下的复选框打开或关闭规则。

> [!NOTE]
> 新通知规则的名称和说明字段仅接受英文字母和数字。 它们不接受空格、短划线、下划线或任何其他标点。

![命名屏幕的屏幕截图，其中填写了所有字段，并选中了"打开规则"复选框](../../media/threat-analytics/ta_create_notification_2.png)

4. 选择要收到通知的报表类型。 可以选择更新所有新发布的或更新的报表，或者仅更新具有特定标记或类型的报表。

![通知屏幕的屏幕截图，其中选择了勒索软件标记，并打开了类型下拉菜单](../../media/threat-analytics/ta_create_notification_3.png)

5. 添加至少一个收件人以接收通知电子邮件。 还可以通过发送测试电子邮件来使用此屏幕来检查通知的接收方式。

![收件人屏幕的屏幕截图。 列出了 3 个收件人，并且已发送测试电子邮件，如绿色复选标记所示](../../media/threat-analytics/ta_create_notification_4.png)

6. 查看新规则。 如果有任何要更改的内容，请选择每个子节末尾的 **"编辑"** 按钮。 审阅完成后，选择 **"创建规则** "按钮。

!["审阅"屏幕的屏幕截图。 编辑按钮以红色突出显示](../../media/threat-analytics/ta_create_notification_5.png)

7. 恭喜！ 新规则已成功创建。 选择 **"完成"** 按钮以完成该过程并关闭浮出控件。

![规则创建屏幕的屏幕截图。 成功创建的规则将沿侧栏显示绿色复选标记，并在屏幕的主区域中显示一个大的绿色复选](../../media/threat-analytics/ta_create_notification_6.png)

8. 新规则现在将显示在威胁分析电子邮件通知列表中。

![设置屏幕中电子邮件通知规则列表的屏幕截图](../../media/threat-analytics/ta_create_notification_7.png)

## <a name="additional-report-details-and-limitations"></a>其他报表详细信息和限制

> [!NOTE]
> 作为统一安全体验的一部分，威胁分析现在不仅适用于Microsoft Defender for Endpoint，还适用于适用于 Office E5 许可证持有者的 Microsoft Defender。
>
> 如果不使用Microsoft 365安全门户 (Microsoft 365 Defender) ，还可以在Microsoft Defender 安全中心门户中看到没有 Microsoft Defender Office数据) 的报表详细信息 ( (Microsoft Defender for Endpoint) 。

若要访问威胁分析报告，需要某些角色和权限。 有关详细信息，请参阅[基于角色的访问控制中的自定义角色Microsoft 365 Defender](custom-roles.md)。

- 若要查看警报、事件或受影响的资产数据，需要拥有 Microsoft Defender 的权限来Office或Microsoft Defender for Endpoint警报数据，或者两者兼有。
- 若要查看阻止的电子邮件尝试，需要有权访问 Microsoft Defender 以Office搜寻数据。
- 若要查看缓解措施，需要拥有Microsoft Defender for Endpoint中危险和漏洞管理数据的权限。

查看威胁分析数据时，请记住以下因素：

- 图表仅反映跟踪的缓解措施。 检查报表概述，了解图表中未显示的其他缓解措施。
- 缓解措施不能保证完全恢复能力。 提供的缓解措施反映了提高复原能力所需的最佳操作。
- 如果设备尚未将数据传输到服务，则它们将计为"不可用"。
- 与防病毒相关的统计信息基于Microsoft Defender 防病毒设置。 具有第三方防病毒解决方案的设备可以显示为"公开"。

## <a name="related-articles"></a>相关文章

- [通过高级搜寻主动查找威胁](advanced-hunting-overview.md)
- [了解分析师报告部分](threat-analytics-analyst-reports.md)
- [评估和解决安全漏洞和暴露问题](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
