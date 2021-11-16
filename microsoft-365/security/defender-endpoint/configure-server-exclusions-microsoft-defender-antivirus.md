---
title: 在 Microsoft Defender 防病毒 Server 上配置Windows排除项
ms.reviewer: pahuijbr
manager: dansimp
description: Windows服务器包括基于服务器角色的自动排除项。 还可以添加自定义排除项。
keywords: 排除项， 服务器， 自动排除项， 自动， 自定义， 扫描， Microsoft Defender 防病毒
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 11/15/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 616c2376e8180a74380f1d6569c4e4612269f562
ms.sourcegitcommit: d40b8c506c34a661a275f756081a27ef9ad5bf4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2021
ms.locfileid: "60972020"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a>在 Microsoft Defender 防病毒 Server 上配置Windows排除项


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender 防病毒

Microsoft Defender 防病毒在 Windows Server 2016 和 Windows Server 2019 上自动注册某些排除项，如指定的服务器角色所定义。 这些排除项不会显示在应用程序中显示的标准排除Windows 安全中心[列表中](microsoft-defender-security-center-antivirus.md)。

除了服务器角色定义的自动排除项之外，还可以添加或删除自定义排除项。 为此，请参阅以下文章：
- [根据文件名、扩展名和文件夹位置配置和验证排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [配置并验证进程打开的文件的排除项](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a>需要记住的几点

请记住以下要点：

- 自定义排除项优先于自动排除项。
- 自动排除项仅适用于 RTP 扫描 (实时) 保护。 在完整扫描、快速扫描或按需扫描过程中，自动排除项不适用。
- 自定义排除项和重复排除项与自动排除项不冲突。
- Microsoft Defender 防病毒部署映像服务和管理 (DISM) 工具来确定计算机上安装了哪些角色。
- 服务器角色的自动排除在 R2 Windows Server 2012，除非这些服务器已载入 Defender for Endpoint。  (请参阅[将Windows载入到 Microsoft Defender for Endpoint Service](configure-server-endpoints.md).) 

本文概述了在发布或Microsoft Defender 防病毒Windows Server 2016的排除项。

由于Microsoft Defender 防病毒内置在Windows Server 2016中，因此会自动排除操作系统文件和服务器角色。 但是，您可以定义自定义排除项。 如有必要，还可以选择退出自动排除项。

本文包括以下几节：

<br/><br/>

|节|说明|
|---|---|
|[Windows Server 2016或更高版本上的自动排除项](#automatic-exclusions-on-windows-server-2016-or-later)|介绍两种主要类型的自动排除项，并包括自动排除项的详细列表|
|[选择退出自动排除项](#opting-out-of-automatic-exclusions)|包括描述如何选择退出自动排除项的重要注意事项和过程|
|[定义自定义排除项](#defining-custom-exclusions)|提供用于定义自定义排除项的操作说明信息的链接|

## <a name="automatic-exclusions-on-windows-server-2016-or-later"></a>Windows Server 2016或更高版本上的自动排除项

在Windows Server 2016或更高版本上，不应定义以下排除项：

- 操作系统文件
- 服务器角色和通过服务器角色添加的任何文件

由于Microsoft Defender 防病毒内置，因此不需要排除在操作系统或更高版本Windows Server 2016文件。 此外，在运行 Windows Server 2016 或更高版本并安装角色时，Microsoft Defender 防病毒包括服务器角色以及安装角色时添加的任何文件的自动排除项。

操作系统排除和服务器角色排除不会显示在应用程序中显示的标准排除Windows 安全中心[列表中](microsoft-defender-security-center-antivirus.md)。

> [!NOTE]
> 服务器角色和操作系统文件的自动排除项不适用于Windows Server 2012。 如果运行 R2 Windows Server 2012已载入 Defender for Endpoint，则自动排除项可能适用。  (请参阅[将Windows载入到 Microsoft Defender for Endpoint Service](configure-server-endpoints.md).) 


### <a name="the-list-of-automatic-exclusions"></a>自动排除项列表

以下各节包含随自动排除项文件路径和文件类型一起提供的排除项。

#### <a name="default-exclusions-for-all-roles"></a>所有角色的默认排除项

本节列出了 Windows Server 2016 Server 2019 Windows Server 2022 中所有Windows排除项。

> [!NOTE]
> 默认位置可能不同于本文中列出的位置。

##### <a name="windows-tempedb-files"></a>Windows"temp.edb"文件

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\windows.edb`

##### <a name="windows-update-files-or-automatic-update-files"></a>Windows更新文件或自动更新文件

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

##### <a name="windows-security-files"></a>Windows 安全中心文件

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

##### <a name="group-policy-files"></a>组策略文件

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

##### <a name="wins-files"></a>WINS 文件

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

##### <a name="file-replication-service-frs-exclusions"></a>文件复制服务 (FRS) 排除项

- 文件复制服务中的文件 (FRS) 工作文件夹。 FRS 工作文件夹在注册表项中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- FRS 数据库日志文件。 FRS 数据库日志文件文件夹在注册表项中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`

  - `%windir%\Ntfrs\*\Edb\*.log`

- FRS 临时文件夹。 暂存文件夹在注册表项中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- FRS 预安装文件夹。 此文件夹由文件夹指定 `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- 分布式文件系统复制 (DFSR) 和工作文件夹。 这些文件夹由注册表项指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`

  > [!NOTE]
  > 有关自定义位置，请参阅 [选择退出自动排除项](#opting-out-of-automatic-exclusions)。

  - `%systemdrive%\System Volume Information\DFSR\$db_normal$`
  - `%systemdrive%\System Volume Information\DFSR\FileIDTable_*`
  - `%systemdrive%\System Volume Information\DFSR\SimilarityTable_*`
  - `%systemdrive%\System Volume Information\DFSR\*.XML`
  - `%systemdrive%\System Volume Information\DFSR\$db_dirty$`
  - `%systemdrive%\System Volume Information\DFSR\$db_clean$`
  - `%systemdrive%\System Volume Information\DFSR\$db_lostl$`
  - `%systemdrive%\System Volume Information\DFSR\Dfsr.db`
  - `%systemdrive%\System Volume Information\DFSR\*.frx`
  - `%systemdrive%\System Volume Information\DFSR\*.log`
  - `%systemdrive%\System Volume Information\DFSR\Fsr*.jrs`
  - `%systemdrive%\System Volume Information\DFSR\Tmp.edb`

##### <a name="process-exclusions"></a>进程排除

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

##### <a name="hyper-v-exclusions"></a>Hyper-V排除项

下表列出了安装角色角色时自动提供的文件类型排除项、文件夹排除项Hyper-V排除项。

<br><br/>

|排除类型|具体信息|
|---|---|
|文件类型|`*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs`|
|Folders|`%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks`|
|进程|`%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe`|

##### <a name="sysvol-files"></a>SYSVOL 文件

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


#### <a name="active-directory-exclusions"></a>Active Directory 排除项

本节列出了在 AD DS 服务器中安装 Active Directory 域服务 (自动) 。

##### <a name="ntds-database-files"></a>NTDS 数据库文件

数据库文件在注册表项中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

##### <a name="the-ad-ds-transaction-log-files"></a>AD DS 事务日志文件

事务日志文件在注册表项中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

##### <a name="the-ntds-working-folder"></a>NTDS 工作文件夹

此文件夹在注册表项中指定 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

##### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a>AD DS 和 AD DS 相关支持文件的进程排除项

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

#### <a name="dhcp-server-exclusions"></a>DHCP 服务器排除项

本节列出了安装 DHCP 服务器角色时自动提供的排除项。 DHCP 服务器文件位置由注册表项中的DatabasePath、DhcpLogFilePath 和 *BackupDatabasePath* 参数指定`HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

#### <a name="dns-server-exclusions"></a>DNS 服务器排除项

本节列出了文件和文件夹排除项，以及安装 DNS 服务器角色时自动提供的进程排除项。

##### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a>DNS 服务器角色的文件和文件夹排除项

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

##### <a name="process-exclusions-for-the-dns-server-role"></a>DNS 服务器角色的进程排除项

- `%systemroot%\System32\dns.exe`

#### <a name="file-and-storage-services-exclusions"></a>文件和存储服务排除项

本节列出了安装 File 和 存储 Services 角色时自动提供的文件和文件夹排除项。 下面列出的排除项不包括群集角色的排除项。

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

#### <a name="print-server-exclusions"></a>打印服务器排除项

本节列出了安装打印服务器角色时自动提供的文件类型排除项、文件夹排除项和进程排除项。

##### <a name="file-type-exclusions"></a>文件类型排除项

- `*.shd`
- `*.spl`

##### <a name="folder-exclusions"></a>文件夹排除

此文件夹在注册表项中指定 `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`

- `%system32%\spool\printers\*`

##### <a name="process-exclusions"></a>进程排除

- `spoolsv.exe`

#### <a name="web-server-exclusions"></a>Web 服务器排除项

本节列出了安装 Web 服务器角色时自动提供的文件夹排除项和进程排除项。

##### <a name="folder-exclusions"></a>文件夹排除

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

##### <a name="process-exclusions"></a>Process exclusions

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

##### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a>关闭 Sysvol\Sysvol 文件夹或 SYSVOL_DFSR\Sysvol 文件夹中的文件扫描

或 文件夹及所有子文件夹的当前位置是副本集根目录的 `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` 文件系统重新分析目标。 `Sysvol\Sysvol`和 `SYSVOL_DFSR\Sysvol` 文件夹默认使用以下位置：

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

当前活动的路径由 NETLOGON 共享引用，并且可以通过以下子项中的 `SYSVOL` SysVol 值名称确定： `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`

从此文件夹及其所有子文件夹中排除以下文件：

- `*.adm`
- `*.admx`
- `*.adml`
- `Registry.pol`
- `Registry.tmp`
- `*.aas`
- `*.inf`
- `Scripts.ini`
- `*.ins`
- `Oscfilter.ini`

#### <a name="windows-server-update-services-exclusions"></a>Windows Server Update Services排除项

本节列出了在 WSUS 角色中安装 Windows Server Update Services (时自动) 排除项。 WSUS 文件夹在注册表项中指定 `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="opting-out-of-automatic-exclusions"></a>选择退出自动排除项

在Windows Server 2016及更高版本中，安全智能更新提供的预定义排除项仅排除角色或功能的默认路径。 如果在自定义路径中安装了角色或功能，或者想要手动控制排除项集，请确保选择退出安全智能更新中提供的自动排除项。 但请记住，自动提供的排除项已针对 Windows Server 2016 及更高版本进行了优化。 请参阅[推荐定义排除项，](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)然后再定义排除列表。

> [!WARNING]
> 选择退出自动排除可能会对性能产生不利影响，或会导致数据损坏。 自动提供的排除项针对 Windows Server 2016、Windows Server 2019 和 Windows Server 2022 角色进行了优化。

由于预定义排除 **项仅排除** 默认路径 ，因此如果将 NTDS 和 SYSVOL 文件夹移动到与原始路径不同的其他驱动器或路径，则必须手动添加排除项。 请参阅 [配置基于文件夹名称或文件扩展名的排除项列表](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension)。

可以使用组策略、PowerShell cmdlet 和 WMI 禁用自动排除列表。

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-windows-server-2019-and-windows-server-2022"></a>使用组策略禁用 Windows Server 2016、Windows Server 2019 和 Windows Server 2022 上的自动排除列表

1. 在组策略管理计算机上，打开 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11))。 右键单击要配置的组策略对象， **然后选择编辑**。

2. 在"**组策略管理编辑器**"中，转到"**计算机配置**"，然后选择"**管理模板"。**

3. 展开树以Windows **排除** \> **Microsoft Defender 防病毒** \> **组件**。

4. 双击关闭 **自动排除项**，将选项设置为 **已启用**。 然后，选择“**确定**”。

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server"></a>使用 PowerShell cmdlet 禁用 Windows Server 上的自动排除项列表

使用以下 cmdlet：

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

若要了解详细信息，请参阅以下资源：

- [使用 PowerShell cmdlet 配置并运行Microsoft Defender 防病毒。](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [将 PowerShell 与 Microsoft Defender 防病毒 一Microsoft Defender 防病毒。](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server"></a>使用 Windows Management Instruction (WMI) 禁用 Windows Server 上的自动排除列表

对以下 [属性MSFT_MpPreference类](/previous-versions/windows/desktop/defender/msft-mppreference)的 **Set** 方法：

```WMI
DisableAutoExclusions
```

有关详细信息和允许的参数，请参阅以下内容：

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="defining-custom-exclusions"></a>定义自定义排除项

如有必要，可以添加或删除自定义排除项。 为此，请参阅以下文章：

- [根据文件名、扩展名和文件夹位置配置和验证排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [配置并验证进程打开的文件的排除项](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="see-also"></a>另请参阅

- [配置并验证扫描的Microsoft Defender 防病毒项](configure-exclusions-microsoft-defender-antivirus.md)
- [根据文件名、扩展名和文件夹位置配置和验证排除项](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [配置并验证进程打开的文件的排除项](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [定义排除时要避免的常见错误](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [自定义、启动和查看Microsoft Defender 防病毒扫描和修正的结果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
