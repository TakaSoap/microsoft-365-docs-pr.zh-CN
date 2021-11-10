---
title: 在文档中与来宾协作
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
ms.custom:
- seo-marvel-apr2020
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: 本文将了解如何与来宾协作处理 SharePoint 和 OneDrive。
ms.openlocfilehash: 7c58b9ef4fdc759c5afa1920083dd1875fad17f1
ms.sourcegitcommit: 6722f66915dfe30c3d0ade97b3e9080a9592251b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2021
ms.locfileid: "60899626"
---
# <a name="collaborate-with-guests-on-a-document"></a>在文档中与来宾协作

如果需要与组织外部人员协作处理SharePoint或OneDrive文档，您可以向这些人员发送一个指向该文档的共享链接。 本文将介绍为组织设置共享Microsoft 365链接所需的 SharePoint 和 OneDrive 配置步骤。

## <a name="video-demonstration"></a>视频演示

该视频展示了本文档中介绍的配置步骤。</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Azure 外部协作设置

Microsoft 365 中的共享在最高级别由 [Azure Active Directory 中的 B2B 外部协作设置](/azure/active-directory/external-identities/delegate-invitations) 管理。 如果来宾共享在 Azure AD 禁用或受限，则此设置将覆盖在 Microsoft 365 中配置的任何共享设置。

检查 B2B 外部协作设置，确保不会阻止与来宾共享。

![Azure Active Directory 组织关系设置页面的屏幕截图。](../media/azure-ad-organizational-relationships-settings.png)

设置外部协作设置

1. 在 [https://aad.portal.azure.com](https://aad.portal.azure.com) 上登录到 Azure Active Directory。
2. 在左侧导航窗格中，单击 **Azure Active Directory**。
3. 单击 **“外部标识”**。
4. 在 **“入门”** 屏幕的左侧导航窗格中，单击 **“外部协作设置”**。
5. 确保 **选中"** 成员用户"和分配到特定管理员角色的用户可以邀请来宾用户（包括具有成员权限的来宾）或"组织中的任何人 **"可以邀请** 来宾用户（包括来宾和非管理员）。
6. 如果进行了任何更改，请单击 **“保存”**。

请注意 **“协作限制"** 部分的设置。 确保不会阻止要协作来宾的域。

如果与多个组织的来宾合作，可能需要限制其访问目录数据的能力。  这将阻止他们查看目录中的来宾。 为此，在 **“来宾用户访问限制”** 下，选择 **“来宾用户具有对目录对象设置的属性和成员身份的有限访问权限”** 或 **“来宾用户访问仅限于其自己的目录对象的属性和成员身份”**。

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint组织级别的共享设置

为了使组织外部人员能够访问 SharePoint 或 OneDrive 中的文档，SharePoint 和 OneDrive 组织级别的共享设置必须允许与组织外部人员共享。

网站的组织级别SharePoint确定各个网站可用的SharePoint设置。 网站设置不能比组织级别设置更宽松。 用户的组织级别设置OneDrive确定将在用户的管理库中可用的OneDrive级别。

For SharePoint and OneDrive， if you want to allow unauthicated file and folder sharing， choose **Anyone**. 如果希望确保组织外部人员必须进行身份验证，请选择"**新来宾和现有来宾"。** *任何人* 链接是最简单的共享方式：组织外部人员无需身份验证即可打开链接，并可以自由将链接传递给其他人。

对于SharePoint，请选择组织中任何网站所需的最宽松设置。

![SharePoint 组织级别共享设置的屏幕截图。](../media/sharepoint-organization-external-sharing-controls.png)


设置 SharePoint 组织级共享设置

1. 在 Microsoft 365 管理中心左侧导航窗格中的 **“管理中心”** 下，单击 **“SharePoint”**。
2. 在管理SharePoint，在左侧导航窗格中的"策略"**下，单击**"共享 **"。**
3. 确保外部共享或SharePoint OneDrive设置为"任何人"或"**新来宾和现有来宾"。**   (请注意，OneDrive设置不能比设置SharePoint更宽松。) 
4. 如果进行了任何更改，请单击 **“保存”**。

## <a name="sharepoint-organization-level-default-link-settings"></a>SharePoint 组织级别的默认链接设置

默认文件和文件夹链接设置确定在用户共享文件或文件夹时默认向用户显示的链接选项。 如果需要，用户可以在共享之前将链接类型更改为其他选项之一。

请记住，此设置会影响SharePoint网站和网站OneDrive。

从以下任一类型中选择一个链接，然后在用户共享文件和文件夹时默认选择该链接：

- **具有链接的** 任何人 - 如果希望执行大量未经身份验证的文件和文件夹共享，请选择此选项。 如果希望允许 *“任何人”* 链接，但担心意外的未经身份验证的共享，请考虑使用其他选项之一作为默认选项。 此链接类型仅在启用 **”任何人“** 共享时可用。
- **仅组织内部人员** - 如果希望大多数文件和文件夹共享是与组织内部人员共享，请选择此选项。
- **特定人员** - 如果希望与来宾进行大量文件和文件夹共享，请考虑此选项。 此类链接适用于来宾，且要求他们进行身份验证。
 
![SharePoint 组织级别文件和文件夹共享设置的屏幕截图。](../media/sharepoint-organization-files-folders-sharing-settings.png)


设置网站SharePoint OneDrive组织级别的默认链接设置

1. 导航到 SharePoint 管理中心的"共享"页面。
2. 在 **“文件夹链接”** 下，选择要使用的默认共享链接。
3. 如果进行了任何更改，请单击 **“保存”**。

若要设置共享链接的权限，在"选择默认为共享链接 **选择的权限"下。**

1. 如果 **不希望** 未经身份验证的用户对文件和文件夹进行更改，请选择"查看"。
2. 如果要 **允许** 未经身份验证的用户对文件和文件夹进行更改，请选择"编辑"。

请注意，上述两个预提交选项不仅适用于来宾/外部用户，还可以应用于内部用户。 您选择的权限选项由自行决定。

设置允许与任何人共享的链接的权限

1. 在" **这些链接可以授予以下权限"下：** 子窗格 
    1. 从 **"文件** "下拉列表中， 
        - 如果要 **允许未经** 身份验证的用户对文件进行更改，请选择"查看和编辑"。
        - 如果您 **不希望** 未经身份验证的用户对文件进行更改，请选择"查看"。
    2. 从 **"文件夹** "下拉列表中，
        - 如果要 **允许未经身份验证的用户** 对文件夹进行更改，请选择"查看、编辑和上载"。
        - 如果 **不希望** 未经身份验证的用户对文件夹进行更改，请选择"查看"。

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint 网站级别共享设置

如果要共享网站中的文件和文件夹SharePoint，还需要检查该网站的网站级别共享设置。

![SharePoint 网站外部共享设置的屏幕截图。](../media/sharepoint-site-external-sharing-settings.png)

设置网站级别共享设置

1. 在 SharePoint 管理中心的左侧导航栏中，展开 **“网站”**，然后单击 **“活动网站”**。
2. 选择要与来宾共享文件和文件夹的网站。
3. 在选定网站 (行中向右滚动，) "外部共享"列中 **的任意位置** 单击。
4. 在弹出的页面中，单击"策略 **"** 选项卡。
5. 在"外部 **共享"窗格下**，单击"编辑 **"。**
6. 确保将共享设置为 **“任何人”** 或 **“新来宾和现有来宾”**。
7. 如果进行了任何更改，请单击 **“保存”**。

## <a name="invite-users"></a>邀请用户

来宾共享设置现已配置;以便用户现在可以与组织外部人员共享文件和文件夹。 有关详细信息[，OneDrive共享文件和文件夹SharePoint](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07)[共享文件或](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c)文件夹。

## <a name="see-also"></a>另请参阅

[有关与未经认证用户共享文件和文件夹的最佳做法](best-practices-anonymous-sharing.md)

[与来宾共享时限制文件意外曝光](share-limit-accidental-exposure.md)

[SharePoint 和 OneDrive 与 Azure AD B2B 的集成](/sharepoint/sharepoint-azureb2b-integration-preview)
