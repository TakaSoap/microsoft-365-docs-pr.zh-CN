---
title: 在 Microsoft Defender for Endpoint 中调查使用实时响应的设备上的实体
description: 使用安全的远程 Shell 连接访问设备，以执行调查工作，并实时对设备执行即时响应操作。
keywords: 远程， shell， 连接， 实时， 响应， 实时， 命令， 脚本， 修正， 搜寻， 导出， 日志， 拖放， 下载， 文件，
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
ms.openlocfilehash: 8987c5642ea48e4c7887735cc0fce0e5bfccc119
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64470386"
---
# <a name="investigate-entities-on-devices-using-live-response"></a>使用实时响应调查设备上的实体

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

实时响应使安全运营团队能够即时访问 (也称为计算机) 使用远程 shell 连接。 这让你能够执行深入调查工作，并立即采取响应操作，以实时迅速包含识别的威胁。

实时响应旨在增强调查，使安全运营团队能够收集取证数据、运行脚本、发送可疑实体进行分析、修正威胁并主动搜寻新出现的威胁。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

使用实时响应，分析员可以执行以下所有任务：

- 运行基本和高级命令以在设备上执行调查工作。
- 下载恶意软件示例和 PowerShell 脚本结果等文件。
- 在后台下载文件 (新建！) 。
- Upload PowerShell 脚本或可执行文件到库，然后从租户级别在设备上运行它。
- 执行或撤消修正操作。

## <a name="before-you-begin"></a>准备工作

在设备上启动会话之前，请确保满足以下要求：

- **验证是否正在运行受支持的** Windows。

  设备必须运行以下版本的设备之一Windows

  - **Windows 10 & 11**
    - [版本 1909](/windows/whats-new/whats-new-windows-10-version-1909) 或更高版本
    - [版本 1903](/windows/whats-new/whats-new-windows-10-version-1903) [和 KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384)
    - [版本 1809 (RS 5) ](/windows/whats-new/whats-new-windows-10-version-1809) [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)
    - [版本 1803 (RS 4) ](/windows/whats-new/whats-new-windows-10-version-1803) [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)
    - [版本 1709 (RS 3) ](/windows/whats-new/whats-new-windows-10-version-1709) [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)

  - **macOS** - 仅适用于公共预览版，最低要求版本：101.43.84 
  
   > [!NOTE]
   > 目前仅支持基于 Intel 的 macOS 系统。
    

  - **Linux** - 仅适用于公共预览版，最低要求版本：101.45.13 
    
  - **Windows Server 2012 R2** - 具有 [KB5005292](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac)
  
  - **Windows Server 2016** - 使用 [KB5005292](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac)

  - **Windows Server 2019**
    - 版本 1903 或 ([KB4515384](https://support.microsoft.com/help/4515384/windows-10-update-kb4515384) 版本) 更高版本
    - 版本 1809 ([KB4537818) ](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)
    
  - **Windows Server 2022**

       

- **从高级设置页面启用实时响应**。

  你需要在"高级功能设置"页中启用 [实时响应](advanced-features.md) 功能。

  > [!NOTE]
  > 只有具有管理安全性或全局管理员角色的用户才能编辑这些设置。
  > 
  > 在启用实时响应之前， [必须在高级功能](advanced-features.md) 设置中启用自动调查。

- **从高级设置页面启用服务器** 实时响应 (推荐) 。

  > [!NOTE]
  > 只有具有管理安全性或全局管理员角色的用户才能编辑这些设置。

- **确保设备具有分配给它的自动化修正级别**。

  你至少需要启用给定设备组的最低修正级别。 否则，将无法与该组的成员建立实时响应会话。

  您将收到以下错误：

  :::image type="content" source="images/live-response-error.png" alt-text="错误消息" lightbox="images/live-response-error.png":::

- **启用实时响应未签名脚本执行** (可选) 。

  >[!IMPORTANT]
  >签名验证仅适用于 PowerShell 脚本。 

  > [!WARNING]
  > 允许使用未签名脚本可能会增加你面临的威胁。

  不建议运行未签名的脚本，因为它会增加你面临的威胁。 但是，如果必须使用这些功能，则需要在"高级功能设置"页 [中启用设置](advanced-features.md) 。

- **确保您具有适当的权限**。

  只有已预配了相应权限的用户才能启动会话。 有关角色分配详细信息，请参阅 [创建和管理角色](user-roles.md)。

  > [!IMPORTANT]
  > 将文件上载到库的选项仅适用于具有"管理安全性设置"权限的用户。
  > 对于仅具有委派权限的用户，按钮显示为灰色。

  根据已授予的角色，可以运行基本或高级实时响应命令。 用户权限由 RBAC 自定义角色控制。

## <a name="live-response-dashboard-overview"></a>实时响应仪表板概述

在设备上启动实时响应会话时，将打开仪表板。 仪表板提供有关会话的信息，如下所示：

- Who创建了会话
- 会话开始时间
- 会话的持续时间

通过仪表板还可以访问：

- 断开会话连接
- Upload文件到库
- 命令控制台
- 命令日志

## <a name="initiate-a-live-response-session-on-a-device"></a>在设备上启动实时响应会话

1. 登录到 Microsoft 365 Defender 门户。

2. 导航到 **终结点>设备清单** ，然后选择要调查的设备。 设备页面将打开。

3. 通过选择"启动实时响应会话 **"启动实时响应会话**。 将显示命令控制台。 在会话连接到设备时等待。

4. 使用内置命令执行调查工作。 有关详细信息，请参阅实时 [响应命令](#live-response-commands)。

5. 完成调查后，选择"断开连接 **会话"**，然后选择"确认 **"**。

## <a name="live-response-commands"></a>实时响应命令

根据已授予的角色，可以运行基本或高级实时响应命令。 用户权限由 RBAC 自定义角色控制。 有关角色分配详细信息，请参阅 [创建和管理角色](user-roles.md)。

> [!NOTE]
> 实时响应是基于云的交互式 Shell，因此，特定命令体验在响应时间上可能会有所不同，具体取决于最终用户和目标设备之间的网络质量和系统负载。

### <a name="basic-commands"></a>基本命令

以下命令适用于被授予运行基本实时响应 **命令的能力的用户** 角色。 有关角色分配详细信息，请参阅 [创建和管理角色](user-roles.md)。

<br>

****
| 命令  | 说明  | Windows 和 Windows Server  | macOS  | Linux  |
|---|---|---|---|---|
| cd  | 更改当前目录。  | Y  | Y  | Y  |
| cls  | 清除控制台屏幕。  | Y  | Y  | Y  |
| connect  | 启动到设备的实时响应会话。  | Y  | Y  | Y  |
| connections  | 显示所有活动连接。  | Y  | N  | N  |
| dir  | 显示目录中的文件和子目录的列表。  | Y  | Y  | Y  |
| drivers  | 显示设备上安装的所有驱动程序。  | Y  | N  | N  |
| fg `<command ID>`  | 将指定的作业放在前台的前台，使其成为当前作业。  注意：fg 从作业（而不是 PID）接受一个可用的"命令 ID"  | Y  | Y  | Y  |
| fileinfo  | 获取有关文件的信息。  | Y  | Y  | Y  |
| findfile  | 在设备上按给定名称查找文件。  | Y  | Y  | Y  |
| getfile <file_path>  | 下载文件。  | Y  | Y  | Y  |
| 帮助  | 提供实时响应命令的帮助信息。  | Y  | Y  | Y  |
| jobs  | 显示当前运行的作业及其 ID 和状态。  | Y  | Y  | Y  |
| 持久性  | 显示设备上所有已知的持久性方法。  | Y  | N  | N  |
| processes  | 显示设备上运行的所有进程。  | Y  | Y  | Y  |
| 注册表  | 显示注册表值。  | Y  | N  | N  |
| scheduledtasks  | 显示设备上的所有计划任务。  | Y  | N  | N  |
| 服务  | 显示设备上的所有服务。  | Y  | N  | N  |
| startupfolders  | 显示设备上启动文件夹中的所有已知文件。  | Y  | N  | N  |
| 状态  | 显示特定命令的状态和输出。  | Y  | N  | N  |
| trace  | 将终端的日志记录模式设置为调试。  | Y  | Y  | Y  |

### <a name="advanced-commands"></a>高级命令

以下命令适用于被授予运行高级实时响应 **命令权限的用户** 角色。 有关角色分配详细信息，请参阅 [创建和管理角色](user-roles.md)。

<br>

****

| 命令  | 说明  | Windows 和 Windows Server  | macOS  | Linux  |
|---|---|---|---|---|
| analyze  | 使用各种描述引擎分析实体以作出裁定。  | Y  | N  | N  |
| collect  | 从计算机收集取证包  | N  | Y  | Y  |
| isolate  | 断开设备与网络的连接，同时保留与 Defender for Endpoint 服务的连接  | N  | Y  | N  |
| release  | 解除设备网络隔离  | N  | Y  | N  |
| run  | 从设备的库中运行 PowerShell 脚本。  | Y  | Y  | Y  |
| 库  | 列出上载到实时响应库的文件。  | Y  | Y  | Y  |
| putfile  | 将库中的文件置于设备。 文件保存在工作文件夹中，在设备默认重启时将被删除。  | Y  | Y  | Y  |
| 修正  | 修正设备上的实体。 修正操作将因实体类型而异：File： delete Process： stop， delete image file Service： stop， delete image file Registry entry： delete Scheduled task： remove Startup folder item： delete file NOTE： This command has a prerequisite command. 可以将 -auto 命令与修正结合使用，以自动运行必备组件命令。  | Y  | Y  | Y  |
| scan | 运行防病毒扫描以帮助识别和修正恶意软件。 | N | Y | Y |
| undo  | 还原已修正的实体。  | Y  | Y  | Y  |


## <a name="use-live-response-commands"></a>使用实时响应命令

控制台中可以使用的命令遵循与命令类似的Windows[原则](/windows-server/administration/windows-commands/windows-commands#BKMK_c)。

高级命令提供了一组更可靠的操作，允许你执行更强大的操作，如下载和上载文件、在设备上运行脚本，以及对实体执行修正操作。

### <a name="get-a-file-from-the-device"></a>从设备获取文件

对于希望从正在调查的设备获取文件的情况，可以使用 命令 `getfile` 。 这允许你从设备保存文件以进一步调查。

> [!NOTE]
> 以下文件大小限制适用：
>
> - `getfile` 限制：3 GB
> - `fileinfo` 限制：30 GB
> - `library` 限制：250 MB

### <a name="download-a-file-in-the-background"></a>在后台下载文件

若要使安全运营团队继续调查受影响的设备，现在可以在后台下载文件。

- 若要在后台下载文件，在实时响应命令控制台中，键入 `download <file_path> &`。
- 如果你正在等待下载文件，可以使用 Ctrl + Z 将其移动到后台。
- 若要将文件下载引入前台，在实时响应命令控制台中，键入 `fg <command_id>`。

下面是一些示例：

<br>

****

|命令|功能|
|---|---|
|`getfile "C:\windows\some_file.exe" &`|开始在后台 *下载some_file.exe文件* 。|
|`fg 1234`|将命令 ID 为 *1234* 的下载返回到前台。|
|

### <a name="put-a-file-in-the-library"></a>将文件放入库中

实时响应具有一个库，您可以将文件放入其中。 该库存储 (脚本) 脚本库，这些文件可以在租户级别的实时响应会话中运行。

实时响应允许运行 PowerShell 脚本，但是必须先将文件放入库中，然后才能运行它们。

你可以拥有可以在启动实时响应会话的设备上运行的 PowerShell 脚本集合。

#### <a name="to-upload-a-file-in-the-library"></a>上载库中的文件

1. 单击 **Upload文件到库**"。

2. 单击 **"** 浏览"，然后选择文件。

3. 提供简要说明。

4. 指定您是否要覆盖同名的文件。

5. 如果需要，请了解脚本需要哪些参数，请选中"脚本参数"复选框。 在文本字段中，输入示例和说明。

6. 单击 **"确认"**。

7.  (可选) 若要验证文件已上载到库，请运行 `library` 命令。

### <a name="cancel-a-command"></a>取消命令

在会话期间，您可以随时按 Ctrl + C 取消命令。

> [!WARNING]
> 使用此快捷方式不会在代理端停止命令。 它将仅取消门户中的命令。 因此，更改操作（如"修正"）可能会继续，同时取消命令。

## <a name="run-a-script"></a>运行脚本

必须先将其上载到库中，然后才能运行 PowerShell/Bash 脚本。

将脚本上载到库后，使用 `run` 命令运行脚本。

如果计划在会话中使用未签名的 PowerShell 脚本，则需要启用"高级功能设置" [页中的](advanced-features.md) 设置。

> [!WARNING]
> 允许使用未签名脚本可能会增加你面临的威胁。

## <a name="apply-command-parameters"></a>应用命令参数

- 查看控制台帮助以了解命令参数。 若要了解单个命令，请运行：

  ```powershell
  help <command name>
  ```

- 将参数应用于命令时，请注意，参数基于固定顺序进行处理：

  ```powershell
  <command name> param1 param2
  ```

- 指定固定顺序之外的参数时，在提供值之前，使用连字符指定参数的名称：

  ```powershell
  <command name> -param2_name param2
  ```

- 在使用具有必备命令的命令时，可以使用标志：

  ```powershell
  <command name> -type file -id <file path> - auto
  ```

  或

  ```powershell
  remediate file <file path> - auto`
  ```

## <a name="supported-output-types"></a>支持的输出类型

实时响应支持表和 JSON 格式输出类型。 对于每个命令，都有一个默认输出行为。 可以使用以下命令修改首选输出格式的输出：

- `-output json`
- `-output table`

> [!NOTE]
> 由于空间有限，表格式中显示的字段较少。 若要在输出中查看更多详细信息，可以使用 JSON 输出命令显示更多详细信息。

## <a name="supported-output-pipes"></a>支持的输出管道

实时响应支持通过管道将输出传输至 CLI 和文件。 CLI 是默认输出行为。 可以使用以下命令将输出通过管道传输至文件：[command] > [filename].txt。

示例：

```console
processes > output.txt
```

## <a name="view-the-command-log"></a>查看命令日志

选择 **"命令日志** "选项卡以查看会话期间在设备上使用的命令。 每个命令都使用完整详细信息进行跟踪，例如：

- ID
- 命令行
- 期限
- 状态和输入或输出侧栏

## <a name="limitations"></a>限制

- 实时响应会话一次限制为 25 个实时响应会话。
- 实时响应会话非活动超时值为 30 分钟。
- 单个实时响应命令的时间限制为 10 分钟`getfile``findfile``run`，、 和 除外，其限制为 30 分钟。
- 用户可以启动最多 10 个并发会话。
- 设备一次只能在一个会话中。
- 以下文件大小限制适用：
  - `getfile` 限制：3 GB
  - `fileinfo` 限制：10 GB
  - `library` 限制：250 MB

## <a name="related-article"></a>相关文章

- [实时响应命令示例](live-response-command-examples.md)
