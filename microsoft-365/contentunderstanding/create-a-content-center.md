---
title: 在 Microsoft SharePoint Syntex 中创建内容中心
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 了解如何创建内容中心。
ms.openlocfilehash: 34ba45cd62214743e5a6784893e0f24e9815fdfb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905820"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a>在 Microsoft SharePoint Syntex 中创建内容中心


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

要创建和管理文档理解模型，首先需要内容中心。 内容中心是模型创建界面，它还包含已应用文档库发布模型的相关信息。</br>

   ![选择文档库](../media/content-understanding/content-center-page.png)</br>

[设置](set-up-content-understanding.md)期间创建默认内容中心。 但 SharePoint 管理员也可根据需要选择创建其他中心。 虽然单个内容中心对于你想汇总所有模型活动的环境可能不错，但你可能希望组织中多个部门有其他中心，这可能对其模型有不同需求和权限要求。

> [!NOTE]
> 在 [Microsoft 365 多地理环境](../enterprise/microsoft-365-multi-geo.md)中，如果中心位置中具有一个默认内容中心，则只能提供该位置内的模型活动汇总。 当前无法在多地理环境中跨服务器场边界汇总模型活动。 


## <a name="create-a-content-center"></a>创建内容中心

SharePoint 管理员可以创建内容中心网站，就像通过管理中心网站预配面板 [创建任何其他 SharePoint 网站](/sharepoint/create-site-collection) 一样。

创建新的内容中心：

1. 在 Microsoft 365 管理中心，转到 SharePoint 管理中心。

2. 在 SharePoint 管理中心的“**网站**”下，选择“**活动网站**”。

3. 在“**活动网站**”页面上，单击“**创建**”，然后选择“**其他选项**”。

4. 在“**选择模板**”菜单上，选择“**内容中心**”。

5. 对于新网站，提供 **网站名称**、**主管理员** 和 **语言**。</br>

   > [!NOTE] 
   > 可选择一个内容中心网站呈现任意可用语言，但请注意，当前模型仅可为英语文件创建。 另请注意，与其他网站模板一样，网站创建后，默认网站语言不可编辑。</br>

6. 选择“**已完成**”。
 
创建内容中心网站后，将看到它在 SharePoint 管理中心的“**活动网站**”页面上列出。 

### <a name="give-access-to-additional-users"></a>授予其他用户访问权限
 
创建网站后，可通过标准的 [SharePoint 网站权限模型](/sharepoint/modern-experience-sharing-permissions)授予其他用户网站访问权限。

## <a name="see-also"></a>另请参阅
[创建分类器](create-a-classifier.md)

[创建提取程序](create-an-extractor.md)

[创建内容中心](create-a-content-center.md)

[文档理解概述](document-understanding-overview.md)

[创建表单处理模型](create-a-form-processing-model.md)

[应用模型](apply-a-model.md)