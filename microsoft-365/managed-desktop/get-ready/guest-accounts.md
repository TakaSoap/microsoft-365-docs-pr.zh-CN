---
title: 来宾帐户的先决条件
description: 来宾帐户的配置指南以及如何调整它们
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: db07ca3bb7577aed7b334ba21893f6fe026819a0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197133"
---
# <a name="prerequisites-for-guest-accounts"></a>来宾帐户的先决条件

## <a name="external-collaboration-settings"></a>外部协作设置

Microsoft 托管桌面 Azure AD 组织中针对来宾帐户访问推荐以下配置。 可以在 Azure 门户的"[](https://portal.azure.com)外部标识 **/外部协作设置"下调整这些设置**：

-   对于 **"来宾用户访问**"，设置为 **"来宾用户对目录对象的属性和成员身份具有有限访问权限"**
-   对于 **"来宾邀请设置**"，设置为"成员"用户，分配到特定管理员角色的用户可以邀请来宾用户（包括具有 **成员权限的来宾）**

Microsoft 托管桌面 Azure AD 组织中进行以下配置，以访问来宾帐户。 可以在 Azure 门户的"[](https://portal.azure.com)外部标识 **/外部协作设置"下调整此设置**：

-   **协作限制**，选择以下任一选项：
    -   如果选择" **允许邀请发送到任何非独占 (域) ，** 则无需其他配置。
    -   如果选择" **拒绝对指定** 域的邀请"，请确保 Microsoft.com 未在目标域中列出。
    -   如果选择"**仅允许** 对限制最严格的 (域) "，请确保 Microsoft.com 列出该域。 

如果设置与这些设置交互的限制，请确保排除"Azure Active Directory **工作区服务帐户"。** 例如，如果你有一个阻止来宾帐户访问 Intune 门户的条件访问策略，则从此策略中排除 **Modern Workplace Service Accounts** 组。

有关详细信息，请参阅启用 [B2B 外部协作并管理谁可以邀请来宾](/azure/active-directory/external-identities/delegate-invitations#to-configure-external-collaboration-settings)。

## <a name="unlicensed-intune-admin"></a>未授权 Intune 管理员

必须 **启用"允许访问未授权的管理员** "设置。 如果没有启用此设置，当我们尝试访问 Azure AD 组织进行服务时，可能会发生错误。 你可以安全地启用此设置，而无需担心安全隐患，因为访问范围由分配给用户的角色（包括我们的运营人员）定义。

若要启用此设置，请按照以下步骤操作：

1. 转到管理Microsoft Endpoint Manager[中心](https://go.microsoft.com/fwlink/?linkid=2109431)。
2. 导航到 **租户管理**  >  **角色**  >  **管理员许可**。
3. 在 **"允许访问未授权的** 管理员"中，选择"**是"。**

> [!IMPORTANT]
> 选择"是"后，无法撤消 **此设置**。

有关详细信息，请参阅未授权[的管理员Microsoft Intune。](/mem/intune/fundamentals/unlicensed-admins)

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>准备使用Microsoft 托管桌面

1. 查看 [托管桌面应用](prerequisites.md)。
2. 运行 [准备情况评估工具](readiness-assessment-tool.md)。
1. 购买 [公司门户](../get-started/company-portal.md)。
1. 查看本文中来宾帐户 (先决条件) 。
1. 检查 [网络配置](network.md)。
1. [准备证书和网络配置文件](certs-wifi-lan.md)。
1. [准备用户对数据的访问权限](authentication.md)。
1. [准备应用](apps.md)。
1. [准备映射的驱动器](mapped-drives.md)。
1. [准备打印资源](printing.md)。
1. 地址 [设备名称](address-device-names.md)。
