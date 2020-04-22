---
title: Microsoft 365 企业版测试环境的数据分类
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南可在 Microsoft 365 企业版测试环境中的文档上创建和使用保留标签。
ms.openlocfilehash: 41873eba8f2d6168d68d771c6feb17a44c775f6a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636088"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 企业版测试环境的数据分类

*此测试实验室指南可用于 Microsoft 365 企业版和 Office 365 企业版测试环境。*

使用本文中的说明，可以在 Microsoft 365 企业版测试环境中使用保留标签配置数据分类。

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 单击[此处](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>阶段 1：构建 Microsoft 365 企业版测试环境。

如果只想使用最低要求以轻型方式配置保留标签，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。
  
如果要在模拟的企业中配置保留标签，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。
  
> [!NOTE]
> 测试保留标签不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务（AD DS）林的目录同步。 此处提供了此选项，以便您可以测试自动授权和组成员身份，并在代表典型组织的环境中进行试验。 

## <a name="phase-2-create-retention-labels"></a>阶段2：创建保留标签

在此阶段中，您将为 SharePoint Online 文档文件夹的不同保留级别创建保留标签。

1. 使用全局管理员帐户登录[Microsoft 365 安全中心](https://security.microsoft.com/homepage)。
    
2. 在浏览器的 "**主页-Microsoft 365 安全**" 选项卡中，单击 "**分类 > 保留标签**"。
    
3. 单击“**创建标签**”。
    
4. 在 "**命名标签**" 窗格中，在 "**命名" 标签**中键入**Internal Public** ，然后单击 "**下一步**"。

5. 在 "**文件计划描述符**" 窗格中，单击 "**下一步**"。
    
6. 在 "**标签设置**" 窗格中，根据需要将 "**保留**" 设置为 **"开**"，然后单击 "**下一步**"。
    
7. 在 "**查看设置**" 窗格中，单击 "**创建标签"**。
    
8. 对具有以下名称的其他标签重复步骤 3-7：
    
  - Private
    
  - 敏感
    
  - 高度机密
  
9. 在 "**保留标签**" 窗格中，单击 "**发布标签**"。
    
10. 在 "**选择要发布的标签**" 窗格中，单击 "**选择要发布的标签**"。
    
11. 在 "**选择标签**" 窗格中，单击 "**添加**"，然后选择全部四个标签。
    
12. 单击 "**添加**"，然后单击 "**完成**"。
    
13. 在“选择要发布的标签”窗格中，单击“下一步”********。
    
14. 在“**选择位置**”窗格中，单击“**下一步**”。
    
15. 在“**命名策略**”窗格中，在“**名称**”中键入“**示例组织**”，然后单击“**下一步**”。
    
16. 在 "**查看设置**" 窗格中，单击 "**发布标签**"。
 
请注意，发布保留标签可能需要几分钟时间。

## <a name="phase-3-apply-retention-labels-to-documents"></a>第3阶段：将保留标签应用于文档

在此阶段中，您将发现 SharePoint Online 网站的 Documents 文件夹中的文件的默认保留标签行为，并手动更改文档的保留标签。

首先，创建一个敏感级别的 SharePoint Online 团队网站：
  
1. 使用浏览器的私有实例，使用全局管理员帐户登录到[Office 365 门户](https://portal.office.com)。
    
2. 在磁贴列表中，单击“SharePoint”****。
    
3. 在浏览器的 "新建**SharePoint** " 选项卡上，单击 "**创建网站**"。
    
4. 在“创建网站”页中，单击“团队网站”********。
    
5. 在 "**团队网站名称**" 中，键入**SensitiveFiles**。
    
6. 在 "**工作组网站说明**" 中，键入 " **SharePoint 网站" 以查找敏感文件**。
    
7.  在“隐私设置”中，选择“专用 - 仅成员可以访问此网站”，然后单击“下一步”************。
    
8. 在 "**要添加哪些用户？"** 窗格中，单击 "**完成**"。
    
接下来，为敏感保留标签配置 SensitiveFiles 团队网站的 Documents 文件夹。
  
1. 在浏览器的 " **SensitiveFiles** " 选项卡中，单击 "**文档**"。
    
2. 单击设置图标，然后单击“库设置”****。
    
3. 在 "**权限和管理**" 下，单击 "**将标签应用于此列表或库中的项目**"。 如果未显示此选项，则尚未发布你的保留标签。 稍后请尝试执行此步骤。
    
4. 在 "**设置-应用标签**" 中，选择下拉框中的 "**敏感**"，然后单击 "**保存**"。

接下来，在 SensitiveFiles 网站中创建一个新文档并更改其保留标签。
    
1. 在 "文档" 文件夹中，单击 "**新建 > Word 文档**"。
    
2. 在空白文档中键入一些文本。 等待文本保存。
    
3. 在菜单栏中，单击 "**共享文档**"。
    
4. 单击**文档 .docx**文件名旁边的垂直省略号，然后单击 "**详细信息**"。
    
5. 在右侧窗格中的 "**属性**" 部分的 "**应用保留标签**" 下，请注意文档是否已自动应用 "**敏感**保留" 标签。
    
6. 单击 "**编辑全部**"。
    
7. 在 "**文档 .docx** " 窗格中，在 "**应用保留标签**" 下，选择 "**高度机密**" 标签，然后单击 "**保存**"。

若要了解如何在生产环境中部署保留标签的信息和链接，请参阅**信息保护**阶段的为[环境配置分类](infoprotect-configure-classification.md)步骤和链接。

## <a name="next-step"></a>后续步骤

在您的测试环境中浏览其他[信息保护](m365-enterprise-test-lab-guides.md#information-protection)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企业版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企业版文档](https://docs.microsoft.com/microsoft-365-enterprise/)

 
