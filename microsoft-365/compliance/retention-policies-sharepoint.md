---
title: 了解 SharePoint 和 OneDrive 的保留策略
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 了解适用于 SharePoint 和 OneDrive 的保留策略。
ms.openlocfilehash: e7a265d39b3cca2ffb9c403cf2c87f287a9325b2
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016243"
---
# <a name="learn-about-retention-policies-for-sharepoint-and-onedrive"></a>了解 SharePoint 和 OneDrive 的保留策略

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

本文中的信息是对[了解保留策略](retention-policies.md)的补充，因为它包含特定于 SharePoint 和 OneDrive 的信息。

## <a name="how-a-retention-policy-works-with-sharepoint-and-onedrive"></a>保留策略如何与 SharePoint 和 OneDrive 一起工作

保留策略在网站集级别进行应用。 在保留策略中添加 SharePoint 网站集或 OneDrive 帐户后，便会创建保存保留库（若尚不存在）。 你可在网站集的最顶级网站中的“**网站内容**”上查看此库。 大多数用户都无法查看保留库，因为此库仅对网站集管理员可见。
  
如果用户尝试更改或删除受保留策略限制的网站中的内容，则策略首先会检查自应用策略后该内容是否发生更改。 如果这是应用保留策略后的首次更改，则保留策略会将内容复制到保留库中，然后允许用户更改或删除原始内容。 网站集上的所有内容都可以复制到保留库中，即使内容与保留策略使用的查询不匹配。
  
计时器作业会定期清理保存保留库。 此作业会定期运行，并将保存保留库中的所有内容与网站上的保留策略使用的所有查询进行比较。 早于其配置的保留期的内容将从保存保留库和原始位置（如果仍在该位置）中删除。 此计时器作业每 7 天运行一次，这意味着删除内容可能需要长达 7 天的时间。
  
此行为适用于应用保留策略时存在的内容。 此外，对于在保留策略中添加网站集后在网站集中创建或添加的所有新内容都会在删除后保留。 然而，新内容不会在第一次编辑时就复制到保留库，只有在删除时才会这样做。 若要保留文件的所有版本，必须启用[版本控制](#how-a-retention-policy-works-with-document-versions-in-a-site-collection)。
  
如果用户尝试删除受保留策略约束的库、列表、文件夹或网站，将收到错误提示。 如果用户首次移动或删除文件夹中受该策略约束的任何文件，可删除一个文件夹。 另外，在此阶段会创建保存保留库，而不是在创建保留策略时创建。 这意味着，若要测试策略，首先必须编辑或删除网站中受保留策略约束的文档，然后转到保存保留库来查看保留的副本。
  
将保留策略分配给 OneDrive 帐户或 SharePoint 网站后，内容路径取决于保留策略是“保留后删除”、“仅保留”还是“仅删除”。

如果保留策略为“保留后删除”：

![SharePoint 和 OneDrive 中的内容生命周期关系图](../media/Retention_Diagram_of_retention_flow_in_sites.png)
  
1. **如果内容在保持期内遭修改或删除**：则会在保留库中创建在分配保留策略时存在的原始内容的副本。 计时器作业可识别保留期限已过期的项目。 这些项目会被移到第二阶段回收站中，并在 93 天后永久删除。 第二阶段回收站对最终用户不可见（仅第一阶段回收站可见），但网站集管理员可以在其中查看和还原内容。

    > [!NOTE]
    > 为了防止意外的数据丢失，不再从保留库中永久删除内容。 相反，只从回收站中永久删除内容，因此保留库中的所有内容现在都要移到第二阶段回收站。
    
2. **如果在保留期限内未修改或删除内容**，则计时器作业会在保留期限结束后将此内容移到第一阶段回收站。 如果用户在第一阶段回收站中删除了该内容或清空了此回收站（也称为清除），则文档会被移到第二阶段回收站。 在第一阶段和第二阶段回收站中的停留时间都计入 93 天保持期。93 天后，无论文档是位于第一阶段回收站中，还是位于第二阶段回收站中，都会从驻留位置永久删除。 回收站未被编入索引，因此无法进行搜索。 因此，电子数据展示搜索无法找到任何要在其上保留的回收站内容。

如果保留策略为“仅保留”或“仅删除”，内容路径在“保留后删除”策略的基础上有所变化：

#### <a name="content-paths-for-retain-only-retention-policy"></a>“仅保留”保留策略的内容路径

1. **如果有人在保持期内修改或删除内容**：则会在保留库中创建原始文档的副本，并保留到保持期结束，然后保留库中的副本会移到第二阶段回收站中，并在 93 天后永久删除。

2. **如果内容在保持期内未遭修改或删除**：保持期前后无变化；文档仍保留在它的原始位置上。

#### <a name="content-paths-for-delete-only-retention-policy"></a>“仅删除”保留策略的内容路径

1. **如果有人在配置的期限内删除内容**：文档会移到第一阶段回收站中。 如果用户从此回收站中删除文档或清空此回收站，文档就会移到第二阶段回收站中。 在第一阶段和第二阶段回收站中的停留时间都计入 93 天保持期。93 天后，无论文档是位于第一阶段回收站中，还是位于第二阶段回收站中，都会从驻留位置永久删除。 如果有人在配置的期限内修改内容，内容就会在配置的期限到期后遵循相同的删除路径。

2. **如果内容在配置的期限内未遭删除**：在保留策略中配置的期限结束时，文档会移到第一阶段回收站中。 如果用户从此回收站中删除文档或清空此回收站（亦称为“清除”），文档就会移到第二阶段回收站中。 在第一阶段和第二阶段回收站中的停留时间都计入 93 天保持期。93 天后，无论文档是位于第一阶段回收站中，还是位于第二阶段回收站中，都会从驻留位置永久删除。 回收站未被编入索引，因此无法进行搜索。 因此，电子数据展示搜索无法找到任何要在其上保留的回收站内容。
    
## <a name="how-a-retention-policy-works-with-document-versions-in-a-site-collection"></a>保留策略如何处理网站集中的文档版本

版本控制是 SharePoint 和 OneDrive 中所有文档库的一项功能。 默认情况下，版本控制至少保留 500 个主要版本，但可以提高此限制。 有关详细信息，请参阅[为列表或库启用和配置版本控制](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37)。
  
“仅保留”策略将保留 SharePoint 网站集或 OneDrive 帐户中文档的所有版本。 当受保留或仅保留策略约束的文档被首次编辑时，都会将原始文档的一个版本复制到保存保留库中。 当受保留或仅保留策略约束的文档遭删除时，如果版本控制已启用，所有版本都会复制到保存保留库中。 在保存保留库中，文档的每个版本都以单独项目的形式存在，并具有自己的保留期：
  
- If the retention policy is based on when the content was created, each version has the same expiration date as the original document. The original document and its versions all expire at the same time.
    
- If the retention policy is based on when the content was last modified, each version has its own expiration date based on when the original document was modified to create that version. The original documents and its versions expire independently of each other.

> [!NOTE]
> 电子数据展示工具无法用于搜索 SharePoint 和 OneDrive 文档的保留版本。

## <a name="when-a-user-leaves-the-organization"></a>如果某用户离开组织 

**SharePoint**：

如果某用户离开组织，此用户创建的任何内容都不会受到影响，因为 SharePoint 被视为协作环境，与用户的邮箱或 OneDrive 帐户不同。

**OneDrive**：

如果某用户离开组织，任何受保留策略约束或包含保留标签的文件都会在策略或标签有效期间保留。 在此期间，所有共享访问继续有效。 在保留期到期后，内容会移到网站集回收站，且不可供除管理员之外的其他任何人访问。如果文档被保留策略标记为记录，那么它在保留期到期前不会遭到删除，之后将永久删除。 

## <a name="how-to-configure-a-retention-policy-for-sharepoint-and-onedrive"></a>如何配置 SharePoint 和 OneDrive 的保留策略

按照[创建和配置保留策略](create-retention-policies.md)以及向导的**选择位置**页面的说明，选择以下选项之一：

- **仅将策略应用于 Exchange 电子邮件、公用文件夹、Office 365 组、OneDrive 和 SharePoint 文档中的内容**

- **让我选择特定位置** > **SharePoint 网站**、**OneDrive 帐户**和 **Office 365 组**。

选择 **SharePoint 网站**位置时，保留策略可以保留 SharePoint 通信网站、未通过 Office 365 组连接的团队网站以及经典网站中的内容。 因为此选项不支持通过 Office 365 组连接的团队网站，所以请改用“**Office 365 组**”位置，该位置适用于该组的邮箱、站点和文件中的内容。 

如果为 SharePoint 网站指定位置，无需网站访问权限，且在“编辑位置”**** 页上指定 URL 时不会进行任何验证。 不过，必须将网站编入索引，系统会检查你指定的网站是否在向导结束时存在。 

如果此检查失败，你会看到一条消息，指明无法验证你所输入的 URL，且只有在验证检查通过后，向导才会创建保留策略。 如果你看到此消息，请返回到向导，以更改 URL 或删除网站。
