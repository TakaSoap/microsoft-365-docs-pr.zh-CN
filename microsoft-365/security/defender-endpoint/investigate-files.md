---
title: 调查适用于终结点的 Microsoft Defender 文件
description: 使用调查选项获取有关与警报、行为或事件关联的文件的详细信息。
keywords: 调查， 调查， 文件， 恶意活动， 攻击动机， 深度分析， 深度分析报告
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 6f93a5ec90404ca28fd47d4115a8ebf8d488216e
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63322039"
---
# <a name="investigate-a-file-associated-with-a-microsoft-defender-for-endpoint-alert"></a>调查与 Microsoft Defender for Endpoint 警报关联的文件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatefiles-abovefoldlink)。

调查与特定警报、行为或事件相关联的文件的详细信息，以帮助确定文件是否呈现恶意活动、识别攻击动机并了解漏洞的潜在范围。

有许多方法可以访问特定文件的详细配置文件页。 例如，可以使用搜索功能、单击警报进程树中的链接、事件 **图**、项目时间线，或选择设备时间线中列出的 **事件**。

进入详细配置文件页面后，可以通过切换新的"文件"页面在新的和旧的页面布局 **之间切换**。 本文的其余部分介绍了较新的页面布局。

可以从文件视图中的以下部分获取信息：

- 文件详细信息， 恶意软件检测， 文件普遍程度
- 深度分析
- 警报
- 在组织中观测到
- 深度分析
- 文件名

您还可以从此页对文件采取操作。

## <a name="file-actions"></a>文件操作

在配置文件页面顶部，在文件信息卡上方。 可在此处执行的操作包括：

- 停止和隔离
- 添加/编辑指示器
- 下载文件
- 咨询威胁专家
- 操作中心

有关这些操作详细信息，请参阅 [对文件执行响应操作](respond-file-alerts.md)。

## <a name="file-details-malware-detection-and-file-prevalence"></a>文件详细信息、恶意软件检测和文件普遍程度

文件详细信息、事件、恶意软件检测和文件流行卡片显示有关文件的各种属性。

你将看到详细信息，如文件的 MD5、病毒总检测比率和 Microsoft Defender AV 检测（如果可用）以及文件的普遍程度。

文件流行卡片显示文件在组织和全球的设备中的显示位置。

> [!NOTE]
> 不同的用户可能会看到不同值在文件流行卡片的"组织单位"部分中。 这是因为卡片显示基于用户具有的 RBAC 范围的信息。 这意味着，如果用户已被授予对一组特定设备的可见性，他们只会看到这些设备上的文件组织普遍程度。

![文件信息的图像。](images/atp-file-information.png)

## <a name="alerts"></a>警报

" **警报** "选项卡提供与文件关联的警报列表。 此列表涵盖了大部分与警报队列相同的信息，但受影响的设备所属的设备组（如果有）除外。 您可以通过从列标题上方的工具栏中选择"自定义列"来选择显示的信息类型。

![与文件部分相关的警报的图像。](images/atp-alerts-related-to-file.png)

## <a name="observed-in-organization"></a>在组织中观测到

" **在组织中观测** 到"选项卡允许你指定日期范围，以查看已使用该文件观测到哪些设备。

> [!NOTE]
> 此选项卡将显示最多 100 台设备。 To see _all_ devices with the file， export the tab to a CSV file， by selecting **Export** from the action menu above the tab's column headers.

![包含文件的最近观察到设备的图像。](images/atp-observed-machines.png)

使用滑块或范围选择器快速指定要检查的与文件有关的事件的时间段。 可以将时间窗口指定为一天。 这样一来，你只能看到当时与该 IP 地址通信的文件，从而大大减少了不必要的滚动和搜索。

## <a name="deep-analysis"></a>深度分析

"**深度** 分析"选项卡允许您提交 [](respond-file-alerts.md#deep-analysis)文件进行深入分析，以发现有关文件行为的更多详细信息，以及文件在组织中的影响。 提交文件后，一旦结果可用，深入分析报告将显示在此选项卡中。 如果深度分析找不到任何内容，则报告将为空，并且结果空间将保留为空。

![深入分析选项卡的图像。](images/submit-file.png)

## <a name="file-names"></a>文件名

" **文件名** "选项卡列出了观测到的文件在组织中使用的所有名称。

![文件名选项卡的图像。](images/atp-file-names.png)

## <a name="related-topics"></a>相关主题

- [查看和组织 Microsoft Defender 终结点队列](alerts-queue.md)
- [管理 Microsoft Defender for Endpoint 警报](manage-alerts.md)
- [调查 Microsoft Defender for Endpoint 警报](investigate-alerts.md)
- [调查 Microsoft Defender 终结点设备列表中的设备](investigate-machines.md)
- [调查与 Microsoft Defender for Endpoint 警报关联的 IP 地址](investigate-ip.md)
- [调查与 Microsoft Defender for Endpoint 警报关联的域](investigate-domain.md)
- [调查 Microsoft Defender for Endpoint 中的用户帐户](investigate-user.md)
- [对文件执行响应操作](respond-file-alerts.md)
