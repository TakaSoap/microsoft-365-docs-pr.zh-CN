---
title: Windows 中的信息保护概述
ms.reviewer: ''
description: 了解信息保护如何工作Windows标识和保护敏感信息
keywords: 信息， 保护， dlp， 数据， 丢失， 防护， 保护
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4a96296f09a82fe2b2c8d5c4d5d250c48f89ffc4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60156290"
---
# <a name="information-protection-in-windows-overview"></a>Windows 中的信息保护概述

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Prerelease information](../../includes/prerelease.md)]

信息保护是 Microsoft 365 企业版的一部分，可提供智能保护，以确保敏感数据的安全，同时在工作场所中提高工作效率。

> [!TIP]
> 阅读我们的博客文章，了解如何将 Microsoft Defender for Endpoint 与 Microsoft 信息保护集成，以发现、保护和监视Windows[敏感数据](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/)。

Defender for Endpoint 应用以下方法来发现、分类和保护数据：

- **数据发现**- 识别Windows的敏感数据
- **数据分类**- 根据安全与合规中心Microsoft 信息保护 (管理) 的常见 MIP Office 365策略&数据。 自动分类允许你保护敏感数据，即使最终用户尚未手动分类它。

## <a name="data-discovery-and-data-classification"></a>数据发现和数据分类

Defender for Endpoint 自动发现具有敏感度标签的文件和包含敏感信息类型的文件。

敏感度标签分类并帮助保护敏感内容。

DLP 策略实施Office 365数据丢失防护 (敏感信息) 分为两类：

- 默认值
- 自定义警报

默认敏感信息类型包括诸如银行帐号、社会保险号或国家/市/市/区号等信息。 有关详细信息，请参阅 [敏感信息类型查找什么](/office365/securitycompliance/what-the-sensitive-information-types-look-for)。

自定义类型是您定义的类型，旨在保护不同类型的敏感信息，例如 (，例如员工 ID 或项目) 。 有关详细信息，请参阅创建自定义 [敏感信息类型](/office365/securitycompliance/create-a-custom-sensitive-information-type)。

在设备上创建或编辑文件时，Windows Defender for Endpoint 会扫描内容，以评估其中是否包含敏感信息。

启用 Azure 信息保护集成，以便当 Defender for Endpoint 通过标签或信息类型发现包含敏感信息的文件时，该文件会自动从设备转发到 Azure 信息保护。

![使用 Azure 信息保护的设置页面的图像。](images/atp-settings-aip.png)

报告的信号可以在 Azure 信息保护 - 数据发现仪表板上查看。

## <a name="azure-information-protection---data-discovery-dashboard"></a>Azure 信息保护 - 数据发现仪表板

此仪表板显示 Defender for Endpoint 和 Azure 信息保护发现的数据的汇总发现信息。 来自 Defender for Endpoint 的数据标记为"位置类型 - 终结点"。

![Azure 信息保护 - 数据发现的图像。](images/azure-data-discovery.png)

请注意右侧"设备风险"列，此设备风险直接派生自 Defender for Endpoint，指示发现文件的安全设备的风险级别，基于 Defender for Endpoint 检测到的活动安全威胁。

单击设备以查看在此设备上观测到的文件列表，及其敏感度标签和信息类型。

> [!NOTE]
> 请允许 Azure 信息保护仪表板发现大约 15-20 分钟反映发现的文件。

## <a name="log-analytics"></a>Log Analytics

Azure Log [Analytics](/azure/log-analytics/log-analytics-overview)中也提供基于 Defender for Endpoint 的数据发现，你可以在这里对原始数据执行复杂的查询。

有关 Azure 信息保护分析详细信息，请参阅 [Azure 信息保护的中央报告](/azure/information-protection/reports-aip)。

在 Azure 门户中打开 Azure Log Analytics，然后打开标准 (或经典查询生成器) 。

若要查看 Defender for Endpoint 数据，请执行包含以下项的查询：

```text
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

### <a name="prerequisites"></a>先决条件

- 客户必须订阅 Azure 信息保护。
- 在服务中启用 Azure 信息保护Microsoft Defender 安全中心：
  - 转到 **"设置"** 中的Microsoft Defender 安全中心，单击"常规 **"设置"高级****"菜单**。
