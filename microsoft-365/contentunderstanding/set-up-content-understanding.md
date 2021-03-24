---
title: 设置 SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: 在Project Cortex中设置对内容的理解
ms.openlocfilehash: cc6fbfbfc130cc6e64b5d7c30e0a9db5f39036ac
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051563"
---
# <a name="set-up-sharepoint-syntex"></a>设置 SharePoint Syntex

管理员可使用 Microsoft 365 管理中心设置 [Microsoft SharePoint Syntex](index.md)。 

开始之前应考虑下列建议：

- 要在哪些 SharePoint 网站中启用表单处理？ 全部、部分、还是选定的站点？
- 你会如何为默认内容中心命名？

可在 Microsoft 365 管理中心内的初始设置后更改你的设置。

设置前，请确保计划在环境中设置和配置内容理解的最佳方式。 例如，你需要做出以下决策：

- 要启用表单处理的 SharePoint 网站 - 所有网站、部分网站或所选网站
- 内容中心的名称和管理员

## <a name="requirements"></a>要求 

> [!NOTE]
> 必须拥有全局管理员或 SharePoint 管理员权限，才能访问 Microsoft 365 管理中心并设置 SharePoint Syntex。

作为管理员，你还可在设置后随时对所选择的设置进行更改，并在整个 Microsoft 365 管理中心中的内容理解管理中设置。

### <a name="licensing"></a>许可

若要使用 SharePoint 整合，您的组织必须具有 SharePoint Syntex 订阅，并且每个用户必须分配以下许可证：

- SharePoint Syntex
- SharePoint 整合 - SPO 类型
- 用于 SharePoint 整合的常用数据服务

如果将来（或试用版过期）取消 SharePoint Syntex 订阅，用户将无法创建或运行文档了解或表单处理模型，且内容中心模板将不再可用。 此外，术语库报表、SKOS 分类导入和内容类型推送将不再可用。 不会删除任何内容，且网站权限不会更改。

### <a name="ai-builder-credits"></a>AI 生成器点数

如果你的组织中的 SharePoint Syntex有300或更多SharePoint Syntex 许可证，则会分配一百万个 AI 生成器点数。 如果许可证少于300个，则必须购买AI 生成器点数才能使用表单处理。

可使用 [AI 生成器计算器](https://powerapps.microsoft.com/ai-builder-calculator)来估算出适合你的AI 生成器容量。

转到[电源平台管理中心](https://admin.powerplatform.microsoft.com/resources/capacity)查询积分和使用情况。

## <a name="to-set-up-sharepoint-syntex"></a>对设置 SharePoint Syntex

1. 在 Microsoft 365 管理中心中，选择“**设置**”，然后查看“**文件和内容**”部分。

2. 在“**文件和内容**”部分中，选择“**自动内容理解**”。<br/>

3. 在 **自动理解内容** 页面上，单击 **开始**， 以逐步完成设置流程。<br/>

    > [!div class="mx-imgBorder"]
    > ![开始设置](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. 在 **配置表单处理** 页面上，可选择是否希望用户能够在特定的 SharePoint 文档库中创建表单处理模型。 在文档库功能区中存在一个菜单选项，以便在已启用该功能的SharePoint文档库中 **创建表单处理模型**。
 
     对于 **应显示用于创建表单处理模型的SharePoint库选项**，可选择：</br>
      - “**所有 SharePoint 网站中的库**”，从而使组织内的所有 SharePoint 库都可显示该选项。</br>
      - “**所选 SharePoint 网站中的库**”，然后选择可显示该选项的网站或上传一个包含最多 50 个网站的列表。</br>
      - 如果不希望对任何网站提供 **SharePoint 库**，则不需要SharePoint库（可在设置后更改）。

   > [!div class="mx-imgBorder"]
   > ![配置表单处理](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > 在收录一个站点后，删除该站点不会影响应用于该站点中的库的现有模型，也不会影响将文档理解模型应用于库的能力。 
    
5. 在 **创建内容中心** 页面上，可创建一个 SharePoint 内容中心站点，用户可在该网站上创建和管理文档理解模型。

    1. 对于 **站点名称**，键入要为内容中心站点提供的名称。
    
    1. **站点地址** 将显示站点的 URL，具体取决于所选择的站点名称。 若想改变它，请点击 **编辑**。

       > [!div class="mx-imgBorder"]
       > ![创建内容中心](../media/content-understanding/admin-cu-create-cc.png)</br>

       选择 **下一步**。

6. 在 **审查并完成** 页面上，可查看所选设置并选择进行更改。 如果对你的选择感到满意，请选择 **激活**。

7. 在确认页面上，点击 **完成**。

8. 你将返回到 **自动理解内容** 页面。 在此页面中，可选择 **管理**，对配置设置进行任何更改。 

## <a name="assign-licenses"></a>分配许可证

配置 SharePoint Syntex 后，必须为将使用任何 SharePoint Syntex 功能的用户分配许可证。

以分配许可证：

1. 在Microsoft 365 管理中心中，在 **用户** 下，点击 **活动用户**。

2. 选择要给予许可的用户，然后选择“**管理产品许可证**”。

3. 从下拉菜单中选择“**应用**”。

4. 选择“**显示 SharePoint Syntex 相关应用**”。 在“**应用**”下，确保“**面向 SharePoint Syntex 的 Common Data Service**”、“**SharePoint Syntex**”和“**SharePoint Syntex - SPO 类型**”都已选中。

    > [!div class="mx-imgBorder"]
    > ![Microsoft 365 管理中心的 SharePoint Syntex 许可证](../media/content-understanding/sharepoint-syntex-licenses.png)

5. 单击 **保存更改**。

## <a name="see-also"></a>另请参阅

[表单处理模式概述](/ai-builder/form-processing-model-overview)

[逐步：如何构建文档理解模型（视频）](https://www.youtube.com/watch?v=DymSHObD-bg)
