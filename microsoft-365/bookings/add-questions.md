---
title: 向预订页面添加自定义和必需的问题
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: fd6b7587-5055-4bcd-83a4-13bd4929bfff
description: 如果需要在客户在线预订约会时询问客户问题，可以将自定义问题和必填问题添加到预订页面。
ms.openlocfilehash: ebbb07857fd8bb196f769dfb7e71ad25a85dfd54
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419342"
---
# <a name="add-custom-and-required-questions-to-the-booking-page"></a><span data-ttu-id="a714f-103">向预订页面添加自定义和必需的问题</span><span class="sxs-lookup"><span data-stu-id="a714f-103">Add custom and required questions to the booking page</span></span>

<span data-ttu-id="a714f-104">Bookings 允许你创建问题，以在客户预订约会时询问客户。</span><span class="sxs-lookup"><span data-stu-id="a714f-104">Bookings lets you create questions to ask your customers when they are booking appointments.</span></span> <span data-ttu-id="a714f-105">它还允许你选择需要哪些问题。</span><span class="sxs-lookup"><span data-stu-id="a714f-105">It also lets you choose which questions are required.</span></span>

<span data-ttu-id="a714f-106">您将问题与服务关联，以便每个服务都可以有一组不同的问题。</span><span class="sxs-lookup"><span data-stu-id="a714f-106">You associate the questions with a service, so each service can have a different set of questions.</span></span> <span data-ttu-id="a714f-107">例如，发夹风格可能询问预订了发色约会的客户是否具有任何已知的脱字号或淡色。</span><span class="sxs-lookup"><span data-stu-id="a714f-107">For example, a hair stylist may ask customers who are booking a hair coloring appointment if they have any known allergies to bleaches or tints.</span></span> <span data-ttu-id="a714f-108">这允许你和客户在到达约会时节省时间。</span><span class="sxs-lookup"><span data-stu-id="a714f-108">This allows you and your customers to save time when they arrive for their appointment.</span></span>

<span data-ttu-id="a714f-109">客户在预订页面上创建约会时将看到自定义问题。</span><span class="sxs-lookup"><span data-stu-id="a714f-109">The customers will see the custom questions when they are creating their appointment on the booking page.</span></span> <span data-ttu-id="a714f-110">员工在从 Bookings 日历创建新预订或查看现有约会时将看到自定义问题。</span><span class="sxs-lookup"><span data-stu-id="a714f-110">Staff will see the custom questions when they create a new booking from the Bookings calendar or when viewing an existing appointment.</span></span> <span data-ttu-id="a714f-111">Bookings 会将所有问题保存到主列表中，这样您就不必为每个服务重新创建相同的问题。</span><span class="sxs-lookup"><span data-stu-id="a714f-111">Bookings saves all of your questions to a master list so that you don't have to re-create the same questions for every service.</span></span> <span data-ttu-id="a714f-112">还可以选择是必需还是可选问题。</span><span class="sxs-lookup"><span data-stu-id="a714f-112">You can also choose whether questions are required or optional.</span></span>

> [!NOTE]
> <span data-ttu-id="a714f-113">在预订日历中查看客户的约会时，可以看到客户的问题的答案。</span><span class="sxs-lookup"><span data-stu-id="a714f-113">The customer's answers to the questions can be seen when you look at their appointment in the booking calendar.</span></span>

<span data-ttu-id="a714f-114">若要详细了解如何个性化和自定义预订页面，请参阅 [自定义预订页面](customize-booking-page.md)。</span><span class="sxs-lookup"><span data-stu-id="a714f-114">For more information about how to personalize and customize your booking page, see [Customize your booking page](customize-booking-page.md).</span></span>

## <a name="add-custom-questions-to-your-services"></a><span data-ttu-id="a714f-115">向服务添加自定义问题</span><span class="sxs-lookup"><span data-stu-id="a714f-115">Add custom questions to your services</span></span>

1. <span data-ttu-id="a714f-116">登录以Microsoft 365然后转到 **Bookings**。</span><span class="sxs-lookup"><span data-stu-id="a714f-116">Sign in to Microsoft 365 and go to **Bookings**.</span></span>

1. <span data-ttu-id="a714f-117">转到"**服务**"，然后编辑现有服务或 **"添加服务"。**</span><span class="sxs-lookup"><span data-stu-id="a714f-117">Go to **Services** and either edit an existing service or **Add a service**.</span></span>

1. <span data-ttu-id="a714f-118">向下滚动到"自定义 **域"** 部分，然后选择"修改 **"。**</span><span class="sxs-lookup"><span data-stu-id="a714f-118">Scroll down to the **Custom fields** section, and then select **Modify**.</span></span>

   <span data-ttu-id="a714f-119">我们添加了一些基本的客户信息问题：客户电子邮件、电话号码、客户地址和客户注释。</span><span class="sxs-lookup"><span data-stu-id="a714f-119">We already added some basic customer information questions: Customer email, phone number, customer address, and customer notes.</span></span> <span data-ttu-id="a714f-120">第一次这样做时，客户信息问题以灰色突出显示。</span><span class="sxs-lookup"><span data-stu-id="a714f-120">The first time you do this, the customer information questions are highlighted in gray.</span></span> <span data-ttu-id="a714f-121">这意味着用户将看到此问题。</span><span class="sxs-lookup"><span data-stu-id="a714f-121">That means that the user will see this question.</span></span> <span data-ttu-id="a714f-122">如果选择该问题，它周围的突出显示框将消失，并且不会询问你的客户该问题。</span><span class="sxs-lookup"><span data-stu-id="a714f-122">If you select the question, the highlight box around it will disappear and your customer won't be asked that question.</span></span>

   <span data-ttu-id="a714f-123">此示例中，电话号码和客户注释已关闭，我们创建了两个新的自定义问题来询问。</span><span class="sxs-lookup"><span data-stu-id="a714f-123">In this example, phone number and customer notes have been turned off and we created two new custom questions to ask.</span></span>

   ![自定义问题屏幕的图像](../media/bookings-questions-custom-fields.png)

1. <span data-ttu-id="a714f-125">若要使问题成为必需问题，请选中 **"必需"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="a714f-125">To make the question required, select the **Required** checkbox.</span></span> <span data-ttu-id="a714f-126">在客户回答完所需问题之前，他们将无法完成预订。</span><span class="sxs-lookup"><span data-stu-id="a714f-126">Your customer won't be able to complete the booking until they've answered the required questions.</span></span>

1. <span data-ttu-id="a714f-127">若要创建自定义问题，请选择 **面板顶部的** "添加问题"。</span><span class="sxs-lookup"><span data-stu-id="a714f-127">To create a custom question, select **Add a question** from the top of the panel.</span></span> <span data-ttu-id="a714f-128">编写问题，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="a714f-128">Write your question, and then select **Save**.</span></span>

1. <span data-ttu-id="a714f-129">单击问题以启用它。</span><span class="sxs-lookup"><span data-stu-id="a714f-129">Click on the question to enable it.</span></span> <span data-ttu-id="a714f-130">它周围将出现一个突出显示框，并且问题已启用。</span><span class="sxs-lookup"><span data-stu-id="a714f-130">A highlighted box appears around it and the question is enabled.</span></span>

1. <span data-ttu-id="a714f-131">单击 **页面** 顶部的"确定"，然后单击"**保存服务"。**</span><span class="sxs-lookup"><span data-stu-id="a714f-131">Click **Ok** at the top of the page, and then **Save the service**.</span></span>

<span data-ttu-id="a714f-132">Bookings 将你的所有自定义问题保存在主列表中，以便你可以轻松地将问题添加到每个服务，而无需重复键入相同的问题。</span><span class="sxs-lookup"><span data-stu-id="a714f-132">Bookings will save all of your custom questions in a master list so that you can easily add questions to each service without needing to repeatedly type the same questions.</span></span> <span data-ttu-id="a714f-133">例如，如果打开其他服务，为第一个服务创建的问题会显示在"自定义字段"部分，但将被禁用。</span><span class="sxs-lookup"><span data-stu-id="a714f-133">For example, if you open a different service, the question you created for the first service will show in the Custom fields section, but it wil be disabled.</span></span> <span data-ttu-id="a714f-134">单击该问题，以便突出显示的矩形显示并启用该问题。</span><span class="sxs-lookup"><span data-stu-id="a714f-134">Click the question so that a highlighted rectangle displays and the question is enabled.</span></span>

<span data-ttu-id="a714f-135">此示例中，可以看到为第一个服务添加的问题可用于此服务。</span><span class="sxs-lookup"><span data-stu-id="a714f-135">In this example, you can see that the questions that were added for the first service are available for this service.</span></span> <span data-ttu-id="a714f-136">您为此服务创建的任何问题都将可用于所有服务。</span><span class="sxs-lookup"><span data-stu-id="a714f-136">Any questions you create for this service will be available for all services.</span></span>

   ![针对多个服务显示的问题的图像](../media/bookings-questions-services.png)

<span data-ttu-id="a714f-138">如果预订页面已发布，则无需执行任何其他工作。</span><span class="sxs-lookup"><span data-stu-id="a714f-138">If your booking page is already published, you don't need to do anything else.</span></span> <span data-ttu-id="a714f-139">客户将在下次预订时看到问题。</span><span class="sxs-lookup"><span data-stu-id="a714f-139">Customers will see the questions the next time they book with you.</span></span> <span data-ttu-id="a714f-140">如果尚未发布你的预订页面，请从网页Outlook预订页面，然后选择保存 **并发布**。</span><span class="sxs-lookup"><span data-stu-id="a714f-140">If your booking page isn't published yet, go to the **booking page** from Outlook on the web, and then select **Save and publish**.</span></span>

> [!WARNING]
> <span data-ttu-id="a714f-141">您还可以从主列表中删除问题。</span><span class="sxs-lookup"><span data-stu-id="a714f-141">You can also delete questions from the master list.</span></span> <span data-ttu-id="a714f-142">但是，如果您删除某个问题，它将从每个服务中删除。</span><span class="sxs-lookup"><span data-stu-id="a714f-142">However, if you delete a question it will be deleted from every service.</span></span> <span data-ttu-id="a714f-143">建议您通过选择该问题来禁用该问题，以确保不会影响任何其他服务。</span><span class="sxs-lookup"><span data-stu-id="a714f-143">We recommend that you disable the question by selecting it to ensure you do not impact any other services.</span></span> <span data-ttu-id="a714f-144">如果问题未被突出显示的矩形包围，则会看到该问题被禁用。</span><span class="sxs-lookup"><span data-stu-id="a714f-144">You can see that a question is disabled if it is not surrounded by a highlighted rectangle.</span></span>

## <a name="customer-experience"></a><span data-ttu-id="a714f-145">客户体验</span><span class="sxs-lookup"><span data-stu-id="a714f-145">Customer experience</span></span>

<span data-ttu-id="a714f-146">当你的客户预订约会时，基本客户信息问题会显示在添加 **你的详细信息部分中** 。</span><span class="sxs-lookup"><span data-stu-id="a714f-146">When your customers book an appointment with you, the basic customer information questions will show in the **Add your details** section.</span></span> <span data-ttu-id="a714f-147">您添加的任何自定义问题将位于" **提供其他信息"部分** 。</span><span class="sxs-lookup"><span data-stu-id="a714f-147">Any customized questions you add will be in the **Provide additional information** section.</span></span>

![启用问题时客户看到的图像](../media/bookings-questions-customer.png)

## <a name="staff-experience"></a><span data-ttu-id="a714f-149">员工体验</span><span class="sxs-lookup"><span data-stu-id="a714f-149">Staff experience</span></span>

<span data-ttu-id="a714f-150">当你的客户预订约会时，你的员工将在预订日历上看到问题和客户的答案。</span><span class="sxs-lookup"><span data-stu-id="a714f-150">When your customers book an appointment with you, your staff will see the questions and the customer's answers on the booking calendar.</span></span> <span data-ttu-id="a714f-151">To see it， go to **Bookings** \> **Calendar** and then open an appointment.</span><span class="sxs-lookup"><span data-stu-id="a714f-151">To see it, go to **Bookings** \> **Calendar** and then open an appointment.</span></span>

![启用问题时员工看到的图像](../media/bookings-questions-staff.png)
