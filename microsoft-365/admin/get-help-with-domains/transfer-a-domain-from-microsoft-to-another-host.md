---
title: 将域从 Microsoft 传输到另一台主机
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: '在此处查找将域从 Microsoft 转移到另一个注册器的步骤。 '
ms.openlocfilehash: 7e00f5ae2c36a06803a3f7a8acd825dcab90805c
ms.sourcegitcommit: 6fb2a1c404ea3c3573b0f7803bf17459a9387891
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788973"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>将域从 Microsoft 传输到另一台主机

从 Microsoft 购买域后，不能将 Microsoft 365 域传输到另一个注册器60天。

> [!NOTE]
> _Whois_   查询显示 Microsoft 购买的域注册器作为通配符西部域 LLC。 但是，应仅联系 microsoft 365 购买的域的相关 Microsoft。

按照以下步骤在 Microsoft 365 获取代码，然后转到其他域注册器网站，以将您的域名转移到新的注册机构。

## <a name="transfer-a-domain"></a>转移域

1. 在管理中心中，转到  **设置**   >  **域**。

2. <在 " **域** " 页上，选择要转移到其他域注册机构的 Microsoft 365 域，然后选择 " **检查运行状况**"。

3. 在页面顶部，选择 " **转移域**"。

4. 在 " **选择转移域的位置** " 页上，选择 **不同的注册**器，然后单击 " **下一步**"。

5. 在 "**解锁域转移**" 页上，选择 "**解锁 <_您的域_ > 的传输**"，然后选择 "**下一步**"。

6. 检查你的域传输联系信息，然后选择 " **下一步**"。

7. 复制授权代码，并等待大约30分钟，让您的域传输状态更改为 "**注册**" 选项卡上的 "已**解锁以供转移**"，然后再继续执行下一步。

8. 转到要对其进行管理的域名注册机构的网站，以继续进行。 按照传输域的说明 (搜索其网站) 的帮助。

您可以在 Microsoft 365 中的 " **域**" 页上找到 "授权代码**注册**" 选项卡。

9. 传输完成后，你将在新域注册机构中续订你的域。

10. 若要完成此过程，请返回管理中心的 " **域** " 页，然后选择 "  **完成域传输**"。

> [!NOTE]
> Microsoft 365 购买的域不符合 nameserver 更改或在 Microsoft 365 组织之间传输域的条件。 如果需要其中任一项，则必须将域注册转移到其他注册器。
