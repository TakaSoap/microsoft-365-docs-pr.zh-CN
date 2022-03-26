---
title: 限制用户可以拥有来宾帐户的组织
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
description: 了解如何指定你的用户可以在哪些组织中拥有来宾帐户。
ms.openlocfilehash: 00db14560c491461435e41e30c106c2554d9ad61
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2022
ms.locfileid: "63715980"
---
# <a name="limit-organizations-where-users-can-have-guest-accounts"></a>限制用户可以拥有来宾帐户的组织

默认情况下，Microsoft 365 Azure Active Directory组织可以邀请你的用户作为来宾加入其组织。 这包括邀请他们访问 Microsoft Team 中的团队、SharePoint网站，以及与用户共享单个文件和文件夹。

如果仅希望用户作为来宾参与特定组织，可以在 [B2B](/azure/active-directory/external-identities/what-is-b2b) 协作的跨Azure Active Directory访问设置中指定这些组织。

> [!NOTE]
> 对跨租户访问设置所做的更改可能需要两个小时才能生效。

## <a name="set-the-default-b2b-collaboration-settings-to-block-users-from-being-guests"></a>设置默认 B2B 协作设置以阻止用户成为来宾

由于默认情况下启用作为来宾参与，因此将来宾参与限制到某些组织需要默认阻止出站 B2B 协作。

默认情况下阻止出站 B2B 协作
1. 使用全局[Azure Active Directory](https://aad.portal.azure.com)或安全管理员帐户登录登录。
1. 选择 **"外部标识"**，然后选择"跨租户访问设置 (**预览)**。
1. 选择" **默认设置"** 选项卡。
1. 在 **"出站访问设置"下****，选择"编辑出站默认值"**。
1. 选择 **"B2B 协作"** 选项卡和" **用户和组"** 选项卡。
1. 在 **"访问状态"** 下，选择" **阻止访问"**。
1. 选择" **外部访问"** 选项卡。
1. 在 **"访问状态"** 下，选择" **阻止访问"**。
1. 选择“**保存**”。
1. 关闭" **默认设置"边** 栏选项卡。

## <a name="add-an-organization"></a>添加组织

接下来，将您希望允许用户作为来宾进行协作的组织添加到跨Azure AD访问列表中。

添加组织
1. In [Azure Active Directory](https://aad.portal.azure.com)， select **External Identities**， and then select **Cross-tenant access settings (preview)**.
1. 选择 **"组织设置"**。
1. 选择 **"添加组织"**。
1. 在 **"添加组织** "窗格中，键入组织 (或租户 ID) 的完整域名。
1. 在搜索结果中选择组织，然后选择"添加 **"**。
1. 组织显示在"组织 **设置"** 列表中。

此时，此组织的所有访问设置都是从默认设置继承的。

## <a name="configure-the-organizations-outbound-setting-to-allow-all-users"></a>配置组织的出站设置以允许所有用户

添加组织后，需要更新组织的出站设置，以允许将 B2B 协作用户添加为来宾。 为要允许用户添加为来宾的每个组织执行此操作。

允许用户在组织中使用 B2B 协作来宾
1. In [Azure Active Directory](https://aad.portal.azure.com)， select **External Identities**， and then select **Cross-tenant access settings (preview)**.
1. 选择要修改的组织的出站访问链接。
1. 在" **B2B 协作"选项卡上** ，选择" **自定义设置"**。
1. 在 **"访问状态"** 下，选择 **"允许访问"**。
1. 在 **"目标**"下，选择"允许所有用户"。
1. 选择 **"保存** "并关闭 **"出站访问设置"** 边栏选项卡。

## <a name="related-topics"></a>相关主题

[B2B 直接连接概述](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[为 B2B 直接连接配置跨租户访问设置](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[限制组织可以邀请的人](limit-invitations-from-specific-organization.md)

[将来宾共享限制为特定组织](limit-guest-sharing-to-specific-organization.md)