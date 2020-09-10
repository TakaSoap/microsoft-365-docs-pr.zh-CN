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
ms.openlocfilehash: dceb777f9ddba9f1ddabfee00608813afae57a86
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419275"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a><span data-ttu-id="b6582-103">在 Microsoft 预订中设置缓冲时间</span><span class="sxs-lookup"><span data-stu-id="b6582-103">Set buffer time in Microsoft Bookings</span></span>

<span data-ttu-id="b6582-104">某些约会可能需要与客户进行设置、清理或重置会议室和设备之前或之后的时间。</span><span class="sxs-lookup"><span data-stu-id="b6582-104">Some of your appointments might require time before or after you meet with your customer to set up, clean up, or reset your room and equipment.</span></span> <span data-ttu-id="b6582-105">或者，如果你正处于客户约会之间，你可能需要一些时间，以确保你和你的团队可以在两个约会之间旅行，而无需让客户等待。</span><span class="sxs-lookup"><span data-stu-id="b6582-105">Or if you’re on the road between customer appointments, you may need time to ensure you and your team can travel between appointments without making the customer wait.</span></span>

<span data-ttu-id="b6582-106">您可以设置约会开始前、约会结束后的缓冲时间，也可以同时设置这两个时间，以便让员工在下一次约会中做额外的准备。</span><span class="sxs-lookup"><span data-stu-id="b6582-106">You can set buffer time before appointments start, after appointments end, or both to give staff the extra time they need to prepare for their next appointment.</span></span>

> [!NOTE]
> <span data-ttu-id="b6582-107">默认情况下，对于拥有 Microsoft 365 商业标准、Microsoft 365 A3 或 Microsoft 365 A5 订阅的客户，预订处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="b6582-107">Bookings is turned on by default for customers who have the Microsoft 365 Business Standard, Microsoft 365 A3, or Microsoft 365 A5 subscriptions.</span></span> <span data-ttu-id="b6582-108">预订也适用于拥有 Office 365 企业版 E3 和 Office 365 企业版 E5 的客户，但默认情况下它处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="b6582-108">Bookings is also available to customers who have Office 365 Enterprise E3 and Office 365 Enterprise E5, but it is turned off by default.</span></span> <span data-ttu-id="b6582-109">若要开始，请参阅 [获取 Microsoft 预订的访问权限](get-access.md)。</span><span class="sxs-lookup"><span data-stu-id="b6582-109">To get started, see [Get access to Microsoft Bookings](get-access.md).</span></span> <span data-ttu-id="b6582-110">若要打开或关闭预订，请参阅 [开启或关闭组织的预订](turn-bookings-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="b6582-110">To turn Bookings on or off, see [Turn Bookings on or off for your organization](turn-bookings-on-or-off.md).</span></span>

## <a name="set-buffer-time-defaults"></a><span data-ttu-id="b6582-111">设置缓冲时间默认值</span><span class="sxs-lookup"><span data-stu-id="b6582-111">Set buffer time defaults</span></span>

<span data-ttu-id="b6582-112">默认缓冲时间是在预订的 " **服务详细信息** " 页上设置的。</span><span class="sxs-lookup"><span data-stu-id="b6582-112">Buffer time defaults are set on the **Service details** page in Bookings.</span></span> <span data-ttu-id="b6582-113">与此页面上设置的所有服务默认值一样，可以通过您的特定预定编辑这些默认值，以满足特定的客户需求。</span><span class="sxs-lookup"><span data-stu-id="b6582-113">Like all service defaults set on this page, these defaults can be edited by you for a specific booking to meet specific customer needs.</span></span>

<span data-ttu-id="b6582-114">可以在 "**服务详细信息**" 页上的 "**默认持续时间**" 选取器的正下方找到 "缓冲时间" 设置。</span><span class="sxs-lookup"><span data-stu-id="b6582-114">The buffer time setting can be found just below the **Default duration** pickers on the **Service details** page.</span></span> <span data-ttu-id="b6582-115">在可以设置给定服务的前，必须通过选择缓冲时间切换启用缓冲时间设置。</span><span class="sxs-lookup"><span data-stu-id="b6582-115">Before it can be set for a given service, you must enable the buffer time setting by selecting the buffer time toggle.</span></span> <span data-ttu-id="b6582-116">这会显示 " **之前** " 和 " **之后** " 下拉下拉选项，用于选取在每次预订之前和之后保留的默认时间量，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6582-116">This causes the **Before** and **After** drop-downs to appear, which are used to pick the default amount of time to hold before and after each booking, as shown here:</span></span>

   ![启用了缓冲时间的预订的映像](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a><span data-ttu-id="b6582-118">缓冲时间和约会计时</span><span class="sxs-lookup"><span data-stu-id="b6582-118">Buffer time and appointment timing</span></span>

<span data-ttu-id="b6582-119">为避免与客户希望与您见面时的混乱，预订将显示缓冲时间和实际约会时间 (客户预期与您在日历中) 的时间，以及电子邮件确认和提醒给相关人员的情况。</span><span class="sxs-lookup"><span data-stu-id="b6582-119">To avoid confusion about when customers expect to meet with you, Bookings shows buffer time and actual appointment time (the time your customers expect to meet with you) on your calendar, and in email confirmations and reminders to relevant staff.</span></span> <span data-ttu-id="b6582-120">例如，下面是您在预订中为客户提供的约会，其中包含15分钟的预定前缓冲时间。</span><span class="sxs-lookup"><span data-stu-id="b6582-120">For example, below is what you’d see in Bookings for an appointment with a customer that includes 15 minutes of pre-appointment buffer time.</span></span>

<span data-ttu-id="b6582-121">请注意，事件本身 (在下图的左侧) 显示较浅的阴影，用于实际客户约会的缓冲时间和深色底纹。</span><span class="sxs-lookup"><span data-stu-id="b6582-121">Note that the event itself (on the left in the image below) shows lighter shading for the buffer time and darker shading for the actual customer appointment.</span></span> <span data-ttu-id="b6582-122">约会调用 (在您选择事件时打开) 具体说明约会是从9：00AM 到10：00AM，Katie，并在约会前的15分钟和约会后0分钟的缓冲时间。</span><span class="sxs-lookup"><span data-stu-id="b6582-122">The appointment call-out (which is opened when you select the event) specifically states that the appointment is from 9:00AM to 10:00AM with Katie Jordan and includes 15 minutes of buffer time before the appointment and 0 minutes after the appointment.</span></span> <span data-ttu-id="b6582-123">对员工的确认和提醒类似于引用特定的缓冲和约会时间，而客户只会获取引用9：00AM 至10：00AM 约会时间的确认和提醒。</span><span class="sxs-lookup"><span data-stu-id="b6582-123">Confirmations and reminders to staff similarly reference specific buffer and appointment time while the customer would only get confirmations and reminders that reference a 9:00AM to 10:00AM appointment time.</span></span>

   ![显示了 "缓冲时间" 的预订约会呼叫图像](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a><span data-ttu-id="b6582-125">缓冲时间和可用性</span><span class="sxs-lookup"><span data-stu-id="b6582-125">Buffer time and availability</span></span>

<span data-ttu-id="b6582-126">您的客户不会直接看到，并且无法更改您设置的缓冲时间。</span><span class="sxs-lookup"><span data-stu-id="b6582-126">Your customers don’t directly see and cannot change the buffer times you set.</span></span> <span data-ttu-id="b6582-127">但是，由于缓冲时间用于计算总体服务持续时间，客户将看到你和你的相关员工在缓冲和定期约会时间期间已预订。</span><span class="sxs-lookup"><span data-stu-id="b6582-127">However, because buffer time is used to calculate overall service duration, customers will see you and your relevant staff as booked during both buffer and regular appointment times.</span></span> <span data-ttu-id="b6582-128">如果约会和其缓冲时间有足够的时间，客户也只会看到你和你的员工的可用性。</span><span class="sxs-lookup"><span data-stu-id="b6582-128">Customers also only see availability for you and your staff if there is enough time for both the appointment and its buffer time.</span></span>

<span data-ttu-id="b6582-129">例如，时间为15分钟的前置约会缓冲时间的一个小时约会要求至少1小时15分钟的可用时间段。</span><span class="sxs-lookup"><span data-stu-id="b6582-129">As an example, a one-hour appointment with a 15-minute pre-appointment buffer time requires an available time block of at least 1 hour and 15 minutes.</span></span> <span data-ttu-id="b6582-130">因此，此服务的约会将在您的日历上填充一个75分钟的时间段，并需要75分钟的时间才能进行预订而不会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="b6582-130">An appointment for this service would therefore fill a 75-minute block of time on your calendar and needs 75 minutes of availability to book without conflict.</span></span>
