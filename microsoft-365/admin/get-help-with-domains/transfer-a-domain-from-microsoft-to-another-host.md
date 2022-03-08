---
title: 将域从 Microsoft 转移到其他主机
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: '在此处查找将域从 Microsoft 转移到另一个注册机构的步骤。 '
ms.openlocfilehash: 192e9c1e14666f80fb670c5c8e268ae54ece0c64
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63316767"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>将域从 Microsoft 转移到其他主机

从 Microsoft 购买域后，60 天内无法将 Microsoft 365 域转移到另一个注册机构。

> [!NOTE]
> _Whoisquery_  显示 Microsoft 购买的域注册机构为"Wild West Domains LLC"。 但是，应仅就 Microsoft 365 购买域与 Microsoft 联系。

按照以下步骤在 Microsoft 365 获取代码，然后转到其他域注册机构网站，设置将域名传输到新注册机构。

## <a name="transfer-a-domain"></a>转移域

1. 在管理中心，转到   **"设置""** > **域"**。

2. 在" **域** "页面上，选择要转移到其他域注册机构的 Microsoft 365 域，然后选择"检查 **运行状况"**。

3. 在页面顶部，选择"转移 **域"**。

4. 在" **选择域的传输位置** "页上，选择 **"其他注册机构"**，然后单击"下一步 **"**。

5. 在" **解锁域传输"** 页面上，选择" **解锁传输<_你的域，_>** 然后选择"下一步 **"**。

6. 检查域传输联系人信息，然后选择"下一 **步"**。

7. 复制授权代码并等待大约 30 分钟，让域传输状态在"注册"选项卡上更改为"已解锁"进行传输，然后再继续执行以下步骤。

8. 转到要管理域名的域注册机构的网站。 按照说明传输域 (在网站上搜索帮助) 。 这通常意味着支付转移费用，将 Authcode 给予新注册机构，以便他们可以启动转移。 Microsoft 将通过电子邮件确认我们已收到转移请求，域将在 5 天内转移。

    可以在 Microsoft 365 中的域页面上找到授权 **** 代码注册选项卡。
    
    > [!TIP]
    > .uk 域需要不同的过程。 请联系 Microsoft 支持部门并请求 **IPS 标记更改** ，以匹配要管理域的注册机构。 标记更改后，域将立即转移到新注册机构。 然后，你需要与新注册机构一起完成转移，可能会支付转移费用，并借助你的新注册机构将已转移的域添加到你的帐户。

9. 传输完成后，你将在新的域注册机构续订域。

10. 若要完成此过程，请返回到管理中心中的"域"页面，然后选择"  **完成域传输"**。 这会将域标记为不再从 Microsoft 365 购买，并禁用域订阅。 它将不会从租户中删除域，并且不会影响域中的现有用户和邮箱。

> [!NOTE]
> Microsoft 365 购买的域不符合更改名称服务器或在 Microsoft 365 组织之间传输域资格。 如果其中任一项是必需的，则必须将域注册转移到另一个注册机构。
