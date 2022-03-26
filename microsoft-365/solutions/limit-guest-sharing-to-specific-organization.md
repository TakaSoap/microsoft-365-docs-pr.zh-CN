---
title: 将来宾共享限制为特定组织
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: 了解如何将来宾共享限制为特定组织Azure AD Microsoft 365共享。
ms.openlocfilehash: 75cfe739e1cdde2e0bd959382b2444487ea726be
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2022
ms.locfileid: "63715987"
---
# <a name="limit-guest-sharing-to-specific-organizations"></a>将来宾共享限制为特定组织

默认情况下，用户可以邀请组织外部人员作为来宾。 这包括邀请他们访问 Microsoft Team 中的团队、SharePoint网站，以及与用户共享单个文件和文件夹。

如果你仅希望用户邀请来自特定组织的来宾，可以在 [B2B](/azure/active-directory/external-identities/what-is-b2b) 协作的跨Azure Active Directory访问设置中指定这些组织。

## <a name="configure-cross-tenant-access-settings"></a>配置跨租户访问设置

限制来宾共享的第一步是更改跨租户Azure AD中的默认设置，以默认阻止邀请来宾。 然后，你可以为特定组织允许来宾邀请。

> [!NOTE]
> 对跨租户访问设置所做的更改可能需要两个小时才能生效。

### <a name="set-the-default-b2b-collaboration-settings-to-block-inviting-guests"></a>设置默认 B2B 协作设置以阻止邀请来宾

由于默认情况下会启用邀请来宾功能，因此限制对特定组织的来宾邀请需要默认阻止入站 B2B 协作。

默认情况下阻止入站 B2B 协作
1. 使用全局[Azure Active Directory](https://aad.portal.azure.com)或安全管理员帐户登录登录。
1. 选择 **"外部标识"**，然后选择"跨租户访问设置 (**预览)**。
1. 选择" **默认设置"** 选项卡。
1. 在 **"入站访问设置"** 下， **选择"编辑入站默认值"**。
1. 选择 **"B2B 协作"** 选项卡和" **用户和组"** 选项卡。
1. 在 **"访问状态"** 下，选择" **阻止访问"**。
1. 选择" **外部访问"** 选项卡。
1. 在 **"访问状态"** 下，选择" **阻止访问"**。
1. 选择“**保存**”。
1. 关闭" **默认设置"边** 栏选项卡。

### <a name="add-the-organization-where-you-want-to-allow-guest-invitations"></a>添加要允许来宾邀请的组织

接下来，添加要允许用户邀请来宾加入跨租户Azure AD访问列表的组织。

添加组织
1. In [Azure Active Directory](https://aad.portal.azure.com)， select **External Identities**， and then select **Cross-tenant access settings (preview)**.
1. 选择 **"组织设置"**。
1. 选择 **"添加组织"**。
1. 在 **"添加组织** "窗格中，键入组织 (或租户 ID) 的完整域名。
1. 在搜索结果中选择组织，然后选择"添加 **"**。
1. 组织显示在"组织 **设置"** 列表中。

此时，此组织的所有访问设置都是从默认设置继承的。

### <a name="configure-inbound-settings-for-the-organization-to-allow-all-users"></a>配置组织的入站设置以允许所有用户

添加组织后，需要更新组织的入站设置，以允许 B2B 协作用户作为来宾受邀。 为希望用户能够邀请来宾的每个组织执行这一点。

1. In [Azure Active Directory](https://aad.portal.azure.com)， select **External Identities**， and then select **Cross-tenant access settings (preview)**.
1. 为要修改的组织选择入站访问链接。
1. 在" **B2B 协作"选项卡上** ，选择" **自定义设置"**。
1. 在 **"访问状态"** 下，选择 **"允许访问"**。
1. 在 **"目标**"下，选择"允许所有用户"。
1. 选择 **"保存** "并关闭 **"出站访问设置"** 边栏选项卡。

## <a name="turn-off-one-time-passcode-authentication"></a>关闭一次密码身份验证

即使将 B2B 协作仅限于某些组织，用户仍可与其他组织的人共享文件和文件夹，只是不会在你的目录中获得来宾帐户。

如果希望完全阻止与其他组织共享，您必须在密码管理中禁用一Azure AD。 这将阻止向组织外部的用户发送一次密码，用于对共享文件或文件夹进行身份验证。

禁用电子邮件一次密码功能
1. 以 Azure AD 全局管理员身份登录到 [Azure 门户](https://portal.azure.com/)。
1. 在导航窗格中选择“**Azure Active Directory**”。
1. 选择 **"外部标识** > **""所有标识提供程序"**。
1. 选择 **"** 电子邮件一次密码"，然后在"为来宾发送电子邮件一次密码"下，选择"禁用来宾的电子邮件一次 **密码 ("** 或"否"（如果该功能之前在预览版) 期间已启用、禁用或选择加入）。
1. 选择“**保存**”。

## <a name="related-topics"></a>相关主题

[B2B 直接连接概述](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[为 B2B 直接连接配置跨租户访问设置](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[限制组织可以邀请的人](limit-invitations-from-specific-organization.md)

[限制用户可以拥有来宾帐户的组织](limit-organizations-where-users-have-guest-accounts.md)