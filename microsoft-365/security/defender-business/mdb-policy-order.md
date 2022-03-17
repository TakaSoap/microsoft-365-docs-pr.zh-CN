---
title: 了解 Microsoft Defender for Business 中的策略顺序
description: 了解 Microsoft Defender for Business 中策略的优先级顺序
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
ms.openlocfilehash: 373f3eb821e00f903837f98896ed5dab0588e946
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2022
ms.locfileid: "63524903"
---
# <a name="understand-policy-order-in-microsoft-defender-for-business"></a>了解 Microsoft Defender for Business 中的策略顺序

> [!IMPORTANT]
> 从 2022 年 3 [月](../../business-premium/index.md) 1 Microsoft 365 商业高级版 Microsoft Defender for Business 将推出给客户。 作为独立订阅的 Defender for Business 在预览版中，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 预览 [包括一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

## <a name="policy-order-in-microsoft-defender-for-business"></a>Microsoft Defender for Business 中的策略顺序

Microsoft Defender for Business 包括预定义策略，可帮助确保员工使用的设备受到保护。 安全团队也可以添加新策略。 例如，假设你想要将某些设置应用到某些设备，而将不同的设置应用于其他设备。 可以通过添加策略（如下一代保护策略或防火墙策略）来完成这一点。

添加策略时，你会注意到已分配优先级顺序。 您可以编辑定义的策略的优先级顺序，但无法更改默认策略的优先级顺序。 例如，假设对于 Windows设备，你有三个下一代保护策略。 在这种情况下，默认策略的优先级为 3。 您可以更改编号为 1 和 2 的策略的顺序，但默认策略将保留列表中的数字 3。 

**对于多个策略，需要记住的重要一点就是设备将仅接收第一个应用的策略。** 引用我们之前关于三个下一代策略的示例，假设你有三个策略都面向的设备。 在这种情况下，这些设备将收到策略号 1，但是不会接收编号为 2 和 3 的策略。 

>
> **有空吗？**
> 请参加有关 <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business 的简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="key-points-to-remember-about-policy-order"></a>要记住的关于策略顺序的要点

- 策略按优先级顺序分配。

- 设备仅接收第一个应用的策略。

- 您可以更改策略的优先级顺序。

- 默认策略的优先级顺序最低。

## <a name="next-steps"></a>后续步骤

- [开始使用 Defender for Business](mdb-get-started.md)

- [管理设备](mdb-manage-devices.md)

- [在 Microsoft Defender for Business 中查看和管理事件](mdb-view-manage-incidents.md)

- [响应和缓解 Microsoft Defender for Business 中的威胁](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)