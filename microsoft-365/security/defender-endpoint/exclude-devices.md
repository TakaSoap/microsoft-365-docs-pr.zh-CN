---
title: 排除Microsoft Defender for Endpoint中的设备
description: 从设备清单列表中排除设备
keywords: 排除
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: cbfc82f56cc1922a663c31defe30dc61c2d3dd9b
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664141"
---
# <a name="exclude-devices"></a>排除设备

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-respondmachine-abovefoldlink)。

## <a name="exclude-devices-from-threat-and-vulnerability-management"></a>从危险和漏洞管理中排除设备

排除非活动、重复或超出范围的设备可让你专注于发现和确定活动设备上的风险的优先级。 此操作还有助于反映更准确的危险和漏洞管理曝光分数，因为排除的设备在危险和漏洞管理报表中不可见。

排除设备后，你将无法查看有关这些设备上的漏洞和已安装软件的更新或相关信息。 它影响高级搜寻中的所有危险和漏洞管理页、报表和相关表。

即使设备排除功能从漏洞管理页和报表中删除设备数据，设备仍保持连接到网络，并且仍可能对组织造成风险。 你将能够随时取消设备排除。

## <a name="how-to-exclude-a-device"></a>如何排除设备

可以选择同时排除单个设备或多个设备。

### <a name="exclude-a-single-device"></a>排除单个设备

1. 转到 **"设备清单** "页，然后选择要排除的设备。
2. 从设备清单页上的操作栏或设备浮出控件中的操作菜单中选择" **排除** "。

   ![排除设备菜单选项的图像。](images/exclude-devices-menu.png)

3. 选择理由：

    - 非活动设备
    - 重复设备
    - 设备不存在
    - 超出范围
    - Other

4. 键入便笺，然后选择 **"排除"设备**。

![排除设备的图像。](images/exclude-device.png)

还可以从设备页面中排除设备。

> [!NOTE]
> 不建议排除活动设备，因为无法查看其漏洞信息尤其有风险。 如果设备处于活动状态，并且你尝试排除它，则会收到警告消息和确认弹出窗口，询问是否确定要排除活动设备。

将设备完全排除在视图和数据漏洞管理可能需要长达 10 小时的时间。

排除的设备在设备清单列表中仍然可见。 可以通过以下方式管理已排除设备的视图：

- 将 **排除状态** 列添加到设备清单视图。
- 使用 **排除状态** 筛选器查看相关设备列表。

![排除状态的图像。](images/exclusion-state.png)

### <a name="bulk-device-exclusion"></a>批量设备排除

还可以选择同时排除多个设备：

1. 转到 **"设备清单** "页，然后选择要排除的设备。

2. 在操作栏中，选择 **"排除**"。

3. 选择理由并选择 **"排除设备**"。

如果在具有不同排除状态的设备列表中选择多个设备，则排除所选设备浮出控件将提供已排除的所选设备数量的详细信息。 可以再次排除设备，但理由和说明将被重写。

![批量排除的图像](images/exclude-device-bulk.png)

排除设备后，如果转到已排除设备的设备页，则无法查看已发现的漏洞、软件清单或安全建议的数据。 数据也不会显示在漏洞管理页、相关的高级搜寻表和易受攻击的设备报表中。

## <a name="stop-excluding-a-device"></a>停止排除设备

你将能够随时停止排除设备。 设备不再被排除后，它们的漏洞数据将显示在漏洞管理页、报表和高级搜寻中。 更改可能需要长达 8 小时才能生效。

1. 转到设备清单，选择排除的设备以打开浮出控件，然后选择 **排除详细信息**
2. 选择 **"停止排除"**

![排除详细信息的图像](images/exclusion-details.png)

## <a name="see-also"></a>另请参阅

- [设备清单](machines-view-overview.md)
