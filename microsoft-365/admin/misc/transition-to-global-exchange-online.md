---
title: 更新 MX 记录以转换到全局 Exchange Online 服务
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何从德国 Microsoft 云Exchange Online全球 Exchange Online服务
ms.openlocfilehash: cf11b44ffd8bb52151100e802929d82f5498c668
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192651"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a>更新 MX 记录以转换到全局 Exchange Online 服务

1. 登录到"Microsoft 365 管理中心"，然后转到 **"设置**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**域"**</a>

2. 状态将显示在每个域的右侧。 如果组织的域指向德国 Microsoft 云Exchange Online，则需要更新 MX 记录。

3. 单击域，然后单击检测到 **的 DNS 错误，单击此处查看**。

4. 此页面将包含说明如何修复 MX 记录的说明。 如果域的注册[机构使用"](../setup/add-domain.md#registrars-with-domain-connect)域连接，可以单击顶部的"修复我的记录"。 否则，你可以按照向导中的链接，分步 **说明注册** 机构。