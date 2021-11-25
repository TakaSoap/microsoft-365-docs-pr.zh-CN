---
title: 反馈循环阻止
description: 反馈循环阻止（也称为快速保护）是 Microsoft Defender for Endpoint 中的行为阻止和包含功能的一部分
keywords: 行为阻止， 快速保护， 反馈阻止， Microsoft Defender for Endpoint
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.localizationpriority: medium
ms.custom:
- next-gen
- edr
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 82d5fb32a9535a5b341bca8e5bee989d88ad8232
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167354"
---
# <a name="feedback-loop-blocking"></a>反馈循环阻止

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a>概述

反馈循环阻止也称为快速保护，是 Microsoft Defender for Endpoint[](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment)中行为阻止和包含功能的一[个组件](/windows/security/threat-protection/)。 通过反馈循环阻止，可以更好地保护整个组织的设备免受攻击。 

## <a name="how-feedback-loop-blocking-works"></a>反馈循环阻止的工作原理

当检测到可疑行为或文件时（如通过[Microsoft Defender 防病毒）时](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)，有关项目的信息将被发送到多个分类器。 快速保护循环引擎检查信息并将信息与其他信号关联，以决定是否阻止文件。 检查项目并对这些项目进行分类会快速发生。 它可快速阻止已确认的恶意软件，并驱动整个生态系统的保护。 

通过快速保护，攻击可以在设备、组织的其他设备和其他组织中的设备上停止，因为攻击尝试扩大其位置。


## <a name="configuring-feedback-loop-blocking"></a>配置反馈循环阻止

如果你的组织对终结点使用 Defender，则默认启用反馈循环阻止。 但是，通过结合使用 Defender for Endpoint 功能、机器学习保护功能和 Microsoft 安全服务中的信号共享，可快速提供保护。 确保已启用和配置 Defender for Endpoint 的以下特性和功能：

- [适用于终结点的 Microsoft Defender 基线](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [载入到 Microsoft Defender for Endpoint 的设备](/microsoft-365/security/defender-endpoint/onboard-configure)

- [块模式下的 EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [减少攻击面](/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [下一代保护](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (防病毒) 

## <a name="related-articles"></a>相关文章

- [行为阻止和控制](behavioral-blocking-containment.md)

- [ (博客) 行为阻止和抑制：将光学镜头转换为保护](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [适用于终结点资源的有用 Microsoft Defender](/microsoft-365/security/defender-endpoint/helpful-resources)
