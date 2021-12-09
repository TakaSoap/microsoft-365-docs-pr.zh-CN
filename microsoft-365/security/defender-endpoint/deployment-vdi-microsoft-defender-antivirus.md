---
title: Microsoft Defender 防病毒虚拟桌面基础结构部署指南
description: 了解如何在虚拟Microsoft Defender 防病毒环境中部署应用程序，以在保护和性能之间实现最佳平衡。
keywords: vdi， hyper-v， vm， 虚拟机， windows defender， 防病毒， av， 虚拟桌面， rds， 远程桌面
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/08/2021
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 46eab67f459e763a212178d768f9a411aaf7adb7
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61372620"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a>虚拟桌面基础结构 （VDI） 环境中 Microsoft Defender 防病毒软件的部署指南

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

除了 Microsoft Defender 防病毒标准本地配置或硬件配置，您还可以在远程桌面 (RDS) 或 VDI) 环境中使用 () 。

有关 Azure Microsoft 远程桌面 和 VDI 支持的信息，请参阅[Azure 虚拟桌面文档](/azure/virtual-desktop)。

有关基于 Azure 的虚拟机，请参阅 Install [Endpoint Protection in Microsoft Defender for Cloud](/azure/security-center/security-center-install-endpoint-protection)。

通过轻松将更新部署到在 VDIs 中运行的 VM，我们缩短了本指南，侧重于如何快速轻松地获取计算机更新。 你不再需要定期创建和密封黄金映像，因为更新会扩展到主机服务器上组件位，然后在虚拟机打开时直接下载到虚拟机。

本指南介绍如何配置 VM 以实现最佳保护和性能，包括如何：

- [为安全智能更新设置专用的 VDI 文件共享](#set-up-a-dedicated-vdi-file-share)
- [随机化计划扫描](#randomize-scheduled-scans)
- [使用快速扫描](#use-quick-scans)
- [阻止通知](#prevent-notifications)
- [禁止每次更新后执行扫描](#disable-scans-after-an-update)
- [扫描过期的计算机或已脱机一段时间的计算机](#scan-vms-that-have-been-offline)
- [应用排除项](#exclusions)

还可以下载虚拟桌面Microsoft Defender 防病毒上的白皮书，[](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf)该白皮书将查看新的共享安全智能更新功能，以及性能测试和有关如何在你自己的 VDI 上测试防病毒性能的指导。

> [!IMPORTANT]
> 尽管 VDI 可以托管在 Windows Server 2012 或 Windows Server 2016 上，但虚拟机 (VM) 至少应运行 Windows 10，1607，因为保护技术和功能在 Windows 早期版本中不可用。
>
> 对 Microsoft Defender AV 在 Windows 10 Insider Preview 内部版本 18323 (及更高版本中的虚拟机上的操作方式进行了性能和功能) 。 如果你需要使用 Insider Preview 版本，我们将在本指南中确定;如果未指定，则最佳保护和性能的最低必需版本为 Windows 10 1607。

## <a name="set-up-a-dedicated-vdi-file-share"></a>设置专用的 VDI 文件共享

在 Windows 10 版本 1903 中，我们引入了共享安全智能功能，此功能将下载的安全智能更新的解包卸载到主机上，从而节省各个计算机上以前的 CPU、磁盘和内存资源。 此功能已被备份，现在适用于 Windows 10版本 1703 及以上版本。 可以使用组策略或 PowerShell 设置此功能。

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a>使用组策略启用共享安全智能功能：

1. 在组策略管理计算机上，打开组策略管理控制台，右键单击要配置的组策略对象，**然后单击编辑。**

2. 在组 **策略管理编辑器中** ，转到计算机 **配置**。

3. 单击 **"管理模板"。**

4. 展开树以Windows **安全Microsoft Defender 防病毒** \>  \> **更新的组件**。

5. 双击为 **VDI 客户端定义安全智能** 位置，然后将选项设置为 **已启用**。 将自动显示一个字段。

6. 输入 `\\<sharedlocation\>\wdav-update` (此值的帮助，请参阅下载[并解压缩) 。](#download-and-unpackage-the-latest-updates)

7. 单击“确定”。

8. 将 GPO 部署到要测试的 VM。

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a>使用 PowerShell 启用共享安全智能功能

使用以下 cmdlet 启用该功能。 然后，你需要按通常将基于 PowerShell 的配置策略推送到 VM 中那样进行推送：

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

请参阅 [下载和解包部分](#download-and-unpackage-the-latest-updates) ，了解 \<shared location\> 将是什么。

## <a name="download-and-unpackage-the-latest-updates"></a>下载最新更新并解压缩

现在，你可以开始下载和安装新更新。 我们在下面创建了一个示例 PowerShell 脚本。 此脚本是下载新更新并使它们为 VM 做好准备的最简单方法。 然后，你应该使用计划任务 (将脚本设置为在特定时间在管理计算机上运行，或者如果你熟悉在 Azure、Intune 或 SCCM 中使用 PowerShell 脚本，则还可以使用这些脚本) 。

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

你可以将计划任务设置为每天运行一次，以便只要下载包并解压缩，VM 就会收到新更新。
我们建议从每天一次开始，但应尝试增加或降低频率以了解影响。

安全智能包通常每三到四小时发布一次。 建议不要设置小于 4 小时的频率，因为这会增加管理计算机上网络开销，而没有任何好处。

还可以设置单个服务器或计算机，以定期代表 VM 获取更新，将它们放在文件共享中供使用。
当设备对共享具有读取访问权限的共享和 NTFS 权限，以便它们可以获取更新时，这是可能的。

为此:
 1. 创建 SMB/CIFS 文件共享。 
 
 2. 使用以下示例创建具有以下共享权限的文件共享。

    ```PowerShell
    PS c:\> Get-SmbShareAccess -Name mdatp$

    Name   ScopeName AccountName AccessControlType AccessRight
    ----   --------- ----------- ----------------- -----------
    mdatp$ *         Everyone    Allow             Change
    ```
   
    > [!NOTE]
    > 为经过身份验证的用户添加了 NTFS **权限：读取：**。 

    对于此示例，文件共享为：

    \\fileserver.fqdn\mdatp$\wdav-update

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a>设置计划任务以运行 PowerShell 脚本

1. 在管理计算机上，打开"任务"开始"菜单键入 **"任务计划程序"。** 打开它，然后选择 **侧面板** 上的"创建任务..."。

2. 输入名称作为 **安全智能解压缩。** 转到触发器 **选项卡。** 选择新建 **...** \>**每天**，然后选择 **确定**。

3. 转到"操作 **"** 选项卡。选择"**新建..."。** 在"程序/脚本 **"字段中输入** **PowerShell。** 在 `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` "添加 **参数"字段中** 输入。 选择“**确定**”。

4. 如果需要，可以选择配置其他设置。

5. 选择 **"** 确定"保存计划任务。

可以通过右键单击任务并单击"运行"来手动启动 **更新**。

### <a name="download-and-unpackage-manually"></a>手动下载并解压缩

如果您希望手动执行所有操作，下面是复制脚本行为要执行哪些操作：

1. 在系统根目录上新建一个文件夹，以存储智能更新，例如 `wdav_update` ，创建文件夹 `c:\wdav_update` 。

2. 使用 GUID 名称wdav_update文件夹下创建子文件夹，例如`{00000000-0000-0000-0000-000000000000}`

   下面是一个示例： `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`

   > [!NOTE]
   > 在脚本中，我们设置它，以便 GUID 的最后 12 个数字是下载文件时的年、月、日以及时间，以便每次创建一个新文件夹。 您可以更改此设置，以便每次将文件下载到同一文件夹中。

3. 将安全智能包从 [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  下载到 GUID 文件夹中。 该文件应命名为 `mpam-fe.exe` 。

4. 打开 cmd 提示符窗口并导航到您创建的 GUID 文件夹。 使用 **/X** 提取命令提取文件，例如 `mpam-fe.exe /X` 。

   > [!NOTE]
   > 每当使用提取的更新包创建一个新的 GUID 文件夹，或者每当使用新提取的包更新现有文件夹时，VM 都会选取更新的包。

## <a name="randomize-scheduled-scans"></a>随机化计划扫描

除了实时保护和扫描之外，计划的 [扫描也运行](configure-real-time-protection-microsoft-defender-antivirus.md)。

扫描本身的开始时间仍基于计划扫描策略 (**ScheduleDay、ScheduleTime** 和 **ScheduleQuickScanTime**) 。  随机化将导致Microsoft Defender 防病毒从计划扫描设置的时间起，在 4 小时窗口中在每台计算机中启动扫描。

有关 [可用于计划](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 扫描的其他配置选项，请参阅计划扫描。

## <a name="use-quick-scans"></a>使用快速扫描

可以指定在计划扫描期间应执行的扫描类型。 快速扫描是首选方法，因为它们旨在查找恶意软件需要驻留的所有位置以处于活动状态。 以下过程介绍如何使用组策略设置快速扫描。

1. 在组策略编辑器中，转到"管理 **模板** \> **Windows组件** Microsoft Defender 防病毒 \>  \> **扫描"。**

2. 选择 **"指定要用于计划扫描** 的扫描类型"，然后编辑策略设置。

3. 将策略设置为 **"已启用"，** 然后在"选项"**下**，选择 **"快速扫描"。**

4. 选择“**确定**”。

5. 如通常一样部署组策略对象。

## <a name="prevent-notifications"></a>阻止通知

有时，Microsoft Defender 防病毒多个会话发送通知或保留通知。 为了最大程度地减小此问题，您可以锁定Microsoft Defender 防病毒用户界面。 以下过程介绍如何使用组策略禁止通知。

1. 在组策略编辑器中，转到Windows **客户端** Microsoft Defender 防病毒 \>  \> **组件。**

2. 选择 **"取消所有通知** "，然后编辑策略设置。

3. 将策略设置为 **"已启用"，** 然后选择"确定 **"。**

4. 如通常一样部署组策略对象。

禁止通知可防止Microsoft Defender 防病毒扫描或采取修正操作Windows 10在操作中心中显示通知。 但是，安全运营团队将在"安全中心"门户中Microsoft 365 Defender[扫描结果](microsoft-defender-security-center.md)。

> [!TIP]
> 若要在 Windows 10 或 Windows 11 上打开操作中心，请执行以下步骤之一：
>
> - 在任务栏的右侧，选择操作中心图标。
> - 按Windows键按钮 + A。
> - 在触摸屏设备上，从屏幕的右边缘轻扫。

## <a name="disable-scans-after-an-update"></a>更新后禁用扫描

在更新后禁用扫描将阻止扫描在收到更新后发生。 如果还运行了快速扫描，可以在创建基本映像时应用此设置。 这样，你可以阻止新更新的 VM 再次执行扫描 (，因为当你创建基本映像映像库时已经) 。

> [!IMPORTANT]
> 在更新后运行扫描有助于确保 VM 受最新安全智能更新的保护。 禁用此选项将降低 VM 的保护级别，并且应仅在首次创建或部署基本映像时使用。

1. 在组策略编辑器中，转到Windows **安全** Microsoft Defender 防病毒 \>  \> **更新的组件**。

2. 选择 **"在安全智能更新后启用扫描"，** 然后编辑策略设置。

3. 将策略设置为 **Disabled**。

4. 选择“**确定**”。

5. 如通常一样部署组策略对象。

此策略阻止扫描在更新后立即运行。

## <a name="scan-vms-that-have-been-offline"></a>扫描已脱机的 VM

1. 在组策略编辑器中，转到Windows **扫描Microsoft Defender 防病毒** \>  \> **组件**。

2. 选择 **"打开捕获快速扫描"，** 然后编辑策略设置。

3. 将策略设置为 **已启用**。

4. 选择“**确定**”。

5. 像通常一样部署组策略对象。

如果 VM 错过两个或多个连续的计划扫描，此策略将强制进行扫描。

## <a name="enable-headless-ui-mode"></a>启用无头 UI 模式

1. 在组策略编辑器中，转到Windows **客户端** Microsoft Defender 防病毒 \>  \> **组件。**

2. 选择 **启用无头 UI 模式** 并编辑策略。

3. 将策略设置为 **已启用**。

4. 单击“确定”。

5. 像通常一样部署组策略对象。

此策略对Microsoft Defender 防病毒最终用户隐藏整个用户界面。

## <a name="exclusions"></a>排除

可以添加、删除或自定义排除项，以满足你的需求。

有关详细信息，请参阅 Configure [Microsoft Defender 防病毒 exclusions on Windows Server。](configure-exclusions-microsoft-defender-antivirus.md)

## <a name="additional-resources"></a>其他资源

- [Tech Community博客：Microsoft Defender 防病毒非永久性 VDI 计算机配置网络](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [远程桌面服务和 VDI 上的 TechNet 论坛](https://social.technet.microsoft.com/Forums/windowsserver/home?forum=winserverTS)
- [SignatureDownloadCustomTask PowerShell 脚本](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)
