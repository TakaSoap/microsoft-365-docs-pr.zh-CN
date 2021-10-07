---
title: 创建公司范围的签名
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
- admindeeplinkMAC
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何创建公司范围的电子邮件签名。
ms.openlocfilehash: bf856881fd19386390031807c0098279fc37a595
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60172811"
---
# <a name="create-a-company-wide-email-signature"></a>创建公司范围的电子邮件签名

## <a name="watch-create-a-company-wide-email-signature"></a>观看：创建公司范围的电子邮件签名

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf?autoplay=false]

公司范围内的电子邮件签名将显示在组织中人员发送的每封电子邮件上。 您可以使用它显示重要详细信息，如公司联系人信息或法律免责声明。 

## <a name="try-it"></a>试一试！

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">"Microsoft 365 管理中心"</a>中，选择 **"Exchange"。**
1. 选择 **"邮件流"。**
1. 选择 **"添加 +**"，然后选择"**应用免责声明"。**
1. 在" **新建规则"** 页上：
    1. 输入规则的名称。
    1. From the **Apply this rule if** drop-down list， select Apply to all **messages**.
    1. 在 **"执行以下操作"** 下拉列表中，验证 **是否显示"附加** 免责声明"。
    1. 在页面右侧，选择 **"输入** 文本"，然后在"指定免责声明"文本框中输入电子邮件 **签名** 的文本。 您可以通过使用 HTML 设置文本的格式来改进签名的外观。
    1. 如果希望图像显示在签名中，则需要使用该图像的公开 URL。 浏览到 Web 上的图像，右键单击它，然后选择复制 **图像地址**。 将地址粘贴到 **"指定免责声明** "文本框中。 选择 **"确定**"，然后向下滚动。
    1. 若要确保签名适用于加密电子邮件，请添加回退选项。 在页面右侧，选择"选择一个"，选择"**自动** 换行"，然后选择"确定 **"。**
    1. 向下滚动，将模式设置为"强制 **"，** 然后选择"保存 **"。**
1. 将显示一条警告消息。 选择 **"是** "将规则应用于所有未来邮件。

    已创建签名。 发送下一封电子邮件时，不会看到刚创建的签名，但电子邮件收件人将看到它。