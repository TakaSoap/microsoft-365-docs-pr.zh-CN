---
title: 本地化用户体验
description: 如何为用户本地化设备
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: c429a072d6ceb2d5d1472533649e30d1fc1a0078
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2022
ms.locfileid: "63524997"
---
# <a name="localize-the-user-experience"></a>本地化用户体验

Microsoft 托管桌面设备的用户可以在设置过程中选择他们选择的语言， ("开箱即用体验"，) 之后。

## <a name="during-setup-the-out-of-box-experience"></a>在设置 ("开箱使用体验") 

在设置过程中，用户可以选择他们选择的语言。 此选择会影响以下属性：

| 属性 | 说明 |
| ------ | ------ |
| Windows 10语言功能 | <ul><li>显示语言</li><li>键盘语言</li><li>按需与语言相关的功能</li><ul> |
| Microsoft 365 应用版语言Enterprise的语言功能 | <ul><li>显示语言</li><li>校对和创作工具</li></ul> |

> [!NOTE]
> 用户只有在设置过程中选择语言，才能按需获取与语言相关的功能。

## <a name="after-completing-setup"></a>完成设置后

用户可以选择自己选择的语言进行Windows 10，Microsoft 365 应用版安装Enterprise完成后随时为用户选择语言。 具体来说：

| 功能 | 说明 |
| ------ | ------ |
| Windows 10语言功能 | <ul><li>显示语言</li><li>键盘语言</li><ul> |
| Microsoft 365 应用版语言Enterprise的语言功能 | <ul><li>显示语言</li><li>校对和创作工具</li></ul> |

## <a name="install-more-languages"></a>安装更多语言

> [!NOTE]
> 从 2022 年 3 月 16 日开始，我们将逐步淘汰"新式 Workplace-Office-Language_Packs"组，允许用户向 Microsoft Office 中添加语言。 到新方法的转换 (请参阅) 将于 2022 年 4 月完成。 如果在此转换期间有任何问题，请联系支持 [人员](../working-with-managed-desktop/admin-support.md)。

默认情况下，Microsoft Office要求用户成为管理员。Microsoft 托管桌面部署 Office 策略，以允许标准用户直接从其 Office 应用安装语言附件包。 有关详细信息，请参阅 [允许不是管理员的用户安装其他语言](/deployoffice/overview-deploying-languages-microsoft-365-apps#allow-users-who-arent-admins-to-install-additional-languages)。

## <a name="supported-languages"></a>支持的语言

对于新设备，制造商必须提供包含你要求的语言的设备映像。 如果你的制造商映像包含支持的语言列表中未包含的语言，则服务仍支持该设备。

如果你要重新使用现有设备，你可能需要与 Microsoft 帐户代表合作以获取相应的映像。 有关详细信息，请参阅 [设备映像](../service-description/device-images.md)。

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

> [!NOTE]
> Microsoft 365 应用版Enterprise列表可能略有不同。

如果用户需要此处列出的语言外的其他语言， [请通过使用管理](../working-with-managed-desktop/admin-support.md) 门户提出 [支持请求](access-admin-portal.md)。

## <a name="languages-for-support-and-operations"></a>支持和操作的语言

### <a name="admin-support-and-operations"></a>管理员支持和操作

Microsoft 托管桌面仅提供英语版管理员支持。 此支持包括管理门户和与 Microsoft 托管桌面 操作的所有通信。 你应该假设所有与管理员相关的交互和界面都将采用英语，除非另行指定。
