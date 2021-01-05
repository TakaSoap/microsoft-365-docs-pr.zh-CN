---
title: 存储在 Exchange Online 邮箱中的内容
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 中基于云的应用生成的数据存储或与用户的 Exchange Online 邮箱相关联。
ms.openlocfilehash: f7bd5b00e8219f382078eb2d4f8aa25bd4c54d69
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750743"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>存储在 Exchange Online 邮箱中的内容

Exchange Online 中的邮箱主要用于存储与电子邮件相关的项目，如邮件、日历项目、任务和便笺。 但是，随着更多的基于云的应用也将数据存储在用户邮箱中，这一点会发生变化。 在邮箱中存储数据的一个优点是，您可以使用内容搜索、核心电子数据展示、高级电子数据展示中的搜索工具从这些基于云的应用中查找、查看和导出数据。 其中一些应用的数据存储在位于非安全邮件中的隐藏文件夹中 (非 IPM) 位于邮箱的子树中。 来自其他基于云的应用的数据可能未存储在邮箱中，但与邮箱关联，如果数据与搜索查询查询匹配，则此数据将在搜索 (中返回) 。 无论基于云的数据存储在用户邮箱中还是与用户邮箱相关联，当用户打开其邮箱时，数据在电子邮件客户端中通常不可见。

下表列出了存储数据或将数据与基于云的邮箱关联的应用程序。 该表还介绍了每个应用生成的内容类型。

|Microsoft 365 应用|说明|
|:---------|:---------|
|Forms|窗体和窗体响应存储在附加到电子邮件的文件中，并存储在创建表单的用户邮箱的隐藏文件夹中。 在 2020 年 4 月之前创建的表单存储为 PDF 文件。 在 2020 之后创建的表单存储为 JSON 文件。  对表单的响应存储在 CSV 文件中。 当您从 PST 文件中导出表单中的内容时，此数据位于 **ApplicationDataRoot** 文件夹中的子文件夹中，该子文件夹使用以下全局唯一标识的 (GUID) ： **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87.**|
|Microsoft 365 组|电子邮件、日历项目、联系人 (联系人) 联系人、便笺和任务存储在与 Microsoft 365 组关联的邮箱中。|
|Outlook/Exchange Online|电子邮件、日历项目、 (联系人) 联系人、便笺和任务都存储在用户的邮箱中。|
|人员|"人 (联系人"应用中的联系人与 Outlook) 中可访问的联系人存储在用户邮箱中。|
|课程计划|在课堂计划中创建的计划存储在创建新计划时预配的相应 Microsoft 365 组的邮箱中。 组邮箱的别名是计划的名称。|
|Skype for Business|Skype for Business 中的对话存储在用户邮箱的对话历史记录文件夹中。 如果 Skype 会议参与者的邮箱置于诉讼保留或分配给保留策略，则附加到会议的文件将保留在参与者邮箱中。|
|Sway|Sway 存储为附加到电子邮件的 HTML 文件，并存储在创建 sway 的用户邮箱的隐藏文件夹中。 在 PST 文件中从 Sway 导出内容时，此数据位于名为以下 GUID) **905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba** 的子文件夹中 **的 ApplicationDataRoot** 文件夹中。|
|Tasks|"任务" (中的任务与 Outlook 应用程序中可以访问的任务相同) 存储在用户邮箱中。|
|Teams|属于 Teams 频道的对话与 Teams 邮箱相关联。 属于 Teams 聊天列表中的对话 (也称为 *1 x N* 聊天) 与参与聊天的用户的邮箱相关联。 此外，Teams 频道中会议和呼叫的摘要信息与拨入会议或呼叫的用户的邮箱相关联。 因此，在搜索 Teams 内容时，你将在 Teams 邮箱中搜索频道对话中的内容，在用户邮箱中搜索 1 x N 聊天中的内容。| 
|微软待办|任务 (，保存在用户邮箱) 的To-Do列表中。|
|Yammer|Yammer 社区中的对话和评论与 Microsoft 365 组邮箱、作者的用户邮箱以及任何已命名的收件人 (@mentioned 或 cc'ed users) 。 在 Yammer 社区外部发送的私有邮件存储在参与该私人邮件的用户的邮箱中。|  
||||

> [!NOTE]
> 目前，如果在电子数据展示和高级电子数据展示事例) 中通过使用保留将邮箱 (置于保留状态，则保留不会保留来自表单和 Sway 的内容。 
