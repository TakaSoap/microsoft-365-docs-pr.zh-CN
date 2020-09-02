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
ms.openlocfilehash: 121380cdaaf5d0397d082159ddf6461c0c12cbe1
ms.sourcegitcommit: 4ac96855d7c269a0055ca8943000b762a70ca4ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "47321981"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>存储在 Exchange Online 邮箱中的内容

Exchange Online 中的邮箱主要用于存储与电子邮件相关的项目，如邮件、日历项目、任务和便笺。 但是，由于更多基于云的应用程序还会将其数据存储在用户邮箱中，因此也会更改。 将数据存储在邮箱中的一个优点是，您可以使用内容搜索、核心电子数据展示、高级电子数据展示和数据调查中的搜索工具来查找、查看和导出这些基于云的应用程序中的数据。 其中一些应用程序中的数据存储在非人际邮件中的隐藏文件夹中， (非 IPM) 子树在邮箱中。 来自其他基于云的应用程序的数据可能不会存储 _在邮箱中_ ，但与邮箱 _关联_ ，则会在搜索 (中返回，如果该数据与搜索查询) 相匹配。 无论基于云的数据是存储在用户邮箱中，还是与用户邮箱相关联，在用户打开其邮箱时，电子邮件客户端中的数据通常不可见。

下表列出了使用基于云的邮箱存储或关联数据的应用程序。 该表还介绍了每个应用程序生成的内容类型。

|Microsoft 365 应用程序|说明|
|:---------|:---------|
|Forms|表单和对表单的响应存储在附加到电子邮件的文件中，并存储在创建表单的用户邮箱中的隐藏文件夹中。 在2020年4月之前创建的表单存储为 PDF 文件。 在2020之后创建的表单存储为 JSON 文件。  对表单的响应存储在 CSV 文件中。 当您从 PST 文件的表单中导出内容时，此数据位于使用以下全局唯一标识 (GUID) ： **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**中的名为的子文件夹中的**ApplicationDataRoot**文件夹中。|
|Microsoft 365 组|电子邮件、日历项目、联系人 (人员) 、便笺和任务都存储在与 Microsoft 365 组相关联的邮箱中。|
|Outlook/Exchange Online|电子邮件、日历项目、联系人 (人员) 、便笺和任务都存储在用户的邮箱中。|
|人员|"人员" 应用 (中的联系人与 Outlook) 中可访问的联系人相同，都存储在用户的邮箱中。|
|课程计划|在课程计划中创建的计划存储在创建新计划时设置的相应 Microsoft 365 组的邮箱中。 组邮箱的别名是计划的名称。|
|Skype for Business|Skype for Business 中的对话存储在用户邮箱的 "对话历史记录" 文件夹中。 如果 Skype 会议参与者的邮箱被置于诉讼保留或分配到保留策略，则附加到会议的文件将保留在参与者邮箱中。|
|Sway|Sway 存储为附加到电子邮件的 HTML 文件，并存储在创建 sway 的用户邮箱的隐藏文件夹中。 从 PST 文件中导出 Sway 中的内容时，此数据位于名为且使用以下 GUID) **905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba**的子文件夹中的**ApplicationDataRoot**文件夹中。|
|任务|任务应用 (中的任务与 Outlook) 中可访问的任务相同，它们存储在用户的邮箱中。|
|Teams|属于团队渠道的对话将与团队邮箱相关联。 在团队中作为聊天列表一部分的对话 (也称为 *1 x N 聊天*) 与参与聊天的用户的邮箱相关联。 此外，团队频道中的会议和呼叫的摘要信息与拨入会议或呼叫的用户的邮箱相关联。 因此，在搜索团队内容时，将在 "团队邮箱" 中搜索频道对话中的内容，并在 1 x N 聊天中搜索用户邮箱中的内容。| 
|微软待办|将任务 (调用 *到-* 待办事项中保存在待办事项列表中) 在用户的邮箱中存储。|
|Yammer|Yammer 社区中的对话和评论与 Microsoft 365 组邮箱相关联，以及作者的用户邮箱以及任何命名的收件人 ( @mentioned 或 cc'ed 用户) 。 在 Yammer 社区之外发送的专用邮件存储在参与该私有邮件的用户的邮箱中。|  
||||

> [!NOTE]
> 在此情况下，如果使用电子数据展示和高级电子数据展示事例中的保留将邮箱上的保留设置 () ，则保留不会保留来自表单和 Sway 的内容。 
