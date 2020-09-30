---
title: SharePoint Syntex 中的图像标记
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: 了解 SharePoint Syntex 中的图像标记
ms.openlocfilehash: 38b9ad6823aa5f63a4ddec87bab7fec52a37f163
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295800"
---
# <a name="image-tagging-in-sharepoint-syntex"></a>SharePoint Syntex 中的图像标记

默认情况下，SharePoint 和 OneDrive 的基本图像标记处于启用状态。 将自动扫描已上载到任一位置的图像，并从 37 个基本标记的列表中应用标记（如果可用）。 用户可通过搜索图像标记查找图像。

用户上传图像时，将自动运行标记过程。 如果已编辑图像，则标记进程将再次运行以更新标记。

拥有映像文件权限的用户可以在文件信息面板或搜索结果页面中查看和编辑标记。 用户编辑图像标记后，系统将不再对该图像执行自动标记，即使已对其进行编辑。

如果关闭了标记，将不再自动标记图像。 不会删除现有标记。

## <a name="configure-image-tagging"></a>配置映像标记

可在 Microsoft 365 管理中心配置图像标记。  

打开或关闭图像标记

1. 在 Microsoft 365 管理员中心中，单击 **“设置”**。

2. 在**组织知识**下，单击 **“自动化内容理解”**。

3. 单击“**管理**”。

4. 在 **"图像标记"** 选项卡上，单击 **"编辑"**。

5. 选择允许 **“基本标记”** 或 **“关闭”** 标记。

6. 单击“**保存**”。

    ![图像标记控件的屏幕截图](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)

## <a name="see-also"></a>另请参阅

[设置内容理解](set-up-content-understanding.md)