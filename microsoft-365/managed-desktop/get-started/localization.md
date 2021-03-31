---
title: 本地化用户体验
description: 如何为用户本地化设备
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 20456ce837be60b707569ae07d4fb00b695b3a98
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445933"
---
# <a name="localize-the-user-experience"></a>本地化用户体验

Microsoft 托管桌面设备的用户可以在设置过程中选择他们选择的语言， ("开箱即用体验"，) 之后。

## <a name="during-setup-the-out-of-box-experience"></a>在设置 ("开箱使用体验") 

在完成设置的过程中，用户可以选择他们选择的语言。 此选择会影响以下属性：

- Windows 10 语言功能：
    - 显示语言
    - 键盘语言
    - 按需与语言相关的功能

- Microsoft 365 企业应用版语言功能：
    - 显示语言
    - 校对和创作工具

> [!NOTE]
> 用户只有在设置过程中选择语言，才能按需获取与语言相关的功能。

## <a name="after-completing-setup"></a>完成设置后

设置过程完成后，用户可以随时为 Windows 10 和 Microsoft 365 企业应用版选择其选择的语言。 具体来说：

- Windows 10 语言功能：
    - 显示语言
    - 键盘语言

- Microsoft 365 企业应用版语言功能：
    - 显示语言
    - 校对和创作工具

若要使 [](#supported-languages)Microsoft 365 企业应用版支持的语言可供用户安装，将用户添加到"新式 **Workplace-Office-Language_Packs** 组"。 这些语言将在 Intune 公司门户中提供。


## <a name="supported-languages"></a>支持的语言

对于新设备，制造商必须提供包含你要求的语言的设备映像。 如果你的制造商映像包含支持的语言列表中提供的语言，服务仍支持该映像。

如果要重新使用现有设备，可能需要与 Microsoft 客户代表合作，以获取相应的映像。 有关详细信息，请参阅设备 [图像](../service-description/device-images.md)。

Microsoft [托管桌面](../service-description/device-images.md#universal-image) 提供的通用映像包括以下语言和适用于 Windows 10：

- 英语 (美国、英国、澳大利亚、CA、) 
- 西班牙语 (西班牙、墨西哥) 
- 日语
- 法语 (法国、加拿大) 
- 德语
- 葡萄牙语（巴西）
- 意大利语
- Chinese Simplified
- 荷兰语  
- 瑞典语
- 丹麦语  
- 芬兰语 
- 俄语 
- 挪威语（博克马尔）
- 韩语
- Chinese Traditional
- 波兰语
- 土耳其语
- 阿拉伯语
- 希伯来语
- 葡萄牙语（葡萄牙）
- 捷克语
- 匈牙利语
- 泰语
- 印度尼西亚语
- 希腊语
- 斯洛伐克语
- 越南语
- 斯洛文尼亚语
- 克罗地亚语
- 罗马尼亚语
- 立陶宛语
- 保加利亚语
- 塞尔维亚 (拉丁语字母) 
- 拉脱维亚语
- 乌克兰语
- 爱沙尼亚语

Microsoft 365 企业应用版可能支持略有不同的列表。

如果用户需要此处列出的语言外的其他语言，请通过使用管理门户 提出[](../working-with-managed-desktop/admin-support.md)[支持请求](access-admin-portal.md)。

## <a name="languages-for-support-and-operations"></a>支持和操作的语言

### <a name="user-support"></a>用户支持
Microsoft 托管桌面仅提供英文版支持。 如果用户在"获取帮助"应用中选择其他语言，他们将从常规 Microsoft 支持渠道获得支持，而不是直接从 Microsoft 托管桌面获得支持。 有关详细信息，请参阅 [获取用户帮助](../working-with-managed-desktop/end-user-support.md)。

如果你的用户需要其他语言的支持，你将需要通过非 Microsoft 支持源或你自己的组织提供。

### <a name="admin-support-and-operations"></a>管理员支持和操作
Microsoft 托管桌面仅提供英语版管理员支持。 这包括管理门户和与 Microsoft 托管桌面操作的所有通信。 你应该假设所有与管理员相关的交互和界面都将采用英语，除非另行指定。


