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
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何创建电子邮件规则以防止勒索软件。
ms.openlocfilehash: 3b45af71aa26beb31e21f5db662091f46343f97d
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926110"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>创建电子邮件规则以防止勒索软件

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 通过阻止在 Outlook 中打开具有潜在危险的文件（如 JavaScript、批处理和可执行文件）来帮助保护你的企业免受勒索软件攻击。 若要通过添加阻止或警告您其他类型的文件的规则来增强此级别的保护，请按照以下步骤操作。

## <a name="try-it"></a>试一试！

1. From the admin center [https://admin.microsoft.com](https://admin.microsoft.com) at， choose **Exchange** under **Admin centers.**
1. 从左侧的菜单中，选择 **邮件流**。
1. 在"规则"选项卡上，选择加号 (+) 旁边的箭头，然后选择"新建 **规则"。**
1. 在 **"新建规则"** 页上，输入规则的名称，滚动到底部，然后选择"更多 **选项"。**
1. Under **Apply this rule if**， select Any **attachment，** and then select **file extension includes these words.**
1. 在 **"指定单词** 或短语"下的框中，输入您希望应用规则的文件扩展名，例如可以包含宏的文件扩展名。 使用加 (+) 符号一次添加一个。

    通过阅读"防范勒索软件 ["了解有关文件类型的更多信息](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)。

1. 向下滚动查看列表，然后选择"确定 **"。**
1. 在新 **规则页面上** ，选择 **"添加** 条件"，然后选择"执行以下操作 **"下的条件**。
1. 您有很多规则选项可供选择，但本示例中，我们将选择"使用邮件 **通知收件人"。**
1. 输入通知的消息文本，然后选择"**确定"。**
1. 可选：在 **"新建规则**"页上，选择"添加例外"，然后输入规则例外（如来自受信任发件人的邮件）的任何详细信息。
1. 在"新建规则" **页上，选择**"保存"，然后查看所提供的规则摘要信息。