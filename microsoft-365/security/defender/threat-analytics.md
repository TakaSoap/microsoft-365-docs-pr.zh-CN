---
title: 威胁分析Microsoft 365 Defender
ms.reviewer: ''
description: 了解新出现的威胁和攻击技术以及如何阻止它们。 评估其对组织的影响，并评估组织的恢复能力。
keywords: 威胁分析， 风险评估， Microsoft 365 Defender， M365D， 缓解状态， 安全配置， 适用于 Office 365 的 Microsoft Defender， Office 365 威胁分析的 Microsoft Defender， MDO 威胁分析， 集成的 MDE 和 MDO 威胁分析数据， 威胁分析数据集成， 集成Microsoft 365 Defender威胁分析
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
ms.openlocfilehash: 40e14f0bb6e38a6923e5e1d454981d49932f7ea1
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2022
ms.locfileid: "64500686"
---
# <a name="threat-analytics-in-microsoft-365-defender"></a>威胁分析Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

> 想要体验 Microsoft 365 Defender？你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

威胁分析是我们来自专业 Microsoft 安全研究人员的产品内威胁情报解决方案。 它旨在帮助安全团队尽可能高效地应对新出现的威胁，例如：

- 活动威胁参与者及其活动
- 热门和新的攻击技术
- 关键漏洞
- 常见攻击面
- 流行的恶意软件

观看此简短视频，详细了解威胁分析如何有助于跟踪和阻止最新威胁。

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWwJfU]

你可以从 Microsoft 365 安全门户导航栏的左上角访问威胁分析，也可以从向组织显示主要威胁的专用仪表板卡访问威胁分析，无论是影响方面还是曝光方面。

:::image type="content" source="../../media/threat-analytics/ta_inlandingpage_mtp.png" alt-text="威胁分析登录页面" lightbox="../../media/threat-analytics/ta_inlandingpage_mtp.png":::

高影响威胁具有最大危害的可能性，而高曝光威胁是资产最易受到的威胁。 了解活动或正在进行的市场活动，了解通过威胁分析可采取哪些措施，有助于让安全运营团队做出明智的决策。

_在何处访问威胁分析_

随着更复杂的对手和新威胁的频繁和普遍出现，必须能够快速：

- 识别并应对新出现的威胁
- 了解你当前是否受到攻击
- 评估威胁对资产的影响
- 查看抵御威胁或暴露给威胁的恢复能力
- 确定可用于停止或包含威胁的缓解、恢复或防护操作

每个报告都提供跟踪威胁的分析，并提供有关如何防御该威胁的广泛指南。 它还包含来自你的网络的数据，指示威胁是否处于活动状态以及是否具有适用的保护。

## <a name="view-the-threat-analytics-dashboard"></a>查看威胁分析仪表板

威胁分析仪表板 (security.microsoft.com/threatanalytics3 [) ](https://security.microsoft.com/threatanalytics3) 突出显示与组织最相关的报告。 它总结了以下各节中的威胁：

- **最新威胁** - 列出最新发布或更新的威胁报告，以及活动警报和已解决警报数。
- **高影响威胁** - 列出对组织影响最大的威胁。 本节首先列出活动警报和已解决警报数最高的威胁。
- **最高曝光** — 首先列出曝光级别最高的威胁。 威胁的曝光级别使用两条信息进行计算：与威胁关联的漏洞程度，以及组织中有多少设备被这些漏洞利用。

从仪表板中选择威胁以查看该威胁的报告。

:::image type="content" source="../../media/threat-analytics/ta_dashboard_mtp.png" alt-text="威胁分析仪表板" lightbox="../../media/threat-analytics/ta_dashboard_mtp.png":::

_威胁分析仪表板。还可以选择与你要阅读的威胁分析报告相关的关键字中的"搜索"字段作为关键字键。_

## <a name="view-a-threat-analytics-report"></a>查看威胁分析报告

每个威胁分析报告分几节提供相关信息：

- [**概述**](#overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses)
- [**分析报告**](#analyst-report-get-expert-insight-from-microsoft-security-researchers)
- [**相关事件**](#related-incidents-view-and-manage-related-incidents)
- [**影响的资产**](#impacted-assets-get-list-of-impacted-devices-and-mailboxes)
- [**阻止的电子邮件尝试**](#prevented-email-attempts-view-blocked-or-junked-threat-emails)
- [**曝光&缓解**](#exposure-and-mitigations-review-list-of-mitigations-and-the-status-of-your-devices)

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a>概述：快速了解威胁、评估其影响并审查防御

" **概述** "部分提供详细分析员报告的预览。 它还提供了突出显示威胁对组织的影响的图表，以及通过错误配置和未修补的设备暴露的图表。

:::image type="content" source="../../media/threat-analytics/ta_overview_mtp.png" alt-text="威胁分析报告的概述部分" lightbox="../../media/threat-analytics/../../media/threat-analytics/ta_overview_mtp.png":::

_威胁分析报告的概述部分_

#### <a name="assess-impact-on-your-organization"></a>评估对组织的影响

每个报告都包括旨在提供有关威胁的组织影响的图表：

- **相关事件** -通过以下数据概述了跟踪的威胁对组织的影响：
  - 活动警报数及其关联的活动事件数
  - 活动事件的严重性
- **一段时间的警报** 显示一段时间的相关 **活动****警报和已** 解决警报数。 已解决的警报数指示组织响应与威胁关联的警报的有多快。 理想情况下，图表应显示几天内解决的警报。
- **"受** 影响资源" 显示当前至少具有一个与 (关联的活动警报) 邮箱中的不同设备和电子邮件帐户的数量。 对于收到威胁电子邮件的邮箱，将触发警报。 查看组织级别和用户级别的策略，查看导致发送威胁电子邮件的覆盖。
- **阻止的电子邮件尝试** - 显示过去七天内在传递前被阻止或传递到垃圾邮件文件夹的电子邮件数量。

#### <a name="review-security-resilience-and-posture"></a>查看安全恢复和状态

每个报告都包括一些图表，这些图表概述了组织对给定威胁的复原能力：

- **安全配置** 状态 — 显示安全设置错误的设备数量。 应用建议的安全设置以帮助缓解威胁。 如果设备已 **应用** 所有跟踪设置，则被视为安全设备。
- **漏洞修补状态** 显示易受攻击的设备的数量。 应用安全更新或修补程序以解决威胁利用的漏洞。

#### <a name="view-reports-per-threat-tags"></a>查看每个威胁标记的报告

你可以根据特定威胁标记或报告类型筛选威胁报告列表 (相关) 报告。

- **威胁** 标记 -帮助你根据特定威胁类别查看最相关的报告。 例如，所有与勒索软件相关的报告。
- **报告** 类型 - 帮助您根据特定报告类型查看最相关的报告。 例如，涵盖工具和技术的所有报告。
- **筛选器** - 帮助你高效地查看威胁报告列表，并基于特定威胁标记或报告类型筛选视图。 例如，查看与勒索软件类别相关的所有威胁报告或包含漏洞的威胁报告。

##### <a name="how-does-it-work"></a>它的工作原理是什么？

Microsoft 威胁智能团队向每个威胁报告添加了威胁标记：

- 现在，有四个威胁标记可用：
  - 勒索软件
  - 网络钓鱼
  - 漏洞
  - 活动组
- 威胁标记在威胁分析页面顶部显示。 每个标记下存在可用报告数量的计数器。

  :::image type="content" source="../../media/threat-analytics/ta-threattags-mtp.png" alt-text="威胁标记" lightbox="../../media/threat-analytics/ta-threattags-mtp.png":::

- 该列表也可以按威胁标记排序：

  :::image type="content" source="../../media/threat-analytics//ta-taglist-mtp.png" alt-text="&quot;威胁标记&quot;部分" lightbox="../../media/threat-analytics//ta-taglist-mtp.png":::

- 筛选器可用于每个威胁标记和报告类型：

  :::image type="content" source="../../media/threat-analytics/ta-threattag-filters-mtp.png" alt-text="&quot;筛选器&quot;页" lightbox="../../media/threat-analytics/ta-threattag-filters-mtp.png":::

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a>分析员报告：从 Microsoft 安全研究人员获取专家见解

在" **分析员报告** "部分，通读详细的专家撰写。 大多数报告都提供攻击链的详细说明，包括映射到 MITRE ATT&CK 框架的策略和技术、详细的建议列表和强大的 [威胁](advanced-hunting-overview.md) 搜寻指南。

[详细了解分析员报告](threat-analytics-analyst-reports.md)

### <a name="related-incidents-view-and-manage-related-incidents"></a>相关事件：查看和管理相关事件

" **相关事件** "选项卡提供与跟踪威胁相关的所有事件的列表。 你可以分配事件或管理链接到每个事件的警报。 

:::image type="content" source="../../media/threat-analytics/ta_related_incidents_mtp.png" alt-text="威胁分析报告的相关事件部分" lightbox="../../media/threat-analytics/ta_related_incidents_mtp.png":::

_威胁分析报告的相关事件部分_

### <a name="impacted-assets-get-list-of-impacted-devices-and-mailboxes"></a>影响的资产：获取受影响设备和邮箱的列表

如果资产受未解决活动警报的影响，则认为资产受到影响。 " **影响的资产"** 选项卡列出了以下类型的受影响资产：

- **影响的设备** - 具有未解析的 Microsoft Defender for Endpoint 警报的终结点。 这些警报通常在看到已知威胁指示器和活动时触发。
- **影响邮箱** - 已接收已触发 Microsoft Defender 进行安全警报Office 365邮箱。 触发警报的多数消息通常会被阻止，但用户或组织级别的策略可以覆盖筛选器。

:::image type="content" source="../../media/threat-analytics/ta_impacted_assets_mtp.png" alt-text="威胁分析报告的&quot;影响的资产&quot;部分" lightbox="../../media/threat-analytics/ta_impacted_assets_mtp.png":::

_威胁分析报告的"影响的资产"部分_

### <a name="prevented-email-attempts-view-blocked-or-junked-threat-emails"></a>阻止的电子邮件尝试：查看阻止或垃圾邮件威胁电子邮件

Microsoft Defender for Office 365通常阻止具有已知威胁指示器（包括恶意链接或附件）的电子邮件。 在某些情况下，检查可疑内容的主动筛选机制会改为将威胁电子邮件发送到垃圾邮件文件夹。 在任一情况下，威胁在设备上启动恶意软件代码的可能性都降低了。

"**阻止的电子邮件尝试**"选项卡列出了所有在传递之前被阻止或由 Microsoft Defender 发送到垃圾邮件文件夹的电子邮件Office 365。

:::image type="content" source="../../media/threat-analytics/ta_prevented_email_attempts_mtp.png" alt-text="威胁分析报告的阻止的电子邮件尝试部分" lightbox="../../media/threat-analytics/ta_prevented_email_attempts_mtp.png":::

_威胁分析报告的"阻止的电子邮件尝试"部分_

### <a name="exposure-and-mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a>曝光和缓解：查看缓解列表和设备的状态

在 **"&** 缓解"部分，查看特定可操作建议的列表，这些建议可帮助你提高组织应对威胁的复原能力。 跟踪的缓解列表包括：

- **安全更新** - 部署在载入的设备上发现漏洞的受支持软件安全更新
- **支持的安全配置**
  - 云端保护  
  - PUA 保护 (可能不需要) 应用程序
  - 实时保护

本节中的缓解信息包含来自 [危险和漏洞管理 的数据，](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)其中还提供了报告中各个链接的详细深化信息。

:::image type="content" source="../../media/threat-analytics/ta_mitigations_mtp.png" alt-text="显示安全配置详细信息的威胁分析报告的缓解部分" lightbox="../../media/threat-analytics/ta_mitigations_mtp.png":::

:::image type="content" source="../../media/threat-analytics/ta_mitigations_mtp2.png" alt-text="显示漏洞详细信息的威胁分析报告的缓解部分" lightbox="../../media/threat-analytics/ta_mitigations_mtp2.png":::

_威胁&报告的曝光和缓解部分_

## <a name="set-up-email-notifications-for-report-updates"></a>设置报告更新的电子邮件通知

你可以设置将向您发送威胁分析报告更新的电子邮件通知。

若要为威胁分析报告设置电子邮件通知，请执行以下步骤：

1. 选择 **设置** 边栏中Microsoft 365 Defender"按钮。 Select **Microsoft 365 Defender** from the list of settings.
 
![Screenshot with "设置" and "Microsoft 365 Defender" both highlighted in red](../../media/threat-analytics/ta_create_notification_0.png)

2. Choose **Email** **notificationsThreat** >  analytics， and select the button， **+ Create a notification rule**. 将出现一个飞出图。

![突出显示为红色"+ 创建通知规则"的屏幕截图](../../media/threat-analytics/ta_create_notification_1.png)

3. 按照该飞出列表中列出的步骤操作。 首先，为新规则命名。 说明字段是可选的，但名称是必需的。 可以使用说明字段下的复选框打开或关闭规则。

> [!NOTE]
> 新通知规则的名称和说明字段仅接受英文字母和数字。 它们不接受空格、短划线、下划线或其他任何标点符号。

![命名屏幕的屏幕截图，已填写所有字段，并且选中了"打开规则"复选框](../../media/threat-analytics/ta_create_notification_2.png)

4. 选择要通知的报告类型。 您可以选择更新所有新发布的或更新的报告，也可以选择仅更新具有特定标记或类型的报告。

![通知屏幕的屏幕截图，选中勒索软件标记，并打开类型的下拉菜单](../../media/threat-analytics/ta_create_notification_3.png)

5. 添加至少一个收件人以接收通知电子邮件。 您还可以通过发送测试电子邮件，使用此屏幕检查通知的接收方法。

![收件人屏幕的屏幕截图。 列出了 3 个收件人，并且已发送测试电子邮件，如绿色选中标记所指示](../../media/threat-analytics/ta_create_notification_4.png)

6. 查看新规则。 如果要更改任何内容，请选择每个子节末尾的"编辑"按钮。 审阅完成后，选择"创建 **规则"** 按钮。

![评价屏幕的屏幕截图。 编辑按钮以红色突出显示](../../media/threat-analytics/ta_create_notification_5.png)

7. 恭喜！ 已成功创建新规则。 选择" **完成** "按钮以完成该过程并关闭该飞出控件。

![已创建规则屏幕的屏幕截图。 成功创建的规则将在边栏上显示绿色选中标记，在屏幕主区域中显示一个大绿色选中标记](../../media/threat-analytics/ta_create_notification_6.png)

8. 你的新规则现在将显示在威胁分析电子邮件通知列表中。

![屏幕中电子邮件通知规则列表的设置屏幕截图](../../media/threat-analytics/ta_create_notification_7.png)

## <a name="additional-report-details-and-limitations"></a>其他报告详细信息和限制

> [!NOTE]
> 作为统一安全体验的一部分，威胁分析现在不仅适用于 Microsoft Defender for Endpoint，还适用于适用于 Office E5 许可证持有者的 Microsoft Defender。
>
> 如果不使用 Microsoft 365 安全门户 (Microsoft 365 Defender) ，还可以在 Microsoft Defender 安全中心 门户 (适用于终结点) 的 Microsoft Defender 中查看报告详细信息 (，而无需使用 Microsoft Defender for Office) 数据。

若要访问威胁分析报告，你需要某些角色和权限。 有关详细信息[，请参阅基于角色的访问控制中的Microsoft 365 Defender](custom-roles.md)角色。

- 若要查看警报、事件或受影响的资产数据，你需要具有 Microsoft Defender for Office 或 Microsoft Defender for Endpoint 警报数据的权限，或同时拥有这两者的权限。
- 若要查看阻止的电子邮件尝试，你需要拥有 Microsoft Defender 的权限，才能Office数据。
- 若要查看缓解，你需要具有在 Microsoft Defender for Endpoint 危险和漏洞管理数据的权限。

查看威胁分析数据时，请记住以下因素：

- 图表仅反映跟踪的缓解。 查看报告概述，了解图表中未显示的其他缓解功能。
- 缓解不保证完全恢复。 提供的缓解反映了改进恢复能力所需的最佳可能操作。
- 如果设备尚未将数据传输到服务，则被视为"不可用"。
- 防病毒相关的统计信息基于Microsoft Defender 防病毒设置。 具有第三方防病毒解决方案的设备可能显示为"公开"。

## <a name="related-articles"></a>相关文章

- [使用高级搜寻主动查找威胁](advanced-hunting-overview.md)
- [了解分析员报告部分](threat-analytics-analyst-reports.md)
- [评估和解决安全漏洞和曝光](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
