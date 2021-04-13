---
title: 使用 Microsoft Defender ATP for Linux 检测并阻止可能不需要的应用程序
description: 使用 Microsoft Defender ATP for Linux (并阻止 PUA) 可能不需要的应用程序。
keywords: microsoft， defender， atp， linux， pua， pus
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e7ac620896bad9adb73308223e28976e219d36d0
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687861"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-linux"></a>使用 Linux 上的 Microsoft Defender for Endpoint 检测并阻止可能不需要的应用程序

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

适用于 Linux 的 Defender (PUA) 保护功能中可能不需要的应用程序可以检测和阻止网络中终结点上的 PUA 文件。

这些应用程序不被视为病毒、恶意软件或其他类型的威胁，但可能会对终结点执行对性能或使用产生不利影响的操作。 PUA 还可以指信誉不佳的应用程序。

这些应用程序会增加网络受到恶意软件感染的风险，导致恶意软件感染更难识别，并且可能会浪费 IT 资源来清理应用程序。

## <a name="how-it-works"></a>运作方式

适用于 Linux 的 Defender for Endpoint 可以检测和报告 PUA 文件。 在阻止模式下配置时，PUA 文件将移动到隔离区。

在终结点上检测到 PUA 时，Linux 的 Defender for Endpoint 会记录威胁历史记录中的感染情况。 可以从 Microsoft Defender 安全中心门户或命令行工具可视化 `mdatp` 历史记录。 威胁名称将包含单词"Application"。

## <a name="configure-pua-protection"></a>配置 PUA 保护

可通过以下方法之一配置适用于 Linux 的 Defender 终结点中的 PUA 保护：

- **关闭**：PUA 保护已禁用。
- **审核**：PUA 文件在产品日志中报告，但不在 Microsoft Defender 安全中心中报告。 威胁历史记录中未存储任何感染记录，产品不采取措施。
- **阻止**：PUA 文件在产品日志和 Microsoft Defender 安全中心中报告。 感染的记录存储在威胁历史记录中，产品会采取措施。

>[!WARNING]
>默认情况下，PUA 保护在 **审核模式下配置** 。

你可以配置从命令行或管理控制台处理 PUA 文件的方式。

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>使用命令行工具配置 PUA 保护：

在终端中，执行以下命令以配置 PUA 保护：

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>使用管理控制台配置 PUA 保护：

在企业中，你可以配置管理控制台（如"小数"或"Ansible"）的 PUA 保护，这类似于配置其他产品设置的方式。 有关详细信息，请参阅设置适用于[](linux-preferences.md#threat-type-settings)Linux 的 Defender[终结点](linux-preferences.md)的首选项文章的威胁类型设置部分。

## <a name="related-articles"></a>相关文章

- [设置适用于 Linux 的 Defender 终结点的首选项](linux-preferences.md)
