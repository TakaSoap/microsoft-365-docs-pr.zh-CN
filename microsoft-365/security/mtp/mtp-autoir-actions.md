---
title: 在自动调查后批准或拒绝待处理的操作
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
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: d7739ac6184509abe4df3aaf140db66f6039717c
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962649"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a>在自动调查后批准或拒绝待处理的操作

**适用于：**
- Microsoft 威胁防护

运行自动调查后，可能会生成一个或多个[修正操作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions)，需要批准这些操作才能继续。 例如，可能需要删除电子邮件的群集，或者可能需要删除已隔离的文件。 应尽快批准（或拒绝）挂起的操作，以便自动调查可以继续并及时完成。 

> [!TIP]
> 如果你认为在 Microsoft 威胁防护中，自动调查和响应功能已丢失或错误地检测到了某些内容，请告诉我们！ 请参阅 [如何在自动调查和响应中报告误报/负面 (AIR) 在 Microsoft 威胁防护中的功能](mtp-autoir-report-false-positives-negatives.md)。

可以使用 [操作中心](#review-a-pending-action-in-the-action-center) 或 [调查详细信息视图](#review-a-pending-action-in-the-investigation-details-view)来审阅和批准挂起的操作。

> [!NOTE]
> 必须具有[相应的权限](mtp-action-center.md#required-permissions-for-action-center-tasks)才能批准或拒绝修正操作。

## <a name="review-a-pending-action-in-the-action-center"></a>在操作中心中查看挂起的操作

1. 转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。 

2. 在“导航”窗格中，选择“操作中心”****。 

3. 在操作中心中的“挂起”选项卡上，选择列表中的某个项****。 

    - 如果选择“调查编号”列中的某个项，将打开“调查详细信息”页面****。 可以在此处查看调查结果，然后批准或拒绝建议的操作。
 
    - 如果选择列表中的某一行，将打开浮出控件，可在其中查看有关该项的信息。 <br/>![批准或拒绝操作](../../media/air-actioncenter-itemselected.png)<br/>使用链接查看关联的警报或调查，并批准或拒绝该操作。

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>在“调查详细信息”视图中查看挂起的操作

![调查详细信息](../../media/mtp-air-investdetails.png)

1. 在[调查详细信息](mtp-autoir-results.md)页上，选择“挂起的操作”（或“操作”）选项卡。此处列出了等待批准的项********。

2. 选择列表中的某个项，然后选择“批准”或“拒绝”********。

## <a name="next-steps"></a>后续步骤

- [查看自动调查的详细信息和结果](mtp-autoir-results.md)
- [处理自动调查和响应功能中的误报/否定](mtp-autoir-report-false-positives-negatives.md)
