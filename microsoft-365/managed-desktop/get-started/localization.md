---
title: 本地化用户体验
description: 如何为用户本地化设备
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 4ff4d72f22faef32b1fabb52e10332af62e50bc7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170055"
---
# <a name="localize-the-user-experience"></a>本地化用户体验

Microsoft 托管桌面设备的用户可以在设置过程中选择他们选择的语言， ("开箱即用体验"，) 之后。

## <a name="during-setup-the-out-of-box-experience"></a>在设置 ("开箱使用体验") 

在完成设置的过程中，用户可以选择他们选择的语言。 此选择会影响以下属性：

- Windows 10语言功能：
    - 显示语言
    - 键盘语言
    - 按需与语言相关的功能

- Microsoft 365 应用版语言Enterprise：
    - 显示语言
    - 校对和创作工具

> [!NOTE]
> 用户只有在设置过程中选择语言，才能按需获取与语言相关的功能。

## <a name="after-completing-setup"></a>完成设置后

用户可以选择自己选择的语言进行Windows 10 Microsoft 365 应用版，Enterprise安装过程完成后随时进行配置。 具体来说：

- Windows 10语言功能：
    - 显示语言
    - 键盘语言

- Microsoft 365 应用版语言Enterprise：
    - 显示语言
    - 校对和创作工具

若要使 [Microsoft 365 应用版](#supported-languages)for Enterprise 支持的语言可供用户安装，可以将用户添加到新式 **Workplace-Office-Language_Packs** 组。 这些语言将在 Intune 公司门户。


## <a name="supported-languages"></a>支持的语言

对于新设备，制造商必须提供包含你要求的语言的设备映像。 如果你的制造商映像包含支持的语言列表中提供的语言，服务仍支持该映像。

如果要重新使用现有设备，可能需要与 Microsoft 客户代表合作以获取相应的映像。 有关详细信息，请参阅设备 [图像](../service-description/device-images.md)。

该[映像提供](../service-description/device-images.md#universal-image)的通用Microsoft 托管桌面包括以下语言和Windows 10：

- 阿拉伯语
- 保加利亚语
- 简体中文
- 繁体中文
- 克罗地亚语
- 捷克语
- 丹麦语  
- 荷兰语  
- 英语 (美国、英国、澳大利亚、CA、) 
- 爱沙尼亚语
- 芬兰语 
- 法语 (法国、加拿大) 
- 德语
- 希腊语
- 希伯来语
- 匈牙利语
- 印度尼西亚语
- 意大利语
- 日语
- 朝鲜语
- 拉脱维亚语
- 立陶宛语
- 挪威语（博克马尔）
- 波兰语
- 葡萄牙语（巴西）
- 葡萄牙语（葡萄牙）
- 罗马尼亚语
- 俄语 
- 塞尔维亚 (拉丁语字母) 
- 斯洛伐克语
- 斯洛文尼亚语
- 西班牙语 (西班牙、墨西哥) 
- 瑞典语
- 泰语
- 土耳其语
- 乌克兰语
- 越南语

Microsoft 365 应用版Enterprise列表可能略有不同。

如果用户需要此处列出的语言外的其他语言，请通过使用管理门户 提出[](../working-with-managed-desktop/admin-support.md)[支持请求](access-admin-portal.md)。

## <a name="languages-for-support-and-operations"></a>支持和操作的语言

### <a name="user-support"></a>用户支持
Microsoft 托管桌面仅提供英文版支持。 如果用户在 microsoft 应用中选择获取帮助语言，他们将从常规 Microsoft 支持渠道获得支持，而不是直接从 Microsoft Microsoft 托管桌面。 有关详细信息，请参阅 [获取用户帮助](../working-with-managed-desktop/end-user-support.md)。

如果用户需要其他语言支持，您必须通过非 Microsoft 支持源或您自己的组织提供支持。

### <a name="admin-support-and-operations"></a>管理员支持和操作
Microsoft 托管桌面仅提供英语版管理员支持。 这包括管理门户和与管理员操作Microsoft 托管桌面通信。 你应该假设所有与管理员相关的交互和界面都将采用英语，除非另行指定。


