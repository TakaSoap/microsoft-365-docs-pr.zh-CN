---
title: 通过 Microsoft 安全分数评估安全状况
description: 介绍如何执行操作以改进 Microsoft 365 安全中心中的 Microsoft 安全分数。
keywords: 安全性、恶意软件、Microsoft 365、M365、安全分数、安全中心、改进操作
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 469056bbae4627e0b013bfc0f2e965586fd15175
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200058"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>使用 Microsoft 安全分数评估安全状况

Microsoft 安全分数是组织的安全状态的度量，数字越大，表明执行了更多改进操作。 可在 https://security.microsoft.com/securescore [Microsoft 365 安全中心](overview-security-center.md)中找到。

为了帮助您更快地了解所需的信息，Microsoft 改善操作将组织成组：

* Identity （Azure AD 帐户 & 角色）
* 数据（Microsoft 信息保护）
* 设备（Microsoft Defender ATP，称为[配置分数](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configuration-score)）
* 应用（电子邮件和云应用，包括 Office 365 和 Microsoft 云应用安全性）
* 基础结构（暂时不提供改进操作）

>[!NOTE]
>在最近发布的 Microsoft 安全分数中，已发布了一个已改进的记分模型，使 Microsoft 安全分数暂时与标识安全分数和 Graph API 不兼容。 [查看详细信息](microsoft-secure-score-whats-new.md)

在 "Microsoft 安全分数概述" 页中，您可以看到在这些组之间如何拆分点以及哪些点可用。 [！注意] 概述页面也是获取总分和基准对比的安全分数的历史趋势的完整视图的位置，以及可采取的优先改进措施以提高成绩。

![安全得分主页](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>检查当前分数

若要查看你当前的分数，请转到 Microsoft 安全分数概述页面，并查找表明你的**安全分数**的磁贴。 你的分数将显示为百分比，以及你已从全部可能的积分中获得的积分数。

此外，如果您在得分旁选择 "**包括**" 按钮，则可以选择分数的不同视图。 这些不同的分数视图将显示在 "分数" 图块和 "点" 细目图表的图中。

以下是你可以向你的总体成绩视图中添加的分数，以便更完整地了解总体成绩：

- **计划分数**：在计划的操作完成时显示计划的分数
- **当前许可证分数**：显示可通过当前 Microsoft 许可证实现的分数
- 可**实现分数**：显示可通过你的 Microsoft 许可证和当前风险接受能力实现的分数

如果您已包括所有可能的分数视图，则会显示如下内容：

![安全分数，包括计划分数、当前许可证得分和实现分数](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>采取行动以提高成绩

"**改进操作**" 选项卡列出了解决可能的攻击面的安全建议，以及它们的状态（若要解决、规划、接受风险，请通过第三方解决这些问题，通过替代的缓解措施进行解决，并完成）。 您可以搜索、筛选和分组所有改进操作。  

### <a name="ranking"></a>排名

排名基于要达到的剩余点数、实现难度、用户影响和复杂性。 最高排名改进操作的剩余分数与较低的难度、用户影响和复杂性相同。

### <a name="view-improvement-action-details"></a>查看改进操作详细信息

选择特定的 "改进" 操作时，将显示完整的 "页面" 飞出控件。  

![改进操作浮出控件示例 ](../../media/secure-score/secure-score-improvement-action-details.png)
 *图2：改进操作浮出控件示例*

若要完成此操作，您有几个选项：

* 选择 "**管理**" 以转到配置屏幕并进行更改。 然后，您将获得该操作所需要的要点，在飞出中可见。点通常需要大约24小时才能更新。

* 选择 "**共享**" 将直接链接复制到 "改进" 操作，或选择用于共享链接（如电子邮件、microsoft 团队、microsoft Planner 或 ServiceNow）的平台。 选择 ServiceNow 将允许你创建将在 ServiceNow 和 Microsoft 365 安全中心主页中可见的更改票证。 若要了解详细信息，请参阅[Microsoft 365 安全中心和 ServiceNow 集成](tickets-security-center.md)。

### <a name="choose-an-improvement-action-status"></a>选择改进操作状态

选择特定于 "改进" 操作的任何状态和记录笔记。 您可以选择的 statues 如下所示：

* **若要解决**此需要，您可以认识到改进操作是必需的，并计划在将来某一时间解决此操作。 此状态也适用于检测为部分但未完全完成的操作。
* **规划**—完成改进操作有一些具体的规划。
* **接受风险**—安全性应始终与可用性平衡，而不是每个建议对您的环境都适用。 在这种情况下，您可以选择接受风险或剩余风险，而不是执行改进操作。 不会向你提供任何点，但操作将不再显示在改进操作列表中。 您可以在历史记录中查看此操作，也可以随时撤消。
* **通过第三方解决**，并**通过备用的缓解措施解决**—改进操作已由第三方应用程序或软件或内部工具解决。 你将获得该操作所需要的要点，因此你的得分更好地反映了你的总体安全状况。 如果第三方或内部工具不再涵盖该控件，您可以选择另一个状态。 请注意，如果将改进操作标记为这些状态之一，Microsoft 将无法深入了解实施的完整性。

#### <a name="threat--vulnerability-management-improvement-actions"></a>威胁 & 漏洞管理改进操作

对于 "设备" 类别中的改进操作，你将无法选择状态。 相反，你将被定向到[Microsoft Defender 安全中心](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)的关联[威胁 & 漏洞管理（TVM）安全建议](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)，以采取措施。 您选择的异常和您编写的理由将特定于该门户，而不会出现在 Microsoft 安全分数门户中。

#### <a name="completed-improvement-actions"></a>已完成的改进操作

一旦完成了改进操作的所有可能的点，改进操作将为 "已完成" 状态。 已完成的改进操作通过 Microsoft 数据进行确认，并且你将无法更改状态。

### <a name="assess-information-and-review-user-impact"></a>评估信息并查看用户影响

**概览**部分将向您告知类别、它可以保护的攻击和产品。

**用户影响**显示了在制定改进操作后用户将会遇到的情况，并且**受影响的用户**将会看到他们会遇到的情况。

### <a name="implement-the-improvement-action"></a>实施改进操作

"**实现**" 部分显示了所有先决条件、分步完成改进操作的后续步骤、改进操作的当前实现状态以及任何 "了解更多" 链接。

先决条件将是在解决改进措施之前需要获取的任何许可证或需要完成的操作。 请确保你的许可证中有足够的座位来完成改进操作，并且这些许可证适用于所需的用户。  

## <a name="we-want-to-hear-from-you"></a>我们希望收到你的来信

如果你有任何问题，请通过在[安全、隐私 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社区中发布来告知我们。 我们正在监视社区，并将提供帮助。

## <a name="related-resources"></a>相关资源

- [Microsoft 安全评分概述](microsoft-secure-score.md)
- [跟踪你的 Microsoft 安全分数历史记录并实现目标](microsoft-secure-score-history-metrics-trends.md)
- [即将推出的功能](microsoft-secure-score-whats-coming.md)
- [新增功能](microsoft-secure-score-whats-new.md)