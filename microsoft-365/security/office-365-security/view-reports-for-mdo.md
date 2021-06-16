---
title: 在报告仪表板Office 365 Defender for Office 365报告
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 在 Microsoft Defender 门户中查找Office 365 Microsoft Defender Microsoft 365报告。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5c45f58ee83de11712b198c85a8e423314289bf
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930198"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-microsoft-365-defender-portal"></a>在 Office 365 Defender 门户的"报告"仪表板中查看Microsoft 365 Defender 报告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

适用于 Office 365 组织的 Microsoft Defender (例如，Microsoft 365 E5 订阅或 Microsoft Defender for Office 365 计划 1 或 Microsoft Defender for Office 365 计划 2 加载项) 包含各种与安全相关的报告。 如果你拥有 [必要的权限](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)，可以在 defender 门户中查看这些报告Microsoft 365报告 \> **电子邮件协作** \> **电子邮件协作报告**。 若要直接转到"报表"仪表板，请打开 <https://security.microsoft.com/emailandcollabreport> 。

![Microsoft 365 Defender 门户中的"报告"仪表板](../../media/user-reported-messages.png)

## <a name="defender-for-office-365-file-types-report"></a>Defender for Office 365 文件类型报告

The **Defender for Office 365 file types report** report shows you the type of files detected as malicious by 保险箱 [Attachments](safe-attachments.md).

 报告聚合视图允许筛选 90 天，而详细信息视图仅允许筛选 10 天。

若要查看报告，请打开 [Microsoft 365 Defender 门户](https://security.microsoft.com)，转到报告仪表板 \> ，然后选择 Defender **Office 365文件类型**。 若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=ATPFileReport> 。

![报告Office 365中的 Defender for Office 365文件类型小组件](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> 此报告中的信息也可在 Defender for [Office 365邮件处置报告中获取](#defender-for-office-365-message-disposition-report)。

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a>Defender for Office 365 文件类型报告的报告视图

提供以下视图：

- **查看数据者：文件**：图表包含以下信息：

  - **恶意Excel附件**
  - **恶意 Flash 附件**
  - **恶意 PDF 附件**
  - **恶意PowerPoint附件**
  - **恶意 URL**
  - **恶意 Word 附件**
  - **恶意可执行附件**
  - **其他**

  当你将鼠标悬停在 (数据点) 上时，你可以看到 EOP 中的[保险箱 附件](safe-attachments.md)和反恶意软件保护检测到的恶意文件类型[的细目](anti-malware-protection.md)。

  ![Defender for Office 365 文件类型报告中的文件视图](../../media/atp-file-types-report-file-view.png)

  如果单击 **"筛选器"，** 可以使用以下筛选器修改报告：

  - **开始日期和****结束日期**
  - 图表中可见的相同文件类型值。

- **查看数据者：消息**：图表包含以下信息：

  - **阻止访问**
  - **邮件被替换**
  - **监视的邮件**
  - **替换为动态电子邮件传递**：有关详细信息，请参阅动态传递 [保险箱附件策略](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)。

  ![Defender for Office 365文件类型报告中的消息视图](../../media/atp-file-types-report-message-view.png)

  如果单击 **"筛选器"，** 可以使用以下筛选器修改报告：

  - **开始日期和****结束日期**
  - 图表中可用的相同邮件处置值，以及传递值的其他 **邮件** 。

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a>Defender for Office 365 文件类型报告的详细信息表视图

如果单击 **"查看详细信息"** 表，报告将提供过去 10 天内在组织中发生的所有单击的近实时视图。 显示的信息取决于您所查看的图表：

- **查看数据者：文件**：

  - **Date**
  - **收件人地址**
  - **发件人地址**
  - **邮件 ID：** 在邮件 **头的 Message-ID** 头字段中可用，并且应该是唯一的。 示例值是 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (尖括号) 。
  - **文件**

  如果单击 **"筛选器"，** 可以使用以下筛选器修改报告：

  - **开始日期和****结束日期**
  - 图表中可见的相同文件类型值。

- **查看数据者： 消息**：

  - **Date**
  - **收件人地址**
  - **发件人地址**
  - **邮件 ID**
  - **文件**
  - **主题**

  如果单击 **"筛选器"，** 可以使用以下筛选器修改结果：

  - **开始日期和****结束日期**
  - 图表中可用的相同邮件处置值，以及传递值的其他 **邮件** 。

若要返回到报告视图，请单击"查看 **报告"。**

## <a name="defender-for-office-365-message-disposition-report"></a>Defender for Office 365 邮件处置报告

**ATP 邮件处置** 报告显示对被检测为包含恶意内容的电子邮件采取的操作。

若要查看报告，请打开 [Microsoft 365 Defender](https://security.microsoft.com)门户，转到报告电子邮件&协作 电子邮件 & 协作报告，然后选择 \>  \> **Defender Office 365邮件处置**。 若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=ATPMessageReport> 。

![报告仪表板Office 365 Defender for Office 365邮件处置小组件](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> 此报告中的信息也可在 Defender for [Office 365文件类型报告中获取](#defender-for-office-365-file-types-report)。

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a>Defender for Office 365邮件处置报告的报告视图

提供以下视图：

- **查看数据者：消息**：图表包含以下信息：

  - **阻止访问**
  - **邮件被替换**
  - **监视的邮件**
  - **替换为动态电子邮件传递**：有关详细信息，请参阅动态传递 [保险箱附件策略](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)。

  ![Defender for Office 365文件类型报告中的消息视图](../../media/atp-file-types-report-message-view.png)

  如果单击 **"筛选器"，** 可以使用以下筛选器修改报告：

  - **开始日期和****结束日期**
  - 图表中可用的相同邮件处置值，以及传递值的其他 **邮件** 。

- **查看数据者：文件**：图表包含以下信息：

  - **恶意Excel附件**
  - **恶意 Flash 附件**
  - **恶意 PDF 附件**
  - **恶意PowerPoint附件**
  - **恶意 URL**
  - **恶意 Word 附件**
  - **恶意可执行附件**
  - **其他**

  当你将鼠标悬停在 (数据点) 上时，你可以看到 EOP 中的[保险箱 附件](safe-attachments.md)和反恶意软件保护检测到的恶意文件类型[的细目](anti-malware-protection.md)。

  ![Defender for Office 365 文件类型报告中的文件视图](../../media/atp-file-types-report-file-view.png)

  如果单击 **"筛选器"，** 可以使用以下筛选器修改报告：

  - **开始日期和****结束日期**
  - 图表中可见的相同文件类型值。

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a>Defender for Office 365 邮件处置报告的详细信息表视图

如果单击 **"查看详细信息"** 表，报告将提供过去 10 天内在组织中发生的所有单击的近实时视图。 显示的信息取决于您所查看的图表：

- **查看数据者： 消息**：

  - **Date**
  - **收件人地址**
  - **发件人地址**
  - **邮件 ID**
  - **文件**
  - **主题**

  如果单击 **"筛选器"，** 可以使用以下筛选器修改结果：

  - **开始日期和****结束日期**
  - 图表中可用的相同邮件处置值，以及传递值的其他 **邮件** 。

- **查看数据者：文件**：

  - **Date**
  - **收件人地址**
  - **发件人地址**
  - **邮件 ID**
  - **文件**

  如果单击 **"筛选器"，** 可以使用以下筛选器修改报告：

  - **开始日期和****结束日期**
  - 图表中可见的相同文件类型值。

若要返回到报告视图，请单击"查看 **报告"。**

## <a name="mail-latency-report"></a>邮件延迟报告

邮件 **延迟报告显示** 组织中遇到的邮件传递和触发延迟的聚合视图。 服务中的邮件传递时间受多种因素的影响，绝对传递时间（以秒表示）通常不是成功或出现问题的良好指标。 一天的较慢的送达时间可能被视为另一天的平均送达时间，反之亦然。 邮件 **延迟报告** 尝试根据有关其他邮件的观察到送达时间的统计数据来限定邮件传递：

- **第 50 个** 百分点值：这是邮件传递时间中间值。 可以将此值视为平均送达时间。
- **第 90** 个百分点值：这表示邮件传递的延迟很高。 仅 10% 的邮件传递时间超过此值。
- **第 99 个** 百分点值：这表示邮件传递的延迟最高。

不包括客户端和网络延迟。

若要查看报告，请打开 [Microsoft 365 Defender](https://security.microsoft.com)门户，转到报告 \> **电子邮件&协作** 电子邮件 \> **& 协作报告**，然后单击邮件延迟报告 下的 查看 **详细信息**。 若要直接转到报告，请打开 <https://security.microsoft.com/mailLatencyReport> 。

!["报告"仪表板中的"邮件延迟报告"小部件](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a>邮件延迟报告的报告视图

打开报表时，默认情况下选择 **第 50** 个百分点值选项卡。

默认情况下，此视图包含配置了以下筛选器的图表：

- **日期**：最近 7 天
- **邮件视图**：
  - 触发的邮件

此图显示按以下类别组织的邮件：

- **邮件传递延迟**
- **触发延迟**

将鼠标悬停在图表中的类别上时，可以看到每个类别中延迟的细分。

![邮件延迟报告](../../media/mail-latency-report.png)

如果 **单击"** 筛选器"，报表视图筛选器修改结果：

- 所有邮件
- 包含附件或 URL 的邮件

如果单击 **"第 90** 个百分点值"选项卡或 **"第 99** 个百分点值"选项卡，则使用第 **50** 个百分点值视图中的相同默认筛选器。

### <a name="details-table-view-for-the-mail-latency-report"></a>邮件延迟报告的详细信息表视图

详细信息表视图中显示了以下信息：

- **Date**
- **百分点值**
- **邮件计数**
- **总体延迟**

![邮件延迟报告详细信息](../../media/mail-latency-report-details.png)

以上显示，11 月 14 日传递和触发的所有邮件的平均延迟为 **108.033** 秒。

详细信息表在每个选项卡上包含相同的信息。

## <a name="threat-protection-status-report"></a>威胁防护状态报告

威胁防护 **状态** 报告是一个单一视图，将有关 [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) 和 Microsoft Defender for Office 365 检测并阻止的恶意内容和恶意电子邮件的信息汇集在一起。 有关详细信息，请参阅威胁 [防护状态报告](view-email-security-reports.md#threat-protection-status-report)。

## <a name="url-threat-protection-report"></a>URL 威胁防护报告

URL **威胁防护报告** 提供检测到的威胁的摘要和趋势视图，以及作为链接的一部分对 URL [单击保险箱视图](safe-links.md)。 此报告不会包含应用了"链接"策略保险箱"不跟踪用户单击"选项的用户的 **单击** 数据。

若要查看报告，请打开 [Microsoft 365 Defender](https://security.microsoft.com)门户，转到报告电子邮件 \> **&协作** 电子邮件 \> **& 协作报告**，然后单击 URL 保护报告下的查看 **详细信息**。 若要直接转到报告，请打开 <https://security.microsoft.com/reports/URLProtectionActionReport> 。

!["报告"仪表板中的"URL 保护报告"小部件](../../media/url-protection-report-widget.png)

> [!NOTE]
> 这是一个 *保护趋势报告*，表示数据表示较大数据集中的趋势。 因此，此处无法实时获得聚合视图中的数据，但详细信息表视图中的数据是，因此您可能会看到这两个视图之间稍有差异。

### <a name="report-view-for-the-url-threat-protection-report"></a>URL 威胁防护报告的报告视图

**URL 威胁防护** 报告有两个聚合视图，每四小时刷新一次，显示过去 90 天的数据：

- **URL 单击保护操作**：显示组织中用户单击的 URL 数以及单击结果：

  - **阻止** (用户导航到 URL) 
  - **阻止并单击 (** 用户已选择继续导航到 URL) 
  - **在扫描过程中单击 (，** 在扫描完成之前用户已单击链接) 

  单击表示用户已单击"阻止"页面访问恶意网站 (管理员可以在"链接策略" (禁用单击保险箱单击) 。

  如果单击 **"筛选器"，** 可以使用以下筛选器修改报告：

  - **开始日期和****结束日期**
  - 可用的单击保护操作以及值 **Allowed** (允许用户导航到 URL) 。

  ![URL 威胁防护报告中的 URL 单击保护操作视图](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **按应用程序单击的 URL：** 显示支持以下链接的应用程序保险箱数：

  - **电子邮件客户端**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **其他**

  如果单击 **"筛选器"，** 可以使用以下筛选器修改报告：

  - **开始日期和****结束日期**
  - 可用的应用程序。

### <a name="details-table-view-for-the-url-threat-protection-report"></a>URL 威胁防护报告的详细信息表视图

如果单击 **"查看** 详细信息"表，报告将提供过去 7 天内在组织中发生的所有单击的近实时视图，并包含以下详细信息：

- **单击时间**
- **用户**
- **URL**
- **Action**
- **应用**

如果在 **详细信息表** 视图中单击"筛选器"，可以按照与"收件人"报表视图相同的条件进行筛选，也可以按"域"或"收件人"（用逗号分隔）进行筛选。 

> [!NOTE]
> " **域** "筛选器是指报告结果中列出的 URL 域。 

若要返回到报告视图，请单击"查看 **报告"。**

## <a name="additional-reports-to-view"></a>要查看的其他报告

除了本文中所述的报告之外，还有其他一些报告可用，如下表所述：

****

|报告|主题|
|---|---|
|**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1) |[威胁资源管理器（和实时检测）](threat-explorer.md)|
|**电子邮件安全** 报告，例如顶级发件人和收件人报告、欺骗邮件报告和垃圾邮件检测报告。|[在 defender 门户中查看Microsoft 365安全报告](view-email-security-reports.md)|
|**邮件流报告**，如转发报告、邮件流状态报告以及顶级发件人和收件人报告。|[在 Defender 门户中查看Microsoft 365流报告](view-mail-flow-reports.md)|
|**仅 PowerShell 保险箱链接** (URL) 。 此 cmdlet 的输出显示过去七保险箱链接操作的结果。|[Get-UrlTrace](/powershell/module/exchange/get-urltrace)|
|**仅适用于 PowerShell 的 EOP** 和 Microsoft Defender Office 365 (邮件) 。 此 cmdlet 的输出包含有关域、日期、事件类型、方向、操作和消息计数的信息。|[Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport)|
|**仅适用于 PowerShell 的 EOP** 和 Defender Office 365检测 (报告) 。 此 cmdlet 的输出包含有关电子邮件或文件中恶意文件或 URL、网络钓鱼尝试、模拟和其他潜在威胁的详细信息。|[Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>查看 Defender for Office 365报告需要哪些权限？

若要查看和使用本文中所述的报告，你需要是 Microsoft 365 Defender 门户中以下角色组之一的成员：

- **组织管理**
- **安全管理员**
- **安全读者**
- **全局读者**

有关详细信息，请参阅 Defender 门户[中Microsoft 365权限](permissions-in-the-security-and-compliance-center.md)。

注意：将用户添加到 Microsoft 365 管理中心中的相应 Azure Active Directory 角色会为用户提供 Microsoft 365 Defender 门户中所需的权限以及 Microsoft 365 中其他功能的权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。

## <a name="what-if-the-reports-arent-showing-data"></a>如果报告未显示数据，该做什么？

如果你在 Defender for Office 365报告中看不到数据，请仔细检查策略是否正确设置。 你的组织必须保险箱[链接](set-up-safe-links-policies.md)策略保险箱[附件](set-up-safe-attachments-policies.md)策略，以便 Defender Office 365保护就位。 另请参阅 [反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)。

## <a name="related-topics"></a>相关主题

[Microsoft 365 Defender 门户中的智能报告和见解](reports-and-insights-in-security-and-compliance.md)

[角色权限 (Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
