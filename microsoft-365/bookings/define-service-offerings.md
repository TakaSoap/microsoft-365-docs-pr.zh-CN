---
title: 在 Bookings 中定义服务产品
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: 有关输入服务产品/服务信息的说明，包括服务名称、说明、位置、持续时间和定价。 还可以标记有资格提供服务的员工。
ms.openlocfilehash: 095188546c01149a793a478a3cbd5ac9fbeb5524
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962533"
---
# <a name="define-your-service-offerings-in-bookings"></a><span data-ttu-id="348d5-104">在 Bookings 中定义服务产品</span><span class="sxs-lookup"><span data-stu-id="348d5-104">Define your service offerings in Bookings</span></span>

<span data-ttu-id="348d5-105">在 Microsoft Bookings 中定义服务产品/服务时，你可以设置服务名称、说明、位置 (选择是希望自己开会还是参加联机会议) 、持续时间、向客户和员工发送的默认提醒、有关服务的内部说明以及定价。</span><span class="sxs-lookup"><span data-stu-id="348d5-105">When you define your service offerings in Microsoft Bookings, you set, a service name, description, location (choose whether you want to meet in person or have an online meeting), duration, default reminders to customers and staff, internal notes about the service, and pricing.</span></span> <span data-ttu-id="348d5-106">还可以标记有资格提供服务的员工。</span><span class="sxs-lookup"><span data-stu-id="348d5-106">You can also tag the employees who are qualified to provide the service.</span></span> <span data-ttu-id="348d5-107">然后，当客户到您的业务网站预订约会时，他们可以看到确切可用的约会类型、选择要提供服务的人及其服务成本。</span><span class="sxs-lookup"><span data-stu-id="348d5-107">Then, when customers come to your business web site to book an appointment, they can see exactly what types of appointments are available, choose the person they want to provide the service, and how much their service will cost.</span></span>

<span data-ttu-id="348d5-108">您还可以将自定义信息和 URL 添加到你在某人通过你的预订页面预订服务时发送的电子邮件确认和提醒。</span><span class="sxs-lookup"><span data-stu-id="348d5-108">You can also add customized information and URLs to the email confirmation and reminders that you send when someone books a service through your booking page.</span></span>

## <a name="create-the-service-details"></a><span data-ttu-id="348d5-109">创建服务详细信息</span><span class="sxs-lookup"><span data-stu-id="348d5-109">Create the service details</span></span>

1. <span data-ttu-id="348d5-110">转到"[管理服务"页，](https://outlook.office.com/bookings/services)然后选择"**添加服务"。**</span><span class="sxs-lookup"><span data-stu-id="348d5-110">Go to the [Manage services page](https://outlook.office.com/bookings/services) and select **Add a service**.</span></span>

2. <span data-ttu-id="348d5-111">**服务** 名称：输入服务的名称。</span><span class="sxs-lookup"><span data-stu-id="348d5-111">**Service name**: enter the name of your service.</span></span> <span data-ttu-id="348d5-112">这是将在"日历"页上的下拉菜单中显示的名称。</span><span class="sxs-lookup"><span data-stu-id="348d5-112">This is the name that will appear in the drop-down menu on the Calendar page.</span></span> <span data-ttu-id="348d5-113">当任何人在日历页面上手动添加约会时，此名称也会显示，并且它将在自助服务页面上显示为磁贴。</span><span class="sxs-lookup"><span data-stu-id="348d5-113">This name will also appear when anyone manually adds an appointment on the Calendar page, and it will appear as a tile on the Self-service page.</span></span>

3. <span data-ttu-id="348d5-114">**说明**：输入的说明是当用户单击"自助服务"页面上的信息图标时将显示的内容。</span><span class="sxs-lookup"><span data-stu-id="348d5-114">**Description**: The description you enter is what will appear when a user clicks the information icon on the Self-service page.</span></span>

4. <span data-ttu-id="348d5-115">**默认位置**：此位置将在员工和客户确认和提醒电子邮件中显示，并且将显示在为预订创建的日历事件上。</span><span class="sxs-lookup"><span data-stu-id="348d5-115">**Default location**: This location is what will be displayed on confirmation and reminder emails for both staff and customers, and it will be displayed on the calendar event created for the booking.</span></span>

5. <span data-ttu-id="348d5-116">**添加联机** 会议：此设置启用或禁用每个约会（通过 Teams 或 Skype）的联机会议，具体取决于您将哪一个配置为员工成员的默认客户端。</span><span class="sxs-lookup"><span data-stu-id="348d5-116">**Add online meeting**: This setting enables or disables online meetings for each appointment, either via Teams or Skype, depending on which one you configure as the default client for the staff member.</span></span>

    - <span data-ttu-id="348d5-117">已启用：</span><span class="sxs-lookup"><span data-stu-id="348d5-117">Enabled:</span></span>

        - <span data-ttu-id="348d5-118">指向会议Teams或 Skype 会议的链接（对于预订是唯一的）将添加到员工和客户日历上的日历事件，以及拨入信息。</span><span class="sxs-lookup"><span data-stu-id="348d5-118">A link to a Teams or Skype meeting, unique to the booking, will be added to the calendar event on both the staff's and the customers' calendars, along with dial-in information.</span></span>
        - <span data-ttu-id="348d5-119">用于加入会议的链接将添加到所有确认和提醒电子邮件中，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="348d5-119">The link to join the meeting will be added to all confirmation and reminder emails, as shown in the following example:</span></span>

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="在 Bookings 中Teams会议的链接示例":::

        > [!NOTE]
        > <span data-ttu-id="348d5-121">Teams，可以通过 Teams 移动应用、桌面Teams、Web 浏览器或电话拨入加入会议。</span><span class="sxs-lookup"><span data-stu-id="348d5-121">Teams meetings can be joined via the Teams mobile app, the Teams desktop app, in a Web browser, or via the phone dial-in.</span></span> <span data-ttu-id="348d5-122">我们强烈建议将 Teams启用为租户的默认联机会议服务，以获得最佳预订虚拟约会体验。</span><span class="sxs-lookup"><span data-stu-id="348d5-122">We strongly recommend enabling Teams as the default online meeting service for your tenant, for the best experience booking virtual appointments.</span></span>

    - <span data-ttu-id="348d5-123">已禁用：</span><span class="sxs-lookup"><span data-stu-id="348d5-123">Disabled:</span></span>
        - <span data-ttu-id="348d5-124">约会将不包含会议选项，并且启用"添加联机会议"时显示的所有与会议相关的字段将不会显示。</span><span class="sxs-lookup"><span data-stu-id="348d5-124">Appointments will not contain a meeting option, and all of the meeting-related fields that appear when **Add online meeting** is enabled will not be shown.</span></span>

6. <span data-ttu-id="348d5-125">**默认持续时间**：这是所有会议的预定时间。</span><span class="sxs-lookup"><span data-stu-id="348d5-125">**Default duration**: This is how long all meetings will be booked for.</span></span> <span data-ttu-id="348d5-126">从开始时间（在预订期间选择）开始阻止时间。</span><span class="sxs-lookup"><span data-stu-id="348d5-126">The time is blocked beginning from the start time, which is selected during booking.</span></span> <span data-ttu-id="348d5-127">将阻止员工日历上的完全约会时间。</span><span class="sxs-lookup"><span data-stu-id="348d5-127">The full appointment time will be blocked on the staff's calendars.</span></span>

7. <span data-ttu-id="348d5-128">**客户无法预订的** 缓冲时间：启用此设置后，每次预订约会时，都会向员工日历添加额外时间。</span><span class="sxs-lookup"><span data-stu-id="348d5-128">**Buffer time your customer can’t book**: Enabling this setting allows for the addition of extra time to the staff’s calendar every time an appointment is booked.</span></span>

    <span data-ttu-id="348d5-129">将在员工的日历上阻止该时间，并影响忙/闲信息。</span><span class="sxs-lookup"><span data-stu-id="348d5-129">The time will be blocked on the staff’s calendar and impact free/busy information.</span></span> <span data-ttu-id="348d5-130">这意味着，如果约会在下午 3：00 结束，并且会议结束时添加了 10 分钟的缓冲区时间，则员工日历将显示为忙碌且不可预订，直到下午 3：10。</span><span class="sxs-lookup"><span data-stu-id="348d5-130">This means if an appointment ends at 3:00 pm and 10 minutes of buffer time has been added to the end of the meeting, the staff’s calendar will show as busy and non-bookable until 3:10pm.</span></span> <span data-ttu-id="348d5-131">如果员工在会议前需要时间进行准备（例如审阅患者图表的顾问或准备相关帐户信息的财务顾问）可能很有用。</span><span class="sxs-lookup"><span data-stu-id="348d5-131">This can be useful if your staff needs time before a meeting to prepare, such as a doctor reviewing a patient’s chart, or a financial advisor preparing relevant account information.</span></span> <span data-ttu-id="348d5-132">在会议后（例如，当某人需要时间前往另一个位置时）它也可能很有用。</span><span class="sxs-lookup"><span data-stu-id="348d5-132">It can also be useful after a meeting, such as when someone needs time to travel to another location.</span></span>

8. <span data-ttu-id="348d5-133">**允许客户管理其** 预订：此设置确定客户是否可以修改或取消其预订（如果预订是通过 Bookings Web 应用上的"日历"选项卡预订的）。</span><span class="sxs-lookup"><span data-stu-id="348d5-133">**Let the customer manage their booking**: This setting determines whether or notthe customer can modify or cancel their booking, provided it was booked through the Calendar tab on the Bookings Web app.</span></span>

    - <span data-ttu-id="348d5-134">已启用：</span><span class="sxs-lookup"><span data-stu-id="348d5-134">Enabled:</span></span>

        <span data-ttu-id="348d5-135">客户 **确认** 电子邮件中将显示"管理预订"按钮。</span><span class="sxs-lookup"><span data-stu-id="348d5-135">The **Manage Booking** button appears on the customer confirmation email.</span></span> <span data-ttu-id="348d5-136">当客户选择此按钮时，将显示三个选项：</span><span class="sxs-lookup"><span data-stu-id="348d5-136">When this button is selected by the customer, three options appear:</span></span>
        - <span data-ttu-id="348d5-137">**重新计划** 选择此选项将用户带到特定于服务的 Self-Service 页面，在此页面中，用户可以从原始预订中选择相同服务和相同员工的新时间和/或日期。</span><span class="sxs-lookup"><span data-stu-id="348d5-137">**Reschedule** Selecting this option brings the user to a service-specific Self-Service page, where they can select a new time and/or date for the same service and same staff member from the original booking.</span></span> <span data-ttu-id="348d5-138">请注意，即使默认情况下原始员工附加到重新安排的预订，用户也具有更改员工成员的选项。</span><span class="sxs-lookup"><span data-stu-id="348d5-138">Note that even though the original staff member is attached to the rescheduled booking by default, the user does have the option of changing the staff member as well.</span></span>
        - <span data-ttu-id="348d5-139">**取消预订** 这将取消预订，并从员工日历中删除它。</span><span class="sxs-lookup"><span data-stu-id="348d5-139">**Cancel booking** This cancels the booking and removes it from the staff's calendar.</span></span>
        - <span data-ttu-id="348d5-140">**新预订** 此选项将用户带到"Self-Service"页面，并列出所有服务和员工，以计划新的预订。</span><span class="sxs-lookup"><span data-stu-id="348d5-140">**New booking** This option brings the user to the Self-Service page with all services and staff listed, for scheduling a new booking.</span></span>

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="Bookings 中的&quot;管理预订&quot;按钮":::

        <span data-ttu-id="348d5-142">只有在你熟悉客户访问该页面时，才建议Self-Service此设置。</span><span class="sxs-lookup"><span data-stu-id="348d5-142">We only recommend leaving this setting enabled if you are comfortable with customers accessing the Self-Service page.</span></span>

    - <span data-ttu-id="348d5-143">已禁用：</span><span class="sxs-lookup"><span data-stu-id="348d5-143">Disabled:</span></span>

        <span data-ttu-id="348d5-144">当用户通过 Bookings Web 应用的"日历"选项卡进行预订时，将不能重新安排或取消预定。</span><span class="sxs-lookup"><span data-stu-id="348d5-144">The user will have no ability to reschedule or cancel their booking when they book through the Calendar tab on the Bookings Web app.</span></span> <span data-ttu-id="348d5-145">但是，当通过 Self-Service 页面进行预订时，即使禁用此设置，客户仍将拥有"管理预订"按钮及其所有选项。</span><span class="sxs-lookup"><span data-stu-id="348d5-145">When booking through the Self-Service page, however, customers will still have the **Manage Booking** button and all of its options, even when this setting is disabled.</span></span>

        <span data-ttu-id="348d5-146">如果希望限制对页面页面的访问，建议Self-Service此设置。</span><span class="sxs-lookup"><span data-stu-id="348d5-146">We recommend disabling this setting if you want to limit access to the Self-Service page.</span></span> <span data-ttu-id="348d5-147">此外，我们建议将文本添加到你的确认和提醒电子邮件中，告知客户如何通过其他方式更改其预订，例如通过致电办公室或通过电子邮件发送技术支持。</span><span class="sxs-lookup"><span data-stu-id="348d5-147">Additionally, we suggest adding text to your confirmation and reminder emails that tells your customers how to make changes to their booking through other means, such as by calling the office or emailing the help desk.</span></span>

9. <span data-ttu-id="348d5-148">**每个事件的最大参与者数** 此设置允许你创建需要多个人能够预订同一约会时间和相同员工预约的服务 (如健身课程) 。</span><span class="sxs-lookup"><span data-stu-id="348d5-148">**Maximum attendees per event** This setting allows you to create services that require the ability for multiple people to book the same appointment time and the same staff (such as a fitness class).</span></span> <span data-ttu-id="348d5-149">所选服务的约会时间段、员工和时间将可供预订，直到达到指定的最大与会者数。</span><span class="sxs-lookup"><span data-stu-id="348d5-149">The appointment time slot for the selected service, staff, and time will be available to book until the maximum number of attendees, specified by you, has been reached.</span></span> <span data-ttu-id="348d5-150">可以在 Bookings Web 应用的"日历"选项卡中查看当前约会容量和与会者。</span><span class="sxs-lookup"><span data-stu-id="348d5-150">Current appointment capacity and attendees can be viewed in the Calendar tab in the Bookings Web app.</span></span>

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="在 Bookings 中设置最大与会者数的示例":::

10. <span data-ttu-id="348d5-152">**默认价格**  这是将在"价格"页上Self-Service的价格。</span><span class="sxs-lookup"><span data-stu-id="348d5-152">**Default price**  This is the price that will display on the Self-Service page.</span></span> <span data-ttu-id="348d5-153">如果选择 **"未设置** 价格"，将不会显示任何价格或对成本或定价的引用。</span><span class="sxs-lookup"><span data-stu-id="348d5-153">If **Price not set** is selected, then no price or reference to cost or pricing will appear.</span></span>

11. <span data-ttu-id="348d5-154">**备注** 此字段显示在预订员工的预订事件以及 Bookings Web 应用中"日历"选项卡上显示的事件中。</span><span class="sxs-lookup"><span data-stu-id="348d5-154">**Notes** This field appears in the booking event for booked staff, as well as on the event that appears on the Calendar tab in the Bookings web app.</span></span>

12. <span data-ttu-id="348d5-155">**自定义域** 如果客户需要回答任何问题才能成功预订，此部分允许添加或删除问题。</span><span class="sxs-lookup"><span data-stu-id="348d5-155">**Custom Fields** This section allows questions to be added, or removed, if the customer needs to answer any in order to successfully book.</span></span>

    - <span data-ttu-id="348d5-156">客户电子邮件、电话号码、地址和注释都是不可删除的字段，但您可以通过在每个字段旁边取消选择"必需"来使其可选。 </span><span class="sxs-lookup"><span data-stu-id="348d5-156">Customer email, phone number, address, and notes are non-removable fields, but you can make them optional by deselecting **Required** beside each field.</span></span>

    - <span data-ttu-id="348d5-157">通过选择"添加问题"，可以添加多个选择或文本 **响应问题**。</span><span class="sxs-lookup"><span data-stu-id="348d5-157">You can add a multiple choice or text-response question by selecting **Add a question**.</span></span>

        <span data-ttu-id="348d5-158">每次预订特定约会时收集所需信息时，自定义字段可能很有用。</span><span class="sxs-lookup"><span data-stu-id="348d5-158">Custom fields can be useful when collecting information that is needed every time the specific appointment is booked.</span></span> <span data-ttu-id="348d5-159">示例包括的访问前保险提供商、贷款类型、学院咨询服务的主要研究或候选人面试的候选人 ID。</span><span class="sxs-lookup"><span data-stu-id="348d5-159">Examples include insurance provider prior to a clinic visit, loan type for loan consultations, major of study for academic advising, or applicant ID for candidate interviews.</span></span>

13. <span data-ttu-id="348d5-160">**提醒和确认** 这两种类型的电子邮件在约会前的指定时段发送给客户、员工或两者。</span><span class="sxs-lookup"><span data-stu-id="348d5-160">**Reminders and Confirmations** Both types of emails are sent out to customers, staff members, or both, at a specified time period before the appointment.</span></span> <span data-ttu-id="348d5-161">根据你的偏好，可以针对每个约会创建多个邮件。</span><span class="sxs-lookup"><span data-stu-id="348d5-161">Multiple messages can be created for each appointment, according to your preference.</span></span>

    - <span data-ttu-id="348d5-162">默认确认和提醒电子邮件包括有关约会的基本信息，例如客户/客户名称、员工姓名、已预订的服务或约会以及约会的时间。</span><span class="sxs-lookup"><span data-stu-id="348d5-162">The default confirmation and reminder emails include basic information about the appointment, such as the customer/client name, staff member's name, the service or appointment booked, and the time of the appointment.</span></span> <span data-ttu-id="348d5-163">对于联机会议，还将包含加入链接。</span><span class="sxs-lookup"><span data-stu-id="348d5-163">For online meetings, a link to join will also be included.</span></span> <span data-ttu-id="348d5-164">如果启用此设置，还可以包括管理预订 (如步骤 8 中所述) 。</span><span class="sxs-lookup"><span data-stu-id="348d5-164">The ability to manage the booking can also be included, if this setting is enabled (as described above in step 8).</span></span>

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="来自 Bookings 的确认电子邮件":::

    - <span data-ttu-id="348d5-166">（可选）你可以在此处添加任何要添加的文本，例如有关日程安排或客户应为约会带来哪些信息。</span><span class="sxs-lookup"><span data-stu-id="348d5-166">Optionally, you can include any additional text you would like here, such as information about rescheduling or what customers should bring for the appointment.</span></span> <span data-ttu-id="348d5-167">下面是添加到原始确认电子邮件的自定义文本示例，如"电子邮件确认的其他信息" **字段** 所示：</span><span class="sxs-lookup"><span data-stu-id="348d5-167">The following is an example of customized text added to the original confirmation email, seen in the **Additional information for Email Confirmation** field:</span></span>

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Bookings 电子邮件中的附加信息":::

14. <span data-ttu-id="348d5-169">**为客户启用短信通知** 如果选中短信，则只会在用户选择加入时，才将邮件发送给客户。</span><span class="sxs-lookup"><span data-stu-id="348d5-169">**Enable text message notifications for your customer** If selected, SMS messages are sent to the customer, but only if they opt-in.</span></span>

    - <span data-ttu-id="348d5-170">手动预订和预订页面上的"选择加入Self-Service框：</span><span class="sxs-lookup"><span data-stu-id="348d5-170">Opt-in box on the manual booking and Self-Service Page:</span></span>

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="Bookings 中的选择加入框":::

    - <span data-ttu-id="348d5-172">短信通知将如下所示， (请注意短信目前仅在北美地区提供) ：</span><span class="sxs-lookup"><span data-stu-id="348d5-172">Text message notifications will look like the following (note that SMS notifications are currently only available in North America):</span></span>

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="来自 Bookings 的文本通知":::

15. <span data-ttu-id="348d5-174">**发布选项** 选择是让此服务显示为可预订Self-Service页上，还是使该服务仅在 Bookings Web 应用程序的"日历"选项卡上可预订。</span><span class="sxs-lookup"><span data-stu-id="348d5-174">**Publishing options** Choose whether to have this service appear as bookable on the Self-Service page, or to make the service bookable only on the Calendar tab within the Bookings Web app.</span></span>

16. <span data-ttu-id="348d5-175">**计划策略** 此设置确定如何查看约会时间，以及可以预订或取消的时间段。</span><span class="sxs-lookup"><span data-stu-id="348d5-175">**Scheduling Policy** This setting determines how appointment times are viewed, and the time period in which bookings can be made or cancelled.</span></span>

17. <span data-ttu-id="348d5-176">**电子邮件通知** 设置电子邮件何时发送给组织员工以及客户或客户。</span><span class="sxs-lookup"><span data-stu-id="348d5-176">**Email notifications** Sets when emails are sent to organization staff and to customers or clients.</span></span>

18. <span data-ttu-id="348d5-177">**员工** 选中此复选框，客户或客户可以选择特定的员工进行约会。</span><span class="sxs-lookup"><span data-stu-id="348d5-177">**Staff** Selecting this checkbox allows customers or clients to choose a specific staff member for their appointment.</span></span>

    - <span data-ttu-id="348d5-178">已启用：</span><span class="sxs-lookup"><span data-stu-id="348d5-178">Enabled:</span></span>

        <span data-ttu-id="348d5-179">客户在"约会"页面上进行预订时，可以从分配给约会的所有Self-Service选择。</span><span class="sxs-lookup"><span data-stu-id="348d5-179">Customers can choose from all staff assigned to the appointment when booking on the Self-Service page.</span></span> <span data-ttu-id="348d5-180">选择"任何人 **"** 选项将允许 Bookings 随机选择一个可用的员工，以分配给该约会。</span><span class="sxs-lookup"><span data-stu-id="348d5-180">Selecting the option of **Anyone** will make Bookings choose an available staff member at random to assign to the appointment.</span></span>

    - <span data-ttu-id="348d5-181">已禁用：</span><span class="sxs-lookup"><span data-stu-id="348d5-181">Disabled:</span></span>

        <span data-ttu-id="348d5-182">客户通过"Self-Service"页面预订可以选择服务和时间和日期。</span><span class="sxs-lookup"><span data-stu-id="348d5-182">Customers booking via the Self-Service page can select a service and a time and date.</span></span> <span data-ttu-id="348d5-183">将随机预订可用员工。</span><span class="sxs-lookup"><span data-stu-id="348d5-183">The available staff will be booked at random.</span></span> <span data-ttu-id="348d5-184">请注意，通过 Bookings Web 应用中的"日历"选项卡预订时，仍可选择特定员工。</span><span class="sxs-lookup"><span data-stu-id="348d5-184">Note that specific staff can still be selected when booked through the Calendar tab in the Bookings Web app.</span></span>

19. <span data-ttu-id="348d5-185">**可用性** 以下选项确定何时可以预订服务：</span><span class="sxs-lookup"><span data-stu-id="348d5-185">**Availability** The following options determine when the service can be booked:</span></span>

    - <span data-ttu-id="348d5-186">**员工空闲时可预订** 该服务根据员工在工作时间内空闲的时间保持可用性，没有额外的时间限制。</span><span class="sxs-lookup"><span data-stu-id="348d5-186">**Bookable when staff are free** The service maintains availability based on when staff are free within business hours, with no extra time restrictions.</span></span>

    - <span data-ttu-id="348d5-187">**每周 (自定义小时数)** 该服务具有一个额外的可用性层，除了 (工作时间或员工工作时间限制外，还可以进一步限制) 。</span><span class="sxs-lookup"><span data-stu-id="348d5-187">**Custom hours (recurring weekly)** The service has an added layer of availability that can be further restricted (in addition to restricting by business hours or with staff hours).</span></span> <span data-ttu-id="348d5-188">如果只能在特定时间提供或执行服务，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="348d5-188">Use this option when your service can only be provided or performed at a specific time.</span></span>

    - <span data-ttu-id="348d5-189">**为日期范围设置不同的可用性** 此设置会影响特定时间点的可用性，而不是定期影响可用性。</span><span class="sxs-lookup"><span data-stu-id="348d5-189">**Set different availability for a date range** This setting impacts availability at a specific point in time, instead of a recurring basis.</span></span> <span data-ttu-id="348d5-190">例如，当服务所需的计算机暂时提供服务和不可用时，或者组织因假日而关闭时，就可以使用此功能。</span><span class="sxs-lookup"><span data-stu-id="348d5-190">For example, this could be used when a machine that is needed for the service is temporarily being serviced and unavailable, or when an organization is closed for a holiday.</span></span>

20. <span data-ttu-id="348d5-191">**分配员工** 选择员工 (，只要你已将员工添加到"员工"选项卡) 该特定服务可预订的人员。</span><span class="sxs-lookup"><span data-stu-id="348d5-191">**Assign Staff** Select the staff (provided you have added staff members to the Staff tab) who will be bookable for that specific service.</span></span> <span data-ttu-id="348d5-192">选择任何单个员工将导致所有员工都分配到该服务。</span><span class="sxs-lookup"><span data-stu-id="348d5-192">Selecting no individual staff will result in all staff being assigned to the service.</span></span>