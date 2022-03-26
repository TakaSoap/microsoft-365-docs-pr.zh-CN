---
title: Microsoft Defender for Office 365 中的威胁资源管理器和实时Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 使用资源管理器或实时检测高效调查和响应威胁。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3b889649de7b56d6a1b5300ff323850a4e555b57
ms.sourcegitcommit: 9c8eca862a2f0fdca7a66c641e382e37fcaefa10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2022
ms.locfileid: "63775353"
---
# <a name="explorer-and-real-time-detections"></a>资源管理器和实时检测

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

本文内容：

- [资源管理器和实时检测之间的差异](#differences-between-explorer-and-real-time-detections)
- [更新了资源管理器和实时检测体验](#updated-experience-for-explorer-and-real-time-detections)
- [所需的许可证和权限](#required-licenses-and-permissions)

> [!NOTE]
> 这是 **资源管理器 (**（也称为威胁资源管理器) 、电子邮件安全性、资源管理器和实时检测基础知识）的 **3** 篇文章系列中的一 **部分 (如** 工具之间的差异以及运行) 所需的权限。  本系列中的其他两篇文章是资源管理器中的威胁搜寻[](threat-hunting-in-threat-explorer.md)和资源管理器[中的电子邮件安全](email-security-in-microsoft-defender.md)。

本文介绍了资源管理器和实时检测报告、使用资源管理器的更新体验与实时检测（你可以切换新旧体验以及所需的许可证和权限）的区别。

如果你的组织拥有 [适用于 Office 365 的 Microsoft Defender](defender-for-office-365.md)，并且你拥有这些权限，可以使用 [](#required-licenses-and-permissions)**资源管理器** **(也称为** 威胁资源管理器) 或实时检测来检测和修正威胁。

In the Microsoft 365 Defender portal at <https://security.microsoft.com>， go to **Email & collaboration**， and then choose **Explorer** _or_ **Real-time detections**. 若要直接转到页面，请使用 或 <https://security.microsoft.com/threatexplorer> <https://security.microsoft.com/realtimereports>。

使用这些工具，你可以：

- 查看由安全Microsoft 365检测到的恶意软件。
- 查看网络钓鱼 URL 并单击裁定数据。
- 从资源管理器中的视图启动自动调查和响应过程。
- 调查恶意电子邮件等。

有关详细信息，请参阅使用 [资源管理器的电子邮件安全性](email-security-in-microsoft-defender.md)。

## <a name="differences-between-explorer-and-real-time-detections"></a>资源管理器和实时检测之间的差异

- *实时检测是* Defender for Office 365计划 1 中可用的报告工具。 *威胁资源管理器* 是一款威胁搜寻和修正工具，适用于 Office 365 计划 2。
- 实时检测报告允许你实时查看检测。 威胁资源管理器也这样做，但它提供给定攻击的其他详细信息（如突出显示攻击活动）并赋予安全运营团队修正威胁 (包括触发自动调查和响应 [调查](automated-investigation-response-office.md)。
- " *所有* 电子邮件"视图在威胁资源管理器中可用，但不包括在实时检测报告中。
- 威胁资源管理器中包含丰富的筛选功能和修正操作。 有关详细信息，请参阅 [Microsoft Defender for Office 365 服务说明：跨 Defender for Office 365 计划的功能可用性](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

## <a name="updated-experience-for-explorer-and-real-time-detections"></a>更新了资源管理器和实时检测体验

更新了威胁资源管理器和实时检测体验，以与现代辅助功能标准保持一致，并优化工作流。 短时间内，你将能够在旧体验和新体验之间进行切换。  

> [!NOTE]
> 切换仅影响你的帐户，不会影响租户中的其他人。 

威胁资源管理器和实时检测分为以下视图：

- *所有电子邮件*：显示 Defender for office 365 分析的所有电子邮件，其中包含好电子邮件和恶意电子邮件。 此功能仅存在于威胁资源管理器中，不可用于实时检测。 默认情况下，它设置为显示两天的数据，这可扩展到最多 30 天。 这也是威胁资源管理器的默认视图。  

- *恶意软件视图*：显示已识别恶意软件威胁的电子邮件。 这是实时检测的默认视图，显示两天的数据 (可以扩展到 30 天) 。  

- *网络钓鱼视图*：显示已识别网络钓鱼威胁的电子邮件。

- *内容恶意软件视图*：显示通过网站、OneDrive、SharePoint或Teams 共享的文件中标识的恶意Teams。 

以下是这些体验中的常见组件：

- 筛选器

    - 可以使用各种筛选器查看基于电子邮件或文件属性的数据。  

    - 默认情况下，时间筛选器应用于记录，并应用两天。  

    - 如果你要应用多个筛选器，它们在"AND"模式下应用，并且可以使用高级筛选器将筛选器更改为"OR"模式。  

    - 您可以使用逗号为同一筛选器添加多个值。  

    > [!div class="mx-imgBorder"]
    > ![资源管理器筛选器](../../media/explorer-new-experience-filters.png)

- 图表

    - 图表基于筛选器提供数据的可视化聚合视图。 可以使用不同的筛选器按不同维度查看数据。  

    > [!NOTE]
    > 即使在列表视图中看到条目，也可能不会在图表视图中看到任何结果。 如果筛选器未生成任何数据，则会发生此情况。 例如，如果已应用筛选器恶意软件系列，但基础数据没有任何恶意电子邮件，则您可能会看到此邮件没有可用于此方案的数据。  

    > [!div class="mx-imgBorder"]
    > ![资源管理器图表视图](../../media/explorer-new-experience-export-chart-data.png)

- 结果网格  

    - 结果网格根据已应用的筛选器显示电子邮件结果。  

    - 根据租户中设置的配置，数据将显示为 UTC 或本地时区，第一列中提供时区信息。  

    - 通过单击"在新建窗口中打开"图标，可以从列表视图导航到 **各个电子邮件实体** 页面。 

    - 还可以自定义列以添加或删除列以优化视图。

    > [!Note]
    > 可以在"图表视图 *"和"* 列表视图"之间进行 *切换* ，以最大化结果集。  

    > [!div class="mx-imgBorder"]
    > ![资源管理器网格视图](../../media/explorer-new-experience-list-chart-view.png)

- 详细的飞出  

    - 你可以单击超链接以访问电子邮件摘要面板， (主题列、收件人或 IP) 条目。  

    - 电子邮件摘要面板取代了旧电子邮件飞出，还提供了访问电子邮件实体面板的路径。  

    - 单个实体飞出控件（如 IP、收件人和 URL）将反映相同的信息，但呈现在基于选项卡的单个视图中，能够根据要求展开和折叠不同的部分。  

    - 对于 URL 等飞出列表，可以单击"查看所有电子邮件"或"查看所有单击"以查看包含该 URL 的完整电子邮件/单击集，以及导出结果集。  

- 操作

    - 从威胁资源管理器中，你可以触发修正操作 *，如删除电子邮件*。 有关修正、修正限制和跟踪修正详细信息，请参阅 [修正恶意电子邮件](remediate-malicious-email-delivered-office-365.md)。  

- 导出

    - 可以单击" **导出图表数据"** 导出图表详细信息。 同样，单击 **"导出电子邮件列表** "导出电子邮件详细信息。

    - 您最多可以导出 200，000 条电子邮件列表记录。 但是，为了提升系统性能和缩短下载时间，您应使用各种电子邮件筛选器。

    > [!div class="mx-imgBorder"]
    > ![导出图表数据](../../media/explorer-new-experience-export-chart-data.png)

除了这些功能之外，你还将获得更新的体验，如顶部 *URL*、热门点击、热门 *目标* 用户和 *电子邮件来源*。 *可以基于在* 资源管理器中应用筛选器进一步筛选主要 URL、顶部单击和热门目标用户。 

## <a name="required-licenses-and-permissions"></a>所需的许可证和权限

必须具有 [Microsoft Defender for Office 365](defender-for-office-365.md)，以使用资源管理器或实时检测：

- 资源管理器仅包含在计划 2 Office 365 Defender 中。
- 实时检测报告包含在计划 1 的 Defender Office 365中。

安全运营团队需要为应受 Office 365 Defender 保护的所有用户分配许可证，并注意资源管理器和实时检测会显示许可用户的检测数据。

若要查看和使用资源管理器 *或* 实时检测，需要以下权限：

- 在 Defender for Office 365：
  - 组织管理
  - 安全 (可以在管理中心Azure Active Directory分配<https://aad.portal.azure.com> () 
  - 安全信息读取者
- 在Exchange Online：
  - 组织管理
  - 仅查看组织管理
  - 仅查看收件人
  - 合规性管理

若要详细了解角色和权限，请参阅以下文章：

- [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)
- [Exchange Online 中的权限](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a>详细信息

- [威胁资源管理器在电子邮件实体页面上收集电子邮件详细信息](mdo-email-entity-page.md)
- [查找和调查投递的恶意电子邮件](investigate-malicious-email-that-was-delivered.md)
- [查看在 SharePoint Online、OneDrive 和 Microsoft Teams](mdo-for-spo-odb-and-teams.md)
- [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft 威胁防护中的自动调查和响应](automated-investigation-response-office.md)
