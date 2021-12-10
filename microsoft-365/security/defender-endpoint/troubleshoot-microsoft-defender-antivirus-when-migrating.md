---
title: 从第三方解决方案迁移时解决 Microsoft Defender 防病毒软件问题
description: 解决迁移到迁移过程中常见的Microsoft Defender 防病毒
keywords: 事件， 错误代码， 日志记录， 疑难解答， microsoft defender 防病毒， windows defender 防病毒， 迁移
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
ms.openlocfilehash: c1b60b66977c4f93591bce20a5cf6ace0b7fc567
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168002"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a>从第三方解决方案迁移时解决 Microsoft Defender 防病毒软件问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)


如果在从第三方安全解决方案迁移到第三方安全解决方案时遇到问题，可以在此处Microsoft Defender 防病毒。

## <a name="review-event-logs"></a>查看事件日志

1. 通过选择任务栏中的"搜索"图标并搜索事件查看器，打开 *事件查看器应用*。

    有关应用程序Microsoft Defender 防病毒信息，请参阅Microsoft Windows Windows Defender 应用程序和服务 \>  \>  \> **日志**。

1. 从"操作"**下方选择**"打开 **"。**

    从详细信息窗格中选择事件将在下窗格中的"常规"和"详细信息"选项卡下 **显示有关****事件的详细信息**。

## <a name="microsoft-defender-antivirus-wont-start"></a>Microsoft Defender 防病毒无法启动

此问题可能以多个不同的事件 ID 的形式显示，所有这些事件都有相同的基本原因。

### <a name="associated-event-ids"></a>关联的事件 ID

事件 ID|日志名称|说明|源
---|---|---|---
15 |Application|更新Windows Defender状态以SECURITY_PRODUCT_STATE_OFF。|安全中心
5007|Microsoft-Windows-Windows Defender/Operational|Windows Defender 防病毒配置已更改。 如果这是意外事件，你应该查看设置，因为这可能是恶意软件的结果。 <p> **旧值：** Default\IsServiceRunning = 0x0 <p> **新值：** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1|Windows Defender
5010|Microsoft-Windows-Windows Defender/Operational|Windows Defender 防病毒间谍软件和其他可能不需要的软件扫描处于禁用状态。|Windows Defender

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a>如何判断Microsoft Defender 防病毒是否因为安装了第三方防病毒而无法启动

在 Windows 10 或 Windows 11 设备上，如果未使用 Microsoft Defender for Endpoint，并且安装了第三方防病毒，Microsoft Defender 防病毒将自动关闭。 如果你使用的是安装了第三方防病毒的 Microsoft Defender for Endpoint，Microsoft Defender 防病毒被动模式启动，功能会减少。

> [!TIP]
> 上述方案仅适用于Windows 10 Windows 11。 其他版本的 Windows对第三[Microsoft Defender 防病毒](microsoft-defender-antivirus-compatibility.md)安全软件一起运行的其他版本有不同的响应。

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a>使用"服务"应用检查Microsoft Defender 防病毒是否已关闭

若要打开"服务"应用，请从 **任务栏中选择"** 搜索"图标，然后搜索 *服务*。 您还可以通过键入 *services.msc* 从命令行打开应用程序。

有关服务Microsoft Defender 防病毒将在服务应用下列出Windows Defender \> **操作**。 防病毒服务名称是Windows Defender 防病毒 *服务*。

检查应用时，你可能会看到 Windows Defender 防病毒 *服务* 已设置为手动，但在尝试手动启动此服务时，你收到一条警告，指出"本地计算机上 Windows Defender 防病毒 服务服务已启动，然后已停止"。 *如果某些服务未由其他服务或程序* 使用，则会自动停止这些服务。

这表示Microsoft Defender 防病毒已自动关闭，以保留和第三方防病毒的兼容性。

#### <a name="generate-a-detailed-report"></a>生成详细报告

可以通过在以管理员模式运行中打开命令提示符，然后输入以下命令来生成有关当前活动组策略的详细报告：

```console
GPresult.exe /h gpresult.html
```

这将生成位于 *./gpresult.html* 的报告。 打开此文件，你可能会看到以下结果，具体取决于Microsoft Defender 防病毒关闭方式。

##### <a name="group-policy-results"></a>组策略结果

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a>如果安全设置是通过组策略 (GPO) 在域或本地级别实现，或者通过 System center configuration manager (SCCM) 

在 GPResults 报告中，在标题 Windows *Components/Windows Defender 防病毒* 下，你可能会看到如下条目，指示Microsoft Defender 防病毒关闭。

Policy|设置|获胜的 GPO
---|---|---
关闭Windows Defender 防病毒|已启用|Win10-Workstations

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a>如果安全设置是通过组策略首选项 (GPP) 

在标题"注册表项 (项路径 *：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender，值名称：DisableAntiSpyware) "* 下，你可能会看到如下条目，指示Microsoft Defender 防病毒已关闭。

DisableAntiSpyware|-
---|---
获胜的 GPO|Win10-Workstations
结果：成功|
**常规**|
Action|更新
**属性**|
Hive|HKEY_LOCAL_MACHINE
密钥路径|SOFTWARE\Policies\Microsoft\Windows Defender
值名称|DisableAntiSpyware
值类型|REG_DWORD
值数据|0x1 (1) 

###### <a name="if-security-settings-are-implemented-via-registry-key"></a>如果安全设置是通过注册表项实现的

报告可能包含以下文本，指示Microsoft Defender 防病毒关闭：

> 注册表 (regedit.exe) 
>
> HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (1)  (十六) 

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a>如果在服务器映像或 Windows中Windows安全设置

你虚构的管理员可能已经在本地通过 *GPEdit.exe* *、LGPO.exe* 或通过修改任务序列中的注册表来设置安全策略 **[DisableAntiSpyware。](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)** 你可以为[受信任映像标识符配置](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender)Microsoft Defender 防病毒。

### <a name="turn-microsoft-defender-antivirus-back-on"></a>打开Microsoft Defender 防病毒"

Microsoft Defender 防病毒当前没有处于活动状态的防病毒，将自动打开该防病毒。 你需要完全关闭第三方防病毒，以确保Microsoft Defender 防病毒完整功能运行。

> [!WARNING]
> 建议编辑 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services 中的wdboot、wdfilter、wdnisdrv、wdnissvc 和 *windefend* 的 Windows Defender 启动值的解决方案不受支持，并可能会强制你重新映像系统。   

如果你开始将 Microsoft Defender for Endpoint 和第三方防病毒与 Microsoft Defender 防病毒 一起使用，则被动模式可用。 被动模式Microsoft Defender 防病毒扫描文件并自行更新，但无法修正威胁。 此外，通过实时保护的行为[](configure-real-time-protection-microsoft-defender-antivirus.md)监视在被动模式下不可用，除非部署了 DLP ([终结点](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview)) 数据丢失防护。

另一个称为[有限定期](limited-periodic-scanning-microsoft-defender-antivirus.md)扫描的功能在设置为自动关闭Microsoft Defender 防病毒最终用户可用。 此功能允许Microsoft Defender 防病毒检测次数有限的第三方防病毒一起定期扫描文件。

> [!IMPORTANT]
> 不建议在企业环境中进行有限定期扫描。 与活动模式相比，在此模式下Microsoft Defender 防病毒运行时提供的检测、管理和报告功能会减少。

### <a name="see-also"></a>另请参阅

- [Microsoft Defender 防病毒兼容性](microsoft-defender-antivirus-compatibility.md)
- [Microsoft Defender 防病毒应用程序中Windows 安全中心](microsoft-defender-security-center-antivirus.md)
