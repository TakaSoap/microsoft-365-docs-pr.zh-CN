---
title: 设置 SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
search.appverid: MET150
localization_priority: Priority
description: 在Project Cortex中设置对内容的理解
ms.openlocfilehash: dfbcc8e41a28e3107b58ac6b8d471e3a2a08d036
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087567"
---
# <a name="set-up-sharepoint-syntex"></a>设置 SharePoint Syntex

管理员可使用 Microsoft 365 管理中心设置 [Microsoft SharePoint Syntex](index.md)。 

开始之前应考虑下列建议：

- Which SharePoint sites will you enable form processing? All of them, some, or select sites?
- 你的默认内容中心会采用什么名字？

可在 Microsoft 365 管理中心内的初始设置后更改你的设置。

Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment. For example, you need to make considerations about the following names of:

- 要启用表单处理的 SharePoint 站点 - 所有这些站点、部分或选定的站点
- 你的内容中心和主站管理员的名字

## <a name="requirements"></a>要求 

> [!NOTE]
> 必须拥有全局管理员或 SharePoint 管理员权限，才能访问 Microsoft 365 管理中心并设置内容理解。

作为管理员，你还可在设置后随时对所选择的设置进行更改，并在整个 Microsoft 365 管理中心中的内容理解管理中设置。

## <a name="to-set-up-sharepoint-syntex"></a>对设置 SharePoint Syntex

1. 在 Microsoft 365 管理中心中，选择“**设置**”，然后查看“**文件和内容**”部分。

2. 在“**文件和内容**”部分中，选择“**自动内容理解**”。<br/>

3. 在 **自动理解内容** 页面上，单击 **开始**， 以逐步完成设置流程。<br/>

    > [!div class="mx-imgBorder"]
    > ![开始设置](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries. A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.
 
     对于 **应显示用于创建表单处理模型的SharePoint库选项**，可选择：</br>
      - **所有SharePoint库** ，均使其可供组织中的所有 SharePoint 库使用。</br>
      - **仅在选定站点中的库**，然后选择需要提供它的站点，或上传最多50个站点的列表。</br>
      - 如果不希望对任何网站提供 **SharePoint 库**，则不需要SharePoint库（可在设置后更改）。

   > [!div class="mx-imgBorder"]
   > ![配置表单处理](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > 在收录一个站点后，删除该站点不会影响应用于该站点中的库的现有模型，也不会影响将文档理解模型应用于库的能力。 
    
5. 在 **创建内容中心** 页面上，可创建一个 SharePoint 内容中心站点，用户可在该网站上创建和管理文档理解模型。

    1. 对于 **站点名称**，键入要为内容中心站点提供的名称。
    
    1. The **Site address** will show the URL for your site, based on what you selected for the site name. If you want to change it, click **Edit**.

       > [!div class="mx-imgBorder"]
       > ![创建内容中心](../media/content-understanding/admin-cu-create-cc.png)</br>

       选择 **下一步**。

6. On the **Review and finish** page, you can look at your selected setting and choose to make changes. If you are satisfied with your selections, select **Activate**.

7. 在确认页面上，点击 **完成**。

8. You'll be returned to your **Automate content understanding** page. From this page, you can select **Manage** to make any changes to your configuration settings. 

## <a name="assign-licenses"></a>分配许可证

配置 SharePoint Syntex 后，必须为将使用任何 SharePoint Syntex 功能的用户分配许可证。

以分配许可证：

1. 在Microsoft 365 管理中心中，在 **用户** 下，点击 **活动用户**。

2. 选择要给予许可的用户，然后单击 **管理产品许可证**。

3. 选择“**分配更多**”。

4. Select **SharePoint Syntex**. Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.

    > [!div class="mx-imgBorder"]
    > ![Microsoft 365 管理中心的 SharePoint Syntex 许可证](../media/content-understanding/sharepoint-syntex-licenses.png)

5. 单击 **保存更改**。

## <a name="ai-builder-credits"></a>AI 生成器点数

If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits. If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.

可使用 [AI 生成器计算器](https://powerapps.microsoft.com/ai-builder-calculator)来估算出适合你的AI 生成器容量。

转到[电源平台管理中心](https://admin.powerplatform.microsoft.com/resources/capacity)查询积分和使用情况。

## <a name="see-also"></a>另请参阅

[表单处理模式概述](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[逐步：如何构建文档理解模型（视频）](https://www.youtube.com/watch?v=DymSHObD-bg)

