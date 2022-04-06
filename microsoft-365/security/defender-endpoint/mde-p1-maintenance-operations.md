---
title: 管理Microsoft Defender for Endpoint计划 1
description: 维护和更新 Defender for Endpoint Plan 1。 管理设置、获取更新并解决误报/负数。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 01/03/2022
ms.prod: m365-security
ms.technology: mdep1
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection: M365-security-compliance
ms.openlocfilehash: 417dd33eed846e45453464e63ff403374ce224dc
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64667397"
---
# <a name="manage-microsoft-defender-for-endpoint-plan-1"></a>管理Microsoft Defender for Endpoint计划 1

**适用对象**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)

在组织中使用 Defender for Endpoint Plan 1 时，安全团队可以执行某些步骤来维护安全解决方案。 在安全团队汇总维护和操作计划时，请确保至少包括以下活动：

- [管理安全智能和产品更新](#manage-security-intelligence-and-product-updates)
- [微调和调整 Defender for Endpoint](#fine-tune-and-adjust-defender-for-endpoint)
- [解决误报/负数](#address-false-positivesnegatives)

## <a name="manage-security-intelligence-and-product-updates"></a>管理安全智能和产品更新

保持Microsoft Defender 防病毒最新对于防范新的恶意软件和攻击技术至关重要。 Microsoft 会定期发布安全智能、防病毒和反恶意软件保护更新。 更新分为两类： 

- 安全智能更新
- 产品更新 

若要管理安全智能和产品更新，请参阅["管理Microsoft Defender 防病毒更新并应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。

## <a name="fine-tune-and-adjust-defender-for-endpoint"></a>微调和调整 Defender for Endpoint

Defender for Endpoint 提供了许多灵活性和配置选项。 可以根据组织的需求调整和微调设置。 例如，可以使用Microsoft Endpoint Manager、组策略和其他方法来管理终结点安全设置。 

若要了解详细信息，请参阅 [Manage Defender for Endpoint](manage-mde-post-migration.md)。

## <a name="address-false-positivesnegatives"></a>解决误报/负数

误报是一个项目，如文件或进程，被检测为恶意，即使它实际上不是威胁。 假负值是未检测为威胁的实体，即使它实际上是。 任何终结点保护解决方案（包括 Defender for Endpoint）都可能发生误报/负值。 但是，可以采取一些步骤来解决这些类型的问题并微调解决方案，如下图所示：

:::image type="content" source="../../media/defender-endpoint/false-positives-overview.png" alt-text="误报和负数过程概述" lightbox="../../media/defender-endpoint/false-positives-overview.png":::

如果在 Defender for Endpoint 中看到误报/负数，请参[阅Microsoft Defender for Endpoint中的地址误报/负](defender-endpoint-false-positives-negatives.md)数。

## <a name="next-steps"></a>后续步骤

- [请参阅Microsoft Defender for Endpoint中的新增功能](whats-new-in-microsoft-defender-endpoint.md)