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
localization_priority: Normal
f1.keywords: NOCSH
description: 本文将了解如何与来宾协作处理 SharePoint 和 OneDrive 中的文档。
ms.openlocfilehash: 1b2fe003902b69e4c0c58852af67862ce6f2eb34
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663507"
---
# <a name="collaborate-with-guests-on-a-document"></a>在文档中与来宾协作

如果需要与组织外部人员协作处理 SharePoint 或 OneDrive 中的文档，可以发送指向文档的共享链接。 本文将介绍为 SharePoint 和 OneDrive 设置共享链接以满足组织需求所需的 Microsoft 365 配置步骤。

## <a name="video-demonstration"></a>视频演示

此视频演示本文档中所述的配置步骤。</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Azure 外部协作设置

Microsoft 365 中的共享由 Azure Active Directory 中的 [B2B](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)外部协作设置在最高级别管理。 如果在 Azure AD 中禁用或限制来宾共享，此设置将覆盖在 Microsoft 365 中配置的任何共享设置。

检查 B2B 外部协作设置以确保不会阻止与来宾共享。

![Azure Active Directory 组织关系设置页面的屏幕截图](../media/azure-ad-organizational-relationships-settings.png)

设置外部协作设置

1. 登录 Azure Active [https://aad.portal.azure.com](https://aad.portal.azure.com) Directory。
2. 在左侧导航窗格中，单击 **Azure Active Directory。**
3. 单击 **"外部标识"。**
4. 在 **"入门"** 屏幕的左侧导航窗格中，单击 **"外部协作设置"。**
5. 确保 **管理员和来宾邀请** 者角色中的用户可以邀请，**并且成员可以邀请** 都设置为 **"是"。**
6. 如果进行了任何更改，请单击 **“保存”**。

记下"协作限制 **"部分** 中的设置。 确保未阻止要协作的来宾的域。

如果与多个组织的来宾合作，可能需要限制其访问目录数据的能力。 这将阻止他们查看目录中的来宾。 为此，在"来宾用户访问限制"下，选择"来宾用户对目录对象设置的属性和成员身份具有有限访问权限"或"来宾"用户访问仅限于其自己的目录对象的属性和 **成员身份**。

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint 组织级共享设置

为了让组织外部人员能够访问 SharePoint 或 OneDrive 中的文档，SharePoint 和 OneDrive 组织级共享设置必须允许与组织外部人员共享。

SharePoint 的组织级别设置决定了各个 SharePoint 网站可用的设置。 网站设置不能比组织级别的设置更宽松。 OneDrive 的组织级别设置确定将在用户的 OneDrive 库中可用的共享级别。

对于 SharePoint 和 OneDrive，如果要允许未经身份验证的文件和文件夹共享，请选择"任何人 **"。** 如果要确保组织外部人员必须进行身份验证，请选择 **"新来宾"和"现有来宾"。** *任何人* 链接都是最简单的共享方式：组织外部人员无需身份验证即可打开链接，并可以免费将链接传递给其他人。

对于 SharePoint，选择组织中任何网站所需的最宽松设置。

![SharePoint 组织级别共享设置的屏幕截图](../media/sharepoint-organization-external-sharing-controls.png)


设置 SharePoint 组织级共享设置

1. 在 Microsoft 365 管理中心左侧导航窗格中的"管理中心"下，单击 **"SharePoint"。**
2. 在 SharePoint 管理中心的左侧导航窗格中，**在"策略**"下，单击"**共享"。**
3. 确保 SharePoint 或 OneDrive 的外部共享设置为"任何人"**或"****新来宾"和"现有来宾"。**  (请注意，OneDrive 设置不能比 SharePoint 设置更宽松。) 
4. 如果进行了任何更改，请单击 **“保存”**。

## <a name="sharepoint-organization-level-default-link-settings"></a>SharePoint 组织级别的默认链接设置

默认文件和文件夹链接设置确定在用户共享文件或文件夹时默认向用户显示的链接选项。 如果需要，用户可以在共享之前将链接类型更改为其他选项之一。

请记住，此设置会影响您组织的 SharePoint 网站以及 OneDrive。

从以下任一类型中选择一个链接，然后在用户共享文件和文件夹时默认选择该链接：

- **具有链接的任何人** - 如果希望执行大量未经身份验证的文件和文件夹共享，请选择此选项。 如果要允许"任何人 *"* 链接，但担心意外的未经身份验证的共享，请考虑使用其他选项之一作为默认选项。 此链接类型仅在启用了"任何人共享 **"时** 可用。
- **仅组织内部人员** - 如果希望大多数文件和文件夹共享与组织内部人员共享，请选择此选项。
- **特定人员** - 如果你希望与来宾共享大量文件和文件夹，请考虑使用此选项。 此类链接适用于来宾，要求他们进行身份验证。
 
![SharePoint 组织级别文件和文件夹共享设置的屏幕截图](../media/sharepoint-organization-files-folders-sharing-settings.png)


设置 SharePoint 和 OneDrive 组织级别的默认链接设置

1. 导航到 SharePoint 管理中心中的"共享"页面。
2. 在 **"文件和文件夹链接**"下，选择要使用的默认共享链接。
3. 如果进行了任何更改，请单击 **“保存”**。

若要设置共享链接的权限，在"选择默认为共享链接 **选择的权限"下。**

1. 如果您 **不希望** 未经身份验证的用户对文件和文件夹进行更改，请选择"查看"。
2. 如果要 **允许** 未经身份验证的用户对文件和文件夹进行更改，请选择"编辑"。

请注意，上述两个预提交选项不仅适用于来宾/外部用户，还可以应用于内部用户。 您选择的权限选项由自行决定。

设置允许与任何人共享的链接的权限

1. 在 **"这些链接"下，可以授予** 以下权限：子窗格、 
    1. 从 **"文件** "下拉列表中， 
        - 如果要 **允许** 未经身份验证的用户对文件进行更改，请选择"查看和编辑"。
        - 如果您 **不希望** 未经身份验证的用户对文件进行更改，请选择"查看"。
    2. 从 **"文件夹** "下拉列表中，
        - 如果要 **允许** 未经身份验证的用户对文件夹进行更改，请选择"查看、编辑和上载"。
        - 如果您 **不希望** 未经身份验证的用户对文件夹进行更改，请选择"查看"。

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint 网站级共享设置

如果要共享 SharePoint 网站中的文件和文件夹，还需要检查该网站的网站级共享设置。

![SharePoint 网站外部共享设置的屏幕截图](../media/sharepoint-site-external-sharing-settings.png)

设置网站级共享设置

1. 在 SharePoint 管理中心的左侧导航窗格中，展开 **"** 网站"，然后单击 **"活动网站"。**
2. 选择要与来宾共享文件和文件夹的网站。
3. 在选定网站 (的行中向右滚动，) 单击"外部共享"列中 **的** 任意位置。
4. 在弹出的页面中，单击"策略 **"** 选项卡。
5. 在"**外部共享"** 窗格下，单击"**编辑"。**
6. 确保共享设置为"任何人 **"或****"新来宾"和"现有来宾"。**
7. 如果进行了任何更改，请单击 **“保存”**。

## <a name="invite-users"></a>邀请用户

来宾共享设置现已配置;以便用户现在可以与组织外部人员共享文件和文件夹。 有关详细信息[，请参阅"共享 OneDrive 文件和文件夹](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07)["和"共享 SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c)文件或文件夹"。

## <a name="see-also"></a>另请参阅

[有关与未经认证用户共享文件和文件夹的最佳做法](best-practices-anonymous-sharing.md)

[与来宾共享时限制文件意外曝光](share-limit-accidental-exposure.md)

[SharePoint 和 OneDrive 与 Azure AD B2B 集成](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
