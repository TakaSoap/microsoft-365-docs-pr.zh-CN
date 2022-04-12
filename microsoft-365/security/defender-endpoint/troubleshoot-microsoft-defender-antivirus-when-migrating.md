---
title: 从第三方解决方案迁移时解决 Microsoft Defender 防病毒软件问题
description: 排查迁移到Microsoft Defender 防病毒时的常见错误
keywords: 事件、错误代码、日志记录、故障排除、Microsoft Defender 防病毒、Windows Defender 防病毒、迁移
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 10/19/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 74843a71131ae8f10628dac96086e68e25acb2b0
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788427"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a>从第三方解决方案迁移时解决 Microsoft Defender 防病毒软件问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

如果从第三方安全解决方案迁移到Microsoft Defender 防病毒时遇到问题，可在此处找到帮助。

## <a name="review-event-logs"></a>查看事件日志

1. 通过选择任务栏中的 **搜索** 图标并搜索 *事件查看器，打开事件查看器* 应用。

    有关Microsoft Defender 防病毒的信息，请参阅应用程序 **和服务日志** \> **Microsoft** \> **Windows Windows Defender**\>。

1. 在此处，选择 **“操作**”下方 **的“打开**”。

    从“详细信息”窗格中选择事件会在“ **常规** ”和“ **详细信息** ”选项卡下的下窗格中显示有关事件的详细信息。

## <a name="microsoft-defender-antivirus-wont-start"></a>Microsoft Defender 防病毒不会启动

此问题可以以多个不同事件 ID 的形式出现，所有这些 ID 都有相同的根本原因。

### <a name="associated-event-ids"></a>关联的事件 ID

事件 ID|日志名称|说明|源
---|---|---|---
15 |应用程序|已成功更新Windows Defender状态以SECURITY_PRODUCT_STATE_OFF。|安全中心
5007|Microsoft-Windows-Windows Defender/Operational|Windows Defender 防病毒配置已更改。 如果这是意外事件，则应查看设置，因为这可能是恶意软件的结果。 <p> **旧值：** Default\IsServiceRunning = 0x0 <p> **新值：** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1|Windows Defender
5010|Microsoft-Windows-Windows Defender/Operational|Windows Defender 防病毒扫描间谍软件和其他可能不需要的软件被禁用。|Windows Defender

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a>如何判断Microsoft Defender 防病毒是否因为安装了第三方防病毒而无法启动

在Windows 10或Windows 11设备上，如果不使用Microsoft Defender for Endpoint，并且安装了第三方防病毒，则Microsoft Defender 防病毒将自动关闭。 如果在安装第三方防病毒的情况下使用Microsoft Defender for Endpoint，则Microsoft Defender 防病毒将以被动模式启动，但功能会降低。

> [!TIP]
> 刚才描述的方案仅适用于Windows 10和Windows 11。 其他版本的Windows对与第三方安全软件一起运行Microsoft Defender 防病毒有不同的[响应](microsoft-defender-antivirus-compatibility.md)。

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a>使用 Services 应用检查Microsoft Defender 防病毒是否已关闭

若要打开“服务”应用，请从任务栏中选择 **“搜索** ”图标并搜索 *服务*。 也可以通过键入 *services.msc* 从命令行打开应用。

有关Microsoft Defender 防病毒的信息将列在“服务”应用 **的“操作Windows Defender** \> **下。** 防病毒服务名称 *Windows Defender 防病毒服务*。

检查应用时，你可能会看到 *Windows Defender 防病毒服务* 设置为手动，但当你尝试手动启动此服务时，你会收到一条警告，指出“*本地计算机上的Windows Defender 防病毒服务服务已启动，然后停止。如果某些服务未被其他服务或程序使用，则它们会自动停止。*

这表明Microsoft Defender 防病毒已自动关闭，以保持与第三方防病毒的兼容性。

#### <a name="generate-a-detailed-report"></a>生成详细报表

通过在 **“以管理模式运行** ”中打开命令提示符，然后输入以下命令，可以生成有关当前活动组策略的详细报告：

```console
GPresult.exe /h gpresult.html
```

这将生成位于 *./gpresult.html* 的报表。 打开此文件，可能会看到以下结果，具体取决于Microsoft Defender 防病毒的关闭方式。

##### <a name="group-policy-results"></a>组策略结果

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a>如果安全设置是通过组策略 (GPO 在域或本地级别) 实现的，或者通过 System center configuration manager (SCCM) 

在 GPResults 报表中，*在标题Windows组件/Windows Defender 防病毒* 下，你可能会看到如下条目，表示Microsoft Defender 防病毒已关闭。

Policy|设置|赢得 GPO
---|---|---
关闭Windows Defender 防病毒|已启用|Win10-Workstations

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a>如果安全设置是通过组策略首选项实现的， (GPP) 

在标题下，*注册表项 (键路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender，值名称：DisableAntiSpyware)*，你可能会看到如下条目，指示Microsoft Defender 防病毒已关闭。

DisableAntiSpyware|-
---|---
赢得 GPO|Win10-Workstations
结果：成功|
**常规**|
Action|更新
**Properties**|
Hive|HKEY_LOCAL_MACHINE
密钥路径|SOFTWARE\Policies\Microsoft\Windows Defender
值名称|DisableAntiSpyware
值类型|REG_DWORD
值数据|0x1 (1) 

###### <a name="if-security-settings-are-implemented-via-registry-key"></a>如果安全设置是通过注册表项实现的

报表可能包含以下文本，指示已关闭Microsoft Defender 防病毒：

> 注册表 (regedit.exe) 
>
> HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (十六进制) 

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a>如果在Windows或Windows服务器映像中设置了安全设置

假想管理员可能已通过 *GPEdit.exe*、 *LGPO.exe* 或修改其任务序列中的注册表在本地设置安全策略 **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**。 可以[为Microsoft Defender 防病毒配置受信任的映像标识符](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender)。

### <a name="turn-microsoft-defender-antivirus-back-on"></a>重新打开Microsoft Defender 防病毒

如果当前没有其他防病毒软件处于活动状态，则Microsoft Defender 防病毒将自动打开。 你需要完全关闭第三方防病毒，以确保Microsoft Defender 防病毒可以使用完整的功能运行。

> [!WARNING]
> 建议在 *HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services* 中编辑 *wdboot*、*wdfilter*、*wdnisdrv*、*wdnissvc* 和 *windefend* 的Windows Defender起始值的解决方案不受支持，并且可能会强制你重新映像系统。

如果开始将Microsoft Defender for Endpoint和第三方防病毒与Microsoft Defender 防病毒一起使用，则可以使用被动模式。 被动模式允许Microsoft Defender 防病毒扫描文件并自行更新，但不会修正威胁。 此外，除非部署[终结点数据丢失防护 (DLP) ](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview)，否则通过[实时保护](configure-real-time-protection-microsoft-defender-antivirus.md)进行的行为监视在被动模式下不可用。

当将Microsoft Defender 防病毒设置为自动关闭时，最终用户可使用另一项功能（称为[有限定期扫描](limited-periodic-scanning-microsoft-defender-antivirus.md)）。 此功能允许Microsoft Defender 防病毒使用数量有限的检测，定期与第三方防病毒一起扫描文件。

> [!IMPORTANT]
> 不建议在企业环境中进行有限的定期扫描。 与活动模式相比，在此模式下运行Microsoft Defender 防病毒时可用的检测、管理和报告功能会减少。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)


### <a name="see-also"></a>另请参阅

- [Microsoft Defender 防病毒兼容性](microsoft-defender-antivirus-compatibility.md)
- [Windows 安全中心应用中的Microsoft Defender 防病毒](microsoft-defender-security-center-antivirus.md)
