---
title: 适用于 Microsoft 365 企业版测试环境的数据分类
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
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487728"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>适用于 Microsoft 365 企业版测试环境的数据分类

*此测试实验室指南可用于适用于企业和 Office 365 企业测试环境的 Microsoft 365。*

本文介绍如何在 Microsoft 365 企业版测试环境中使用保留标签配置数据分类。

对测试环境中的数据进行分类包括三个阶段：
- [第1阶段：构建您的 Microsoft 365 企业版测试环境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [阶段2：创建保留标签](#phase-2-create-retention-labels)
- [第3阶段：将保留标签应用于文档](#phase-3-apply-retention-labels-to-documents)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第1阶段：构建您的 Microsoft 365 企业版测试环境

如果只想使用最低要求以轻型方式配置保留标签，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。
  
如果要在模拟的企业中配置保留标签，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。
  
> [!NOTE]
> 测试保留标签不需要模拟企业测试环境，其中包括连接到 internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。 它作为选项提供，以便您可以测试自动授权和组成员身份，并在代表典型组织的环境中进行试验。

## <a name="phase-2-create-retention-labels"></a>阶段2：创建保留标签

在此阶段，为 SharePoint Online 文档文件夹的不同保留级别创建保留标签：

1. 使用全局管理员帐户登录 [Microsoft 365 安全中心](https://security.microsoft.com/homepage) 。
1. 从浏览器的 "**主页-Microsoft 365 安全**" 选项卡中，选择 "**分类**  >  **保留标签**"。
1. 选择“**创建标签**”。
1. 在 "**命名标签**" 窗格中，在 "**命名" 标签**中输入 "**内部公用**"，然后选择 "**下一步**"。
1. 在 " **文件计划描述符** " 窗格中，选择 " **下一步**"。
1. 在 " **标签设置** " 窗格中，根据需要将 " **保留** " 设置为 **"开**"，然后选择 " **下一步**"。
1. 在 " **查看设置** " 窗格中，选择 **"创建标签"**。
1. 对具有以下名称的其他标签重复步骤 3-7：
  - Private
  - 敏感
  - 高度机密
1. 在 " **保留标签** " 窗格中，选择 " **发布标签**"。
1. 在 " **选择要发布的标签** " 窗格中，选择 " **选择要发布的标签**"。
1. 在 " **选择标签** " 窗格中，选择 " **添加** "，然后选择全部四个标签。
1. 选择 " **添加**"，然后选择 " **完成**"。
1. 在 " **选择要发布的标签** " 窗格中，选择 " **下一步**"。
1. 在 " **选择位置** " 窗格中，选择 " **下一步**"。
1. 在 "**命名策略**" 窗格中，在 "**名称**" 中输入**示例组织**，然后选择 "**下一步**"。
1. 在 " **查看设置** " 窗格中，选择 " **发布标签**"。
 
发布保留标签可能需要几分钟时间。

## <a name="phase-3-apply-retention-labels-to-documents"></a>第3阶段：将保留标签应用于文档

在此阶段中，您将发现 SharePoint Online 网站的 Documents 文件夹中的文件的默认保留标签行为，并手动更改文档的保留标签。

首先，创建一个敏感级别的 SharePoint Online 团队网站：
  
1. 使用浏览器的专用实例，使用全局管理员帐户登录 [Microsoft 365 管理中心](https://admin.microsoft.com) 。
1. 在磁贴列表中，选择 " **SharePoint**"。
1. 在浏览器的 "新建 **SharePoint** " 选项卡上，选择 " **创建网站**"。
1. 在“创建网站”**** 页中，选择“团队网站”****。
1. 在 " **团队网站名称** " 框中，输入 **SensitiveFiles**。
1. 在 " **团队网站说明** " 框中，输入 **敏感文件的 SharePoint 网站**。
1. 在 " **隐私设置**" 中，选择 " **仅专用成员可以访问此网站**"，然后选择 " **下一步**"。
1. 在 " **要添加哪些用户？"** 窗格中，选择 " **完成**"。
    
接下来，为敏感保留标签配置 SensitiveFiles 团队网站的 Documents 文件夹。
  
1. 在浏览器的 " **SensitiveFiles** " 选项卡中，选择 " **文档**"。
1. 选择 " **设置** " 图标，然后选择 " **库设置**"。
1. 在 " **权限和管理**" 下，选择 " **将标签应用于此列表或库中的项目**"。 如果未显示此选项，则您的保留标签尚未发布。 稍后请尝试执行此步骤。
1. 在 " **设置-应用标签**" 中，选择下拉框中的 " **敏感** "，然后选择 " **保存**"。

接下来，在 SensitiveFiles 网站中创建一个新文档并更改其保留标签。
    
1. 在 "文档" 文件夹中，选择 "**新建**  >  **Word 文档**"。
1. 在空白文档中输入一些文本。 等待文本保存。
1. 在菜单栏上，选择 " **共享文档**"。
1. 在 " **Document.docx** 文件名旁边，选择垂直省略号，然后选择" **详细信息**"。
1. 在右侧窗格中的 " **属性** " 部分的 " **应用保留标签**" 下，请注意文档是否已自动应用 " **敏感** 保留" 标签。
1. 单击“编辑全部”****。
1. 在 " **Document.docx** " 窗格中的 " **应用保留标签**" 下，选择 " **高度机密** " 标签，然后选择 " **保存**"。

## <a name="next-step"></a>后续步骤

在您的测试环境中浏览其他 [信息保护](m365-enterprise-test-lab-guides.md#information-protection) 特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](https://docs.microsoft.com/microsoft-365-enterprise/)
