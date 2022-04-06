---
title: 了解策略顺序Microsoft Defender 商业版
description: 了解Microsoft Defender 商业版中的策略的优先级顺序
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/24/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 13e803666cc7af14af52031eb86a2f86edf06f80
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666297"
---
# <a name="understand-policy-order-in-microsoft-defender-for-business"></a>了解策略顺序Microsoft Defender 商业版

> [!IMPORTANT]
> Microsoft Defender 商业版从 2022 年 3 月 1 日开始向[Microsoft 365 商业高级版](../../business-premium/index.md)客户推出。 Defender for Business 作为独立订阅处于预览状态，将逐步推出给 [在此处注册](https://aka.ms/mdb-preview) 以请求该订阅的客户和 IT 合作伙伴。 预览版包括 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的一些信息涉及到预租产品/服务，这些产品/服务在商业发布之前可能会进行重大修改。 Microsoft 不会对此处提供的信息作出明示或暗示的保证。 

## <a name="policy-order-in-microsoft-defender-for-business"></a>Microsoft Defender 商业版中的策略顺序

Microsoft Defender 商业版包括预定义的策略，以帮助确保员工使用的设备受到保护。 安全团队也可以添加新策略。 例如，假设要将某些设置应用到某些设备，并将不同的设置应用于其他设备。 为此，可以添加策略，例如下一代保护策略或防火墙策略。

添加策略时，你会注意到分配了优先级顺序。 可以编辑定义的策略的优先级顺序，但不能更改默认策略的优先级顺序。 例如，假设对于Windows客户端设备，你有三个下一代保护策略。 在这种情况下，默认策略优先级为 3 号。 可以更改编号为 1 和 2 的策略的顺序，但默认策略将保留在列表中的 3 号。 

**要记住的有关多个策略的重要事项是，设备将仅收到第一个应用的策略。** 引用我们之前的三个下一代策略示例，假设你拥有所有三个策略的目标设备。 在这种情况下，这些设备将收到策略编号 1，但不会收到编号为 2 和 3 的策略。 

>
> **有空吗？**
> 请对<a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender 商业版进行简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="key-points-to-remember-about-policy-order"></a>要记住的有关策略顺序的要点

- 策略按优先级顺序分配。

- 设备仅接收第一个应用的策略。

- 可以更改策略的优先级顺序。

- 默认策略的优先级最低。

## <a name="next-steps"></a>后续步骤

- [开始使用 Defender for Business](mdb-get-started.md)

- [管理设备](mdb-manage-devices.md)

- [在Microsoft Defender 商业版中查看和管理事件](mdb-view-manage-incidents.md)

- [响应和缓解Microsoft Defender 商业版中的威胁](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)