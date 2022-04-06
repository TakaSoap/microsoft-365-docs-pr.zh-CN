---
title: 在频道中与外部参与者协作
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
localization_priority: Priority
f1.keywords: NOCSH
recommendations: false
description: 了解如何与组织外部的人员使用共享频道。
ms.openlocfilehash: 9fa58be15eab0844fa92d408320902c23f36de93
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468877"
---
# <a name="collaborate-with-external-participants-in-a-channel"></a>在频道中与外部参与者协作

如果要允许用户在 [共享频道](/MicrosoftTeams/shared-channels) 中与组织外部的人员协作，则需要为要与之协作的每个组织配置 B2B 直接连接。(或者，可以 [与所有外部组织启用共享频道](/microsoft-365/solutions/allow-direct-connect-with-all-organizations)。)

启用与其他组织的共享频道时：

- 组织中的团队所有者将能够邀请其他组织中的人员参与共享频道。
- 你所在组织的自定义（业务线）应用将在共享频道中可用，因此外部参与者将能够访问它们。
- 你所在组织的应用列表将在共享频道中可用，因此外部参与者将能够访问它们。

> [!NOTE]
> 共享频道处于预览状态，并且需要你已配置 [Microsoft Teams 公共预览版](/MicrosoftTeams/public-preview-doc-updates)。 如果计划与其他组织共享频道，他们还必须配置 Teams 公共预览版。

## <a name="enable-shared-channels-in-teams"></a>在 Teams 中启用共享频道

默认情况下 Teams 中的共享频道处于启用状态。 请按照此过程确认设置。

配置共享频道
1. 在 [Teams 管理中心](https://admin.teams.microsoft.com/) 内，展开“**Teams**”，然后选择“**Teams 策略**”。
1. 选择要为其启用共享通道的策略，然后选择“**编辑**”。
1. 选择希望启用的选项：
    - 如果要允许团队所有者创建共享频道，请启用“**创建共享频道**”。
    - 要允许团队所有者与组织外部的人员共享共享频道，请启用“**与外部共享共享频道**”。
    - 要允许用户受邀加入其他组织的共享频道，请启用“**可受邀加入外部共享频道**”。
1. 选择“**应用**”。

## <a name="configure-cross-tenant-access-settings-in-azure-ad"></a>在 Azure AD 中配置跨租户访问设置

默认情况下，Azure AD B2B 直接连接处于禁用状态。 要在共享频道中启用与其他组织的人员协作，必须：

1. [添加组织](#add-an-organization)。
1. 为组织 [配置入站设置](#configure-inbound-settings)，以允许组织中的用户可受邀加入共享频道。
1. 为组织 [为配置出站设置](#configure-outbound-settings)，以允许用户受邀加入其他组织的共享频道。

作为此配置的一部分，我们将启用 **Office 365** 应用程序，其中包括 Teams 和 Teams 集成服务（如 SharePoint）。

> [!NOTE]
> 对跨租户访问设置的更改可能需要两个小时才能生效。

### <a name="add-an-organization"></a>添加组织

添加要与其参与共享频道的每个组织。

添加组织
1. 使用全局管理员或安全管理员帐户登录到 [Azure Active Directory](https://aad.portal.azure.com)。
1. 选择“**外部标识**”，然后选择“**跨租户访问设置（预览）**”。
1. 选择“**组织设置**”。
1. 选择“**添加组织**”。
1. 在“**添加组织**”窗格中，键入组织的完整域名（或租户 ID）。
1. 在搜索结果中选择组织，然后选择“**添加**”。
1. 组织将显示在“**组织设置**”列表中。 此时，此组织的所有访问设置都继承自默认设置。

### <a name="configure-inbound-settings"></a>配置入站设置

对于要在其中邀请外部参与者的每个组织，请按照此过程操作。

为组织配置入站设置
1. 在 [Azure Active Directory](https://aad.portal.azure.com) 中，选择“**外部标识**”，然后选择“**跨租户访问设置（预览）**”。
1. 选择要修改的组织的入站访问链接。
1. 在“**B2B 直接连接**”选项卡上，选择“**自定义设置**”。
1. 在“**外部用户和组**”选项卡上，选择“**允许访问**”和“**所有用户和组**”。 (如果要限制对特定用户和组的访问，例如已签署保密协议的用户和组，可以选择 **选择外部用户和组**。)
1. 在“**应用程序**”选项卡上，选择“**允许访问**”和“**选择应用程序**”。
1. 选择“**添加 Microsoft 应用程序**”。
1. 选择“**Office 365**”应用程序，然后选择“**选择**”。
1. 选择“**保存**”并关闭“**出站访问设置**”边栏选项卡。

### <a name="configure-outbound-settings"></a>配置出站设置

对于希望用户能够在其中参与外部共享频道的每个组织，请按照此过程操作。

为组织配置出站设置
1. 在 [Azure Active Directory](https://aad.portal.azure.com) 中，选择“**外部标识**”，然后选择“**跨租户访问设置（预览）**”。
1. 选择要修改的组织的出站访问链接。
1. 在“**B2B 直接连接**”选项卡上，选择“**自定义设置**”。
1. 在“**外部用户和组**”选项卡上，选择“**允许访问**”并设置所有用户的“**目标**”。
1. 在“**外部应用程序**”选项卡上，选择“**允许访问**”和“**选择外部应用程序**”。
1. 选择“**添加 Microsoft 应用程序**”。
1. 选择“**Office 365**”应用程序，然后选择“**选择**”。
1. 选择“**保存**”并关闭“**出站访问设置**”边栏选项卡。

## <a name="see-also"></a>另请参阅

[B2B 直接连接概述](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[配置 B2B 直接连接的跨租户访问设置](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[限制组织可以邀请的人员](limit-invitations-from-specific-organization.md)

[共享频道限制](/MicrosoftTeams/shared-channels#shared-channel-limits)
