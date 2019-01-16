---
title: 自动为您的 Microsoft 365 企业版测试环境的许可和组成员身份
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Microsoft 365 企业版测试环境中配置基于组的许可和动态组成员身份。
ms.openlocfilehash: 45a78af202f2d9ab029683aae4d95ed9a3370b08
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865787"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>自动为您的 Microsoft 365 企业版测试环境的许可和组成员身份

基于组的自动许可分配或删除许可证根据组成员身份的用户帐户。动态组成员身份添加或删除成员添加到一组基于用户帐户属性，如部门或国家/地区。本文将向您演示 Microsoft 365 企业版测试环境中的这两种。

有两个阶段设置 Microsoft 365 企业版测试环境中的自动许可和动态组成员身份：

1. 创建 Microsoft 365 企业版测试环境。
2. 配置和测试动态组成员身份和自动许可。

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>第 1 阶段： 构建 Microsoft 365 企业版测试环境

如果您只想要的最低硬件要求与轻型方式测试自动许可和组成员身份，按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。
  
如果您想要在模拟企业中测试自动许可和组成员身份，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。
  
> [!NOTE]
> 测试自动许可和组成员身份不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试自动许可和组成员身份并与之试验环境值，该值代表典型组织中。 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>第 2 阶段： 配置和测试动态组成员身份和自动许可

首先，创建一个新的销售组，并添加动态组成员资格规则，以便与设置为销售部门的用户帐户会自动添加到 Sales 组。

1. 使用专用的 Internet 浏览器实例时，登录到 Office 门户[https://office.com](https://office.com)与您的 Office 365 E5 试用订阅的全局管理员帐户。
2. 在浏览器的独立选项卡上，转到在 Azure 门户[https://portal.azure.com](https://portal.azure.com)。
3. 在 Azure 门户中，单击“Azure Active Directory”>“用户和组”>“所有组”****。
4. 在**所有组**刀片中，单击**新组**。
5. 在**组类型**中，选择**Office 365**。
6. 在**组名**框中，键入**销售**。
7. 在**成员资格类型**中，选择**动态用户**。
8. 单击“添加动态查询”****。
9. 在“添加以下位置的用户”**** 中，选择“部门”****。
10. 在下一个字段中，选择“等于”****。
11. 在下一步字段中，键入**销售**。
12. 单击“添加查询”****，然后单击“创建”****。
13. 关闭**组**和**组的所有组**刀片。

接下来，您配置 Sales 组，以便 Office 365 E5 和企业移动多个安全 E5 许可证自动分配成员。

1. 在 Azure Active Directory**概述**刀片中，单击**许可证 > 所有产品**。
2. 在列表中，选择“**企业移动性 + 安全性 E5**”和“**Office 365 企业版 E5**”，然后单击“**分配**”。
3. 在**分配许可证**刀片中，单击**用户和组**。
4. 在组列表中，选择**销售**组。
5. 单击“**选择**”，然后单击“**分配**”。
6. 关闭浏览器中的 Azure 门户选项卡。

接下来，测试动态组成员身份和用户 4 帐户自动许可。 

1. 从**Microsoft Office Home**选项卡上的在浏览器中，单击**管理**。
2. 从**Office Admin center**选项卡，单击**活动用户**。
3. 在**活动用户**页上，单击**用户 4**帐户。
4. 在**用户 4**窗格中，单击**产品**许可证的**编辑**。
5. 在**产品许可证**窗格中，打开**企业移动 + 安全 E5**和**Office 365 企业 E5**许可证关闭，然后单击**保存 > 关闭**。
6. 在用户 4 帐户的属性，确认没有产品许可证已分配不有任何组成员身份。
7. **联系人**信息，请单击**编辑**。
8. 在**编辑联系人信息**窗格中，单击**联系人信息**。
9. 在**部门**字段中，键入**销售**、，然后单击**保存 > 关闭**。
10. 等待几分钟，然后定期单击右上角用户 4 帐户窗格中的刷新图标。 

您应看到时间:

- 使用**销售**组进行了更新的**组成员身份**属性。
- 更新了**企业移动 + 安全 E5**和**Office 365 企业 E5**许可证**产品许可证**属性。

有关信息和链接部署动态组成员身份和生产环境中自动许可的标识阶段，请参阅以下步骤：

- [设置自动许可](identity-group-based-licensing.md)
- [设置动态组成员身份](identity-automatic-group-membership.md)

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[阶段 2：身份](identity-infrastructure.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企业版文档](https://docs.microsoft.com/microsoft-365-enterprise/)
