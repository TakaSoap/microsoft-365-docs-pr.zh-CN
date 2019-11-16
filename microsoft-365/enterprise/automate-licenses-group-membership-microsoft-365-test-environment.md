---
title: 自动化 Microsoft 365 企业版测试环境的许可和组成员身份
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 在 Microsoft 365 企业版测试环境中配置基于组的许可和动态组成员身份。
ms.openlocfilehash: fe6380d94919556904a1fb1ac0624fac3496fe30
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673248"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>自动化 Microsoft 365 企业版测试环境的许可和组成员身份

*此测试实验室指南仅可用于 Microsoft 365 企业版测试环境。*

基于组的许可根据组成员身份自动分配或删除用户帐户的许可证。 动态组成员身份根据用户帐户属性（如部门或国家/地区）添加或删除组中的成员。 本文将指导您完成 Microsoft 365 企业版测试环境中的两个演示。

在 Microsoft 365 企业版测试环境中设置自动许可和动态组成员身份有两个阶段：

1. 创建 Microsoft 365 企业版测试环境。
2. 配置和测试动态组成员身份和自动许可。

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 单击[此处](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>阶段 1：构建 Microsoft 365 企业版测试环境。

如果只想使用最低要求以轻型方式测试自动许可和组成员身份，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。
  
如果要在模拟的企业中测试自动授权和组成员身份，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。
  
> [!NOTE]
> 测试自动许可和组成员身份不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务（AD DS）林的目录同步。 此处提供了此选项，以便您可以测试自动授权和组成员身份，并在代表典型组织的环境中进行试验。 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>第2阶段：配置和测试动态组成员身份和自动许可

首先，创建一个新的 Sales 组并添加一个动态组成员身份规则，以便将部门设置为 "销售" 的用户帐户自动添加到 "销售" 组中。

1. 使用 Internet 浏览器的专用实例， [https://portal.office.com](https://portal.office.com)使用 Office 365 E5 测试实验室订阅的全局管理员帐户登录到 office 365 门户。
2. 在浏览器的一个单独的选项卡上，转到 Azure [https://portal.azure.com](https://portal.azure.com)门户处。
3. 在 Azure 门户中，单击“Azure Active Directory”>“用户和组”>“所有组”****。
4. 在 "**所有组**" 边栏选项卡上，单击 "**新建组**"。
5. 在 "**组类型**" 中，选择 " **Office 365**"。
6. 在 "**组名称**" 中，键入**Sales**。
7. 在 "**成员身份类型**" 中，选择 "**动态用户**"。
8. 单击“添加动态查询”****。
9. 在“添加以下位置的用户”**** 中，选择“部门”****。
10. 在下一个字段中，选择“等于”****。
11. 在下一个字段中，键入**Sales**。
12. 单击“添加查询”****，然后单击“创建”****。
13. 关闭 "**组**" 和 "**组"-"所有组**" 刀片。

接下来，配置 Sales 组，以便自动为成员分配 Office 365 E5 和企业移动性 + 安全 E5 许可证。

1. 在 "适用于 Azure Active Directory 的**概述**刀片" 中，单击 "**许可证 > 所有产品**"。
2. 在列表中，选择“**企业移动性 + 安全性 E5**”和“**Office 365 企业版 E5**”，然后单击“**分配**”。
3. 在 "**分配许可证**" 边栏选项卡上，单击 "**用户和组**"。
4. 在组列表中，选择 "**销售**" 组。
5. 单击“**选择**”，然后单击“**分配**”。
6. 关闭浏览器中的 Azure 门户选项卡。

接下来，在用户4帐户上测试动态组成员身份和自动许可。 

1. 在浏览器中的 " **Microsoft Office 主页**" 选项卡上，单击 "**管理**"。
2. 在 " **Microsoft 365 管理中心**" 选项卡上，单击 "**活动用户**"。
3. 在 "**活动用户**" 页上，单击 "**用户 4** " 帐户。
4. 在 "**用户 4** " 窗格中，单击 "**产品许可证**" 的 "**编辑**"。
5. 在 "**产品许可证**" 窗格中，关闭**企业移动性 + 安全 E5**和**Office 365 企业版 E5**许可证，然后单击 "**保存" > "关闭**"。
6. 在 "User 4" 帐户的 "属性" 中，确认未分配任何产品许可证，并且没有组成员身份。
7. 单击**** "编辑**联系人信息**"。
8. 在 "**编辑联系人信息**" 窗格中，单击 "**联系人信息**"。
9. 在 "**部门**" 字段中，键入**Sales**，然后单击 "**保存" > "关闭**"。
10. 等待几分钟，然后定期单击 "用户 4" 帐户窗格右上角的 "刷新" 图标。 

您应该会看到以下内容：

- 更新了**Sales**组的**组成员身份**属性。
- 使用**企业移动性 + 安全 E5**和**Office 365 企业版 e5**许可证更新的**产品许可证**属性。

请参阅 Identity 阶段的这些步骤，了解在生产中部署动态组成员身份和自动许可的信息和链接：

- [设置自动许可](identity-use-group-management.md#identity-group-license)
- [设置动态组成员身份](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[阶段 2：标识](identity-infrastructure.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企业版文档](https://docs.microsoft.com/microsoft-365-enterprise/)
