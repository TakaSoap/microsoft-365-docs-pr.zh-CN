---
title: 在 Microsoft 预订中设置语言和时区
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 94af3e22-aca6-4e91-8b91-1cd5a02a9ea8
description: 在 Microsoft 预订中更改语言和时区设置。 如果在错误的时间创建了预订，则可能会为错误的时区设置预订。
ms.openlocfilehash: 07e5dde2a896610ee079063943aff24ec69ba721
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419273"
---
# <a name="set-language-and-time-zones-in-microsoft-bookings"></a><span data-ttu-id="32c3d-104">在 Microsoft 预订中设置语言和时区</span><span class="sxs-lookup"><span data-stu-id="32c3d-104">Set language and time zones in Microsoft Bookings</span></span>

<span data-ttu-id="32c3d-105">如果您使用的是 Microsoft 预订且在错误的时间创建了预订，则可能需要更改时区设置。</span><span class="sxs-lookup"><span data-stu-id="32c3d-105">If you are using Microsoft Bookings and bookings are created at the wrong time, then your time zone settings might need to be changed.</span></span> <span data-ttu-id="32c3d-106">同样，如果某些预订采用错误的语言，则可能需要更改您的语言设置。</span><span class="sxs-lookup"><span data-stu-id="32c3d-106">Likewise, if some bookings are in the wrong language, you might need to change your language settings.</span></span>

<span data-ttu-id="32c3d-107">有两种独立的语言和时区设置可用于预订。</span><span class="sxs-lookup"><span data-stu-id="32c3d-107">There are two separate language and time zone settings for Bookings.</span></span> <span data-ttu-id="32c3d-108">第一个设置控制预订日历的语言和时区，并使用 Outlook 在登录用户的个人日历的 web 设置上进行设置。</span><span class="sxs-lookup"><span data-stu-id="32c3d-108">The first setting controls the language and time zone of the booking calendar and is set using the Outlook on the web settings for the personal calendar of the logged-in user.</span></span> <span data-ttu-id="32c3d-109">第二个设置影响客户使用的自助式预订页面，并使用 "区域设置" 页面设置，该页面仅控制该页面的语言和时区。</span><span class="sxs-lookup"><span data-stu-id="32c3d-109">The second setting affects the self-service booking page that your customers use and is set using a "regional settings" page that controls language and time zone only for that page.</span></span>

> [!NOTE]
> <span data-ttu-id="32c3d-110">默认情况下，对于拥有 Microsoft 365 商业标准、Microsoft 365 A3 或 Microsoft 365 A5 订阅的客户，预订处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="32c3d-110">Bookings is turned on by default for customers who have the Microsoft 365 Business Standard, Microsoft 365 A3, or Microsoft 365 A5 subscriptions.</span></span> <span data-ttu-id="32c3d-111">预订也适用于拥有 Office 365 企业版 E3 和 Office 365 企业版 E5 的客户，但默认情况下它处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="32c3d-111">Bookings is also available to customers who have Office 365 Enterprise E3 and Office 365 Enterprise E5, but it is turned off by default.</span></span> <span data-ttu-id="32c3d-112">若要开始，请参阅 [获取 Microsoft 预订的访问权限](get-access.md)。</span><span class="sxs-lookup"><span data-stu-id="32c3d-112">To get started, see [Get access to Microsoft Bookings](get-access.md).</span></span> <span data-ttu-id="32c3d-113">若要打开或关闭预订，请参阅 [开启或关闭组织的预订](turn-bookings-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="32c3d-113">To turn Bookings on or off, see [Turn Bookings on or off for your organization](turn-bookings-on-or-off.md).</span></span>

## <a name="setting-language-and-time-zone-for-a-booking-calendar"></a><span data-ttu-id="32c3d-114">为预订日历设置语言和时区</span><span class="sxs-lookup"><span data-stu-id="32c3d-114">Setting language and time zone for a booking calendar</span></span>

<span data-ttu-id="32c3d-115">预订日历使用已登录用户的语言和时区设置。</span><span class="sxs-lookup"><span data-stu-id="32c3d-115">The booking calendar uses the logged-in user’s language and time zone settings.</span></span> <span data-ttu-id="32c3d-116">例如，如果登录用户的时区设置为东部标准时间 (EST) ，则预订日历将在 EST 中显示现有的约会开始时间和结束时间。</span><span class="sxs-lookup"><span data-stu-id="32c3d-116">For example, If the logged-in user’s time zone is set to Eastern Standard Time (EST), then the booking calendar will show existing appointment start and end times in EST.</span></span> <span data-ttu-id="32c3d-117">此时区最初是在用户的 Microsoft 365 和 Outlook 网页帐户上创建时设置的。</span><span class="sxs-lookup"><span data-stu-id="32c3d-117">This time zone was originally set when the user’s Microsoft 365 and Outlook on the web accounts were created.</span></span>

<span data-ttu-id="32c3d-118">若要设置预订日历的语言和时区，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="32c3d-118">To set the language and time zone for the booking calendar:</span></span>

1. <span data-ttu-id="32c3d-119">登录到 Microsoft 365 并在登陆页上选择 "Outlook 磁贴" (如下面的屏幕截图所示) 或 Microsoft 365 应用启动器中所示。</span><span class="sxs-lookup"><span data-stu-id="32c3d-119">Log into Microsoft 365 and select the Outlook tile on the landing page (as shown in the screenshot below) or in the Microsoft 365 App Launcher.</span></span>

   ![Microsoft 365 登录页上的 Outlook 磁贴的图像](../media/bookings-outlook-tile.png)

1. <span data-ttu-id="32c3d-121">打开 Outlook 后，选择屏幕右上角的 **齿轮图标** 以打开您的个人和帐户设置，然后在 " **设置** " 面板搜索框中搜索 "时区"。</span><span class="sxs-lookup"><span data-stu-id="32c3d-121">After Outlook opens, select the **gear icon** in the upper, right-hand corner of the screen to open your personal and account settings, then search for “time zone” in the **Settings** panel search box.</span></span> <span data-ttu-id="32c3d-122">面板将更新，以显示此帐户的当前个人语言和时区设置。</span><span class="sxs-lookup"><span data-stu-id="32c3d-122">The panel will update to show your current personal language and time zone settings for this account.</span></span> <span data-ttu-id="32c3d-123">如上文所述，此设置还控制预定日历的语言和时区。</span><span class="sxs-lookup"><span data-stu-id="32c3d-123">As noted above, this setting also controls the language and time zone of the booking calendar.</span></span>

1. <span data-ttu-id="32c3d-124">通过在 " **语言" 或 "当前时区** " 框中选择下拉箭头，然后选择所需的设置来更改语言或时区。</span><span class="sxs-lookup"><span data-stu-id="32c3d-124">Change the language or time zone by selecting the drop-down arrow in the **Language or Current time zone** box and choosing the desired setting.</span></span>

1. <span data-ttu-id="32c3d-125">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="32c3d-125">Click **Save**.</span></span> <span data-ttu-id="32c3d-126">"设置" 面板将关闭，Outlook 在 web 上重新启动，并应用新的语言和时区设置。</span><span class="sxs-lookup"><span data-stu-id="32c3d-126">The Settings panel closes, Outlook on the web restarts, and the new language and time zone settings are applied.</span></span>

## <a name="setting-the-language-and-time-zone-for-the-booking-page"></a><span data-ttu-id="32c3d-127">为预订页面设置语言和时区</span><span class="sxs-lookup"><span data-stu-id="32c3d-127">Setting the language and time zone for the booking page</span></span>

1. <span data-ttu-id="32c3d-128">在 Microsoft 365 中，选择应用启动器，然后选择 " **预订**"。</span><span class="sxs-lookup"><span data-stu-id="32c3d-128">In Microsoft 365, select the app launcher, and then select **Bookings**.</span></span>

1. <span data-ttu-id="32c3d-129">在导航窗格中，选择 " **预订页面** "，然后选择 " **更改语言和时区设置**"。</span><span class="sxs-lookup"><span data-stu-id="32c3d-129">In the navigation pane, select **Booking page** and select **Change language and time zone settings**.</span></span>

   ![屏幕截图：更改语言和时区设置链接](../media/bookings-region-language-timezone-settings.png)

1. <span data-ttu-id="32c3d-131">选择你的语言和当前时区，然后选择 "确定"。</span><span class="sxs-lookup"><span data-stu-id="32c3d-131">Select your language and current time zone and choose OK.</span></span>

   ![屏幕截图：语言和时区设置](../media/bookings-region-timezone-settings.png)
