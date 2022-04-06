---
title: 查看电子邮件安全报告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何查找和使用Microsoft 365 Defender门户中提供的电子邮件安全报告。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 44d09eefb065ee204dd90980dfe710d6b3ddb88e
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666781"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a>在Microsoft 365 Defender门户中查看电子邮件安全报告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Defender门户<https://security.microsoft.com>中提供了各种报表，可帮助你了解电子邮件安全功能（如Microsoft 365中的反垃圾邮件和反恶意软件功能）如何保护组织。 如果拥有 [必要的权限](#what-permissions-are-needed-to-view-these-reports)，可以查看和下载本文中所述的这些报表。

> [!NOTE]
>
> **电子邮件&协作报** 表页上的某些报表需要Microsoft Defender for Office 365。 有关这些报表的信息，请参阅[Microsoft 365 Defender门户中的"查看Defender for Office 365报表](view-reports-for-mdo.md)"。
>
> 与邮件流相关的报表现在位于Exchange管理中心。 有关这些报表的详细信息，请[参阅新Exchange管理中心的邮件流报表](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。

## <a name="email-security-report-changes-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender门户中的电子邮件安全报告更改

下表介绍了Microsoft 365 Defender门户中已替换、移动或弃用的Exchange Online Protection (EOP) 和Microsoft Defender for Office 365报表。

|已弃用的报表和 cmdlet|新报表和 cmdlet|消息中心 ID|Date|
|---|---|:---:|:---:|
|**URL 跟踪** <p> Get-URLTrace|[URL 保护报告](view-reports-for-mdo.md#url-protection-report) <p> [Get-SafeLinksAggregateReport](/powershell/module/exchange/get-safelinksaggregatereport) <br> [Get-SafeLinksDetailReport](/powershell/module/exchange/get-safelinksdetailreport)|MC2399999|2021 年 6 月|
|**已发送和接收电子邮件报告** <p> Get-MailTrafficReport <br> Get-MailDetailReport|[威胁防护状态报告](#threat-protection-status-report) <br> [邮件流状态报告](#mailflow-status-report) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport) <br> [Get-MailFlowStatusReport](/powershell/module/exchange/get-mailflowstatusreport)|MC236025|2021 年 6 月|
|**转发报表** <p> 无 cmdlet|[EAC 中的自动转发消息报表](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report) <p> 无 cmdlet|MC250533|2021 年 6 月|
|**保险箱附件文件类型报表** <p> Get-AdvancedThreatProtectionTrafficReport <br> Get-MailDetailMalwareReport|[威胁防护状态报告：通过电子邮件 \> 恶意软件查看数据](#view-data-by-email--malware-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|MC250532|2021 年 6 月|
|**保险箱附件消息处置报告** <p> Get-AdvancedThreatProtectionTrafficReport <br> Get-MailDetailMalwareReport|[威胁防护状态报告：通过电子邮件 \> 恶意软件查看数据](#view-data-by-email--malware-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|MC250531|2021 年 6 月|
|**电子邮件报告中检测到的恶意软件** <p> Get-MailTrafficReport <br> Get-MailDetailMalwareReport|[威胁防护状态报告：通过电子邮件 \> 恶意软件查看数据](#view-data-by-email--malware-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|MC250530|2021 年 6 月|
|**垃圾邮件检测报告** <p> Get-MailTrafficReport <br> Get-MailDetailSpamReport|[威胁防护状态报告：通过电子邮件 \> 垃圾邮件查看数据](#view-data-by-email--spam-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|MC250529|2021 年 10 月|
|Get-AdvancedThreatProtectionDocumentReport <p> Get-AdvancedThreatProtectionDocumentDetail|[Get-ContentMalwareMdoAggregateReport](/powershell/module/exchange/get-contentmalwaremdoaggregatereport) <p> [Get-ContentMalwareMdoDetailReport](/powershell/module/exchange/get-contentmalwaremdodetailreport)|TBA|2022 年 5 月|
|**Exchange传输规则报告** <p> [Get-MailTrafficPolicyReport](/powershell/module/exchange/get-mailtrafficpolicyreport) <br> [Get-MailDetailTransportRuleReport](/powershell/module/exchange/get-maildetailtransportrulereport)|[Exchange EAC 中的传输规则报表](/exchange/monitoring/mail-flow-reports/mfr-exchange-transport-rule-report) <p> [Get-MailTrafficPolicyReport](/powershell/module/exchange/get-mailtrafficpolicyreport) <br> [Get-MailDetailTransportRuleReport](/powershell/module/exchange/get-maildetailtransportrulereport)|MC316157|2022 年 4 月|
|Get-MailTrafficTopReport|[威胁防护状态报告：通过电子邮件 \> 恶意软件查看数据](#view-data-by-email--malware-and-chart-breakdown-by-detection-technology) <p> [Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <br> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport) <p> **注意**：Get-MailTrafficTopReport 中的加密报告功能没有替代方法。|MC315742|2022 年 4 月|

## <a name="compromised-users-report"></a>泄露的用户报告

> [!NOTE]
> 此报表在具有Exchange Online邮箱的Microsoft 365组织中可用。 它在独立Exchange Online Protection (EOP) 组织中不可用。

" **被入侵的用户** "报告显示在过去 7 天内标记为 **"可疑** "或 **"受限"** 的用户帐户数。 这些状态中的任一状态中的帐户都存在问题，甚至遭到入侵。 使用频繁时，可以使用报表在可疑或受限帐户中发现峰值甚至趋势。 有关被入侵用户的详细信息，请参阅 ["响应已泄露的电子邮件帐户](responding-to-a-compromised-email-account.md)"。

:::image type="content" source="../../media/compromised-users-report-widget.png" alt-text="&quot;电子邮件&quot;&协作报告页上的&quot;已泄露用户&quot;小组件" lightbox="../../media/compromised-users-report-widget.png":::

聚合视图显示过去 90 天的数据，详细信息视图显示过去 30 天的数据。

若要在Microsoft 365 Defender门户<https://security.microsoft.com>中查看报表，请转到 **"报** \> **表电子邮件"&协作** \> **电子邮件&协作报表**。 在 **"电子邮件&协作报告** "页上，找到 **"已入侵的用户** "，然后单击 **"查看详细信息**"。 若要直接转到报表，请打开 <https://security.microsoft.com/reports/CompromisedUsers>。

在 **"被入侵的用户** "页上，图表显示指定日期范围的以下信息：

- **受限**：由于模式高度可疑，用户帐户被限制不发送电子邮件。
- **可疑**：用户帐户已发送可疑电子邮件，并且有被限制发送电子邮件的风险。

下图的详细信息表显示了以下信息：

- **创建时间**
- **用户 ID**
- **操作**
- **标记**：有关用户标记的详细信息，请参阅 [用户标记](user-tags.md)。

可以通过单击" **筛选器** "并在浮出控件中选择一个或多个显示的以下值来筛选图表和详细信息表：

- **日期 (UTC)**： **开始日期** 和 **结束日期**。
- **活动**： **受限** 或 **可疑**
- **标记**： **所有** 或指定的用户标记 (包括优先级帐户) 。

配置完筛选器后，单击" **应用**"、" **取消**"或 **"清除"筛选器**。

在 **"已入侵的用户** "页上，"创建计划" ![图标。](../../media/m365-cc-sc-create-icon.png) **[创建计划](#schedule-report)**， ![请求报表图标。](../../media/m365-cc-sc-download-icon.png) **[请求报告](#request-report)** 和 ![导出图标。](../../media/m365-cc-sc-download-icon.png) **[导出](#export-report)** 按钮可用。

:::image type="content" source="../../media/compromised-users-report-activity-view.png" alt-text="&quot;已入侵的用户&quot;报表中的&quot;报表&quot;视图" lightbox="../../media/compromised-users-report-activity-view.png":::

## <a name="exchange-transport-rule-report"></a>Exchange传输规则报告

**Exchange传输规则** 报表显示了邮件流规则 (（也称为传输规则）对组织中传入和传出邮件) 的影响。

若要在Microsoft 365 Defender门户中查看报表，请转到 **"报** \> **表电子邮件"&协作** \> **电子邮件&协作报表**。 在 **"电子邮件&协作报告**"页上，找到 **Exchange传输规则**，然后单击 **"查看详细信息**"。 若要直接转到报表，请打开 <https://security.microsoft.com/reports/ETRRuleReport>。

:::image type="content" source="../../media/transport-rule-report-widget.png" alt-text="电子邮件&协作报表页上的Exchange传输规则小组件" lightbox="../../media/transport-rule-report-widget.png":::

在 **Exchange传输规则报表** 页上，以下各节介绍了可用的图表和数据。
> [!NOTE]
> **Exchange传输规则报表** 现已在 EAC 中提供。 有关详细信息，请参阅[新 EAC 中的Exchange传输规则报告](/exchange/monitoring/mail-flow-reports/mfr-exchange-transport-rule-report)。


### <a name="chart-breakdown-by-direction"></a>按方向划分的图表明细

:::image type="content" source="../../media/transport-rule-report-etr-direction-view.png" alt-text="Exchange传输规则报表中Exchange传输规则的方向视图" lightbox="../../media/transport-rule-report-etr-direction-view.png":::

如果 **按方向选择图表明细**，则可使用以下图表：

- **按Exchange传输规则查看数据**：受邮件流规则影响的 **入站** 和 **出站** 邮件数。
- **按 DLP 查看数据Exchange传输规则**：受数据丢失防护影响的 **入站** 和 **出站** 邮件数 (DLP) 邮件流规则。

下图下的详细信息表中显示了以下信息：

- **Date**
- **DLP 策略** (仅 **按 DLP Exchange传输规则查看数据**) 
- **传输规则**
- **主题**
- **发件人地址**
- **收件人地址**
- **严重性**
- **方向**

可以通过单击" **筛选器** "并在浮出控件中选择一个或多个显示的以下值来筛选图表和详细信息表：

- **日期 (UTC)** **开始日期** 和 **结束日期**。
- **方向**： **出站** 和 **入站**。
- **严重性**：**高严重性**、**中等严重性和****低严重性**

配置完筛选器后，单击" **应用**"、" **取消**"或 **"清除"筛选器**。

在 **Exchange传输规则报表** 页上，"创建计划"![图标。](../../media/m365-cc-sc-create-icon.png) **[创建计划](#schedule-report)**， ![请求报表图标。](../../media/m365-cc-sc-download-icon.png) **[请求报告](#request-report)** 和 ![导出图标。](../../media/m365-cc-sc-download-icon.png) **[导出](#export-report)** 按钮可用。

### <a name="chart-breakdown-by-severity"></a>按严重性划分的图表明细

:::image type="content" source="../../media/transport-rule-report-etr-severity-view.png" alt-text="Exchange传输规则报表中Exchange传输规则的严重性视图" lightbox="../../media/transport-rule-report-etr-severity-view.png":::

如果 **按严重性选择图表明细**，则可使用以下图表：

- **按Exchange传输规则查看数据**：**高严重性**、**中等严重性和****低严重性** 消息的数量。 将严重性级别设置为规则中的操作， (**使用严重性级别** 或 _SetAuditSeverity_) 审核此规则。 有关详细信息，请参阅[Exchange Online中的邮件流规则操作](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。

- **按 DLP 查看数据Exchange传输规则**：受 DLP 邮件流规则影响 **的高严重性**、**中等严重性和****低严重性** 邮件的数量。

下图下的详细信息表中显示了以下信息：

- **Date**
- **DLP 策略** (仅 **按 DLP Exchange传输规则查看数据**) 
- **传输规则**
- **主题**
- **发件人地址**
- **收件人地址**
- **严重性**
- **方向**

可以通过单击" **筛选器** "并在浮出控件中选择一个或多个显示的以下值来筛选图表和详细信息表：

- **日期 (UTC)** **开始日期** 和 **结束日期**
- **方向**： **出站** 和 **入站**
- **严重性**：**高严重性**、**中等严重性和****低严重性**

配置完筛选器后，单击" **应用**"、" **取消**"或 **"清除"筛选器**。

在 **Exchange传输规则报表** 页上，"创建计划"![图标。](../../media/m365-cc-sc-create-icon.png) **[创建计划](#schedule-report)**， ![请求报表图标。](../../media/m365-cc-sc-download-icon.png) **[请求报告](#request-report)** 和 ![导出图标。](../../media/m365-cc-sc-download-icon.png) **[导出](#export-report)** 按钮可用。

## <a name="forwarding-report"></a>转发报表

> [!NOTE]
> 此报表现已在 EAC 中提供。 有关详细信息，请 [参阅新 EAC 中的自动转发消息报表](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)。

## <a name="mailflow-status-report"></a>邮件流状态报告

**邮件流状态报表** 是一个智能报表，显示有关传入和传出电子邮件、垃圾邮件检测、恶意软件、标识为"良好"的电子邮件以及边缘上允许或阻止的电子邮件的信息。 这是唯一包含边缘保护信息的报表，并显示在允许Exchange Online Protection (EOP) 进入服务进行评估之前阻止了多少电子邮件。 请务必了解，如果将邮件发送到五个收件人，我们将其计数为五个不同的消息，而不是一条消息。

若要在Microsoft 365 Defender门户<https://security.microsoft.com>中查看报表，请转到 **"报** \> **表电子邮件"&协作** \> **电子邮件&协作报表**。 在 **"电子邮件&协作报表** "页上，找到 **"邮件流状态摘要** "，然后单击 **"查看详细信息**"。 若要直接转到报表，请打开 <https://security.microsoft.com/reports/mailflowStatusReport>。

:::image type="content" source="../../media/mail-flow-status-report-widget.png" alt-text="电子邮件&协作报表页上的邮件流状态摘要小组件" lightbox="../../media/mail-flow-status-report-widget.png":::

### <a name="type-view-for-the-mailflow-status-report"></a>邮件流状态报表的类型视图

:::image type="content" source="../../media/mail-flow-status-report-type-view.png" alt-text="邮件流状态报表中的&quot;类型&quot;视图" lightbox="../../media/mail-flow-status-report-type-view.png":::

在 **"邮件流状态"报表** 页上，默认情况下会选择" **类型** "选项卡。 该图表显示指定日期范围的以下信息：

- **好邮件**：确定不为垃圾邮件或用户或组织策略允许的电子邮件。
- **Total**
- **恶意软件**：被各种筛选器阻止为恶意软件的电子邮件。
- **网络钓鱼电子邮件**：被各种筛选器阻止为网络钓鱼的电子邮件。
- **垃圾邮件**：被各种筛选器阻止为垃圾邮件的电子邮件。
- **边缘保护**：在 EOP 或 Defender for Office 365 评估之前在边缘/外围被拒绝的电子邮件。
- **规则消息**：由邮件流规则处理的电子邮件 (也称为传输规则) 。

下图的详细信息表显示了以下信息：

- **方向**
- **Type**
- **24 小时**
- **3 天**
- **7 天**
- **15 天**
- **30 天**

可以通过单击" **筛选器** "并在浮出控件中选择一个或多个显示的以下值来筛选图表和详细信息表：

- **日期 (UTC)**： **开始日期** 和 **结束日期**。
- **邮件方向**： **入站** 和 **出站**。
- **类型**：
  - **好邮件**
  - **恶意软件**
  - **垃圾邮件**
  - **边缘保护**
  - **规则消息**
  - **钓鱼电子邮件**

配置完筛选器后，单击" **应用**"、" **取消**"或 **"清除"筛选器**。

返回" **邮件流状态"报表** 页，如果单击 **"选择类别以获取更多详细信息**"，则可以从以下值中进行选择：

- **网络钓鱼电子邮件**：此选择将转到 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。
- **电子邮件中的恶意软件**：此选择将转到 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。
- **垃圾邮件检测**：此选择将转到 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。
- **边缘阻止的垃圾邮件**：此选择将转到 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。

在 **"邮件流状态"报表** 页上，"创建计划" ![图标。](../../media/m365-cc-sc-create-icon.png) **[创建计划](#schedule-report)** 和 ![导出图标。](../../media/m365-cc-sc-download-icon.png) **[导出](#export-report)** 按钮可用。

### <a name="direction-view-for-the-mailflow-status-report"></a>邮件流状态报表的方向视图

:::image type="content" source="../../media/mail-flow-status-report-direction-view.png" alt-text="邮件流状态报表中的&quot;方向&quot;视图" lightbox="../../media/mail-flow-status-report-direction-view.png":::

如果单击 **"方向"** 选项卡，图表将显示指定日期范围的以下信息：

- **入境**
- **出站**

可以通过单击" **筛选器** "并在浮出控件中选择一个或多个显示的以下值来筛选图表和详细信息表：

- **日期 (UTC)**： **开始日期** 和 **结束日期**。
- **邮件方向**： **入站** 和 **出站**。
- **类型**：
  - **好邮件**
  - **恶意软件**
  - **垃圾邮件**
  - **边缘保护**
  - **规则消息**
  - **钓鱼电子邮件**

配置完筛选器后，单击" **应用**"、" **取消**"或 **"清除"筛选器**。

返回" **邮件流状态"报表** 页，如果单击 **"选择类别以获取更多详细信息**"，则可以从以下值中进行选择：

- **网络钓鱼电子邮件**：此选择将转到 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。
- **电子邮件中的恶意软件**：此选择将转到 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。
- **垃圾邮件检测**：此选择将转到 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。
- **边缘阻止的垃圾邮件**：此选择将转到 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。

在 **"邮件流状态"报表** 页上，"创建计划" ![图标。](../../media/m365-cc-sc-create-icon.png) **创建计划** 和 ![导出图标。](../../media/m365-cc-sc-download-icon.png) **导出** 按钮可用。

### <a name="mailflow-view-for-the-mailflow-status-report"></a>邮件流状态报表的邮件流视图

**"邮件流**"视图显示 Microsoft 的电子邮件威胁防护功能如何筛选组织中的传入和传出电子邮件。 此视图使用水平流图 (称为 _Sankey_ 关系图) 提供有关总电子邮件计数的详细信息，以及配置的威胁防护功能（包括边缘防护、反恶意软件、反钓鱼、反垃圾邮件和反欺骗）如何影响此计数。

:::image type="content" source="../../media/mail-flow-status-report-mailflow-view.png" alt-text="邮件流状态报表中的&quot;邮件流&quot;视图" lightbox="../../media/mail-flow-status-report-mailflow-view.png":::

聚合视图和详细信息表视图允许 90 天的筛选。

关系图中的信息由 **EOP** 或 **Defender for Office 365** 技术进行颜色编码。

该图被组织成以下水平带：

- **电子邮件带总数** ：此值始终首先显示。
- **边缘块** 和 **已处理** 的带：
  - **边缘块**：在边缘筛选并标识为边缘保护的消息。
  - **已处理**：筛选堆栈处理的消息。
- 结果带：
  - **规则块**：由Exchange邮件流规则处理的消息 (传输规则) 。
  - **恶意软件块**：由各种筛选器标识为恶意软件的消息。<sup>\*</sup>
  - **网络钓鱼块**：通过各种筛选器处理过程中标识为网络钓鱼的消息。<sup>\*</sup>
  - **垃圾邮件块**：通过各种筛选器处理过程中标识为垃圾邮件的消息。<sup>\*</sup>
  - **模拟块**：在Defender for Office 365中检测到为用户模拟或域模拟的消息。<sup>\*</sup>
  - **引爆块**：通过保险箱附件策略或Defender for Office 365中的链接策略 保险箱保险箱在文件或 URL 爆炸期间检测到的消息。<sup>\*</sup>
  - **已删除 ZAP**：通过零小时自动清除删除的消息 (ZAP) 。<sup>\*</sup>
  - **已传递**：由于允许，向用户传递的消息。<sup>\*</sup>

如果将鼠标悬停在关系图中的水平带上，则会看到相关消息的数量。

<sup>\*</sup> 如果单击此元素，将展开图表以显示更多详细信息。 有关展开的节点中每个元素的说明，请参阅 [检测技术](/office/office-365-management-api/office-365-management-activity-api-schema#detection-technologies)。

:::image type="content" source="../../media/mail-flow-status-report-mailflow-view-details.png" alt-text="邮件流状态报表中的&quot;邮件流&quot;视图中的网络钓鱼块详细信息" lightbox="../../media/mail-flow-status-report-mailflow-view-details.png":::

关系图下方的详细信息表显示了以下信息：

- **Date**
- **电子邮件总数**
- **边缘筛选**
- **规则消息**
- **反恶意软件引擎，保险箱附件，已筛选规则**
- **DMARC 模拟、欺骗、网络钓鱼筛选**
- **引爆检测**
- **已筛选反垃圾邮件**
- **已删除 ZAP**
- **检测到未检测到威胁的消息**

如果在详细信息表中选择一行，则会在显示的详细信息浮出控件中显示电子邮件计数的进一步细分。

可以通过单击" **筛选器** "并在浮出控件中选择一个或多个显示的以下值来筛选图表和详细信息表：

- **日期 (UTC)** **开始日期** 和 **结束日期**。
- **方向**： **出站** 和 **入站**。

配置完筛选器后，单击" **应用**"、" **取消**"或 **"清除"筛选器**。

回到 **"邮件流状态"报表** 页上，可以单击 **"显示趋势** "以查看显示的 **"邮件流趋势** "浮出控件中的趋势图。

:::image type="content" source="../../media/mail-flow-status-report-mailflow-view-show-trends.png" alt-text="邮件流状态报告中邮件流视图中的&quot;邮件流趋势&quot;浮出控件" lightbox="../../media/mail-flow-status-report-mailflow-view-show-trends.png":::

在 **"邮件流状态"报表** 页上，"导出" ![图标。](../../media/m365-cc-sc-download-icon.png) **导出** 按钮可用。

## <a name="malware-detections-report"></a>恶意软件检测报告

> [!NOTE]
> 此报表已弃用。 [威胁防护状态报](#threat-protection-status-report)表中提供了相同的信息。

## <a name="mail-latency-report"></a>邮件延迟报告

Defender for Office 365中的 **邮件延迟报告** 包含有关组织内遇到的邮件传递和引爆延迟的信息。 有关详细信息，请参 [阅"邮件延迟"报告](view-reports-for-mdo.md#mail-latency-report)。

## <a name="spam-detections-report"></a>垃圾邮件检测报告

> [!NOTE]
> 此报表已弃用。 [威胁防护状态报](#threat-protection-status-report)表中提供了相同的信息。

## <a name="spoof-detections-report"></a>欺骗检测报告

**欺骗检测** 报告显示有关因欺骗而被阻止或允许的消息的信息。 有关欺骗的详细信息，请参阅 [EOP 中的防欺骗保护](anti-spoofing-protection.md)。

报表的聚合视图允许 90 天的筛选，而详细信息视图仅允许十天的筛选。

若要在Microsoft 365 Defender门户中查看报表，请转到 **"报** \> **表电子邮件"&协作** \> **电子邮件&协作报表**。 在 **"电子邮件&协作报告** "页上，查找 **欺骗检测** ，然后单击 **"查看详细信息**"。 若要直接转到报表，请打开 <https://security.microsoft.com/reports/SpoofMailReport>。

:::image type="content" source="../../media/spoof-detections-widget.png" alt-text="电子邮件&协作报表页上的 Spoof 检测小组件" lightbox="../../media/spoof-detections-widget.png":::

图表显示以下信息：

- **通过**
- **失败**
- **SoftPass**
- **无**
- **其他**

将鼠标悬停在图表中 (数据点) 一天时，可以看到检测到的欺骗消息数以及原因。

可以通过单击" **筛选器** "并在浮出控件中选择一个或多个显示的以下值来筛选图表和详细信息表：

- **日期 (UTC)** **开始日期** 和 **结束日期**
- **结果**：
  - **通过**
  - **失败**
  - **SoftPass**
  - **无**
  - **其他**
- **欺骗类型**： **内部** 和 **外部**

:::image type="content" source="../../media/spoof-detections-report-page.png" alt-text="Microsoft 365 Defender门户中的&quot;欺骗邮件报表&quot;页" lightbox="../../media/spoof-detections-report-page.png":::

下图的详细信息表显示了以下信息：

- **Date**
- **欺骗用户**
- **发送基础结构**
- **欺骗类型**
- **结果**
- **结果代码**
- **SPF**
- **DKIM**
- **DMARC**
- **消息计数**

有关复合身份验证结果代码的详细信息，请参阅[Microsoft 365中的反垃圾邮件标头](anti-spam-message-headers.md)。

在 **"欺骗检测** "页上，"创建计划" ![图标。](../../media/m365-cc-sc-create-icon.png) **[创建计划](#schedule-report)**， ![请求报表图标。](../../media/m365-cc-sc-download-icon.png) **[请求报告](#request-report)** 和 ![导出图标。](../../media/m365-cc-sc-download-icon.png) **[导出](#export-report)** 按钮可用。

## <a name="submissions-report"></a>提交报告

**提交报告** 显示有关管理员已报告给 Microsoft 进行分析的项目的信息。 有关详细信息，请参阅 ["使用管理员提交"将可疑垃圾邮件、网络钓鱼、URL 和文件提交到 Microsoft](admin-submission.md)。

若要在Microsoft 365 Defender门户<https://security.microsoft.com>中查看报表，请转到 **"报** \> **表电子邮件"&协作** \> **电子邮件&协作报表**。 在 **"电子邮件&协作报告** "页上，找到 **"提交** "，然后单击 **"查看详细信息**"。 若要直接转到报表，请打开 <https://security.microsoft.com/adminSubmissionReport>。 若要转到 [Microsoft 365 Defender门户中的管理员提交](admin-submission.md)，请单击 **"转到提交**"。 管理员将能够查看过去 30 天的报表。

:::image type="content" source="../../media/submissions-report-widget.png" alt-text="电子邮件&协作报表页上的&quot;提交&quot;小组件" lightbox="../../media/submissions-report-widget.png":::

图表显示以下信息：

- **Pending**
- **已完成**

可以通过单击" **筛选器** "并在浮出控件中选择一个或多个显示的以下值来筛选图表和详细信息表：

- **报告日期**： **开始时间** 和 **结束时间**
- **提交类型**：
  - **电子邮件**
  - **URL**
  - **文件**
- **提交 ID**
- **网络消息 ID**
- **Sender**
- **名称**
- **提交者**
- **提交原因**：
  - **不是垃圾**
  - **网络钓鱼**
  - **恶意软件**
  - **垃圾邮件**
- **重新扫描状态**：
  - **Pending**
  - **已完成**

图下的详细信息表显示了相同的信息，并且具有与 **"电子邮件&协作** \> **提交**"的"**提交分析**"选项卡上相同的 **组** 或 **自定义列** 选项。 有关详细信息， [请参阅向 Microsoft 提交的视图管理员提交](admin-submission.md#view-admin-submissions-to-microsoft)。

在 **"提交** "页上，可以使用" **[导出](#export-report)** "按钮。

:::image type="content" source="../../media/submissions-report-page.png" alt-text="Microsoft 365 Defender门户中的&quot;提交报告&quot;页" lightbox="../../media/submissions-report-page.png":::

## <a name="threat-protection-status-report"></a>威胁防护状态报告

**威胁防护状态** 报告在 EOP 和 Defender for Office 365 中均可用;但是，报表包含不同的数据。 例如，EOP 客户可以查看有关电子邮件中检测到的恶意软件的信息，但不能查看[有关保险箱附件检测到的](mdo-for-spo-odb-and-teams.md)恶意文件的信息，SharePoint、OneDrive和Microsoft Teams。

该报表提供包含恶意内容的电子邮件计数，例如反恶意软件引擎阻止的文件或网站地址 (URL) 、[零小时自动清除 (ZAP) ](zero-hour-auto-purge.md)，以及反[钓鱼策略中的](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)[保险箱链接](safe-links.md)、[保险箱 附件](safe-attachments.md)和模拟保护功能等Defender for Office 365功能。 可以使用此信息来确定趋势或确定是否需要调整组织策略。

**注意**：请务必了解，如果将邮件发送到五个收件人，我们将其计数为五个不同的消息，而不是一条消息。

若要在Microsoft 365 Defender门户中查看报表，请转到 **"报** \> **表电子邮件"&协作** \> **电子邮件&协作报表**。 在 **"电子邮件&协作报告** "页上，找到 **威胁防护状态** ，然后单击 **"查看详细信息**"。 若要直接转到报表，请打开以下 URL 之一：

- Defender for Office 365：<https://security.microsoft.com/reports/TPSAggregateReportATP>
- EOP： <https://security.microsoft.com/reports/TPSAggregateReport>

:::image type="content" source="../../media/threat-protection-status-report-widget.png" alt-text="电子邮件&协作报告页上的威胁防护状态小组件" lightbox="../../media/threat-protection-status-report-widget.png":::

默认情况下，图表显示过去 7 天的数据。 如果在 **威胁防护状态报告** 页上单击"**筛选器**"，则可以选择 90 天的日期范围 (试用订阅可能限制为 30 天) 。 详细信息表允许筛选 30 天。

以下部分介绍了可用视图。

### <a name="view-data-by-overview"></a>按概述查看数据

:::image type="content" source="../../media/threat-protection-status-report-overview-view.png" alt-text="威胁防护状态报告中的概述视图" lightbox="../../media/threat-protection-status-report-overview-view.png":::

在" **视图数据概述** "视图中，图表中显示了以下检测信息：

- **电子邮件恶意软件**
- **电子邮件网络钓鱼**
- **电子邮件垃圾邮件**
- **内容恶意软件**

图表下方没有可用的详细信息表。

如果单击 **"筛选器**"，则可使用以下筛选器：

- **日期 (UTC)** **开始日期** 和 **结束日期**。
- **检测**：
  - **电子邮件恶意软件**
  - **电子邮件网络钓鱼**
  - **电子邮件垃圾邮件**
  - **内容恶意软件**
- **受**：**MDO** (Defender for Office 365) 和 **EOP** 保护。
- **标记**： **所有** 或指定的用户标记 (包括优先级帐户) 。 有关用户标记的详细信息，请参阅 [用户标记](user-tags.md)。
- **方向**：
  - **全部**
  - **入境**
  - **出站**
- **域**： **全部** 或 [已接受的域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **策略类型**：
  - **全部**
  - **反恶意软件**
  - **安全附件**
  - **防网络钓鱼**
  - **反垃圾邮件**
  - **邮件流规则** (传输规则) 
  - **其他**

配置完筛选器后，单击" **应用**"、" **取消**"或 **"清除"筛选器**。

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a>按检测技术按电子邮件 \> 网络钓鱼和图表明细查看数据

:::image type="content" source="../../media/threat-protection-status-report-phishing-detection-tech-view.png" alt-text="威胁防护状态报告中网络钓鱼电子邮件的检测技术视图" lightbox="../../media/threat-protection-status-report-phishing-detection-tech-view.png":::

> [!NOTE]
> 从 2021 年 5 月开始，电子邮件中的网络钓鱼检测已更新为包含网络钓鱼 URL **的消息附件** 。 此更改可能会将一些检测卷 **从"通过电子邮件 \> 恶意软件查看"视图中的数据** 转移到 **"通过电子邮件 \> 网络钓鱼"视图查看数据** 中。 换句话说，带有网络钓鱼 URL（传统上标识为恶意软件）的消息附件现在可能被标识为网络钓鱼。

在 **"按电子邮件 \> 网络钓鱼查看数据** "和 **"按检测技术划分的图表明细** "视图中，图表中显示了以下信息：

- **URL 恶意信誉**<sup>\*</sup>：由其他Microsoft 365客户Defender for Office 365爆炸生成的恶意 URL 信誉。
- **高级筛选器**：基于机器学习的网络钓鱼信号。
- **常规筛选器**：基于分析师规则的网络钓鱼信号。
- **欺骗组织内**：发送方正在尝试欺骗收件人域。
- **欺骗外部域**：发送方正在尝试欺骗其他一些域。
- **欺骗 DMARC**：消息上的 DMARC 身份验证失败。
- **模拟品牌**：基于发件人的知名品牌的模拟。
- **混合分析检测**
- **文件信誉**
- **指纹匹配**
- **URL 引爆信誉**<sup>\*</sup>
- **URL 引爆**<sup>\*</sup>
- **模拟用户**<sup>\*</sup>
- **模拟域**<sup>\*</sup>：模拟客户拥有或定义的域。
- **邮箱智能模拟**<sup>\*</sup>：模拟管理员定义或通过邮箱智能学习的用户。
- **文件引爆**<sup>\*</sup>
- **文件引爆信誉**<sup>\*</sup>
- **运动**<sup>\*</sup>

<sup>\*</sup>仅Defender for Office 365

在图表下方的详细信息表中，提供了以下信息：

- **Date**
- **主题**
- **发件人**
- **Recipients**
- **检测技术**
- **传递状态**
- **发件人 IP**
- **标记**：有关用户标记的详细信息，请参阅 [用户标记](user-tags.md)。

如果单击 **"筛选器**"，则可使用以下筛选器：

- **日期 (UTC)** **开始日期** 和 **结束日期**
- **检测**：与图表中的值相同。
- **受以下保护**：**MDO** (Defender for Office 365) 或 **EOP**
- **方向**：
  - **全部**
  - **入境**
  - **出站**
- **标记**： **所有** 或指定的用户标记 (包括优先级帐户) 。
- **域**： **全部** 或 [已接受的域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **策略类型**：
  - **全部**
  - **反恶意软件**
  - **安全附件**
  - **防网络钓鱼**
  - **反垃圾邮件**
  - **邮件流规则** (传输规则) 
  - **其他**
- **策略名称 (详细信息表视图仅)**： **全部** 或指定的策略。
- **收件人**

配置完筛选器后，单击" **应用**"、" **取消**"或 **"清除"筛选器**。

在 **"威胁防护状态** "页上，"创建计划" ![图标。](../../media/m365-cc-sc-create-icon.png) **[创建计划](#schedule-report)**， ![请求报表图标。](../../media/m365-cc-sc-download-icon.png) **[请求报告](#request-report)** 和 ![导出图标。](../../media/m365-cc-sc-download-icon.png) **[导出](#export-report)** 按钮可用。

### <a name="view-data-by-email--spam-and-chart-breakdown-by-detection-technology"></a>按检测技术按电子邮件 \> 垃圾邮件和图表明细查看数据

:::image type="content" source="../../media/threat-protection-status-report-spam-detection-tech-view.png" alt-text="威胁防护状态报告中垃圾邮件的检测技术视图" lightbox="../../media/threat-protection-status-report-spam-detection-tech-view.png":::

在 **"按电子邮件 \> 垃圾邮件查看数据** 和 **按检测技术划分的图表细分** "视图中，图表中显示了以下信息：

- **URL 恶意声誉**
- **高级筛选器**
- **常规筛选器**
- **混合分析检测**：多个筛选器促成了消息的判决。
- **指纹匹配**：由于先前的消息，消息标记为错误。
- **域信誉**：此消息被视为基于发件人域信誉的垃圾邮件。
- **批量**：检测到的项超出了用户的批量设置。
- **IP 信誉**：此消息被视为基于发送 IP 地址信誉的垃圾邮件。

在图表下方的详细信息表中，提供了以下信息：

- **Date**
- **主题**
- **发件人**
- **Recipients**
- **检测技术**
- **传递状态**
- **发件人 IP**
- **标记**：有关用户标记的详细信息，请参阅 [用户标记](user-tags.md)。

如果单击 **"筛选器**"，则可使用以下筛选器：

- **日期 (UTC)** **开始日期** 和 **结束日期**
- **检测**：与图表中的值相同。
- **方向**：
  - **全部**
  - **入境**
  - **出站**
- **标记**： **所有** 或指定的用户标记 (包括优先级帐户) 。
- **域**： **全部** 或 [已接受的域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **策略类型**：
  - **全部**
  - **反恶意软件**
  - **安全附件**
  - **防网络钓鱼**
  - **反垃圾邮件**
  - **邮件流规则** (传输规则) 
  - **其他**
- **策略名称 (详细信息表视图仅)**： **全部** 或指定的策略。
- **收件人**

配置完筛选器后，单击" **应用**"、" **取消**"或 **"清除"筛选器**。

在 **"威胁防护状态** "页上，"创建计划" ![图标。](../../media/m365-cc-sc-create-icon.png) **[创建计划](#schedule-report)**， ![请求报表图标。](../../media/m365-cc-sc-download-icon.png) **[请求报告](#request-report)** 和 ![导出图标。](../../media/m365-cc-sc-download-icon.png) **[导出](#export-report)** 按钮可用。

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a>按电子邮件 \> 恶意软件查看数据，按检测技术查看图表明细

:::image type="content" source="../../media/threat-protection-status-report-malware-detection-tech-view.png" alt-text="威胁防护状态报告中恶意软件的检测技术视图" lightbox="../../media/threat-protection-status-report-malware-detection-tech-view.png":::

> [!NOTE]
> 从 2021 年 5 月开始，电子邮件中的恶意软件检测已更新为在邮件附件中包含 **有害 URL** 。 此更改可能会 **通过电子邮件 \> 网络钓鱼视图** 将一些检测卷从视图数据中移出，并 **转移到"通过电子邮件 \> 恶意软件查看数据** "视图中。 换句话说，传统上标识为网络钓鱼的消息附件中的有害 URL 现在可能被标识为恶意软件。

在 **"通过电子邮件 \> 恶意软件查看数据** "和 **"按检测技术划分的图表明细** "视图中，图表中显示了以下信息：

- **文件引爆**<sup>\*</sup>：通过保险箱附件进行检测。
- **文件引爆信誉**<sup>\*</sup>：由Defender for Office 365引爆生成的所有恶意文件信誉。
- **文件信誉**
- **反恶意软件引擎**<sup>\*</sup>：来自反恶意软件引擎的检测。
- **反恶意软件策略文件类型块**：这些是由于邮件中标识的恶意文件类型而筛选出的电子邮件。
- **URL 恶意信誉**<sup>\*</sup>
- **URL 引爆**<sup>\*</sup>
- **URL 引爆信誉**<sup>\*</sup>
- **运动**<sup>\*</sup>

在图表下方的详细信息表中，提供了以下信息：

- **Date**
- **主题**
- **发件人**
- **Recipients**
- **检测技术**
- **传递状态**
- **发件人 IP**
- **标记**：有关用户标记的详细信息，请参阅 [用户标记](user-tags.md)。

如果单击 **"筛选器**"，则可使用以下筛选器：

- **日期 (UTC)** **开始日期** 和 **结束日期**
- **检测**：与图表中的值相同。
- **受以下保护**：**MDO** (Defender for Office 365) 或 **EOP**
- **方向**：
  - **全部**
  - **入境**
  - **出站**
- **标记**： **所有** 或指定的用户标记 (包括优先级帐户) 。
- **域**： **全部** 或 [已接受的域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **策略类型**：
  - **全部**
  - **反恶意软件**
  - **安全附件**
  - **防网络钓鱼**
  - **反垃圾邮件**
  - **邮件流规则** (传输规则) 
  - **其他**
- **策略名称 (详细信息表视图仅)**： **全部** 或指定的策略。
- **收件人**

配置完筛选器后，单击" **应用**"、" **取消**"或 **"清除"筛选器**。

在 **"保护状态** "页上，"创建计划" ![图标。](../../media/m365-cc-sc-create-icon.png) **[创建计划](#schedule-report)**， ![请求报表图标。](../../media/m365-cc-sc-download-icon.png) **[请求报告](#request-report)** 和 ![导出图标。](../../media/m365-cc-sc-download-icon.png) **[导出](#export-report)** 按钮可用。

### <a name="chart-breakdown-by-policy-type"></a>按策略类型划分的图表明细

:::image type="content" source="../../media/threat-protection-status-report-phishing-policy-type-view.png" alt-text="威胁防护状态报告中网络钓鱼电子邮件、垃圾邮件或恶意软件电子邮件的策略类型视图" lightbox="../../media/threat-protection-status-report-phishing-policy-type-view.png":::

在 **"通过电子邮件 \> 网络钓鱼查看数据**"、" **按电子邮件 \> 垃圾邮件查看数据**"或 **"按电子邮件 \> 查看数据"恶意软件** 视图中， **按策略类型选择图表明细** 显示图表中的以下信息：

- **反恶意软件**
- **保险箱附件**<sup>\*</sup>
- **防网络钓鱼**
- **反垃圾邮件**
- **邮件流规则** (也称为传输规则) 
- **其他**

在图表下方的详细信息表中，提供了以下信息：

- **Date**
- **主题**
- **发件人**
- **Recipients**
- **检测技术**
- **传递状态**
- **发件人 IP**
- **标记**：有关用户标记的详细信息，请参阅 [用户标记](user-tags.md)。

如果单击 **"筛选器**"，则可使用以下筛选器：

- **日期 (UTC)** **开始日期** 和 **结束日期**
- **检测**：
  - **URL 恶意信誉**<sup>\*</sup>：由其他Microsoft 365客户Defender for Office 365爆炸生成的恶意 URL 信誉。
  - **高级筛选器**：基于机器学习的网络钓鱼信号。
  - **常规筛选器**：基于分析师规则的网络钓鱼信号。
  - **欺骗组织内**：发送方正在尝试欺骗收件人域。
  - **欺骗外部域**：发送方正在尝试欺骗其他一些域。
  - **欺骗 DMARC**：消息上的 DMARC 身份验证失败。
  - **模拟品牌**：基于发件人的知名品牌的模拟。
  - **混合分析检测**
  - **文件信誉**
  - **指纹匹配**
  - **URL 引爆信誉**<sup>\*</sup>
  - **URL 引爆**<sup>\*</sup>
  - **模拟用户**<sup>\*</sup>
  - **模拟域**<sup>\*</sup>：模拟客户拥有或定义的域。
  - **邮箱智能模拟**<sup>\*</sup>：模拟管理员定义或通过邮箱智能学习的用户。
  - **文件引爆**<sup>\*</sup>
  - **文件引爆信誉**<sup>\*</sup>
  - **运动**<sup>\*</sup>
- **受以下保护**：**MDO** (Defender for Office 365) 或 **EOP**
- **方向**：
  - **全部**
  - **入境**
  - **出站**
- **标记**： **所有** 或指定的用户标记 (包括优先级帐户) 。
- **域**： **全部** 或 [已接受的域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **策略类型**：
  - **全部**
  - **反恶意软件**
  - **安全附件**
  - **防网络钓鱼**
  - **反垃圾邮件**
  - **邮件流规则** (传输规则) 
  - **其他**
- **策略名称 (详细信息表视图仅)**： **全部** 或指定的策略。
- **收件人**

<sup>\*</sup>仅Defender for Office 365

配置完筛选器后，单击" **应用**"、" **取消**"或 **"清除"筛选器**。

在 **"威胁防护状态** "页上，"创建计划" ![图标。](../../media/m365-cc-sc-create-icon.png) **[创建计划](#schedule-report)**， ![请求报表图标。](../../media/m365-cc-sc-download-icon.png) **[请求报告](#request-report)** 和 ![导出图标。](../../media/m365-cc-sc-download-icon.png) **[导出](#export-report)** 按钮可用。

### <a name="chart-breakdown-by-delivery-status"></a>按传递状态划分的图表明细

:::image type="content" source="../../media/threat-protection-status-report-phishing-delivery-status-view.png" alt-text="威胁防护状态报告中网络钓鱼电子邮件和恶意软件电子邮件的传递状态视图" lightbox="../../media/threat-protection-status-report-phishing-delivery-status-view.png":::

在 **"通过电子邮件 \> 网络钓鱼查看数据**"、" **通过电子邮件 \> 垃圾邮件查看数据**"或 **"通过电子邮件 \> 查看数据"恶意软件** 视图中，选择 **"按传递方式显示图表明细"状态** 会在图表中显示以下信息：

- **托管邮箱：收件箱**
- **托管邮箱：垃圾邮件**
- **托管邮箱：自定义文件夹**
- **托管邮箱：已删除的邮件**
- **转发**
- **本地服务器：已交付**
- **隔离**
- **交付失败**
- **下降**

在图表下方的详细信息表中，提供了以下信息：

- **Date**
- **主题**
- **发件人**
- **Recipients**
- **检测技术**
- **传递状态**
- **发件人 IP**
- **标记**：有关用户标记的详细信息，请参阅 [用户标记](user-tags.md)。

如果单击 **"筛选器**"，则可使用以下筛选器：

- **日期 (UTC)** **开始日期** 和 **结束日期**
- **检测**：
  - **URL 恶意信誉**<sup>\*</sup>：由其他Microsoft 365客户Defender for Office 365爆炸生成的恶意 URL 信誉。
  - **高级筛选器**：基于机器学习的网络钓鱼信号。
  - **常规筛选器**：基于分析师规则的网络钓鱼信号。
  - **欺骗组织内**：发送方正在尝试欺骗收件人域。
  - **欺骗外部域**：发送方正在尝试欺骗其他一些域。
  - **欺骗 DMARC**：消息上的 DMARC 身份验证失败。
  - **模拟品牌**：基于发件人的知名品牌的模拟。
  - **混合分析检测**
  - **文件信誉**
  - **指纹匹配**
  - **URL 引爆信誉**<sup>\*</sup>
  - **URL 引爆**<sup>\*</sup>
  - **模拟用户**<sup>\*</sup>
  - **模拟域**<sup>\*</sup>：模拟客户拥有或定义的域。
  - **邮箱智能模拟**<sup>\*</sup>：模拟管理员定义或通过邮箱智能学习的用户。
  - **文件引爆**<sup>\*</sup>
  - **文件引爆信誉**<sup>\*</sup>
  - **运动**<sup>\*</sup>
- **受以下保护**：**MDO** (Defender for Office 365) 或 **EOP**
- **方向**：
  - **全部**
  - **入境**
  - **出站**
- **标记**： **所有** 或指定的用户标记 (包括优先级帐户) 。
- **域**： **全部** 或 [已接受的域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **策略类型**：
  - **全部**
  - **反恶意软件**
  - **安全附件**
  - **防网络钓鱼**
  - **反垃圾邮件**
  - **邮件流规则** (传输规则) 
  - **其他**
- **策略名称 (详细信息表视图仅)**： **全部** 或指定的策略。
- **收件人**

<sup>\*</sup>仅Defender for Office 365

配置完筛选器后，单击" **应用**"、" **取消**"或 **"清除"筛选器**。

在 **"威胁防护状态** "页上，"创建计划" ![图标。](../../media/m365-cc-sc-create-icon.png) **[创建计划](#schedule-report)**， ![请求报表图标。](../../media/m365-cc-sc-download-icon.png) **[请求报告](#request-report)** 和 ![导出图标。](../../media/m365-cc-sc-download-icon.png) **[导出](#export-report)** 按钮可用。

### <a name="view-data-by-content--malware"></a>按内容 \> 恶意软件查看数据

:::image type="content" source="../../media/threat-protection-status-report-content-malware-view.png" alt-text="威胁防护状态报告中的内容恶意软件视图" lightbox="../../media/threat-protection-status-report-content-malware-view.png":::

在"**按内容\>恶意软件查看数据**"视图中，Microsoft Defender for Office 365组织的图表中显示以下信息：

- **反恶意软件引擎**：SharePoint中检测到的恶意文件、OneDrive和Microsoft Teams [Microsoft 365中的内置病毒检测](virus-detection-in-spo.md)。
- **MDO 引爆**：[保险箱附件检测到用于SharePoint、OneDrive和Microsoft Teams](mdo-for-spo-odb-and-teams.md)的恶意文件。
- **文件信誉**

在图表下方的详细信息表中，提供了以下信息：

- **日期 (UTC)**
- **附件的文件名**
- **工作负载**
- **检测技术**
- **文件大小**
- **上次修改用户**

如果单击 **"筛选器**"，则可使用以下筛选器：

- **日期 (UTC)** **开始日期** 和 **结束日期**
- **检测**： **反恶意软件引擎**、 **MDO 引爆** 和 **文件引爆**
- **工作负荷**：**Teams**、**SharePoint** 和 **OneDrive**

配置完筛选器后，单击" **应用**"、" **取消**"或 **"清除"筛选器**。

在 **"威胁防护状态** "页上，"创建计划" ![图标。](../../media/m365-cc-sc-create-icon.png) **[创建计划](#schedule-report)**， ![请求报表图标。](../../media/m365-cc-sc-download-icon.png) **[请求报告](#request-report)** 和 ![导出图标。](../../media/m365-cc-sc-download-icon.png) **[导出](#export-report)** 按钮可用。

### <a name="view-data-by-system-override-and-chart-breakdown-by-reason"></a>按系统替代查看数据，按原因查看图表明细

:::image type="content" source="../../media/threat-protection-status-report-system-override-view-breakdown-by-reason.png" alt-text="威胁防护状态报告中的&quot;消息重写&quot;和&quot;按原因划分的图表&quot;视图明细" lightbox="../../media/threat-protection-status-report-system-override-view-breakdown-by-reason.png":::

在 **"按系统替代的视图数据** "和 **"按原因划分的图表明细** "视图中，图表中显示了以下替代原因信息：

- **本地跳过**
- **IP 允许**
- **Exchange** 邮件流规则 (传输规则) 
- **组织允许的发件人**
- **组织允许的域**
- **未启用 ZAP**
- **用户保险箱发件人**
- **用户保险箱域**
- **网络钓鱼模拟**：有关详细信息，请参阅 [配置向用户传递第三方网络钓鱼模拟以及向 SecOps 邮箱发送未经筛选的消息](configure-advanced-delivery.md)。
- **第三方筛选器**

在图表下方的详细信息表中，提供了以下信息：

- **Date**
- **主题**
- **发件人**
- **Recipients**
- **系统重写**
- **发件人 IP**
- **标记**：有关用户标记的详细信息，请参阅 [用户标记](user-tags.md)。

如果单击 **"筛选器**"，则可使用以下筛选器：

- **日期 (UTC)** **开始日期** 和 **结束日期**
- **原因**：与图表相同的值。
- **传递位置**： **未启用垃圾邮件文件夹** 或 **SecOps 邮箱**。
- **方向**：
  - **全部**
  - **入境**
  - **出站**
- **标记**： **所有** 或指定的用户标记 (包括优先级帐户) 。
- **域**： **全部** 或 [已接受的域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **策略类型**： **全部**
- **策略名称 (详细信息表视图仅)**： **全部**
- **收件人**

配置完筛选器后，单击" **应用**"、" **取消**"或 **"清除"筛选器**。

在 **"威胁防护状态** "页上，"导出" ![图标。](../../media/m365-cc-sc-download-icon.png) **[导出](#export-report)** 按钮可用。

### <a name="view-data-by-system-override-and-chart-breakdown-by-delivery-location"></a>按系统重写查看数据，按传递位置查看图表细分

:::image type="content" source="../../media/threat-protection-status-report-system-override-view-breakdown-by-delivery-location.png" alt-text="威胁防护状态报告中的&quot;消息重写&quot;和&quot;按传递位置&quot;视图显示的图表明细" lightbox="../../media/threat-protection-status-report-system-override-view-breakdown-by-delivery-location.png":::

在 **"按系统覆盖的视图数据** "和 **"按传递位置视图划分的图表明细** "中，图表中显示了以下替代原因信息：

- **垃圾邮件文件夹未启用**
- **SecOps 邮箱**：有关详细信息，请参阅 [配置向用户传递第三方网络钓鱼模拟以及向 SecOps 邮箱发送未经筛选的消息](configure-advanced-delivery.md)。

在图表下方的详细信息表中，提供了以下信息：

- **Date**
- **主题**
- **发件人**
- **Recipients**
- **系统重写**
- **发件人 IP**
- **标记**：有关用户标记的详细信息，请参阅 [用户标记](user-tags.md)。

如果单击 **"筛选器**"，则可使用以下筛选器：

- **日期 (UTC)** **开始日期** 和 **结束日期**
- **原因**
  - **本地跳过**
  - **IP 允许**
  - **Exchange** 邮件流规则 (传输规则) 
  - **组织允许的发件人**
  - **组织允许的域**
  - **未启用 ZAP**
  - **用户保险箱发件人**
  - **用户保险箱域**
  - **网络钓鱼模拟**：有关详细信息，请参阅 [配置向用户传递第三方网络钓鱼模拟以及向 SecOps 邮箱发送未经筛选的消息](configure-advanced-delivery.md)。
  - **第三方筛选器**
- **传递位置**： **未启用垃圾邮件文件夹** 或 **SecOps 邮箱**。
- **方向**：
  - **全部**
  - **入境**
  - **出站**
- **标记**： **所有** 或指定的用户标记 (包括优先级帐户) 。 有关用户标记的详细信息，请参阅 [用户标记](user-tags.md)。
- **域**： **全部** 或 [已接受的域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- **策略类型**：
  - **全部**
  - **反恶意软件**
  - **保险箱附件**<sup>\*</sup>
  - **防网络钓鱼**
  - **反垃圾邮件**
  - **邮件流规则** (传输规则) 
  - **其他**
- **策略名称 (详细信息表视图仅)**： **全部**
- **收件人**

<sup>\*</sup>仅Defender for Office 365

配置完筛选器后，单击" **应用**"、" **取消**"或 **"清除"筛选器**。

在 **"威胁防护状态** "页上，"导出" ![图标。](../../media/m365-cc-sc-download-icon.png) **[导出](#export-report)** 按钮可用。

## <a name="top-malware-report"></a>顶级恶意软件报告

**顶部恶意软件** 报告显示 [EOP 中反恶意软件保护](anti-malware-protection.md)检测到的各种恶意软件。

若要在Microsoft 365 Defender门户中查看报表，请转到 **"报** \> **表电子邮件"&协作** \> **电子邮件&协作报表**。 在 **"电子邮件&协作报告** "页上，找到 **"热门恶意软件"** ，然后单击 **"查看详细信息**"。 若要直接转到报表，请打开 <https://security.microsoft.com/reports/TopMalware>。

:::image type="content" source="../../media/top-malware-report-widget.png" alt-text="&quot;电子邮件&quot;&协作报表页上的&quot;热门恶意软件&quot;小组件" lightbox="../../media/top-malware-report-widget.png":::

将鼠标悬停在饼图中的楔子上时，可以看到一种恶意软件的名称，以及检测到有多少消息具有该恶意软件。

在 **"顶部恶意软件"报表** 页上，将显示饼图的较大版本。 图表下方的详细信息表显示了以下信息：

- **顶级恶意软件**
- **Count**

如果单击 **"筛选器**"，可以指定一个日期范围，其中包含 **"开始日期** "和 **"结束日期**"。

在 **"顶部恶意软件** "页上，"创建计划" ![图标。](../../media/m365-cc-sc-create-icon.png) **[创建计划](#schedule-report)** 和 ![导出图标。](../../media/m365-cc-sc-download-icon.png) **[导出](#export-report)** 按钮可用。

:::image type="content" source="../../media/top-malware-report-view.png" alt-text="&quot;顶部恶意软件&quot;报表视图" lightbox="../../media/top-malware-report-view.png":::

## <a name="top-senders-and-recipients-report"></a>顶级发件人和收件人报告

EOP 和 Defender for Office 365 中都提供了 **顶级发件人和收件人** 报表;但是，报表包含不同的数据。 例如，EOP 客户可以查看有关顶级恶意软件、垃圾邮件和网络钓鱼 (欺骗) 收件人的信息，但不能查看通过[模拟保护](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)检测到[的保险箱附件](safe-attachments.md)或网络钓鱼检测到的恶意软件信息。

**顶级发件人和收件人** 显示组织中的热门邮件发件人，以及 EOP 检测到的邮件和Defender for Office 365保护功能的顶级收件人。 默认情况下，报表显示上周的数据，但数据可用于过去 90 天。

若要在Microsoft 365 Defender门户<https://security.microsoft.com>中查看报表，请转到 **"报** \> **表电子邮件"&协作** \> **电子邮件&协作报表**。 在 **"电子邮件&协作报表** "页上，找到 **"热门发件人和收件人"报** 表，然后单击 **"查看详细信息**"。 若要直接转到报表，请打开以下 URL 之一：

- Defender for Office 365：<https://security.microsoft.com/reports/TopSenderRecipientsATP>
- EOP： <https://security.microsoft.com/reports/TopSenderRecipient>

:::image type="content" source="../../media/top-senders-and-recipients-widget.png" alt-text="&quot;报表&quot;仪表板中的&quot;热门发件人和收件人&quot;小组件" lightbox="../../media/top-senders-and-recipients-widget.png":::

将鼠标悬停在饼图中的楔子上时，可以看到发件人或收件人的邮件数。

在 **"顶部发件人和收件人** "页上，将显示饼图的较大版本。 可使用以下图表：

- **显示顶级邮件发件人的数据** (这是默认视图) 
- **显示顶级邮件收件人的数据**
- **显示顶级垃圾邮件收件人的数据**
- **显示 EOP)  (顶级恶意软件收件人的数据**
- **显示顶级网络钓鱼收件人的数据**
- **显示 MDO)  (顶级恶意软件收件人的数据**
- **显示 MDO)  (顶级网络钓鱼收件人的数据**

数据会根据所选内容进行更改。

将鼠标悬停在饼图中的楔子上时，可以看到该特定发件人或收件人的消息计数。

下图的详细信息表显示发送方或收件人以及基于所选视图的消息计数。

可以通过单击" **筛选器** "并选择 **"开始日期** "和" **结束日期**"来筛选图表和详细信息表。

配置完筛选器后，单击" **应用**"、" **取消**"或 **"清除"筛选器**。

在 **"顶部发件人和收件人** "页上，"导出" ![图标。](../../media/m365-cc-sc-download-icon.png) **导出** 按钮可用。

:::image type="content" source="../../media/top-senders-and-recipients-report-view.png" alt-text="顶部发件人和收件人报表中的&quot;显示顶级邮件发件人数据&quot;视图" lightbox="../../media/top-senders-and-recipients-report-view.png":::

## <a name="url-protection-report"></a>URL 保护报告

**URL 保护报告** 仅在Microsoft Defender for Office 365中可用。 有关详细信息，请参阅 [URL 保护报告](view-reports-for-mdo.md#url-protection-report)。

## <a name="user-reported-messages-report"></a>用户报告的消息报告

> [!IMPORTANT]
> 若要使 **用户报告的消息** 报告正常工作，必须为Microsoft 365环境 **启用审核日志记录**。 通常是由在 Exchange Online 中分配为审核日志的角色执行。 有关详细信息，请参阅[打开或关闭Microsoft 365审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。

**用户报告的消息** 报表显示有关用户通过使用报表邮件 [加载](enable-the-report-message-add-in.md)项或 [报表网络钓鱼加载项](enable-the-report-phish-add-in.md)报告为垃圾邮件、网络钓鱼尝试或好邮件的电子邮件的信息。

若要在Microsoft 365 Defender门户中查看报表，请转到 **"报** \> **表电子邮件"&协作** \> **电子邮件&协作报表**。 在 **"电子邮件&协作报告** "页上，找到 **用户报告的消息** ，然后单击 **"查看详细信息**"。 若要直接转到报表，请打开 <https://security.microsoft.com/reports/userSubmissionReport>。 若要转到 [Microsoft 365 Defender门户中的管理员提交](admin-submission.md)，请单击 **"转到提交**"。

:::image type="content" source="../../media/user-reported-messages-widget.png" alt-text="电子邮件&协作报表页上的用户报告邮件小组件" lightbox="../../media/user-reported-messages-widget.png":::

可以通过单击" **筛选器** "并在浮出控件中选择一个或多个显示的以下值来筛选图表和详细信息表：

- **报告日期**： **开始时间** 和 **结束时间**
- **报告者**
- **电子邮件主题**
- **消息报告 ID**
- **网络消息 ID**
- **Sender**
- **报告原因**
  - **不是垃圾**
  - **网络钓鱼**
  - **垃圾邮件**
- **网络钓鱼模拟**： **是** 或 **否**

配置完筛选器后，单击" **应用**"、" **取消**"或 **"清除"筛选器**。

若要对条目进行分组，请单击 **"组** "，然后从下拉列表中选择以下值之一：

- **无**
- **原因**
- **Sender**
- **报告者**
- **重新扫描结果**
- **网络钓鱼模拟**

:::image type="content" source="../../media/user-reported-messages-report.png" alt-text="用户报告的消息报告" lightbox="../../media/user-reported-messages-report.png":::

下图的详细信息表显示了以下信息：

- **电子邮件主题**
- **报告者**
- **报告日期**
- **Sender**
- **报告原因**
- **重新扫描结果**
- **标记**：有关用户标记的详细信息，请参阅 [用户标记](user-tags.md)。

若要将消息提交给 Microsoft 进行分析，请从表中选择消息条目，单击 **"提交到 Microsoft 进行分析** "，然后从下拉列表中选择以下值之一：

- **报表干净**
- **报表网络钓鱼**
- **报告恶意软件**
- **报告垃圾邮件**'
- **触发调查** (Defender for Office 365) 

在 **"用户报告的消息** "页上，"导出" ![图标。](../../media/m365-cc-sc-download-icon.png) **[导出](#export-report)** 按钮可用。

## <a name="what-permissions-are-needed-to-view-these-reports"></a>查看这些报表需要哪些权限？

若要查看和使用本文中所述的报表，需要成为Microsoft 365 Defender门户中以下角色组之一的成员：

- **组织管理**
- **安全管理员**
- **安全信息读取者**
- **全局读取者**

有关详细信息，请参阅 [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)。

**注意**：将用户添加到Microsoft 365 管理中心中相应的Azure Active Directory角色，为用户提供Microsoft 365 Defender门户中所需的权限 _以及_ Microsoft 365中其他功能的权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。

## <a name="what-if-the-reports-arent-showing-data"></a>如果报表未显示数据，该怎么办？

如果未在报表中看到数据，请检查正在使用的筛选器，并仔细检查策略是否已正确设置。 若要了解详细信息，请参阅 ["防范威胁](protect-against-threats.md)"。

## <a name="schedule-report"></a>计划报表

1. 在特定报表的主页上，单击 !["创建计划"图标。](../../media/m365-cc-sc-create-icon.png) **创建计划**。
2. **"创建计划报表**"向导随即打开。 在 **"名称计划报** 表"页上，查看或自定义 **"名称"** 值，然后单击 **"下一步**"。
3. 在 **"设置首选项** "页上，配置以下设置：
   - **频率**：选择以下值之一：
     - **每周** (默认) 
     - **每月**
   - **开始日期**：开始生成报表的时间。 默认值为当前。
   - **到期日期**：报表生成结束时。 默认值为从今天起的一年。

   完成后，请单击“**下一步**”。

4. 在 **"收件人"** 页上，为报表选择收件人。 默认值是电子邮件地址，但可以添加其他地址。

   完成后，请单击“**下一步**”。

5. 在 **"审阅** "页上，查看所选内容。 可以单击相应部分中的 **"返回** "按钮或 **"编辑** "链接进行更改。

   完成后，请单击“**提交**”。

### <a name="managed-existing-scheduled-reports"></a>托管的现有计划报表

若要管理已创建的计划报表，请执行以下步骤：

1. 在Microsoft 365 Defender门户中<https://security.microsoft.com>，转到 **"报**\>表"展开 **电子邮件&协作**\>选择 **"管理计划**"。

   若要直接转到" **管理计划"** 页，请使用 <https://security.microsoft.com/ManageSubscription>。

2. 在 **"管理计划** "页上，为每个计划的报表显示以下信息：
   - **计划开始日期**
   - **计划名称**
   - **报告类型**
   - **Frequency**
   - **上次发送时间**

   查找要修改的现有计划报表。

3. 选择计划报表后，请在打开的详细信息浮出控件中执行以下任何操作：
   - **编辑名称**：单击此按钮，更改浮出控件中显示的报表的名称，然后单击" **保存**"。
   - **删除计划**：单击此按钮，阅读显示 (以前的报表将不再可用于下载) ，然后单击 **"保存**"。
   - **计划详细信息** 部分：单击 **"编辑首选项** "以更改以下设置：
     - **频率**： **每周** 或 **每月**
     - **开始日期**
     - **有效期**

     完成后，单击“**保存**”。

   - **"收件人"** 部分：单击 **"编辑收件人** "以添加或删除计划的报表的收件人。 完成后，单击" **保存"**

   完成后，单击“关闭”。

## <a name="request-report"></a>请求报告

1. 在特定报表的主页上，单击 !["请求报表"图标。](../../media/m365-cc-sc-download-icon.png) **请求报告**。
2. 随即打开 **"创建按需报表** "向导。 在 **"按需名称"报表页上** ，查看或自定义 **"名称"** 值，然后单击 **"下一步**"。
3. 在 **"设置首选项"页上** ，查看或配置以下设置：
   - **开始日期**：开始生成报表的时间。 默认值为一个月前。
   - **到期日期**：报表生成结束时。 默认值为当前。

   完成后，请单击“**下一步**”。

4. 在 **"收件人"** 页上，为报表选择收件人。 默认值是电子邮件地址，但可以添加其他地址。

   完成后，请单击“**下一步**”。

5. 在 **"审阅** "页上，查看所选内容。 可以单击相应部分中的 **"返回** "按钮或 **"编辑** "链接进行更改。

   完成后，请单击“**提交**”。

6. 成功创建报表后，将转到 **"新建按需报表创建** "页，可在其中单击 **"创建其他报** 表"或 **"完成**"。

   报表也可在报表 **下载** 页上使用，如下一部分所述。

### <a name="download-reports"></a>下载报表

1. 在Microsoft 365 Defender门户中<https://security.microsoft.com>，转到 **"报**\>表"展开 **电子邮件&协作**\>选择 **"报表"进行下载**。

   若要直接转到 **"报表"下载** 页，请使用 <https://security.microsoft.com/ReportsForDownload>。

2. 在 **"下载报告** "页上，会显示每个可用报表的以下信息：
   - **开始日期**
   - **名称**
   - **报告类型**
   - **上次发送时间**
   - **方向**

   查找并选择要下载的报表。

## <a name="export-report"></a>导出报表

在特定报表的主页上，单击" ![导出"图标。](../../media/m365-cc-sc-download-icon.png) 如果 **该链接**) 可用，则导出 (。 将显示导 **出条件** 浮出控件，可在其中配置以下设置：

- **选择要导出的视图**：选择以下值之一：
  - **摘要**：数据可用于过去 90 天。
  - **详细信息**：数据可用于过去 30 天。
- **日期 (UTC)**： **开始日期** 和 **结束日期**。

配置完筛选器后，单击" **导出**"。 在打开的对话框中，可以选择打开文件、保存文件或记住所选内容。

每个导出.csv文件限制为 150，000 行。 如果数据包含超过 150，000 行，则会创建多个.csv文件。

## <a name="related-topics"></a>相关主题

[EOP 中的反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)

[Microsoft 365 Defender门户中的智能报表和见解](reports-and-insights-in-security-and-compliance.md)

[在Microsoft 365 Defender门户中查看邮件流报表](view-mail-flow-reports.md)

[查看报表Defender for Office 365](view-reports-for-mdo.md)
