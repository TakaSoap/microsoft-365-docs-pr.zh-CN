---
title: 安全建议危险和漏洞管理
description: 获取可操作的安全建议（按威胁、被泄露的可能性和价值危险和漏洞管理。
keywords: 危险和漏洞管理， 适用于终结点的 Microsoft Defender 电视安全建议， 网络安全建议， 可操作的安全建议
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e7ff7a98e8550996068686b5b0805ea3a72cd6ae
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468558"
---
# <a name="security-recommendations---threat-and-vulnerability-management"></a>安全建议 - 危险和漏洞管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)。

组织中标识的网络安全漏洞将映射到可操作的安全建议，并按其影响确定优先级。 优先建议有助于缩短缓解或修正漏洞和推动合规性的时间。

每个安全建议都包括可操作修正步骤。 为了帮助进行任务管理，也可使用 Microsoft Intune 和 Microsoft Endpoint Configuration Manager。 当威胁形势发生变化时，建议也会发生变化，因为它会持续从你的环境收集信息。

> [!TIP]
> 若要获取有关新漏洞事件的电子邮件，请参阅在 [Microsoft Defender for Endpoint 中配置漏洞电子邮件通知](configure-vulnerability-email-notifications.md)

## <a name="how-it-works"></a>如何工作

组织的每台设备都基于三个重要因素进行评分，以帮助客户在正确的时间专注于正确的内容。

- **威胁**：组织设备中的漏洞和攻击的特征和泄露历史记录。 根据这些因素，安全建议显示活动警报的相应链接、正在进行的威胁活动及其相应的威胁分析报告。
- **泄露可能性**：组织的安全状态和抵御威胁的复原能力。
- **业务价值**：组织的资产、关键流程和知识产权。

## <a name="navigate-to-the-security-recommendations-page"></a>导航到"安全建议"页

以几种不同方式访问"安全建议"页：

- 漏洞管理门户中的威胁和Microsoft 365 Defender[菜单](portal-overview.md)
- 仪表板中危险和漏洞管理[建议](tvm-dashboard-insights.md)

查看以下位置的相关安全建议：

- "软件"页
- 设备页面

### <a name="navigation-menu"></a>导航菜单

转到"**漏洞管理"导航** 菜单，然后选择"推荐 **"**。 此页面包含针对组织中发现的威胁和漏洞的安全建议列表。

### <a name="top-security-recommendations-in-the-threat-and-vulnerability-management-dashboard"></a>仪表板中的顶级安全危险和漏洞管理建议

在给定一天中，作为安全管理员，你可以查看 危险和漏洞管理 仪表板，以查看[](tvm-dashboard-insights.md)你的曝光分数与[你的 Microsoft 设备安全分数并排](tvm-microsoft-secure-score-devices.md)显示。[](tvm-exposure-score.md) 目标是 **降低组织对** 漏洞的暴露程度，提高组织的设备安全性，以抵御网络安全威胁攻击。 顶级安全建议列表可帮助你实现该目标。

:::image type="content" source="images/top-security-recommendations350.png" alt-text="顶级安全建议卡片" lightbox="images/top-security-recommendations350.png":::


顶级安全建议列出了根据上一节中提到的重要因素（威胁、被泄露的可能性和价值）确定优先级的改进机会。 选择一个建议将你访问包含更多详细信息的安全建议页面。

## <a name="security-recommendations-overview"></a>安全建议概述

查看建议、发现漏洞的数量、相关组件、威胁见解、公开设备的数量、状态、修正类型、修正活动、对曝光分数和 Microsoft 设备安全分数的影响以及关联的标记。

"公开设备 **"图的颜色** 随着趋势的变化而更改。 如果公开的设备数量上升，则颜色将变为红色。 如果公开设备的数量减少，图形的颜色将变为绿色。

> [!NOTE]
> 威胁漏洞管理显示最多 **30** 天之前使用的设备。 这不同于适用于终结点的 Microsoft Defender 的其余部分，如果设备已使用超过 7 天，则设备处于"非活动"状态。

:::image type="content" source="images/tvmsecrec-updated.png" alt-text="安全建议登录页面" lightbox="images/tvmsecrec-updated.png":::

### <a name="icons"></a>图标

有用的图标也会快速吸引你注意：

- ![箭头命中目标。](images/tvm_alert_icon.png) 可能的活动警报
- ![红色 bug。](images/tvm_bug_icon.png) 关联的公共攻击
- ![光灯。](images/tvm_insight_icon.png) 建议见解

### <a name="explore-security-recommendation-options"></a>探索安全建议选项

选择要调查或处理的安全建议。

:::image type="content" source="images/secrec-flyouteolsw.png" alt-text="安全建议飞出页" lightbox="images/secrec-flyouteolsw.png":::

从飞出菜单，可以选择以下任一选项：

- **打开软件页** - 打开软件页，获取有关软件及其分发方式的更多上下文。 这些信息可能包括威胁上下文、相关建议、发现的漏洞、公开的设备数量、发现的漏洞、已安装软件的设备的名称和详细信息以及版本分发。

- [**修正选项**](tvm-remediation.md) - 提交修正请求以在 Microsoft Intune中打开票证，让 IT 管理员进行选取和解决。 在"修正"页中跟踪修正活动。

- [**例外选项**](tvm-exception.md) - 提交异常、提供理由以及设置异常持续时间（如果尚无法修正问题）。

> [!NOTE]
> 在 Windows、Linux 或 macOS 设备上进行软件更改时，通常需要 2-4 小时才能将数据反映在安全门户中。 可能需要 8 小时才能反映 iOS 和 Android 设备上的更改。 在某些情况下，可能需要更长时间。
> 
> 配置更改可能需要 4 到 24 小时。

### <a name="investigate-changes-in-device-exposure-or-impact"></a>调查设备曝光或影响的更改

如果公开设备的数量明显增长，或者对组织曝光分数和 Microsoft 设备安全分数的影响明显增加，则值得调查该安全建议。

1. 选择建议和 **"打开软件"页**
2. 选择 **"事件时间线** "选项卡以查看与该软件相关的所有影响事件，例如新漏洞或新的公共攻击。 [详细了解事件时间线](threat-and-vuln-mgt-event-timeline.md)
3. 确定如何处理增加或组织的曝光，例如提交修正请求

## <a name="request-remediation"></a>请求修正

这危险和漏洞管理修复功能通过修正请求工作流填补了安全和 IT 管理员之间的空白。 安全管理员（如你可以请求 IT 管理员将漏洞从安全建议页面修正到 Intune） [了解有关修正选项的详细信息](tvm-remediation.md)

### <a name="how-to-request-remediation"></a>如何请求修正

选择要请求修正的安全建议，然后选择" **修正选项"**。 填写表单，然后选择" **提交请求"**。 转到" [**修正"**](tvm-remediation.md) 页以查看修正请求的状态。 [了解有关如何请求修正的信息](tvm-remediation.md#request-remediation)

## <a name="file-for-exception"></a>异常文件

当建议此时不相关时，作为修正请求的替代方法，你可以为建议创建例外。 [详细了解异常](tvm-exception.md)

只有具有"异常处理"权限的用户才能添加异常。 [详细了解 RBAC 角色](user-roles.md)。

为建议创建例外时，建议不再处于活动状态。 建议状态将更改为"完全 **异常**"或"部分异常 (组设置) 。

### <a name="how-to-create-an-exception"></a>如何创建异常

选择要创建例外的安全建议，然后选择" **例外选项"**。

:::image type="content" source="images/tvm-exception-options.png" alt-text="安全建议飞出控件中的例外选项按钮" lightbox="images/tvm-exception-options.png":::

填写表单并提交。 若要查看当前 (和过去) 的所有异常，请导航到"威胁 & 漏洞管理"菜单下的 [](tvm-remediation.md)"修正 **"** 页并选择"异常 **"选项卡。** 详细了解如何创建 [异常](tvm-exception.md#create-an-exception)

## <a name="report-inaccuracy"></a>报告 inaccuracy

当你看到任何模糊、不准确、不完整或已修正的安全建议信息时，你可以报告误报。

1. 打开安全建议。

2. 选择要报告的安全建议旁边的三个点，然后选择"报告 **不准确"**。

   :::image type="content" source="images/report-inaccuracy500.png" alt-text="&quot;报告不准确&quot;按钮" lightbox="images/report-inaccuracy500.png":::

3. 从弹出窗格中，从下拉菜单中选择不准确类别，填写您的电子邮件地址和有关不准确的详细信息。

4. 选择“**提交**”。 你的反馈将立即发送给危险和漏洞管理专家。

## <a name="related-articles"></a>相关文章

- [威胁和漏洞管理概述](next-gen-threat-and-vuln-mgt.md)
- [仪表板](tvm-dashboard-insights.md)
- [风险评分](tvm-exposure-score.md)
- [设备的 Microsoft 安全功能分数](tvm-microsoft-secure-score-devices.md)
- [修正漏洞](tvm-remediation.md)
- [创建和查看安全建议例外](tvm-exception.md)
- [活动日程表](threat-and-vuln-mgt-event-timeline.md)
