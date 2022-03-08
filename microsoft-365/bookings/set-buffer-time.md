---
title: 在 Microsoft Bookings 中设置缓冲区时间
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: 在 Microsoft Bookings 中的约会之前或之后设置缓冲区时间，以留出时间清理或重置设备。
ms.openlocfilehash: a33159b0b5f168bbb61c88bc9b4181e05c8abbb1
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329315"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>在 Microsoft Bookings 中设置缓冲区时间

在与客户会面之前或之后，某些约会可能需要一些时间才能设置、清理或重置会议室和设备。 或者，如果你在客户约会之间出差，你可能需要一些时间来确保你和团队可以在约会之间出差，而无需客户等待。

你可以设置在约会开始、约会结束之后或两者同时设置的缓冲区时间，为员工提供准备下一个约会所需的额外时间。

## <a name="set-buffer-time-defaults"></a>设置缓冲区时间默认值

缓冲区时间默认值在 Bookings 的 **"服务详细信息"** 页面上设置。 与此页面上设置的所有服务默认值一样，你可以编辑这些默认值，以用于特定预订以满足特定的客户需求。

可以在"服务详细信息"页面上的"默认 **持续时间选取器** "正下方找到缓冲区 **时间** 设置。 必须先通过选择缓冲区时间切换来启用缓冲区时间设置，然后才能为给定服务设置它。 这将导致 **显示"之前"** 和"之后"下拉列表，它们用于选取每个预订之前和之后的默认保留时间，如下所示：

   ![启用缓冲区时间后 Bookings 的图像。](../media/bookings-buffertime.png)

<!--## Buffer time and appointment timing

To avoid confusion about when customers expect to meet with you, Bookings shows buffer time and actual appointment time (the time your customers expect to meet with you) on your calendar, and in email confirmations and reminders to relevant staff. For example, below is what you’d see in Bookings for an appointment with a customer that includes 15 minutes of pre-appointment buffer time.

Note that the event itself (on the left in the image below) shows lighter shading for the buffer time and darker shading for the actual customer appointment. The appointment call-out (which is opened when you select the event) specifically states that the appointment is from 9:00AM to 10:00AM with Katie Jordan and includes 15 minutes of buffer time before the appointment and 0 minutes after the appointment. Confirmations and reminders to staff similarly reference specific buffer and appointment time while the customer would only get confirmations and reminders that reference a 9:00AM to 10:00AM appointment time.

   ![Image of Bookings appointment call-out with buffer time showing.](../media/bookings-buffertime-callout.png)
-->

## <a name="buffer-time-and-availability"></a>缓冲区时间和可用性

你的客户不会直接看到并且无法更改你设置的缓冲区时间。 但是，由于缓冲区时间用于计算总体服务持续时间，因此客户将看到你和相关员工在缓冲区和常规约会时间都进行预订。 如果约会及其缓冲区时间足够，客户也只能看到你和员工是否可用。

例如，具有 15 分钟预先约会缓冲区的一小时约会需要至少 1 小时 15 分钟的可用时间块。 因此，此服务的约会将在您的日历上填写 75 分钟的时间块，并且需要 75 分钟的可用时间进行预订，而不会发生冲突。
