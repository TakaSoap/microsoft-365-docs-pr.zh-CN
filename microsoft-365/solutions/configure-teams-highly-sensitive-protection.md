---
title: 配置具有高度敏感数据保护的团队
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
description: 了解如何部署具有高度敏感数据保护的团队。
ms.openlocfilehash: f044dd672d52db4100fcb4cfec2519a8605c7be8
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002597"
---
# <a name="configure-teams-with-protection-for-highly-sensitive-data"></a>配置具有高度敏感数据保护的团队

在本文中，我们将了解如何针对高度敏感级别的保护设置团队。 在执行本文中的步骤之前，请确保已完成[部署具有基线保护的团队](configure-teams-baseline-protection.md)中的步骤。

对于这一层级的保护，我们创建了敏感度标签，可在组织中使用此敏感度标签来处理高度敏感的团队和文件。 只有组织成员和指定来宾才能解密使用此标签的文件。 如果需要进一步的隔离权限，使只有指定团队成员才能解密文件，参见[部署具有安全隔离的团队](secure-teams-security-isolation.md)。

高度敏感级别提供了以下超出基线层级的额外保护：

- 团队的敏感度标签，可用于打开或关闭来宾共享，并仅允许未托管设备通过 Web 访问 SharePoint 内容。 此标签还可用于对文件进行分类和解密。
- 限制性更强的默认共享链接类型
- 只有团队所有者可以创建专用频道。
- 关联 SharePoint 网站的访问请求被关闭。

## <a name="guest-sharing"></a>来宾共享

根据业务性质，你可能希望也可能不希望为包含高度敏感数据的团队启用来宾共享。 如果确实计划与团队中的组织外部人员进行协作，则建议启用来宾共享。 Microsoft 365 包括许多安全性和合规性功能，可帮助你安全地共享敏感内容。 这通常比直接通过电子邮件向组织外部的人员发送内容更安全。

有关与来宾安全共享的详细信息，请参阅以下资源：

- [在与组织外人员共享文件时限制意外公开信息](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [创建安全的来宾共享环境](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

为允许或阻止来宾共享，我们将团队的敏感度标签与关联 SharePoint 网站的网站级别共享控件结合使用，这两者将在后面讨论。

## <a name="sensitivity-labels"></a>敏感度标签

对于高度敏感级别的保护，我们将使用敏感度标签对团队进行分类。 此标签还可用于分类和解密此团队或其他团队，或者其他文件位置（如 SharePoint 或 OneDrive）中的单个文件。 

首先，必须为 Teams 启用敏感度标签。 有关详细信息，请参阅[使用敏感度标签保护 Microsoft Teams、Office 365 组和 SharePoint 网站中的内容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

如果已在组织中部署了敏感度标签，请考虑此标签与总体标签策略的匹配情况。 可根据需要更改名称或设置以满足组织的需求。

为 Teams 启用灵敏度标签后，下一步是创建标签。

创建敏感度标签
1. 打开 [Microsoft 365 合规中心](https://compliance.microsoft.com)。
2. 在“**解决方案**”下，单击“**信息保护**”。
3. 单击“**创建标签**”。
4. 为标签命名。 建议使用“**高度敏感**”，但如果该名称已在使用，则可以选择其他名称。
5. 添加工具提示，然后单击“**下一步**”。
6. 在“**加密**”页面上的“**加密**”下拉列表中，选择“**应用**”。
7. 在“**向特定用户和组分配权限**”下，单击“**分配权限**”。
8. 点击“**添加组织中的所有用户和组**”。
9. 如果某些来宾用户应具有解密文件的权限，请单击“**添加用户或组**”并添加他们。
10.  单击“**保存**”，然后单击“**下一步**”。
11. 如果希望自动向使用此标签分类的文件添加页眉、页脚或水印，请在“**内容标记**”页面上启用内容标记。
12. 在“**网站和组设置**”页面上，将“**网站和组设置**”设置为“**开启**”。
13. 在“**Office 365 与组连接的团队网站的隐私**”下拉菜单中，选择“**专用 - 只有成员才能访问网站**”。
14. 如果想要允许来宾访问，请选择“**允许 Office 365 组所有者将组织外部的人员添加到组**”复选框。 
15. 在“**未托管的设备**”下，选择“**阻止访问**”。
16. 单击“**下一步**”。
17. 在“**Office 应用程序自动标记**”页面上，单击“**下一步**”。
18. 单击“**提交**”，然后单击“**完成**”。

创建标签后，需要将其发布到使用它的用户。 对于敏感保护，我们将对所有用户提供该标签。 在 Microsoft 365 合规中心的“**信息保护**”页面的“**标签策略**”选项卡上发布标签。 如果你拥有适用于所有用户的现有策略，请将此标签添加到该策略。 如果需要创建新策略，请参阅[通过创建标签策略来发布灵敏度标签](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy)。

## <a name="create-a-team"></a>创建团队

对高度敏感方案的进一步配置在与团队相关联的 SharePoint 网站中完成，因此下一步是创建团队。

创建高度敏感信息团队
1. 在 Teams 中，单击应用程序左侧的“**团队**”，然后在团队列表底部单击“**加入或创建团队**”。
2. 点击“**创建团队**”（第一张卡片，左上角）。
3. 选择“**从头开始构建团队**”。
4. 在“**敏感度**”列表中，选择刚才创建的“**高敏感**”标签。
5. 在“**隐私**”下，单击“**专用**”。
6. 为该团队键入一个名称，然后单击“**创建**”。
7. 将用户添加到团队，然后单击“**关闭**”。

## <a name="private-channel-settings"></a>专用频道设置

在此层级，仅限团队所有者创建专用频道。

限制专用频道创建
1. 在团队中，单击“**更多选项**”，然后单击“**管理团队**”。
2. 在“**设置**”选项卡上，展开“**成员权限**”。
3. 清除“**允许成员创建专用频道**”复选框。

还可以使用“[团队策略](https://docs.microsoft.com/MicrosoftTeams/teams-policies)”来控制谁可以创建专用频道。

## <a name="sharepoint-settings"></a>SharePoint 设置

每次使用高度敏感标签创建新团队时，都需要在 SharePoint 中执行两步操作：

- 更新 SharePoint 管理中心中网站的来宾共享设置，使其与创建标签时选择的内容一致，并将默认共享链接更新为“*现有访问权限者*”。
- 自主更新网站中的网站共享设置，防止成员共享文件、文件夹或网站，并关闭访问请求。

### <a name="site-guest-sharing-settings"></a>网站来宾共享设置

创建标签时选择的来宾共享设置（仅影响团队成员身份）应与关联的SharePoint 网站的来宾共享设置匹配，如下所示：

|标签设置|SharePoint 网站设置|
|:------------|:----------------------|
|**允许 Office 365 组所有者将组织外部的人员添加到组**已选中|**新来宾和现有来宾**（新团队默认值）|
|**允许 Office 365 组所有者将组织外部的人员添加到组**未选中|**仅组织内部人员**|

更新网站设置
1. 打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。
2. 在“**网站**”下，单击“**活动的网站**”。
3. 单击与团队关联的网站。
4. 在“**策略**”选项卡的“**外部共享**”下，单击“**编辑**”。
5. 如果在创建高度敏感标签时允许来宾共享，请确保选择“**新来宾和现有来宾**”。 如果创建标签时不允许共享，选择“**仅限组织中的人员**”。
6. 在“默认共享链接类型”下，清除“**与组织级别设置相同**”复选框，然后选择“**具有现有访问权限的人员**”。
7. 单击“**保存**”。

如果要将在团队创建过程中编制脚本，可使用含有以下参数的 [Set-sposite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite)：

- `-SharingCapability Disabled` 用于禁用来宾共享（默认启用）
- `-DefaultSharingLinkType Internal` 用于更改“*指定人员*”的默认共享链接

#### <a name="private-channels"></a>专用频道

如果向团队添加私人频道，则每个私人频道都会使用默认共享设置创建新的 SharePoint 网站。 这些网站在 SharePoint 管理中心中不可见，因此必须使用 Set-SPOSite PowerShell cmdlet 来更新来宾共享设置。

### <a name="site-sharing-settings"></a>网站共享设置

为了确保不与非团队成员共享 SharePoint 网站，我们将此类共享限制为所有者。 我们还将文件和文件夹的共享限制为团队所有者。 这有助于确保无论何时与团队外部人员共享文件，所有者都会知道。

配置仅限所有者的网站共享
1. 在 Teams 中，导航至要更新团队的“**常规**”标签。
2. 在团队的工具栏中，单击“文件”****。
3. 单击省略号，然后单击“在 SharePoint 中打开”****。
4. 在基础 SharePoint 网站的工具栏中，依次单击设置图标和“网站权限”****。
5. 在“网站权限”窗格的“**共享设置**”下方，单击“**更改共享设置**”。
6. 在“**共享权限**”下方，选择“**仅网站所有者可以共享文件、文件夹和网站**”。
7. 将“**允许访问请求**”设置为“**关闭**”，然后单击“**保存**”。

## <a name="see-also"></a>另请参阅

[创建和配置敏感度标签及其策略](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels)

