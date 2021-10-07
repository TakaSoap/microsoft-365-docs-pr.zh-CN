---
title: 分配设备值 - 危险和漏洞管理
description: 了解如何为设备分配低、普通或高值，以帮助区分资产优先级。
keywords: Microsoft Defender for Endpoint 设备值、危险和漏洞管理设备值、高价值设备、设备值曝光分数
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a1cc240c1c013468b482533ab00ef498543431fd
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193921"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a>分配设备值 - 危险和漏洞管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)。

[!include[Prerelease information](../../includes/prerelease.md)]

定义设备值有助于区分资产优先级。 设备值用于将单个资产的风险损失纳入危险和漏洞管理评分计算中。 分配为"高值"的设备将获得更多权重。

您还可以使用设置 [的设备值 API](set-device-value.md)。

设备值选项：

- 低
- 标准（默认）
- 高

应分配高值的设备示例：

- 域控制器、Active Directory
- 面向 Internet 的设备
- VIP 设备
- 托管内部/外部生产服务的设备

## <a name="choose-device-value"></a>选择设备值

1. 导航到任何设备页面，最简单的位置是设备清单。

2. 从 **页面顶部的** 操作栏旁边的三个点中选择设备值。

    ![设备值下拉列表的示例。](images/tvm-device-value-dropdown.png)

3. 将显示一个显示当前设备值及其的含义的飞出图。 查看设备的值，然后选择最适合你的设备的值。
![设备值飞出的示例。](images/tvm-device-value-flyout.png)

## <a name="how-device-value-impacts-your-exposure-score"></a>设备值如何影响你的曝光分数

曝光分数是所有设备的加权平均值。 如果你有设备组，还可以按设备组筛选分数。

- 普通设备的权重为 1
- 低值设备的权重为 0.75
- 高价值设备的权重为 NumberOfAssets / 10。
    - 如果你有 100 台设备，则每个高价值设备的权重将为 10 (100/10) 

## <a name="related-topics"></a>相关主题

- [威胁漏洞管理概述](next-gen-threat-and-vuln-mgt.md)
- [曝光分数](tvm-exposure-score.md)
- [API](next-gen-threat-and-vuln-mgt.md#apis)