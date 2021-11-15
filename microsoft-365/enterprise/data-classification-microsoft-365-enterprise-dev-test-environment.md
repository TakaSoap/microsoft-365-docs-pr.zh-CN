---
title: 企业测试环境Microsoft 365数据分类
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: M365-security-compliance
ms.custom:
- Ent_TLGs
- admindeeplinkMAC
- admindeeplinkDEFENDER
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南创建和使用企业测试环境中 Microsoft 365文档的保留标签。
ms.openlocfilehash: 517183ca8e61415ec2817683c4a1ce88c251301b
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2021
ms.locfileid: "60962563"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>企业测试环境Microsoft 365数据分类

*本测试实验室指南可用于企业Microsoft 365和Office 365 企业版环境。*

本文介绍如何在企业测试环境中使用 Microsoft 365配置数据分类。

对测试环境中的数据进行分类分为三个阶段：
- [第 1 阶段：构建Microsoft 365测试环境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [阶段 2：创建保留标签](#phase-2-create-retention-labels)
- [阶段 3：将保留标签应用于文档](#phase-3-apply-retention-labels-to-documents)

![Microsoft 云的测试实验室指南。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 有关企业测试实验室指南堆栈中Microsoft 365文章的直观映射，请转到 Microsoft 365 [for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第 1 阶段：构建Microsoft 365测试环境

如果你只想按最低要求以轻型方式配置保留标签，请按照轻型基本配置 [中的说明操作](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
如果要在模拟的企业中配置保留标签，请按照传递 [身份验证 中的说明操作](pass-through-auth-m365-ent-test-environment.md)。
  
> [!NOTE]
> 测试保留标签不需要模拟的企业测试环境，该环境中包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务 (AD DS) 同步。 它在此处作为一个选项提供，以便你可以测试自动许可和组成员身份，并尝试在代表典型组织的环境中进行试验。

## <a name="phase-2-create-retention-labels"></a>阶段 2：创建保留标签

在此阶段，为联机文档文件夹的不同保留级别SharePoint保留标签：

1. 使用全局管理员<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365</a>登录安全中心。
1. 从浏览器 **的"** 主页 - Microsoft 365安全"选项卡中，选择"**分类保留**  >  **标签"。**
1. 选择“**创建标签**”。
1. 在"**命名标签"窗格中****，在"** 命名标签"中 **输入**"内部公用"，然后选择"下一步 **"。**
1. 在"**文件计划描述符"窗格中**，选择"下一 **步"。**
1. 在"**标签设置"** 窗格中，根据需要将 **"保留**"设置为 **"打开**"，然后选择"下一 **步"。**
1. 在"**查看设置"窗格中**，选择 **"创建标签"。**
1. 对具有以下名称的其他标签重复步骤 3-7：
  - Private
  - 敏感
  - 高度机密
1. 在"**保留标签"窗格中**，选择"**发布标签"。**
1. 在"**选择要发布的标签"窗格中**，**选择"选择要发布的标签"。**
1. 在" **选择标签"** 窗格中，选择 **"添加"** 并选择所有四个标签。
1. 选择 **"添加**"，然后选择"完成 **"。**
1. 在"**选择要发布的标签"窗格中，** 选择"下一 **步"。**
1. 在"**选择位置"窗格中**，选择"下一 **步"。**
1. 在"**命名策略"窗格中**，在"名称"**中输入"****示例组织**"，然后选择"下一 **步"。**
1. 在"**查看设置"窗格中**，选择"**发布标签"。**
 
可能需要几分钟才能发布保留标签。

## <a name="phase-3-apply-retention-labels-to-documents"></a>阶段 3：将保留标签应用于文档

在此阶段中，您将发现 SharePoint Online 网站的"文档"文件夹中的文件的默认保留标签行为，并手动更改文档的保留标签。

首先，在 Online 团队网站SharePoint敏感级别：
  
1. 使用浏览器的专用实例，使用全局<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理员Microsoft 365 管理中心</a>登录浏览器。
1. 在磁贴列表中，选择 **"SharePoint"。**
1. 在浏览器的新 **SharePoint** 选项卡上，选择"**创建网站"。**
1. 在“创建网站”页中，选择“团队网站”。
1. 在" **团队网站名称"** 框中，输入 **SensitiveFiles**。
1. 在"**团队网站说明"** 框中 **，SharePoint敏感文件的网站"。**
1. 在 **"隐私设置**"**中，选择"专用 - 只有成员可以访问此网站**"，然后选择"下一 **步"。**
1. 在Who **添加？"窗格中，** 选择"完成 **"。**
    
接下来，为敏感保留标签配置 SensitiveFiles 团队网站的 Documents 文件夹。
  
1. 在浏览器 **的"SensitiveFiles"** 选项卡中，选择"文档 **"。**
1. 选择 **"设置** 图标，然后选择"**库设置"。**
1. 在 **"权限和管理"下**，**选择"将标签应用于此列表或库中的项目"。** 如果未显示此选项，则尚未发布保留标签。 稍后尝试执行此步骤。
1. 在 **设置应用标签**"中，选择下拉框中的"敏感"，然后选择"保存 **"。**

接下来，在 SensitiveFiles 网站中创建新文档并更改其保留标签。
    
1. 在"文档"文件夹中，选择"**新建**  >  **Word 文档"。**
1. 在空白文档中输入一些文本。 等待保存文本。
1. 在菜单栏上，选择"**共享文档"。**
1. 在文件 **Document.docx，** 选择垂直省略号， **然后选择详细信息**。
1. 在右窗格的"属性"**部分，****在"** 应用保留标签"下，请注意，文档已自动应用"**敏感**"保留标签。
1. 单击 **编辑全部**。
1. 在 **"Document.docx"** 窗格中的"**应用保留** 标签"下，选择"**高度机密"标签**，然后选择"保存 **"。**

## <a name="next-step"></a>后续步骤

探索 [测试环境中](m365-enterprise-test-lab-guides.md#information-protection) 的其他信息保护特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](/microsoft-365-enterprise/)