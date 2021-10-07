---
title: 访问管理门户
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
description: 如何查找和使用管理门户，包括控制对管理门户的访问。
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: d0444b1ad169619f2dfbe79b7b42ad8849f4736d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60188897"
---
# <a name="access-the-admin-portal"></a>访问管理门户

您的网关连接到 Microsoft 托管桌面[服务Microsoft Endpoint Manager。](https://endpoint.microsoft.com/) 如果你不熟悉此门户的设备管理功能，请参阅Microsoft Endpoint Manager[文档](/mem/)。

> [!NOTE]
> 在[Microsoft Endpoint Manager](https://endpoint.microsoft.com/)支持以下浏览器：
> - Microsoft Edge (最新版本) 
> - Safari (最新版本，仅 Mac) 
> - Chrome (最新版本) 
> - Firefox (最新版本) 

管理帐户将需要特定权限才能访问Microsoft 托管桌面管理Microsoft Endpoint Manager。 可以使用基于角色的访问控制在组织中管理对这些功能的管理员访问权限。 Azure AD Azure Active Directory (多个) 管理员角色和内置 Microsoft 托管桌面 角色可用于更精细地控制 Microsoft 托管桌面 管理门户中的不同功能。 有关角色Azure Active Directory，请参阅[Azure AD 内置角色](/azure/active-directory/roles/permissions-reference)。 与应用于各种 Microsoft 产品和服务的 Azure AD 管理员角色不同，内置角色特定于 Microsoft 托管桌面 并且仅保证访问此服务的管理员功能。 管理员可以单独或结合 Azure AD 管理员角色向用户分配内置角色，Microsoft 托管桌面现有管理员帐户的权限。

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Azure Active Directory具有访问权限Microsoft 托管桌面角色

|Azure AD 角色  |Microsoft 托管桌面权限  |
|---------|---------|
|全局管理员     | 具有此角色的 **管理员将拥有** 对管理门户中所有功能的Microsoft 托管桌面权限。         |
|全局读取者     | 具有此角色的管理员将拥有对管理 **门户中** 所有功能的只读Microsoft 托管桌面权限。         |
|Intune 服务管理员     |  具有此角色的 **管理员将在管理** 门户中对与安全不相关的功能Microsoft 托管桌面权限。       |
|服务支持管理员     | 具有此角色的 **管理员将具有** 对与安全不相关的功能的只读权限，并且具有在管理门户中管理支持请求Microsoft 托管桌面写入权限。         |
|安全管理员 | 具有此角色的 **管理员将拥有** 针对所有功能的只读权限，并且对管理门户中安全相关Microsoft 托管桌面写入权限。 |
|安全信息读取者 |具有此角色的管理员将拥有对管理 **门户中** 所有功能的只读Microsoft 托管桌面权限。|

如果需要有关分配角色Azure Active Directory帮助，请参阅[Azure AD 内置角色](/azure/active-directory/roles/permissions-reference)。

> [!IMPORTANT]
> 只有全局管理员角色才具有必要的权限，才能在组织中注册Microsoft 托管桌面。 请注意，Azure Active Directory角色将为用户帐户提供跨各种Microsoft 服务。 完成注册Microsoft 托管桌面，应始终使用具有完成其他任务所需的最小特权的角色。 

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>由用户提供的内置Microsoft 托管桌面


|内置角色  |Microsoft 托管桌面权限  |
|---------|---------|
|Microsoft 托管桌面服务管理员  | 分配给用户时，此角色授予管理员对与管理门户中与安全不相关的功能的Microsoft 托管桌面权限。  |
|Microsoft 托管桌面服务读者 | 当分配给用户时，此角色向管理员授予对管理员门户中与安全不相关的功能的只读Microsoft 托管桌面权限。 |
|Microsoft 托管桌面安全管理器 |分配给用户时，此角色仅向管理员授予对管理门户中与安全相关的Microsoft 托管桌面权限。   |

> [!NOTE]
> 安全功能包括与安全相关的通信、安全联系人的管理、安全相关支持请求的管理以及安全相关报告的访问权限。 

### <a name="assigning-built-in-roles-to-user"></a>向用户分配内置角色

为了轻松管理内置角色，每个自定义角色都有一个安全组，其名称为"新式工作区角色 _-_ 角色名称" (例如，"新式工作区角色 – 安全管理器") 。 若要将用户分配到其中一个安全组，请按照以下步骤操作：
1. 转到Microsoft Endpoint Manager门户。
2. 选择 **左侧** 的"组"。
3. 搜索 **"现代工作区角色**"，然后选择与要分配的角色关联的组。 
4. 选择 **左侧** 的"成员"，然后在命令栏上选择 **"+** 添加成员"。
5. 输入要添加的人的电子邮件。 如果他们是来宾，必须先邀请他们，然后才能分配组。
6. 选择 **底部的** "选择"。

> [!NOTE]
> 当前不支持嵌套角色分配安全组。 

### <a name="assigning-built-in-roles-to-groups"></a>向组分配内置角色

如果需要将一个或多个内置角色分配给现有组，请按照以下步骤操作：

1. 转到["portal.azure.com"。](https://portal.azure.com/)
2. 搜索并打开 **Enterprise应用程序**。
3. 将"**应用程序类型"** 筛选器更改为 _"Microsoft 应用程序"，_ 然后选择"应用 **"。**
4. 搜索并选择"_现代工作场所客户 API"。_
5. 从 **左侧窗格中** 选择"用户和组"，然后选择 **"+ 添加用户/组"。**
6. 从用户和组搜索 **你需要的组**。
7. 从"选择角色" **中搜索适用的角色**，然后选择它。
8. 选择“**分配**”。

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>开始使用 Microsoft 托管桌面

1. 访问管理门户 (本文) 。
1. [在管理门户中添加和验证管理员联系人](add-admin-contacts.md)。
1. [注册后调整设置](conditional-access.md)。
1. 部署并分配 [Intune 公司门户](company-portal.md)。
1. [分配许可证](assign-licenses.md)。
1. [部署应用](deploy-apps.md)。
1. [设置设备](set-up-devices.md)。
1. 设置 [使用 Autopilot 和注册状态页的首次运行体验](esp-first-run.md)。
1. [启用用户支持功能](enable-support.md)。
1. [让用户做好使用设备的准备](get-started-devices.md)。
1. [开始使用应用控制](get-started-app-control.md)。