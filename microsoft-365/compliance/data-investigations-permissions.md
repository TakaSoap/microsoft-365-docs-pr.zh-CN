---
title: '为数据调查 (预览分配权限) '
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文介绍如何在 Microsoft 365 中设置使用 "数据调查" 工具所需的权限。
ms.openlocfilehash: 85a800c3e21c270f46de78bdef77d7b7a98e0eca
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285438"
---
# <a name="assign-permissions-for-data-investigations-preview"></a>为数据调查 (预览分配权限) 

若要访问 Office 365 或 Microsoft 365 合规性中心中的数据调查，您需要是 "数据调查人员" 角色组的成员。 若要将成员添加到角色组，您必须是 "组织管理" 角色组的成员，或者在安全 & 合规性中心中为其分配角色管理角色。 在用户成为 "数据调查员" 角色组的成员后，他们可以在您所属的数据调查中创建、访问和执行调查。

分配数据调查权限：

1. 转到 [https://protection.office.com](https://protection.office.com) 并使用组织中的管理员帐户的凭据登录。

2. 在安全 & 合规中心中，单击 " **权限**"。

3. 单击 " **数据调查** 人员" 角色组，然后在弹出页面上的 " **成员** " 旁边，单击 " **编辑**"。

4. 单击 " **选择成员** "，然后单击 " **添加**"。 选择要添加为数据调查人员的用户，然后单击 " **添加**"。

5. 添加所有用户后，单击 " **完成** "，然后单击 " **保存** " 以保存对角色组所做的更改。

> [!NOTE]
> 分配给 "数据调查人员" 角色组的数据调查管理角色提供了访问 Office 365 或 Microsoft 365 合规性中心中的数据调查工具所需的权限。 默认情况下，此角色不会分配给 "组织管理" 角色组，这意味着组织中的全局管理员可能无法在默认情况下访问数据调查工具。 若要解决此问题，可以将全局管理员添加到数据调查员角色组，或将数据调查管理角色添加到组织管理角色组。 第三个选项是创建自定义角色组，并将数据调查管理角色分配给 (和其他角色) 然后添加相应的成员。 有关角色组和角色的详细信息，请参阅 [安全性 & 合规性中心中的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。
