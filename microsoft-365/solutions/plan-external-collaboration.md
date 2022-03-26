---
title: 规划外部协作
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
localization_priority: Normal
f1.keywords: NOCSH
recommendations: false
description: 规划要用于外部协作Microsoft 365。
ms.openlocfilehash: 56999f3acda0da4f801f3a7ec171c73fe05943a3
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2022
ms.locfileid: "63715985"
---
# <a name="plan-external-collaboration"></a>规划外部协作

Microsoft 365提供了几种用于与组织外部人员协作的选项：

- 1：1 和群组Teams组织外部人员进行聊天
- Teams组织外部人员召开会议
- 与组织外部人员共享单个文件或文件夹
- 团队中的协作，具有频道对话、文件协作和共享应用

本文介绍了第四个选项，即通过频道对话进行组协作、文件协作和共享应用。 

## <a name="terms"></a>Terms

- **Azure AD B2B** 协作 – 允许用户与组织外部人员共享文件、文件夹、网站、组和团队的功能。 这些人员使用目录中的来宾帐户访问共享资源。
- **Azure AD B2B** 直接连接 – 允许用户与其他组织人员共享组织中资源Azure AD的功能。 这些人员通过使用自己的工作或学校帐户访问共享资源。 不会在组织中创建来宾帐户。
- **外部** 参与者 – 组织外部使用自己的身份（而不是目录中的来宾帐户）参与资源（如共享频道）的人。
- **外部组织** – 正在与另一个组织共享资源。
- **来宾** – 组织外部通过登录目录中的来宾帐户来访问共享资源的人。
- **宿主** 组织 – 托管共享资源（如共享频道）的组织。
- **共享频道** – Teams团队外部人员共享的共享频道。 这些人员可以位于组织内部，也可以来自Azure AD组织。
- **共享** 链接 – 具有对用于与他人共享该文件或文件夹的文件或文件夹的权限的链接。 与共享人员可以在组织内部或外部。

## <a name="options-for-collaboration-in-a-team"></a>团队中的协作选项

在团队中与组织外部人员协作时，有两个选项可以让他们访问与你共享的资源。

**来宾共享**

来宾共享Azure AD B2B 协作，以便通过为每个人在 Azure AD 中添加来宾帐户，与组织外部人员共享和协作。 来宾帐户可用于以下各项：

- 团队、网站SharePoint组中的来宾Microsoft 365成员身份
- 单个文件和文件夹共享

团队中的来宾具有与常规团队成员类似的功能。

**共享频道中的外部参与者**

外部参与者通过使用自己的共享或标识来访问Azure AD Microsoft 365资源。 这可以通过 B2B Azure AD由两个组织配置的组织关系直接连接来启用。 来宾帐户不在此关系中使用。

与来宾共享相比，共享频道中的外部参与者的主要优点是，组织外部人员可以在 Teams 中与用户进行协作，而无需更改其用户上下文。 使用来宾帐户时，用户必须使用Teams或学校帐户注销并再次使用来宾帐户登录。 或者，他们可以在专用浏览器会话中Teams一个单独的应用程序副本。 组织之间的这种切换需要一些时间，并且可能导致用户在退出给定组织时错过重要通信。

使用共享频道，用户可以保持登录到其组织，并访问与其他组织共享的频道。 来自其他组织的共享频道与Teams团队和频道一起提供。 无需切换组织。

## <a name="feature-comparison"></a>功能比较

下表介绍了可用体验，具体取决于所使用的帐户类型。

|功能|组织 (用户) |来宾 (Azure AD协作) |外部参与者 (Azure AD直接连接) |
|:-----|:-----|:------|:-------|
|团队访问|Y|Y|N|
|共享频道访问|Y|N|Y|
|通过文件共享链接的权限|Y|Y|N|
|使用共享频道|Y|N|Y|
|使用私人频道|Y|Y|N|
|目录中的帐户|Y|Y|N|
|访问审查|Y|Y|Y|
            
## <a name="planning-considerations"></a>规划注意事项

大多数组织都将使用与外部参与者的来宾共享和共享通道。 

默认情况下，来宾共享在 Azure AD、Microsoft 365 (Teams、Microsoft 365 组和 SharePoint) 中启用。 这样，用户即可邀请来宾加入团队和网站，并与他们共享文件，而无需向 IT 寻求帮助。

如果：
- 你要邀请组织外部人员加入团队，而不是个别频道
- 您希望与组织外部不在频道中的人员共享频道中的文件或文件夹
- 您希望与没有工作或学校帐户的组织外部人员进行协作。

尽管 Teams 中默认启用共享频道，但与共享频道的外部协作要求 Azure AD 管理员在您的组织和要共享的其他组织之间设置跨租户访问。 每个组织还必须在最终设置跨租户访问。

如果计划与其他组织使用共享通道，可以在自助服务模型和请求模型之间选择。

- 自助服务 – 可以配置跨租户访问，以允许对所有其他组织进行入站和Azure AD访问。 或者，可以阻止不希望用户共享的组织列表，使所有其他组织都可用。 这样，用户即可邀请组织外部人员参与共享频道，而无需联系支持人员或 IT 部门。
- 按请求 – 您可以为要允许共享频道的每个组织配置跨租户访问。 选择此模型时，必须记录用户业务流程以请求与另一个组织的跨租户访问。

## <a name="compliance-in-shared-channels"></a>共享频道中的合规性

共享频道与合规性Microsoft 365集成。

##### <a name="communications-compliance"></a>通信合规性

管理员可以设置策略来监视频道中所有用户的内容。 通信合规性策略涵盖频道中所有消息内容，包括 [共享频道](/microsoft-365/compliance/communication-compliance)。 共享频道继承主机组织的策略。

##### <a name="conditional-access"></a>条件访问

宿主组织的条件 [访问策略](/azure/active-directory/conditional-access/overview) 应用于外部参与者，包括 B2B 直接连接用户。 不使用外部组织的策略。 共享通道支持以下类型的条件访问策略：

- 范围为所有来宾用户、外部参与者、SharePoint Online 云应用的策略
- 授予需要 MFA、兼容设备或已加入设备的混合Azure AD访问控制。 

基于 IP 的策略在文件级别SharePoint支持。 因此，外部参与者可能会从受限位置访问共享通道，但在尝试打开文件时将阻止。

##### <a name="data-loss-prevention-dlp"></a>数据丢失防护 (DLP)

管理员可以将 [DLP 策略应用于](/microsoft-365/compliance/dlp-policy-design) 所有频道（包括共享频道）都继承该策略的团队。 共享频道继承主机组织的策略。

##### <a name="retention-policy"></a>保留策略

管理员可以在团队 [中应用保留](/microsoft-365/compliance/retention) 策略，所有频道（包括共享频道）都继承保留策略。 共享频道继承父团队的策略。

##### <a name="sensitivity-labels"></a>敏感度标签

[主机组织中](/microsoft-365/compliance/sensitivity-labels) 可用的敏感度标签是可应用于共享频道网站中的文档的唯一标签。 外部参与者无法打开通过敏感度标签加密的文件。 不使用自动标记。

共享频道及其关联的SharePoint网站从父团队继承标签。

##### <a name="information-barriers"></a>信息屏障

不允许根据信息屏障策略 [进行通信的用户不能](/microsoftteams/information-barriers-in-teams) 是共享频道的一部分。 信息屏障策略仅对宿主组织的用户有效。 如果用户是另一个组织共享渠道中的外部参与者，则信息屏障策略不适用。

##### <a name="ediscovery"></a>电子数据展示

管理员可以对频道中的所有用户执行搜索。 所有通道（包括共享通道）都是可发现的。 无论谁添加了数据，频道中所有邮件数据都由合规性管理员发现。

##### <a name="legal-hold"></a>合法持有

管理员可以将不是团队一部分的主机组织的仅频道成员放在保留状态。 他们还可以 [将整个团队放在保留状态](/MicrosoftTeams/legal-hold)。 管理员无法将外部参与者放在保留状态。

##### <a name="audit-logs"></a>审核日志

对现有审核事件 [执行的所有操作](/microsoft-365/compliance/detailed-properties-in-the-office-365-audit-log) 在共享频道中进行审核。


## <a name="related-topics"></a>相关主题

[文件协作简介Microsoft 365](/sharepoint/intro-to-file-collaboration)

[规划与 SharePoint 中的文件Microsoft 365](/sharepoint/deploy-file-collaboration)
