---
title: 设置日程安排策略
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4b2c84ec-64d3-4027-af4c-40f69e7b37c9
description: 了解如何设置企业的计划策略。 计划策略包括约会长度以及可接受的潜在客户和取消时间。
ms.openlocfilehash: 82cc9a66e82665040a1f0d08635cae10cd413d4b
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419272"
---
# <a name="set-your-scheduling-policies"></a><span data-ttu-id="3a421-104">设置日程安排策略</span><span class="sxs-lookup"><span data-stu-id="3a421-104">Set your scheduling policies</span></span>

<span data-ttu-id="3a421-105">并非所有约会都相同。</span><span class="sxs-lookup"><span data-stu-id="3a421-105">Not all appointments are the same.</span></span> <span data-ttu-id="3a421-106">一些服务仅需要几分钟，而另一些可能需要数小时或数小时以上。</span><span class="sxs-lookup"><span data-stu-id="3a421-106">Some take only a few minutes, while others can take hours or more.</span></span> <span data-ttu-id="3a421-107">在 Microsoft Bookings 中，预订页面是设置企业日程安排策略的地方。</span><span class="sxs-lookup"><span data-stu-id="3a421-107">In Microsoft Bookings, the booking page is where you set the scheduling policies for your business.</span></span> <span data-ttu-id="3a421-108">计划策略包括约会长度、可接受的潜在客户和取消时间，以及预订更改的自动通知。</span><span class="sxs-lookup"><span data-stu-id="3a421-108">Scheduling policies include the length of appointments, acceptable lead and cancellation times, and automatic notifications of booking changes.</span></span> <span data-ttu-id="3a421-109">可以在"服务"页中为每项服务添加其他自定义项，其中附加的持续时间设置和策略仅适用于该服务。</span><span class="sxs-lookup"><span data-stu-id="3a421-109">Additional customization can be added for each service within the Services page, with additional duration settings and policies that apply only to that service.</span></span>

<span data-ttu-id="3a421-110">您在此处设置的策略是顶级策略。</span><span class="sxs-lookup"><span data-stu-id="3a421-110">The policies you set here are the top-level policies.</span></span> <span data-ttu-id="3a421-111">它们将自动应用于您提供的所有服务，除非您选择基于每个服务对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="3a421-111">They are automatically applied to all the services you offer unless you choose to modify them on a per-service basis.</span></span> <span data-ttu-id="3a421-112">例如，假设对于大多数服务（如初次预订）而言，一天取消通知是可接受的。</span><span class="sxs-lookup"><span data-stu-id="3a421-112">For example, let's say that for most services, such as initial consultations, one-day notice for cancellations is acceptable.</span></span> <span data-ttu-id="3a421-113">但是，对于需要设施预订或费用的服务（如课堂课程）可能需要三天的通知。</span><span class="sxs-lookup"><span data-stu-id="3a421-113">But for those services that require facility reservations or fees, such as golf lessons, you might require three days' notice.</span></span> <span data-ttu-id="3a421-114">您可以在"服务"页上设置此服务级别策略。</span><span class="sxs-lookup"><span data-stu-id="3a421-114">You can set this service-level policy on the Services page.</span></span> <span data-ttu-id="3a421-115">有关 [说明，请参阅定义](define-service-offerings.md) 服务产品/服务。</span><span class="sxs-lookup"><span data-stu-id="3a421-115">See [Define your service offerings](define-service-offerings.md) for instructions.</span></span>

## <a name="types-of-scheduling-policies"></a><span data-ttu-id="3a421-116">计划策略的类型</span><span class="sxs-lookup"><span data-stu-id="3a421-116">Types of scheduling policies</span></span>

<span data-ttu-id="3a421-117">此表说明了预订页面上可用的各种计划策略。</span><span class="sxs-lookup"><span data-stu-id="3a421-117">This table explains the various scheduling policies available on the booking page.</span></span>

| <span data-ttu-id="3a421-118">策略</span><span class="sxs-lookup"><span data-stu-id="3a421-118">Policy</span></span> | <span data-ttu-id="3a421-119">说明</span><span class="sxs-lookup"><span data-stu-id="3a421-119">Explanation</span></span> |
|---|---|
| <span data-ttu-id="3a421-120">时间增量</span><span class="sxs-lookup"><span data-stu-id="3a421-120">Time increments</span></span> | <span data-ttu-id="3a421-121">确定约会之间的间隔。</span><span class="sxs-lookup"><span data-stu-id="3a421-121">Determines the intervals between appointments.</span></span> <span data-ttu-id="3a421-122">可以将时间增量从 5 分钟设置为 4 小时。</span><span class="sxs-lookup"><span data-stu-id="3a421-122">You can set your time increments from 5 minutes to 4 hours.</span></span> <span data-ttu-id="3a421-123">还可以设置自己的自定义时间增量。</span><span class="sxs-lookup"><span data-stu-id="3a421-123">You can also set your own customized time increments.</span></span> <span data-ttu-id="3a421-124">例如，间隔 15 分钟意味着客户可以在 8：00、8：15、8：30 等时间安排 60 分钟的约会。</span><span class="sxs-lookup"><span data-stu-id="3a421-124">An interval of 15 minutes, for example, means a customer could schedule a 60-minute appointment at 8:00, 8:15, 8:30, and so on.</span></span> <span data-ttu-id="3a421-125">相反，60 分钟的间隔意味着只能在一小时进行约会。</span><span class="sxs-lookup"><span data-stu-id="3a421-125">Conversely, a 60-minute interval means that appointments are only available on the hour.</span></span> <span data-ttu-id="3a421-126"> (若要设置服务持续时间，请参阅 [定义服务产品](define-service-offerings.md)/) </span><span class="sxs-lookup"><span data-stu-id="3a421-126">(To set service durations, see [Define your service offerings](define-service-offerings.md).)</span></span> |
| <span data-ttu-id="3a421-127">前导时间（以小时表示）</span><span class="sxs-lookup"><span data-stu-id="3a421-127">Lead time in hours</span></span> | <span data-ttu-id="3a421-128">基于安排的约会构建员工计划，因此必须提前知道在任何特定日期有多少客户要提供服务。</span><span class="sxs-lookup"><span data-stu-id="3a421-128">You build your staffing plan based on the appointments that are scheduled so it's important to know in advance how many customers are coming in for service on any particular day.</span></span> <span data-ttu-id="3a421-129">提前时间策略使您可以指定客户必须提前预定或取消约会的小时数。</span><span class="sxs-lookup"><span data-stu-id="3a421-129">The lead time policy enables you to specify the number of hours in advance that customers must book or cancel an appointment.</span></span> |
| <span data-ttu-id="3a421-130">提前的最大天数</span><span class="sxs-lookup"><span data-stu-id="3a421-130">Maximum days in advance</span></span> | <span data-ttu-id="3a421-131">如果你想要限制客户提前预订约会的远远，那么这就是你的设置！</span><span class="sxs-lookup"><span data-stu-id="3a421-131">If you want to limit how far in advance customers can book appointments, then this is the setting for you!</span></span> <span data-ttu-id="3a421-132">可以将最大值设置为 365 天或更长。</span><span class="sxs-lookup"><span data-stu-id="3a421-132">You can set the maximum for 365 days or more.</span></span> |
| <span data-ttu-id="3a421-133">创建或更改预订时通知</span><span class="sxs-lookup"><span data-stu-id="3a421-133">Notify when a booking is created or changed</span></span> | <span data-ttu-id="3a421-134">如果希望每当客户预约或更改现有约会时接收电子邮件，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="3a421-134">Select this option when you want to receive an email any time a customer books an appointment or changes an existing one.</span></span> <span data-ttu-id="3a421-135">电子邮件将转到"业务信息"页上指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="3a421-135">The email will go to the mailbox specified on the Business information page.</span></span> <span data-ttu-id="3a421-136">有关详细信息 [，请参阅输入你的](enter-business-information.md) 业务信息。</span><span class="sxs-lookup"><span data-stu-id="3a421-136">See [Enter your business information](enter-business-information.md) for details.</span></span> |

## <a name="set-your-policies"></a><span data-ttu-id="3a421-137">设置策略</span><span class="sxs-lookup"><span data-stu-id="3a421-137">Set your policies</span></span>

1. <span data-ttu-id="3a421-138">在Microsoft 365中，选择应用启动器，然后选择 Bookings。</span><span class="sxs-lookup"><span data-stu-id="3a421-138">In Microsoft 365, select the app launcher, and then select Bookings.</span></span>

1. <span data-ttu-id="3a421-139">在导航窗格中，选择"**预订页面"。**</span><span class="sxs-lookup"><span data-stu-id="3a421-139">In the navigation pane, select **Booking page**.</span></span>

1. <span data-ttu-id="3a421-140">在"计划策略 **"部分下选择策略** 。</span><span class="sxs-lookup"><span data-stu-id="3a421-140">Select your policies under the **Scheduling policy** section.</span></span>

1. <span data-ttu-id="3a421-141">选择 **"保存并发布"。**</span><span class="sxs-lookup"><span data-stu-id="3a421-141">Select **Save and publish**.</span></span>

## <a name="publish-the-booking-page"></a><span data-ttu-id="3a421-142">发布预订页面</span><span class="sxs-lookup"><span data-stu-id="3a421-142">Publish the booking page</span></span>

<span data-ttu-id="3a421-143">准备好发布预订页面后，请选择"保存 **并发布"。**</span><span class="sxs-lookup"><span data-stu-id="3a421-143">When you're ready to publish your booking page, select **Save and publish**.</span></span> <span data-ttu-id="3a421-144">有关详细信息 [，请参阅自定义和发布](customize-booking-page.md) 你的预订页面。</span><span class="sxs-lookup"><span data-stu-id="3a421-144">See [Customize and publish your booking page](customize-booking-page.md) for more information.</span></span>
