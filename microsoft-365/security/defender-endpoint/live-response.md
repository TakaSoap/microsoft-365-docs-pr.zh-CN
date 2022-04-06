---
title: 在Microsoft Defender for Endpoint中使用实时响应调查设备上的实体
description: 使用安全的远程 shell 连接访问设备，以执行调查工作，并实时对设备执行即时响应操作。
keywords: remote， shell， connection， live， response， 实时， 命令， 脚本， 修正， 搜寻， 导出， 日志， 删除， 下载， 文件，
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
ms.openlocfilehash: 5e5d2b2bd47ba30aaf152171605947bb9a627480
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666341"
---
# <a name="investigate-entities-on-devices-using-live-response"></a>使用实时响应调查设备上的实体

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

实时响应使安全操作团队可以即时访问设备 (也称为使用远程 shell 连接的计算机) 。 这使你能够执行深入的调查工作，并立即采取响应行动，以便实时包含已识别的威胁。

实时响应旨在通过使安全运营团队能够收集取证数据、运行脚本、发送可疑实体进行分析、修正威胁以及主动搜寻新出现的威胁来增强调查。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

使用实时响应，分析师可以执行以下所有任务：

- 运行基本和高级命令，在设备上执行调查工作。
- 下载文件，例如恶意软件示例和 PowerShell 脚本的结果。
- 下载后台文件 (新的！) 。
- Upload PowerShell 脚本或可执行文件到库，并从租户级别在设备上运行它。
- 执行或撤消修正操作。

## <a name="before-you-begin"></a>准备工作

在设备上启动会话之前，请确保满足以下要求：

- **验证是否正在运行受支持的Windows版本**。

  设备必须运行以下版本之一的Windows

  - **Windows 10 & 11**
    - [版本 1909](/windows/whats-new/whats-new-windows-10-version-1909) 或更高版本
    - [版本 1903](/windows/whats-new/whats-new-windows-10-version-1903) 与 [KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384)
    - 使用 [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818) 的[版本 1809 (RS 5) ](/windows/whats-new/whats-new-windows-10-version-1809)
    - [版本 1803 (RS 4) ](/windows/whats-new/whats-new-windows-10-version-1803) [与 KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)
    - [版本 1709 (RS 3) ](/windows/whats-new/whats-new-windows-10-version-1709) [与 KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)

  - **macOS** - 仅适用于公共预览版，最低必需版本：101.43.84

   > [!NOTE]
   > 目前仅支持基于 Intel 的 macOS 系统。

  - **Linux** - 仅适用于公共预览版，最低必需版本：101.45.13

  - **Windows Server 2012 R2** - [使用 KB5005292](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac)

  - **Windows Server 2016** - [使用 KB5005292](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac)

  - **Windows Server 2019**
    - 版本 1903 或 ([KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384)) 更高版本
    - 版本 1809 ([与 KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)) 

  - **Windows Server 2022**

- **从高级设置页启用实时响应**。

  需要在" [高级功能设置](advanced-features.md) "页中启用实时响应功能。

  > [!NOTE]
  > 只有具有管理安全性或全局管理员角色的用户才能编辑这些设置。
  >
  > 在启用实时响应之前，必须在 [高级功能设置](advanced-features.md) 中启用自动调查。

- **从高级设置页为服务器启用实时响应** (建议的) 。

  > [!NOTE]
  > 只有具有管理安全性或全局管理员角色的用户才能编辑这些设置。

- **确保设备分配了自动化修正级别**。

  至少需要为给定设备组启用最低修正级别。 否则，你将无法与该组的成员建立实时响应会话。

  你将收到以下错误：

  :::image type="content" source="images/live-response-error.png" alt-text="错误消息" lightbox="images/live-response-error.png":::

- **启用实时响应无符号脚本执行** (可选) 。

  >[!IMPORTANT]
  >签名验证仅适用于 PowerShell 脚本。

  > [!WARNING]
  > 允许使用无符号脚本可能会增加你面临的威胁。

  不建议运行无符号脚本，因为它可能会增加你对威胁的风险。 但是，如果必须使用它们，则需要在 ["高级功能设置](advanced-features.md) "页中启用设置。

- **确保拥有适当的权限**。

  只有已使用相应权限预配的用户才能启动会话。 有关角色分配的详细信息，请参阅 [创建和管理角色](user-roles.md)。

  > [!IMPORTANT]
  > 将文件上传到库的选项仅适用于具有"管理安全设置"权限的用户。
  > 对于仅具有委派权限的用户，该按钮会灰显。

  根据授予你的角色，可以运行基本或高级实时响应命令。 用户权限由 RBAC 自定义角色控制。

## <a name="live-response-dashboard-overview"></a>实时响应仪表板概述

在设备上启动实时响应会话时，会打开仪表板。 仪表板提供有关会话的信息，例如：

- Who创建会话
- 会话启动时
- 会话的持续时间

仪表板还允许你访问：

- 断开会话连接
- 将文件Upload到库
- 命令控制台
- 命令日志

## <a name="initiate-a-live-response-session-on-a-device"></a>在设备上启动实时响应会话

1. 登录到Microsoft 365 Defender门户。

2. 导航到 **>设备清单的终结点** ，并选择要调查的设备。 "设备"页随即打开。

3. 通过选择 **"启动实时响应"会话启动实时响应会话来启动实时响应会话**。 将显示命令控制台。 在会话连接到设备时等待。

4. 使用内置命令执行调查工作。 有关详细信息，请参阅 [Live 响应命令](#live-response-commands)。

5. 完成调查后，选择 **"断开连接"会话**，然后选择 **"确认**"。

## <a name="live-response-commands"></a>实时响应命令

根据授予你的角色，可以运行基本或高级实时响应命令。 用户权限由 RBAC 自定义角色控制。 有关角色分配的详细信息，请参阅 [创建和管理角色](user-roles.md)。

> [!NOTE]
> 实时响应是基于云的交互式 shell，因此，特定的命令体验在响应时间上可能会有所不同，具体取决于最终用户与目标设备之间的网络质量和系统负载。

### <a name="basic-commands"></a>基本命令

以下命令可用于授予运行 **基本** 实时响应命令的用户角色。 有关角色分配的详细信息，请参阅 [创建和管理角色](user-roles.md)。

| 命令  | 说明  | Windows和Windows服务器  | macOS  | Linux  |
|---|---|---|---|---|
| Cd  | 更改当前目录。  | Y  | Y  | Y  |
| Cls  | 清除控制台屏幕。  | Y  | Y  | Y  |
| connect  | 启动设备的实时响应会话。  | Y  | Y  | Y  |
| 连接  | 显示所有活动连接。  | Y  | N  | N  |
| 迪尔  | 显示目录中的文件和子目录的列表。  | Y  | Y  | Y  |
| 司机  | 显示设备上安装的所有驱动程序。  | Y  | N  | N  |
| 盖瑞 `<command ID>`  | 将指定的作业放在前景中，使其成为当前作业。  注意：fg 从作业（而不是 PID）获取可用的"命令 ID"  | Y  | Y  | Y  |
| fileinfo  | 获取有关文件的信息。  | Y  | Y  | Y  |
| findfile  | 在设备上按给定名称查找文件。  | Y  | Y  | Y  |
| getfile <file_path>  | 下载文件。  | Y  | Y  | Y  |
| 帮助  | 提供实时响应命令的帮助信息。  | Y  | Y  | Y  |
| jobs  | 显示当前正在运行的作业及其 ID 和状态。  | Y  | Y  | Y  |
| 坚持  | 显示设备上所有已知的持久性方法。  | Y  | N  | N  |
| processes  | 显示设备上运行的所有进程。  | Y  | Y  | Y  |
| 注册表  | 显示注册表值。  | Y  | N  | N  |
| scheduledtasks  | 显示设备上的所有计划任务。  | Y  | N  | N  |
| 服务  | 显示设备上的所有服务。  | Y  | N  | N  |
| startupfolders  | 显示设备上启动文件夹中的所有已知文件。  | Y  | N  | N  |
| 状态  | 显示特定命令的状态和输出。  | Y  | N  | N  |
| 跟踪  | 将终端的日志记录模式设置为调试。  | Y  | Y  | Y  |

### <a name="advanced-commands"></a>高级命令

以下命令可用于授予运行 **高级** 实时响应命令的用户角色。 有关角色分配的详细信息，请参阅 [创建和管理角色](user-roles.md)。

| 命令  | 说明  | Windows和Windows服务器  | macOS  | Linux  |
|---|---|---|---|---|
| 分析  | 使用各种有罪引擎分析实体以作出判决。  | Y  | N  | N  |
| 收集  | 从计算机收集取证包  | N  | Y  | Y  |
| 分离  | 在保留与 Defender for Endpoint 服务的连接的同时，断开设备与网络的连接  | N  | Y  | N  |
| 释放  | 从网络隔离释放设备  | N  | Y  | N  |
| 运行  | 从设备上的库运行 PowerShell 脚本。  | Y  | Y  | Y  |
| 图书馆  | 列出上传到实时响应库的文件。  | Y  | Y  | Y  |
| putfile  | 将文件从库放置到设备。 文件保存在工作文件夹中，并在设备默认重启时删除。  | Y  | Y  | Y  |
| remediate  | 修正设备上的实体。 修正操作将因实体类型而异：文件：删除过程：停止、删除映像文件服务：停止、删除映像文件注册表项：删除计划任务：删除启动文件夹项：删除文件说明：此命令具有先决条件命令。 可以结合使用 -auto 命令和修正来自动运行先决条件命令。  | Y  | Y  | Y  |
| 扫描 | 运行防病毒扫描以帮助识别和修正恶意软件。 | N | Y | Y |
| 撤消  | 还原已修正的实体。  | Y  | Y  | Y  |

## <a name="use-live-response-commands"></a>使用实时响应命令

可以在控制台中使用的命令遵循[与Windows命令](/windows-server/administration/windows-commands/windows-commands#BKMK_c)类似的原则。

高级命令提供了一组更可靠的操作，可用于执行更强大的操作，例如下载和上传文件、在设备上运行脚本，以及对实体执行修正操作。

### <a name="get-a-file-from-the-device"></a>从设备获取文件

对于想要从所调查设备获取文件的情况，可以使用该 `getfile` 命令。 这样便可以从设备保存文件以供进一步调查。

> [!NOTE]
> 以下文件大小限制适用：
>
> - `getfile` 限制：3 GB
> - `fileinfo` 限制：30 GB
> - `library` 限制：250 MB

### <a name="download-a-file-in-the-background"></a>在后台下载文件

若要使安全运营团队能够继续调查受影响的设备，现在可以在后台下载文件。

- 若要在后台下载文件，请在实时响应命令控制台中键入 `download <file_path> &`。
- 如果正在等待下载文件，可以使用 Ctrl + Z 将其移动到后台。
- 若要将文件下载带到前台，请在实时响应命令控制台中键入 `fg <command_id>`。

下面是一些示例：

<br>

****

|命令|功能|
|---|---|
|`getfile "C:\windows\some_file.exe" &`|开始在后台下载名为 *some_file.exe* 的文件。|
|`fg 1234`|将命令 ID *为 1234* 的下载返回到前台。|
|

### <a name="put-a-file-in-the-library"></a>在库中放置文件

实时响应有一个库，可将文件放入其中。 库存储文件 (，例如可在租户级别的实时响应会话中运行的脚本) 。

实时响应允许 PowerShell 脚本运行，但必须先将文件放入库中才能运行它们。

可以有一个 PowerShell 脚本集合，这些脚本可以在启动实时响应会话的设备上运行。

#### <a name="to-upload-a-file-in-the-library"></a>在库中上传文件

1. 单击 **Upload文件到库**。

2. 单击 **"浏览"** 并选择该文件。

3. 提供简要说明。

4. 指定是否要覆盖同名文件。

5. 如果想要，请知道脚本需要哪些参数，请选中脚本参数复选框。 在文本字段中，输入示例和说明。

6. 单击 **"确认**"。

7.  (可选) 若要验证文件是否已上传到库，请运行该 `library` 命令。

### <a name="cancel-a-command"></a>取消命令

在会话期间，随时可以通过按 CTRL + C 来取消命令。

> [!WARNING]
> 使用此快捷方式不会在代理端停止命令。 它只会取消门户中的命令。 因此，更改操作（如"修正"）可能会继续，同时取消该命令。

## <a name="run-a-script"></a>运行脚本

在运行 PowerShell/Bash 脚本之前，必须先将其上传到库。

将脚本上传到库后，使用该 `run` 命令运行脚本。

如果计划在会话中使用未签名的 PowerShell 脚本，则需要在 ["高级功能设置](advanced-features.md) "页中启用设置。

> [!WARNING]
> 允许使用无符号脚本可能会增加你面临的威胁。

## <a name="apply-command-parameters"></a>应用命令参数

- 查看控制台帮助以了解命令参数。 若要了解单个命令，请运行：

  ```powershell
  help <command name>
  ```

- 将参数应用于命令时，请注意，参数是按固定顺序处理的：

  ```powershell
  <command name> param1 param2
  ```

- 在指定固定顺序之外的参数时，请在提供值之前使用连字符指定参数的名称：

  ```powershell
  <command name> -param2_name param2
  ```

- 使用具有先决条件命令的命令时，可以使用标志：

  ```powershell
  <command name> -type file -id <file path> - auto
  ```

  或

  ```powershell
  remediate file <file path> - auto`
  ```

## <a name="supported-output-types"></a>支持的输出类型

实时响应支持表和 JSON 格式输出类型。 对于每个命令，都有一个默认的输出行为。 可以使用以下命令修改首选输出格式的输出：

- `-output json`
- `-output table`

> [!NOTE]
> 由于空间有限，以表格式显示的字段更少。 若要查看输出中的更多详细信息，可以使用 JSON 输出命令，以便显示更多详细信息。

## <a name="supported-output-pipes"></a>支持的输出管道

实时响应支持 CLI 和文件的输出管道。 CLI 是默认输出行为。 可以使用以下命令将输出传递给文件：[命令] > [filename].txt。

示例：

```console
processes > output.txt
```

## <a name="view-the-command-log"></a>查看命令日志

选择 **"命令日志** "选项卡可查看会话期间在设备上使用的命令。 每个命令都使用完整详细信息进行跟踪，例如：

- ID
- 命令行
- 期限
- 状态和输入或输出侧栏

## <a name="limitations"></a>限制

- 实时响应会话一次限制为 25 个实时响应会话。
- 实时响应会话非活动超时值为 30 分钟。
- 单个实时响应命令的时间限制为 10 分钟，但限制为 30 分钟的除外`getfile``findfile``run`。
- 用户最多可以启动 10 个并发会话。
- 设备一次只能在一个会话中。
- 以下文件大小限制适用：
  - `getfile` 限制：3 GB
  - `fileinfo` 限制：10 GB
  - `library` 限制：250 MB

## <a name="related-article"></a>相关文章

- [实时响应命令示例](live-response-command-examples.md)
