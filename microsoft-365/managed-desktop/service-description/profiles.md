---
title: 了解设备配置文件
description: 管理员可以分配给设备的各种配置文件
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: d12a197db8dbcb6356882082c212754fef726d4e
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320825"
---
# <a name="device-profiles"></a>设备配置文件

你可以将设备配置文件视为设备配置选项层次结构的一部分。

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="显示为棱锥的设备配置。说明如下。":::

| 设备配置选项 | 说明
| ----- | ----- |
| 配置 | 最上面是你自己的配置，如网络详细信息或应用程序。 设备可以具有任意数目的这些配置，这些配置不会由Microsoft 托管桌面。 |
| 自定义 | 下一个较高级别是其他 [自定义](customizing.md)项。 每台设备可以具有一个或多个自定义 (或) 自定义。 自定义项可以修改设备配置文件中的 (层或基础配置) ，也可以修改基于标准配置分层的全新的请求。 |
| 设备配置文件 | 每个Microsoft 托管桌面设备必须分配一个且仅分配一个配置文件。 管理员可以选择已分配设备的配置文件。<br><br>你可以为设备分配不同的预设置配置文件。 每个配置文件都针对特定类型的用户的需求进行了优化。 有三个设备配置文件可用：<ul><li>Standard</li><li>敏感数据</li><li>Power user</li> |
| Foundation 版 | 从根本上说，Microsoft 托管桌面设备的基础包括：<br><ul><li>标准安全基线</li><li>合规性策略</li><li>Windows更新设置</li><li>组</li></ul><br>若要使用Microsoft 托管桌面，每个设备必须包含所有这些元素。 管理员无法更改这些元素。 你必须向用户提交Microsoft 托管桌面。 |

## <a name="device-profile-details"></a>设备配置文件详细信息

下表总结了设备配置文件配置的每个设置的设置及其默认值。 在后台，这些设置使用自定义配置文件OMA-URIs中的自定义配置文件来Microsoft Endpoint Manager。

<br>

****

| 功能 | 敏感数据 | Power User | Standard |
| ----- | :-----: | :-----: | :-----: |
|**阻止外部存储**| 是 | 是 | 否 |
|**[云块级别](/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel)**| 高 | 高 | 高 |
|**禁用 Microsoft 帐户**| 是 | 是 | 否 |
|**禁用个人OneDrive**| 是 | 是 | 否 |
|**[切换到安全桌面进行提升](/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-useraccountcontrol-switchtothesecuredesktopwhenpromptingforelevation)**| 否 | 是 | 否 |
|**适用于终结点设备标记的 Microsoft Defender**| M365Managed-SensitiveData | M365Managed-PowerUser | M365Managed-Standard |
|**设备上管理员？**| 否 | 是 | 否 |
|**Autopilot 配置文件**| MMD Standard | MMD Power User | MMD Standard |
|**AppLocker**| 是 | 否 | 否 |
|**阻止公共存储**| 是 | 是 | 否 |
|

每个设备配置文件也涉及以下项：

- 设备组Azure Active Directory成员资格。
- 设备组的Azure Active Directory成员身份。
- 配置Microsoft Endpoint Manager配置文件。

> [!IMPORTANT]
> 不要直接修改这些组的成员身份。 使用"重新分配配置文件"中所述 [的接口](../working-with-managed-desktop/change-device-profile.md)。

## <a name="limitations"></a>限制

你可以像对任何其他策略一样请求设备配置文件及其详细信息的例外。

请记住，你的组织只能有一个设备配置文件Azure Active Directory"租户 (租户) 。 例如，你无法请求敏感数据设备配置文件仅对部分用户禁用 AppLocker。 所有具有敏感数据设备配置文件的设备都必须具有相同的配置。

每台设备只能有一个配置文件。 如果给定设备由多个用户使用，则该设备上的所有用户都将具有相同的配置。
