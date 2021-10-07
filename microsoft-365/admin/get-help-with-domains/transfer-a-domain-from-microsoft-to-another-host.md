---
title: 将域从 Microsoft 转移到其他主机
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
ms.openlocfilehash: c6e74f654c1bbd35f69b071a2076c95cb651f476
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60164616"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>将域从 Microsoft 转移到其他主机

从 Microsoft 购买域后，Microsoft 365域 60 天内无法转移到另一个注册机构。

> [!NOTE]
> Whois _查询_   显示 Microsoft 购买的域注册机构为"Wild West Domains LLC"。 但是，应仅就你购买Microsoft 365联系 Microsoft。

按照以下步骤在 Microsoft 365 获取代码，然后转到其他域注册机构网站以设置将域名传输到新注册机构。

## <a name="transfer-a-domain"></a>转移域

1. 在管理中心，  **转到"设置**   >  **域"。**

2. On the **Domains** page， select the Microsoft 365 domain that you want to transfer to another domain registrar， and then select **Check health**.

3. 在页面顶部，选择"转移 **域"。**

4. 在"**选择域的传输位置**"页上，选择 **"其他注册机构"，** 然后单击"下一步 **"。**

5. 在解锁 **域传输页面上**，选择解锁 **传输<_你的域，_ >** 然后选择下一 **步**。

6. 检查域传输联系人信息，然后选择"下一 **步"。**

7. 复制授权代码并等待大约 30 分钟，让域传输状态在"注册"选项卡上更改为"已解锁"进行传输，然后再继续执行以下步骤。

8. 转到要管理域名的域注册机构的网站。 按照说明传输域 (在网站上搜索帮助) 。 这通常意味着支付转移费用，将 Authcode 给予新注册机构，以便他们可以启动转移。 Microsoft 将通过电子邮件确认我们已收到转移请求，域将在 5 天内转移。

    您可以在"域"页面上找到授权代码"注册" **选项卡Microsoft 365。**
    
    > [!TIP]
    > .uk 域需要不同的过程。 请联系 Microsoft 支持部门并请求 **IPS 标记更改** ，以匹配要管理域的注册机构。 标记更改后，域将立即转移到新注册机构。 然后，你需要与新的注册机构合作来完成转移，可能支付转移费用，并借助你的新注册机构将已转移的域添加到你的帐户。

9. 传输完成后，你将在新的域注册机构续订域。

10. 若要完成此过程，请返回到管理中心中的"域"页面，然后选择"完成  **域传输"。** 这会将域标记为不再从 Microsoft 365购买，并禁用域订阅。 它将不会从租户中删除域，并且不会影响域中的现有用户和邮箱。

> [!NOTE]
> Microsoft 365购买的域不符合名称服务器更改或在组织之间传输Microsoft 365资格。 如果其中任一项是必需的，则必须将域注册转移到另一个注册机构。
