---
title: 主题中Microsoft Viva的角色
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
ms.localizationpriority: medium
description: 在 Viva 主题中了解用户角色。
ms.openlocfilehash: bf245cfc41fa3ad08af74dd2f2efbb8c0ddfef37
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60205793"
---
# <a name="roles-in-microsoft-viva-topics"></a>主题中Microsoft Viva的角色

当您在环境环境中使用 Viva Microsoft 365，您的用户可以具有以下角色：

- 主题查看者
- 主题参与者
- 知识经理
- 知识管理员

## <a name="topic-viewer"></a>主题查看者

主题查看者是组织中可以查看其 SharePoint 新式网站中突出显示的主题的用户，Microsoft 搜索 SharePoint Office.com 和主题中心查看主题。 他们可以在主题页面上查看有关主题的更多详细信息。 

若要使主题突出显示及其主题页面对主题查看者可见，用户必须：

- [由管理员为其分配 Viva 主题](./set-up-topic-experiences.md#assign-licenses)Microsoft 365许可证。
- 允许查看主题。 此任务由知识管理员在 Microsoft 365 管理中心 中的 Viva 主题设置页中Microsoft 365 管理中心。

## <a name="topic-contributors"></a>主题参与者

主题参与者是组织中不仅具有主题查看者权限，而且可编辑现有主题或创建新主题的用户。 它们在手动"选择"AI 或手动提供的信息主题页面中的信息 (或手动提供的信息) 以确保其质量。

具有主题参与者权限的用户将在主题页面上看到"编辑"按钮，该按钮允许他们更新和发布主题。

主题参与者也可以通过其主题中心创建和发布新主题。

若要创建和编辑主题，用户必须：

- [由管理员为其分配 Viva 主题](./set-up-topic-experiences.md#assign-licenses)Microsoft 365许可证。
- [分配有创建和编辑主题的权限](./topic-experiences-user-permissions.md)。 此任务由知识管理员在 Microsoft 365 管理中心 中的 Viva 主题设置页中Microsoft 365 管理中心。

## <a name="knowledge-managers"></a>知识经理

知识经理是管理组织中主题的用户。  主题管理通过主题中心的" **管理** 主题"页完成，并且仅对知识管理人员可见。

在" **管理主题"** 页上，知识管理人员可以执行以下任务：

- 查看 AI 建议的主题。
- 查看主题以确认它们有效。
- 删除不希望用户看到的主题。

此外，知识经理可以编辑现有主题或创建新主题。

若要管理主题，用户必须：

- [由管理员为其分配 Viva 主题](./set-up-topic-experiences.md#assign-licenses)Microsoft 365许可证。
- [分配有管理主题权限) 。](./topic-experiences-user-permissions.md) 此任务由知识管理员在 Microsoft 365 管理中心 中的 Viva 主题设置页中Microsoft 365 管理中心。

对业务有全面了解的用户可能是担任知识经理角色的良好候选者。 这些人员不仅可能知道主题是否有效，而且还可能了解公司内与这些主题相关的人员。

## <a name="knowledge-admins"></a>知识管理员

知识管理员是在你的环境中设置和配置 Viva 主题Microsoft 365管理员。 他们还会在设置完成后管理 Viva 主题设置。 知识管理员角色需要你成为全局Microsoft 365管理员或SharePoint管理员，因为设置和管理在 Microsoft 365 管理中心。
在设置过程中，知识管理员可以将 Viva 主题配置为：

- 选择将爬网哪些 SharePoint 网站来识别主题。
- 选择哪些许可用户可以查看主题（主题查看者）。
- 选择要排除而不识别的主题。
- 选择哪些许可用户可以创建和编辑主题（主题参与者）。
- 选择哪些许可用户可以管理主题（知识经理）。
- 将主题中心命名。

知识经理需要能与组织内的所有 Viva Topics 利益干系人协调以了解如何对其进行配置。 例如，如果新项目包含敏感信息，则需要通知知识经理，以便他们可以确保不针对主题对 SharePoint 网站进行爬网，或者需要排除特定主题名称。
