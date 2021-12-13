---
title: Microsoft 365 合规中心中的权限
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
description: 了解如何管理用户Microsoft 365 合规中心。
ms.collection: M365-security-compliance
ms.custom:
- admindeeplinkCOMPLIANCE
- admindeeplinkEXCHANGE
ms.openlocfilehash: 45540713452b91da171f6fc52eef8210fa256c4e
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61423691"
---
# <a name="permissions-in-the-microsoft-365-compliance-center"></a>Microsoft 365 合规中心中的权限

该Microsoft 365 合规中心最近已更新，现在支持直接管理在 Microsoft 365 中执行合规性任务的用户的权限。 此更新意味着你不再需要使用安全与合规Office 365&管理合规性解决方案的权限。 使用 Microsoft 365 合规中心中的新"权限"页，你可以管理用户的权限，以执行设备管理、数据丢失防护、电子数据展示、内部风险管理、保留等功能中的合规性任务。 用户只能执行您明确授予其访问权限的合规性任务。

若要查看 Microsoft 365 合规中心中的"权限"选项卡，用户需要是全局管理员，或需要分配有角色管理角色 (角色只能分配给组织管理角色组) 。  *角色管理* 角色允许用户查看、创建和修改角色组。

!["权限"页Microsoft 365 合规中心。](../media/m365-compliance-center-permissions.png)

该权限Microsoft 365 合规中心基于基于角色的访问控制 (RBAC) 权限模型。 RBAC 与大多数 Microsoft 365 服务使用的权限模型相同，因此如果您熟悉这些服务中的权限结构，那么将熟悉在 Microsoft 365 合规中心 中授予权限。 切记，在 Microsoft 365 合规中心 中管理的权限并不涵盖每个服务中所需的所有权限的管理。 你仍然需要在管理中心中管理特定服务的特定权限。 例如，如果需要分配存档、审核和 MRM 保留策略的权限，则需要在管理中心中管理Exchange<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">权限</a>。

## <a name="relationship-of-members-roles-and-role-groups"></a>成员、角色和角色组之间的关系

角色授予执行一组任务的权限;例如，案例管理角色允许用户使用电子数据展示事例。

角色组是一组角色，使用户能够在角色组中跨合规性解决方案Microsoft 365 合规中心。 例如，通过将用户添加到 *内部* 风险管理角色组，指定管理员、分析师、研究人员和审核员在单个组中配置必要的内部风险管理权限。 The Microsoft 365 合规中心 includes default role groups for tasks and functions for each compliance solution that you'll need to assign people to. 通常，我们建议根据需要将单个用户添加为默认合规性角色组的成员。

![显示角色组与角色和成员之间关系的图表。](../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-microsoft-365-compliance-center"></a>使用应用程序功能所需的Microsoft 365 合规中心

若要查看 Microsoft 365 合规中心 中可用的所有默认角色组以及默认情况下分配给角色组的角色，请参阅安全与合规中心&[权限。](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)

管理网站中Microsoft 365 合规中心仅允许用户访问功能范围内提供的合规性Microsoft 365 合规中心。 如果要向 Microsoft 365 合规中心 中未包含的其他功能授予权限，例如 Exchange 邮件流规则 (也称为传输规则) ，则需要使用<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange</a>管理中心。

## <a name="azure-roles-in-the-microsoft-365-compliance-center"></a>Azure 角色Microsoft 365 合规中心

"权限"页Azure AD  >  角色"部分Microsoft 365 合规中心 **角色** Azure Active Directory角色。 这些角色旨在与组织 IT 组中的工作职能保持一致，从而可以轻松地使人员获得完成其工作所需的所有权限。 通过选择管理员角色并查看角色面板详细信息，可以查看当前分配给每个角色的用户。 若要管理角色Azure AD，请选择"管理Azure AD"。 此选项会将你重定向到 Azure 管理门户。

|Role|说明|
|:---|:----------|
|**全局管理员**|访问所有 Microsoft 365 服务中的所有管理功能的权限。 只有全局管理员才能分配其他管理员角色。 更多信息，请参阅[全局管理员/公司管理员](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator)。|
|**合规性数据管理员**|在 Microsoft 365 中跟踪组织的数据，以确保其受到保护，并深入了解任何问题以帮助降低风险。有关详细信息，请参阅 [合规性数据管理员](/azure/active-directory/roles/permissions-reference#compliance-data-administrator)。|
|**合规性管理员**|帮助组织遵守任何法规要求，管理电子数据展示案例，并维护 Microsoft 365 位置、标识和应用的数据治理策略。有关详细信息，请参阅 [合规性管理员](/azure/active-directory/roles/permissions-reference#compliance-administrator)。|
|**安全操作员**|查看、调查和响应对 Microsoft 365 用户、设备和内容的活动威胁。 有关详细信息，请参阅[安全操作员](/azure/active-directory/roles/permissions-reference#security-operator)。|
|**安全信息读取者**|查看和调查对 Microsoft 365 用户、设备和内容的活动威胁，但（不同于安全操作员）他们无权采取措施来进行响应。有关详细信息，请参阅 [安全信息读取者](/azure/active-directory/roles/permissions-reference#security-reader)。|
|**安全管理员**|通过管理安全策略、查看 Microsoft 365 产品中的安全分析和报告和及时了解威胁形势来控制组织的总体安全。有关详细信息，请参阅 [安全性管理员](/azure/active-directory/roles/permissions-reference#security-administrator)。|
|**全局读取者**|只读版本的 **全局管理员** 角色。 查看 Microsoft 365 中所有设置和管理信息。 有关详细信息，请参阅 [全局信息读取者](/azure/active-directory/roles/permissions-reference#global-reader)。|
|**攻击模拟管理员**|创建和管理 攻击模拟 创建、启动/计划模拟以及查看模拟结果的所有方面。有关详细信息，请参阅 [攻击模拟管理员](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator)。|
|**攻击有效负载作者**|创建攻击负载，但不真正开始或计划其目标。 有关详细信息，请参阅[攻击有效负载作者](/azure/active-directory/roles/permissions-reference#attack-payload-author)。|
|

## <a name="add-users-to-a-compliance-role-group"></a>将用户添加到合规性角色组

完成以下步骤以将用户添加到合规性角色组：

1. 使用 Microsoft 365 组织中管理员帐户的凭据登录到 Microsoft 365 合规中心 的权限区域，然后转到"权限"以选择链接以查看和管理 Microsoft 365<a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank"></a>中的合规性角色。
1. 展开"**合规中心"** 部分，然后选择"**角色"。**
1. 在" **合规性中心角色** "页上，选择要添加用户的合规性角色组，然后选择详细信息窗格上的 **"编辑角色** 组"。
1. 从左侧导航窗格中选择“**选择成员**”，然后选择“**编辑**”。
1. 选择“**添加**”，然后选中希望添加到角色组的所有用户的复选框。
1. 选择“**添加**”，然后选择“**完成**”。
1. 选择“**保存**”以将用户添加到角色组。 选择“**关闭**”以完成步骤。

## <a name="remove-users-from-a-compliance-role-group"></a>从合规性角色组中删除用户

完成以下步骤以从合规性角色组中删除用户：

1. 使用 Microsoft 365 组织中管理员帐户的凭据登录到 Microsoft 365 合规中心 的权限区域，然后转到"权限"以选择链接以查看和管理 Microsoft 365<a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank"></a>中的合规性角色。
1. 展开"合规中心"部分，然后选择"**角色"。**
1. 在" **合规性中心角色** "页上，选择要从中删除用户的合规性角色组，然后选择详细信息窗格上的" **编辑角色** 组"。
1. 从左侧导航窗格中选择“**选择成员**”，然后选择“**编辑**”。
1. 选择 **"** 删除"，然后选中要从角色组中删除的所有用户的复选框。
1. 选择 **"删除**"，然后选择"**完成"。**
1. 选择 **"** 保存"以从角色组中删除用户。 选择“**关闭**”以完成步骤。

## <a name="create-a-custom-role-group"></a>创建自定义角色组

完成以下步骤以创建自定义角色组：

1. 使用你的组织中管理员帐户Microsoft 365 合规中心登录管理员帐户的权限区域，Microsoft 365"权限 <a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">**"。**</a>
1. 在"**权限&角色"页上**，选择"合规性 **中心>角色"。**
1. 在"**合规性中心角色"页上**，选择"创建 **"。**
1. 在" **命名角色组** "页上的"名称"字段中输入自定义角色 **组** 的名称。 角色组的名称无法在角色组创建后更改。 如果需要，请在"说明"字段中输入自定义角色 **组** 的说明。 选择“**下一步**”以继续。
1. 在"**选择角色"** 页上，选择"**选择角色"。**
1. 选择 **"** 添加"，然后选择要添加到自定义角色组的角色。 选择 **"添加**"以添加角色组，然后选择"完成 **"。**
1. 选择“**下一步**”以继续。
1. 在"**选择成员"** 页上，选择"**选择成员"。**
1. 选择 **"** 添加"，然后选择要添加到自定义角色组的成员。 选择 **"添加**"以添加成员，然后选择"完成 **"。**
1. 选择“**下一步**”以继续。
1. 在 **"查看设置"** 页上，查看自定义角色组的详细信息。 如果需要编辑信息，请选择相应 **部分** 中的"编辑"。 当所有设置都正确时，选择"创建角色组"以创建自定义角色组，或选择"取消"以放弃更改，而不是创建自定义角色组。

## <a name="update-a-custom-role-group"></a>更新自定义角色组

完成以下步骤以更新自定义角色组：

1. 使用你的组织中管理员帐户Microsoft 365 合规中心登录管理员帐户的权限区域，Microsoft 365"权限 <a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">**"。**</a>
1. 在"**权限&角色"页上**，选择"合规性 **中心>角色"。**
1. 在" **合规中心角色"** 页上，选择要更新的角色组。
1. 在所选角色组的详细信息窗格中，选择"编辑 **角色组"。**
1. 在 **"编辑角色组名称"** 页上，更新"说明"字段中自定义角色 **组的说明** 。 无法更改自定义角色组的名称。
1. 在" **选择角色** "页上， **选择** "编辑"以更新分配给角色组的角色。
1. 选择 **"** 添加"，然后选择要添加到自定义角色组的角色。 选择 **"添加**"以添加角色组，然后选择"完成 **"。**
1. 在"**选择成员"** 页上，选择"编辑 **"。**
1. 选择 **"** 添加"，然后选择要添加到自定义角色组的成员。 选择 **"添加**"以添加成员，然后选择"完成 **"。**
1. 选择 **"保存**"以保存 *更新后的"说明**"、角色组**和"成员"* 值。
1. 在所选角色组的详细信息窗格中，选择"关闭 **"。**

## <a name="delete-a-custom-role-group"></a>删除自定义角色组

完成以下步骤以更新自定义角色组：

1. 使用你的组织中管理员帐户Microsoft 365 合规中心登录管理员帐户的权限区域，Microsoft 365"权限 <a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">**"。**</a>
1. 在"**权限&角色"页上**，选择"合规性 **中心>角色"。**
1. 在" **合规中心角色"** 页上，选择要更新的角色组。
1. 在所选角色组的详细信息窗格中，选择"**删除角色组"。**
1. 在" **警告** "对话框中，选择 **"** 是"删除角色组，或选择" **否** "取消删除过程。
