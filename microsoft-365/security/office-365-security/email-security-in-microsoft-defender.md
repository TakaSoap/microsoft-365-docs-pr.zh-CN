---
title: 使用 Microsoft Defender for Office 365 中的威胁资源管理器进行电子邮件Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 查看和调查恶意软件钓鱼尝试。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0326a51f14b402b9a579e8668ef2c026f9de789
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877892"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a>使用 Microsoft Defender for Office 365 中的威胁资源管理器进行电子邮件Office 365

本文内容：

- [查看电子邮件中检测到的恶意软件](#view-malware-detected-in-email)
- [查看网络钓鱼 URL 并单击裁定数据](#view-phishing-url-and-click-verdict-data)
- [启动自动调查和响应](#start-automated-investigation-and-response)

> [!NOTE]
> 这是威胁资源管理器 (**资源管理器) 、** 电子邮件安全、资源管理器和实时检测基础知识的 **3** 篇文章系列中的一部分 **(如** 工具之间的差异以及操作它们所需的权限) 。 本系列中的其他两篇文章是威胁资源管理器和威胁[](threat-hunting-in-threat-explorer.md)资源管理器中的威胁搜寻和[实时检测基础知识](real-time-detections.md)。 

本文介绍如何查看和调查电子邮件中检测到的恶意软件和网络钓鱼Microsoft 365安全功能。 

**适用对象**

- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a>查看电子邮件中检测到的恶意软件

若要查看在电子邮件中检测到的恶意软件Microsoft 365技术排序，请使用 Explorer >[](threat-explorer-views.md#email--malware)的"电子邮件 (恶意软件"视图或实时检测) 。 恶意软件是默认视图，因此一旦打开资源管理器，可能会选择它。

1. 在安全&中心 () ，选择"威胁管理资源管理器 (<https://protection.office.com> 或实时检测 \> ) 。   (此示例使用 Explorer.) 

   如果你位于 Defender 门户的聚合 <https://security.microsoft.com> Microsoft 365， () "&**资源管理器**  >  **"。**

   从此处，从"视图"开始，选择一个特定的时间范围来调查 (如果需要) ，并按资源管理器演练来聚焦 [筛选器](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)。

2. 在"**视图"** 菜单中，选择"**电子邮件恶意软件** \> **"。**

   > [!div class="mx-imgBorder"]
   > ![资源管理器的"视图"菜单](../../media/ExplorerViewEmailMalwareMenu.png)

3. 单击 **"发件人**"，然后选择"**基本** \> **检测技术"。**

   你的检测技术现在用作报告的筛选器。

   > [!div class="mx-imgBorder"]
   > ![恶意软件检测技术](../../media/ExplorerEmailMalwareDetectionTech.png)

4. 选择一个选项。 然后选择" **刷新"** 按钮以应用该筛选器。

   > [!div class="mx-imgBorder"]
   > ![选定的检测技术](../../media/ExplorerEmailMalwareDetectionTechATP.png)

   报告将刷新，以使用所选的技术选项显示电子邮件中检测到的恶意软件的结果。 在这里，你可以进行进一步分析。 

## <a name="view-phishing-url-and-click-verdict-data"></a>查看网络钓鱼 URL 并单击裁定数据

您可以通过电子邮件中的 URL 查看网络钓鱼尝试，包括允许、阻止和覆盖的 URL 列表。 若要标识单击的[URL，保险箱链接](safe-links.md)。 请确保为单击保险箱和单击[](set-up-safe-links-policies.md)裁定的日志记录设置"链接"策略保险箱链接" 。

若要查看邮件中的网络钓鱼 URL 并单击网络钓鱼邮件中的 URL，请使用资源管理器的电子邮件[  >  ](threat-explorer-views.md#email--phish)网络钓鱼视图或实时检测。

1. 在安全&中心 () ，选择"威胁管理资源管理器 (<https://protection.office.com> 或实时检测 \> ) 。   (此示例使用 Explorer.) 

2. 在"**视图"** 菜单中，选择"**电子邮件钓鱼** \> **邮件"。**

   > [!div class="mx-imgBorder"]
   > ![网络钓鱼上下文中资源管理器的"查看"菜单](../../media/ExplorerViewEmailPhishMenu.png)

3. 单击 **"发件人**"，然后选择 **"URL""** \> **单击裁定"。**

4. 选择一个或多个选项，如"阻止"和"阻止 **覆盖**"，然后选择与应用该筛选器的选项位于同一行上的"刷新"按钮。  (请勿刷新浏览器窗口。) 

   > [!div class="mx-imgBorder"]
   > ![URL 和单击裁定](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   报告将刷新，以在报告下的"URL"选项卡上显示两个不同的 URL 表：

   - **顶部 URL** 是筛选到的邮件中的 URL，每个 URL 的电子邮件传递操作计数。 在网络钓鱼电子邮件视图中，此列表通常包含合法 URL。 攻击者在邮件中混合了好 URL 和坏 URL，以尝试传递这些 URL，但它们会使恶意链接看起来更有趣。 URL 表按总电子邮件计数排序，但隐藏此列以简化视图。

   - **点击量** 最高是保险箱链接包装的 URL，按总点击数排序。 此列也不显示，以简化视图。 按列的总计数指示每个保险箱 URL 的链接单击裁定计数。 在网络钓鱼电子邮件视图中，这些 URL 通常是可疑或恶意 URL。 但是，该视图可能包含不是威胁但包含钓鱼邮件中的 URL。 此处不会显示对未包链接的 URL 单击。

   这两个 URL 表按传递操作和位置显示网络钓鱼电子邮件中的顶部 URL。 这些表显示了在出现警告时被阻止或访问的 URL 单击，因此你可以看到向用户显示哪些潜在的错误链接以及用户点击了哪些链接。 在这里，你可以进行进一步分析。 例如，在图表下方，可以看到在组织环境中被阻止的电子邮件中的顶部 URL。

   > [!div class="mx-imgBorder"]
   > ![阻止的浏览器 URL](../../media/ExplorerPhishClickVerdictURLs.png)

   选择 URL 以查看更多详细信息。

   > [!NOTE]
   > 在"URL"弹出对话框中，将删除对电子邮件的筛选，以显示环境中 URL 曝光的完整视图。 这允许你在资源管理器中筛选你关注的电子邮件，查找潜在威胁的特定 URL，然后通过"URL 详细信息"对话框) 扩展你了解环境中 (中的 URL 曝光，而无需将 URL 筛选器添加到资源管理器视图本身。

### <a name="interpretation-of-click-verdicts"></a>单击裁定的解释

在"电子邮件或 URL"飞出、点击次数和筛选体验中，你将看到不同的单击裁定值：

- **无：** 无法捕获 URL 裁定。 用户可能通过 URL 单击过。
- **允许：** 允许用户导航到 URL。
- **已阻止：** 阻止用户导航到 URL。
- **待定裁定：** 向用户显示等待触发的页面。
- **被阻止覆盖：** 阻止用户直接导航到 URL。 但用户过度控制块以导航到 URL。
- **已绕过待定裁定：** 向用户显示触发页面。 但是，用户为了访问 URL 而过度使用邮件。
- **错误：** 向用户显示错误页面，或捕获裁定时出错。
- **失败：** 捕获裁定时发生未知异常。 用户可能通过 URL 单击过。

## <a name="start-automated-investigation-and-response"></a>启动自动调查和响应

> [!NOTE]
> Microsoft Defender for *Office 365 Plan 2* and *Office 365 E5 中提供了自动调查和响应功能*。

[自动调查和响应](automated-investigation-response-office.md) 可以节省安全运营团队在调查和缓解网络攻击上花费的时间和精力。 除了配置可触发安全手册的警报之外，还可以从资源管理器中的视图启动自动调查和响应过程。 有关详细信息，请参阅 [示例：安全管理员从资源管理器触发调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。

## <a name="other-articles"></a>其他文章

[使用"电子邮件实体"页调查电子邮件](mdo-email-entity-page.md)
