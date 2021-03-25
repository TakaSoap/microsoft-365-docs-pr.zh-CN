---
title: 使用 Microsoft Defender ATP for Mac 检测并阻止可能不需要的应用程序
description: 使用 Microsoft Defender ATP for Mac (并阻止 PUA) 可能不需要的应用程序。
keywords: microsoft， defender， atp， mac， pua， pus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6e65e847403160d24eac04a553ca16a46314e33d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187417"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-mac"></a>使用 Microsoft Defender for Endpoint for Mac 检测并阻止可能不需要的应用程序

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


Microsoft Defender for Mac (PUA) 保护功能中可能不需要的应用程序可以检测和阻止网络中终结点上的 PUA 文件。

这些应用程序不被视为病毒、恶意软件或其他类型的威胁，但可能会对终结点执行对性能或使用产生不利影响的操作。 PUA 还可以指信誉不佳的应用程序。

这些应用程序会增加网络受到恶意软件感染的风险，导致恶意软件感染更难识别，并且可能会浪费 IT 资源来清理应用程序。

## <a name="how-it-works"></a>运作方式

适用于 Mac 的 Microsoft Defender for Endpoint 可以检测和报告 PUA 文件。 在阻止模式下配置时，PUA 文件将移动到隔离区。

在终结点上检测到 PUA 时，除非已禁用通知，否则 Microsoft Defender for Mac 终结点会向用户显示通知。 威胁名称将包含单词"Application"。

## <a name="configure-pua-protection"></a>配置 PUA 保护

可通过以下方法之一配置 Microsoft Defender for Endpoint for Mac 中的 PUA 保护：

- **关闭**：PUA 保护已禁用。
- **审核**：PUA 文件在产品日志中报告，但不在 Microsoft Defender 安全中心中报告。 不会向用户显示任何通知，产品不会采取任何操作。
- **阻止**：PUA 文件在产品日志和 Microsoft Defender 安全中心中报告。 用户会收到通知，产品会采取操作。

>[!WARNING]
>默认情况下，PUA 保护在 **审核模式下配置** 。

你可以配置从命令行或管理控制台处理 PUA 文件的方式。

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>使用命令行工具配置 PUA 保护：

在终端中，执行以下命令以配置 PUA 保护：

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>使用管理控制台配置 PUA 保护：

在你的企业中，你可以从管理控制台（如 JAMF 或 Intune）配置 PUA 保护，类似于配置其他产品设置的方式。 有关详细信息，请参阅设置适用于[](mac-preferences.md#threat-type-settings)Mac 的 Microsoft [Defender for Endpoint 的](mac-preferences.md)首选项主题中的威胁类型设置部分。

## <a name="related-topics"></a>相关主题

- [设置适用于 Mac 的 Microsoft Defender 终结点的首选项](mac-preferences.md)
