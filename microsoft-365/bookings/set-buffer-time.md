---
title: 在 Microsoft Bookings 中设置缓冲区时间
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: 在 Microsoft Bookings 中的约会之前或之后设置缓冲区时间，以留出时间清理或重置设备。
ms.openlocfilehash: 21830b0cc1ec2f14bc845937387e700fb7a2ee72
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59200773"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>在 Microsoft Bookings 中设置缓冲区时间

在与客户会面之前或之后，某些约会可能需要一些时间才能设置、清理或重置会议室和设备。 或者，如果你在客户约会之间出差，你可能需要一些时间来确保你和团队可以在约会之间出差，而无需客户等待。

你可以设置在约会开始、约会结束之后或两者同时设置的缓冲区时间，为员工提供准备下一个约会所需的额外时间。

## <a name="set-buffer-time-defaults"></a>设置缓冲区时间默认值

缓冲区时间默认值在 Bookings 的 **"服务详细信息"** 页面上设置。 与此页面上设置的所有服务默认值一样，你可以编辑这些默认值，以用于特定预订以满足特定的客户需求。

可以在"服务详细信息"页面上的"默认持续时间 **选取器** "正下方找到缓冲区 **时间** 设置。 必须先通过选择缓冲区时间切换来启用缓冲区时间设置，然后才能为给定服务设置它。 这将导致 **显示"之前"** 和"之后"下拉列表，它们用于选取每个预订之前和之后的默认保留时间，如下所示： 

   ![启用缓冲区时间后 Bookings 的图像。](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a>缓冲区时间和约会计时

为了避免客户期望何时与你们会面，Bookings 在日历上以及向相关员工的电子邮件确认和提醒中显示 (客户预期与) 会面的缓冲时间和实际约会时间。 例如，下面是你在 Bookings 中看到的客户约会包含 15 分钟预约会缓冲区时间的内容。

请注意，事件本身 (位于图像左侧，) 显示缓冲区时间较浅的底纹，而实际客户约会的底纹较深。 约会调用 (在选择事件时打开) 具体指出约会与 Katie Jordan 的上午 9：00 到 10：00 之间，包括约会前的 15 分钟缓冲区时间以及约会后 0 分钟。 员工确认和提醒同样引用特定缓冲区和约会时间，而客户只会收到引用上午 9：00 到上午 10：00 约会时间的确认和提醒。

   ![显示缓冲区时间后 Bookings 约会调用的图像。](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a>缓冲区时间和可用性

你的客户不会直接看到并且无法更改你设置的缓冲区时间。 但是，由于缓冲区时间用于计算总体服务持续时间，因此客户将看到你和相关员工在缓冲区和常规约会时间都进行预订。 如果约会及其缓冲区时间足够，客户也只能看到你和员工是否可用。

例如，具有 15 分钟预先约会缓冲区的一小时约会需要至少 1 小时 15 分钟的可用时间块。 因此，此服务的约会将填充日历上的 75 分钟时间块，并且需要 75 分钟的可用时间才能预订而不会发生冲突。
