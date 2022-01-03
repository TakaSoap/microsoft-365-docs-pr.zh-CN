---
title: 限制 Microsoft 365 中的共享
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
search.appverid:
- SPO160
- MET150
f1.keywords: NOCSH
ms.custom:
- admindeeplinkMAC
- admindeeplinkTEAMS
ms.localizationpriority: high
recommendations: false
description: 了解在 Microsoft 365 中用于限制或禁用共享的选项。
ms.openlocfilehash: a34a1a457ed9c53f6393d65617f8ac0d9e611209
ms.sourcegitcommit: d7cdbdda9b829c49caa3105eb47d3f26b88a5daf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2022
ms.locfileid: "61660162"
---
# <a name="limit-sharing-in-microsoft-365"></a>限制 Microsoft 365 中的共享

虽然无法完全禁用内部共享，也无法删除网站中的“共享”按钮，但可通过多种方式来限制 Microsoft 365 中的共享，以满足组织的需求。

下表列出了共享文件的方法。 有关详细信息，请单击“**共享方法**”列中的链接。

|共享方法|说明|限制选项|
|:-------------|:----------|:-------------|
|[Microsoft 365 组或团队](#microsoft-365-group-or-team)|如果被授予对 Microsoft Teams 团队或 Microsoft 365 组的访问权限，可以有权编辑关联的 SharePoint 网站中的文件。|如果组或团队是专用的，则用于加入团队的共享邀请将会转到所有者那里以供其审批。 管理员可通过禁用来宾访问或使用敏感度标签来阻止组织外部人员的访问。|
|[SharePoint 网站](#sharepoint-site)|可向用户授予对 SharePoint 网站的“所有者”、“成员”或“访问者”访问权限，他们将拥有对网站中文件的相应访问权限级别。|可限制网站权限，以便只有网站所有者可以共享网站。 管理员可以将网站设置为只读或完全阻止访问。|
|[与特定人员共享](#sharing-with-specific-people)|网站成员和拥有编辑权限的人员可以提供对文件和文件夹的直接权限，或通过使用 *特定人员* 链接进行共享。|可限制网站权限，以便只有网站所有者可以共享文件和文件夹。 在这种情况下，网站成员提供的直接访问和 *特定人员* 链接共享将会转到网站所有者那里以供其审批。|
|[SharePoint 和 OneDrive 来宾共享](#sharepoint-guest-sharing)|SharePoint 网站所有者和成员以及 OneDrive 所有者可与组织外部的人员共享文件和文件夹。|可针对整个组织或单个网站禁用来宾共享。|
|[*你组织中的人员* 共享链接](#people-in-your-organization-sharing-links)|SharePoint 网站所有者和成员可以使用 *你组织中的人员* 链接（可用于组织内的所有人）来共享文件。|可在网站级别禁用 *你组织中的人员* 链接。|
|[创建网站、组和团队](#create-sites-groups-and-teams)|默认情况下，用户可以创建他们可以共享内容的新网站、组和团队。|管理员可限制可创建网站、组和团队的人员。|
|[电子邮件](#email)|有权访问文件的人员可通过电子邮件将其发送给其他人。|管理员可以使用敏感度标签对文件进行加密，以防止有人与未经授权的人员共享这些文件。|
|[下载或文件复制](#download-or-file-copy)|有权访问文件的人员可以下载或复制该文件，并与 Microsoft 365 范围之外的其他人共享。|管理员可以使用敏感度标签对文件进行加密，以防止有人与未经授权的人员共享这些文件。|

你还可以限制人员访问共享内容的条件。 有关详细信息，请参阅本文后面的[条件访问](#conditional-access)。

虽然可以使用本文中所述的管理员控制来限制组织中的共享，但我们强烈建议考虑使用 Microsoft 365 中提供的安全性和合规性功能来创建安全的共享环境。有关信息，请参阅 [使用 Microsoft 365 在 SharePoint 中的文件协作](/sharepoint/deploy-file-collaboration) 和 [使用安全隔离配置团队](secure-teams-security-isolation.md)。

若要了解组织中如何使用共享，请[运行文件和文件夹共享报告](/sharepoint/sharing-reports)。

## <a name="microsoft-365-group-or-team"></a>Microsoft 365 组或团队

若要限制 Microsoft 365 组或 Microsoft Teams 团队中的共享，请务必将组或团队设为私人。 组织内部人员可以随时加入公共组或团队。 除非组或团队是专用的，否则无法在组织内限制团队或其文件的共享。

### <a name="guest-sharing"></a>来宾共享

如果想要阻止 Teams 中的来宾访问，可在 Teams 管理中心内关闭来宾共享。

关闭 Teams 的来宾共享
1. 在 Teams 管理中心中，展开"来宾访问 **"选项卡** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**** 组织范围的设置</a>。
2. 关闭“**在 Teams 中允许访客访问**”。
3. 单击“**保存**”。

若要阻止 Microsoft 365 组中的来宾访问，可以在 Microsoft 365 管理中心内禁用组来宾访问设置。

禁用 Microsoft 365 组中的来宾共享的具体步骤
1. 在 Microsoft 365 管理中心中，单击“**设置**” > “**组织设置**” > <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">“**服务**”选项卡</a>。
2. 单击“**Microsoft 365 组**”。
3. 取消选中“**允许组织外部的组成员访问组内容**”和“**允许组所有者将组织外部的人员添加到组**”复选框。
4. 单击“**保存更改**”。

    ![Microsoft 365 管理中心中内 Microsoft 365 组共享设置的屏幕截图。](../media/office-365-groups-guest-settings-off.png)

> [!NOTE]
> 如果想要阻止特定组或团队的来宾共享，可使用 [Microsoft PowerShell](per-group-guest-access.md) 或[敏感性标签](../compliance/sensitivity-labels-teams-groups-sites.md)来执行此操作。

可通过在 Azure Active Directory 中允许或阻止域，将来宾共享限制为指定域的用户。 如果已启用 [Azure AD B2B 的 SharePoint 和 OneDrive 集成](/sharepoint/sharepoint-azureb2b-integration-preview)，该操作还会影响 SharePoint 中的来宾共享。

仅允许向指定域发出共享邀请
1. 在 Azure Active Directory 中的“概述”页面上，单击“**组织关系**”。
2. 单击“**设置**”。
3. 在“**协作限制**”下，选择“**拒绝向指定域发出邀请**”或“**仅允许向指定域发出邀请**”，然后键入要使用的域。
4. 单击“**保存**”。

    ![Azure Active Directory 中的协作限制设置的屏幕截图。](../media/azure-ad-allow-only-specified-domains.png)

## <a name="sharepoint-site"></a>SharePoint 网站

你可以将 SharePoint 网站共享的执行者限制为仅限网站所有者。 这将防止网站成员共享网站。 请注意，如果网站连接到了 Microsoft 365 组，组成员可以邀请其他人加入此组，这些用户将拥有网站访问权限。

将网站共享的执行者限制为所有者
1. 在网站中，单击齿轮图标，然后单击“**网站权限**”。
2. 在“**共享设置**”下，单击“**更改共享设置**”。
3. 选择“**网站所有者和成员以及拥有编辑权限的人员可共享文件和文件夹，但只有网站所有者才可共享网站**”。
4. 单击“**保存**”。

    ![SharePoint 网站中共享权限设置的屏幕截图。](../media/sharepoint-site-sharing-permissions-level-two.png)

可通过关闭访问请求来阻止不是网站成员的用户请求访问。

关闭访问请求
1. 在网站中，单击齿轮图标，然后单击“**网站权限**”。
2. 在“**共享设置**”下，单击“**更改共享设置**”。
3. 关闭“**允许访问请求**”，然后单击“**保存**”。

可通过为相应网站允许或阻止域，将网站共享限制为指定域。

按域限制网站共享
1. 在 SharePoint 管理中心中的“**网站**”下，单击“**活动站点**”。
2. 单击要配置的网站。
3. 在“**策略**”选项卡的“**外部共享**”下，单击“**编辑**”。
4. 在“**外部共享的高级设置**”下，选中“**按域限制共享**”。
5. 添加你想要允许或阻止的域，然后单击“**保存**”。
6. 单击“**保存**”。

    ![允许的域网站级别设置的屏幕截图。](../media/limit-site-sharing-by-domain.png)

### <a name="block-access-to-a-site"></a>阻止访问网站

可以通过更改网站的锁定状态来阻止对网站的访问或使网站成为只读网站。有关详细信息，请参阅 [锁定和解锁网站](/sharepoint/manage-lock-status)。

### <a name="permissions-inheritance"></a>权限继承

虽然不推荐，但你可以使用 [SharePoint 权限继承](/sharepoint/what-is-permissions-inheritance)自定义网站和子网站的访问级别。

## <a name="sharing-with-specific-people"></a>与特定人员共享

如果你想限制网站或其内容的共享，可以将网站配置为仅允许网站所有者共享文件、文件夹和该网站。 进行此配置后，当网站成员尝试使用 *特定人员* 链接共享文件或文件夹时，该尝试将会转到网站所有者那里以供其审批。

将网站、文件和文件夹共享的执行者限制为所有者
1. 在网站中，单击齿轮图标，然后单击“**网站权限**”。
2. 在“**共享设置**”下，单击“**更改共享设置**”。
3. 选择“**只有站点所有者可共享文件、文件夹和站点**”。
4. 单击“**保存**”。

    ![将 SharePoint 网站中共享权限设置设为仅限所有者的屏幕截图。](../media/sharepoint-site-only-site-owners-can-share.png)

## <a name="sharepoint-guest-sharing"></a>SharePoint 来宾共享

如果想要阻止与组织外部的人员共享 SharePoint 或 OneDrive 文件和文件夹，可针对整个组织或单个网站关闭来宾共享。

针对组织关闭 SharePoint 来宾共享
1. 在 SharePoint 管理中心中的“**策略**”下，单击“**共享**”。
2. 在“**外部共享**”下，将 SharePoint 滑块向下拖动到“**仅限组织中的人员**”。
3. 单击“**保存**”。

    ![将 SharePoint 组织级别共享设置设为面向所有人的屏幕截图。](../media/sharepoint-tenant-sharing-off.png)


针对网站关闭来宾共享
1. 在 SharePoint 管理中心中的“**网站**”下，单击“**活动站点**”。
2. 单击要配置的网站。
3. 在“**策略**”选项卡的“**外部共享**”下，单击“**编辑**”。
4. 在“**外部共享**”下，选择“**仅限组织中的人员**”，然后单击“**保存**”。

    ![将 SharePoint 网站级别共享设置设为仅面向组织中的人员的屏幕截图。](../media/sharepoint-site-external-sharing-settings-off.png)

你可以单击 Microsoft 365 管理中心中的用户，然后选择 **OneDrive** 选项卡上的 **管理外部共享** 来关闭个人 OneDrive 的来宾共享。

如果想要允许与组织外部的人员共享，但要确保每个人都进行身份验证，可以针对整个组织或单个网站禁用 *任何人*（匿名共享）链接。

在组织级别关闭 *任何人* 链接
1. 在 SharePoint 管理中心中的“**策略**”下，单击“**共享**”。
2. 在“**外部共享**”下，将 SharePoint 滑块向下拖动到“**新来宾和现有来宾**”。
3. 单击“**保存**”。

    ![将 SharePoint 组织级别共享设置设为面向新来宾和现有来宾的屏幕截图。](../media/sharepoint-guest-sharing-new-existing-guests.png)

关闭站点的 *“任何人”* 链接
1. 在 SharePoint 管理中心中的“**网站**”下，单击“**活动站点**”。
2. 单击要配置的网站。
3. 在“**策略**”选项卡的“**外部共享**”下，单击“**编辑**”。
4. 在“**外部共享**”下，选择“**新来宾和现有来宾**”，然后单击“**保存**”。

    ![将 SharePoint 网站级别共享设置设为面向新设置和现有设置的屏幕截图。](../media/sharepoint-site-external-sharing-settings-new-existing-guests.png)

## <a name="people-in-your-organization-sharing-links"></a>*你组织中的人员* 共享链接

默认情况下，网站成员可以通过使用 *组织中的人员* 链接与组织中的其他人共享文件和文件夹。可以通过使用 PowerShell 来禁用 *组织中的人员* 链接：

```powershell
Set-SPOSite -Identity <site> -DisableCompanyWideSharingLinks Disabled
```

例如：

```powershell
Set-SPOSite -Identity https://contoso.sharepoint.com -DisableCompanyWideSharingLinks Disabled
```

## <a name="create-sites-groups-and-teams"></a>创建网站、组和团队

默认情况下，用户可以创建他们可以共享内容的新网站、组和团队（具体取决于你的共享设置）。 你可限制可创建网站、组和团队的人员。 请参阅以下参考：

- [管理 SharePoint 中的网站创建](/sharepoint/manage-site-creation)
- [管理可创建 Microsoft 365 组的人员](./manage-creation-of-groups.md)

> [!NOTE]
> 限制组创建将限制团队创建。

## <a name="email"></a>电子邮件

可通过加密防止不必要的电子邮件共享。 这将防止电子邮件被转发或与未经授权的用户共享。 你可以使用敏感度标签来启用电子邮件加密。 有关详细信息，请参阅[使用敏感度标签中的加密限制对内容的访问](../compliance/encryption-sensitivity-labels.md)。

## <a name="download-or-file-copy"></a>下载或文件复制

有权访问 Microsoft 365 中的文件和文件夹的用户可以下载文件并将其复制到外部媒体。 若要减少不必要的文件共享的风险，可使用敏感度标签对内容进行加密。

## <a name="conditional-access"></a>条件访问

Azure Active Directory 条件访问提供的选项可根据网络位置、设备运行状况、登录风险和其他因素限制或阻止与人员共享。请参阅 [什么是条件访问？](/azure/active-directory/conditional-access/overview)。

SharePoint 提供与 Azure AD 条件访问直接集成服务，适用于未托管的设备和网络位置。有关详细信息，请参阅以下参考：

- [控制来自非托管设备的访问](/sharepoint/control-access-from-unmanaged-devices)
- [根据网络位置控制对 SharePoint 和 OneDrive 数据的访问](/sharepoint/control-access-based-on-network-location)

## <a name="see-also"></a>另请参阅

[Microsoft 365 来宾共享设置参考](microsoft-365-guest-settings.md)
