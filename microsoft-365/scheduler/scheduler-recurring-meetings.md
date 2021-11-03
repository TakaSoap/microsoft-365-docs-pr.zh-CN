---
title: 安排动态定期会议
ms.author: sarichardson
author: sallyri
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
ms.reviewer: strettin
ms.localizationpriority: medium
description: 用户可以详细了解如何安排动态定期会议。
ms.openlocfilehash: d4f99b336088e7c565c741a8f631e4fefbada68f
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60701269"
---
# <a name="scheduling-dynamic-recurring-meetings"></a>安排动态定期会议

计划程序的动态会议围绕用户的忙碌日程安排工作。 由计划程序管理的定期会议的行为不同于计划中传统的定期Outlook。 若要使未来日历保持打开状态并最大限度地减少与与会者的冲突，计划程序将一次安排一个定期会议实例。

例如，要求Cortana"安排每天 30 分钟专注时间"最初将在日历上创建一个 30 分钟的约会，用于下一个可用日期。  约会时间一过，计划程序将在下一天继续预订另一个实例。 如果原始时间段当前不可用，则计划程序将根据您的可用性调整时间。

相同的启发方法可应用于受邀者的会议。 你可以将与会者包括在请求中，并要求Cortana"每两周安排一次会议"。 将基于组织中所有与会者的当前可用性动态安排第一个和每个连续会议。 如果你或与会者下一天不办公或外出，会议时间将自动调整为当每个人都可用时，并且根据新安排的日期为后续会议实例保留所需的节奏。

## <a name="booking-with-attendees-outside-your-organization"></a>与组织外部的与会者一起预订

在安排组织外部与会者时，虚拟助理会发送第一次会议的外部与会者时间选项。 将基于组织者和内部与会者的可用性自动安排所有将来的会议。

计划程序支持每天、每周和每月间隔。

## <a name="examples-of-how-to-request-recurring-meetings"></a>如何请求定期会议的示例

下面是一些如何通过电子邮件Cortana定期会议的示例：

- "Cortana，每 2 周安排一次会议。"
- "每月 30 分钟预订一次评价。"
- "Cortana将找到 30 分钟让我们每周二开会的时间。"
- "Cortana，每周五下午 3：30 安排 30 分钟"

## <a name="changing-recurring-frequency"></a>更改定期频率

可以更改由计划程序管理的任何定期会议或非定期会议的频率。 答复Cortana来自会议线程中最后一封确认电子邮件的邮件，Cortana：

- "将此选项更改为每月一次。"
- "Cortana，每两周召开一次此会议。"

## <a name="cancelling-recurring-meetings"></a>取消定期会议

您可以回复Cortana确认消息，并要求"取消此会议"以取消计划的实例。 但是，计划程序将继续以相同的频率安排将来的会议。 或者，您可以仅要求计划程序将下一个实例重新安排到所需日期或时间。 如果要取消整个定期系列，请响应"取消此系列"，并且不会计划任何未来实例。

## <a name="recurring-meeting-limitations"></a>定期会议限制

请注意，定期计划程序可以理解和支持的定期类型存在一些技术限制：

- 不支持在同一间隔内多次 (例如："每周两次") 。
- 不支持重复周期的结束日期 (例如："12 月 20 日之前的每一天") 。 由于每个会议都安排在上一次会议完成时，只需使用"取消此会议系列Cortana回复来自会议的最新消息。
- 计划程序当前不支持大于 90 天的定期频率。
