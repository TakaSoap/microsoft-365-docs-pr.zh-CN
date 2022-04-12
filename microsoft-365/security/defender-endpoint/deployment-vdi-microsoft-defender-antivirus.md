---
title: Microsoft Defender 防病毒虚拟桌面基础结构部署指南
description: 了解如何在虚拟桌面环境中部署Microsoft Defender 防病毒，以便在保护与性能之间取得最佳平衡。
keywords: vdi， hyper-v， vm， 虚拟机， windows defender， 防病毒， av， 虚拟桌面， rds， 远程桌面
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 03/18/2022
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 3ef53a6e3cdbd578475b90b198359411a4102859
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789307"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a>虚拟桌面基础结构 （VDI） 环境中 Microsoft Defender 防病毒软件的部署指南

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

除了标准的本地或硬件配置外，还可以在远程桌面 (RDS) 或非永久性虚拟桌面基础结构 (VDI) 环境中使用Microsoft Defender 防病毒。

有关Microsoft 远程桌面服务和 VDI 支持的详细信息，请参阅 [Azure 虚拟桌面文档](/azure/virtual-desktop)。

有关基于 Azure 的虚拟机，请参阅[Microsoft Defender for Cloud中安装Endpoint Protection](/azure/security-center/security-center-install-endpoint-protection)。

为了轻松地将更新部署到 VDI 中运行的 VM，我们缩短了本指南，重点介绍如何快速轻松地在计算机上获取更新。 不再需要定期创建和密封黄金映像，因为更新将扩展到主机服务器上的组件位，然后在启用时直接下载到 VM。

本指南介绍如何配置 VM 以获得最佳的保护和性能，包括如何：

- [为安全智能更新设置专用 VDI 文件共享](#set-up-a-dedicated-vdi-file-share)
- [随机化计划的扫描](#randomize-scheduled-scans)
- [使用快速扫描](#use-quick-scans)
- [阻止通知](#prevent-notifications)
- [禁用每次更新后发生的扫描](#disable-scans-after-an-update)
- [扫描已脱机一段时间的过期计算机或计算机](#scan-vms-that-have-been-offline)
- [应用排除项](#exclusions)

还可以下载[虚拟桌面基础结构上的白皮书Microsoft Defender 防病毒](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf)，其中介绍了新的共享安全智能更新功能，以及性能测试和有关如何在自己的 VDI 上测试防病毒性能的指南。

> [!NOTE]
> 位于 demo.wd.microsoft.com 处的 Defender for Endpoint 演示网站已弃用，并将在未来删除。

> [!IMPORTANT]
> 尽管 VDI 可以托管在Windows Server 2012或Windows Server 2016上，但虚拟机 (VM) 应至少运行 1607 Windows 10，因为早期版本的 Windows 中无法使用保护技术和功能。
>
> Microsoft Defender AV 在 Windows 10 预览体验成员预览版、内部版本 18323 (和更高版本) 中对虚拟机的运行方式进行了性能和功能改进。 我们将在本指南中确定是否需要使用预览体验成员预览版版本;如果未指定，则最佳保护和性能所需的最低版本Windows 10 1607。

## <a name="set-up-a-dedicated-vdi-file-share"></a>设置专用 VDI 文件共享

在 Windows 10 版本 1903 中，我们引入了共享安全智能功能，该功能将下载的安全智能更新的解包卸载到主机上，从而在单个计算机上保存以前的 CPU、磁盘和内存资源。 此功能已回传，现在适用于 Windows 10 版本 1703 及更高版本。 可以使用组策略或 PowerShell 设置此功能。

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a>使用组策略启用共享安全智能功能：

1. 在组策略管理计算机上，打开组策略管理控制台，右键单击要配置的组策略对象，然后单击 **“编辑**”。

2. 在 **组策略管理编辑器** 中转到 **计算机配置**。

3. 单击 **“管理模板**”。

4. 将树展开到安全 **智能更新****Microsoft Defender 防病毒Windows** \> **组件**\>。

5. 双击 **“为 VDI 客户端定义安全智能位置**”，然后将选项设置为 **“已启用**”。 会自动显示字段。

6. 输入 `\\<sharedlocation\>\wdav-update` (以获取此值的帮助，请参阅 [下载和解包](#download-and-unpackage-the-latest-updates)) 。

7. 单击“确定”。

8. 将 GPO 部署到要测试的 VM。

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a>使用 PowerShell 启用共享安全智能功能

使用以下 cmdlet 启用该功能。 然后需要推送此功能，因为通常会将基于 PowerShell 的配置策略推送到 VM 上：

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

有关内容，请参阅 [“下载和解包](#download-and-unpackage-the-latest-updates) ”部分 \<shared location\> 。

## <a name="download-and-unpackage-the-latest-updates"></a>下载并解压缩最新更新

现在，可以开始下载和安装新更新。 我们为你创建了下面的示例 PowerShell 脚本。 此脚本是下载新更新并为 VM 做好准备的最简单方法。 然后，应使用计划的任务 (将脚本设置为在某个时间在管理计算机上运行，或者，如果熟悉如何在 Azure、Intune 或 SCCM 中使用 PowerShell 脚本，则还可以) 使用这些脚本。

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd /d $vdmpath & mpam-fe.exe /x"
```

可以将计划任务设置为每天运行一次，以便每当下载并解压缩包时，VM 都会收到新的更新。
建议从每天一次开始，但应尝试增加或降低频率以了解影响。

安全智能包通常每三到四小时发布一次。 不建议设置小于 4 小时的频率，因为它会增加管理计算机上的网络开销，没有任何好处。

还可以设置单个服务器或计算机，以按间隔代表 VM 提取更新，并将其放在文件共享中供使用。
当设备具有共享和 NTFS 权限以对共享进行读取访问，以便它们可以获取更新时，这是可能的。

为此:
 1. 创建 SMB/CIFS 文件共享。 
 
 2. 使用以下示例创建具有以下共享权限的文件共享。

    ```PowerShell
    PS c:\> Get-SmbShareAccess -Name mdatp$

    Name   ScopeName AccountName AccessControlType AccessRight
    ----   --------- ----------- ----------------- -----------
    mdatp$ *         Everyone    Allow             Read
    ```
   
    > [!NOTE]
    > 为经过身份验证的用户添加 NTFS 权限 **：读取：**。 

    对于此示例，文件共享为：

    \\\fileserver.fqdn\mdatp$\wdav-update

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a>设置计划任务以运行 PowerShell 脚本

1. 在管理计算机上，打开"开始"菜单并键入 **任务计划程序**。 打开它，然后在侧面板上选择 **“创建任务...** ”。

2. 输入名称作为 **安全智能解包程序**。 转到 **“触发器”** 选项卡。选择 **“新建...** \>**每天**，然后选择 **“确定**”。

3. 转到 **“操作”** 选项卡。选择 **“新建...** 在 **“程序/脚本**”字段中输入 **PowerShell**。 在 **“添加参数**”字段中输入`-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1`。 选择“确定”。

4. 如果需要，可以选择配置其他设置。

5. 选择 **“确定** ”以保存计划的任务。

可以通过右键单击任务并单击“ **运行**”手动启动更新。

### <a name="download-and-unpackage-manually"></a>手动下载和解包

如果希望手动执行所有操作，下面是复制脚本行为所要执行的操作：

1. 在调用 `wdav_update` 以存储智能更新的系统根上创建一个新文件夹，例如，创建文件夹 `c:\wdav_update`。

2. 在具有 GUID 名称 *的wdav_update* 下创建子文件夹，例如 `{00000000-0000-0000-0000-000000000000}`

   下面是一个示例： `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`

   > [!NOTE]
   > 在脚本中，我们将其设置为 GUID 的最后 12 位数字是下载文件的年、月、日和时间，以便每次创建一个新文件夹。 可以更改此项，以便每次将文件下载到同一个文件夹。

3. 从 [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  GUID 文件夹下载安全智能包。 该文件应命名 `mpam-fe.exe`。

4. 打开 cmd 提示窗口并导航到创建的 GUID 文件夹。 例如`mpam-fe.exe /X`，使用 **/X** 提取命令提取文件。

   > [!NOTE]
   > 每当使用提取的更新包创建新的 GUID 文件夹，或者每当使用新的提取包更新现有文件夹时，VM 都会选取更新后的包。

## <a name="randomize-scheduled-scans"></a>随机化计划的扫描

除了 [实时保护和扫描](configure-real-time-protection-microsoft-defender-antivirus.md)之外，还运行计划扫描。

扫描本身的开始时间仍基于计划扫描策略 (**ScheduleDay**、 **ScheduleTime** 和 **ScheduleQuickScanTime**) 。 随机化将导致Microsoft Defender 防病毒在计划扫描时间集中的四小时内对每台计算机启动扫描。

有关可用于计划扫描的其他配置选项，请参阅 [计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 。

## <a name="use-quick-scans"></a>使用快速扫描

可以指定应在计划扫描期间执行的扫描类型。 快速扫描是首选方法，因为它们旨在查找恶意软件需要驻留的所有位置才能处于活动状态。 以下过程介绍如何使用组策略设置快速扫描。

1. 在组策略编辑器\>中，转到管理 **模板****Windows组件** \> **Microsoft Defender 防病毒** \> **扫描**。

2. 选择 **“指定要用于计划扫描的扫描类型** ”，然后编辑策略设置。

3. 将策略设置为 **“已启用**”，然后在 **“选项**”下选择  **“快速扫描**”。

4. 选择“**确定**”。

5. 如通常一样部署组策略对象。

## <a name="prevent-notifications"></a>阻止通知

有时，可能会向多个会话发送或保留Microsoft Defender 防病毒通知。 为了最大程度地减少此问题，可以锁定Microsoft Defender 防病毒用户界面。 以下过程介绍如何使用组策略取消通知。

1. 在组策略编辑器中，转到客户端 **接口****Microsoft Defender 防病毒Windows** \> **组件**\>。

2. 选择 **“取消所有通知** ”，然后编辑策略设置。

3. 将策略设置为 **“已启用**”，然后选择 **“确定**”。

4. 如通常一样部署组策略对象。

禁止通知可防止在执行扫描或执行修正操作时Windows 10 Microsoft Defender 防病毒通知显示在操作中心。 但是，在检测到并停止攻击时，安全运营团队将看到扫描结果;警报（如“初始访问警报”）会触发并显示在[Microsoft 365 Defender门户](/microsoft-365/security/defender/microsoft-365-defender)中。

> [!TIP]
> 若要在Windows 10或Windows 11上打开操作中心，请执行以下步骤之一：
>
> - 在任务栏的右端，选择“操作中心”图标。
> - 按Windows徽标键按钮 + A。
> - 在触摸屏设备上，从屏幕右边缘轻扫。

## <a name="disable-scans-after-an-update"></a>在更新后禁用扫描

在更新后禁用扫描可防止在收到更新后进行扫描。 如果还运行了快速扫描，则可以在创建基础映像时应用此设置。 这样，就可以防止新更新的 VM 再次执行扫描 (因为在创建基础映像) 时已经对其进行了扫描。

> [!IMPORTANT]
> 更新后运行扫描将有助于确保 VM 受到最新的安全智能更新的保护。 禁用此选项将降低 VM 的保护级别，并且仅在首次创建或部署基础映像时才应使用。

1. 在组策略编辑器中，转到安全 **智能更新****Microsoft Defender 防病毒Windows** \> **组件**\>。

2. 选择 **在安全智能更新后启用扫描** ，然后编辑策略设置。

3. 将策略设置为 **“已禁用**”。

4. 选择“**确定**”。

5. 如通常一样部署组策略对象。

此策略可防止扫描在更新后立即运行。

## <a name="scan-vms-that-have-been-offline"></a>扫描已脱机的 VM

1. 在组策略编辑器中，转到 **Windows组件** \> **Microsoft Defender 防病毒** \> **扫描**。

2. 选择 **“打开追赶快速扫描** ”，然后编辑策略设置。

3. 将策略设置为 **“已启用**”。

4. 选择“确定”。

5. 像平时一样部署组策略对象。

如果 VM 错过了两次或更多次连续计划的扫描，则此策略强制执行扫描。

## <a name="enable-headless-ui-mode"></a>启用无头 UI 模式

1. 在组策略编辑器中，转到客户端 **接口****Microsoft Defender 防病毒Windows** \> **组件**\>。

2. 选择 **“启用无头 UI”模式** 并编辑策略。

3. 将策略设置为 **“已启用**”。

4. 单击“确定”。

5. 像平时一样部署组策略对象。

此策略隐藏组织中最终用户的整个Microsoft Defender 防病毒用户界面。

## <a name="exclusions"></a>排除项

可以根据需要添加、删除或自定义排除项。

有关详细信息，请参阅[在Windows服务器上配置Microsoft Defender 防病毒排除项](configure-exclusions-microsoft-defender-antivirus.md)。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="additional-resources"></a>其他资源

- [技术Community博客：为非持久性 VDI 计算机配置Microsoft Defender 防病毒](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [远程桌面服务和 VDI 上的 TechNet 论坛](https://social.technet.microsoft.com/Forums/windowsserver/home?forum=winserverTS)
- [SignatureDownloadCustomTask PowerShell 脚本](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)
