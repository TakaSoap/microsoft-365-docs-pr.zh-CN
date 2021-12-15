---
title: '在 Microsoft Defender for Business 预览版中分配 (和) '
description: '了解如何在 Microsoft Defender for Business 预览版中 (角色) '
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/13/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 1a003bc5ad0208972f03e761dbfb251c2b2509b0
ms.sourcegitcommit: 74f79aacb4ffcc6cb0e315239b1493324eabb449
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2021
ms.locfileid: "61507418"
---
# <a name="assign-roles-and-permissions-in-microsoft-defender-for-business-preview"></a>在 Microsoft Defender for Business 预览版中分配 (和) 

> [!IMPORTANT]
> Microsoft Defender for Business 现在为预览版，将逐步向在此处注册以请求[](https://aka.ms/mdb-preview)它的客户和 IT 合作伙伴推出。 我们将于未来几周内载入一组初始客户和合作伙伴，并扩大预览版本，从而一般可用。 请注意，预览将启动 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

若要在 Microsoft 365 Defender 门户中执行任务，例如配置 Microsoft Defender for Business (预览版) 、查看报告或对检测到的威胁执行响应操作，必须为安全团队分配适当的权限。 权限通过在 Microsoft 365 Defender 门户或 () 中分配 [https://security.microsoft.com](https://security.microsoft.com) Azure Active Directory。 [](/azure/active-directory/roles/manage-roles-portal) 

## <a name="what-to-do"></a>需执行的操作

1. [了解 Defender for Business 预览版 (中的角色) 。 ](#roles-in-defender-for-business)

2. [查看或编辑安全团队的角色分配](#view-or-edit-role-assignments)。

3. [继续执行下一步](#next-steps)。

## <a name="roles-in-defender-for-business"></a>Defender for Business 中的角色

下表介绍了可以在 Defender for Business 预览版中分配的三 (角色) 。 [了解有关管理员角色和](../../admin/add-users/about-admin-roles.md)。 <br/><br/>

| 权限级别 | 说明 |
|:---|:---|
| **全局管理员** (也称为全局管理员)  <br/><br/> *最佳做法是限制全局管理员的数量。* | 全局管理员可以执行所有类型的任务。 默认情况下，注册你的公司Microsoft 365 Microsoft Defender for Business 预览版 () 全局管理员。 <br/><br/> 全局管理员能够跨所有门户访问/更改Microsoft 365设置，例如： <br/>- [https://admin.microsoft.com](https://admin.microsoft.com) Microsoft 365 管理中心 ()  <br/>- Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) ()  |
| **安全管理员** (也称为安全管理员)  | 安全管理员可以执行以下任务： <br/>- 查看和管理安全策略和设置 <br/>- 查看和管理这些活动中的 (威胁和警报，包括对活动终结点采取)  <br/>- 查看安全信息和报告 |
| **安全信息读取者** | 安全读者可以执行以下任务： <br/>- 查看安全策略和设置 <br/>- 查看安全威胁和警报 <br/>- 查看安全信息和报告  |


## <a name="view-or-edit-role-assignments"></a>查看或编辑角色分配

1. 转到"Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) () 并登录。

2. In the navigation pane， choose **Permissions & roles**， and then under **Azure AD**， select **Roles**.

3. 选择下列角色之一以打开其侧窗格：

   - 全局管理员
   - 安全管理员
   - 安全读者

   > [!IMPORTANT]
   > Microsoft 建议仅向用户授予执行其任务所需的访问权限。 我们将此概 *念称为权限最小* 特权。 若要了解更多信息，请参阅 [Best practices for least-privileged access for applications](/azure/active-directory/develop/secure-least-privileged-access)。 

4. 在侧窗格中，选择"管理 **Azure AD** 链接。 此操作可让你Azure Active Directory (Azure AD) 查看和管理角色分配。

5. 选择要打开其配置文件的用户，然后选择"**分配的角色"。**

   - 若要添加角色，请选择 **"+ 添加分配"。**
   - 若要删除角色，请选择 **"X 删除分配"。** 

## <a name="next-steps"></a>后续步骤

继续：

- [步骤 3：设置电子邮件通知](mdb-email-notifications.md)

- [步骤 4：将设备载入 Microsoft Defender for Business (预览) ](mdb-onboard-devices.md)