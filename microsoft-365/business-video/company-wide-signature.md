---
title: 创建公司范围内的签名
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: 了解如何创建公司范围内的电子邮件签名。
ms.openlocfilehash: 64c269abd25cab74ec5b0836975902e46a611c8c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701838"
---
# <a name="create-a-company-wide-email-signature"></a>创建公司范围内的电子邮件签名

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf?autoplay=false]

公司范围内的电子邮件签名显示在组织中人员发送的每封电子邮件上。 您可以使用它显示重要详细信息，如公司联系人信息或法律免责声明。 

## <a name="try-it"></a>试一试！

1. 在 Microsoft 365 管理中心中，选择 **Exchange。**
1. 选择 **"邮件流"。**
1. 选择 **"添加 +"，** 然后选择"**应用免责声明"。**
1. 在" **新建规则"** 页上：
    1. 输入规则的名称。
    1. 从"**在下拉列表中应用** 此规则"中，选择"**应用于所有邮件"。**
    1. 在 **"执行以下操作"** 下拉列表中，验证 **是否显示"追加免责声明** "。
    1. 在页面右侧，选择 **"** 输入文本"，然后在"指定免责声明"文本框中输入电子邮件签名的文本。  您可以通过使用 HTML 设置文本的格式来改进签名的外观。
    1. 如果希望图像显示在签名中，则需要使用该图像的公开 URL。 浏览到 Web 上的图像，右键单击它，然后选择"**复制图像地址"。** 将地址粘贴到 **"指定免责声明** "文本框中。 选择 **"** 确定"，然后向下滚动。
    1. 若要确保签名适用于加密电子邮件，请添加回退选项。 在页面右侧，选择"**选择** 一个"，选择"**自动** 换行"，然后选择"**确定"。**
    1. 向下滚动并保留模式设置为 **"** 强制"，然后选择"**保存"。**
1. 将显示一条警告消息。 选择 **"是** "将规则应用于所有未来邮件。

    已创建签名。 发送下一封电子邮件时，不会看到刚创建的签名，但电子邮件收件人将看到它。