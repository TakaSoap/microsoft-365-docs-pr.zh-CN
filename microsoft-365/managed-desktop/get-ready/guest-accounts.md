---
title: 来宾帐户的先决条件
description: 来宾帐户的配置指南以及如何调整它们
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 80770c6c122cc4e2892c22a43f185ffbac40c637
ms.sourcegitcommit: cafca45069819a44c7cf8c67f6c1e105de1b3393
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2022
ms.locfileid: "62520406"
---
# <a name="prerequisites-for-guest-accounts"></a>来宾帐户的先决条件

## <a name="external-collaboration-settings"></a>外部协作设置

Microsoft 托管桌面为来宾帐户访问Azure AD以下配置。 可以在 Azure 门户的"外部标识 [](https://portal.azure.com)**/外部协作设置"下调整这些设置**：

| 设置 | 设置为 |
| ------ | ------ |
| 来宾访问权限 | 来宾对目录对象的属性和成员身份具有有限的访问权限。 |
| 来宾邀请设置 | 分配给特定管理员角色的成员用户和用户可以邀请来宾，包括具有成员权限的来宾 |

Microsoft 托管桌面组织需要以下配置Azure AD来宾帐户访问。 可以在 Azure 门户的"外部标识 [](https://portal.azure.com)**/外部协作设置"下调整此设置**：

| 设置 | 选项 |
| ------ | ------ |
| 协作限制 | 选择以下任一选项： <ul><li>如果选择" **允许邀请发送到任何域"， (包含**) ，则无需其他配置。</li><li>如果选择" **拒绝对指定** 域的邀请"，请确保 Microsoft.com 未在目标域中列出。</li><li>如果选择"**仅允许** 对限制最严格的 (域) "，请确保 Microsoft.com 列出该域。</li><ul>

如果设置与这些设置交互的限制，请确保排除Azure Active Directory **工作区服务帐户**。 例如，如果你有一个阻止来宾帐户访问 Intune 门户的条件访问策略，则从此策略中排除 **Modern Workplace Service Accounts** 组。

有关详细信息，请参阅启用 [B2B 外部协作并管理可以邀请来宾的人](/azure/active-directory/external-identities/delegate-invitations#to-configure-external-collaboration-settings)。

## <a name="unlicensed-intune-admin"></a>未授权 Intune 管理员

必须 **启用"允许访问未授权的管理员** "设置。 如果没有启用此设置，当我们尝试访问你的组织服务时Azure AD错误。 你可以安全地启用此设置，而无需担心安全隐患。 访问范围由分配给用户的角色（包括我们的运营人员）定义。

**若要启用此设置：**

1. 转到管理Microsoft Endpoint Manager[中心](https://go.microsoft.com/fwlink/?linkid=2109431)。
2. 导航到 **租户管理，****选择角色。** 然后，选择 **"管理员许可"**。
3. 在" **允许访问未授权的** 管理员"部分，选择" **是"**。

> [!IMPORTANT]
> 选择"是"后，无法撤消 **此设置**。

有关详细信息，请参阅未[许可的管理员Microsoft Intune](/mem/intune/fundamentals/unlicensed-admins)。

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>准备使用Microsoft 托管桌面

1. 查看 [托管桌面应用](prerequisites.md)。
1. 运行 [准备情况评估工具](readiness-assessment-tool.md)。
1. 购买 [公司门户](../get-started/company-portal.md)。
1. 查看本文中来宾帐户 (先决条件) 。
1. 检查 [网络配置](network.md)。
1. [准备证书和网络配置文件](certs-wifi-lan.md)。
1. [准备用户对数据的访问权限](authentication.md)。
1. [准备应用](apps.md)。
1. [准备映射的驱动器](mapped-drives.md)。
1. [准备打印资源](printing.md)。
1. 地址 [设备名称](address-device-names.md)。
