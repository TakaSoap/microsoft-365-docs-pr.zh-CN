---
title: 在 Microsoft 预订中设置缓冲时间
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: 在 Microsoft 预订中的约会前后设置缓冲时间，以允许清理或重置设备。
ms.openlocfilehash: 882ab0340fe56976429ed8294f2fa386b801941f
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962343"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>在 Microsoft 预订中设置缓冲时间

某些约会可能需要与客户进行设置、清理或重置会议室和设备之前或之后的时间。 或者，如果你正处于客户约会之间，你可能需要一些时间，以确保你和你的团队可以在两个约会之间旅行，而无需让客户等待。

您可以设置约会开始前、约会结束后的缓冲时间，也可以同时设置这两个时间，以便让员工在下一次约会中做额外的准备。

## <a name="set-buffer-time-defaults"></a>设置缓冲时间默认值

默认缓冲时间是在预订的 " **服务详细信息** " 页上设置的。 与此页面上设置的所有服务默认值一样，可以通过您的特定预定编辑这些默认值，以满足特定的客户需求。

可以在 "**服务详细信息**" 页上的 "**默认持续时间**" 选取器的正下方找到 "缓冲时间" 设置。 在可以设置给定服务的前，必须通过选择缓冲时间切换启用缓冲时间设置。 这会显示 " **之前** " 和 " **之后** " 下拉下拉选项，用于选取在每次预订之前和之后保留的默认时间量，如下所示：

   ![启用了缓冲时间的预订的映像](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a>缓冲时间和约会计时

为避免与客户希望与您见面时的混乱，预订将显示缓冲时间和实际约会时间 (客户预期与您在日历中) 的时间，以及电子邮件确认和提醒给相关人员的情况。 例如，下面是您在预订中为客户提供的约会，其中包含15分钟的预定前缓冲时间。

请注意，事件本身 (在下图的左侧) 显示较浅的阴影，用于实际客户约会的缓冲时间和深色底纹。 约会调用 (在您选择事件时打开) 具体说明约会是从9：00AM 到10：00AM，Katie，并在约会前的15分钟和约会后0分钟的缓冲时间。 对员工的确认和提醒类似于引用特定的缓冲和约会时间，而客户只会获取引用9：00AM 至10：00AM 约会时间的确认和提醒。

   ![显示了 "缓冲时间" 的预订约会呼叫图像](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a>缓冲时间和可用性

您的客户不会直接看到，并且无法更改您设置的缓冲时间。 但是，由于缓冲时间用于计算总体服务持续时间，客户将看到你和你的相关员工在缓冲和定期约会时间期间已预订。 如果约会和其缓冲时间有足够的时间，客户也只会看到你和你的员工的可用性。

例如，时间为15分钟的前置约会缓冲时间的一个小时约会要求至少1小时15分钟的可用时间段。 因此，此服务的约会将在您的日历上填充一个75分钟的时间段，并需要75分钟的时间才能进行预订而不会发生冲突。
