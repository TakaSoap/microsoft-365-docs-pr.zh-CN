---
title: 配置具有安全隔离的团队
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
- admindeeplinkCOMPLIANCE
recommendations: false
description: 了解如何创建具有唯一敏感度标签的团队来保证安全。
ms.openlocfilehash: 293ac9a1a28757dacba39d30e619ac41be786e04
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60785878"
---
# <a name="configure-a-team-with-security-isolation"></a>配置具有安全隔离的团队

本文向你提供在 Microsoft Teams 中配置私人团队的建议和步骤，并使用唯一敏感标签来加密文件，以使仅团队成员可以对其进行解密。

除了专用访问之外，本文还介绍了如何配置关联 SharePoint 网站，你可以从团队频道的“**文件**”部分进行访问，以获得存储高度管控数据所需的其他安全性。

采用安全隔离的团队的配置元素如下：

- 私人团队
- 关联 SharePoint 团队网站上的其他安全性：
  - 阻止网站成员与他人共享网站。
  - 阻止非网站成员请求访问该网站。
- 专为此团队提供的敏感度标签：
    - 阻止从未托管的设备访问 SharePoint 内容
    - 允许或拒绝来宾访问团队，具体取决于需求
    - 加密团队所应用的文件

> [!IMPORTANT]
> 继续执行本文中的步骤之前，确保启用[敏感度标签来保护 Microsoft Teams、Office 365 组和 SharePoint 网站中的内容](../compliance/sensitivity-labels-teams-groups-sites.md)。

观看此视频以简要了解部署流程。
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mGHf]

<a name="poster"></a> 有关此方案的 1 页摘要，请参阅 [采用安全隔离的 Microsoft Teams 文章](../downloads/team-security-isolation-poster.pdf)。

[![“采用安全隔离的 Microsoft Teams”文章。](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)

你还可以下载 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf) 或 [PowerPoint](https://download.microsoft.com/download/8/0/5/8057fc16-c044-40b6-a652-7ed555ba2895/team-security-isolation-poster.pptx) 格式的海报，并以信件、法律或小报 (11 x 17) 的纸型打印。

按照以下说明，在你自己的测试实验室环境中 [此](team-security-isolation-dev-test.md)。

查看 Contoso Corporation 在此次案例研究中如何使用一个 [不](contoso-team-for-top-secret-project.md)。

## <a name="initial-protections"></a>初始保护

为了帮助保护对团队及其基础 SharePoint 网站的访问，请查看以下最佳做法：
- [标识和设备访问策略](../security/office-365-security/identity-access-policies.md)
- [SharePoint Online 访问策略](../security/office-365-security/sharepoint-file-access-policies.md)
- [部署具有基线保护的团队](configure-teams-baseline-protection.md)

## <a name="guest-sharing"></a>来宾共享

根据业务性质，可能会也可能不希望为此团队启用来宾共享。 如果确实计划与团队中的组织外部人员进行协作，请启用来宾共享。 

有关与来宾安全共享的详细信息，请参阅以下资源：

- [在与组织外人员共享文件时限制意外公开信息](./share-limit-accidental-exposure.md)
- [创建安全的来宾共享环境](./create-secure-guest-sharing-environment.md)

为允许或阻止来宾共享，我们将团队的敏感度标签与关联 SharePoint 网站的网站级别共享控件结合使用，这两者将在后面讨论。

## <a name="create-a-private-team"></a>创建私人团队。

由于我们正在专为此团队创建敏感度标签，下一步是创建团队。 如果有现有团队，可以使用此团队。

创建机密信息团队
1. 在 Teams 中，单击应用程序左侧的“**团队**”，然后在团队列表底部单击“**加入或创建团队**”。
2. 点击“**创建团队**”（第一张卡片，左上角）。
3. 选择“**从头开始构建团队**”。
4. 在“**敏感度**”列表中，保留默认值。
5. 在“**隐私**”下，单击“**专用**”。
6. 键入与敏感项目相关的团队的名称。例如，**Project Saturn**。
7. 单击“**创建**”。
8. 将用户添加到团队，然后单击“**关闭**”。

## <a name="private-channel-settings"></a>专用频道设置

建议对团队所有者限制创建专用频道。

限制专用频道创建
1. 在团队中，单击“**更多选项**”，然后单击“**管理团队**”。
2. 在“**设置**”选项卡上，展开“**成员权限**”。
3. 清除“**允许成员创建专用频道**”复选框。

还可以使用“[团队策略](/MicrosoftTeams/teams-policies)”来控制谁可以创建专用频道。

## <a name="create-a-sensitivity-label"></a>创建敏感度标签

为配置团队进行安全隔离，我们将使用专门为此团队创建的敏感度标签。 此标签用于以团队级别控制来宾共享和阻止访问未托管的设备。 也可以用于对团队中的单个文件进行分类和加密，以使只有团队所有者和成员才能打开它们。

如果拥有能够查看机密文件但是不能编辑的内部合作伙伴或利益干系人组，可以将他们添加至具有“仅查看”权限的标签。 然后可将这些人员添加至具有“读取者”权限的团队 SharePoint 网站，他们对保管文件的网站具有只读访问权限，而不是本身拥有此权限。

创建敏感度标签

1. 打开Microsoft 365 合规中心，在 **解决方案** 下，选择 <a href="https://go.microsoft.com/fwlink/p/?linkid=2174015" target="_blank">**信息保护**</a>。
1. 单击“**创建标签**”。
1. 为标签命名。我们建议以你将要使用的团队为其命名。
1. 添加显示名称和说明，然后单击“**下一步**”。
1. 在“**定义此标签页的搜索范围**”中，选择“**文件和电子邮件**”和“**组和站点**”，然后单击“**下一步**”。
1. 在“**选择文件和电子邮件的保护设置**”页面中，选择“**加密文件和电子邮件**”，然后单击“**下一步**”。
1. 在“**加密页面中**”页面中，选择“**配置加密设置**”。
1. 单击“**添加用户或组**”，选择创建的团队，然后单击“**添加**”
1. 单击“**选择权限**”。
1. 从下拉列表中选择“**合著者**”，然后单击“**保存**”。
1. 如果包括对带有标签的文件有只读权限的用户或组：
    1. 单击“**分配权限**”。
    1. 单击“**添加用户或组**”，选择要添加的用户或组，然后单击“**添加**”。
    1. 单击“**选择权限**”。
    1. 从下拉列表中选择“**查看者**”，然后单击“**保存**”。
13.  单击“**保存**”，然后单击“**下一步**”。
14. 在“*文件和电子邮件自动标记*”页面中，单击“**下一步**”。
15. 在“**定义组和站点的防护设置**”页面中，选择“**隐私和外部用户访问设置**”和“**设备权限和外部共享设置**”，然后单击“**下一步**”。
16. 在“**定义隐私和外部用户权限设置**”页面中，选择“**隐私**”下的“**私人**”选项。
17. 如果你想允许来宾访问，选择“**外部用户权限**”下的“**让 Microsoft 365 组所有者添加组织外的人员为来宾**”。
18. 单击“**下一步**”。
19. 在“**定义外部共享和设备权限设置**”页面中，选择“**从标记的 SharePoint 站点控制外部共享**”。
20. 如果当前允许来宾访问，在“**无法共享的内容**”下选择“**新的和当前来宾**”；如果不允许，则选择“**仅组织中的人员**”。
21. 在“**未托管的设备的访问**”下，选择“**阻止访问**”。
22. 单击“**下一步**”。
23. 在“**数据库列自动标记**”页面中，单击“**下一步**”。
24. 单击“**创建标签**”，然后单击“**完成**”。

创建标签后，需要将其发布到使用它的用户。 在这种情况中，我们将标签仅提供给团队中的人员。

发布敏感度标签：

1. 在Microsoft 365 合规中心中，在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2174015" target="_blank">**信息保护** 页</a>上，选择"**标签策略"** 选项卡。
2. 单击“**发布标签**”。
3. 在“**选择要发布的敏感度标签**”页面上，单击“**选择要发布的敏感度标签**”。
4. 选择创建的标签，然后单击“**添加**”。
5. 单击“**下一步**”。
6. 在“发布到用户和组”页面上，单击“**选择用户和组**”。
7. 单击“**添加**”，然后选择创建的团队。
8. 单击“**添加**”，然后单击“**完成**”。
9. 单击“**下一步**”。
10. 在“策略设置”页面上，选中“**用户必须提供理由才可删除标签或设置更低分类标签**”复选框，然后单击“**下一步**”。
11. 键入策略名称，然后单击“**下一步**”。
12. 单击“**提交**”，然后单击“**完成**”。

## <a name="apply-the-label-to-the-team"></a>将标签应用于团队

标签发布后，必须将其应用于团队，以使来宾共享和托管设备设置生效。 此操作在 SharePoint 管理中心中进行。 注意，标签在发布后可能需要一些时间才可用。

应用敏感度标签
1. 打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。
2. 在“**站点**”下，单击“**活动站点**”。
3. 单击与团队关联的网站。
4. 在“**策略**”选项卡的“**敏感度**”下，单击“**编辑**”。
5. 选择创建的标签，然后单击“**保存**”。

## <a name="sharepoint-settings"></a>SharePoint 设置

在 SharePoint 中需要执行三个步骤：

- 更新 SharePoint 管理中心中网站的来宾共享设置，使其与创建标签时选择的内容一致，并将默认共享链接更新为“*现有访问权限者*”。
- 自主更新网站中的网站共享设置，防止成员共享文件、文件夹或网站，并关闭访问请求。
- 如果将人员或组添加至具有“查看者”权限的标签，可将他们添加至具有“只读”权限的 SharePoint 网站。

### <a name="sharepoint-guest-settings"></a>SharePoint 来宾设置

创建标签时选择的来宾共享设置（仅影响团队成员身份）应与关联的SharePoint 网站的来宾共享设置匹配，如下所示：

|标签设置|SharePoint 网站设置|
|:------------|:----------------------|
|**允许 Office 365 组所有者将组织外部的人员添加到组** 已选中|**新来宾和现有来宾**（新团队默认值）|
|**允许 Office 365 组所有者将组织外部的人员添加到组** 未选中|**仅组织内部人员**|

我们还将更新默认共享链接类型，以减少将文件和文件夹意外共享给比预期更多受众的风险。

更新网站设置
1. 打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。
2. 在“**站点**”下，单击“**活动站点**”。
3. 单击与团队关联的网站。
4. 在“**策略**”选项卡的“**外部共享**”下，单击“**编辑**”。
5. 如果在创建敏感标签时允许来宾共享，请确保选定“**新来宾和现有来宾**”。 如果创建标签时不允许共享，选择“**仅限组织中的人员**”。
6. 在“默认共享链接类型”下，清除“**与组织级别设置相同**”复选框，然后选择“**具有现有访问权限的人员**”。
7. 单击“**保存**”。

#### <a name="private-channels"></a>专用频道

如果向团队添加私人频道，则每个私人频道都会使用默认共享设置创建新的 SharePoint 网站。 这些网站在 SharePoint 管理中心中不可见，因此必须使用含有以下参数的 [Set-SPOSite ](/powershell/module/sharepoint-online/set-sposite) PowerShell cmdlet 来更新来宾共享设置：

- `-SharingCapability Disabled` 用于禁用来宾共享（默认启用）
- `-DefaultSharingLinkType Internal` 用于更改“*指定人员*”的默认共享链接

如果你不打算将专用频道用于你的团队，请考虑在“[团队设置](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc)”中的“**成员权限**”下关闭团队成员创建它们的功能。

### <a name="site-sharing-settings"></a>网站共享设置

为了确保不与非团队成员共享 SharePoint 网站，我们将此类共享限制为所有者。 我们还将文件和文件夹的共享限制为团队所有者。 这有助于确保无论何时与团队外部人员共享文件，所有者都会知道。

配置仅限所有者的网站共享
1. 在 Teams 中，导航至要更新团队的“**常规**”标签。
2. 在团队的工具栏中，单击“文件”。
3. 单击省略号，然后单击“在 SharePoint 中打开”。
4. 在基础 SharePoint 网站的工具栏中，依次单击设置图标和“网站权限”。
5. 在“网站权限”窗格的“**共享设置**”下方，单击“**更改共享设置**”。
6. 在“**共享权限**”下方，选择“**仅网站所有者可以共享文件、文件夹和网站**”，然后单击“**保存**”。

### <a name="custom-site-permissions"></a>自定义网站权限

如果将具有“查看者”权限的人员添加到敏感度标签，则可以将其添加到具有“读取”权限的 SharePoint 网站中，以便他们可以轻松访问文件。

将用户添加至网站
1. 在网站中单击设置图标，然后单击“**网站权限**”。
2. 点击“**邀请其他人**”，然后点击“**仅共享网站**”。
3. 键入要邀请的用户和组的名称。
4. 对于要添加的每个人或组，将其权限从“**编辑**”更改为“**读取**”。
5. 选择是否要向他们发送含有网站链接的电子邮件。
6. 单击“**添加**”。

## <a name="additional-protections"></a>附加保护

Microsoft 365 提供了其他用于保护内容的方法。 考虑以下选项是否有助于提高组织的安全性。

- 让你的来宾用户同意[使用条款](/azure/active-directory/conditional-access/terms-of-use)。
- 为来宾用户配置“[会话超时策略](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)”。
- 创建“[敏感信息类型](../compliance/sensitive-information-type-learn-about.md)”，并使用“[数据丢失保护](../compliance/dlp-learn-about-dlp.md)”来设置有关访问敏感信息的策略。
- 使用 [Azure Active Directory 访问](/azure/active-directory/governance/access-reviews-overview)审核，定期审核团队访问权限和成员资格。

## <a name="drive-user-adoption-for-team-members"></a>驱动团队成员的用户采用

随着团队的建立，是时候驱动该团队的采用以及提升它对团队成员的额外安全性。

### <a name="train-your-users"></a>培训用户

团队成员可以访问团队及其所有资源，包括聊天、会议和其他应用。 使用频道的“**文件**”部分中的文件时，团队成员应为所创建的文件分配敏感度标签。

当标签应用至文件时，文件被加密。 团队成员可以打开并进行实时协作。 如果文件离开网站并转发给恶意用户，则他们必须提供作为团队成员的用户帐户的凭据，这样才能打开文件并查看其内容。 

培训团队成员：

- 了解使用新团队访问聊天、会议、文件和 SharePoint 网站的其他资源的重要性以及高度管控数据泄露的后果，例如法律后果、监管罚款、勒索软件或失去竞争优势。
- 如何访问团队。
- 如何在网站上创建新文件和上传本地存储的新文件。
- 如何为团队使用正确的敏感性标签标记文件。
- 标签如何保护文件（即使文件泄露到网站外部）。

此培训应包括实践练习，让团队成员可以体验这些功能及其结果。

### <a name="conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a>定期审查使用情况并处理团队成员的反馈意见

在培训后的几周内：

- 快速处理团队成员的反馈意见并微调相关策略和配置。
- 分析团队的使用情况，并将其与预期使用情况进行比较。
- 验证是否使用敏感度标签正确标记了高度管控的文件。 通过查看 SharePoint 中的文件夹并使用“**添加列**”的“**显示/隐藏列**”选项添加“**敏感度**”列，可以查看为哪些文件分配了标签。

根据需要重新培训用户。

## <a name="see-also"></a>另请参阅

[Azure AD Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-configure)