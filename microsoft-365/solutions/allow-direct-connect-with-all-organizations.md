---
title: 启用与所有外部组织的共享频道
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
description: 了解如何启用与所有其他组织和组织Microsoft 365 Azure Active Directory频道。
ms.openlocfilehash: 601bfaa825afdaf9ec5addb4b7c7e21804b07cb7
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2022
ms.locfileid: "63715981"
---
# <a name="enable-shared-channels-with-all-external-organizations"></a>启用与所有外部组织的共享频道

虽然在 Teams 中默认启用外部共享通道，Azure Active Directory [B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview) 直接连接的跨租户访问设置也必须配置为在外部共享通道。 默认情况下，这些设置设置为阻止所有组织。

你可以更改 B2B 直接连接默认设置以允许所有组织。 这允许用户在共享频道中协作，而您的组织不必为要协作的每个组织创建单独的配置。  (请注意，你进行协作的组织还必须配置其 B2B 直接连接设置。) 

如果您的组织不需要限制与其他组织的协作，则默认情况下启用所有组织可以节省您单独管理每个组织的时间和复杂性。

> [!NOTE]
> 对跨租户访问设置所做的更改可能需要两个小时才能生效。

## <a name="allow-users-to-invite-people-in-other-organizations-to-participate-in-shared-channels"></a>允许用户邀请其他组织中的人员参与共享频道

默认情况下，您可以允许用户邀请其他组织中的人员使用共享资源（如 Teams 中的共享频道）。

默认情况下允许用户邀请 B2B 直接连接参与者
1. 使用全局[Azure Active Directory](https://aad.portal.azure.com)或安全管理员帐户登录登录。
1. 选择 **"外部标识"**，然后选择"跨租户访问设置 (**预览)**。
1. 在" **默认设置"** 选项卡上的"入站 **访问设置"下**，选择 **"编辑入站默认设置"**。
1. 选择 **"B2B 直接连接"** 选项卡。
1. 在" **用户和组"** 选项卡上的" **访问状态"下**，选择" **允许访问"**。
1. 在" **外部应用程序"** 选项卡上的" **访问状态"下**，选择" **允许访问"**。
1. 选择“**保存**”。
1. 选择" **信任设置"** 选项卡。
1. 选择是否要信任来自其他组织的已加入Azure AD身份验证、兼容设备或混合设备。
1. 选择“**保存**”。
1. 关闭" **默认设置"边** 栏选项卡。

## <a name="allow-users-to-participate-in-shared-channels-in-other-organizations"></a>允许用户参与其他组织中的共享频道

默认情况下，您可以允许用户访问由外部组织托管的资源（例如，Teams共享频道）。

默认情况下允许用户访问其他组织的资源
1. In [Azure Active Directory](https://aad.portal.azure.com)， select **External Identities**， and then select **Cross-tenant access settings (preview)**.
1. 在" **默认设置"** 选项卡上的" **出站访问设置"下**，选择 **"编辑出站默认设置"**。
1. 选择 **"B2B 直接连接"** 选项卡。
1. 在" **用户和组"** 选项卡上的" **访问状态"下**，选择" **允许访问"**。
1. 在" **外部应用程序"** 选项卡上的" **访问状态"下**，选择" **允许访问"**。
1. 选择“**保存**”。
1. 关闭" **默认设置"边** 栏选项卡。

## <a name="related-topics"></a>相关主题

[B2B 直接连接概述](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[为 B2B 直接连接配置跨租户访问设置](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

