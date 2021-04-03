---
title: 添加域
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何将另一个域添加到订阅。
ms.openlocfilehash: 8899cb9667ffa080746ca9173b61897f9c5db399
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578997"
---
# <a name="add-another-domain"></a>添加其他域

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

您的公司可能出于不同目的需要多个域名。 例如，你可能想要添加公司名称的不同拼写，因为客户已在使用它，并且他们的通信未能到达你。

## <a name="try-it"></a>试一试！

1. 在 Microsoft 365 管理中心中，选择"设置 **"。**
1. 在 **"设置自定义域"下，选择**"查看 **"。**
1. 选择 **"管理**"，然后选择"**添加域"。**
1. 输入要添加的新域名，然后选择"下一步 **"。**
1. 登录域注册机构（在这种情况下为 GoDaddy），然后选择"下一步 **"。**
1. 如果系统提示，登录注册机构，然后选择"授权 **"。**
1. 选择 **"为我添加 DNS 记录"，** 然后选择"下一 **步"。**
1. 选择新域的服务并清除将由其他域处理的任何服务的复选框。 例如，如果你只想将新域用于电子邮件，请选择 **"Exchange"，** 然后清除 **"Skype for Business"** 和 **"Office 365** 移动设备管理"复选框。
1. 选择 **"下** 一 **步"，"** 授权 **"，"** 下一步"，然后选择"**完成"。** 已添加新域。

若要在你的新域中接收电子邮件，你需要为每个用户添加新的电子邮件别名：

1. 选择 **"用户****"** 和"活动用户"，然后选择将为其分配新别名的用户。
1. 选择 **"管理电子邮件别名"，** 然后选择"**添加别名"。**
1. 输入用户名，然后从下拉列表中选择新域。
1. 选择 **"保存更改**"，然后关闭窗口。
1. 对应在新域中接收电子邮件的每个用户重复这些步骤。