---
title: 删除域
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: 了解如何删除 Microsoft 365 中的旧域，并将用户和组移至另一个域。
ms.openlocfilehash: 57e52cc4f44e41d31200b8b5469aed6c36b63d24
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814416"
---
# <a name="remove-a-domain"></a>删除域

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end
  
 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
是否由于想将域添加到其他 Microsoft 365 订阅计划而要删除该域？ 或者只是想取消订阅？ 可[更改计划或订阅](../../commerce/subscriptions/switch-to-a-different-plan.md)，也可[取消订阅](../../commerce/subscriptions/cancel-your-subscription.md)。
  
### <a name="step-1-move-users-to-another-domain"></a>步骤 1：将用户移至另一个域

#### <a name="move-users"></a>移动用户

::: moniker range="o365-worldwide"

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>。

2. 选择 **用户** > **活动用户**。

3. 选中要移动的所有用户姓名旁边的框。

4. 选择**页面**顶部 (**更多...) ，** 然后选择"更改**域"。**

5. 在" **更改域"** 窗格中，选择一个不同的域。

如果位于要删除的域中，则也需要自行执行此过程。编辑自己帐户的域时，必须先注销，然后使用选择继续的新域重新登录。

::: moniker-end

::: moniker range="o365-germany"

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>。  

2. 选择 **用户** > **活动用户**。

3. 选择要移动的所有用户姓名旁边的框。

4. 在页面顶部，选择更多**More** > **编辑域**。

5. 在" **编辑域** "窗格中，选择一个不同的域。
  
如果位于要删除的域中，则也需要自行执行此过程。编辑自己帐户的域时，必须先注销，然后使用选择继续的新域重新登录。

::: moniker-end

::: moniker range="o365-21vianet"

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>。  

2. 选择 **用户** > **活动用户**。

3. 选择要移动的所有用户姓名旁边的框。

4. 在页面顶部，选择更多**More** > **编辑域**。

5. 在" **编辑域** "窗格中，选择一个不同的域。
  
如果位于要删除的域中，则也需要自行执行此过程。编辑自己帐户的域时，必须先注销，然后使用选择继续的新域重新登录。

::: moniker-end

#### <a name="move-yourself"></a>自行移动

::: moniker range="o365-worldwide"

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>。

2. 转到" **用户的** \> **活动用户**"，然后从列表中选择您的帐户。

3. 在' **帐户** '选项卡上，选择 **'管理用户名**'，然后选择其他域。
  
4. 在顶部选择帐户名，然后选择"注**销"。**

5. 使用新域和相同密码登录。

也可使用 PowerShell 将用户移动到另一个域。 有关详细信息，请参阅 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)。 若要设置默认域，请使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)。

::: moniker-end

::: moniker range="o365-germany"

1. 转到" **用户** \> **活动用户**"，并在列表中选择你的姓名。

2. 在" **用户名/电子邮件"** 部分，选择" **编辑"，** 然后选择其他域。

3. 选择 **"设置为主** > **保存关闭** > **"。**
  
4. 在顶部选择帐户名，然后选择"注**销"。**

5. 使用新域和相同密码登录。

也可使用 PowerShell 将用户移动到另一个域。 有关详细信息，请参阅 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)。 若要设置默认域，请使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)。

::: moniker-end

::: moniker range="o365-21vianet"

1. 转到" **用户** \> **活动用户**"，并在列表中选择你的姓名。

2. 在" **用户名/电子邮件"** 部分，选择" **编辑"，** 然后选择其他域。

3. 选择 **"设置为主** > **保存关闭** > **"。**
  
4. 在顶部选择帐户名，然后选择"注**销"。**

5. 使用新域和相同密码登录。

也可使用 PowerShell 将用户移动到另一个域。 有关详细信息，请参阅 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)。 若要设置默认域，请使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)。

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a>步骤 2：将组移至另一个域

::: moniker range="o365-worldwide"

1. 在管理中心，转到"组 **组** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">"</a> 页面。
  
2. 选择组名称，然后在"电子邮件地址，主 **"** 下的 **"常规"选项卡上，选择**"编辑 **"。**

3. 使用下拉列表选择另一个域。

4. 依次选择“**保存**”和“**关闭**”。 对与要删除的域关联的任何组或通讯组列表重复此过程。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">，转到</a>"组 **组** > **"** 页面。

2. 选择组名称，然后选择"名称"旁**边的"编辑****"。**

3. 使用下拉列表选择另一个域。

4. 依次选择“**保存**”和“**关闭**”。 对与要删除的域关联的任何组或通讯组列表重复此过程。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">，转到</a>"组 **组** > **"** 页面。

2. 选择组名称，然后选择"名称"旁**边的"编辑****"。**

3. 使用下拉列表选择另一个域。

4. 依次选择“**保存**”和“**关闭**”。 对与要删除的域关联的任何组或通讯组列表重复此过程。

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a>步骤 3：删除旧域

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到"设置 **域** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">"</a> 页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到"设置 **域** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">"</a> 页面。

::: moniker-end
  
2. 在" **域** "页面上，选择要删除的域。

3. 在右侧窗格中，选择"**删除"。**

4. 按照任何其他提示操作，然后选择"关闭 **"。**

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>删除域需要多长时间？

如果域未在许多地方（如安全组、通讯组列表、用户和 Microsoft 365 组）引用的，则删除域对 Microsoft 365 而只需要花费 5 分钟。 如果存在众多使用该域的引用，则删除域可能需要数小时（一天）。
  
如果有数百或数千用户，使用 PowerShell 查询所有用户，然后将其移至另一个域。否则，可能大量用户将在 UI 中丢失，然后当你要删除域时，将无法删除而且找不到原因。有关详细信息，请参阅 [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)。若要设置默认域，请使用 [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0)。
  
## <a name="still-need-help"></a>是否仍需要帮助？

::: moniker range="o365-worldwide"

> [!NOTE]
> 不能从你的帐户中删除 [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) 域。
  
仍然无法正常工作？你的域可能需要手动删除。[请致电我们](../contact-support-for-business-products.md)，让我们打理一切！
  
::: moniker-end

## <a name="related-articles"></a>相关文章

[关于域的常见问题](../setup/domains-faq.md)

[切换到其他 Microsoft 365 商业版计划](../../commerce/subscriptions/switch-to-a-different-plan.md)

[取消订阅](../../commerce/subscriptions/cancel-your-subscription.md)
