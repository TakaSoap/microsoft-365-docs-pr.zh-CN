---
title: 管理应用中Microsoft 托管桌面
description: 了解如何更新部署到其他设备的业务线Microsoft 托管桌面的信息
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: ad30f6647df4146efe81daec4b2bcaa506b7c8b0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60169883"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>在 Microsoft 托管桌面中管理业务线应用

<!--Application management -->

有两种方法可以管理已载入应用并部署到Microsoft 托管桌面设备的应用Microsoft 托管桌面更新。 可以在应用门户或 Intune Microsoft 托管桌面应用更新。 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>更新 Microsoft 托管桌面 中的业务线Microsoft 托管桌面

**在企业门户中更新业务线Microsoft 托管桌面应用**
1. 登录到管理[Microsoft 托管桌面 。](https://aka.ms/mmdportal)
2. 在 **"清单"** 下，选择 **"应用"。**  
3. 选择要更新的应用，然后选择"编辑 **"。**
4. 在 **"管理"** 下，选择"**属性"。** 
5. 单击 **"应用包文件**"，然后浏览以上载新的应用包文件。
6. 选择 **应用包文件**。
7. 选择文件夹图标并浏览到更新后的应用文件的位置。 选择 **“打开”**。 使用程序包信息更新应用信息。
8. 验证 **应用版本是否** 反映了更新的应用包。 

更新后的应用将部署到用户设备。

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>在 Intune 中更新业务线应用

**在 Intune 中更新业务线应用**
1. 登录到 [Azure 门户](https://portal.azure.com)。
2. 选择 **"所有服务**  >  **Intune"。** Intune 位于监视 **+ 管理** 部分。
3. 选择 **"客户端应用>应用"。**
4. 在应用列表中查找并选择你的应用。
5. 在"**概述"边** 栏选项卡中，选择"**属性"。**
6. 选择 **应用包文件**。
7. 选择文件夹图标并浏览到更新后的应用文件的位置。 选择 **“打开”**。 使用程序包信息更新应用信息。
8. 验证 **应用版本是否** 反映了更新的应用包。

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>将应用回滚到以前版本

如果在部署应用的新版本时发现错误，你可以回滚到以前的版本。 此处概述的过程适用于类型列为 **Windows MSI** 业务线应用或 Windows 应用 (**Win 32**) - 预览

**将业务线应用回滚到以前版本**

1. 登录到管理[Microsoft 托管桌面 。](https://aka.ms/mmdportal)
2. 在 **"清单"** 下，选择 **"应用"。**  
3. 选择需要回滚的应用，然后选择"编辑 **"。**
4. 在 **"管理"** 下，选择"**属性"。** 
    - For **Windows MSI line-of-business app** apps， select App **information**， and then under Ignore **app version，** select **Yes**.
    - For **Windows app (Win 32) - preview** apps， select App **information，** select **Detection rules，** and then select **Add**. 
    如果存在 MSI 规则，请验证 **MSI 产品版本检查** 是否设置为 **"否"。**
5. [Upload应用源文件的以前版本Microsoft 托管桌面](../get-started/deploy-apps.md)管理门户。  

