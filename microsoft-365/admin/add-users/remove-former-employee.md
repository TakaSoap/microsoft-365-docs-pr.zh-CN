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
localization_priority: Normal
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
search.appverid:
- BCS160
- MET150
- MOE150
description: 按照此解决方案中的步骤从员工Microsoft 365并保护组织的数据。
ms.openlocfilehash: 4b4cf59fdce81b3098ee333095daa8e1af1cd5c5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241732"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a>概述：删除以前的员工和安全数据

我们经常收到一个问题："当员工离开我的组织时，我应该如何保护数据和保护访问？" 本系列文章介绍如何阻止访问Microsoft 365、保护数据应执行的步骤以及如何允许其他员工访问数据。

观看有关删除员工的简短视频。 <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](../../business-video/index.yml)。

防止员工登录：

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
2. 选择用户名旁边的框，然后选择重置 **密码**。
3. 输入新密码，然后选择"重置 **"。**  (不要将其发送给他们。) 
4. 选择要转到其属性窗格的用户名称，在"帐户"选项卡上，选择"**启动注销"。**

> [!NOTE]
> 你需要是全局管理员才能启动注销。

在一小时内（或离开当前Microsoft 365页面后）将提示他们重新登录。 访问令牌适合一小时，因此时间线取决于该令牌所剩的时间，以及他们是否导航到当前网页。

> [!IMPORTANT]
> 尽管我们已对此解决方案中的步骤进行编号，并且不必按确切顺序完成解决方案，但我们建议采用这种方法执行这些步骤。

## <a name="before-you-begin"></a>准备工作

您需要是全局管理员才能完成此解决方案中的步骤。

|||
|:-----|:-----|
|**步骤** <br/> |**为什么执行此操作** <br/> |
|[步骤 1 - 阻止以前的员工登录并阻止对 Microsoft 365 服务的访问](remove-former-employee-step-1.md) <br/> |这会阻止以前的员工登录Microsoft 365并阻止该员工访问Microsoft 365服务。 <br/> |
|[步骤 2 - 保存以前员工的邮箱的内容](remove-former-employee-step-2.md) <br/> |这对将要接管员工工作或者存在诉讼的人很有用。 <br/> |
|[步骤 3 - 将前员工的电子邮件转发给其他员工或转换为共享邮箱](remove-former-employee-step-3.md) <br/> |这可保证前员工的电子邮件地址处于活动状态。如果客户或合作伙伴仍向以前员工的地址发送电子邮件，此功能可让他们发送给接管该工作的员工。 <br/> |
|[步骤 4 - 向另一名员工授予OneDrive和Outlook权限](remove-former-employee-step-6.md) <br/> |如果仅删除用户的许可证但不删除其帐户，则甚至 30 天后仍可访问该用户的 OneDrive 中的内容。 <br/><br/> 在删除帐户之前，应该向其他用户授予OneDrive Outlook访问权限。 删除员工帐户后，其OneDrive Outlook内容将保留 **30** 天。 但是，在这 30 天内，您可以还原用户帐户并访问其内容。 如果还原用户帐户，OneDrive Outlook 30 天后仍可供你访问。 <br/> |
|[步骤 5 - 擦除和阻止前员工的移动设备](remove-former-employee-step-4.md) <br/> |从手机或平板电脑删除业务数据。  <br/> |
|[步骤 6 - 删除Microsoft 365员工的许可证](remove-former-employee-step-7.md) <br/> |移除许可证后，可将许可证分配给其他人。也可删除许可证，以便在聘用其他人员之前，无需为其付费。  <br/><br/> 移除或删除许可证时，用户的旧电子邮件、联系人和日历将保留 **30 days** ，然后永久删除。如果删除许可证但不删除其帐户，则在 30 天后仍可以访问该用户的 OneDrive 中的内容。  <br/> |
|[步骤 7 - 删除以前员工的用户帐户](remove-former-employee-step-7.md) <br/> |这将从管理中心中删除帐户。 进行清除，保持干净。 <br/> |

## <a name="related-articles"></a>相关文章

[还原用户](restore-user.md)
