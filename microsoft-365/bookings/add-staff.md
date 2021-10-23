---
title: 向 Bookings 添加员工
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
description: 使用此页面创建员工列表并管理员工详细信息，例如姓名、电话号码和电子邮件地址。
ms.openlocfilehash: b76b3e647af6f43f1c8ad7364fe24c895dc86b45
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2021
ms.locfileid: "60553972"
---
# <a name="add-staff-to-bookings"></a>向 Bookings 添加员工

Bookings 中的"员工"页面是创建员工列表和管理员工详细信息（如姓名、电话号码和电子邮件地址）的地方。 您还可以在此处为每位员工设置工作时间。

## <a name="before-you-begin"></a>准备工作

尽管 Bookings 是一项Microsoft 365功能，但并非所有员工成员都需要拥有Microsoft 365帐户。 所有员工都必须具有有效的电子邮件地址，以便他们可以接收预订和计划更改。

## <a name="watch-add-your-staff-to-bookings"></a>观看：将员工添加到 Bookings

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

## <a name="steps"></a>步骤

> [!NOTE]
> 这些步骤在全新 Bookings 体验中尚不可用。

1. 转到" [管理人员"页面，](https://outlook.office.com/bookings/staff) 然后选择" **添加员工"**

2. 选择" **添加员工"** 按钮。

3. 从组织内部添加员工时，在"添加人员"字段中键入其姓名，在人员显示在下拉菜单中时选择他们。 其他字段将自动填充。

    添加员工后，可以通过选择员工姓名旁边的 **x** 并编辑"添加人员"字段来编辑显示在所有 Bookings 通信 **上的名称。** 如果您希望员工能够为客户显示特定标题或名称（例如将 Adele Vance 列出为"Dr. Vance， MD"，这将非常有用。

4. 若要从组织外部添加员工，请手动填写他们的电子邮件和其他信息。

    > [!NOTE]
    > 来自租户外部的员工将无法与 Bookings 共享忙/闲信息。

5. 对于每个员工成员，选择一个角色：管理员、查看者或来宾。
    - **管理员可以编辑** 所有设置、添加和删除员工以及创建、编辑或删除预订。
    - **查看** 者可以在日历上查看所有预订，但无法修改或删除它们。 他们具有对设置的只读访问权限。
    - **可以将** 来宾分配给预订，但他们无法打开预订邮箱。

6. 选择 **"创建或更改分配给** 员工的预订时通过电子邮件通知所有员工"以启用员工电子邮件。 下面是一个示例电子邮件：

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="来自 Bookings 的通知电子邮件。":::

7. 如果希望 **Office 365员工日历中的忙**/闲信息通过 Bookings 影响预订服务的可用性，请选择"日历上的事件影响可用性"。

    例如，如果员工有安排在星期三下午 3 点召开团队会议或个人约会，则 Bookings 将显示该员工无法在这一时间段预订。 该时间将在 Bookings 日历视图中显示为忙碌或暂定，如以下示例所示。

    :::image type="content" source="media/bookings-busy-tentative-view.jpg" alt-text="Bookings 日历的视图。":::

> [!IMPORTANT]
> 我们强烈建议将此设置保留为 (默认情况下启用此设置) 以避免双重预订并优化员工成员的可用性。

8. 选择 **"使用营业时间**"将员工的所有可预订时间设置为仅在"业务信息"页上的"营业时间"部分中设置的营业时间内。

    通过取消选中此框，可以给员工提供自定义小时数，以进一步限制可以预订的时间。 这适用于以下情形：员工可能只能在星期二和星期三开会，或者将上午专用于一种类型的约会，以及安排其他类型的约会。

    > [!NOTE]
    > 在向服务分配员工时，只会显示添加到员工页面的前 31 名员工。

## <a name="make-a-bookings-user-a-super-user-without-adding-them-as-staff-in-bookings"></a>使 Bookings 用户成为超级用户，而不将用户添加为 Bookings 中的 Staff

你可能想要在 Bookings 中将人员添加到员工列表中，而不向客户或客户提供此人。 一旦使他们成为超级用户，他们将成为预订邮箱的管理员。 作为预订邮箱管理员的定义是拥有对预订邮箱的完全访问权限和发送权限。

> [!NOTE]
> 这些步骤仅在所添加的用户尚未在 Bookings 中 **分配查看者** 角色时运行。

1. [连接 PowerShell Microsoft 365。](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

2. 使用 PowerShell，通过以下命令分配完全访问权限：

    ```powershell
    Add-MailboxPermission -Identity <bookingmailbox@emailaddress> -User <adminusers@emailaddress> -AccessRights FullAccess -Deny:$false
    ```

3. 然后运行此命令以分配发送为权限。

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

下面是一个将 Allie Bellew 添加到 Contoso 医疗保健预订邮箱的示例 PowerShell 命令。

1. 首先运行此命令：

    ```powershell
    Add-MailboxPermission -Identity "daycare@contoso.com" -User "Allie Bellew" -AccessRights FullAccess -InheritanceType All
    ```

2. 然后运行此命令：

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

**Allie Bellew** 现在具有管理员访问权限，但在 Bookings 中不会显示为可预订员工。
