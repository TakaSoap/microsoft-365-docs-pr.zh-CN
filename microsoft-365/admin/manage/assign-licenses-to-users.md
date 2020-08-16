---
title: 向用户分配许可证
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 了解如何向用户分配许可证。
ms.date: 08/14/2020
ms.openlocfilehash: e1f28107f7774fa4eccbecb3882cbd002a6eea1a
ms.sourcegitcommit: 919b5d0f33b41b4beaca5fbb06e1c75d65027b7e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2020
ms.locfileid: "46757553"
---
# <a name="assign-licenses-to-users"></a>向用户分配许可证

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

::: moniker range="o365-worldwide"

可在“**活动用户**”页面或“**许可证**”页面上向用户分配许可证。 所使用的方法取决于是要向特定用户分配产品许可证还是向特定产品分配用户许可证。

::: moniker-end

[了解如何同时添加用户帐户和分配许可证](../add-users/add-users.md)。

## <a name="before-you-begin"></a>准备工作

- 你必须是全局、许可证或用户管理员才能分配许可证。 有关详细信息，请参阅[关于 Microsoft 365 管理员角色](../add-users/about-admin-roles.md)。
- 你可以[使用 Office 365 PowerShell 向用户帐户分配许可证](https://go.microsoft.com/fwlink/p/?linkid=850410)。
- 若要使用基于组的许可，请参阅[在 Azure Active Directory 中按组成员身份向用户分配许可证](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)
- 某些服务（如 Sway）会自动分配给用户，无需单独分配。

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a>使用“许可证”页面向用户分配许可证

使用“**许可证**”页面分配许可证时，最多可向 20 名用户分配特定产品的许可证。 在“**许可证**”页面上，你将看到你所订阅的所有产品的列表。 你还将看到每个产品的许可证总数、分配的许可证数以及可用的许可证数量。

1. 在管理中心，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>”页面。
2. 选择产品。
3. 在产品详细信息页面上，选择“**分配许可证**”。
4. 在“**向用户分配许可证**”窗格中，开始键入名称，然后从结果中将其选中，将其添加到列表中。 一次最多可添加 20 名用户。
5. 选择“**打开或关闭应用和服务**”，向特定项目分配访问权限或删除其访问权限。
6. 完成后，选择“分配”****，然后选择“关闭”****。

如果出现冲突，则将显示一则消息，指出问题是什么以及如何修复它。 例如，如果选择包含冲突服务的许可证，错误消息将指示审阅随每个许可证包含的服务并重试。

## <a name="change-the-apps-and-services-a-user-has-access-to"></a>更改用户有权访问的应用和服务

1. 在管理中心，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>”页面。
2. 在“**许可证**”页面上，选择特定用户所对应的行。
3. 在右侧窗格中，选择或取消选择要授予或取消访问权限的应用和服务。
4. 完成后，选择“**保存**”，然后选择“**关闭**”。

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a>使用“活动用户”页面分配许可证

使用“**活动用户**”页面分配许可证时，将向产品分配用户许可证。

### <a name="assign-licenses-to-multiple-users"></a>向多个用户分配许可证

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
2. 选中要向其分配许可证的用户姓名旁边的圆圈。
3. 在顶部选择“**更多选项(...)**”，然后选择“**管理产品许可证**”。
4. 在“**管理产品许可证**”窗格中，选择“**添加到现有产品许可证分配**”\>“**下一步**”。
5. 在“**添加到现有产品**”窗格中，将希望所选用户具备的许可证的开关切换到“**开**”位置。\
    默认情况下，与这些许可证关联的所有服务都将自动分配给该用户。 可限制能提供给用户的具体服务。 将不希望所选用户具备的服务的开关切换到“**关**”。
6. 在窗格底部，选择“**添加**”\>“**关闭**”。  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a>向多个用户分配许可证

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。
2. 选中要向其分配许可证的用户姓名旁边的框。
3. 在“**批量操作**”窗格中，选择“**编辑产品许可证**”。
4. 在“**分配产品**”窗格中，选择“**添加到现有产品许可证分配**”\>“**下一步**”。
5. 将希望所选用户具备的许可证的开关切换到“**开**”位置。\
    默认情况下，与这些许可证关联的所有服务都将自动分配给该用户。 可限制能提供给用户的具体服务。 将不希望所选用户具备的服务的开关切换到“**关**”。
6. 在“**添加到现有产品**”窗格底部，选择“**添加**”\>“**关闭**”\>“**关闭**”。

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a>向多个用户分配许可证

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。
2. 选中要向其分配许可证的用户姓名旁边的框。
3. 在“**批量操作**”窗格中，选择“**编辑产品许可证**”。
4. 在“**分配产品**”窗格中，选择“**添加到现有产品许可证分配**”\>“**下一步**”。
5. 将希望所选用户具备的许可证的开关切换到“**开**”位置。\
    默认情况下，与这些许可证关联的所有服务都将自动分配给该用户。 可限制能提供给用户的具体服务。 将不希望所选用户具备的服务的开关切换到“**关**”。
6. 在“**添加到现有产品**”窗格底部，选择“**添加**”\>“**关闭**”\>“**关闭**”。

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a>向一个用户分配许可证

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。
2. 选择要向其分配许可证的用户所对应的行。
3. 在右侧窗格，选择“**许可证和应用**”。
4. 展开“**许可证**”部分，选择要分配的许可证的框，然后选择“**保存更改**”。

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a>向一个用户分配许可证

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。
2. 选中要向其分配许可证的用户姓名旁边的框。
3. 在右侧窗格的“**产品许可证**”行中，选择“**编辑**”。
4. 在“**产品许可证**”窗格中，将要分配给此用户的许可证的开关切换到“**开**”位置。\
    默认情况下，与该许可证关联的所有服务都将自动分配给该用户。 可限制能提供给用户的具体服务。 将不希望所选用户具备的服务的开关切换到“**关**”。
5. 在“**产品许可证**”窗格底部，选择“**保存**”\>“**关闭**”\>“**关闭**”。

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a>向一个用户分配许可证

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。
2. 选中要向其分配许可证的用户姓名旁边的框。
3. 在右侧窗格的“**产品许可证**”行中，选择“**编辑**”。
4. 在“**产品许可证**”窗格中，将要分配给此用户的许可证的开关切换到“**开**”位置。\
    默认情况下，与该许可证关联的所有服务都将自动分配给该用户。 可限制能提供给用户的具体服务。 将不希望所选用户具备的服务的开关切换到“**关**”。
5. 在“**产品许可证**”窗格底部，选择“**保存**”\>“**关闭**”\>“**关闭**”。

::: moniker-end

## <a name="assign-a-license-to-a-guest-user"></a>向来宾用户分配许可证

可在 Azure Active directory 管理中心中邀请来宾用户与你的组织进行协作。 若要了解有关来宾用户的信息，请参阅 [Azure Active Directory B2B 中的来宾用户访问是什么？](https://docs.microsoft.com/azure/active-directory/external-identities/what-is-b2b) 如果你没有任何来宾用户，请参阅[快速入门：在 Azure 门户中将来宾用户添加到你的目录](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)。

> [!IMPORTANT]
> 必须是全局管理员才能执行这些步骤。

1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory 管理中心</a>
2. 在导航窗格中，选择“**用户**”。
3. 在“**用户 | 所有用户（预览）**”页面上，选择“**添加筛选器**”。
4. 在“**选择字段**”菜单中，选择“**用户类型**”，然后选择“**应用**”。
5. 在下一个菜单中，选择“**来宾**”。
6. 在结果列表中，选择需要许可证的用户。
7. 在“**管理**”下，选择“**许可证**”。
8. 选择“**分配**”。
9. 在“**更新许可证分配**”页面上，选择要为其分配许可证的产品。
10. 在右侧，清除不希望来宾用户拥有访问权限的任何服务所对应的复选框。
11. 选择“**保存**”。

## <a name="next-steps"></a>后续步骤

如果用户尚未安装 Office 应用，你可以与其共享[员工快速入门指南](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f)以进行各项设置，如[如何在电脑或 Mac 上下载并安装 Microsoft 365 或 Office 2019](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)以及[如何在移动设备上设置 Office 应用和电子邮件](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)。

## <a name="related-content"></a>相关内容

[了解订阅和许可证](../../commerce/licenses/subscriptions-and-licenses.md)（文章）\
[取消向用户分配许可证](remove-licenses-from-users.md)（文章）\
[购买或删除订阅的许可证](../../commerce/licenses/buy-licenses.md)（文章）