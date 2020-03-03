---
title: 解决 Office 365 商业版中的许可证冲突
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: 了解如何解决与 Office 365 for business 订阅的许可证冲突。
ms.openlocfilehash: 63464951c4f1fd568248ca5c43da9f8c94347711
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361777"
---
# <a name="resolve-license-conflicts-in-office-365-for-business"></a>解决 Office 365 商业版中的许可证冲突

我们建议您在创建新用户之前购买订阅所需的许可证。 通过这种方式，可在创建用户帐户时，将许可证分配给新用户。 如果你已将所有许可证分配给了用户，但一些许可证已经过期，或者你尝试删除已分配给某用户的许可证，将出现许可证冲突。 有关详细信息，请参阅[从订阅中删除许可证](../../commerce/licenses/remove-licenses-from-subscription.md)。
  
## <a name="how-do-i-view-license-conflicts"></a>如何查看许可证冲突？

1. 在管理中心，转到 "**记帐** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面。

    如果使用的是 Office 365 德国，请转到 "<a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">许可证</a>" 页。

    如果你正在使用由世纪互联运营的 Office 365，请转到 "<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">许可证</a>" 页面。

2. 检查" **状态**"列以查看冲突信息。 如果存在冲突，您将看到一条警告消息，指出一个或多个用户需要有效的许可证。

    > [!NOTE]
    > 如果没有冲突，则不会看到" **状态**"列。

## <a name="how-do-i-resolve-license-conflicts"></a>如何解决许可证冲突？

您可以通过[购买更多许可证](../../commerce/licenses/buy-licenses.md)或[从不再需要这些许可证的用户那里删除许可证](remove-licenses-from-users.md)来解决许可证冲突。 你可以根据需要[删除用户帐户以空出许可证](../add-users/delete-a-user.md)。
  
## <a name="related-articles"></a>相关文章 

[向用户分配许可证](assign-licenses-to-users.md)
  
[删除用户许可证](remove-licenses-from-users.md)
