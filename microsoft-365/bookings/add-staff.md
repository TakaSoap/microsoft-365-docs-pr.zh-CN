---
title: 向 Bookings 添加员工
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
description: 使用此页面可以创建员工列表并管理员工成员详细信息，例如姓名、电话号码和电子邮件地址。
ms.openlocfilehash: ca938acf4bfb567d366c7ffd684e8bce8c9eea74
ms.sourcegitcommit: dd5fc139affb4cba4089cbdb2c478968b680699a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2022
ms.locfileid: "64746782"
---
# <a name="add-staff-to-bookings"></a>向 Bookings 添加员工

> [!NOTE]
> 本文可帮助你与最新版本的Microsoft Bookings交互。 以前的版本将在未来几个月内停用。

Bookings中的“人员”页是创建人员配置列表和管理员工成员详细信息（例如姓名、电话号码和电子邮件地址）的位置。 还可以从此处为每个工作人员设置工作时间。

## <a name="before-you-begin"></a>准备工作

虽然Bookings是Microsoft 365的一项功能，但并非所有员工都必须拥有Microsoft 365帐户。 所有员工必须具有有效的电子邮件地址，以便他们能够接收预订和计划更改。

## <a name="watch-add-your-staff-to-bookings"></a>观看：将员工添加到Bookings

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

## <a name="steps"></a>步骤

1. 从主页中选择日历。 

2. 在左窗格中转到“员工”选项，然后选择 **“添加新员工**”。

3. 从组织内添加员工时，请在 **“添加人员** ”字段中键入其姓名，并在下拉菜单中显示时选择他们。 其他字段将自动填充。

    添加员工后，可以通过选择姓名旁边的 **x** 并编辑 **“添加人员**”字段来编辑所有Bookings通信中显示的名称。 如果希望员工为客户显示特定的标题或名称，例如将 Adele Vance 列为“MD 万斯博士”，则此操作非常有用。

4. 若要从组织外部添加员工，请手动填写其电子邮件和其他信息。

    > [!NOTE]
    > 租户外部的工作人员将无法与Bookings共享忙/闲信息。

5. 对于每个工作人员，选择一个角色：管理员、查看器或来宾。
    - **管理员** 可以编辑所有设置、添加和删除员工，以及创建、编辑或删除预订。
    - **查看者** 可以看到日历上的所有预订，但无法修改或删除这些预订。 它们对设置具有只读访问权限。
    - **可以为来宾** 分配预订，但无法打开预订邮箱。

6. **在创建或更改分配给他们的预订以启用员工电子邮件时，选择通过电子邮件通知所有员工**。 下面是一个示例电子邮件：

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="来自Bookings的通知电子邮件。":::

7. 如果希望员工日历中的闲/忙信息通过Bookings影响预订服务的可用性，则选择Office 365 **日历上的事件会影响可用性**。

    例如，如果一名工作人员在周三下午 3 点安排了团队会议或个人约会，Bookings将显示该工作人员在该时间段内不可预订。 该时间将在Bookings日历视图中显示为忙碌或试探性，如下面的示例所示。

    :::image type="content" source="media/bookings-busy-tentative-view-2.png" alt-text="Bookings日历的视图。":::

> [!IMPORTANT]
> 我们强烈建议将此设置保留 (默认) 启用此设置，以避免双重预订，并优化员工的可用性。

8. 选择 **“使用营业时间** ”，将员工的所有可预订时间设置为仅在“业务信息”页的 **“营业时间** ”部分中设置的营业时间内。

    通过取消选中此框，可以为员工提供可预订的自定义时间，进一步限制时间。 这对于员工可能只在星期二和星期三的网站上，或者将早晨用于一种类型的约会，以及他们的下午用于其他类型的情况很有帮助。

    > [!NOTE]
    > Bookings Bookings日历中最多支持 100 名工作人员。

## <a name="make-a-bookings-user-a-super-user-without-adding-them-as-staff-in-bookings"></a>使Bookings用户成为超级用户，而无需在Bookings中将其添加为“工作人员”

你可能希望在Bookings中将人员添加到员工列表，而不向客户或客户提供。 一旦你使他们成为超级用户，他们将成为预订邮箱的管理员。 作为预订邮箱的管理员定义为具有对预订邮箱的完全访问权限和发送方式权限。

> [!NOTE]
> 仅当添加的用户尚未在Bookings中分配 **查看器** 角色时，这些步骤才有效。

1. [连接使用 PowerShell Microsoft 365](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

2. 使用 PowerShell，使用以下命令分配完全访问权限：

    ```powershell
    Add-MailboxPermission -Identity <bookingmailbox@emailaddress> -User <adminusers@emailaddress> -AccessRights FullAccess -Deny:$false
    ```

3. 然后运行此命令以分配发送方式权限。

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

下面是一个示例 PowerShell 命令，用于将 Allie Bellew 添加到 Contoso 日托预订邮箱。

1. 首先运行以下命令：

    ```powershell
    Add-MailboxPermission -Identity "daycare@contoso.com" -User "Allie Bellew" -AccessRights FullAccess -InheritanceType All
    ```

2. 然后运行以下命令：

    ```powershell
    Add-RecipientPermission -Identity "daycare@contoso.com" -Trustee "Allie Bellew" -AccessRights SendAs -Confirm:$false
    ```

**Allie Bellew** 现在具有管理员访问权限，但在 Bookings 中不显示为可预订的员工。
