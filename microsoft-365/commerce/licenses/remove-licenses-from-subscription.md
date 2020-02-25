---
title: 从 Office 365 商业版订阅删除许可证
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 9c64d127-e2dd-4ecc-81f5-2f87e5a74803
description: 了解当许可证已分配给某人时，如何从 Office 365 for business 订阅中删除许可证。
ms.openlocfilehash: d1af1b5696d359daf6578e090180b79587952106
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238371"
---
# <a name="remove-licenses-from-your-office-365-for-business-subscription"></a>从 Office 365 商业版订阅删除许可证

不能删除订阅中已分配给用户的许可证。 如果要删除当前分配给某人的许可证，则需要先[删除许可证（来自用户](../../admin/manage/remove-licenses-from-users.md)），然后才能从订阅中删除该许可证。

::: moniker range="o365-worldwide"

> [!NOTE]
> 如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。

## <a name="remove-licenses"></a>Remove licenses

1. 在管理中心，转到“**账单**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">产品和服务</a>”页面。

2. 在 "**产品 & 服务**" 页上，找到要从中删除许可证的订阅，然后选择 "**添加/删除许可证**"。

    [如果看不到"添加/删除"链接，该怎么办？](#what-if-i-dont-see-the-addremove-licenses-link)

3. 在 "**许可证总数**" 框中，输入此订阅所需的许可证总数，然后选择 "**提交更改**"。 例如，如果你有 110 个许可证而要删除其中 5 个，请输入 105。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心中，转到 "**记帐** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">订阅</a>" 页。

2. 在 "**订阅**" 页上，选择要从中删除许可证的订阅，然后选择 "**添加/删除许可证**"。

    [如果看不到"添加/删除"链接，该怎么办？](#what-if-i-dont-see-the-addremove-licenses-link)

3. 在" **许可证总数**"框中，输入此订阅所需的许可证总数，然后选择" **提交**"。 例如，如果你有 110 个许可证而要删除其中 5 个，请输入 105。


::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心中，转到 "**记帐** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">订阅</a>" 页。

2. 在 "**订阅**" 页上，选择要从中删除许可证的订阅，然后选择 "**添加/删除许可证**"。

    [如果看不到"添加/删除"链接，该怎么办？](#what-if-i-dont-see-the-addremove-licenses-link)

3. 在" **许可证总数**"框中，输入此订阅所需的许可证总数，然后选择" **提交**"。 例如，如果你有 110 个许可证而要删除其中 5 个，请输入 105。

::: moniker-end

## <a name="what-if-i-dont-see-the-addremove-licenses-link"></a>如果看不到"添加/删除"链接，该怎么办？

本部分介绍" **添加/删除许可证**"链接不可用的原因，以及发生这种情况时应该怎么办。
  
### <a name="a-credit-check-is-pending"></a>正在等待信用检查

如果正在等待信用检查，你将看到"正在等待信用检查"消息，并在完成信用检查之后才能删除许可证。如果正在等待信用检查，请稍后返回查看是否已完成信用检查。信用检查通常需要两个工作日才能完成。
  
完成信用检查后，应可在" **用户**"部分看到" **添加/删除许可证**"链接。 如果是这样，请转到 "[删除 Office 365 中的许可证" 以进行商业订阅](#remove-licenses-from-your-office-365-for-business-subscription)。
  
### <a name="you-activated-the-subscription-using-a-product-key"></a>使用产品密钥激活了订阅

如果订阅是使用 25 个字符的产品密钥购买并激活的，你将看到"预付费"字样。如果订阅是使用产品密钥购买的，则不能删除许可证，因为已经为其付费。但是，可以在续订订阅时删除额外的许可证。
  
### <a name="you-bought-your-subscription-through-a-partner"></a>通过合作伙伴购买了订阅

如果你的订阅是通过 CSP 或合作伙伴购买的，则无法删除许可证。 请联系你的 CSP 或使用批量许可服务中心（VLSC）链接联系你的合作伙伴以获取帮助。
  
## <a name="what-you-need-to-know-about-removing-licenses-from-users-in-office-365-for-business"></a>在 Office 365 商业版中删除用户许可证的需知

- 您必须是全局管理员或用户管理管理员。有关详细信息，请参阅[关于管理员角色](../../admin/add-users/about-admin-roles.md)。

- 使用这些步骤向现有用户帐户添加许可证。请[了解如何同时添加用户帐户和分配许可证](../../admin/add-users/add-users.md)。

## <a name="articles-about-managing-licenses-for-your-subscription"></a>有关管理订阅许可证的文章

- [了解订阅和许可证](subscriptions-and-licenses.md)

- [删除用户许可证](../../admin/manage/remove-licenses-from-users.md)

- [向用户分配许可证](../../admin/manage/assign-licenses-to-users.md)

- [购买订阅的许可证](buy-licenses.md)

- [购买另一个订阅](../buy-another-subscription.md)

- [购买或编辑附加设备](../buy-or-edit-an-add-on.md)

- [管理 Yammer 用户许可证](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)

## <a name="related-links"></a>相关链接

[取消订阅](../subscriptions/cancel-your-subscription.md)
