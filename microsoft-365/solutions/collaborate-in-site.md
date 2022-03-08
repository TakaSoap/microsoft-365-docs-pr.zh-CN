---
title: 在网站中与来宾协作
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: 了解设置Microsoft 365来宾协作的 SharePoint 网站所需的配置步骤。
ms.openlocfilehash: 7187149324f88c64570549429f86291320431566
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63318535"
---
# <a name="collaborate-with-guests-in-a-site"></a>在网站中与来宾协作

如果需要跨文档、数据和列表与来宾进行协作，可以使用SharePoint网站。 新式SharePoint网站连接到Microsoft 365组，可以管理网站成员身份并提供其他协作工具，如共享邮箱和日历。

本文将介绍设置与来宾Microsoft 365网站所需的 SharePoint 配置步骤。

## <a name="video-demonstration"></a>视频演示

该视频展示了本文档中介绍的配置步骤。</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Azure 外部协作设置

Microsoft 365 中的共享在最高级别由 [Azure Active Directory 中的 B2B 外部协作设置](/azure/active-directory/external-identities/delegate-invitations) 管理。 如果在 Azure AD 中禁用或限制来宾共享，此设置将覆盖你在 Microsoft 365 中配置的任何共享设置。

检查 B2B 外部协作设置，确保不会阻止与来宾共享。

!["外部Azure Active Directory协作设置屏幕截图。](../media/azure-ad-organizational-relationships-settings.png)

设置外部协作设置

1. 在 [https://aad.portal.azure.com](https://aad.portal.azure.com) 上登录到 Azure Active Directory。
2. 在左侧导航窗格中，单击 **Azure Active Directory**。
3. 单击 **“外部标识”**。
4. 在 **“入门”** 屏幕的左侧导航窗格中，单击 **“外部协作设置”**。
5. 请确保选择 **成员用户和分配给特定管理员角色的用户可以邀请来宾用户，包括具有成员权限的来宾** 或 **组织中的任何用户都可以邀请来宾用户，包括来宾和非管理员**。
6. 如果进行了任何更改，请单击 **“保存”**。

请注意 **“协作限制"** 部分的设置。 确保不会阻止要协作来宾的域。

如果与多个组织的来宾合作，可能需要限制其访问目录数据的能力。  这将阻止他们查看目录中的来宾。 为此，在 **“来宾用户访问限制”** 下，选择 **“来宾用户具有对目录对象设置的属性和成员身份的有限访问权限”** 或 **“来宾用户访问仅限于其自己的目录对象的属性和成员身份”**。

## <a name="microsoft-365-groups-guest-settings"></a>Microsoft 365 组来宾设置

新式SharePoint网站使用Microsoft 365组来控制网站访问。 必须Microsoft 365组来宾设置，来宾访问才能SharePoint网站。

![Microsoft 365 管理中心中的 Microsoft 365 组来宾设置的屏幕截图。](../media/office-365-groups-guest-settings.png)

设置 Microsoft 365 组来宾设置

1. 在 Microsoft 365 管理中心左侧导航窗格中，展开 **“设置”**。
2. 单击 **“组织设置”**。
3. 在列表中，单击 **“Microsoft 365 组”**。
4. 确保复选框 **允许组所有者将组织外部人员作为来宾添加到 Microsoft 365 组** 和 **允许来宾组成员访问组内容** 都已选中。
5. 如果进行了更改，请单击 **“保存更改”**。

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint组织级别的共享设置

若要使来宾能够访问SharePoint网站，SharePoint级别共享设置必须允许与来宾共享。

组织级别设置确定将可用于各个网站的设置。 网站设置不能比组织级别设置更宽松。

如果要允许未经身份验证的文件和文件夹共享，请选择"任何人 **"**。 如果希望确保组织外部的所有人员均必须进行身份验证，请选择"新来宾和现有 **来宾"**。 选择组织中任何网站所需的最宽松设置。

![SharePoint 组织级别共享设置的屏幕截图。](../media/sharepoint-organization-external-sharing-controls.png)


设置 SharePoint 组织级共享设置

1. In the Microsoft 365 管理中心， in the left navigation pane， under **Admin centers**， select **SharePoint**.
2. 在管理SharePoint左侧导航窗格中的"策略"下 **，选择"** 共享 <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**"**</a>。
3. 确保 SharePoint 的外部共享设置为 **“任何人”** 或 **“新来宾和现有来宾”**。
4. 如果进行了更改，请选择"保存 **"**。

## <a name="create-a-site"></a>创建网站

下一步是创建计划用于与来宾协作的网站。

创建网站
1. 在 SharePoint 管理中心的"**网站"** 下，选择 <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**活动网站**</a>。
2. 选择 **“创建”**。
3. 选择 **"团队网站"**。
4. 键入网站名称，然后输入组所有者名称 (网站所有者) 。
5. 在 **"高级** 设置"下，选择是希望此网站是公共网站还是专用网站。
6. 选择“下一步”。
7. 选择“完成”。

我们稍后将邀请用户。 接下来，检查此网站的网站级别共享设置非常重要。

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint 网站级别共享设置

检查网站级别的共享设置，以确保这些设置允许您希望用于此网站的访问类型。 例如，如果将组织级别设置设置为"任何人"，但希望所有来宾对此网站进行身份验证，请确保网站级别共享设置设置为"新来宾和现有来宾 **"**。

请注意，该网站无法与"任何人"设置 (**未经** 身份验证) ，但单个文件和文件夹可以共享。

您还可以使用敏感度[标签来控制网站外部SharePoint设置](../compliance/sensitivity-labels-teams-groups-sites.md)。

![SharePoint 网站外部共享设置的屏幕截图。](../media/sharepoint-site-external-sharing-settings.png)

设置网站级别共享设置
1. 在SharePoint管理中心的左侧导航栏中，展开"**网站**"，然后选择"<a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**活动网站"**</a>。
2. 选择要共享的网站。
3. 选择"..."，然后选择" **共享"**。
4. 确保将共享设置为 **“任何人”** 或 **“新来宾和现有来宾”**。
5. 如果进行了更改，请选择"保存 **"**。

## <a name="invite-users"></a>邀请用户

来宾共享设置现已配置，因此你可以开始向网站添加内部用户和来宾。 网站访问通过关联的组Microsoft 365，因此我们将在那里添加用户。

邀请内部用户加入组

1. 导航到要添加用户的网站。
2. 选择 **右上角** 表示成员计数的成员链接。
3. 选择“**添加成员**”。
4. 键入要邀请到网站的用户的姓名或电子邮件地址，然后选择"保存 **"**。

无法从网站添加来宾。 你需要使用自定义Outlook 网页版。 因此，作为添加来宾并邀请来宾加入组的先决条件，请单击"URL"列中网站的 **URL**  以导航到特定于网站的页面。 从此页中，单击 **应用启动器** 图标并选择"**Outlook"**。 这是一个屏幕，你可以从其中邀请来宾加入一个组，此过程如下所述。

邀请来宾加入组
1. 在 **"** 组"下，单击要邀请来宾的组。
2. 打开组联系人卡片，单击右上角的"成员"链接 (表示成员计数) 。
3. 单击 **"添加成员"**。
4. 键入要邀请的来宾的电子邮件地址，然后单击"添加 **"**。
5. 单击“关闭”。
请注意，只有不是 **组所有者时** ，才需要单击"关闭"，因此，不允许将来宾添加到组中。 在这种情况下，将来宾添加到组的请求将传输给组所有者进行审批。

## <a name="see-also"></a>另请参阅

[有关与未经认证用户共享文件和文件夹的最佳做法](best-practices-anonymous-sharing.md)

[与来宾共享时限制文件意外曝光](share-limit-accidental-exposure.md)

[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md)（创建安全的来宾共享环境）

[创建有托管来宾的 B2B 外网](b2b-extranet.md)

[SharePoint 和 OneDrive 与 Azure AD B2B 的集成](/sharepoint/sharepoint-azureb2b-integration-preview)
