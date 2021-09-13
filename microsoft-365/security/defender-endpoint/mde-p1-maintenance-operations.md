---
title: '管理 Microsoft Defender for Endpoint Plan 1 (preview) '
description: 维护和更新终结点计划 1 的 Defender。 管理设置、获取更新并解决误报/负面影响。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 08/30/2021
ms.prod: m365-security
ms.technology: mde
localization_priority: Normal
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.openlocfilehash: c74549579efc9ddf94aa89cfe2007620ddd2d826
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59196578"
---
# <a name="manage-microsoft-defender-for-endpoint-plan-1-preview"></a>管理 Microsoft Defender for Endpoint Plan 1 (preview) 

> [!TIP]
> 如果你已Microsoft 365 E3但没有Microsoft 365 E5，请访问 [https://aka.ms/mdep1trial](https://aka.ms/mdep1trial) 注册预览计划！

当你在组织中使用 Defender for Endpoint Plan 1 (预览) 时，你的安全团队可以采取某些步骤来维护你的安全解决方案。 当安全团队将维护和操作计划汇集在一起时，请确保至少包括以下活动：

- [管理安全智能和产品更新](#manage-security-intelligence-and-product-updates)
- [微调和调整适用于终结点的 Defender](#fine-tune-and-adjust-defender-for-endpoint)
- [解决误报/负数](#address-false-positivesnegatives)

> [!IMPORTANT]
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 本文包含指向在线内容的链接，这些链接可能介绍 Defender for Endpoint Plan 1 (预览版中未) 。

## <a name="manage-security-intelligence-and-product-updates"></a>管理安全智能和产品更新

保持Microsoft Defender 防病毒是抵御新的恶意软件和攻击技术的关键。 Microsoft 为安全智能、防病毒和反恶意软件保护发布定期更新。 更新分为两类： 

- 安全智能更新
- 产品更新 

若要管理安全智能和产品更新，请参阅管理Microsoft Defender 防病毒[更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。

## <a name="fine-tune-and-adjust-defender-for-endpoint"></a>微调和调整适用于终结点的 Defender

Defender for Endpoint 提供了很多灵活性和配置选项。 您可以调整和微调设置，以满足组织的需求。 例如，可以使用 Microsoft Endpoint Manager、组策略和其他方法来管理终结点安全设置。 

若要了解更多信息，请参阅[管理适用于终结点的 Defender。](manage-atp-post-migration.md)

## <a name="address-false-positivesnegatives"></a>解决误报/负数

误报是一个被检测为恶意的项目，如文件或进程，即使它不是实际的威胁。 漏报是未检测为威胁的实体，即使实际存在。 任何终结点保护解决方案（包括 Defender for Endpoint）都可能发生误报/负数。 但是，您可以采取一些步骤来解决这些种类的问题并微调您的解决方案，如下图所示：

:::image type="content" source="../../media/defender-endpoint/false-positives-overview.png" alt-text="误报和负面影响过程概述":::

如果你在 Defender for Endpoint 中看到误报/负数，请参阅在 Microsoft Defender for Endpoint 中解决 [误报/负数](defender-endpoint-false-positives-negatives.md)。

## <a name="next-steps"></a>后续步骤

- [查看 Microsoft Defender for Endpoint 中的新增功能](whats-new-in-microsoft-defender-atp.md)