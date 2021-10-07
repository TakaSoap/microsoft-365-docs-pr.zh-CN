---
title: 使用 Linux 上的 Microsoft Defender for Endpoint 检测并阻止可能不需要的应用程序
description: 在 Linux 上使用 Microsoft Defender for Endpoint (并阻止 PUA) 可能不需要的应用程序。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， pua， pus
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 73ddc6e4ec4c114a86c88c62287e15e7fa051175
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154790"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-linux"></a>使用 Linux 上的 Microsoft Defender for Endpoint 检测并阻止可能不需要的应用程序

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

Linux 上的 Defender for Endpoint (PUA) 保护功能可能不需要的应用程序可以检测和阻止网络中终结点上的 PUA 文件。

这些应用程序不被视为病毒、恶意软件或其他类型的威胁，但可能会对终结点执行对性能或使用产生不利影响的操作。 PUA 还可以指信誉不佳的应用程序。

这些应用程序会增加网络受到恶意软件感染的风险，导致恶意软件感染更难识别，并且可能会浪费 IT 资源来清理应用程序。

## <a name="how-it-works"></a>如何工作

Linux 上的 Defender for Endpoint 可以检测和报告 PUA 文件。 在阻止模式下配置时，PUA 文件将移动到隔离区。

在终结点上检测到 PUA 时，Linux 上的 Defender for Endpoint 会记录威胁历史记录中的感染情况。 可以从中心门户或命令行Microsoft 365 Defender可视化 `mdatp` 历史记录。 威胁名称将包含单词"Application"。

## <a name="configure-pua-protection"></a>配置 PUA 保护

可通过以下方法之一配置 Linux 上的 Defender for Endpoint 中的 PUA 保护：

- **关闭**：PUA 保护已禁用。
- **审核**：PUA 文件在产品日志中报告，但不在Microsoft 365 Defender。 威胁历史记录中未存储任何感染记录，产品不采取措施。
- **Block**：PUA 文件在产品日志中和产品日志中Microsoft 365 Defender。 感染的记录存储在威胁历史记录中，产品会采取措施。

> [!WARNING]
> 默认情况下，PUA 保护在 **审核模式下配置** 。

你可以配置从命令行或管理控制台处理 PUA 文件的方式。

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>使用命令行工具配置 PUA 保护：

在终端中，执行以下命令以配置 PUA 保护：

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>使用管理控制台配置 PUA 保护：

在企业中，你可以配置管理控制台（如"小数"或"Ansible"）的 PUA 保护，这类似于配置其他产品设置的方式。 有关详细信息，请参阅在 Linux[](linux-preferences.md#threat-type-settings)上设置 Defender [for Endpoint](linux-preferences.md)的首选项一文的威胁类型设置部分。

## <a name="related-articles"></a>相关文章

- [在 Linux 上设置 Defender for Endpoint 的首选项](linux-preferences.md)
