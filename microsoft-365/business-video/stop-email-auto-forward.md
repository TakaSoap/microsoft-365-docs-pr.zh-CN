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
- AdminTemplateSet
- admindeeplinkMAC
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何通过创建邮件流规则来停止自动转发电子邮件，以避免窃取专有信息。
ms.openlocfilehash: 5c13e43f29b6d49b13daf4eb0aa6e3d6fd8275ae
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59170815"
---
# <a name="stop-email-auto-forward"></a>停止电子邮件自动转发

## <a name="watch-stop-auto-forwarding-emails"></a>观看：停止自动转发电子邮件

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

如果黑客获取用户邮箱的访问权限，他们可以将用户的电子邮件自动转发到外部地址并窃取专有信息。 您可以通过创建邮件流规则来停止此操作。

## <a name="try-it"></a>试一试！

1. From the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>， select **Exchange**， **mail flow**， and on the **rules** tab， select the plus sign and choose create a **new rule**.
1. 选择“其他选项”。 命名新规则。
1. 然后打开下拉以在 中应用 **此规则，选择** 发件人 **，然后****是外部内部**。
1. 选择 **"组织内部"，** 然后选择"确定 **"。**
1. 选择 **"添加** 条件"，打开下拉列表，选择 **"邮件属性**"， **然后包含邮件类型**。
1. 打开"**选择邮件类型**"下拉列表，选择"**自动转发"，** 然后选择"确定 **"。**
1. 打开" **执行以下操作"** 下拉列表，选择" **阻止** 邮件"， **然后拒绝邮件并包含说明**。
1. 输入说明的消息文本，然后选择"确定 **"。**
1. 滚动到底部，**然后选择保存。**

    已创建规则，黑客将无法再自动转发邮件。

## <a name="related-content"></a>相关内容

[为用户添加另一个电子邮件别名](../admin/email/add-another-email-alias-for-a-user.md)（文章）\
[在 Microsoft 365 中配置电子邮件转发](../admin/email/configure-email-forwarding.md)（文章）\
[查找并修复作为企业管理员Office 365的电子邮件](/exchange/troubleshoot/email-delivery/email-delivery-issues) (问题) 