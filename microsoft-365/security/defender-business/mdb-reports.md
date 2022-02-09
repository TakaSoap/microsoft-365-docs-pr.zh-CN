---
title: 'Microsoft Defender for Business 预览版 (中的) '
description: '获取 Microsoft Defender for Business 预览版中提供的 (概述) '
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 01/06/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 9d70984e4bce9cd7724326ca5f823fb9cf7d7440
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2022
ms.locfileid: "62464736"
---
# <a name="reports-in-microsoft-defender-for-business-preview"></a>Microsoft Defender for Business 预览版 (中的) 

> [!IMPORTANT]
> Microsoft Defender for Business 现在为预览版，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 我们将于未来几周内载入一组初始客户和合作伙伴，并扩大预览版本，从而一般可用。 请注意，预览将启动 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 Microsoft Defender for Business (预览) 包括下表中所述的几个报告：<br/><br/>

一些报告在 Microsoft 365 Defender 门户 () [https://security.microsoft.com](https://security.microsoft.com) 。 本文介绍这些报告、如何使用这些报告以及如何查找它们。

>
> **有空吗？**
> 请参加有关 <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business 的简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

<br/><br/>

## <a name="reports-in-defender-for-business"></a>Defender for Business 中的报告

|报告  |说明  |
|---------|---------|
| **安全报告**  | 安全报告提供有关组织的标识、设备和应用的信息。 若要访问此报告，在导航窗格中，选择 **ReportsGeneralSecurity** >  >  **报告**。 <br/><br/>**提示** 可以在 Microsoft 365 Defender 门户的主页上查看 () [https://security.microsoft.com](https://security.microsoft.com) 。 |
| **威胁防护**  | 威胁防护报告提供有关警报和警报趋势的信息。 使用 **"警报趋势** "列查看有关过去 30 天内触发的警报的信息。 使用 **警报状态** 列可查看有关警报的当前快照信息，例如未解决警报的类别及其分类。 若要访问此报告，在导航窗格中，选择 **ReportsEndpointsThreat** >  >  **保护**。 <br/><br/>**提示**：您还可以 **使用事件列表** 查看有关警报的信息。 在导航窗格中，选择 **"事件** "以查看和管理当前事件。 若要了解更多信息，请参阅在 [Microsoft Defender for Business ](mdb-view-manage-incidents.md)中查看和管理事件 (预览) 。 |
| **设备健康状况和合规性** | 设备运行状况和合规性报告提供有关设备运行状况和趋势的信息。 可以使用此报告确定 Defender for Business (预览版) 传感器在设备上是否正常工作以及 Microsoft Defender 防病毒。 若要访问此报告，在导航窗格中，选择 **ReportsEndpointsDevice** >  >  **运行状况和合规性**。 <br/><br/>**提示**：可以使用设备 **清单** 列表查看有关组织设备的信息。 在导航窗格中，选择" **设备清单"**。 若要了解的详细信息，请参阅管理 [Microsoft Defender for Business 中的设备 (预览) ](mdb-manage-devices.md)。 |
| **易受攻击的设备** | 易受攻击的设备报告提供有关设备和趋势的信息。 使用 **"** 趋势"列查看有关过去 30 天内发出警报的设备的信息。 使用 **"状态** "列查看有关具有警报的设备的当前快照信息。 若要访问此报告，在导航窗格中，选择 **ReportsEndpointsVulnerable** >  >  **设备**。<br/><br/>**提示**：可以使用设备 **清单** 列表查看有关组织设备的信息。 在导航窗格中，选择" **设备清单"**。 若要了解的详细信息，请参阅管理 [Microsoft Defender for Business 中的设备 (预览) ](mdb-manage-devices.md)。 |
| **Web 保护功能** | Web 保护报告显示了尝试访问钓鱼网站、恶意软件矢量、攻击网站、不受信任的或低信誉网站以及明确阻止的网站。 被阻止的网站类别包括成人内容、成人网站、法律责任网站等。 若要访问此报告，在导航窗格中，选择 **ReportsEndpointsWeb** >  >  **protection**。<br/><br/>**提示**：如果尚未为组织配置 Web 保护，请选择 **设置中的"** 报表视图"。 然后，在" **规则"** 下，选择 **"Web 内容筛选"**。 若要了解有关 Web 内容筛选的信息，请参阅 [Web 内容筛选](../defender-endpoint/web-content-filtering.md)。 |

## <a name="see-also"></a>另请参阅

- [开始使用 Microsoft Defender for Business (预览) ](mdb-get-started.md)

- [在 Microsoft Defender for Business 预览版中查看 (事件) ](mdb-view-manage-incidents.md)

- [在 Microsoft Defender for Business 预览版中 (设备) ](mdb-manage-devices.md)
