---
title: Microsoft Defender for Business 中的简化配置过程
description: 了解 Microsoft Defender for Business 中的简化配置过程
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/08/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: e406bec25d628e028ecf7d0b2aaf4a1447e3a42e
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61374868"
---
# <a name="the-simplified-configuration-process-in-microsoft-defender-for-business"></a>Microsoft Defender for Business 中的简化配置过程

> [!IMPORTANT]
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 本文包含指向可能介绍 Microsoft Defender for Business 预览版中未包含的一些 (内容) 。

Microsoft Defender for Business 采用简化的配置过程，专为中小型企业设计。 此体验通过类似向导的体验和默认策略（旨在从第一天开始保护公司设备）来猜测载入和管理设备。 **我们建议使用简化的配置过程;但是，不限于此选项**。

对于载入设备和为公司设备配置安全设置，你可以从以下几种体验中选择： 

- Microsoft Defender for Business 中的简化配置过程 (*推荐)* 
- Microsoft Endpoint Manager，包括Microsoft Intune
- 用于管理设备的非 Microsoft 解决方案 

## <a name="what-to-do"></a>需执行的操作

1. [查看设置和配置选项](#review-your-setup-and-configuration-options)
2. [详细了解 Defender for Business 中的简化配置过程](#why-we-recommend-using-the-simplified-configuration-process)
3. [继续执行下一步](#next-steps)

## <a name="review-your-setup-and-configuration-options"></a>查看设置和配置选项

下表介绍了每种体验：
<br/><br/>

| 门户体验  | 说明  |
|---------|---------|
| Microsoft 365 Defender 门户中的 [https://security.microsoft.com](https://security.microsoft.com) ()  <br/> (*对于大多数客户来说，这是推荐*)   | 简化的配置体验包括可帮助你保护公司设备的默认安全设置和策略。 借助此体验，安全团队使用Microsoft 365 Defender门户： <br/>- 设置和配置 Defender for Business <br/>- 查看和管理事件<br/>- 响应和缓解威胁<br/>- 查看报告<br/>- 查看挂起或已完成的操作 <br/><br/> 此门户是贵公司安全设置和威胁防护功能的一站式商店。 你获得简化的体验，帮助你快速高效地入门。  此外，还可以编辑设置或定义新策略以满足公司需求。<br/><br/>若要了解更多信息，请参阅 [在 Microsoft Defender for Business 中查看或编辑设备策略](mdb-view-edit-policies.md)。 |
| 管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ()   | Microsoft Endpoint Manager包括 Microsoft Intune、基于云的移动设备管理 (MDM) 以及适用于应用) 设备的 MAM (移动应用管理。 <br/><br/>许多组织使用 Intune 管理其设备，如移动电话、平板电脑和笔记本电脑。 若要了解更多信息[，Microsoft Intune你的设备的 MDM 和 MAM 提供程序](/mem/intune/fundamentals/what-is-intune)。 <br/><br/>如果你已在使用 Microsoft Intune 或 Microsoft Endpoint Manager，可以继续使用该解决方案。 |
| 非 Microsoft 设备管理解决方案  | 如果你使用的是非 Microsoft 生产力和设备管理解决方案，例如 Jamf for macOS 或 Ansible for Linux，你可以继续使用适用于 Business 的 Defender 解决方案。 <br/><br/>当设备载入到 Defender for Business 时，你将在应用门户中查看Microsoft 365 Defender警报。 若要了解详细信息，请参阅 Defender for Endpoint 的载入 [和配置工具选项](../defender-endpoint/onboard-configure.md)。<br/><br/>如果你已在使用非 Microsoft 设备管理解决方案，可以继续使用该解决方案。 |


## <a name="why-we-recommend-using-the-simplified-configuration-process"></a>为何我们建议使用简化的配置过程

**我们建议大多数客户在 Microsoft Defender for Business** 中使用简化的配置过程。 简化的配置过程已简化，特别是对于中小型企业。 Defender for Business 旨在帮助你在第一天保护公司设备，而无需深入的技术专长或特殊知识。 使用默认安全设置和策略，设备在载入后即受到保护。


Defender for Business 旨在提供强大的保护，同时节省你配置安全设置的时间和精力。 通过简化体验，Microsoft 365 Defender轻松载入和管理设备。 此外，还包括默认策略，以便公司设备在载入后即受到保护。 您可以保留默认设置，也可以进行更改以满足业务需求。 还可以添加新策略以根据需要管理设备。

## <a name="next-steps"></a>后续步骤

- [设置和配置 Microsoft Defender for Business](mdb-setup-configuration.md)

- [开始使用 Microsoft Defender for Business](mdb-get-started.md)