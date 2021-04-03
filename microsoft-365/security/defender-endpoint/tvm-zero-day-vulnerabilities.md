---
title: 缓解零日漏洞 - 威胁和漏洞管理
description: 了解如何通过威胁和漏洞管理查找并减少环境中零日漏洞。
keywords: mdatp tvm zero day vulnerabilities， tvm， threat & vulnerability management， zero day， 0-day， mitigate 0 day vulnerabilities， vulnerable CVE
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 941e4989dcb91ff9240131f5980d0e1eced2b21d
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501221"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a>缓解零日漏洞 - 威胁和漏洞管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

零日漏洞是公开披露的漏洞，尚未发布正式的修补程序或安全更新程序。 零日漏洞通常具有高严重性级别，并且被主动利用。

威胁和漏洞管理将仅显示其拥有相关信息的零日漏洞。

## <a name="find-information-about-zero-day-vulnerabilities"></a>查找有关零日漏洞的信息

一旦发现零日漏洞，相关信息将在 Microsoft Defender 安全中心通过以下体验传达。

### <a name="threat-and-vulnerability-management-dashboard"></a>威胁和漏洞管理仪表板

在"顶级安全建议"卡片中查找带零日标记的建议。

![带零日标记的热门建议。](images/tvm-zero-day-top-security-recommendations.png)

在"最易受攻击的软件"卡中查找带零日标记的顶级软件。

![具有零日标记的易受攻击的软件。](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a>"漏洞"页

查找已命名的零日漏洞以及说明和详细信息。

- 如果此漏洞分配了 CVE ID，你将在 CVE 名称旁边看到零日标签。

- 如果此漏洞未分配 CVE ID，你将在类似于"TVM-XXXX-XXXX"的内部临时名称下找到它。 分配官方 CVE-ID 后，该名称将更新，但以前的内部名称仍可搜索，并位于侧面板中。

![零日示例，针对"漏洞"页面的 CVE-2020-17087。](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a>软件清单页

查找带零日标记的软件。 按"零日"标记进行筛选，以仅查看具有零日漏洞的软件。

![软件清单页中的 Windows Server 2016 零日示例。](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a>"软件"页

查找受零日漏洞影响的每个软件的零日标记。

![Windows Server 2016 软件页的零日示例。](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a>"安全建议"页

查看有关修正和缓解选项的清晰建议，包括解决方法（如果存在）。 按"零日"标记进行筛选，以仅查看解决零日漏洞的安全建议。

如果有软件具有零日漏洞和其他要解决的漏洞，你将获得有关所有漏洞的一个建议。

![安全建议页中的 Windows Server 2016 零日示例。](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a>解决零日漏洞

转到安全建议页面，然后选择一个零日建议。 将打开一个空出场，并提供有关该软件的零日和其他漏洞的信息。

如果缓解选项和解决方法可用，将会提供相关链接。 在可以部署修补程序或安全更新之前，解决方法可能会帮助降低此零日漏洞带来的风险。

打开修正选项并选择注意类型。 建议对零日漏洞使用"注意"修正选项，因为更新尚未发布。 由于没有要执行的特定操作，因此无法选择截止日期。 如果你希望修正此软件存在较旧的漏洞，你可以替代"需要注意"的修正选项并选择"更新"。

![安全建议页中 Windows Server 2016 的零日飞出示例。](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a>跟踪零日修正活动

转到威胁和漏洞管理 [修正](tvm-remediation.md) 页面以查看修正活动项。 如果选择"注意需要"修正选项，则没有进度栏、票证状态或截止日期，因为我们可以监视任何实际操作。 您可以按修正类型（如"软件更新"或"需要注意"）进行筛选，以查看同一类别的所有活动项。

## <a name="patching-zero-day-vulnerabilities"></a>修补零日漏洞

当修补程序在零日发布时，建议将更改为"更新"，其旁边的蓝色标签显示"零日的新安全更新"。 它不再视为零日，将从所有页面中删除零日标记。

![建议使用新的修补程序标签"更新 Microsoft Windows 10"。](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a>相关文章

- [威胁和漏洞管理概述](next-gen-threat-and-vuln-mgt.md)
- [仪表板](tvm-dashboard-insights.md)
- [安全性建议](tvm-security-recommendation.md)
- [软件库存](tvm-software-inventory.md)
- [我组织中的漏洞](tvm-weaknesses.md)
