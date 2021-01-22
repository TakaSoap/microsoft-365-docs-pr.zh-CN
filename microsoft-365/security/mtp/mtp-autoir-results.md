---
title: 自动调查的详细信息和结果
description: 在自动调查期间和之后，可以查看结果和关键发现
keywords: 自动化， 调查， 结果， 分析， 详细信息， 修正， autoair
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.technology: m365d
ms.openlocfilehash: c050683bb3ed052ae4752ffdee66fe51fb99b88b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930362"
---
# <a name="details-and-results-of-an-automated-investigation"></a>自动调查的详细信息和结果

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

当 Microsoft 365 Defender 中发生自动调查时，可在自动调查过程期间和之后获得有关该调查的详细信息。 如果您具有 [必要的权限](mtp-action-center.md#required-permissions-for-action-center-tasks)，可以在调查详细信息视图中查看这些详细信息。 调查详细信息视图为您提供了最新状态以及批准任何挂起操作的能力。 

![调查详细信息](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a>打开调查详细信息视图

可以使用下列方法之一打开调查详细信息视图：
- [选择操作中心中的项目](#select-an-item-in-the-action-center)
- [从事件详细信息页面选择调查](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>选择操作中心中的项目

使用操作中心在"历史记录"选项卡 ("挂起"选项卡) 或 (**挂起审批**) 。  

1. 转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。 

2. 在“导航”窗格中，选择“操作中心”。 

3. 在"挂起 **"或** " **历史记录"** 选项卡上，选择一个项目。 如果您具有必要的 [权限](mtp-action-center.md#required-permissions-for-action-center-tasks)，您可以批准 (或拒绝) 操作。

### <a name="open-an-investigation-from-an-incident-details-page"></a>从事件详细信息页面打开调查

使用事件详细信息页面查看有关事件的详细信息，包括触发的有关任何受影响设备、用户帐户或邮箱的信息的警报。

1. 转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。 

2. 在导航窗格中，选择 **"事件"。** 

3. 在列表中选择一个项目以打开事件详细信息视图。<br/>![事件详细信息](../../media/mtp-incidentdetails-tabs.png)

4. 在 **"调查"** 选项卡上，选择列表中的调查。

## <a name="investigation-details"></a>调查详细信息

使用调查详细信息视图查看过去、当前和挂起的与调查相关的活动。 调查详细信息视图类似于下图：

![调查详细信息](../../media/mtp-air-investdetails.png)

在"调查详细信息"视图中，你可以看到"调查"**图**、警报、设备、标识、关键发现、实体、日志和待定操作选项卡上的信息，如下表所述。   

| Tab | 说明 |
|--------|--------|
| **调查图**   | 提供调查的直观表示形式。 描述实体并列出发现的威胁，以及警报以及是否正在等待批准任何操作。<br/>你可以单击图形上的项目以查看更多详细信息。 例如，单击"找到 **的威胁** "图标将你进入 **"关键发现"** 选项卡。 |
| **警告**    | 列出与调查相关的警报。 警报可能来自用户计算机上的威胁防护功能、Office 应用、云应用安全和其他 Microsoft 365 Defender 功能。|
| **设备** | 列出调查中包含的计算机以及修正级别。|
| **关键发现**  | 列出调查的结果以及执行或挂起的状态和操作。 你可以批准此选项卡上设备和标识的挂起操作。|
| **Entities**  | 列出与调查关联的用户活动、文件、进程、服务、驱动程序、IP 地址和持久性方法，以及状态和采取的操作。|
|**Log**    | 提供调查期间执行的所有步骤的详细视图以及状态。|
| **挂起的操作** | 列出需要审批的项目以继续。|

## <a name="next-steps"></a>后续步骤

- [批准或拒绝与自动调查和响应相关的操作](mtp-autoir-actions.md)
- [查看修正操作](mtp-remediation-actions.md)
