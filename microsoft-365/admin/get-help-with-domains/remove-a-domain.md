---
title: 删除域
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: 了解如何从域中删除旧域Microsoft 365将用户和组移动到另一个域或取消订阅。
ms.openlocfilehash: 3da47275e090296c9b192b4bd60ad19dd8cf4149
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63316823"
---
# <a name="remove-a-domain"></a>删除域

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。

是否要删除域，因为你想要将其添加到不同的订阅Microsoft 365计划中？ 或者只是想取消订阅？ 可[更改计划或订阅](../../commerce/subscriptions/switch-to-a-different-plan.md)，也可[取消订阅](../../commerce/subscriptions/cancel-your-subscription.md)。

> [!TIP]
> 如果需要有关本主题中步骤的帮助，请考虑 [与 Microsoft 小型企业专家合作](https://go.microsoft.com/fwlink/?linkid=2186871)。 借助业务助手，你和你的员工在发展业务时，可以针对从加入到日常使用的各个方面随时访问小型企业专家。

### <a name="step-1-move-users-to-another-domain"></a>步骤 1：将用户移动到另一个域

#### <a name="move-users"></a>移动用户

::: moniker range="o365-worldwide"

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>。

::: moniker-end

::: moniker range="o365-21vianet"

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>。

::: moniker-end

2. 选择 **"用户** > **""活动用户"**。

3. 选中要移动的所有用户的名称旁边的框。

4. 在页面顶部，然后选择"更改 **域"**。

5. 在" **更改域** "窗格中，选择其他域。

如果位于要删除的域中，则也需要自行执行此过程。编辑自己帐户的域时，必须先注销，然后使用选择继续的新域重新登录。

#### <a name="move-yourself"></a>移动自己

::: moniker range="o365-worldwide"

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>。

::: moniker-end

::: moniker range="o365-21vianet"

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>。

::: moniker-end

2. 转到 **"用户** \> **"**"活动用户"，然后从列表中选择你的帐户。

3. 在" **帐户"** 选项卡上，选择 **"管理用户名**"，然后选择其他域。

4. At the top， select your account name， then select **Sign Out**.

5. 使用新域和相同的密码登录。

也可使用 PowerShell 将用户移动到另一个域。有关详细信息，请参阅 [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname)。若要设置默认域，请使用 [Set-MsolDomain](/powershell/module/msonline/set-msoldomain)。

### <a name="step-2-move-groups-to-another-domain"></a>步骤 2：将组移动到另一个域

::: moniker range="o365-worldwide"

1. 在管理中心，转到组 **组**\>页面。<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a>

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">中心</a>，转到组 **组**>页面。

::: moniker-end

2. 选择组名称，然后在"电子邮件地址"下的"常规 **"** 选项卡上， **选择**"主要"，选择"编辑 **"**。

3. 使用下拉列表选择另一个域。

4. 依次选择“**保存**”和“**关闭**”。 对与要删除的域关联的任何组或通讯组列表重复此过程。

### <a name="step-3-remove-the-old-domain"></a>步骤 3：删除旧域

::: moniker range="o365-worldwide"

> [!NOTE]
> 如果要删除自定义域，请参阅 [删除自定义域，然后再](#remove-a-custom-domain) 继续。

1. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到"设置 **域"**\>页面。<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"></a>

::: moniker-end

2. 在 **"域** "页面上，选择要删除的域。

3. 在右侧窗格中，选择"删除 **"**。

4. 按照任何其他提示，然后选择"关闭 **"**。




### <a name="remove-a-custom-domain"></a>删除自定义域

如果要取消订阅并使用自定义域，则必须执行一些额外步骤，然后才能取消订阅。 

#### <a name="change-your-domain-nameserver-records-if-needed"></a>更改域名服务器记录（若需要）

如果设置了自定义域，则添加 DNS 记录以便此域使用 Microsoft 365 服务。在删除域之前，请确保在 DNS 主机上更新 DNS 记录，如域的 MX 记录。

例如，在 DNS 主机上更改 MX 记录。发送到你的域的电子邮件不再发到你的 Microsoft 地址，转而发到新的电子邮件提供商。（MX 记录确定针对你的域的电子邮件发送到何处。）

- 如果名称服务器 (NS) 记录 [当前指向 Office 365 名称服务器](../../admin/setup/add-domain.md)，则仅在更改 NS 记录以指向新的 DNS 主机（参见步骤 2）后，对 MX 记录的更改才会生效。

- 在更新 MX 记录之前，请告知用户你要切换其电子邮件的日期，以及计划使用的新电子邮件提供商。 此外，如果用户想要将其现有 Microsoft 电子邮件移动到新的提供商，他们必须执行额外的步骤。

- 在更改 MX 记录时，请确保保存[数据](/microsoft-365/commerce/subscriptions/cancel-your-subscription#save-your-data)并根据需要Office[文件](/microsoft-365/commerce/subscriptions/cancel-your-subscription#uninstall-office-optional)。

#### <a name="update-your-domain-mx-and-other-dns-records-if-youre-using-a-custom-domain"></a>更新域的 MX 或其他 DNS 记录（如果正在使用自定义域）

如果你在设置域时将名称服务器 (NS) 记录切换为 Microsoft 365，则必须在计划使用的 DNS 主机处设置或更新 MX 记录和其他 DNS 记录，然后将 NS 记录更改到该 DNS 主机。

如果在设置域时未切换 NS 记录，则更改 MX 记录后，邮件将立即开始转到新的地址。

若要更改 NS 记录，请参阅更改[名称服务器以设置Microsoft 365注册机构的名称](../../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md)。



## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>删除域需要多长时间？

如果域未在很多位置（如安全组、通讯组列表、用户和 Microsoft 365 组）被引用，Microsoft 365删除域。 如果存在众多使用该域的引用，则删除域可能需要数小时（一天）。

如果有数百或数千用户，使用 PowerShell 查询所有用户，然后将其移至另一个域。否则，可能大量用户将在 UI 中丢失，然后当你要删除域时，将无法删除而且找不到原因。有关详细信息，请参阅 [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname)。若要设置默认域，请使用 [Set-MsolDomain](/powershell/module/msonline/set-msoldomain)。

## <a name="still-need-help"></a>仍然需要帮助？

::: moniker range="o365-worldwide"

> [!NOTE]
> 不能从你的帐户中删除 [".onmicrosoft.com"](../setup/domains-faq.yml) 域。 删除域时，用户帐户将恢复为".onmicrosoft.com"地址作为主 SMTP/UserprincipalName。

仍然无法正常工作？你的域可能需要手动删除。[请致电我们](../../business-video/get-help-support.md)，让我们打理一切！

::: moniker-end

::: moniker range="o365-21vianet"

> [!NOTE]
> 无法从帐户 [中删除".partner.onmschina.cn"](../setup/domains-faq.yml) 域。 删除域时，用户帐户将恢复为".partner.onmschina.cn"地址作为主 SMTP/UserprincipalName。

仍然无法正常工作？你的域可能需要手动删除。[请致电我们](../../business-video/get-help-support.md?view=o365-21vianet&preserve-view=true)，让我们打理一切！

::: moniker-end

## <a name="related-content"></a>相关内容

[域常见问题](../setup/domains-faq.yml) （文章）

[切换到其他业务Microsoft 365， (](../../commerce/subscriptions/switch-to-a-different-plan.md)文章) 

[取消订阅 (](../../commerce/subscriptions/cancel-your-subscription.md) 文章) 
