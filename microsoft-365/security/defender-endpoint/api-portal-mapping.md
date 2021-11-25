---
title: Microsoft Defender for Endpoint 警报字段
description: 了解警报字段如何映射到 Microsoft Defender for Endpoint 中的值
keywords: 检测， 检测字段， 字段， api， 字段， 拉取检测， rest api， 请求， 响应
search.appverid: met150
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
ms.custom: api
ms.openlocfilehash: 2bb199a8ca0f8734da6562304b15cbf2cb4170cf
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167414"
---
# <a name="microsoft-defender-for-endpoint-alert-fields"></a>Microsoft Defender for Endpoint 警报字段

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-apiportalmapping-abovefoldlink)。

了解哪些数据字段作为检测 API 的一部分公开，以及如何映射到Microsoft 365 Defender。

> [!NOTE]
>
> - [适用于终结点警报的](alerts.md) Defender 由一个或多个检测组成。
> - **Microsoft Defender ATP 检测** 由设备上发生的可疑事件及其相关的警报 **详细信息组成** 。
> - Microsoft Defender for Endpoint 警报 API 是警报使用的最新 API，包含每个警报的相关证据的详细列表。 有关详细信息，请参阅[警报方法和属性和](alerts.md)[列表警报](get-alerts.md)。

## <a name="detections-api-fields-and-portal-mapping"></a>检测 API 字段和门户映射

下表列出了检测 API 有效负载中公开的可用字段。 它显示了填充值的示例，并引用了如何在门户上反映数据。

ArcSight 字段列包含 Defender for Endpoint 字段和 ArcSight 中的内置字段之间的默认映射。 当你启用 SIEM 集成功能时，你可以从门户下载映射文件，并且你可以对其进行修改以满足你的组织的需求。 有关详细信息，请参阅在 Defender [for Endpoint 中启用 SIEM 集成](enable-siem-integration.md)。

字段编号与下图中的数字匹配。

> [!div class="mx-tableFixed"]
>
> |门户标签|SIEM 字段名称|ArcSight 字段|示例值|说明|
> |---|---|---|---|---|
> |1|AlertTitle|name|Microsoft Defender AV 检测到"Mikatz"高严重性恶意软件|可用于每个检测的值。|
> |2|Severity|deviceSeverity|高|可用于每个检测的值。|
> |3|类别|deviceEventCategory|恶意软件|可用于每个检测的值。|
> |4|检测源|sourceServiceName|防病毒|Microsoft Defender 防病毒或 Defender for Endpoint。 可用于每个检测的值。|
> |5|MachineName|sourceHostName|desktop-4a5ngd6|可用于每个检测的值。|
> |6 |FileName|fileName|Robocopy.exe|可用于与文件或进程关联的检测。|
> |7 |FilePath|filePath|C:\Windows\System32\Robocopy.exe|可用于与文件或进程关联的检测。|
> |8 |UserDomain|sourceNtDomain|CONTOSO|运行活动的用户上下文的域，可用于基于终结点行为的 Defender 检测。|
> |9 |UserName|sourceUserName|liz.bean|运行活动的用户上下文，可用于基于终结点行为的检测的 Defender。|
> |10 |Sha1|fileHash|3da065e07b990034e9db7842167f70b63aa5329|可用于与文件或进程关联的检测。|
> |11|Sha256|deviceCustomString6|ebf54f745dc81e1958f75e4ca91dd0ab989fc9787bb6b0bf993e2f5|可用于 Microsoft Defender AV 检测。|
> |12 |Md5|deviceCustomString5|db979c04a99b96d370988325bb5a8b21|可用于 Microsoft Defender AV 检测。|
> |13|ThreatName|deviceCustomString1|HackTool：Win32/M一tz！dha|可用于 Microsoft Defender AV 检测。|
> |14 |IpAddress|sourceAddress|218.90.204.141|可用于与网络事件关联的检测。 例如，"与恶意网络目标的通信"。|
> |15 |URL|requestUrl|down.esales360.cn|可用于与网络事件关联的检测。 例如，"与恶意网络目标的通信"。|
> |16|RemediationIsSuccess|deviceCustomNumber2|TRUE|可用于 Microsoft Defender AV 检测。 当为 TRUE 时，ArcSight 值为 1，FALSE 时为 0。|
> |17 |WasExecutingWhileDetected|deviceCustomNumber1|FALSE|可用于 Microsoft Defender AV 检测。 当为 TRUE 时，ArcSight 值为 1，FALSE 时为 0。|
> |18 |AlertId|externalId|636210704265059241_673569822|可用于每个检测的值。|
> |19|LinkToWDATP|flexString1|`https://securitycenter.windows.com/alert/636210704265059241_673569822`|可用于每个检测的值。|
> |20|AlertTime|deviceReceiptTime|2017-05-07T01：56：59.3191352Z|事件发生的时间。 可用于每个检测的值。|
> | 21|MachineDomain|sourceDnsDomain|contoso.com|与已加入设备AAD域名。 可用于每个检测的值。|
> |22|Actor|deviceCustomString4|一个|可用于与已知主角组相关的警报。|
> |21+5|ComputerDnsName|无映射|liz-bean.contoso.com|设备完全限定的域名。 可用于每个检测的值。|
> ||LogOnUsers|sourceUserId|contoso\liz-bean;contoso\为 hardee|事件发生时交互式登录用户的域和用户。 注意：对于 Windows 10版本 1607 的设备，域信息将不可用。|
> ||InternalIPv4List|无映射|192.168.1.7, 10.1.14.1|活动网络接口的 IPV4 内部 IP 列表。|
> ||InternalIPv6List|无映射|fd30：0000：0000：0001：ff4e：003e：0009：000e， FE80：CD00：0000：0CDE：1257：0000：211E：729C|活动网络接口的 IPV6 内部 IP 列表。|
> ||LinkToMTP|无映射|`https://securitycenter.windows.com/alert/da637370718981685665_16349121`|可用于每个检测的值。
> ||IncidentLinkToMTP|无映射|`"https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM`|可用于每个检测的值。
> ||IncidentLinkToWDATP|无映射|`https://securitycenter.windows.com/preferences2/integration/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM`|可用于每个检测的值。
> |内部字段|LastProcessedTimeUtc|无映射|2017-05-07T01：56：58.9936648Z|事件到达后端的时间。 为检索检测的范围设置请求参数时，可以使用此字段。|
> ||不是架构的一部分|deviceVendor||ArcSight 映射中的静态值 - "Microsoft"。|
> ||不是架构的一部分|deviceProduct||ArcSight 映射中的静态值 - "Microsoft Defender ATP"。|
> ||不是架构的一部分|deviceVersion||ArcSight 映射中的静态值 - "2.0"，用于标识映射版本。|

:::image type="content" alt-text="带数字的警报图像。" source="images/atp-alert-page.png" lightbox="images/atp-alert-page.png":::

:::image type="content" alt-text="包含数字的警报详细信息窗格的图像。" source="images/atp-siem-mapping13.png":::

:::image type="content" alt-text="包含数字 1 的项目时间线的图像。" source="images/atp-siem-mapping3.png" lightbox="images/atp-siem-mapping3.png":::

:::image type="content" alt-text="包含数字 2 的项目时间线的图像。" source="images/atp-siem-mapping4.png" lightbox="images/atp-siem-mapping4.png":::

:::image type="content" alt-text="映像计算机视图。" source="images/atp-mapping6.png" lightbox="images/atp-mapping6.png":::

:::image type="content" alt-text="图像浏览器 URL。" source="images/atp-mapping5.png" lightbox="images/atp-mapping5.png":::

:::image type="content" alt-text="图像参与者警报。" source="images/atp-mapping7.png" lightbox="images/atp-mapping7.png":::

## <a name="related-topics"></a>相关主题

- [在 Microsoft Defender for Endpoint 中启用 SIEM 集成](enable-siem-integration.md)
- [配置 ArcSight 以拉取适用于终结点检测的 Microsoft Defender](configure-arcsight.md)
- [使用 REST API 拉取 Microsoft Defender 的终结点检测](pull-alerts-using-rest-api.md)
- [SIEM 工具集成问题疑难解答](troubleshoot-siem.md)
