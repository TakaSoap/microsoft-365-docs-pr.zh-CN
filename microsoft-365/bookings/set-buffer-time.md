---
title: 在Microsoft Bookings中设置缓冲区时间
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: 在Microsoft Bookings中设置约会前后的缓冲区时间，以便有时间清理或重置设备。
ms.openlocfilehash: 28d4c7feb76770cb40f5a780c2d406dc3bfeef8d
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64714694"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>在Microsoft Bookings中设置缓冲区时间

> [!NOTE]
> 本文可帮助你与最新版本的Microsoft Bookings交互。 以前的版本将在未来几个月内停用。

与客户会面之前或之后，某些约会可能需要一些时间来设置、清理或重置房间和设备。 或者，如果你在客户约会之间，可能需要时间来确保你和你的团队可以在约会之间旅行，而无需让客户等待。

你可以在约会开始前、约会结束后设置缓冲时间，也可以为员工提供准备下一次约会所需的额外时间。

## <a name="set-buffer-time-defaults"></a>设置缓冲区时间默认值

缓冲区时间默认设置在Bookings中的 **"服务详细信息**"页上。 与此页上设置的所有服务默认值一样，可以编辑这些默认值以进行特定预订以满足特定的客户需求。

可以在 **"服务详细信息** "页上找到缓冲区时间设置。 在为给定服务设置缓冲区时间设置之前，必须通过选择缓冲区时间切换来启用缓冲区时间设置。 这会导致出现 **"前****后**"下拉列表，这些下拉列表用于选择每次预订前后要保留的默认时间，如下所示：

   ![启用了缓冲区时间的Bookings的图像。](../media/bookings-buffertime.png)

<!--## Buffer time and appointment timing

To avoid confusion about when customers expect to meet with you, Bookings shows buffer time and actual appointment time (the time your customers expect to meet with you) on your calendar, and in email confirmations and reminders to relevant staff. For example, below is what you’d see in Bookings for an appointment with a customer that includes 15 minutes of pre-appointment buffer time.

Note that the event itself (on the left in the image below) shows lighter shading for the buffer time and darker shading for the actual customer appointment. The appointment call-out (which is opened when you select the event) specifically states that the appointment is from 9:00AM to 10:00AM with Katie Jordan and includes 15 minutes of buffer time before the appointment and 0 minutes after the appointment. Confirmations and reminders to staff similarly reference specific buffer and appointment time while the customer would only get confirmations and reminders that reference a 9:00AM to 10:00AM appointment time.

   ![Image of Bookings appointment call-out with buffer time showing.](../media/bookings-buffertime-callout.png)
-->

## <a name="buffer-time-and-availability"></a>缓冲区时间和可用性

客户不会直接看到，也不能更改设置的缓冲区时间。 但是，由于缓冲区时间用于计算整体服务持续时间，因此客户会在缓冲区和常规约会时间看到你和你的相关员工已预订。 客户仅在约会及其缓冲时间都有足够的时间时，才会看到你和你的员工可用性。

例如，具有 15 分钟的预约会缓冲区的一小时约会需要至少 1 小时 15 分钟的可用时间块。 因此，此服务的约会将填满日历上的 75 分钟时间块，并且需要 75 分钟的可用性才能预订，而不会发生冲突。
