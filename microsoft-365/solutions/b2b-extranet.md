---
title: 创建有托管来宾的 B2B 外网
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
ms.custom: ''
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: 了解如何使用合作伙伴组织的托管来宾创建 B2B Extranet 站点或团队。
ms.openlocfilehash: ab8bba31538b9e79ed198f65349f14d8211f81f7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60162130"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a>创建有托管来宾的 B2B 外网

可以使用["Azure Active Directory](/azure/active-directory/governance/entitlement-management-overview)管理"创建 B2B Extranet，以与使用"授权管理"Azure Active Directory。 这允许用户在 Extranet 网站或团队中自行注册，并可以通过审批工作流接收访问权限。

通过这种共享协作资源的方法，合作伙伴组织可以帮助维护和批准来宾，从而减少 IT 部门的负担，并允许最熟悉协作协议的人管理用户访问。

本文逐步介绍了创建资源包的步骤 (在这种情况下，创建一个站点或团队) 可通过自助服务访问注册模型与合作伙伴组织共享。 

在开始之前，创建要与合作伙伴组织共享的站点或团队，并启用它进行来宾共享。 有关详细信息 [，请参阅在网站](collaborate-in-site.md) 中与来宾协作或与 [团队中的](collaborate-as-team.md) 来宾协作。 我们还建议您 [查看创建安全的](create-secure-guest-sharing-environment.md) 来宾共享环境，了解可用于在与来宾协作时维护治理策略的安全与合规性功能。

## <a name="license-requirements"></a>许可要求

使用此功能需要一个Azure AD Premium P2许可证。 

专用云（如 Azure Germany 和 Azure China 21Vianet）目前不可用。

## <a name="video-demonstration"></a>视频演示

此视频演示了本文中介绍的过程。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a>连接合作伙伴组织

为了邀请来自合作伙伴组织的来宾，你需要将合作伙伴的域添加为 Azure Active Directory 中的连接组织。

添加已连接的组织
1. 在 ["Azure Active Directory"](https://aad.portal.azure.com)中，单击 **"标识治理"。**
2. 单击"**连接的组织"。**
4. 单击 **"添加已连接的组织"。**
5. 键入组织的名称和说明，然后单击"下一步：**目录 + 域"。**
6. 单击 **"添加目录 + 域"。**
7. 键入要连接的组织的域，然后单击"添加 **"。**
8. 单击 **连接"，** 然后单击"下一 **步： 发起人"。**
9. 添加来自组织或要连接到要批准来宾访问的组织的人员。
10. 单击“**下一步: 评审+创建**”。
11. 查看已选择的设置，然后单击"创建 **"。**

    ![已连接组织页面的屏幕截图Azure Active Directory。](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a>选择要共享的资源

选择要与合作伙伴组织共享的资源的第一步是创建包含这些资源的目录。

创建目录
1. 在 ["Azure Active Directory"](https://aad.portal.azure.com)中，单击 **"标识治理"。**
2. 单击 **"目录"。**
3. 单击 **"新建目录"。**
4. 键入目录的名称和说明，并确保为外部用户启用和启用 **两者** 都设置为 **是**。
5. 单击“**创建**”。

   ![Identity Governance 中的目录页面Azure Active Directory屏幕截图。](../media/identity-governance-catalogs.png)

创建目录后，添加SharePoint要与合作伙伴组织共享的网站或团队。

向目录添加资源
1. 在 Azure AD Identity Governance 中，单击 **"目录"，** 然后单击要添加资源的目录。
2. 单击 **"资源**"，然后单击"**添加资源"。**
3. 选择要包括在 extranet SharePoint团队或网站，然后单击"添加 **"。**

   ![Identity Governance 中的目录资源Azure Active Directory屏幕截图。](../media/identity-governance-catalog-resource.png)

定义要共享的资源后，下一步是创建访问包，该包定义授予合作伙伴用户的访问权限类型以及请求访问的新合作伙伴用户的审批过程。

创建访问包
1. 在 Azure AD Identity Governance 中，单击 **"目录"，** 然后单击要创建访问包的目录。
2. 单击 **"访问程序包**"，然后单击"**新建访问包"。**
3. 键入访问包的名称和说明，然后单击下一步： **资源角色**。
4. 从目录中选择要用于 Extranet 的资源。
5. 对于每个资源，在" **角色** "列中，选择要授予使用 Extranet 的来宾的用户角色。
6. 单击 **"下一步：请求"。**
7. 在 **"可以请求访问的用户"下**，**选择"对于不在目录中的用户"。**
8. 确保已选择 **"特定连接的组织**"选项，然后单击"添加 **目录"。**
9. 选择之前添加的已连接组织，然后单击"选择 **"**
10. 在 **"审批"** 下，**为"需要****审批"选择"是"。**
11. 在 **"第一个审批者**"下，选择之前添加的发起人之一或选择特定用户。
12. 单击 **"添加回退** "并选择回退审批者。
13. 在 **"启用"** 下，选择"**是"。**
14. 单击 **下一步： 生命周期**。
15. Choose the expiration and access review settings that you want to use， and then click **Next： Review + Create**.
16. 查看设置，然后单击"创建 **"。**

    ![Identity Governance 中的访问包屏幕Azure Active Directory屏幕截图。](../media/identity-governance-access-packages.png)

如果你正在与大型组织合作，你可能想要隐藏访问包。 如果包处于隐藏状态，则合作伙伴组织的用户将不会在"我的访问"门户 *上看到该* 包。 相反，必须发送直接链接以注册程序包。 隐藏访问包可以减少不恰当的访问请求数，还有助于保留在合作伙伴组织的门户中组织的可用访问包。

将访问包设置为隐藏
1. 在 Azure AD Identity Governance 中，单击 **"访问程序包"，** 然后单击访问包。
2. 在"**概述"页上**，单击"编辑 **"。**
3. 在 **"属性"** 下，**为"隐藏**"**选择**"是"，然后单击"保存 **"。**

   ![编辑访问包属性屏幕的屏幕截图。](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a>邀请合作伙伴用户

如果将访问包设置为隐藏，则需要向合作伙伴组织发送直接链接，以便他们可以请求访问你的站点或团队。

查找访问门户链接
1. 在 Azure AD Identity Governance 中，单击 **"访问程序包"，** 然后单击访问包。
2. 在" **概述"** 页上，单击"我的访问门户"链接 **的** "复制到 **剪贴板"链接**。

   ![包含访问门户链接的访问包属性的屏幕截图。](../media/identity-governance-access-portal-link.png)

复制链接后，你可以将其与合作伙伴组织的联系人共享，并且他们可以将其发送给协作团队中的用户。

## <a name="see-also"></a>另请参阅

[创建安全的来宾共享环境](create-secure-guest-sharing-environment.md)