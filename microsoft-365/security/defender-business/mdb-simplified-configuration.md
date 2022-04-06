---
title: Microsoft Defender 商业版中的简化配置过程
description: 在Microsoft Defender 商业版中了解简化的配置过程
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/15/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 02f970f7ad9981336ba54aaafcf936e952f1b726
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663107"
---
# <a name="the-simplified-configuration-process-in-microsoft-defender-for-business"></a>Microsoft Defender 商业版中的简化配置过程

> [!IMPORTANT]
> Microsoft Defender 商业版从 2022 年 3 月 1 日开始向[Microsoft 365 商业高级版](../../business-premium/index.md)客户推出。 Defender for Business 作为独立订阅处于预览状态，将逐步推出给 [在此处注册](https://aka.ms/mdb-preview) 以请求该订阅的客户和 IT 合作伙伴。 预览版包括 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的一些信息涉及到预租产品/服务，这些产品/服务在商业发布之前可能会进行重大修改。 Microsoft 不会对此处提供的信息作出明示或暗示的保证。 

Microsoft Defender 商业版具有简化的配置过程，专为中小型企业设计。 此体验采用了载入和管理设备的猜测，其体验类似于向导，并采用默认策略，旨在从第一天起保护公司的设备。 **建议使用简化的配置过程;但是，不限于此选项**。

在载入设备和为公司设备配置安全设置方面，可以从多种体验中进行选择： 

- 建议Microsoft Defender 商业版 () 中的简化配置过程 
- Microsoft Endpoint Manager，其中包括Microsoft 365 商业高级版) 中包含的[Microsoft Intune (](../../business-premium/index.md)
- 用于管理设备的非 Microsoft 解决方案 

## <a name="what-to-do"></a>需执行的操作

1. [查看设置和配置选项](#review-your-setup-and-configuration-options)

2. [详细了解 Defender for Business 中的简化配置过程](#why-we-recommend-using-the-simplified-configuration-process)

3. [继续执行后续步骤](#next-steps)

>
> **有空吗？**
> 请对<a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender 商业版进行简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="review-your-setup-and-configuration-options"></a>查看设置和配置选项

下表描述了每种体验：
<br/><br/>

| 门户体验  | 说明  |
|---------|---------|
| Microsoft 365 Defender门户中的简化配置体验 () [https://security.microsoft.com](https://security.microsoft.com) <br/> (*这是大多数客户的建议选项*)   | 简化的配置体验包括类似向导的体验，可帮助你设置和配置 Defender for Business。 简化的配置还包括默认的安全设置和策略，以帮助你在公司设备加入 Defender for Business 后立即保护它们。 <br/><br/>使用此体验，安全团队使用Microsoft 365 Defender门户执行以下操作： <br/>- 设置和配置 Defender for Business <br/>- 查看和管理事件<br/>- 响应和缓解威胁<br/>- 查看报表<br/>- 查看挂起或已完成的操作 <br/><br/> Microsoft 365 Defender门户是公司安全设置和威胁防护功能的一站式商店。 你可以获得简化的体验，帮助你快速高效地入门。 若要了解详细信息，请参阅["使用向导"设置Microsoft Defender 商业版](mdb-use-wizard.md)。<br/><br/>而且，可以编辑设置或定义新策略以满足公司的需求。<br/><br/>若要了解详细信息，请参阅[Microsoft Defender 商业版中的"查看"或"编辑设备策略](mdb-view-edit-policies.md)"。 |
| Microsoft Endpoint Manager管理中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com)  | Microsoft Endpoint Manager包括Microsoft Intune、基于云的移动设备管理 (MDM) 和移动应用程序管理 (适用于应用和设备的 MAM) 提供程序。 [Microsoft 365 商业高级版](../../business-premium/index.md)客户已Endpoint Manager。 <br/><br/>许多公司使用Intune来管理其设备，如手机、平板电脑和笔记本电脑。 若要了解详细信息，请参阅[Microsoft Intune是设备的 MDM 和 MAM 提供程序](/mem/intune/fundamentals/what-is-intune)。 <br/><br/>如果已在使用Microsoft Intune或Microsoft Endpoint Manager，则可以继续使用该解决方案。 |
| 非 Microsoft 设备管理解决方案  | 如果使用的是非 Microsoft 生产力和设备管理解决方案，则可以继续将该解决方案与 Defender for Business 配合使用。 <br/><br/>当设备载入到 Defender for Business 时，你将在Microsoft 365 Defender门户中看到其状态和警报。 若要了解详细信息，请参阅 [Defender for Endpoint 的载入和配置工具选项](../defender-endpoint/onboard-configure.md)。 |


## <a name="why-we-recommend-using-the-simplified-configuration-process"></a>为什么建议使用简化的配置过程

建议对大多数客户 **使用Microsoft Defender 商业版中的简化配置过程**。 简化的配置过程非常简化，尤其适用于中小型企业。 Defender for Business 旨在帮助你在第一天保护公司的设备，而无需深入的技术专业知识或专业知识。 使用默认安全设置和策略时，设备在加入后会立即受到保护。

Defender for Business 旨在提供强大的保护，同时节省配置安全设置的时间和精力。 Microsoft 365 Defender门户中的简化体验使载入设备和管理设备变得简单。 此外，还包含默认策略，以便公司设备在加入后立即受到保护。 可以保留默认设置，也可以根据业务需求进行更改。 还可以添加新策略以根据需要管理设备。

## <a name="next-steps"></a>后续步骤

- [设置和配置Microsoft Defender 商业版](mdb-setup-configuration.md)

- [使用Microsoft Defender 商业版开始](mdb-get-started.md)
