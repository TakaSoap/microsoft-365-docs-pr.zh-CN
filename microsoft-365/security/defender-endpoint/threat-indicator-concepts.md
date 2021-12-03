---
title: 了解 Microsoft Defender for Endpoint 中的威胁情报概念
description: 为组织创建自定义威胁警报并了解 Microsoft Defender for Endpoint 中威胁智能的概念
keywords: 威胁情报， 警报定义， 泄露指示器， ioc
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 440f788c4adb757013611bb05621b4eb4f4e9715
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61302442"
---
# <a name="understand-threat-intelligence-concepts"></a>了解威胁智能概念

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-threatindicator-abovefoldlink)。

高级网络安全攻击由多个复杂的恶意事件、属性和上下文信息组成。 确定和确定哪些活动符合可疑条件可能是一项极具挑战性的任务。 了解特定于你的行业的已知属性和异常活动是了解何时将观察到的行为称为可疑行为的基础。

通过Microsoft 365 Defender，你可以创建自定义威胁警报，以帮助跟踪组织中可能的攻击活动。 你可以标记可疑事件以将线索拼接在一起，并可能停止攻击链。 这些自定义威胁警报将仅出现在你的组织中，并标记你设置为跟踪的事件。

创建自定义威胁警报之前，必须了解警报定义和泄露指示器背后的概念 (ICS) 它们之间的关系。

## <a name="alert-definitions"></a>警报定义
警报定义是上下文属性，可用于共同识别有关可能的网络安全攻击的早期线索。 这些指示器通常是攻击者为成功实现攻击目标而执行的活动、特征和操作的组合。 监视这些属性组合对于在达到攻击者的目标之前获取攻击点并可能干扰事件链至关重要。

## <a name="indicators-of-compromise-ioc"></a>IOC (泄露) 
IIC 是单独已知的恶意事件，指示网络或设备已被破坏。 与警报定义不同，这些指示器被视为泄露的证据。 通常，在攻击已发生且达到目标（例如，攻击发生）后，它们经常看到。 在取证调查期间，跟踪 IIC 也很重要。 尽管它可能无法干预攻击链，但收集这些指示器对于为可能的未来攻击创建更好的防护非常有用。

## <a name="relationship-between-alert-definitions-and-iocs"></a>警报定义和 ICS 之间的关系
在 Microsoft 365 Defender 和 Microsoft Defender for Endpoint 的上下文中，警报定义是 IOC 的容器并定义警报，包括为特定 IOC 匹配而触发的元数据。 各种元数据作为警报定义的一部分提供。 诸如攻击的警报定义名称、严重性和说明等元数据以及其他选项一起提供。

每个 IOC 都基于其类型、值和操作定义具体的检测逻辑，确定其匹配方法。 它绑定到一个特定的警报定义，该定义定义检测如何在控制台上显示为Microsoft 365 Defender警报。

下面是 IOC 的示例：
- 类型：Sha1
- 值：92cfceb39d57d914ed8b14d0e37643de0797ae56
- 操作：等于

IIC 与警报定义具有多对一关系，因此警报定义可以具有许多与其对应的 IPC。


## <a name="related-topics"></a>相关主题
- [管理指示器](manage-indicators.md)
