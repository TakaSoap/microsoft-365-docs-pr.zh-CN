---
title: 将员工添加到预订
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 298c529b-407b-4a2b-b2c5-6e77a9d1f07f
description: 使用此页面可创建你的教职员工列表，并管理教职员工成员的详细信息，如姓名、电话号码和电子邮件地址。
ms.openlocfilehash: cfd42eedb6e0bea08cdee1503fc373167996c75b
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419345"
---
# <a name="add-staff-to-bookings"></a>将员工添加到预订

预订中的 "员工" 页面是创建人员名单和管理员工成员详细信息（如姓名、电话号码和电子邮件地址）的地方。 您还可以在此处为每个教职员工成员设置工作时间。

> [!NOTE]
> 默认情况下，对于拥有 Microsoft 365 商业标准、Microsoft 365 A3 或 Microsoft 365 A5 订阅的客户，预订处于启用状态。 预订也适用于拥有 Office 365 企业版 E3 和 Office 365 企业版 E5 的客户，但默认情况下它处于关闭状态。 若要开始，请参阅 [获取 Microsoft 预订的访问权限](get-access.md)。 若要打开或关闭预订，请参阅 [开启或关闭组织的预订](turn-bookings-on-or-off.md)。

## <a name="add-staff"></a>添加员工

虽然预订是 Microsoft 365 的一项功能，但并不是所有的教职员工成员都需要拥有 Microsoft 365 帐户。 所有教职员工成员都必须具有有效的电子邮件地址，以便他们可以接收预订和日程安排更改。

观看此视频或按照以下步骤添加你的员工。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

1. 转到 "[管理员工" 页面](https://outlook.office.com/bookings/staff)并选择 "**添加教职员工**"

2. 选择 " **添加教职员工** " 按钮。

3. 在租户中添加员工时，请在 " **添加人员** " 字段中键入他们的姓名，并在它们出现在下拉菜单中时选择它们。 其他字段将自动填充。

    添加教职员工成员后，可以通过选择其名称旁边的 **x** 并编辑 " **添加人员** " 字段，来编辑在所有预订通信中显示的名称。 如果您希望教职员工成员为客户显示特定标题或名称（例如，将 Adele Vance 为 "Vance，MD"），这会非常有用。

4. 若要添加来自租户外部的员工，请手动填写其电子邮件和其他信息。

    > [!NOTE]
    > 你租户外部的员工将无法与预订共享忙/闲信息。

5. 对于每个教职员工成员，选择一个角色：管理员、查看者或来宾。
    - **管理员** 可以编辑所有设置、添加和删除员工以及创建、编辑或删除预订。
    - **查看者** 可以查看日历上的所有预订，但不能修改或删除它们。 它们具有对设置的只读访问权限。
    - 可以将**来宾**分配给预订，但不能打开预订邮箱。

6. **如果创建或更改了分配给他们的预订**以启用员工电子邮件，则选择 "通过电子邮件通知所有人员"。 以下是电子邮件示例：

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="来自预定的通知电子邮件":::

7. 选择 " **Office 365 日历上的事件** "。如果您希望员工的日历中的忙/闲信息通过预订影响预定服务的可用性，则会影响可用性。

    例如，如果某个教职员工成员在星期三为3pm 安排了团队会议或个人约会，则预订将向该员工显示 "无法在该时间段内预订的成员"。 该时间将在 "预定日历" 视图中显示为 "忙碌" 或 "暂定"，如以下示例所示。

    :::image type="content" source="media/bookings-busy-tentative-view.jpg" alt-text="预订日历的视图":::

> [!IMPORTANT]
> 强烈建议将此设置保留在 (默认情况下启用此设置) 以避免进行双重预订并优化教职员工成员的可用性。

8. 选择 " **使用营业时间** " 可将教职员工成员的所有 bookable 时间设置为仅在 "业务信息" 页上的 " **营业时间** " 部分中设置的工作时间内。

    通过取消选中此框，可以向员工提供自定义时间，以便在可以预订时进一步限制。 如果教职员工成员只能在网站星期二和星期三，或者为其他类型的一种类型的约会和他们的 afternoons 专门提供上午，这将非常有用。
