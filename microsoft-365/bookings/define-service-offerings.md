---
title: 在 Bookings 中定义服务产品
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: 有关输入服务产品/服务信息的说明，包括服务名称、说明、位置、持续时间和定价。 还可以标记有资格提供服务的员工。
ms.openlocfilehash: 6b276d9ec2d943527f1a6d8ab310fc91406f216c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60151550"
---
# <a name="define-your-service-offerings-in-bookings"></a>在 Bookings 中定义服务产品

在 Microsoft Bookings 中定义服务产品/服务时，可设置服务名称、说明、位置 (选择是希望自己开会还是具有联机会议) 、持续时间、向客户和员工发送的默认提醒、有关服务的内部说明以及定价。 还可以标记有资格提供服务的员工。 然后，当客户到您的业务网站预订约会时，他们可精确查看可用的约会类型、选择要提供服务的人及其服务成本。

您还可以将自定义信息和 URL 添加到你在某人通过你的预订页面预订服务时发送的电子邮件确认和提醒。

## <a name="create-the-service-details"></a>创建服务详细信息

1. In Microsoft 365， select the App launcher， and then select **Bookings**.

2. 转到 **"设置**  ->  [管理服务"页](https://outlook.office.com/bookings/settings/services)，然后选择"**添加新服务"。**

3. 在" **基本详细信息** "页上，添加选择。

   **服务** 名称：输入服务的名称。 这是将显示在"日历"页上的下拉菜单中的名称。 当任何人在日历页面上手动添加约会时，此名称也会显示，并且它将在自助服务页面上显示为磁贴。

   **说明**：输入的说明是当用户单击"自助服务"页面上的信息图标时将显示的内容。

   **默认位置**：此位置将在员工和客户确认和提醒电子邮件中显示，并且将显示在为预订创建的日历事件上。

   **添加联机** 会议：此设置启用或禁用每个约会（通过 Teams 或 Skype）的联机会议，具体取决于您将哪一个配置为员工成员的默认客户端。

   - 已启用：
     - 指向 Teams 或 Skype 会议的链接（对于预订是唯一的）将添加到员工和客户日历上的日历事件，以及拨入信息。
     - 用于加入会议的链接将添加到所有确认和提醒电子邮件中，如以下示例所示：

       :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="在 Bookings 中Teams会议的链接示例。":::

       > [!NOTE]
       > Teams，可以通过 Teams 移动应用、Teams桌面应用、Web 浏览器或电话拨入加入会议。 我们强烈建议将 Teams启用为租户的默认联机会议服务，以获得最佳预订虚拟约会体验。

   - 已禁用：
     - 约会将不包含会议选项，并且启用"添加联机会议"时显示的所有与会议相关的字段将不会显示。

   **Duration**：这是所有会议将预订的时长。 从开始时间（在预订期间选择）开始阻止时间。 将阻止员工日历上的完全约会时间。

   **缓冲区** 时间：启用此设置可允许每次预订约会时向员工日历添加额外时间。

   将在员工的日历上阻止该时间，并影响忙/闲信息。 这意味着，如果约会在下午 3：00 结束，并且会议结束时添加了 10 分钟的缓冲区时间，则员工日历将显示为忙碌且不可预订，直到下午 3：10。 如果员工在会议前需要时间进行准备（例如审阅患者图表的顾问或准备相关帐户信息的财务顾问）可能很有用。 在会议后（例如，当某人需要时间前往另一个位置时）它也可能很有用。

   **未设置价格**：选择将在"价格"页上Self-Service选项。 如果选择 **"未设置** 价格"，将不会显示任何价格或对成本或定价的引用。

   **备注**：此字段显示在预订员工的预订事件以及 Bookings Web 应用中"日历"选项卡上显示的事件中。

   **每个** 事件的最大与会者数 ：此设置允许你创建需要多个人能够预订同一约会时间和相同员工参与的服务 (如健身课程) 。 所选服务的约会时间段、员工和时间将可供预订，直到达到指定的最大与会者数。 可以在 Bookings Web 应用的"日历"选项卡中查看当前约会容量和与会者。

   :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="在 Bookings 中设置最大与会者数的示例":::

   **允许客户管理其** 预订：此设置确定客户是否可以修改或取消其预订，只要预订是通过 Bookings Web 应用上的"日历"选项卡预订的。

   - 已启用：

     客户 **确认** 电子邮件中将显示"管理预订"按钮。 当客户选择此按钮时，将显示三个选项：

     - **重新计划** 选择此选项将用户带到特定于服务的 Self-Service 页面，在此页面中，用户可以从原始预订中选择相同服务和同一员工的新时间和/或日期。 请注意，即使默认情况下原始员工附加到重新安排的预订，用户也具有更改员工成员的选项。
     - **取消预订** 这将取消预订，并从员工日历中删除它。
     - **新预订** 此选项将用户带到已列出Self-Service和员工以安排新预订的"开始"页面。

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="Bookings 中的&quot;管理预订&quot;按钮。":::

      只有在你熟悉客户访问该页面时，才建议Self-Service此设置。

   - 已禁用：

     当用户通过 Bookings Web 应用的"日历"选项卡进行预订时，将不能重新安排或取消预定。 但是，当通过 Self-Service 页面进行预订时，即使禁用此设置，客户仍将拥有"管理预订"按钮及其所有选项。

     如果希望限制对页面页面的访问，建议Self-Service此设置。 此外，我们建议在确认和提醒电子邮件中添加文本，告知客户如何通过其他方式（例如，致电办公室或发送电子邮件到技术支持）更改其预订。

4. 在 **"可用性选项**"页上，你可以看到从"预订"页面为员工计划策略和可用性选择的选项。 有关详细信息，请参阅设置 [日程安排策略](set-scheduling-policies.md)。

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="在 Bookings 中设置最大与会者数的示例。":::

5. **默认价格**  这是将在"价格"页上Self-Service的价格。 如果选择 **"未设置** 价格"，将不会显示任何价格或对成本或定价的引用。

6. **备注** 此字段显示在预订员工的预订事件以及 Bookings Web 应用中"日历"选项卡上显示的事件中。

7. **每次** 预订特定约会时收集所需信息时，自定义字段可能很有用。 示例包括的访问前保险提供商、贷款类型、学院咨询服务的主要研究或候选人面试的候选人 ID。 当您的客户与自己和员工预订约会时，这些字段将显示在"预订"页面上。

   客户电子邮件、电话号码、地址和注释都是不可删除的字段，但您可以通过在每个字段旁边取消选择"必需"来使其可选。 

8. 在 **"提醒和确认"** 页上，可以设置发送的提醒和通知。 提醒和通知在约会前的指定时间发送给客户、员工或两者。 根据你的偏好，可以针对每个约会创建多个邮件。

   :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="来自 Bookings 的确认电子邮件。":::

   你可以在此处添加任何要添加的文本，例如有关日程安排或客户应为约会带来哪些信息。 下面是添加到原始确认电子邮件的自定义文本示例，如"电子邮件确认的其他信息 **"字段** 所示：

   :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Bookings 电子邮件中的其他信息。":::

9. **为客户启用短信通知** 如果选中，SMS 消息将发送给客户，但仅在用户选择加入时发送。

   - 手动预订和预订页面上的"选择加入"Self-Service框中：

     :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="Bookings 中的选择加入框。":::

   - 短信通知将如下所示， (SMS 通知当前仅适用于北美地区) ：

     :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="来自 Bookings 的文本通知。":::

10. 默认 **计划选项** 为打开状态。 若要自定义客户预订特定员工成员方式，请关闭切换。

11. **发布选项** 选择是让此服务显示为可预订Self-Service页上，还是使该服务仅在 Bookings Web 应用程序的"日历"选项卡上可预订。
