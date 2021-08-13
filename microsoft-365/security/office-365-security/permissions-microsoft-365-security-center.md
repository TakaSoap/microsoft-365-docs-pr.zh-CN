---
title: Microsoft 365 Defender 门户中的权限
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
audience: Admin
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 管理员可以了解如何在 Microsoft 365 Defender 门户中管理与安全相关的所有任务的权限。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9f417bbb784a328970c32602d52a76f5c855016f325b316af53ed0a4ff137db1
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "56790209"
---
# <a name="permissions-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender 门户中的权限

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

需要管理跨所有 Microsoft 365 服务的安全方案。 并且你需要灵活地向组织 IT 组中的正确人员授予正确的管理员权限。

Microsoft 365 Defender 门户 (<https://security.microsoft.com>) 支持为在 Microsoft 365 中执行安全任务的用户直接管理权限。 通过使用 Microsoft 365 Defender 门户管理权限，你可以集中管理与安全相关的所有任务的权限。

若要在 Microsoft 365 Defender 门户中管理权限，请转到“**权限和角色**”或 <https://security.microsoft.com/securitypermissions>。 你需要是 Microsoft 365 Defender 门户中的 **全局管理员** 或“**组织管理**”角色组的成员。 具体而言，“**角色管理**”角色允许用户在 Microsoft 365 Defender 门户中查看、创建和修改角色组，默认情况下，该角色仅分配给“**组织管理**”角色组。

> [!NOTE]
> 有关 Microsoft 365 合规中心中的权限的信息，请参阅 [Microsoft 365 合规中心中的权限](../../compliance/microsoft-365-compliance-center-permissions.md)。

## <a name="relationship-of-members-roles-and-role-groups"></a>成员、角色和角色组之间的关系

Microsoft 365 Defender 门户中的权限以基于角色的访问控制 (RBAC) 权限模型为基础。 RBAC 与大多数 Microsoft 365 服务使用的权限模型相同，因此如果你熟悉这些服务中的权限结构，那么将非常熟悉如何在 Microsoft 365 Defender 门户中授予权限。

**角色** 授予执行一组任务的权限。

**角色组** 是一组允许人们在 Microsoft 365 Defender 门户中完成工作的角色。 例如，攻击模拟器管理员角色组包括攻击模拟器管理员角色，以创建和管理攻击模拟培训的所有方面。

Microsoft 365 Defender 门户包括你需要分配的最常见任务和功能的默认角色组。 通常，我们建议你只需将单个用户作为 **成员** 添加到默认角色组。

![显示角色组与角色和成员之间关系的图表](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="roles-and-role-groups-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender 门户中的角色和角色组

Microsoft 365 Defender 门户中的“**权限和角色**”提供了以下类型的角色和角色组：

- **Azure AD 角色**：可以查看角色和分配的用户，但无法在 Microsoft 365 Defender 门户中直接管理它们。 Azure AD 角色是为 **所有** Microsoft 365 服务分配权限的中心角色。

- **电子邮件和协作角色**：这些角色组与安全与合规中心中可用的角色组相同，但可以直接在 Microsoft 365 Defender 门户中管理它们。 在此处分配的权限特定于 Microsoft 365 Defender 门户、Microsoft 365 合规中心和安全与合规性中心，不包括其他 Microsoft 365 工作负载所需的所有权限。

![Microsoft 365 Defender 门户中的权限和角色页面](../../media/m365-sc-permissions-and-roles-page.png)

### <a name="azure-ad-roles-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender 门户中的 Azure AD 角色

转到 **电子邮件和协作角色** \> **权限和角色** \> **Azure AD 角色** \> **角色** （或直接发送到 <https://security.microsoft.com/aadpermissions>），你将看到本部分中介绍的 Azure AD 角色。

选择某个角色时，会显示一个包含角色说明和用户分配的详细信息飞出。 但是要管理这些分配，您需要在详细信息弹出按钮中单击 **管理 Azure AD 中的成员**。

![链接以管理 Azure Active Directory 中的权限](../../media/permissions-manage-in-azure-ad-link.png)

有关详细信息，请参阅[查看和分配 Azure Active Directory 中的管理员角色](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

<br>

****

|角色|说明|
|---|---|
|**全局管理员**|访问所有 Microsoft 365 服务中的所有管理功能的权限。 只有全局管理员才能分配其他管理员角色。 更多信息，请参阅[全局管理员/公司管理员](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator)。|
|**合规性数据管理员**|在 Microsoft 365 中跟踪组织的数据，确保数据受到保护，并深入了解任何问题以帮助缓解风险。 有关详细信息，请参阅[合规性数据管理员](/azure/active-directory/roles/permissions-reference#compliance-data-administrator)。|
|**合规性管理员**|帮助组织遵守任何法规要求，管理电子数据展示案例，并维护 Microsoft 365 位置、标识和应用中的数据治理策略。 有关详细信息，请参阅[合规性管理员](/azure/active-directory/roles/permissions-reference#compliance-administrator)。|
|**安全操作员**|查看、调查和响应对 Microsoft 365 用户、设备和内容的活动威胁。 有关详细信息，请参阅[安全操作员](/azure/active-directory/roles/permissions-reference#security-operator)。|
|**安全信息读取者**|查看和调查对 Microsoft 365 用户、设备和内容的活动威胁，但（不同于安全操作员）他们无权采取措施来进行响应。 有关详细信息，请参阅[安全信息读取者](/azure/active-directory/roles/permissions-reference#security-reader)。|
|**安全管理员**|通过管理安全策略、查看 Microsoft 365 产品中的安全分析和报告以及及时了解威胁形势来控制组织的总体安全。 有关详细信息，请参阅[安全管理员](/azure/active-directory/roles/permissions-reference#security-administrator)。|
|**全局读取者**|只读版本的 **全局管理员** 角色。 查看 Microsoft 365 中所有设置和管理信息。 有关详细信息，请参阅 [全局信息读取者](/azure/active-directory/roles/permissions-reference#global-reader)。|
|**攻击模拟管理员**|创建和管理 [攻击模拟](attack-simulation-training.md) 创建、启动/安排模拟以及审查模拟结果的各个方面。 有关详细信息，请参阅 [攻击模拟管理员](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator)。|
|**攻击有效负载作者**|创建攻击负载，但不真正开始或计划其目标。 有关详细信息，请参阅[攻击有效负载作者](/azure/active-directory/roles/permissions-reference#attack-payload-author)。|
|

### <a name="email--collaboration-roles-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender 门户中的电子邮件和协作角色

转到 **电子邮件和协作角色** \> **权限和角色** \> **电子邮件和协作角色** \> **角色** （或直接发送到 <https://security.microsoft.com/emailandcollabpermissions>），你将看到安全与合规中心中可用的相同角色组。

有关这些角色组的完整信息，请参阅 [安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)

#### <a name="modify-email--collaboration-role-membership-in-the-microsoft-365-defender-portal"></a>在 Microsoft 365 Defender 门户中修改电子邮件和协作角色成员资格

1. 在 Microsoft 365 Defender 门户中，转到“**电子邮件和协作角色**”\>“**权限和角色**”\>“**电子邮件和协作角色**”\>“**角色**”。

2. 在打开的 **权限** 页面中，从列表中选择要修改的角色组。 你可以单击列标题 **名称** 以按名称对列表进行排序，也可以单击 **搜索** ![搜索"图标](../../media/m365-cc-sc-search-icon.png) 以查找角色组。

3. 在显示的角色组详细信息飞出中，单击 **成员** 部分中的 **编辑**。

4. 在出现的 **“编辑选择成员”** 页面中，请执行下列步骤之一：
   - 如果没有角色组成员，请单击 **选择成员**。
   - 如果已有角色组成员，请单击 **"编辑"**

5. 在出现的 **“选择成员”** 弹出按钮中，执行以下步骤之一：

   - 单击“**添加**”。 在显示的用户列表中，选择一个或多个用户。 或者，可以单击 **搜索** ![搜索图标](../../media/m365-cc-sc-search-icon.png) 查找和选择用户。

     选中要添加的用户后，单击 **"添加"**。

   - 单击 **“移除”**。 选择一个或多个现有成员。 或者，可以单击 **搜索** ![搜索图标](../../media/m365-cc-sc-search-icon.png) 查找和选择用户。

     选中要删除的用户后，单击 **"删除"**。

6. 返回 **“选择成员”** 弹出按钮，单击 **完成**。

7. 返回 **编辑选择成员** 页面，点击 **保存**。

8. 返回角色组详细信息浮出控件，单击 **完成**。
