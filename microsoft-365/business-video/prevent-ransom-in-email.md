---
title: 创建针对勒索软件的电子邮件规则
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: 了解如何创建电子邮件规则以防止勒索软件。
ms.openlocfilehash: 0d8b4a9de881f47752ac0bfbf778453d6ee73046
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422249"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>创建电子邮件规则以防止勒索软件

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 通过阻止在 Outlook 中打开具有潜在危险的文件（如 JavaScript、批处理和可执行文件）来帮助保护你的企业免受勒索软件攻击。 若要通过添加阻止或警告您其他类型的文件的规则来增强此级别的保护，请按照以下步骤操作。

## <a name="try-it"></a>试一试！

1. From the admin center [https://admin.microsoft.com](https://admin.microsoft.com) at， choose **Exchange** under **Admin centers.**
1. 从左侧的菜单中，选择 **邮件流**。
1. 在"规则"选项卡上，选择加号 (+) 旁边的箭头，然后选择"创建新 **规则"。**
1. 在 **"新规则"** 页上，输入规则的名称，滚动到底部，然后选择"更多 **选项"。**
1. 在 **"如果应用此规则"下**， **选择"任何附件**"，然后选择文件 **扩展名包含这些词语**。
1. 在 **"指定单词** 或短语"下的框中，输入您希望应用规则的文件扩展名，例如可以包含宏的文件扩展名。 使用加 (+) 符号一次添加一个。

    通过阅读"防范勒索软件" [了解有关文件类型的内容](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)。

1. 向下滚动查看列表，然后选择"确定 **"。**
1. 在新 **规则页上** ，选择 **"添加条件**"，然后选择"执行以下操作 **"下的条件**。
1. 您有很多规则选项可供选择，但本示例中，我们将选择"使用邮件 **通知收件人"。**
1. 输入通知的消息文本，然后选择"确定 **"。**
1. 可选：在 **"新建规则**"页上，选择"添加例外"，然后输入规则例外的任何详细信息，例如来自受信任发件人的邮件。
1. 在"新建规则"页上， **选择"** 保存"，然后查看所提供的规则摘要信息。