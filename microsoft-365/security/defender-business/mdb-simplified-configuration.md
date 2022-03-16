---
title: Microsoft Defender for Business 中的简化配置过程
description: 了解 Microsoft Defender for Business 中的简化配置过程
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/15/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 5a5b78515176de74fd97430b638782c3e453d917
ms.sourcegitcommit: a216617d6ff27fe7d3089a047fbeaac5d72fd25c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "63512736"
---
# <a name="the-simplified-configuration-process-in-microsoft-defender-for-business"></a>Microsoft Defender for Business 中的简化配置过程

> [!IMPORTANT]
> 从 2022 年 3 [月](../../business-premium/index.md) 1 Microsoft 365 商业高级版 Microsoft Defender for Business 将推出给客户。 作为独立订阅的 Defender for Business 在预览版中，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 预览 [包括一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

Microsoft Defender for Business 采用简化的配置过程，专为中小型企业设计。 此体验通过类似向导的体验和默认策略（旨在从第一天开始保护公司设备）来猜测载入和管理设备。 **我们建议使用简化的配置过程;但是，您不限于此选项**。

对于载入设备和为公司设备配置安全设置，你可以从以下几种体验中选择： 

- Microsoft Defender for Business 中的简化配置过程 (*推荐)* 
- Microsoft Endpoint Manager，其中包括Microsoft Intune (包括在Microsoft 365 商业高级版[) ](../../business-premium/index.md)
- 用于管理设备的非 Microsoft 解决方案 

## <a name="what-to-do"></a>需执行的操作

1. [查看设置和配置选项](#review-your-setup-and-configuration-options)

2. [详细了解 Defender for Business 中的简化配置过程](#why-we-recommend-using-the-simplified-configuration-process)

3. [继续执行下一步](#next-steps)

>
> **有空吗？**
> 请参加有关 <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business 的简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="review-your-setup-and-configuration-options"></a>查看设置和配置选项

下表介绍了每种体验：
<br/><br/>

| 门户体验  | 说明  |
|---------|---------|
| Microsoft 365 Defender门户中的 () [https://security.microsoft.com](https://security.microsoft.com) <br/> (*这是对大多数客户推荐的选项)*  | 简化的配置体验包括类似向导的体验，可帮助你设置和配置 Defender for Business。 简化的配置还包括默认安全设置和策略，可帮助你在将公司设备载入 Defender for Business 后尽快保护这些设备。 <br/><br/>借助此体验，安全团队使用Microsoft 365 Defender门户： <br/>- 设置和配置 Defender for Business <br/>- 查看和管理事件<br/>- 响应和缓解威胁<br/>- 查看报告<br/>- 查看挂起或已完成的操作 <br/><br/> Microsoft 365 Defender门户是公司安全设置和威胁防护功能的一站式商店。 你获得简化的体验，帮助你快速高效地入门。 若要了解更多信息，请参阅 [使用向导设置 Microsoft Defender for Business](mdb-use-wizard.md)。<br/><br/>此外，还可以编辑设置或定义新策略以满足公司需求。<br/><br/>若要了解更多信息，请参阅 [在 Microsoft Defender for Business 中查看或编辑设备策略](mdb-view-edit-policies.md)。 |
| 管理Microsoft Endpoint Manager中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com))   | Microsoft Endpoint Manager包括 Microsoft Intune、基于云的移动设备管理 (MDM) 以及适用于应用和设备 (MAM) 的移动应用程序管理。 [Microsoft 365 商业高级版](../../business-premium/index.md)客户已拥有Endpoint Manager。 <br/><br/>许多公司使用 Intune 管理其设备，如移动电话、平板电脑和笔记本电脑。 若要了解更多信息，[Microsoft Intune你的设备的 MDM 和 MAM 提供程序](/mem/intune/fundamentals/what-is-intune)。 <br/><br/>如果已在使用 Microsoft Intune 或 Microsoft Endpoint Manager，可以继续使用该解决方案。 |
| 非 Microsoft 设备管理解决方案  | 如果你使用的是非 Microsoft 生产力和设备管理解决方案，你可以继续将该解决方案与 Defender for Business 一同使用。 <br/><br/>当设备载入到 Defender for Business 时，你将在应用门户中查看Microsoft 365 Defender警报。 若要了解更多信息，请参阅 [Defender for Endpoint 的载入和配置工具选项](../defender-endpoint/onboard-configure.md)。 |


## <a name="why-we-recommend-using-the-simplified-configuration-process"></a>为何我们建议使用简化的配置过程

**我们建议大多数客户在 Microsoft Defender for Business** 中使用简化的配置过程。 简化的配置过程已简化，特别是对于中小型企业。 Defender for Business 旨在帮助你在第一天保护公司设备，而无需深入的技术专长或特殊知识。 使用默认安全设置和策略，设备在载入后即受到保护。

Defender for Business 旨在提供强大的保护，同时节省你配置安全设置的时间和精力。 通过简化体验，Microsoft 365 Defender轻松载入和管理设备。 此外，还包括默认策略，以便公司设备在载入后即受到保护。 您可以保留默认设置，也可以进行更改以满足业务需求。 还可以添加新策略以根据需要管理设备。

## <a name="next-steps"></a>后续步骤

- [设置和配置 Microsoft Defender for Business](mdb-setup-configuration.md)

- [开始使用 Microsoft Defender for Business](mdb-get-started.md)
