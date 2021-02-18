---
title: 单独的 SharePoint Online 团队网站
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: 了解独立的 SharePoint Online 团队网站，包括其用途、要求和功能。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 056c6f2a463d38dd27b26d484995280dddedf436
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286581"
---
# <a name="isolated-sharepoint-online-team-sites"></a>单独的 SharePoint Online 团队网站

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [适用于 Office 365 计划 1 的 Microsoft Defender](office-365-atp.md)
- SharePoint Online 

 **摘要：** 了解有关单独的 SharePoint Online 团队网站的用法。

SharePoint Online团队网站是快速创建协作空间的简便方法。用户可在 Microsoft Office 365 中的笔记、文档、文章、日历和其他资源协同工作。SharePoint Online 团队网站基于 Microsoft 365 组，它具有一个简化的管理模型，允许与一组私有组成员或整个组织展开开放式协作。默认 SharePoint Online 团队网站允许 Microsoft 365 组的成员邀请其他用户并控制权限设置。

但是，有时需要由组成员身份控制的网站访问权限以及由 SharePoint 管理员管理的 SharePoint Online 权限级别。 我们将其称为隔离站点，此站点与正在协作、查看其内容或管理此站点的一组用户隔离。 可能需要隔离的网站，如下所示：

- 组织内的一个机密项目。

- 对于组织高度敏感或宝贵的知识产权的位置。

- 组织所采取的法律行动的资源或组织受约束的资源。

- 在具有某些重叠的多个组织之间共享 Microsoft 365 订阅，但大多数情况下都作为单独业务实体存在。

下面是单独网站的要求：

- 只有 SharePoint Online 管理员可以执行网站管理，其中包括访问网站和配置自定义权限的组成员身份。

- 网站成员不能邀请其他成员到团队网站。

- 不是单独网站成员的用户不能请求对该网站的访问。当他们尝试访问与该网站相关联的任何 URL 时，将会收到拒绝访问网页的消息。

通过 SharePoint Online 管理员要求进行集中式访问控制和自定义权限的折衷方案是，随着时间的推移，该网站仍然保持独立。例如，当前成员不能以有意或无意的方式在 Microsoft 365 订阅中邀请不是该网站成员的其他用户或为其配置自定义权限。

单独网站可以与其他功能结合使用，例如：

- 信息权限管理，用于确保网站上的资源保持加密，即使在本地下载资源并将其上传到在整个组织中可用的其他站点。

- 数据丢失防护，用于防止用户发送该网站的资源（如文件、电子邮件）。

## <a name="next-steps"></a>后续步骤

若要在试用版订阅中尝试创建单独的 SharePoint Online 团队网站，请参阅[单独的 SharePoint Online 团队网站开发/测试环境](isolated-sharepoint-online-team-site-dev-test-environment.md)中的分步说明。

当准备好在生产中部署单独的 SharePoint Online 团队网站后，请参阅[设计单独的 SharePoint Online 团队网站](design-an-isolated-sharepoint-online-team-site.md)中的分步设计注意事项。

## <a name="related-topics"></a>相关主题

[设计单独的 SharePoint Online 团队网站](design-an-isolated-sharepoint-online-team-site.md)

[管理独立 SharePoint Online 团队网站](manage-an-isolated-sharepoint-online-team-site.md)

[部署独立 SharePoint Online 团队网站](deploy-an-isolated-sharepoint-online-team-site.md)
