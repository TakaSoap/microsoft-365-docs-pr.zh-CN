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
ms.openlocfilehash: 9daf0ded219165f692c3e5b1b6512ab264f25d41b2fda97d085a3443cbe506a3
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53819123"
---
# <a name="prerequisites-for-guest-accounts"></a>来宾帐户的先决条件

## <a name="external-collaboration-settings"></a>外部协作设置

Microsoft 托管桌面 Azure AD 组织中需要以下设置来访问来宾帐户。 可以在 Azure 门户的"[](https://portal.azure.com)外部标识 **/外部协作设置"下调整这些设置**：

-   对于 **设置为"成员** 用户"的来宾邀请限制，分配给特定管理员角色的用户可以邀请来宾用户（包括具有 **成员权限的来宾）**
-   对于 **"协作限制"，** 选择以下任一选项：
    -   如果选择" **允许邀请发送到任何非独占 (域) ，** 则无需其他配置。
    -   如果选择" **拒绝对指定** 域的邀请"，请确保 Microsoft.com 未列在目标域中。
    -   如果选择"**仅允许** 对限制最严格的 (域) "，请确保 Microsoft.com 列出该域。 

如果设置与这些设置交互的限制，请确保排除"Azure Active Directory **工作区服务帐户"。** 例如，如果你有一个阻止来宾帐户访问 Intune 门户的条件访问策略，则从此策略中排除 **Modern Workplace Service Accounts** 组。

## <a name="unlicensed-intune-admin"></a>未授权 Intune 管理员

必须 **启用"允许访问未授权的管理员** "设置。 如果没有启用此设置，当我们尝试访问 Azure AD 组织进行服务时，可能会发生错误。 你可以安全地启用此设置，而无需担心安全隐患，因为访问范围由分配给用户的角色（包括我们的运营人员）定义。

若要启用此设置，请按照以下步骤操作：

1. 转到管理Microsoft Endpoint Manager[中心](https://go.microsoft.com/fwlink/?linkid=2109431)。
2. 导航到 **租户管理**  >  **角色**  >  **管理员许可**。
3. 在 **"允许访问未授权的** 管理员"中，选择"**是"。**

> [!IMPORTANT]
> 选择"是"后，无法撤消 **此设置**。

有关详细信息，请参阅未授权的[管理员Microsoft Intune。](/mem/intune/fundamentals/unlicensed-admins)

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
