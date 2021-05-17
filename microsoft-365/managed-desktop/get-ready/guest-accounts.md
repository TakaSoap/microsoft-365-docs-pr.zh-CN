---
title: 来宾帐户的先决条件
description: 来宾帐户的配置指南以及如何调整它们
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: bbf679a01716fc48d37b241d69740f50a985f048
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574603"
---
# <a name="prerequisites-for-guest-accounts"></a>来宾帐户的先决条件

Microsoft 托管桌面 Azure AD 组织中需要以下设置来访问来宾帐户。 可以在 Azure 门户的"[](https://portal.azure.com)外部标识 **/外部协作"下调整这些设置**：

-   **具有来宾邀请者角色的管理员和用户可以将邀请设置为****"是"**
-   对于 **"协作限制"，** 选择以下任一选项：
    -   如果选择" **允许邀请发送到任何非独占 (域) ，** 则无需其他配置。
    -   如果选择" **拒绝对指定** 域的邀请"，请确保 Microsoft.com 未列在目标域中。
    -   如果选择"**仅允许** 对限制最严格的 (域) "，请确保 Microsoft.com 列出该域。 

如果设置与这些设置交互的限制，请确保排除"Azure Active Directory **工作区服务帐户"。** 例如，如果你有一个阻止来宾帐户访问 Intune 门户的条件访问策略，则从此策略中排除 **Modern Workplace Service Accounts** 组。

## <a name="steps-to-get-ready"></a>准备步骤

1. 查看 [托管桌面应用](prerequisites.md)。
2. 使用 [准备情况评估工具](readiness-assessment-tool.md)。
3. [来宾帐户帐户 (](guest-accounts.md) 本文) 
4. [Microsoft 托管桌面的网络配置](network.md)
5. [为 Microsoft 托管桌面准备证书和网络配置文件](certs-wifi-lan.md)
6. [为 Microsoft 托管桌面准备本地资源访问权限](authentication.md)
7. [Microsoft 托管桌面中的应用](apps.md)
8. [为 Microsoft 托管桌面准备映射的驱动器](mapped-drives.md)
9. [为 Microsoft 托管桌面准备打印资源](printing.md)