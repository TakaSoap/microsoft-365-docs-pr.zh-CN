---
title: 向预订页面添加自定义和必需的问题
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.assetid: fd6b7587-5055-4bcd-83a4-13bd4929bfff
description: 如果你需要在客户在线预订约会时询问客户问题，你可以将自定义问题和必填问题添加到预订页面。
ms.openlocfilehash: d7d997ff02e2a6b8d849cb50014924733bac8e32
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173963"
---
# <a name="add-custom-and-required-questions-to-the-booking-page"></a>向预订页面添加自定义和必需的问题

Bookings 允许你创建问题，以在客户预订约会时询问客户。 它还允许你选择需要哪些问题。

您将问题与服务关联，以便每个服务都可以有一组不同的问题。 例如，发夹风格可能询问预订了发色约会的客户是否具有任何已知的脱字号或淡色。 这允许你和客户在到达约会时节省时间。

客户在预订页面上创建约会时将看到自定义问题。 员工在从 Bookings 日历创建新预订或查看现有约会时将看到自定义问题。 Bookings 会将所有问题保存到主列表中，这样您就不必为每个服务重新创建相同的问题。 还可以选择是必需还是可选问题。

> [!NOTE]
> 在预订日历中查看客户的约会时，可以看到客户的问题的答案。

若要详细了解如何个性化和自定义预订页面，请参阅 [自定义预订页面](customize-booking-page.md)。

## <a name="add-custom-questions-to-your-services"></a>向服务添加自定义问题

1. 登录到 Microsoft 365 然后转到 **Bookings**。

1. 转到"**服务**"，然后编辑现有服务或 **"添加服务"。**

1. 向下滚动到"自定义 **域"** 部分，然后选择"修改 **"。**

   我们添加了一些基本的客户信息问题：客户电子邮件、电话号码、客户地址和客户注释。 第一次这样做时，客户信息问题以灰色突出显示。 这意味着用户将看到此问题。 如果选择该问题，它周围的突出显示框将消失，并且不会询问你的客户该问题。

   此示例中，电话号码和客户注释已关闭，我们创建了两个新的自定义问题来询问。

   ![自定义问题屏幕的图像。](../media/bookings-questions-custom-fields.png)

1. 若要使问题成为必需问题，请选中 **"必需"** 复选框。 在客户回答完所需问题之前，他们将无法完成预订。

1. 若要创建自定义问题，请选择 **面板顶部的** "添加问题"。 编写问题，然后选择"保存 **"。**

1. 单击问题以启用它。 它周围将出现一个突出显示框，并且问题已启用。

1. 单击 **页面** 顶部的"确定"，然后单击"**保存服务"。**

Bookings 将你的所有自定义问题保存在主列表中，以便你可以轻松地将问题添加到每个服务，而无需重复键入相同的问题。 例如，如果打开其他服务，为第一个服务创建的问题会显示在"自定义字段"部分，但将被禁用。 单击该问题，以便突出显示的矩形显示并启用该问题。

此示例中，可以看到为第一个服务添加的问题可用于此服务。 您为此服务创建的任何问题都将可用于所有服务。

   ![针对多个服务显示的问题的图像。](../media/bookings-questions-services.png)

如果预订页面已发布，则无需执行任何其他工作。 客户将在下次预订时看到问题。 如果你的预订页面尚未发布，请从"开始"页面转到Outlook 网页版，然后选择"保存 **并发布"。**

> [!WARNING]
> 您还可以从主列表中删除问题。 但是，如果您删除某个问题，它将从每个服务中删除。 建议您通过选择该问题来禁用该问题，以确保不会影响任何其他服务。 如果问题未被突出显示的矩形包围，则会看到该问题被禁用。

## <a name="customer-experience"></a>客户体验

当你的客户预订约会时，基本客户信息问题会显示在添加 **你的详细信息部分中** 。 您添加的任何自定义问题将位于" **提供其他信息"部分** 。

![启用问题时客户看到的图像。](../media/bookings-questions-customer.png)

## <a name="staff-experience"></a>员工体验

当你的客户预订约会时，你的员工将在预订日历上看到问题和客户的答案。 To see it， go to **Bookings** \> **Calendar** and then open an appointment.

![启用问题时员工看到的图像。](../media/bookings-questions-staff.png)
