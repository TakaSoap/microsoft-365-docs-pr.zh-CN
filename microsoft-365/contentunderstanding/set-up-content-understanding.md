---
title: 设置 SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 设置项目 Cortex 中的内容理解
ms.openlocfilehash: 31c6b6dd31b3f1bc47deb8424dd847cc0af6d429
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "48304776"
---
# <a name="set-up-sharepoint-syntex"></a>设置 SharePoint Syntex

管理员可以使用 Microsoft 365 管理中心设置和 Microsoft SharePoint Syntex。 

在开始之前，请考虑以下事项：

- 您将在哪些 SharePoint 网站上启用表单处理？ 所有用户、部分或选择网站？
- 您要将内容中心命名为什么，谁是主网站管理员？

你可以在 Microsoft 365 管理中心内初始安装后更改你的设置。

本文中的内容适用于 Project Cortex 私人预览。 了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。

在安装之前，请务必规划在您的环境中设置和配置内容理解的最佳方式。 例如，您需要考虑以下名称：

- 您要为其启用表单处理的 SharePoint 网站-所有用户、部分或选定网站
- 你的内容中心和主要网站管理员的名称

## <a name="requirements"></a>Requirements 

> [!NOTE]
> 您必须具有全局管理员或 SharePoint 管理员权限才能访问 Microsoft 365 管理中心并设置内容了解。

作为管理员，您还可以在安装后随时更改所选设置，并在 Microsoft 365 管理中心内的内容理解管理设置中进行更改。

## <a name="to-set-up-sharepoint-syntex"></a>设置 SharePoint Syntex

1. 在 Microsoft 365 管理中心，选择 " **设置**"，然后查看 " **组织知识库** " 部分。

2. 在 " **组织知识库** " 部分，选择 " **自动内容理解**"。<br/>

    ![组织知识设置页](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. 在 " **自动化 SharePoint Syntex** " 页上，单击 " **入门** " 以浏览安装过程。<br/>

    ![开始安装](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. 在 "打开图像标记" 页上，选择是否要允许 [图像标记](image-tagging.md)。

    ![图像标记选项的屏幕截图](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. 在 " **配置表单处理** " 页上，您可以选择是否希望让用户能够使用 AI 生成器在特定的 SharePoint 文档库中创建表单处理模型。 "文档库" 功能区中将提供一个菜单选项，以便在启用了 SharePoint 文档库中 **创建表单处理模型** 。
 
     对于 **哪个 SharePoint 库应显示用于创建表单处理模型的选项**，您可以选择：</br>
      - **所有 sharepoint 库** ，使其可用于组织中的所有 sharepoint 库。</br>
      - **仅选定网站中的库**，然后选择要使其可用的网站。</br>

   ![配置表单处理](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > 在 SharePoint 文档库上启用此设置不会影响应用于库的现有模型，也不会影响将文档理解模型应用于库的功能。 
    
6. 在 " **创建内容中心** " 页上，您可以创建 SharePoint 内容中心网站，用户可以在该网站上创建和管理文档理解模型。 </br>
    a. 在 " **网站名称**" 中，键入要为内容中心网站提供的名称。</br>
    b. **网站地址**将根据您为网站名称选择的内容显示网站的 URL。 如果要对其进行更改，请单击 " **编辑**"。</br>

      ![创建内容中心](../media/content-understanding/admin-cu-create-cc.png)</br>

    选择“**下一步**”。

7. 在 " **检查和完成** " 页上，您可以查看选定的设置并选择进行更改。 如果您对所做的选择感到满意，请选择 " **激活**"。

8. 在 "确认" 页上，单击 " **完成**"。

9. 您将返回到 " **自动内容理解** " 页面。 在此页面中，您可以选择 " **管理** " 以对配置设置进行任何更改。 

## <a name="assign-licenses"></a>分配许可证

配置 SharePoint Syntex 后，必须为将使用表单处理和文档理解功能的用户分配许可证。

要分配许可证，请执行以下操作：

1. 在 Microsoft 365 管理中心的 " **用户**" 下，单击 " **活动用户**"。

2. 选择要许可的用户，然后单击 " **管理产品许可证**"。

3. 选择 " **分配更多**"。

4. 选择 " **智能内容服务**"。 在 "**应用程序**" 下，确保同时选中 "智能内容服务" 和 "**智能内容服务**"**的通用数据服务**。

    ![Microsoft 365 管理中心中的 SharePoint Syntex 许可证](../media/content-understanding/sharepoint-syntex-licenses.png)

5. 单击“**保存更改**”。

## <a name="ai-builder-credits"></a>AI 生成器片尾

如果你的组织中有针对 SharePoint Syntex 的300或更多 SharePoint Syntex 许可证，则会向你分配 1000000 AI 生成器信用。 如果许可证数量少于300个，则必须购买 AI 生成器信用才能使用表单处理。

您可以使用 [Ai 生成器计算器](https://powerapps.microsoft.com/ai-builder-calculator)估计适合您的 ai 生成器容量。

请转到 [Power Platform 管理中心](https://admin.powerplatform.microsoft.com/resources/capacity) 查看你的学分和使用情况。

## <a name="see-also"></a>另请参阅

[表单处理模型概述](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[分步：了解如何构建文档理解模型 (视频) ](https://www.youtube.com/watch?v=DymSHObD-bg)

