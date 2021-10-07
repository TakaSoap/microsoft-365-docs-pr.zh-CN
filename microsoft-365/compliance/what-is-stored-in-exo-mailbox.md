---
title: 存储在邮箱Exchange Online内容
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ''
description: 由基于云的应用在 Microsoft 365 中生成的内容将存储或与用户的邮箱Exchange Online关联。 可以使用 Microsoft 电子数据展示工具搜索此内容。
ms.openlocfilehash: f7db327d21928df925bfd6451226ab96782d715b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60198561"
---
# <a name="content-stored-in-exchange-online-mailboxes-for-ediscovery"></a>存储在电子数据Exchange Online邮箱中的内容

邮箱Exchange Online主要用于存储与电子邮件相关的项目，如邮件、日历项目、任务和便笺。 但是，随着更多基于云的应用也将数据存储在用户邮箱中，这一点会发生变化。 在邮箱中存储数据的一个优点是，您可以使用内容搜索、核心电子数据展示和 Advanced eDiscovery 中的搜索工具从这些基于云的应用中查找、查看和导出数据。 其中一些应用的数据存储在非邮件的隐藏文件夹中 (非 IPM) 位于邮箱的子树中。 来自其他基于云的应用的数据可能未存储在邮箱中，但与邮箱关联，如果数据与搜索查询匹配 (将在搜索) 。 无论基于云的数据存储在用户邮箱中还是与用户邮箱相关联，当用户打开其邮箱时，数据在电子邮件客户端中通常不可见。

下表列出了存储数据或将数据与基于云的邮箱关联的应用程序。 该表还介绍了每个应用生成的内容类型。

<br>

****

|Microsoft 365应用|说明|
|---|---|
|表单<sup>*</sup>|窗体和窗体响应存储在附加到电子邮件的文件中，并存储在创建窗体的用户邮箱的隐藏文件夹中。 在 2020 年 4 月之前创建的表单存储为 PDF 文件。 在 2020 之后创建的表单存储为 JSON 文件。 对表单的响应存储在 CSV 文件中。 在 PST 文件中从表单导出内容时，此数据位于名为 的子文件夹中的 **ApplicationDataRoot** 文件夹中，该子文件夹由以下全局唯一标识的 (GUID) ： **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**.|
|Microsoft 365 组|电子邮件、日历项目、联系人 (联系人) 联系人、便笺和任务存储在与组关联的Microsoft 365邮箱中。|
|Outlook/Exchange Online|电子邮件、日历项目、联系人 (联系人) 联系人、便笺和任务存储在用户的邮箱中。|
|人员|"人 (应用中的联系人与用户邮箱中可访问的联系人Outlook) 存储在用户邮箱中。|
|课程计划|在课堂计划中创建的计划存储在相应组Microsoft 365组（在新建计划时设置）的邮箱中。 组邮箱的别名是计划的名称。|
|Skype for Business|用户Skype for Business对话存储在用户邮箱的对话历史记录文件夹中。 如果会议参与者的邮箱Skype诉讼保留或分配给保留策略，则附加到会议的文件将保留在参与者邮箱中。|
|Sway<sup>*</sup>|Sway 存储为 HTML 文件，该文件附加到电子邮件，并存储在创建 sway 的用户邮箱中的隐藏文件夹中。 在 PST 文件中从 Sway 导出内容时，此数据位于名为 的子文件夹中的 **ApplicationDataRoot** 文件夹中，该子文件夹具有以下 **GUID：905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba**。|
|Tasks|"任务" (中的任务与用户邮箱中可访问的任务Outlook) 任务存储在用户邮箱中。|
|Teams|属于邮箱频道Teams对话与邮箱Teams关联。 属于聊天列表中的对话Teams (*也称为 1 x N* 聊天) 与参与聊天的用户的邮箱相关联。 此外，Teams频道中的会议和呼叫的摘要信息与拨入会议或呼叫的用户的邮箱相关联。 因此，在搜索Teams内容时，您将在 Teams 邮箱中搜索频道对话中的内容，在用户邮箱中搜索 1 x N 聊天中的内容。|
|微软待办|任务 (*个称为"to-dos"* 的任务，它们保存在) 应用程序To-Do中存储于用户的邮箱中。|
|Yammer|Yammer 社区中的对话和评论与 Microsoft 365 组邮箱、作者的用户邮箱以及任何命名的收件人（ (@ 提及或抄送用户) ）。 在组织社区Yammer发送的私人邮件存储在参与该私人邮件的用户的邮箱中。|
|

> [!NOTE]
> <sup>*</sup>目前，如果使用核心电子数据展示或 Advanced eDiscovery 事例) 中的保留将邮箱 (置于保留状态，此应用的内容将不会被保留。
