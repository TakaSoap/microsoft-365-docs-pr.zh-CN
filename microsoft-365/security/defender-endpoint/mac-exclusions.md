---
title: 在 Mac 上配置和验证 Microsoft Defender for Endpoint 的排除项
description: 提供并验证 Mac 上的 Microsoft Defender for Endpoint 的排除项。 可以针对文件、文件夹和进程设置排除项。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 排除， 扫描， 防病毒
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
ms.openlocfilehash: d779ee570e310a2d8a07154d73fe353db8bce907
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207879"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-macos"></a>在 macOS 上配置和验证适用于终结点的 Microsoft Defender 的排除项

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

本文提供有关如何定义适用于按需扫描以及实时保护和监视的排除项的信息。

> [!IMPORTANT]
> 本文中介绍的排除项不适用于 Mac 上的其他 Defender for Endpoint 功能，包括终结点检测和响应 (EDR) 。 使用本文中所述的方法排除的文件仍可以触发EDR检测。

你可以从 Mac 上的 Defender for Endpoint 扫描中排除某些文件、文件夹、进程和进程打开的文件。

排除项可用于避免对组织唯一或自定义的文件或软件进行错误检测。 它们还可用于缓解由 Mac 上的 Defender for Endpoint 引起的性能问题。

> [!WARNING]
> 定义排除项会降低 Mac 上 Defender for Endpoint 所提供的保护。 您应始终评估与实施排除项相关的风险，并且只应排除您确信不是恶意的文件。

## <a name="supported-exclusion-types"></a>支持的排除类型

下表显示了 Mac 上的 Defender for Endpoint 支持的排除类型。

排除|定义|示例
---|---|---
文件扩展名|计算机上任意位置具有扩展名的所有文件|`.test`
文件|由完整路径标识的特定文件|`/var/log/test.log` <p> `/var/log/*.log` <p> `/var/log/install.?.log`
Folder|指定文件夹下的所有 (以递归) |`/var/log/` <p> `/var/*/`
流程|由 (的完整路径或文件名指定的特定进程) 及其打开的所有文件|`/bin/cat` <p> `cat` <p> `c?t`

文件、文件夹和进程排除项支持以下通配符：

通配符|说明|示例|匹配|不匹配
---|---|---|---|---
\*|匹配任意数目的任何字符，包括无字符 (请注意，当在路径内使用此通配符时，它将仅替换一个) |`/var/*/*.log`|`/var/log/system.log`|`/var/log/nested/system.log`
?|匹配任何单个字符|`file?.log`|`file1.log` <p> `file2.log`|`file123.log`

> [!NOTE]
> 产品在评估排除项时尝试解析固定链接。 当排除项包含通配符或目标文件 (卷上不存在时，) `Data` 解析不起作用。

## <a name="how-to-configure-the-list-of-exclusions"></a>如何配置排除项列表

### <a name="from-the-management-console"></a>从管理控制台

若要详细了解如何配置 JAMF、Intune 或其他管理控制台中的排除项，请参阅在 Mac 上设置 [Defender for Endpoint 的首选项](mac-preferences.md)。

### <a name="from-the-user-interface"></a>从用户界面

打开 Defender for Endpoint 应用程序并导航到"管理 **设置** \> **""** 添加或删除排除..."，如以下屏幕截图所示：

![管理排除项屏幕截图。](images/mdatp-37-exclusions.png)

选择要添加的排除类型并按照提示操作。

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>使用 EICAR 测试文件验证排除列表

可以使用 下载测试文件来验证排除列表 `curl` 是否正常工作。

在下面的 Bash 代码段中， `test.txt` 将 替换为符合排除规则的文件。 例如，如果已排除扩展 `.testing` ，请将 替换为 `test.txt` `test.testing` 。 如果要测试路径，请确保在此路径内运行命令。

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

如果 Mac 上的 Defender for Endpoint 报告恶意软件，则规则无法工作。 如果没有恶意软件报告，并且下载的文件存在，则排除将正常工作。 你可以打开文件以确认内容与 EICAR 测试文件网站上 [介绍的内容相同](http://2016.eicar.org/86-0-Intended-use.html)。

如果您无法访问 Internet，您可以创建自己的 EICAR 测试文件。 使用下面的 Bash 命令将 EICAR 字符串写入新的文本文件：

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

还可以将字符串复制到空白文本文件中，并尝试使用文件名或试图排除的文件夹中保存它。

## <a name="allow-threats"></a>允许威胁

除了将某些内容排除在扫描之外，还可以将产品配置为不检测某些威胁 (由威胁名称标识) 。 使用此功能时应谨慎，因为它可能会使设备处于未保护状态。

若要将威胁名称添加到允许列表，请执行以下命令：

```bash
mdatp threat allowed add --name [threat-name]
```

可以使用以下命令获取与设备上检测关联的威胁名称：

```bash
mdatp threat list
```

例如，若要 (与 EICAR 检测关联的威胁) 添加到允许列表中，请执行 `EICAR-Test-File (not a virus)` 以下命令：

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
