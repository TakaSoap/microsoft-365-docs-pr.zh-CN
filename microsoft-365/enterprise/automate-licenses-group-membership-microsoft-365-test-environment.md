---
title: 针对企业测试环境自动Microsoft 365和组成员身份
f1.keywords:
  - NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: M365-identity-device-management
ms.custom:
  - TLG
  - Ent_TLGs
description: 在企业测试环境中配置基于组的许可和Microsoft 365组成员身份。
---

# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>针对企业测试环境自动Microsoft 365和组成员身份

*本测试实验室指南只能用于Microsoft 365测试环境。*

基于组的许可根据组成员身份自动分配或删除用户帐户的许可证。 动态组成员身份基于用户帐户属性（如部门或国家/地区）向组添加或删除 **成员**。 本文将分步演示在企业测试环境中Microsoft 365和删除组的成员。

在企业测试环境环境中Microsoft 365自动许可和动态组成员身份包括两个阶段：

- [第 1 阶段：构建Microsoft 365测试环境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [阶段 2：配置和测试动态组成员身份和自动许可](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Microsoft 云的测试实验室指南。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 有关企业测试实验室指南堆栈中Microsoft 365文章的直观映射，请转到 Microsoft 365 [企业测试实验室指南堆栈](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第 1 阶段：构建Microsoft 365测试环境

如果你希望仅测试具有最低要求的轻型自动许可和组成员身份，请按照轻型基本配置 [中的说明进行操作](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
如果要在模拟企业中测试自动许可和组成员身份，请按照传递身份验证 [中的说明操作](pass-through-auth-m365-ent-test-environment.md)。
  
> [!NOTE]
> 测试自动许可和组成员身份不需要模拟的企业测试环境，该环境包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务 (AD DS) 目录同步。 它在此处作为一个选项提供，以便你可以测试自动许可和组成员身份，并尝试在代表典型组织的环境中进行试验。
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>阶段 2：配置和测试动态组成员身份和自动许可

首先，创建一个名为 Sales 的新组，并添加动态组成员身份规则，以便部门设置为 **Sales** 的用户帐户自动加入销售组。

1. 在 Internet 浏览器的专用实例中，Microsoft 365 管理中心测试实验室订阅的[](https://admin.microsoft.com)全局管理员Microsoft 365 E5登录。
2. 在浏览器的单独选项卡上，转到 Azure 门户，位于 [https://portal.azure.com](https://portal.azure.com)。
3. 在 Azure 门户中，在 **搜索** 框中输入组，**然后选择组。**
4. 在" **所有组"窗格中** ，选择" **新建组"**。
5. 在 **"组类型"** 中，**选择"Microsoft 365"**。
6. 在 **"组名称"** 中，输入 **Sales**。
7. 在 **"成员身份类型"** 中，选择 **"动态用户"**。
8. 选择 **"动态用户成员"**。
9. 在" **动态成员资格规则"** 窗格中： 
   - 选择 **部门** 属性。
   - 选择 **"等于"** 运算符。
   - 在" **值"** 框中，输入 **Sales**。
10. 选择“保存”。
11. 选择“**创建**”。

接下来，配置"销售"组，以便自动为成员分配Microsoft 365 E5许可证。

1. 选择" **销售"** 组，然后选择"许可证 **"**。
2. 在"**更新许可证分配**"**窗格中，选择**"Microsoft 365 E5"，然后选择"保存 **"**。
3. 在浏览器中，关闭 Azure 门户选项卡。

接下来，在 User 4 帐户上测试动态组成员身份和自动许可：

1. 从浏览器 **Microsoft Office主页**"选项卡中，选择"**管理员"**。
2. 从"**Microsoft 365 管理中心**"选项卡中，选择"**活动用户"**。
3. 在" **活动用户"** 页上，选择 **"用户 4"** 帐户。
4. 在"**用户 4"** 窗格中，为 **"产品许可证****"选择"编辑"**。
5. 在"**产品许可证"** 窗格中 **，禁用Microsoft 365 E5** 许可证，然后选择"**SaveClose** > "。
6. 在 User 4 帐户的属性中，确认尚未分配任何产品许可证，并且没有组成员身份。
7. 对于 **"联系人信息"**，选择"编辑 **"**。
8. 在" **编辑联系人信息"窗格中** ，选择 **"联系人信息"**。
9. 在"**部门"** 框中，输入 **"销售"**，然后选择"**SaveClose** > "。
10. 等待几分钟，然后定期选择"用户 4"帐户窗格右上方的"刷新"图标。

随着时间的推移，你应该会看到：

- **使用 Sales 组** 更新的组 **成员身份** 属性。
- **使用产品** 许可证 **更新Microsoft 365 E5属性**。

请参阅以下文章以在生产中部署动态组成员身份和自动许可：

- [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Azure Active Directory 中的动态组](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[部署标识](deploy-identity-solution-overview.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](/microsoft-365-enterprise/)