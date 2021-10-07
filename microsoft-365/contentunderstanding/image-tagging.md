---
title: SharePoint Syntex 中的图像标记
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: admindeeplinkMAC
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
description: 了解 SharePoint Syntex 中的图像标记
ms.openlocfilehash: 79df10f80dd02930dc49f56274b00664c6f1d3d2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60205925"
---
# <a name="image-tagging-in-sharepoint-syntex"></a>SharePoint Syntex 中的图像标记

（即将推出）

借助 SharePoint Syntex 中的图像标记，用户可以通过搜索图像标记来查找图像，并基于图像标记创建工作流。 默认情况下，SharePoint 和 OneDrive 的基本图像标记处于启用状态。 将自动扫描已上载到任一位置的图像，并从 37 个基本标记的列表中应用标记（如果可用）。 用户可通过搜索图像标记查找图像。

用户上传图像时，将自动运行标记过程。 如果已编辑图像，则标记进程将再次运行以更新标记。

拥有映像文件权限的用户可以在文件信息面板或搜索结果页面中查看和编辑标记。 用户编辑图像标记后，即使已对其进行编辑，系统将不再自动标记该图像。

如果关闭了标记，将不再自动标记图像。 不会删除现有标记。

> [!NOTE]
> 系统生成的标记可能会随图像或标记技术的更新而变化。


## <a name="configure-image-tagging"></a>配置映像标记

[设置 SharePoint Syntex](set-up-content-understanding.md) 后，可在 Microsoft 365 管理中心中配置图像标记。  

打开或关闭图像标记

1. 在"Microsoft 365 管理中心中，选择"设置 <a href="https://go.microsoft.com/fwlink/p/?linkid=2171997" target="_blank">**"。**</a>

2. 在 **组织知识** 下，单击 **“自动化内容理解”**。

3. 单击“**管理**”。

4. 在 **"图像标记"** 选项卡上，单击 **"编辑"**。

5. 选择允许 **“基本标记”** 或 **“关闭”** 标记。

6. 单击“**保存**”。

    ![图像标记控件的屏幕截图。](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)
