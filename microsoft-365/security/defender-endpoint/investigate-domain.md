---
title: 调查 Microsoft Defender 终结点域
description: 使用调查选项查看设备和服务器是否一直与恶意域通信。
keywords: 调查域， 域， 恶意域， Microsoft Defender for Endpoint， 警报， URL
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 9f2514c0f43bd8a7f1ab5dade389c0a12f3c4e54
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2021
ms.locfileid: "60587785"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a>调查与 Microsoft Defender for Endpoint 警报关联的域

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatedomain-abovefoldlink)。

调查域，以查看企业网络中设备和服务器是否一直与已知的恶意域通信。

可以使用搜索功能或单击设备时间线中的域链接来调查 **域**。

您可以在 URL 视图中查看以下部分的信息：

- URL 详细信息、联系人、名称服务器
- 与此 URL 相关的警报 
- 组织中 URL
- 最近观察到的具有 URL 的设备

## <a name="url-worldwide"></a>全球 URL

" **全球 URL"** 部分列出了 URL、指向 Whois 的更多详细信息的链接、相关打开事件的数量以及活动警报的数量。

## <a name="incident"></a>事件

事件 **卡片** 显示过去 180 天内所有事件活动警报的条形图。

## <a name="prevalence"></a>普遍程度

**"普遍** 程度"卡片提供指定时段内组织中 URL 的普遍程度的详细信息。

尽管默认时间段是过去 30 天，但可以通过选择卡片右上角的向下箭头来自定义范围。 可用范围最短的是过去一天的普遍程度，最长范围是过去 6 个月。

## <a name="alerts"></a>警报

" **警报** "选项卡提供与 URL 关联的警报列表。 此处显示的表是警报队列屏幕上显示的警报的筛选版本，只显示与域关联的警报、严重性、状态、关联事件、分类、调查状态等。

通过从列标题上方的操作菜单中选择"自定义列"，可以调整"通知"选项卡以显示更多或更少的信息。 通过在同一菜单上选择每页的项目， **还可以调整显示** 的项目数。

## <a name="observed-in-organization"></a>在组织中观测到

" **在组织中观测** 到"选项卡提供有关在 URL 上观测到的事件和关联警报按时间顺序排列的视图。 此选项卡包括时间线和可自定义的表格，其中列出了事件详细信息，如时间、设备和所发生事件的简要说明。 

可以通过在表格标题上方的文本字段中输入日期来查看不同时间段的事件。 您还可以通过选择时间线的不同区域来自定义时间范围。

**调查域：**

1. 从搜索栏 **下拉菜单中选择** **URL。**
2. 在"搜索"字段中 **输入** URL。
3. 单击搜索图标或按 **Enter。** 将显示有关 URL 的详细信息。 注意：将仅返回在来自组织中设备的通信中观察到的 URL 的搜索结果。
4. 使用搜索筛选器定义搜索条件。 您还可以使用时间线搜索框筛选组织中观测到与 URL 通信的所有设备的显示结果、与通信关联的文件和上次观测日期。
5. 单击任何设备名称将进入该设备的视图，你可以继续调查报告的警报、行为和事件。

## <a name="related-topics"></a>相关主题
- [查看并组织 Microsoft Defender for Endpoint 警报队列](alerts-queue.md)
- [管理 Microsoft Defender for Endpoint 警报](manage-alerts.md)
- [调查 Microsoft Defender for Endpoint 警报](investigate-alerts.md)
- [调查与 Microsoft Defender for Endpoint 警报关联的文件](investigate-files.md)
- [调查 Microsoft Defender 终结点设备列表中的设备](investigate-machines.md)
- [调查与 Microsoft Defender for Endpoint 警报关联的 IP 地址](investigate-ip.md)
- [调查 Microsoft Defender for Endpoint 中的用户帐户](investigate-user.md)
