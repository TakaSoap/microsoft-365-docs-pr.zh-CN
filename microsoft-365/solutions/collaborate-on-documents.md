---
title: 在文档中与来宾协作
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
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: 在本文中，您将了解如何与来宾在 SharePoint 和 OneDrive 中的文档中进行协作。
ms.openlocfilehash: 022811be642a79c07c632cefcc67a27f19e3af4f
ms.sourcegitcommit: 39af527404cb06e05c5aa4550dbec39aec133016
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2020
ms.locfileid: "48422601"
---
# <a name="collaborate-with-guests-on-a-document"></a>在文档中与来宾协作

如果需要与组织外部的人员协作处理 SharePoint 或 OneDrive 中的文档，则可以向其发送指向文档的共享链接。 在本文中，我们将演练必要的 Microsoft 365 配置步骤，以设置 SharePoint 和 OneDrive 的共享链接，以满足组织的需求。

## <a name="video-demonstration"></a>视频演示

该视频显示了本文档中描述的配置步骤。</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Azure 组织关系设置

Microsoft 365 中的共享受 [Azure Active Directory 中的组织关系设置](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)的最高级别的管辖。 如果在 Azure AD 中禁用或限制来宾共享，此设置将覆盖您在 Microsoft 365 中配置的任何共享设置。

检查组织关系设置以确保不会阻止与来宾共享。

![Azure Active Directory 组织关系设置页面的屏幕截图](../media/azure-ad-organizational-relationships-settings.png)

设置组织关系设置

设置外部协作设置

1. 在上登录到 Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) 。
2. 在左侧导航窗格中，单击 " **Azure Active Directory**"。
3. 单击 " **外部标识**"。
4. 在 " **开始** " 屏幕的左侧导航窗格中，单击 " **外部协作设置**"。
5. 确保 **来宾邀请者角色中的管理员和用户可以邀请** 和 **成员** 都可以邀请都设置为 **"是"**。
6. 如果进行了任何更改，请单击 **“保存”**。

请注意 " **协作限制** " 部分中的设置。 确保不会阻止您要与之进行协作的来宾域。

如果您使用多个组织的来宾，您可能希望限制其访问目录数据的能力。 这将阻止他们看到目录中的其他人是来宾。 若要执行此操作，请在 " **来宾用户访问限制**" 下，选择 " **来宾用户对属性和目录对象的成员身份的访问权限受到限制** "，并且 **来宾用户访问仅限于其自己的目录对象的属性和成员身份**。

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint 组织级别的共享设置

为使组织外部的人员能够访问 SharePoint 或 OneDrive 中的文档，SharePoint 和 OneDrive 组织级共享设置必须允许与组织外部的人员共享。

SharePoint 的组织级别设置确定将对单个 SharePoint 网站可用的设置。 网站设置不能比组织级别设置更具有更好的许可。 OneDrive 的组织级别设置决定了将在用户的 OneDrive 库中可用的共享级别。

对于 SharePoint 和 OneDrive，如果要允许未经身份验证的文件和文件夹共享，请选择 " **任何人**"。 如果您想要确保组织外部的人员必须进行身份验证，请选择 " **新建" 和 "现有来宾**"。 *任何* 链接都是最简单的共享方式：组织外部的人员可以在不进行身份验证的情况下打开链接，并且可以自由地将其传递给其他人。

对于 SharePoint，选择组织中的任何网站将需要的 "最高" 设置。

![SharePoint 组织级别共享设置的屏幕截图](../media/sharepoint-organization-external-sharing-controls.png)


设置 SharePoint 组织级别的共享设置

1. 在 Microsoft 365 管理中心的左侧导航窗格中，单击 " **管理中心**" 下的 " **SharePoint**"。
2. 在 SharePoint 管理中心中，在左侧导航窗格中的 " **策略**" 下，单击 " **共享**"。
3. 确保将 SharePoint 或 OneDrive 的外部共享设置为 " **任何人** " 或 **新的和现有的来宾**。  (请注意，OneDrive 设置不能比 SharePoint 设置更许可。 ) 
4. 如果进行了任何更改，请单击 **“保存”**。

## <a name="sharepoint-organization-level-default-link-settings"></a>SharePoint 组织级别的默认链接设置

默认的文件和文件夹链接设置确定在用户共享文件或文件夹时，默认情况下将向用户显示的链接选项。 如果需要，用户可以在共享之前将链接类型更改为其他选项之一。

请注意，此设置会影响组织中的 SharePoint 网站以及 OneDrive。

从以下任何类型中选择一个链接，当用户共享文件和文件夹时，默认情况下会选择该链接：

- **任何具有链接的人** -如果您想要执行大量未经身份验证的文件和文件夹共享，请选择此选项。 如果要允许 *任何人* 链接，但担心意外的共享，请考虑其他选项之一作为默认选项。 仅当您已启用 **任何** 共享时，此链接类型才可用。
- **仅限组织中的人员** -如果您希望大多数文件和文件夹共享与组织内部的人员共享，请选择此选项。
- **特定人员** -如果您希望对来宾执行大量文件和文件夹共享，请考虑此选项。 此类型的链接可与来宾配合使用，并要求用户进行身份验证。
 
![SharePoint 组织级别文件和文件夹共享设置的屏幕截图](../media/sharepoint-organization-files-folders-sharing-settings.png)


设置 SharePoint 和 OneDrive 组织级默认链接设置

1. 导航到 SharePoint 管理中心中的 "共享" 页面。
2. 在 " **文件和文件夹链接**" 下，选择要使用的默认共享链接。
3. 如果进行了任何更改，请单击 **“保存”**。

若要设置共享链接的权限，请在 " **选择默认情况下为共享链接选择的权限" 下。**

1. 如果不希望未经身份验证的用户对文件和文件夹进行更改，请选择 " **查看** "。
2. 如果要允许未经身份验证的用户对文件和文件夹进行更改，请选择 " **编辑** "。

请注意，以上两个 premission 选项不仅可用于来宾/外部用户，而且适用于内部用户。 您选择的权限选项由自行决定决定。

设置允许与任何人共享的链接的权限

1. 在 " **以下链接可以提供这些权限：** " 子窗格中， 
    1. 从 " **文件** " 下拉列表中， 
        1. 如果要允许未经身份验证的用户对文件进行更改，请选择 " **查看和编辑** "。
        2. 如果不希望未经身份验证的用户对文件进行更改，请选择 " **查看** "。
    2. 从 " **文件夹** " 下拉列表中，
        1. 如果您希望允许未经身份验证的用户对文件夹进行更改，请选择 **"查看、编辑和上传** "。
        2. 如果不希望未经身份验证的用户对文件夹进行更改，请选择 " **查看** "。

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint 网站级别的共享设置

如果要共享 SharePoint 网站中的文件和文件夹，则还需要检查该网站的网站级共享设置。

![SharePoint 网站外部共享设置的屏幕截图](../media/sharepoint-site-external-sharing-settings.png)

设置网站级共享设置

1. 在 SharePoint 管理中心中，在左侧导航窗格中，展开 " **网站** "，然后单击 " **活动网站**"。
2. 选择要在其上与来宾共享文件和文件夹的网站。
3. 在所选网站所在行 (中向右滚动) 并单击 " **外部共享** " 列中的任意位置。
4. 从弹出的页面中，单击 " **策略** " 选项卡。
5. 在 " **外部共享** " 窗格中，单击 " **编辑**"。
6. 确保将 "共享" 设置为 " **任何人** " 或 " **新的和现有的来宾**"。
7. 如果进行了任何更改，请单击 **“保存”**。

## <a name="invite-users"></a>邀请用户

现在已配置来宾共享设置;因此，用户现在可以与组织外部的人员共享文件和文件夹。 有关详细信息，请参阅 [共享 OneDrive 文件和文件夹](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) 以及 [共享 SharePoint 文件或文件夹](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) 。

## <a name="see-also"></a>另请参阅

[有关与未经认证用户共享文件和文件夹的最佳做法](best-practices-anonymous-sharing.md)

[与来宾共享时限制文件意外曝光](share-limit-accidental-exposure.md)

[与 Azure AD B2B 的 SharePoint 和 OneDrive 集成](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
