---
title: '设置内容了解（预览） '
description: 如何设置项目 Cortex。
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: fca80e45dfa45ee5da9521854c6eebfbd87d8859
ms.sourcegitcommit: 91c82a79962387205c4dd4dd8d61322b79fed55f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2020
ms.locfileid: "46539898"
---
# <a name="set-up-content-understanding-preview"></a>设置内容了解（预览）

> [!Note] 
> 本文中的内容适用于 Project Cortex 私人预览。 了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。

管理员可以使用 Microsoft 365 管理中心来设置和配置内容了解。 

在安装之前，请务必规划在您的环境中设置和配置内容理解的最佳方式。 例如，你将需要考虑以下事项：
- 您将在哪些 SharePoint 网站上启用表单处理？ 所有用户、部分或选择网站？
- 您的内容中心的名称，以及谁是主网站管理员？

管理员还可以在安装完成后通过 Microsoft 365 管理中心中的内容了解管理设置来随时更改所选的设置。


## <a name="requirements"></a>Requirements 
您必须具有全局管理员或 SharePoint 管理员权限才能访问 Microsoft 365 管理中心并设置内容了解。


## <a name="to-set-up-content-understanding"></a>设置内容了解

1. 在 Microsoft 365 管理中心，选择 "**设置**"，然后查看 "**组织知识库**" 部分。
2. 在 "**组织知识库**" 部分，选择 "**自动内容理解**"。<br/>

    ![组织知识设置页](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. 在 "**自动内容理解**" 页上，单击 "**入门**" 以引导您完成设置过程。<br/>

    ![开始安装](../media/content-understanding/admin-content-understanding-get-started.png)</br>


4. 在 "**配置表单处理**" 页上，您可以选择是否希望让用户能够使用 AI 生成器在特定的 SharePoint 文档库中创建表单处理模型。 "文档库" 功能区中将提供一个菜单选项，以便在启用了 SharePoint 文档库中**创建表单处理模型**。
 
     对于**哪个 SharePoint 库应显示用于创建表单处理模型的选项**，您可以选择：</br>
    - **所有 sharepoint 库**，使其可用于租户中的所有 sharepoint 库。</br>
    - **仅选定网站中的库**，然后选择要使其可用的网站。</br>
    - 如果当前不希望使其对任何网站可用（可以在安装后更改此库），则**没有 SharePoint 库**。
</br>

   ![配置表单处理](../media/content-understanding/admin-configforms.png)
</br>

   > [!Note]
   > 在 SharePoint 文档库上启用此设置不会影响应用于库的现有模型，也不会影响将文档理解模型应用于库的功能。 

    
5. 在 "**创建内容中心**" 页上，您可以创建 SharePoint 内容中心网站，用户可以在该网站上创建和管理文档理解模型。 </br>
    a. 在 "**网站名称**" 中，键入要为内容中心网站提供的名称。</br>
    b. **网站地址**将根据您为网站名称选择的内容显示网站的 URL。</br>

    > [!Note] 
    > 虽然您可以选择任何支持的语言，但请注意，只能为英语创建内容理解模型。</br>

      ![创建内容中心](../media/content-understanding/admin-cu-create-cc.png)</br>


    选择“**下一步**”。
6. 在 "**完成并检查**" 页上，您可以查看选定的设置并选择进行更改。 如果您对所做的选择感到满意，请选择 "**激活**"。



7. **内容理解激活**的页面将会显示，确认系统已添加表单处理首选项并创建内容中心网站。 选择“完成”****。

8. 您将返回到 "**自动内容理解**" 页面。 在此页面中，您可以选择 "**管理**" 以对配置设置进行任何更改。 

## <a name="see-also"></a>另请参阅



  






