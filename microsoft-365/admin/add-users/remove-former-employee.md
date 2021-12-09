---
title: 删除以前的员工 - 概述
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
- m365solution-removeemployee
search.appverid:
- BCS160
- MET150
- MOE150
description: 按照此解决方案中的步骤从员工Microsoft 365并保护组织的数据。
ms.openlocfilehash: 15ef426892bcabe0af71c52f1664255cb82b6637
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61370244"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a>概述：删除以前的员工和安全数据

我们经常收到一个问题："当员工离开我的组织时，我应该如何保护数据和保护访问？" 本系列文章介绍如何阻止访问 Microsoft 365以便这些用户无法登录 Microsoft 365、应执行哪些步骤保护组织数据，以及如何允许其他员工访问电子邮件和 OneDrive 数据。

## <a name="before-you-begin"></a>准备工作

您需要是全局管理员才能完成此解决方案中的步骤。

若要完成本系列中的步骤，请使用这些功能Microsoft 365功能。

|产品或组件|功能或特性|
|---|---|
|Microsoft 365 管理中心|转换邮箱， 转发电子邮件， 撤销访问权限， 删除用户 |
|Exchange 管理中心|阻止用户、阻止访问电子邮件、擦除设备 |
|OneDrive 和 SharePoint |向其他用户授予访问权限 |
|Outlook|导入 pst 文件，添加邮箱 |
|Active Directory|在混合环境中删除用户 |

## <a name="watch-delete-a-user"></a>监视：删除用户

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR?autoplay=false]

当员工离开公司时，你需要将其从企业Microsoft 365中删除。 在执行此操作之前，应阻止他们访问公司文件、保留他们创建的文档，并执行与删除用户相关的其他一些管理任务。

1. 从管理中心，选择"**用户"，** 然后选择"**活动用户"。**
1. 选择要删除的用户，然后选择"删除 **用户"。**
1. 选中此框可删除其许可证，并选中此框可删除其电子邮件别名。
1. 选中此框以向另一个用户授予对前员工的电子邮件的访问权限，然后选择"**选择用户并设置电子邮件选项"。**
1. 若要删除关联的电子邮件别名，请选择 **其别名旁边的"X"。**
1. 查看共享邮箱信息，然后选择"完成 **"。**
1. 确认选项设置正确，然后选择分配 **并转换**。
1. 查看结果，然后选择"关闭 **"。**

删除用户后，您最多有 30 天的时间可以还原其帐户。

## <a name="solution-remove-a-former-employee"></a>解决方案：删除以前的员工

> [!IMPORTANT]
> 尽管我们已对此解决方案中的步骤进行编号，并且不必按确切顺序完成解决方案，但我们建议采用这种方法执行这些步骤。

:::image type="content" source="../../media/delete-user-account.png" alt-text="Screenshot： Steps for removing a former employee from your organization":::

<br>

****

|步骤|为什么执行此操作|
|---|---|
|[步骤 1 - 阻止以前的员工登录并阻止Microsoft 365服务](remove-former-employee-step-1.md)|这会阻止以前的员工登录Microsoft 365并阻止该员工访问Microsoft 365服务。|
|[步骤 2 - 保存以前员工的邮箱的内容](remove-former-employee-step-2.md)|这对将要接管员工工作或者存在诉讼的人很有用。|
|[步骤 3 - 将前员工的电子邮件转发给其他员工或转换为共享邮箱](remove-former-employee-step-3.md)|这可保证前员工的电子邮件地址处于活动状态。如果客户或合作伙伴仍向以前员工的地址发送电子邮件，此功能可让他们发送给接管该工作的员工。|
|[步骤 4 - 向另一名员工授予OneDrive和Outlook权限](remove-former-employee-step-4.md)|如果仅删除用户的许可证但不删除其帐户，则甚至 30 天后仍可访问该用户的 OneDrive 中的内容。 <p> 在删除帐户之前，应该向另一OneDrive授予Outlook访问权限。 删除员工帐户后，其OneDrive Outlook内容将保留 **30** 天。 但是，在这 30 天内，您可以还原用户帐户并访问其内容。 如果还原用户帐户，OneDrive Outlook 30 天后仍可供你访问。|
|[步骤 5 - 擦除和阻止前员工的移动设备](remove-former-employee-step-5.md)|从手机或平板电脑删除业务数据。|
|[步骤 6 - 删除Microsoft 365员工的许可证](remove-former-employee-step-6.md)|移除许可证后，可将许可证分配给其他人。也可删除许可证，以便在聘用其他人员之前，无需为其付费。  <p> 移除或删除许可证时，用户的旧电子邮件、联系人和日历将保留 **30 days** ，然后永久删除。如果删除许可证但不删除其帐户，则在 30 天后仍可以访问该用户的 OneDrive 中的内容。  |
|[步骤 7 - 删除以前员工的用户帐户](remove-former-employee-step-7.md)|这会从管理中心中删除帐户。 进行清除，保持干净。|
|

## <a name="related-content"></a>相关内容

[Restore a user (](restore-user.md) article) \
[向 Microsoft 365 添加新员工](add-new-employee.md)（文章）\
[向用户分配许可证](../manage/assign-licenses-to-users.md)
[取消分配用户许可证 (](../manage/remove-licenses-from-users.md) 文章) 
