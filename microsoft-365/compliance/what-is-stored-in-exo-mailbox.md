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
description: Office 365 中基于云的应用程序生成的数据存储或与用户的 Exchange Online 邮箱相关联。
ms.openlocfilehash: 88cd2bf459ed7a50c06194b22f2ae6a999380d51
ms.sourcegitcommit: 9a4084ce2b80bac883412e0ec956b6c0cc18d0f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2020
ms.locfileid: "42400979"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>存储在 Exchange Online 邮箱中的内容

Exchange Online 中的邮箱主要用于存储与电子邮件相关的项目，如邮件、日历项目、任务和便笺。 但是，随着基于云的 Office 365 的应用程序也会将其数据存储在用户的邮箱中。 将数据存储在邮箱中的一个优点是，您可以使用内容搜索、核心电子数据展示、高级电子数据展示和数据调查中的搜索工具来查找、查看和导出这些基于云的应用程序中的数据。 其中一些应用程序中的数据存储在邮箱中非人际邮件（非 IPM）子树中的隐藏文件夹中。 来自其他基于云的应用程序的数据可能不会存储_在邮箱中_，但与邮箱_相关联_，并且会在搜索中返回（如果该数据与搜索查询相匹配）。 无论基于云的数据是存储在用户邮箱中，还是与用户邮箱相关联，在用户打开其邮箱时，电子邮件客户端中的数据通常不可见。

下表列出了存储或将数据与基于云的邮箱相关联的 Office 365 应用程序。 该表还介绍了每个应用程序生成的内容类型。

|Office 365 应用|说明|
|:---------|:---------|
|Forms|表单（存储为 PDF 文件）和对表单（存储在 CSV 文件中）的响应将附加到电子邮件中，并存储在创建表单的用户邮箱中的隐藏文件夹中。 从 PST 文件中的表单导出内容时，此数据位于名为的子文件夹中的 " **ApplicationDataRoot** " 文件夹中，该文件夹具有以下全局唯一标识（GUID）： **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**。|
|Office 365 组|电子邮件、日历项目、联系人（人员）、便笺和任务存储在与 Office 365 组相关联的邮箱中。|
|Outlook/Exchange Online|电子邮件、日历项目、联系人（人员）、便笺和任务存储在用户的邮箱中。|
|人员|"人员" 应用中的联系人（与 Outlook 中可访问的联系人相同）存储在用户的邮箱中。|
|课程计划|在课程计划中创建的计划存储在创建新计划时设置的相应 Office 365 组的邮箱中。 组邮箱的别名是计划的名称。|
|Skype for Business|Skype for Business 中的对话存储在用户邮箱的 "对话历史记录" 文件夹中。 如果 Skype 会议参与者的邮箱被置于诉讼保留或分配到保留策略，则附加到会议的文件将保留在参与者邮箱中。|
|Sway|Sway 存储为附加到电子邮件的 HTML 文件，并存储在创建 sway 的用户邮箱的隐藏文件夹中。 从 PST 文件中导出 Sway 中的内容时，此数据位于名为 with with the GUID 的子文件夹中的**ApplicationDataRoot**文件夹中） **905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba**。|
|任务|任务应用程序中的任务（与 Outlook 中可访问的任务相同）存储在用户的邮箱中。|
|Teams|属于团队渠道的对话将与团队邮箱相关联。 团队中聊天列表的一部分对话（也称为*1 x N 聊天*）与参与聊天的用户的邮箱相关联。 此外，团队频道中的会议和呼叫的摘要信息与拨入会议或呼叫的用户的邮箱相关联。 因此，在搜索团队内容时，将在 "团队邮箱" 中搜索频道对话中的内容，并在 1 x N 聊天中搜索用户邮箱中的内容。| 
|微软待办|"待办事项" 应用中的任务（*在待办事项列表中调用）* 存储在用户的邮箱中。|
||||

> [!NOTE]
> 在此情况下，如果保留在邮箱上（使用电子数据展示和高级电子数据展示事例中的保留），保留中的内容将不会保留。 
