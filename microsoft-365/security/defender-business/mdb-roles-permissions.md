---
title: 分配角色和权限Microsoft Defender 商业版
description: 了解如何在服务器中分配角色Microsoft Defender 商业版
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 04/01/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 33fb7548d2dbd231368a459cd58b9d50e7c4673e
ms.sourcegitcommit: 7aa2441c1f2cc5b4b5495d6fdb993e563f86647f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2022
ms.locfileid: "64638237"
---
# <a name="assign-roles-and-permissions-in-microsoft-defender-for-business"></a>分配角色和权限Microsoft Defender 商业版

> [!IMPORTANT]
> Microsoft Defender 商业版 2022 年 3 [Microsoft 365 商业高级版](../../business-premium/index.md) 1 开始向客户推出。 作为独立订阅的 Defender for Business 在预览版中，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 预览 [包括一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

若要在安全Microsoft 365 Defender中执行任务，如配置Microsoft Defender 商业版、查看报告或对检测到的威胁采取响应操作，必须为安全团队分配适当的权限。 权限通过在 [https://security.microsoft.com](https://security.microsoft.com) Microsoft 365 Defender 门户或 () 中分配[Azure Active Directory。](/azure/active-directory/roles/manage-roles-portal) 

## <a name="what-to-do"></a>需执行的操作

1. [了解 Defender for Business 中的角色](#roles-in-defender-for-business)。

2. [查看或编辑安全团队的角色分配](#view-or-edit-role-assignments)。

3. [继续执行下一步](#next-steps)。

>
> **有空吗？**
> 请参加<a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">我们的简短调查，了解Microsoft Defender 商业版</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="roles-in-defender-for-business"></a>Defender for Business 中的角色

下表介绍了可在 Defender for Business 中分配的三个角色。 [了解有关管理员角色和](../../admin/add-users/about-admin-roles.md)。 <br/><br/>

| 权限级别 | 说明 |
|:---|:---|
| **全局管理员** (也称为全局管理员)  <br/><br/> *最佳做法是限制全局管理员的数量。* | 全局管理员可以执行所有类型的任务。 默认情况下，注册公司Microsoft 365或Microsoft Defender 商业版全局管理员。 <br/><br/> 全局管理员能够跨所有门户访问/Microsoft 365设置，例如： <br/>- Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com))  <br/>- Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) |
| **安全管理员** (也称为安全管理员)  | 安全管理员可以执行以下任务： <br/>- 查看和管理安全策略 <br/>- 查看和管理这些活动中的 (威胁和警报，包括对活动终结点采取)  <br/>- 查看安全信息和报告 |
| **安全信息读取者** | 安全读者可以执行以下任务： <br/>- 查看安全策略 <br/>- 查看安全威胁和警报 <br/>- 查看安全信息和报告  |


## <a name="view-or-edit-role-assignments"></a>查看或编辑角色分配

1. 转到"Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 并登录。

2. 在导航窗格中，选择"权限 **&角色"**，然后在"**Azure AD"角色****"**。

3. 选择下列角色之一以打开其侧窗格：

   - 全局管理员
   - 安全管理员
   - 安全读者

   > [!IMPORTANT]
   > Microsoft 建议仅向用户授予执行其任务所需的访问权限。 我们将此概 *念称为权限最小* 特权。 若要了解更多信息，请参阅 [应用程序最小特权访问的最佳实践](/azure/active-directory/develop/secure-least-privileged-access)。 

4. 在侧窗格中，选择"管理 **Azure AD** 链接。 此操作可让你Azure Active Directory (Azure AD) 查看和管理角色分配。

5. 选择要打开其配置文件的用户，然后选择" **分配的角色"**。

   - 若要添加角色，请选择" **+ 添加分配"**。
   - 若要删除角色，请选择 **"X 删除分配"**。 

## <a name="need-to-add-users"></a>需要添加用户？

如果尚未向订阅添加用户，请参阅同时添加用户 [和分配许可证](../../admin/add-users/add-users.md)。

## <a name="next-steps"></a>后续步骤

继续：

- [步骤 3：设置电子邮件通知](mdb-email-notifications.md)

- [步骤 4：将设备载入Microsoft Defender 商业版](mdb-onboard-devices.md)