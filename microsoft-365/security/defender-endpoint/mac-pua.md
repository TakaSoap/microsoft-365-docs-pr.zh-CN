---
title: 使用 Mac 上的 Microsoft Defender for Endpoint 检测并阻止可能不需要的应用程序
description: 检测并阻止使用 macOS (Microsoft Defender for Endpoint) PUA 中可能不需要的应用程序。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， pua， pus
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f372835ebcdd64225f3eb3952dc6b227d1a70627
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60699181"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-macos"></a>使用 macOS 上的 Microsoft Defender for Endpoint 检测并阻止可能不需要的应用程序

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

macOS 上的 Microsoft Defender for Endpoint (PUA) 保护功能可能不需要的应用程序可以检测和阻止网络中终结点上的 PUA 文件。

这些应用程序不被视为病毒、恶意软件或其他类型的威胁，但可能会对终结点执行对性能或使用产生不利影响的操作。 PUA 还可以指信誉不佳的应用程序。

这些应用程序会增加网络受到恶意软件感染的风险，导致恶意软件感染更难识别，并且可能会浪费 IT 资源来清理应用程序。

## <a name="how-it-works"></a>运作方式

macOS 上的 Microsoft Defender for Endpoint 可以检测和报告 PUA 文件。 在阻止模式下配置时，PUA 文件将移动到隔离区。

在终结点上检测到 PUA 时，macOS 上的 Microsoft Defender for Endpoint 会向用户显示通知，除非已禁用通知。 威胁名称将包含单词"Application"。

## <a name="configure-pua-protection"></a>配置 PUA 保护

可通过以下方法之一配置 macOS 上适用于终结点的 Microsoft Defender 中的 PUA 保护：

- **关闭**：PUA 保护已禁用。
- **审核**：PUA 文件在产品日志中报告，但不在Microsoft 365 Defender中。 不会向用户显示任何通知，产品不会采取任何操作。
- **Block**：PUA 文件在产品日志和发布门户中Microsoft 365 Defender报告。 用户会收到通知，产品会采取操作。

> [!WARNING]
> 默认情况下，PUA 保护在 **审核模式下配置** 。

你可以配置从命令行或管理控制台处理 PUA 文件的方式。

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>使用命令行工具配置 PUA 保护：

在终端中，执行以下命令以配置 PUA 保护：

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>使用管理控制台配置 PUA 保护：

在企业中，你可以从管理控制台（如 JAMF 或 Intune）配置 PUA 保护，这类似于配置其他产品设置的方式。 有关详细信息，请参阅在 macOS 上设置 Microsoft Defender for Endpoint 的首选项主题[中的威胁类型](mac-preferences.md)设置部分。 [](mac-preferences.md#threat-type-settings)

## <a name="related-topics"></a>相关主题

- [在 macOS 上设置适用于终结点的 Microsoft Defender 的首选项](mac-preferences.md)
