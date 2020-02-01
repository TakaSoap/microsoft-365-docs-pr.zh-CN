---
title: 管理自助服务购买（管理员）
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
- commerce
search.appverid:
- MET150
description: 管理员可以了解如何管理组织中的用户所做的自我服务购买。
ms.openlocfilehash: 5db942b42f398e8951da43add7013569af52c53f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594106"
---
# <a name="manage-self-service-purchases-admin"></a>管理自助服务购买（管理员）

作为管理员，你可以查看组织中的人员进行的自助购买。 您可以查看产品、购买者名称、购买订阅、到期日期、购买价格和分配给每种自助服务购买的用户。 如果你的组织需要，你可以通过 PowerShell 基于每个产品禁用自助购买。 你的数据管理和访问策略与通过自助服务购买或集中购买的产品相同。

您还可以控制组织中的用户是否可以进行自助服务购买。 有关详细信息，请参阅[Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。

## <a name="view-self-service-subscriptions"></a>查看自助服务订阅

1. 在 "管理中心" 中，转到 "**帐单** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">产品 & 服务</a>" 页。

2. 在 "**优化结果**" 下，从 "**帐户类型**" 下拉选择 "**自助服务**"。

3. 若要查看订阅的更多详细信息，请从列表中选择一个订阅。

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>查看拥有自助服务购买订阅许可证的所有者

1. 在管理中心，转到 "**记帐** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面。

2. 选择 "筛选器" 图标，然后选择 "**自助服务**"。

3. 选择一个产品以查看分配给人员的许可证。

    > [!NOTE]
    > 如果有多个产品购买，则该产品仅列出一次，"**可用数量**" 列显示为该产品购买的所有订阅的总数。

4. "**用户**" 列表按进行自助服务购买的人员的姓名进行分组。

5. 若要导出具有这些订阅的许可证的用户列表，请选择要导出的订阅，然后选择 "**导出用户**"。

## <a name="disable-or-enable-self-service-purchases"></a>禁用或启用自助购买

您可以为组织中的用户禁用或启用自助服务购买。 **MSCommerce** PowerShell 模块包含**AllowSelfServicePurchase**的**PolicyID**参数值，可让你控制组织中的用户是否可以进行自助购买，以及为哪些产品提供服务。

您可以使用**MSCommerce** PowerShell 模块执行以下操作：

- 查看**AllowSelfServicePurchase**参数值&mdash;的默认状态，无论它是由产品启用还是禁用
- 查看适用产品的列表以及是否启用或禁用自助式购买
- 查看或修改特定产品的当前设置以启用或禁用该产品

有关详细信息，请参阅[Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。

## <a name="centralize-licenses-under-a-single-subscription"></a>在单个订阅下集中使用许可证

您可以分配现有许可证，或通过现有协议为分配到自助购买的用户购买其他订阅。 在分配了这些集中购买的许可证之后，可以请求该购买者取消其现有订阅。

1. 使用全局管理员或帐单管理员帐户登录到<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>。

2. 转到 "**付费** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">购买服务</a>" 页。

3. 查找并选择要购买的产品，然后选择 "**购买**"。

4. 完成其余步骤以完成购买。

5. 按照查看在第6步中要引用的用户列表中[查看拥有自助购买订阅的许可证](#view-who-has-licenses-for-a-self-service-purchase-subscription)的步骤中的步骤操作。

6. 将许可证分配给在其他订阅中具有许可证的每个人。 有关完整步骤，请参阅向[用户分配许可证](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users)。

7. 请与购买自助服务购买订阅的人员联系，让他们取消该订阅。

## <a name="need-help-contact-us"></a>需要帮助? 联系我们。

有关自助购买的常见问题，请参阅[自助服务购买 FAQ](self-service-purchase-faq.md)。

如果你有任何疑问或需要有关自助购买的帮助，请[联系支持人员](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。