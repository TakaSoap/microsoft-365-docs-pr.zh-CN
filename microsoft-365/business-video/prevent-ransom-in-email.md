---
title: 创建针对勒索软件的电子邮件规则
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何创建电子邮件规则以防止勒索软件。
ms.openlocfilehash: f76d9883ef2d22803867da267f48760ec8894f99
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60172739"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>创建电子邮件规则以防止勒索软件

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365防止 JavaScript、批处理和可执行文件等潜在危险文件在 Outlook 中打开，帮助保护你的企业免受勒索软件Outlook。 若要通过添加阻止或警告其他类型的文件的规则来增强此级别的保护，请按照以下步骤操作。

## <a name="try-it"></a>试一试！

1. 在管理中心中 [https://admin.microsoft.com](https://admin.microsoft.com) ，选择 **"Exchange** 中心 **"下的"管理中心"。**
1. 从左侧的菜单中，选择"**邮件流"。**
1. On the rules tab， choose the arrow next to the plus (+) symbol， and then choose **Create a new rule**.
1. 在"**新规则**"页上，输入规则名称，滚动到底部，然后选择"更多 **选项"。**
1. 在 **"在应用此规则时"** 下，选择 **"任何附件**"，然后选择"**文件扩展名包含以下词语"。**
1. 在"指定 **单词** 或短语"下的框中，输入您希望应用规则的文件扩展名，例如可以包含宏的文件扩展名。 使用加 (+) 符号一次添加一个。

    阅读"防范勒索软件 ["，详细了解文件类型](../admin/security-and-compliance/secure-your-business-data.md#ransomware)。

1. 向下滚动查看列表，然后选择"确定 **"。**
1. 在新规则 **页面上，** 选择" **添加** 条件"，然后选择"执行以下操作 **"下的条件**。
1. 您有很多规则选项可供选择，但本示例中我们将选择"使用邮件 **通知收件人"。**
1. 为通知输入消息文本，然后选择"确定 **"。**
1. 可选：在 **"新建规则**"页上，选择"添加例外"，然后输入规则例外的任何详细信息，例如来自受信任发件人的邮件。
1. 在"新建规则"页上，选择" **保存"，** 然后查看所提供的规则摘要信息。