---
title: 限制组织可以邀请的人
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
description: 了解如何限制哪些用户作为来宾或共享频道参与者受邀加入特定组织。
ms.openlocfilehash: 599f83a4464498f7a964f02a955f802cb8545432
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2022
ms.locfileid: "63715986"
---
# <a name="limit-who-can-be-invited-by-an-organization"></a>限制组织可以邀请的人

如果您与其他组织协作，并且希望限制作为 Teams 中的来宾或共享频道成员受邀加入该组织的人，可以在 Azure Active Directory 中的跨租户访问设置中指定可受邀者。

> [!NOTE]
> 对跨租户访问设置所做的更改可能需要两个小时才能生效。

## <a name="create-a-security-group"></a>创建安全组

指定可邀请加入另一个组织人员的最简单方法是使用安全组。 可以将安全组与定义的成员身份或动态安全组一同使用。 可以使用现有安全组或为此创建新安全组。

创建安全组
1. 使用全局[Azure Active Directory](https://aad.portal.azure.com)或安全管理员帐户登录登录。
1. 在 **"Active Directory"** 页上，选择" **组"** ，然后选择" **新建组"**。
1. 为 **组** 类型 **选择"安全性"**。
1. 键入 **组名称。** 
1. （可选）为组添加说明。
1. For **Azure AD roles can be assigned to the group**， choose **No**.
1. 选择预定义的成员资格 **类型 (所需的)**。
1. 如果使用的是动态用户成员资格 [，请添加](/azure/active-directory/enterprise-users/groups-dynamic-membership) 组所有者和成员或动态查询。
1. 选择“**创建**”。 组已创建，可供你添加成员。

## <a name="add-an-organization"></a>添加组织

若要定义与其他组织的协作规则，您必须将该组织添加到跨Azure AD访问设置。 如果尚未添加组织，请按照此过程进行添加。

添加组织
1. In [Azure Active Directory](https://aad.portal.azure.com)， select **External Identities**， and then select **Cross-tenant access settings (preview)**.1. 选择 **"组织设置"**。
1. 选择 **"添加组织"**。
1. 在 **"添加组织** "窗格中，键入组织 (或租户 ID) 的完整域名。
1. 在搜索结果中选择组织，然后选择"添加 **"**。
1. 组织显示在"组织 **设置"** 列表中。 此时，此组织的所有访问设置都是从默认设置继承的。

## <a name="choose-who-can-be-invited-by-an-organization"></a>选择组织可以邀请谁

有两个选项可用于限制可受邀加入组织的人：

- 限制可邀请作为来宾的人。 这将阻止将用户作为来宾添加到Azure AD组织的用户。 它阻止与不在安全Microsoft 365人员共享文件、文件夹、网站、团队和组。
- 限制可添加到外部共享频道的人。 这可以防止不在安全组内的人被添加到另一个组织的共享频道。

In [Azure Active Directory](https://aad.portal.azure.com)， select **External Identities**， and then select **Cross-tenant access settings (preview)**.

限制可邀请作为来宾的来宾
1. 选择要修改的组织的出站访问链接。
1. 在" **B2B 协作"选项卡上** ，选择" **自定义设置"**。
1. 在 **"访问状态"** 下，选择 **"允许访问"**。
1. 在 **"目标**"下 **，选择"选择外部用户和组"**。
1. 选择链接以添加用户和组。
1. 搜索并选择想要使用的安全组。
1. 选择“**选择**”。
1. 选择 **"保存** "并关闭 **"出站访问设置"** 边栏选项卡。


限制可邀请为共享频道参与者的人
1. 选择要修改的组织的出站访问链接。
1. 在 **"B2B 直接连接"选项卡上** ，选择" **自定义设置"**。
1. 在 **"访问状态"** 下，选择 **"允许访问"**。
1. 在 **"目标**"下 **，选择"选择外部用户和组"**。
1. 选择链接以添加用户和组。
1. 搜索并选择想要使用的安全组。
1. 选择“**选择**”。
1. 选择 **"保存** "并关闭 **"出站访问设置"** 边栏选项卡。

## <a name="related-topics"></a>相关主题

[B2B 直接连接概述](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[为 B2B 直接连接配置跨租户访问设置](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[限制用户可以拥有来宾帐户的组织](limit-organizations-where-users-have-guest-accounts.md)

[将来宾共享限制为特定组织](limit-guest-sharing-to-specific-organization.md)