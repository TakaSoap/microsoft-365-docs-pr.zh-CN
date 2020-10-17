---
title: 为 Microsoft 365 企业版测试环境自动化许可和组成员身份
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 在 Microsoft 365 企业版测试环境中配置基于组的许可和动态组成员身份。
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487572"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>为 Microsoft 365 企业版测试环境自动化许可和组成员身份

*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*

基于组的许可根据组成员身份自动分配或删除用户帐户的许可证。 动态组成员身份根据用户帐户属性（如 **部门** 或 **国家/地区**）添加或删除组中的成员。 本文将指导您完成在 Microsoft 365 企业版测试环境中添加和删除组成员的演示。

在 Microsoft 365 企业版测试环境中设置自动许可和动态组成员身份包括两个阶段：

- [第1阶段：构建您的 Microsoft 365 企业版测试环境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [第2阶段：配置和测试动态组成员身份和自动许可](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第1阶段：构建您的 Microsoft 365 企业版测试环境

如果您希望仅使用最低要求测试自动许可和组成员身份，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。
  
如果要在模拟的企业中测试自动授权和组成员身份，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。
  
> [!NOTE]
> 测试自动授权和组成员身份不需要模拟企业测试环境，其中包括连接到 internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。 它作为选项提供，以便您可以测试自动授权和组成员身份，并在代表典型组织的环境中进行试验。
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>第2阶段：配置和测试动态组成员身份和自动许可

首先，创建一个名为 Sales 的新组，并添加一个动态组成员身份规则，以便将 **部门** 设置为 " **销售** " 的用户帐户自动加入 "销售" 组。

1. 在 internet 浏览器的专用实例中，使用 Microsoft 365 E5 测试实验室订阅的全局管理员帐户登录 [microsoft 365 管理中心](https://admin.microsoft.com) 。
2. 在浏览器的一个单独的选项卡上，转到 Azure 门户处 [https://portal.azure.com](https://portal.azure.com) 。
3. 在 Azure 门户中，在搜索框中输入 **组** ，然后选择 " **组**"。
4. 在 " **所有组** " 窗格中，选择 " **新建组**"。
5. 在 " **组类型**" 中，选择 " **Microsoft 365**"。
6. 在 " **组名称**" 中，输入 **Sales**。
7. 在 " **成员身份类型**" 中，选择 " **动态用户**"。
8. 选择 " **动态用户成员**"。
9. 在 " **动态成员身份规则** " 窗格中： 
   - 选择 " **部门** " 属性。
   - 选择 " **等于** " 运算符。
   - 在 " **值** " 框中，输入 **Sales**。
10. 选择“**保存**”。
11. 选择 **“创建”**。

接下来，配置 "销售" 组，以便自动向成员分配 Microsoft 365 E5 许可证。

1. 选择 " **销售** " 组，然后选择 " **许可证**"。
2. 在 " **更新许可证分配** " 窗格中，选择 " **Microsoft 365 E5**"，然后选择 " **保存**"。
3. 在浏览器中，关闭 "Azure 门户" 选项卡。

接下来，测试用户4帐户上的动态组成员身份和自动许可：

1. 在浏览器的 " **Microsoft Office 主页** " 选项卡中，选择 " **管理员**"。
2. 从 " **Microsoft 365 管理中心** " 选项卡中，选择 " **活动用户**"。
3. 在 " **活动用户** " 页上，选择 " **用户 4** " 帐户。
4. 在 "**用户 4** " 窗格中，选择 "**编辑****产品许可证**"。
5. 在 "**产品许可证**" 窗格上，禁用**Microsoft 365 E5**许可证，然后选择 "**保存**" "  >  **关闭**"。
6. 在 "User 4" 帐户的 "属性" 中，确认未分配任何产品许可证，并且没有组成员身份。
7. 有关 **联系人信息**，请选择 " **编辑**"。
8. 在 " **编辑联系人信息** " 窗格中，选择 " **联系人信息**"。
9. 在 "**部门**" 框中，输入**Sales**，然后选择 "**保存**" "  >  **关闭**"。
10. 等待几分钟，然后定期选择 "用户 4" 帐户窗格右上角的 " **刷新** " 图标。

此时，您应看到以下内容：

- 更新了**Sales**组的**组成员身份**属性。
- 使用**Microsoft 365 E5**许可证更新的 "**产品许可证**" 属性。

请参阅以下文章以在生产环境中部署动态组成员身份和自动许可：

- [Azure Active Directory 中的基于组的许可](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Azure Active Directory 中的动态组](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[标识路线图](identity-roadmap-microsoft-365.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](https://docs.microsoft.com/microsoft-365-enterprise/)
