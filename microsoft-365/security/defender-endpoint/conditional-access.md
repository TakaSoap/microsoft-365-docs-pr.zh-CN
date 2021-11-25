---
title: 启用条件访问以更好地保护用户、设备和数据
description: 启用条件访问，以防止应用程序在认为存在风险且应用程序被确定为不兼容时运行。
keywords: 条件访问， 阻止应用程序， 安全级别， intune，
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8ee1b1542eb2e737da509ce12ad9c2a605a4ffa5
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2021
ms.locfileid: "61170503"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a>启用条件访问以更好地保护用户、设备和数据

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-conditionalaccess-abovefoldlink)。

条件访问是一项功能，它通过确保只有安全设备有权访问应用程序，来帮助你更好地保护用户和企业信息。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4byD1]

使用条件访问，可以基于设备的风险级别控制对企业信息的访问。 这有助于在使用受信任应用程序的受信任设备上保留受信任的用户。

可以通过强制执行策略来阻止应用程序运行，直到设备返回到兼容状态，来定义设备和应用程序可以运行和访问网络信息的安全条件。

Defender for Endpoint 中条件访问的实现基于 Intune Microsoft Intune (设备) 策略和条件Azure Active Directory (Azure AD) 策略。

合规性策略与条件访问一起用于仅允许满足一个或多个设备合规性策略规则的设备访问应用程序。

## <a name="understand-the-conditional-access-flow"></a>了解条件访问流

设置条件访问，以便当在设备上看到威胁时，将阻止对敏感内容的访问，直到该威胁得到修正。

该流程首先会发现设备具有较低、中等或高风险。 然后将这些风险确定发送到 Intune。

根据在 Intune 中配置策略方式，可以设置条件访问，以便满足某些条件时应用策略。

例如，可以将 Intune 配置为在高风险设备上应用条件访问。

在 Intune 中，设备合规性策略与条件Azure AD结合使用，以阻止对应用程序的访问。 同时，启动自动调查和修正过程。

 在进行自动调查和修正时，用户仍可以使用该设备，但在完全修复威胁之前，将阻止访问企业数据。

若要解决在设备上发现的风险，你需要将设备返回到兼容状态。 设备在未发现任何风险时将返回到兼容状态。

有三种方法可以解决风险：

1. 使用手动或自动修正。
2. 解决设备上的活动警报。 这将从设备中删除风险。
3. 你可以从活动策略中删除设备，因此条件访问不会应用到该设备。

手动修正需要 secops 管理员调查警报并解决在设备上看到的风险。 自动修正通过下一节"配置条件访问"中提供的配置 [设置进行配置](configure-conditional-access.md)。

通过手动或自动修正来消除风险时，设备将返回到兼容状态，并授予对应用程序的访问权限。

下面的示例事件序列说明了操作中的条件访问：

1. 用户打开恶意文件，并且 Defender for Endpoint 将设备标志为高风险。
2. 高风险评估将传递到 Intune。 同时，启动自动调查以修正已识别的威胁。 还可以执行手动修正来修正已识别的威胁。
3. 根据在 Intune 中创建的策略，设备被标记为不兼容。 然后，评估将Azure AD Intune 条件访问策略告知用户。 在Azure AD中，将应用相应的策略来阻止对应用程序的访问。
4. 已完成手动或自动调查和修正，并删除威胁。 Defender for Endpoint 发现设备上没有风险，Intune 评估设备是否合规。 Azure AD应用允许访问应用程序的策略。
5. 用户现在可以访问应用程序。

## <a name="related-topic"></a>相关主题

- [在 Microsoft Defender for Endpoint 中配置条件访问](configure-conditional-access.md)
