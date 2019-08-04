---
title: 在 Microsoft 托管桌面中管理应用
description: 有关如何更新部署到 Microsoft 托管桌面设备的业务线应用程序的信息
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 87968e1238ee5b3dce6e569846e253dada72dd6d
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390729"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>在 Microsoft 托管桌面中管理业务线应用程序

<!--Application management -->

有几种方法可以管理已载入到 Microsoft 托管桌面的应用程序的应用程序更新, 并将其部署到 Microsoft 托管桌面设备。 你可以在 Microsoft 托管桌面门户或 Intune 中进行应用更新。 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>在 Microsoft 托管桌面中更新业务线应用程序

**在 Microsoft 托管桌面门户中更新业务线应用程序**
1. 登录到[Microsoft 托管桌面管理门户](http://aka.ms/mmdportal)。
2. 在 "**清单**" 下, 选择 "**应用**"。  
3. 选择要更新的应用程序, 然后选择 "**编辑**"。
4. 在 "**管理**" 下, 选择 "**属性**"。 
5. 单击 "**应用程序包文件**", 然后浏览以上载新的应用程序包文件。
6. 选择 "**应用程序包文件**"。
7. 选择文件夹图标并浏览到更新后的应用程序文件所在的位置。 选择“打开”****。 应用程序信息使用包信息进行更新。
8. 验证**应用程序版本**是否反映了更新后的应用程序包。 

更新后的应用程序将部署到您的用户的设备上。

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>更新 Intune 中的业务线应用程序

**在 Intune 中更新业务线应用程序**
1. 登录到[Azure 门户](https://azure.portal.com)。
2. 选择 "**所有服务** > "**Intune**。 Intune 位于 "**监控 + 管理**" 部分。
3. 选择 "**客户端应用 > 应用**"。
4. 在应用列表中查找并选择您的应用程序。
5. 在**概述**边栏中, 选择 "**属性**"。
6. 选择 "**应用程序包文件**"。
7. 选择文件夹图标并浏览到更新后的应用程序文件所在的位置。 选择“打开”****。 应用程序信息使用包信息进行更新。
8. 验证**应用程序版本**是否反映了更新后的应用程序包。

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>将应用程序回退到以前的版本

如果在部署新版本的应用程序时发现错误, 则可以回滚到以前的版本。 此处所述的过程适用于类型列为**WINDOWS MSI 应用程序**或 windows 应用程序的应用程序 **(Win 32)-preview**

**将业务线应用程序回滚到以前的版本**

1. 登录到[Microsoft 托管桌面管理门户](http://aka.ms/mmdportal)。
2. 在 "**清单**" 下, 选择 "**应用**"。  
3. 选择需要回滚的应用程序, 然后选择 "**编辑**"。
4. 在 "**管理**" 下, 选择 "**属性**"。 
    - 对于**WINDOWS MSI 应用**程序应用程序, 请选择 "**应用程序信息**", 然后在 "**忽略应用程序版本**" 下, 选择 **"是"**。
    - 对于**Windows 应用 (Win 32)-预览**应用程序, 选择 "**应用程序信息**", 选择 "**检测规则**", 然后选择 "**添加**"。 
    如果存在 MSI 规则, 请验证**msi 产品版本检查**是否设置为 "**否**"。
5. 将[以前版本的应用程序源文件上传](../get-started/deploy-apps.md)到 Microsoft 托管桌面管理门户。  

