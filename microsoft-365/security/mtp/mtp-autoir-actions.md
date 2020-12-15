---
title: 批准或拒绝自动调查后挂起的操作
description: 使用操作中心管理与自动调查和响应相关的操作
keywords: 操作, 中心, autoair, 自动化, 调查, 响应, 修正
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.date: 12/09/2020
ms.openlocfilehash: b34f4a532571d6215500ab2bec022489fd462d0f
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683355"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a>批准或拒绝自动调查后挂起的操作

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

运行自动调查后，可能会生成一个或多个[修正操作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions)，需要批准这些操作才能继续。 例如，可能需要删除电子邮件的群集，或者可能需要删除已隔离的文件。 应尽快批准（或拒绝）挂起的操作，以便自动调查可以继续并及时完成。 

> [!TIP]
> 如果认为 Microsoft 365 Defender 中的自动调查和响应功能遗漏或检测错误，请告诉我们！ 请参阅 [如何在 Microsoft 365](mtp-autoir-report-false-positives-negatives.md)Defender 中的 AIR (功能中的自动调查和响应) 误报/负数。

挂起的操作可以通过使用操作中心或 [调查详细信息视图](#review-a-pending-action-in-the-action-center) 进行 [审阅和批准](#review-a-pending-action-in-the-investigation-details-view)。

> [!NOTE]
> 必须具有[相应的权限](mtp-action-center.md#required-permissions-for-action-center-tasks)才能批准或拒绝修正操作。 有关详细信息，请参阅 [Microsoft 365 Defender 中自动调查和响应的先决条件](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。

## <a name="review-a-pending-action-in-the-action-center"></a>在操作中心中查看挂起的操作

1. 转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。 

2. 在“导航”窗格中，选择“操作中心”。 

3. 在操作中心中的“挂起”选项卡上，选择列表中的某个项。 

    - 如果选择“调查编号”列中的某个项，将打开“调查详细信息”页面。 可以在此处查看调查结果，然后批准或拒绝建议的操作。
 
    - 如果选择列表中的某一行，将打开浮出控件，可在其中查看有关该项的信息。 <br/>![批准或拒绝操作](../../media/air-actioncenter-itemselected.png)<br/>使用链接查看关联的警报或调查，并批准或拒绝该操作。

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>在“调查详细信息”视图中查看挂起的操作

![调查详细信息](../../media/mtp-air-investdetails.png)

1. 在[调查详细信息](mtp-autoir-results.md)页上，选择“挂起的操作”（或“操作”）选项卡。此处列出了等待批准的项。

2. 选择列表中的某个项，然后选择“批准”或“拒绝”。

## <a name="next-steps"></a>后续步骤

- [查看自动调查的详细信息和结果](mtp-autoir-results.md)
- [处理自动调查和响应功能中的误报/负数](mtp-autoir-report-false-positives-negatives.md)
