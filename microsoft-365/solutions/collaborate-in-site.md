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
localization_priority: Normal
f1.keywords: NOCSH
description: 了解设置 SharePoint 网站以与来宾协作所需的 Microsoft 365 配置步骤。
ms.openlocfilehash: 6862fe715fe2f19b968b773bc6df6c70c207a44f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663520"
---
# <a name="collaborate-with-guests-in-a-site"></a>在网站中与来宾协作

如果需要跨文档、数据和列表与来宾进行协作，可以使用 SharePoint 网站。 新式 SharePoint 网站连接到 Microsoft 365 组，可以管理网站成员身份并提供其他协作工具，如共享邮箱和日历。

本文将介绍设置 SharePoint 网站以与来宾协作所需的 Microsoft 365 配置步骤。

## <a name="video-demonstration"></a>视频演示

此视频演示本文档中所述的配置步骤。</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Azure 外部协作设置

Microsoft 365 中的共享由 Azure Active Directory 中的 [B2B](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)外部协作设置在最高级别管理。 如果在 Azure AD 中禁用或限制来宾共享，此设置将覆盖你在 Microsoft 365 中配置的任何共享设置。

检查 B2B 外部协作设置以确保不会阻止与来宾共享。

![Azure Active Directory 外部协作设置页的屏幕截图](../media/azure-ad-organizational-relationships-settings.png)

设置外部协作设置

1. 登录 Azure Active [https://aad.portal.azure.com](https://aad.portal.azure.com) Directory。
2. 在左侧导航窗格中，单击 **Azure Active Directory。**
3. 单击 **"外部标识"。**
4. 在 **"入门"** 屏幕的左侧导航窗格中，单击 **"外部协作设置"。**
5. 确保 **管理员和来宾邀请** 者角色中的用户可以邀请，**并且成员可以邀请** 都设置为 **"是"。**
6. 如果进行了任何更改，请单击 **“保存”**。

记下"协作限制 **"部分** 中的设置。 确保未阻止要协作的来宾的域。

如果与多个组织的来宾合作，可能需要限制其访问目录数据的能力。 这将阻止他们查看目录中的来宾。 为此，在"来宾用户访问限制"下，选择"来宾用户对目录对象设置的属性和成员身份具有有限访问权限"或"来宾"用户访问仅限于其自己的目录对象的属性和 **成员身份**。

## <a name="microsoft-365-groups-guest-settings"></a>Microsoft 365 组来宾设置

新式 SharePoint 网站使用 Microsoft 365 组来控制网站访问。 必须打开 Microsoft 365 组来宾设置，SharePoint 网站中的来宾访问才能正常工作。

![Microsoft 365 管理中心中的 Microsoft 365 组来宾设置的屏幕截图](../media/office-365-groups-guest-settings.png)

设置 Microsoft 365 组来宾设置

1. 在 Microsoft 365 管理中心的左侧导航窗格中，展开"**设置"。**
2. 单击 **"组织设置"。**
3. 在列表中，单击 **"Microsoft 365 组"。**
4. 确保允许组所有者将组织外部人员作为来宾添加到 **Microsoft 365** 组，同时选中"允许 **来宾** 组成员访问组内容"复选框。
5. 如果进行了更改，请单击"**保存更改"。**

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint 组织级共享设置

若要使来宾能够访问 SharePoint 网站，SharePoint 组织级共享设置必须允许与来宾共享。

组织级别的设置确定将可用于各个网站的设置。 网站设置不能比组织级别的设置更宽松。

如果要允许未经身份验证的文件和文件夹共享，请选择"任何人 **"。** 如果要确保组织外部的所有人员均必须进行身份验证，请选择 **"新来宾"和"现有来宾"。** 选择组织中任何网站所需的最宽松设置。

![SharePoint 组织级别共享设置的屏幕截图](../media/sharepoint-organization-external-sharing-controls.png)


设置 SharePoint 组织级共享设置

1. 在 Microsoft 365 管理中心左侧导航窗格中的"管理中心"下，单击 **"SharePoint"。**
2. 在 SharePoint 管理中心的左侧导航窗格中，**在"策略**"下，单击"**共享"。**
3. 确保 SharePoint 的外部共享设置为"任何人 **"** 或"**新来宾"和"现有来宾"。**
4. 如果进行了任何更改，请单击 **“保存”**。

## <a name="create-a-site"></a>创建网站

下一步是创建计划用于与来宾协作的网站。

创建网站
1. 在 SharePoint 管理中心中的“**网站**”下，单击“**活动站点**”。
2. 单击“**创建**”。
3. 单击 **"团队网站"。**
4. 键入网站名称，然后输入组所有者的名称 (网站所有者) 。
5. 在 **"高级** 设置"下，选择是希望此网站是公共网站还是专用网站。
6. 单击"下一步"。
7. 单击“完成”。

我们稍后将邀请用户。 接下来，检查此网站的网站级别共享设置非常重要。

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint 网站级共享设置

检查网站级别的共享设置，以确保这些设置允许此网站访问的类型。 例如，如果将组织级别设置设置为"任何人"，但希望所有来宾对此网站进行身份验证，请确保网站级别共享设置设置为"新建"和"现有来宾 **"。**

请注意，网站无法与未通过身份验证 (**任何人** 进行) ，但单个文件和文件夹可以。

您还可以使用敏感度标签 [来控制 SharePoint 网站的外部共享设置](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

![SharePoint 网站外部共享设置的屏幕截图](../media/sharepoint-site-external-sharing-settings.png)

设置网站级共享设置
1. 在 SharePoint 管理中心的左侧导航栏中，展开 **“站点”**，然后单击 **“活动站点”**。
2. 选择要共享的网站。
3. 单击...，然后单击"**共享"。**
4. 确保共享设置为"任何人 **"或****"新来宾"和"现有来宾"。**
5. 如果进行了任何更改，请单击 **“保存”**。

## <a name="invite-users"></a>邀请用户

现在配置了来宾共享设置，因此您可以开始向网站添加内部用户和来宾。 网站访问通过关联的 Microsoft 365 组进行控制，因此我们将在那里添加用户。

邀请内部用户加入组
1. 导航到要添加用户的网站。
2. 单击 **表示** 成员计数的右上角的"成员"链接。
3. 单击“**添加成员**”。
4. 键入要邀请到网站的用户的名称或电子邮件地址，然后单击"保存 **"。**

无法从网站添加来宾。 你需要使用 Web 上的 Outlook 添加它们。 因此，作为添加来宾并邀请来宾加入组的先决条件，请单击 URL 列中网站的 **URL**  以导航到特定于网站的页面。 在此页中，单击 **应用启动器** 图标并选择 **Outlook。** 这是你可以从其中邀请来宾加入组的屏幕，此过程如下所述。

邀请来宾加入组
1. 在 **"** 组"下，单击要邀请来宾的组。
2. 打开组联系人卡片，单击右上角的"成员"链接 (表示成员计数) 。
3. 单击 **"添加成员"。**
4. 键入要邀请的来宾的电子邮件地址，然后单击"添加 **"。**
5. 单击“关闭”。
请注意，仅当您不是组 **的所有者时** ，才需要单击"关闭"，因此，不允许将来宾添加到组中。 在这种情况下，将来宾添加到组的请求将转移给组所有者进行审批。

## <a name="see-also"></a>另请参阅

[有关与未经认证用户共享文件和文件夹的最佳做法](best-practices-anonymous-sharing.md)

[与来宾共享时限制文件意外曝光](share-limit-accidental-exposure.md)

[创建安全的来宾共享环境](create-secure-guest-sharing-environment.md)

[创建托管有来宾的 B2B 外联网](b2b-extranet.md)

[SharePoint 和 OneDrive 与 Azure AD B2B 集成](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
