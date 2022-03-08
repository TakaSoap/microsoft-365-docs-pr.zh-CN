---
title: 自动调查的详细信息和结果
description: 查看自动调查的结果和主要Microsoft 365 Defender
keywords: 自动化， 调查， 结果， 分析， 详细信息， 修正， autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.openlocfilehash: 05e16a32fb21f682a756c32201a69c192d398184
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63321803"
---
# <a name="details-and-results-of-an-automated-investigation"></a>自动调查的详细信息和结果

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

使用 Microsoft 365 Defender，当自动[调查运行时，](m365d-autoir.md)有关该调查的详细信息在自动调查过程期间和之后均可用。 如果您具有 [必要的权限](m365d-action-center.md#required-permissions-for-action-center-tasks)，您可以在调查详细信息视图中查看这些详细信息，该视图为您提供了最新状态以及批准任何挂起操作的能力。 

## <a name="new-unified-investigation-page"></a> ("新建) 统一调查"页

最近更新了调查页面，以包含跨设备、电子邮件和协作内容的信息。 新的统一调查页面定义通用语言，并提供跨 [Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) [自动调查的统一体验](../office-365-security/defender-for-office-365.md)。 若要访问统一调查页面，请选择你将在以下位置看到的黄色横幅中的链接：

- 安全与合规中心Office 365<a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">调查&页</a>
- Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com)
- 事件门户中的任意事件或<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender体验</a>

## <a name="open-the-investigation-details-view"></a>打开调查详细信息视图

可以使用以下方法之一打开调查详细信息视图：

- [选择操作中心中的项目](#select-an-item-in-the-action-center)
- [从事件详细信息页面选择调查](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>选择操作中心中的项目

改进[的操作中心](m365d-action-center.md) ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 跨设备、电子邮件和协作内容和标识&修正操作[](m365d-remediation-actions.md)。 列出的操作包括自动或手动采取的修正操作。 在操作中心中，可以查看正在等待审批的操作以及已批准或已完成的操作。 还可以导航到更多详细信息，如调查页面。

> [!TIP]
> 您必须具有 [某些权限才能](m365d-action-center.md#required-permissions-for-action-center-tasks) 批准、拒绝或撤消操作。

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender并</a>登录。 

2. 在“导航”窗格中，选择“操作中心”。 

3. 在"挂起 **"或** " **历史记录"** 选项卡上，选择一个项目。 将打开其飞出窗格。

4. 查看飞出窗格中的信息，然后执行以下步骤之一：
   - 选择 **"打开调查"** 页以查看有关调查的更多详细信息。
   - 选择 **"批准** "以启动挂起的操作。
   - 选择 **"** 拒绝"以防止执行挂起的操作。
   - 选择 **"开始搜寻** "转到" [高级搜寻"](advanced-hunting-overview.md)。

### <a name="open-an-investigation-from-an-incident-details-page"></a>从事件详细信息页面打开调查

使用事件详细信息页面查看有关事件的详细信息，包括触发的有关任何受影响的设备、用户帐户或邮箱的信息的警报。

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender并</a>登录。 

2. In the navigation pane， choose **Incidents & alertsIncidents** > . 

3. 选择列表中的某个项目，然后选择" **打开事件页面"**。

4. 选择 **"调查"** 选项卡，然后在列表中选择调查。 将打开其飞出窗格。

5. 选择 **"打开调查"页**。 

下面是一个示例。

:::image type="content" source="../../media/mtp-incidentdetails-tabs.png" alt-text="调查页面的示例。" lightbox="../../media/mtp-incidentdetails-tabs.png":::

## <a name="investigation-details"></a>调查详细信息

使用调查详细信息视图可查看过去、当前和挂起的与调查相关的活动。 下面是一个示例。

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="调查详细信息的示例。" lightbox="../../media/mtp-air-investdetails.png":::

在"调查详细信息"视图中，你可以看到"调查 **"图**、警报、设备、标识、关键发现、实体、日志和挂起操作选项卡上的信息，如下表所述。 

> [!NOTE]
> 你在调查详细信息页面中看到的特定选项卡取决于你的订阅包括的内容。 例如，如果你的订阅不包括 Microsoft Defender for Office 365计划 2，你将看不到"邮箱 **"** 选项卡。

| Tab | 说明 |
|:--------|:--------|
| **调查图** | 提供调查的直观表示。 描述实体并列出找到的威胁及警报，以及是否有任何待批准的操作。<br/>可以选择图形上的项目以查看更多详细信息。 例如，选择 **"证据**"图标将你带至"证据"选项卡，可在其中查看检测到的实体及其裁定。 |
| **警告** | 列出与调查相关的警报。 警报可能来自用户设备上的威胁防护功能、Office应用、Microsoft Defender for Cloud Apps 以及其他Microsoft 365 Defender功能。|
| **Devices** | 列出包含在调查中的设备及其修正级别。  (修正级别对应于设备 [组的](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)自动化级别。)  |
| **邮箱** |列出受检测到的威胁影响的邮箱。  |
| **用户**  | 列出受检测到的威胁影响的用户帐户。 |
| **证据** | 列出由警报或调查引发的证据片段。 包括有关 (*、可疑*、*未知* 或未找到威胁) 和修正状态裁定。 |
| **Entities** | 提供有关每个已分析实体的详细信息，包括每个实体类型裁定 (*恶意*、可疑或未找到任何威胁) 。|
|**Log** | 提供触发警报后执行的所有调查操作按时间顺序的详细视图。|
| **挂起的操作历史记录** | 列出需要审批的项目以继续。 转到操作中心 () [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 审批挂起的操作。 |

## <a name="next-steps"></a>后续步骤

- [查看和管理修正操作](m365d-autoir-actions.md)
- [详细了解修正操作](m365d-remediation-actions.md)
