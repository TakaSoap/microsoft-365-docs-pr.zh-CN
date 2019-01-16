---
title: Microsoft 365 企业版的数据分类测试环境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南创建和使用 Office 365 标签对 Microsoft 365 企业版测试环境中的文档。
ms.openlocfilehash: 33ac1fa8e26c0037882e6c240cc04ec19e6a6a7b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866013"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 企业版的数据分类测试环境

使用本文中的说明，您可以配置 Microsoft 365 企业版在测试环境中使用 Office 365 保留标签的数据分类。

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>第 1 阶段： 构建 Microsoft 365 企业版测试环境

如果您只想要配置轻型方式的最低硬件要求与 Office 365 标签，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。
  
如果您想要配置模拟企业中的 Office 365 标签，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。
  
> [!NOTE]
> 测试 Office 365 标签不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试自动许可和组成员身份并与之试验环境值，该值代表典型组织中。 

## <a name="phase-2-create-office-365-labels"></a>第 2 阶段：创建 Office 365 标签

在此阶段中，您将创建为 SharePoint Online 文档文件夹的保留的不同级别的标签。
  
1. 如果需要使用专用的 Internet 浏览器实例，并登录到您的全局管理员帐户的 Office 门户。为了帮助，请参阅[从何处登录到 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。
    
2. 在“**Microsoft Office 主页**”标签页中，单击“**管理**”磁贴。
    
3. 在浏览器的新“Office 管理中心”**** 标签页中，单击“管理中心”>“安全&amp;合规性”****。
    
4. 从新**主页-安全&amp;合规性**选项卡上的浏览器中，单击**分类 > 标签**。从**主页 > 标签**窗格中，单击**保留**选项卡。
    
5. 单击**创建标签**。
    
6. 在“**命名标签**”窗格中，键入“**内部公用**”，然后单击“**下一步**”。
    
7. 在“**标签设置**”窗格中，单击“**下一步**”。
    
8. 在“查看设置”**** 窗格中，单击“创建此标签”****，然后单击“关闭”****。
    
9. 对以下标签重复步骤 5-8：
    
  - Private
    
  - 敏感
    
  - 高度机密
    
10. 在“开始”>“标签”窗格中，单击“发布标签”********。
    
11. 在“选择要发布的标签”窗格中，单击“选择要发布的标签”********。
    
12. 在“选择标签”窗格中，单击“添加”并选择全部四个标签********。
    
13. 单击“完成”****。
    
14. 在“选择要发布的标签”窗格中，单击“下一步”********。
    
15. 在“**选择位置**”窗格中，单击“**下一步**”。
    
16. 在“**命名策略**”窗格中，在“**名称**”中键入“**示例组织**”，然后单击“**下一步**”。
    
17. 在“**查看设置**”窗格中，单击“**发布标签**”，然后单击“**关闭**”。

请注意，可能需要几分钟，要发布的标签。

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a>第 3 阶段： 将 Office 365 保留标签应用于文档

在此阶段中，可以发现的 SharePoint Online 网站的文档文件夹中的文件的默认标签行为和手动更改文档的标签。

首先，创建敏感级别 SharePoint Online 团队网站：
  
1. 在本地计算机上使用浏览器中，登录到 Office 门户使用全局管理员帐户。为了帮助，请参阅[从何处登录到 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。
    
2. 在磁贴列表中，单击“SharePoint”****。
    
3. 在新**SharePoint**选项卡在浏览器中，单击**创建网站**。
    
4. 在“创建网站”页中，单击“团队网站”********。
    
5. 在**工作组网站名称**框中，键入**SensitiveFiles**。
    
6. 在**团队网站说明**框中，键入**敏感文件的 SharePoint 网站**。
    
7.  在“**隐私设置**”中，选择“**专用 - 仅成员可以访问此网站**”，然后单击“**下一步**”。
    
8. 在“**希望添加哪些人员?**”窗格中，单击“**完成**”。
    
接下来，配置敏感标签 SensitiveFiles 工作组网站的文档文件夹。
  
1. 在浏览器的**SensitiveFiles**选项卡上，单击**文档**。
    
2. 单击设置图标，然后单击“**库设置**”。
    
3. 在“权限和管理”下，单击“向此库中的项应用标签”********。
    
4. 在**设置应用标签**，在下拉列表框中，选择**敏感**，然后单击**保存**。

接下来，SensitiveFiles 网站中创建一个新文档，并更改其标签。
    
1. 在文档文件夹中，单击**新建 > Word 文档**。
    
2. 空白文档中键入一些文本。等待要保存的文本。
    
3. 在菜单栏中，单击**共享文档**。
    
4. 单击**Document.docx**文件名旁边的 Word 图标。
    
5. 在右侧窗格中，在**属性**部分下**应用保留标签**，请注意文档已自动应用**敏感**标签。
    
6. 单击**编辑所有**。
    
7. 在**Document.docx**窗格中的**应用标签**、 下，选择的**高度机密**标签，然后单击**保存**。

有关信息和生产环境中的 Office 365 保留标签的链接的**信息保护**阶段，请参阅[针对您的环境配置分类](infoprotect-configure-classification.md)步骤。

## <a name="next-step"></a>后续步骤

浏览您的测试环境中其他[信息保护](m365-enterprise-test-lab-guides.md#information-protection)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企业版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企业版文档](https://docs.microsoft.com/microsoft-365-enterprise/)

 