---
title: 易受攻击的设备报告 - 危险和漏洞管理
description: 显示易受攻击的设备趋势和当前统计信息的报告。 目标是了解设备曝光的目的和范围。
keywords: Microsoft Defender for Endpoint-tvm 易受攻击的设备， Microsoft Defender for Endpoint， tvm， reduce threat & vulnerability exposure， reduce threat and vulnerability， monitor security configuration
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
ms.openlocfilehash: fa5280d9c6f396e8e164397210c1b58dfcfc8d9b
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64466710"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a>易受攻击的设备报告 - 危险和漏洞管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)。

该报告显示包含易受攻击的设备趋势和当前统计信息的图形和条形图。 目标是了解设备曝光的目的和范围。

通过访问报告门户中的Microsoft 365 Defender报告">**易受攻击的设备"**

有两列：

- 趋势 (随着时间的推移) 。 可以显示过去 30 天、3 个月、6 个月或自定义日期范围。
- 状态 (当前信息) 

**筛选器**：你可以按漏洞严重性级别、攻击可用性、漏洞年数、操作系统平台、Windows 10或 Windows 11 版本或设备组筛选数据。

**向下钻** 取：如果要进一步探索见解，请选择相关条形图以查看"设备清单"页中的已筛选设备列表。 可以从中导出列表。

## <a name="severity-level-graphs"></a>严重性级别图形

根据在该设备上发现的最严重漏洞，每台设备仅计数一次。

:::image type="content" source="images/tvm-report-severity.png" alt-text=" 显示当前设备漏洞严重性级别以及一段时间的级别的图形。" lightbox="images/tvm-report-severity.png":::

## <a name="exploit-availability-graphs"></a>攻击可用性图

根据最高级别的已知攻击，每台设备仅计数一次。

:::image type="content" source="images/tvm-report-exploit-availability.png" alt-text="显示当前设备攻击可用性和一段时间可用性的图形" lightbox="images/tvm-report-exploit-availability.png":::

## <a name="vulnerability-age-graphs"></a>漏洞年龄图

每台设备仅在最旧的漏洞发布日期下计算一次。 较早的漏洞遭到利用的机会较高。

:::image type="content" source="images/tvm-report-age.png" alt-text="显示当前设备漏洞时间和时间的图形" lightbox="images/tvm-report-age.png":::

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a>操作系统平台图的易受攻击的设备

因软件漏洞而公开的每台操作系统上的设备数量。

:::image type="content" source="images/tvm-report-os.png" alt-text="显示操作系统平台当前易受攻击的设备以及操作系统平台一段时间易受攻击的设备的图形" lightbox="images/tvm-report-os.png":::

## <a name="vulnerable-devices-by-windows-version-graphs"></a>按版本图Windows易受攻击的设备

因易受攻击的应用程序或操作系统Windows 10或Windows 11版本上的设备数量。

:::image type="content" source="images/tvm-report-version.png" alt-text="按版本显示当前易受攻击的设备Windows 10，以及按版本Windows 10易受攻击的设备的图形" lightbox="images/tvm-report-version.png":::

## <a name="related-topics"></a>相关主题

- [威胁和漏洞管理概述](next-gen-threat-and-vuln-mgt.md)
- [安全性建议](tvm-security-recommendation.md)
