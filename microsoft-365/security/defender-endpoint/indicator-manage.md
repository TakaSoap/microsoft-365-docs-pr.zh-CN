---
title: 管理指示器
ms.reviewer: ''
description: 管理定义实体检测、防护和排除的文件哈希、IP 地址、URL 或域的指示器。
keywords: import， indicator， list， ioc， csv， manage， allowed， block， clean， malicious， file hash， ip address， urls， domain
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fbed4f51fcd0b2154c46a88dc3d408330238ec63
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/29/2021
ms.locfileid: "61217646"
---
# <a name="manage-indicators"></a>管理指示器

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)。

1. 在导航窗格中，选择"设置"下 (终结点 \>  \> ) 。 

2. 选择要管理的实体类型的选项卡。

3. 更新指示器的详细信息，并单击"保存"或单击"删除"按钮（如果要从列表中删除该实体）。

## <a name="import-a-list-of-iocs"></a>导入 IoCs 列表

还可以选择上传定义指示器属性、要采取的操作和其他详细信息的 CSV 文件。

下载示例 CSV，了解受支持的列属性。

1. 在导航窗格中，选择"设置"下 (终结点 \>  \> ) 。 

2. 选择要导入其指示器的实体类型的选项卡。

3. 选择 **导入** \> **选择文件**。

4. 选择“**导入**”。 为要导入的所有文件执行这一操作。

5. 选择“**完成**”。

> [!NOTE]
> 每个批次只能上载 500 个指示器。

下表显示了受支持的参数。

参数|类型|说明
:---|:---|:---
indicatorType|枚举|指示器的类型。 可能的值是："FileSha1"、"FileSha256"、"IpAddress"、"DomainName"和"Url"。 **Required**
indicatorValue|String|Indicator [实体的](ti-indicator.md) 标识。 **Required**
action|枚举|如果在组织中发现指示器，将采取的操作。 可能的值包括："Alert"、"AlertAndBlock"和"Allowed"。 **Required**
title|String|指示器警报标题。 **Required**
说明|String| 指示器的说明。 **Required**
expirationTime|DateTimeOffset|指示器的过期时间，格式为 YYYY-MM-DDTHH：MM：SS.0Z。 **可选**
severity|枚举|指示器的严重性。 可能的值包括："Informational"、"Low"、"Medium"和"High"。 **可选**
recommendedActions|String|TI 指示器警报建议操作。 **可选**
rbacGroupNames|String|将应用指示器的 RBAC 组名称的逗号分隔列表。 **可选**
“类别”|String|警报的类别。 示例包括：执行和凭据访问。 **可选**
mitretechniques|String|MITRE 技术代码/id (逗号分隔) 。 有关详细信息，请参阅策略[Enterprise策略](https://attack.mitre.org/tactics/enterprise/)。 **可选** 建议在 MITRE 技术时在类别中添加值。
GenerateAlert|String|是否应该生成警报。 可能的值是：True 或 False。 **可选**



> [!NOTE]
> 不支持无Inter-Domain IP (CIDR) 表示法。
有关详细信息，请参阅 [Microsoft Defender for Endpoint 警报类别现在与 MITRE ATT&CK！](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748)一致。

## <a name="see-also"></a>另请参阅

- [创建指示器](manage-indicators.md)
- [创建文件指示器](indicator-file.md)
- [创建 IP 和 URL/域指示器](indicator-ip-domain.md)
- [创建基于证书的指示器](indicator-certificates.md)
