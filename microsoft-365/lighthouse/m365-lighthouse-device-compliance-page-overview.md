---
title: Microsoft 365 Lighthouse设备合规性页面概述
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 对于托管服务提供商 (使用) 托管服务提供商Microsoft 365 Lighthouse，请了解"设备合规性"页。
ms.openlocfilehash: 76cb914b878b3da8236e91ddda538cb13fa3aa8c
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63317593"
---
# <a name="microsoft-365-lighthouse-device-compliance-page-overview"></a>Microsoft 365 Lighthouse设备合规性页面概述

Microsoft 365 Lighthouse通过选择左侧导航窗格中的"设备"打开"设备合规性"页，查看有关所有客户租户的 Intune  设备合规性的见解和信息。 在此页面中，你可以获取跨租户的合规性状态的概述，查看每个租户的设备列表，并获取有关合规性策略和设置的状态报告。

## <a name="overview-tab"></a>"概述"选项卡  
  
在"概述"选项卡上，可以查看租户中的设备合规性状态、查看每月设备合规性趋势，并跟踪设备是否分配有合规性策略。 还可以查看多少租户没有使用条件访问策略强制执行任何设备合规性要求。 可以选择" **查看更多"** 以查看更多详细信息。

若要获取特定客户租户的详细设备合规性信息，请在该租户的任何状态列下选择一个值。 这将打开"设备"选项卡，以便你可以查看所选租户的设备合规性详细信息。

若要将设备合规性数据导出到Excel逗号分隔值 (.csv) 文件，请选择"导出 **"**。

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png" alt-text="&quot;概述&quot;选项卡的屏幕截图。" lightbox="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png":::

## <a name="devices-tab"></a>"设备"选项卡

在"设备"选项卡上，彩色计数注释栏显示具有以下合规性状态的所有客户租户中的设备总数：Compliant、Not compliant、In grace period 和 Not evaluated。 有关不同合规性状态的信息，请参阅 [监视 Intune 设备合规性策略](/mem/intune/protect/compliance-policy-monitor)。

若要了解哪些租户的设备具有特定的合规性状态，请从计数注释栏中选择该状态以筛选列表。 若要查看一个或多个特定客户租户的设备合规性状态，请使用"租户"下拉菜单筛选列表。

选择列表中的任意设备名称以查看有关该设备的当前合规性状态的详细信息。 你可以同步或重新启动设备，如果需要进行故障排除 **或** 执行进一步操作Microsoft Endpoint Manager请选择"在设备上查看设备"。

> [!NOTE]
> 重新启动设备时，设备所有者不会自动收到通知，并且可能会丢失未保存的工作。 因此，你可能想要在重启设备之前通知设备所有者。

"设备"选项卡还包括以下选项：

- **导出：** 选择将设备合规性数据导出到Excel逗号分隔值 (.csv) 文件中。
- **刷新：** 选择以检索最新的设备合规性数据。
- **同步：** 从列表中选择状态为"不兼容、宽限期或未评估"的一个或多个设备，然后选择此选项以强制这些设备签入 Intune 并立即接收已分配给它们的任何策略。
- **重新启动：** 从列表中选择一个或多个状态为"不符合、宽限期"或"未评估"的设备，然后选择此选项以重新启动这些设备。
- **搜索：** 输入关键字以快速找到列表中的特定设备。
 
:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png" alt-text="&quot;设备&quot;选项卡的屏幕截图。" lightbox="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png":::

## <a name="policies-tab"></a>"策略"选项卡

在"策略"选项卡上，可以使用"比较"选项查看租户中的设备合规性策略，并比较两个或三个相同平台 **类型的** 策略。

若要查看特定平台上设备的策略，请使用 **"操作系统** "下拉菜单筛选列表。 若要查看一个或多个特定客户租户的策略，请使用"租户"下拉菜单筛选列表。

选择列表中的任意策略名称以查看有关该策略的更多详细信息。 如果需要采取措施或查看其他信息，请选择"**查看此** 策略"Microsoft Endpoint Manager。

"策略"选项卡还包括以下选项：

- **导出：** 选择将设备合规性策略数据导出到Excel逗号分隔值 (.csv) 文件。
- **刷新：** 选择以检索最新的设备合规性策略数据。
- **搜索：** 输入关键字以快速找到列表中的特定设备合规性策略。

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png" alt-text="&quot;策略&quot;选项卡的屏幕截图。" lightbox="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png":::

## <a name="settings-tab"></a>设置选项卡

the 设置 tab provides an aggregated report of non-complians settings across tenant devices. 

若要查看特定平台上设备的不兼容设置，请使用"平台"下拉菜单筛选列表。 若要查看一个或多个特定客户租户的不兼容设置，请使用"租户"下拉菜单筛选列表。

在列表中选择任何不兼容的设置名称以打开一个窗格，您可以在其中查看具有该特定不兼容设置的设备的租户列表。 在这里，可以通过从列表中选择任何租户来进一步向下钻取，以查看有关该租户内具有特定不兼容设置的设备的信息。 如果需要排除故障或执行进一步操作，还可以同步或重新启动设备，Microsoft Endpoint Manager"在设备上查看设备"。

"设置"选项卡还包括以下选项：

- **导出：** 选择将不兼容的设置数据导出到Excel逗号分隔值 (.csv) 文件中。
- **刷新：** 选择以检索最新的不合规设置数据。
- **搜索：** 输入关键字以在列表中快速找到特定的不兼容设置。

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png" alt-text="&quot;设置&quot;选项卡设置屏幕截图。" lightbox="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png":::

## <a name="related-content"></a>相关内容

[Windows 365 (云电脑) 概述 (](m365-lighthouse-win365-page-overview.md)文章) \
[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) 
