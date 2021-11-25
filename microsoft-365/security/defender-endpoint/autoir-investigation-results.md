---
title: 查看自动调查的详细信息和结果
description: 在自动调查期间和之后，可以查看结果和关键发现
keywords: 自动化， 调查， 结果， 分析， 详细信息， 修正， autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
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
ms.openlocfilehash: bed61ca559ff6fe387d76e9f56842ae765e186fe
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2021
ms.locfileid: "61170304"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a>查看自动调查的详细信息和结果

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

使用 Microsoft Defender for [Endpoint，当自动](automated-investigations.md) 调查运行时，有关该调查的详细信息在自动调查过程期间和之后均可用。 如果您具有必要的权限，您可以在调查详细信息视图中查看这些详细信息。 调查详细信息视图为您提供了最新状态以及批准任何挂起操作的能力。

## <a name="new-unified-investigation-page"></a> ("新建！) 统一调查"页

最近更新了调查页面，以包含跨设备、电子邮件和协作内容的信息。 新的统一调查页面定义通用语言，并提供跨[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)和 Microsoft Defender for Office 365[进行自动调查的统一体验](/microsoft-365/security/office-365-security/office-365-atp)。

> [!TIP]
> 若要了解有关变化内容的信息，请参阅"新建 [ (！) 统一调查"页](/microsoft-365/security/mtp/mtp-autoir-results)。

## <a name="open-the-investigation-details-view"></a>打开调查详细信息视图

可以使用以下方法之一打开调查详细信息视图：

- [选择操作中心中的项目](#select-an-item-in-the-action-center)
- [从事件详细信息页面选择调查](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>选择操作中心中的项目

改进的操作[中心](auto-investigation-action-center.md)将跨设备、电子邮件[](manage-auto-investigation.md#remediation-actions)、协作内容和标识&修正操作汇集在一起。 列出的操作包括自动或手动采取的修正操作。 在操作中心中，可以查看正在等待审批的操作以及已批准或已完成的操作。 还可以导航到更多详细信息，如调查页面。

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>并登录。
2. 在“导航”窗格中，选择“操作中心”。
3. 在"挂起 **"或** " **历史记录"** 选项卡上，选择一个项目。 将打开其飞出窗格。
4. 查看飞出窗格中的信息，然后执行以下步骤之一：
   - 选择 **"打开调查"** 页以查看有关调查的更多详细信息。
   - 选择 **"批准** "以启动挂起的操作。
   - 选择 **"** 拒绝"以防止执行挂起的操作。
   - 选择 **"开始搜寻**"转到"[高级搜寻"。](advanced-hunting-overview.md)

### <a name="open-an-investigation-from-an-incident-details-page"></a>从事件详细信息页面打开调查

使用事件详细信息页面查看有关事件的详细信息，包括触发的有关任何受影响的设备、用户帐户或邮箱的信息的警报。

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>并登录。
2. 在导航窗格中，选择"事件 **&事件** \> **"。**
3. 选择列表中的某个项目，然后选择"打开 **事件页面"。**
4. 选择 **"调查"** 选项卡，然后在列表中选择调查。 将打开其飞出窗格。
5. 选择 **"打开调查"页**。

## <a name="investigation-details"></a>调查详细信息

使用调查详细信息视图可查看过去、当前和挂起的与调查相关的活动。 调查详细信息视图类似于下图：

在调查详细信息视图中，你可以看到调查 **图形**、警报、设备、标识、关键发现、实体、日志和挂起操作选项卡上的信息，如下表所述。    

> [!NOTE]
> 你在调查详细信息页面中看到的特定选项卡取决于你的订阅包括的内容。 例如，如果你的订阅不包括 Microsoft Defender for Office 365计划 2，你将看不到"邮箱 **"** 选项卡。

|Tab|Description|
|---|---|
|**调查图**|提供调查的直观表示。 描述实体并列出找到的威胁及警报，以及是否有任何待批准的操作。 <p> 可以选择图形上的项目以查看更多详细信息。 例如，选择 **"证据**"图标将你带至"证据"选项卡，可在其中查看检测到的实体及其裁定。|
|**警告**|列出与调查相关的警报。 警报可能来自用户设备上的威胁防护功能、Office应用、适用于云应用的 Defender 和其他Microsoft 365 Defender功能。|
|**Devices**|列出包含在调查中的设备及其修正级别。  (修正级别对应于设备[组 .) ](automation-levels.md)|
|**邮箱**|列出受检测到的威胁影响的邮箱。|
|**用户**|列出受检测到的威胁影响的用户帐户。|
|**证据**|列出由警报/调查引发的证据片段。 包括有关 *(、**可疑或**未找到* 威胁) 和修正状态裁定。|
|**Entities**|提供有关每个已分析实体的详细信息，包括每个实体类型裁定 (*恶意*、可疑或未找到任何威胁) 。 |
|**Log**|提供触发警报后执行的所有调查操作按时间顺序的详细视图。|
|**挂起的操作**|列出需要审批的项目以继续。 转到操作中心 <https://security.microsoft.com/action-center> () 审批挂起的操作。|

## <a name="see-also"></a>另请参阅

- [在自动调查后查看修正操作](manage-auto-investigation.md)
- [查看并组织 Microsoft Defender for Endpoint 事件队列](view-incidents-queue.md)
