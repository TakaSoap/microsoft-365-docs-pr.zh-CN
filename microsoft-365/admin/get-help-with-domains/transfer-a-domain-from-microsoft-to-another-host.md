---
title: 将域从 Microsoft 传输到另一个主机
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
description: '在此处找到将域从 Microsoft 传输到另一注册机构的步骤。 '
ms.openlocfilehash: 18f2b6502268b757b651abe08585cc06b63d7129
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782470"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>将域从 Microsoft 传输到另一个主机

从 Microsoft 购买域后，60 天内无法将Microsoft 365域传输到其他注册机构。

> [!NOTE]
> _Whois_ 查询将 Microsoft 购买的域注册机构显示为 Wild West Domains LLC。 但是，应仅联系 Microsoft，了解Microsoft 365购买的域。

按照以下步骤在Microsoft 365获取代码，然后转到另一个域注册机构网站以设置将域名传输到新注册机构。

## <a name="transfer-a-domain"></a>传输域

1. 在管理中心，转到 **设置** \> **域**。

2. 在 **“域”页上**，选择要传输到另一个域注册机构的Microsoft 365域，然后选择 **“检查运行状况**”。

3. 在页面顶部，选择 **“传输”域**。

4. 在 **“选择域位置”** 页上，选择 **其他注册机构**，然后单击 **“下一步**”。

5. 在 **“解锁域传输**”页上，**为 _域_><选择“解锁传输**”，然后选择 **“下一步**”。

6. 检查域传输联系人信息，然后选择 **“下一步**”。

7. 复制授权代码，等待大约 30 分钟，以便域传输状态更改 **为“已解锁** ”以在 **“注册”** 选项卡上进行传输，然后再继续执行后续步骤。

8. 请转到要在今后管理域名的域注册机构的网站。 按照有关转移域的说明 (在其网站上搜索帮助) 。 这通常意味着支付转让费，并向新注册机构提供身份验证码，以便他们可以启动传输。 Microsoft 将向你发送电子邮件，确认我们已收到传输请求，域将在 5 天内传输。

    可以在Microsoft 365的 **“域**”页上找到“授权代码 **注册**”选项卡。

    > [!TIP]
    > .uk 域需要不同的过程。 请联系Microsoft 支持部门，请求 **更改 IPS 标记**，以匹配要在今后管理域的注册机构。 标记更改后，域会立即传输到新注册机构。 然后，你需要与新的注册机构合作来完成转移，可能支付转移费，并使用新的注册机构将已转移的域添加到帐户。

9. 传输完成后，你将在新的域注册机构续订域。

10. 若要完成此过程，请返回到管理中心的 **“域** ”页，然后选择 **“完成域传输**”。 这会将域标记为不再从Microsoft 365购买，并将禁用域订阅。 它不会从租户中删除域，也不会影响域上的现有用户和邮箱。

> [!NOTE]
> Microsoft 365购买的域不符合名称服务器更改或在Microsoft 365组织之间传输域的条件。 如果其中任一项是必需的，则必须将域注册转移到另一注册机构。
