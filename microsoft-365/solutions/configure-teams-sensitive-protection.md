---
title: 配置具有敏感数据保护的团队
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
recommendations: false
description: 了解如何部署具有敏感数据保护的团队。
ms.openlocfilehash: 20178cf1238a6dd329db0b84da5b0054d23a519845c967d66dc502f96eee4fb4
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53888495"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a>配置具有敏感数据保护的团队

在本文中，我们将了解如何针对敏感级别的保护设置团队。 在执行本文中的步骤之前，请确保已完成[部署具有基线保护的团队](configure-teams-baseline-protection.md)中的步骤。 敏感级别提供了以下超出基线层级的额外保护：

- 团队的敏感度标签，可用于打开或关闭来宾共享，并仅允许未托管设备通过 Web 访问 SharePoint 内容。此标签还可用于对文件进行分类。
- 限制性更强的默认共享链接类型
- 只有团队所有者可以创建专用频道。

## <a name="video-demonstration"></a>视频演示

观看此视频，演练本文中介绍的过程。
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4NMS6]

## <a name="guest-sharing"></a>来宾共享

根据业务性质，你可能希望也可能不希望为包含敏感数据的团队启用来宾共享。 如果确实计划与团队中的组织外部人员进行协作，则建议启用来宾共享。 Microsoft 365 包括许多安全性和合规性功能，可帮助你安全地共享敏感内容。 这通常比直接通过电子邮件向组织外部的人员发送内容更安全。

有关与来宾安全共享的详细信息，请参阅以下资源：

- [在与组织外人员共享文件时限制意外公开信息](./share-limit-accidental-exposure.md)
- [创建安全的来宾共享环境](./create-secure-guest-sharing-environment.md)

为允许或阻止来宾共享，我们将团队的敏感度标签与关联 SharePoint 网站的网站级别共享控件结合使用，这两者将在后面讨论。

## <a name="sensitivity-labels"></a>敏感度标签

对于敏感级别的保护，我们将使用敏感度标签对团队进行分类。 此标签还可用于分类此团队或其他团队，或者其他文件位置（如 SharePoint 或 OneDrive）中的单个文件。 

首先，必须为 Teams 启用敏感度标签。 有关详细信息，请参阅[使用敏感度标签保护 Microsoft Teams、Office 365 组和 SharePoint 网站中的内容](../compliance/sensitivity-labels-teams-groups-sites.md)。

如果已在组织中部署了敏感度标签，请考虑此标签与总体标签策略的匹配情况。 可根据需要更改名称或设置以满足组织的需求。

为 Teams 启用灵敏度标签后，下一步是创建标签。

创建敏感度标签
1. 打开 [Microsoft 365 合规中心](https://compliance.microsoft.com)。
2. 在“**解决方案**”下，单击“**信息保护**”。
3. 单击“**创建标签**”。
4. 为标签命名。 建议使用“**敏感**”，但如果该名称已在使用，则可以选择其他名称。
5. 添加显示名称和说明，然后单击“**下一步**”。
6. 在“**定义此标签页的搜索范围**”中，选择“**文件和电子邮件**”和“**组和站点**”，然后单击“**下一步**”。
7. 在“**选择文件和电子邮件的防护设置**”页面中，单击“**下一步**”。
8. 在“*文件和电子邮件自动标记*”页面中，单击“**下一步**”。
9. 在“**定义组和站点的防护设置**”页面中，选择“**隐私和外部用户访问设置**”和“**设备权限和外部共享设置**”，然后单击“**下一步**”。
10. 在“**定义隐私和外部用户权限设置**”页面中，选择“**隐私**”下的“**私人**”选项。
11. 如果你想允许来宾访问，选择“**外部用户权限**”下的“**让 Microsoft 365 组所有者添加组织外的人员为来宾**”。
12. 单击“**下一步**”。
13. 在“**定义外部共享和设备权限设置**”页面中，选择“**从标记的 SharePoint 站点控制外部共享**”。
14. 如果当前允许来宾访问，在“**无法共享的内容**”下选择“**新的和当前来宾**”；如果不允许，则选择“**仅组织中的人员**”。
15. 在“**非托管的设备的访问**”下，选择“**允许仅限于 Web 的访问**”。
16. 单击“**下一步**”。
17. 在“**数据库列自动标记**”页面中，单击“**下一步**”。
18. 单击“**创建标签**”，然后单击“**完成**”。

创建标签后，需要将其发布到使用它的用户。 对于敏感保护，我们将对所有用户提供该标签。 在 Microsoft 365 合规中心的“**信息保护**”页面的“**标签策略**”选项卡上发布标签。 如果你拥有适用于所有用户的现有策略，请将此标签添加到该策略。 如果需要创建新策略，请参阅[通过创建标签策略来发布灵敏度标签](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)。

## <a name="create-a-team"></a>创建团队

对敏感方案的进一步配置在与团队相关联的 SharePoint 网站中完成，因此下一步是创建团队。

针对敏感信息创建团队
1. 在 Teams 中，单击应用程序左侧的“**团队**”，然后在团队列表底部单击“**加入或创建团队**”。
2. 点击“**创建团队**”（第一张卡片，左上角）。
3. 选择“**从头开始构建团队**”。
4. 在“**灵敏度**”列表中，选择刚才创建的“**敏感**”标签。
5. 在“**隐私**”下，单击“**专用**”。
6. 为该团队键入一个名称，然后单击“**创建**”。
7. 将用户添加到团队，然后单击“**关闭**”。

## <a name="private-channel-settings"></a>专用频道设置

在此层级，仅限团队所有者创建专用频道。

限制专用频道创建
1. 在团队中，单击“**更多选项**”，然后单击“**管理团队**”。
2. 在“**设置**”选项卡上，展开“**成员权限**”。
3. 清除“**允许成员创建专用频道**”复选框。

还可以使用“[团队策略](/MicrosoftTeams/teams-policies)”来控制谁可以创建专用频道。

## <a name="sharepoint-settings"></a>SharePoint 设置

每次使用敏感标签创建新团队时，都需要在 SharePoint 中执行两步操作：

- 更新 SharePoint 管理中心中网站的来宾共享设置，将默认共享链接更新为“*特定人员*”。
- 更新网站本身的网站共享设置，防止成员共享网站。

### <a name="site-default-sharing-link-settings"></a>网站默认共享链接设置

更新网站默认共享链接类型

1. 打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。
2. 在“**站点**”下，单击“**活动站点**”。
3. 单击与团队关联的网站。
4. 在“**策略**”选项卡的“**外部共享**”下，单击“**编辑**”。
5. 在“默认共享链接类型”下，清除“**与组织级别设置相同**”复选框，然后选择“**特定人员(仅用户指定的人员)**”。
6. 单击“**保存**”。

若要将脚本作为团队创建过程的一部分进行编写，可使用 [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) 和 `-DefaultSharingLinkType Direct` 参数，将默认共享链接更改为 *特定人员*。

#### <a name="private-channels"></a>专用频道

如果向团队添加私人频道，则每个私人频道都会使用默认共享设置创建新的 SharePoint 网站。 这些网站在 SharePoint 管理中心中不可见，因此必须使用 Set-SPOSite PowerShell cmdlet 来更新来宾共享设置。

### <a name="site-sharing-settings"></a>网站共享设置

为了帮助确保不与非团队成员共享 SharePoint 网站，我们限制为仅允许所有者进行此类共享。

配置仅限所有者的网站共享
1. 在 Teams 中，导航至要更新团队的“**常规**”标签。
2. 在团队的工具栏中，单击“文件”。
3. 单击省略号，然后单击“在 SharePoint 中打开”。
4. 在基础 SharePoint 网站的工具栏中，依次单击设置图标和“网站权限”。
5. 在“**网站权限**”窗格的“**网站共享**”下方，单击“**更改成员共享方式**”。
6. 在“**共享权限**”下，选择选择“**网站所有者和成员以及拥有编辑权限的人员可共享文件和文件夹，但只有网站所有者才可共享网站**”，然后单击“**保存**”。


## <a name="see-also"></a>另请参阅

[创建和配置敏感度标签及其策略](../compliance/create-sensitivity-labels.md)
