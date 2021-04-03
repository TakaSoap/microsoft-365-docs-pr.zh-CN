---
title: 停止自动转发电子邮件
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: 了解如何停止自动转发电子邮件。
ms.openlocfilehash: b6715cfdf8622521d977e0746cb9a340a8f70a5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578599"
---
# <a name="stop-email-auto-forward"></a>停止电子邮件自动转发

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

如果黑客获取用户邮箱的访问权限，他们可以将用户的电子邮件自动转发到外部地址并窃取专有信息。 您可以通过创建邮件流规则来停止此操作。

## <a name="try-it"></a>试一试！

1. 从 Microsoft 365 管理中心，选择 **"Exchange"** 和"**邮件** 流"，在"规则"选项卡上，选择加号并选择"**创建新规则"。**
1. 选择“其他选项”。 命名新规则。
1. 然后打开下拉以应用此规则 **if**，选择发件人 **，然后****是外部内部**。
1. 选择 **"组织内部"，** 然后选择"确定 **"。**
1. 选择 **"添加** 条件"，打开下拉列表，选择 **"邮件属性**"， **然后包含邮件类型**。
1. 打开"**选择邮件类型**"下拉列表，选择"**自动转发"，** 然后选择"确定 **"。**
1. 打开" **执行以下操作"** 下拉列表，选择" **阻止** 邮件"，然后拒绝 **邮件并包含说明**。
1. 输入说明的消息文本，然后选择"确定 **"。**
1. 滚动到底部，**然后选择保存。**

    已创建规则，黑客将无法再自动转发邮件。