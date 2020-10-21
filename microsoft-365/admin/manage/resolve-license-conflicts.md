---
title: 解决许可证冲突
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: 了解如何解决与 Microsoft 365 for business 订阅的许可证冲突。
ms.openlocfilehash: a7f0b5cbca98a0550954e322c6fbe51d93627ee4
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645079"
---
# <a name="resolve-license-conflicts"></a>解决许可证冲突

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

我们建议您在创建新用户之前购买订阅所需的许可证。 通过这种方式，可在创建用户帐户时，将许可证分配给新用户。 如果你已将所有许可证分配给了用户，但一些许可证已经过期，或者你尝试删除已分配给某用户的许可证，将出现许可证冲突。 有关详细信息，请参阅 [从订阅中删除许可证](../../commerce/licenses/remove-licenses-from-subscription.md)。
  
## <a name="how-do-i-view-license-conflicts"></a>如何查看许可证冲突？

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>”页面。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">许可证</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">许可证</a>”页面。

::: moniker-end

2. 检查" **状态**"列以查看冲突信息。 如果存在冲突，您将看到一条警告消息，指出一个或多个用户需要有效的许可证。

    > [!NOTE]
    > 如果没有冲突，则不会看到" **状态**"列。

## <a name="how-do-i-resolve-license-conflicts"></a>如何解决许可证冲突？

您可以通过 [购买更多许可证](../../commerce/licenses/buy-licenses.md) 或 [从不再需要这些许可证的用户那里删除许可证](remove-licenses-from-users.md)来解决许可证冲突。 你可以根据需要[删除用户帐户以空出许可证](../add-users/delete-a-user.md)。
  
## <a name="related-articles"></a>相关文章

[向用户分配许可证](assign-licenses-to-users.md)
  
[删除用户许可证](remove-licenses-from-users.md)
