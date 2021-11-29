---
title: 在 Linux 上配置并验证 Microsoft Defender for Endpoint 的排除项
description: 在 Linux 上提供并验证 Microsoft Defender for Endpoint 的排除项。 可以针对文件、文件夹和进程设置排除项。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 排除， 扫描， 防病毒
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
ms.openlocfilehash: b86cad016af0f7819d69f0156498336652e6292d
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/29/2021
ms.locfileid: "61218102"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a>在 Linux 上配置并验证 Microsoft Defender for Endpoint 的排除项

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

本文提供有关如何定义适用于按需扫描以及实时保护和监视的排除项的信息。

> [!IMPORTANT]
> 本文中介绍的排除项不适用于 Linux 上的其他 Defender for Endpoint 功能，包括终结点检测和响应 (EDR) 。 使用本文中介绍的方法排除的文件仍可以触发EDR检测。

你可以从 Linux 扫描上的 Defender for Endpoint 中排除某些文件、文件夹、进程和进程打开的文件。

排除项可用于避免对组织唯一或自定义的文件或软件进行错误检测。 它们还可用于缓解 Linux 上的 Defender for Endpoint 导致的性能问题。

> [!WARNING]
> 定义排除项会降低 Linux 上 Defender for Endpoint 所提供的保护。 您应始终评估与实施排除项相关的风险，并且只应排除您确信不是恶意的文件。

## <a name="supported-exclusion-types"></a>支持的排除类型

下表显示了 Linux 上的 Defender for Endpoint 支持的排除类型。

排除|定义|示例
---|---|---
文件扩展名|扩展名位于设备上任意位置的所有文件|`.test`
文件|由完整路径标识的特定文件|`/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
Folder|指定文件夹下的所有 (以递归) |`/var/log/`<br/>`/var/*/`
流程|由 (的完整路径或文件名指定的特定) 及其打开的所有文件|`/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> 上述路径必须是硬链接，而不是符号链接，才能成功排除。 可以通过运行 来检查路径是否为符号链接 `file <path-name>` 。

文件、文件夹和进程排除项支持以下通配符：

通配符|说明|示例|匹配|不匹配
---|---|---|---|---
\*|匹配任意数目的任何字符，包括无 (请注意，当在路径内使用此通配符时，它将仅替换一个) |`/var/\*/\*.log`|`/var/log/system.log`|`/var/log/nested/system.log`
?|匹配任何单个字符|`file?.log`|`file1.log`<br/>`file2.log`|`file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a>如何配置排除项列表

### <a name="from-the-management-console"></a>从管理控制台

若要详细了解如何配置来自部署、Ansible 或其他管理控制台的排除项，请参阅在 Linux 上设置 [Defender for Endpoint 的首选项](linux-preferences.md)。

### <a name="from-the-command-line"></a>从命令行

运行以下命令以查看用于管理排除项的可用开关：

```bash
mdatp exclusion
```

> [!TIP]
> 使用通配符配置排除项时，使用双引号将参数括起来以防止出现 globbing。

示例：

- 为文件扩展名添加排除项：

    ```bash
    mdatp exclusion extension add --name .txt
    ```

    ```Output
    Extension exclusion configured successfully
    ```

- 为文件添加排除项：

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```

    ```Output
    File exclusion configured successfully
    ```

- 为文件夹添加排除项：

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```

    ```Output
    Folder exclusion configured successfully
    ```

- 添加第二个文件夹的排除项：

    ```bash
    mdatp exclusion folder add --path /var/log/
    mdatp exclusion folder add --path /other/folder
    ```

    ```Output
    Folder exclusion configured successfully
    ```

- 为包含通配符的文件夹添加排除项：

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > 这将仅排除 */var/* 下一级的路径，但不包括嵌套较深的文件夹;例如 *，/var/this-subfolder/but-not-this-subfolder*。

    ```bash
    mdatp exclusion folder add --path "/var/"
    ```

    > [!NOTE]
    > 这将排除其父级为 */var/* 的所有路径;例如 *，/var/this-subfolder/and-this-subfolder-as-well*。

    ```Output
    Folder exclusion configured successfully
    ```

- 为进程添加排除项：

    ```bash
    mdatp exclusion process add --name cat
    ```

    ```Output
    Process exclusion configured successfully
    ```

- 为第二个进程添加排除项：

    ```bash
    mdatp exclusion process add --name cat
    mdatp exclusion process add --name dog
    ```

    ```Output
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>使用 EICAR 测试文件验证排除列表

可以使用 下载测试文件来验证排除列表 `curl` 是否正常工作。

在下面的 Bash 代码段中， `test.txt` 将 替换为符合排除规则的文件。 例如，如果已排除扩展 `.testing` ，请将 替换为 `test.txt` `test.testing` 。 如果要测试路径，请确保在此路径内运行命令。

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

如果 Linux 上的 Defender for Endpoint 报告恶意软件，则规则无法工作。 如果没有恶意软件报告，并且下载的文件存在，则排除将正常工作。 你可以打开文件以确认内容与 EICAR 测试文件网站上 [介绍的内容相同](http://2016.eicar.org/86-0-Intended-use.html)。

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
