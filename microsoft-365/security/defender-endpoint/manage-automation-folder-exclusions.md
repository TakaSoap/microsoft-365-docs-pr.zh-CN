---
title: 管理自动化文件夹排除
description: 添加自动化文件夹排除项，以控制从自动调查中排除的文件。
keywords: 管理， 自动化， 排除， 阻止， 清理， 恶意
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 37a251acd3b7631cffffaf2eb76bf0f2b4954ee6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185833"
---
# <a name="manage-automation-folder-exclusions"></a>管理自动化文件夹排除 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

自动文件夹排除项允许你指定自动调查将跳过的文件夹。 

可以控制要跳过的文件夹的以下属性：
- Folders 
- 文件的扩展名
- 文件名


**Folders**<br>
可以指定要跳过的文件夹及其子文件夹。 


>[!NOTE]
>目前尚不支持使用通配符作为排除目录下的文件的方法。 


**Extensions**<br>
可以指定要排除在特定目录中的扩展。 扩展是阻止攻击者使用排除文件夹隐藏攻击的一种方法。 扩展明确定义要忽略的文件。 

**文件名**<br>
可以指定要排除在特定目录中的文件名。 名称是阻止攻击者使用排除文件夹隐藏攻击的一种方法。 名称明确定义要忽略的文件。 



## <a name="add-an-automation-folder-exclusion"></a>添加自动化文件夹排除
1. 在导航窗格中，**选择"设置**  >  **文件夹排除项"。**  

2. 单击 **"新建文件夹排除"。**  

3. 输入文件夹详细信息：

    - 文件夹
    - 扩展
    - 文件名
    - 说明
    

4. 单击“保存”。

>[!NOTE]
> 用于收集或检查已排除文件的 Live Response 命令将失败，并出现错误："已排除文件"。 此外，自动调查将忽略排除的项目。

## <a name="edit-an-automation-folder-exclusion"></a>编辑自动化文件夹排除 
1. 在导航窗格中，**选择"设置**  >  **文件夹排除项"。** 

2. 单击 **文件夹** 排除上的"编辑"。  

3. 更新规则的详细信息，**然后单击保存。**

## <a name="remove-an-automation-folder-exclusion"></a>删除自动化文件夹排除 
1. 在导航窗格中，**选择"设置**  >  **文件夹排除项"。**  
2. 单击 **"删除排除"。** 


## <a name="related-topics"></a>相关主题
- [管理允许/阻止的自动化列表](manage-indicators.md)
- [管理自动化文件上载](manage-automation-file-uploads.md)
