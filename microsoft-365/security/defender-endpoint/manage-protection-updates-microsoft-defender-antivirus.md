---
title: 管理Microsoft Defender 防病毒接收更新的方式和位置
description: 管理Microsoft Defender 防病毒接收保护更新的方式的回退顺序。
keywords: 更新， 安全基线， 保护， 回退顺序， ADL， MMPC， UNC， 文件路径， 共享， wsus
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 04cedfa951387274261c3a7a064cf11a4b97db62
ms.sourcegitcommit: dd7e5b67ff4ae4e7f74490e437c1795933c74cc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64731452"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a>管理 Microsoft Defender 防病毒软件保护更新源

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

使防病毒保护保持最新至关重要。 管理Microsoft Defender 防病毒的保护更新有两个组件：

- *从中* 下载更新的位置;和
- 下载和应用更新 *时*。

本文介绍如何指定应从何处下载更新 (这也称为回退顺序) 。 请参阅["管理Microsoft Defender 防病毒更新并应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)主题，以大致了解更新的工作原理，以及如何配置更新 (的其他方面，例如计划更新) 。

> [!IMPORTANT]
> Microsoft Defender 防病毒安全智能更新和平台更新通过Windows 更新传递，并且从 2019 年 10 月 21 日星期一开始，所有安全情报更新都将是 SHA-2 专用签名的。 必须更新设备以支持 SHA-2 才能更新安全智能。 若要了解详细信息，请参阅[针对 Windows 和 WSUS 的 2019 SHA-2 代码签名支持要求](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)。

<a id="fallback-order"></a>

## <a name="fallback-order"></a>回退顺序

通常，根据网络配置，将终结点配置为单独从主源下载更新，然后按优先级顺序从其他源下载更新。 更新是根据指定的顺序从源获取的。 如果当前源中的更新已过期，则会立即使用列表中的下一个源。

发布更新时，将应用一些逻辑来最大程度地减少更新的大小。 在大多数情况下，只会下载并应用最新更新与当前安装的更新之间的差异 (这称为设备上的增量) 。 但是，增量的大小取决于两个主要因素：

- 设备上上次更新的年龄;和
- 用于下载和应用更新的源。

终结点上的更新越早，下载时间越大。 但是，还必须考虑下载频率。 更频繁的更新计划可能会导致更多的网络使用，而不太频繁的计划可能会导致每次下载的文件大小更大。

有五个位置可以指定终结点应在何处获取更新：

- [Microsoft Update](https://support.microsoft.com/help/12373/windows-update-faq)
- [Windows服务器更新服务](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus) <sup>[[1](#fn1)]<sup></sup>  
- [Microsoft Endpoint Configuration Manager](/configmgr/core/servers/manage/updates)
- [网络文件共享](#unc-share)
- [Microsoft Defender 防病毒和其他 Microsoft 反恶意软件](https://www.microsoft.com/wdsi/defenderupdates)<sup>的安全智能更新 [[2](#fn1)]<sup></sup>

 (<a id="fn1">1</a>) Intune内部定义更新服务器 - 如果使用 SCCM/SUP 获取Microsoft Defender 防病毒的定义更新，并且需要访问客户端设备上阻止的Windows 更新，则可以转换为共同管理，并将终结点保护工作负载卸载到Intune。 在Intune中配置的反恶意软件策略中，有一个"内部定义更新服务器"选项，可将其配置为使用本地 WSUS 作为更新源。 这有助于控制官方 WU 服务器中的哪些更新已获得企业批准，还有助于代理和保存到官方Windows UPdates 网络的网络流量。

 (<a id="fn1">2</a>) 你的策略和注册表可能将其列为MICROSOFT 恶意软件防护中心 (MMPC) 安全智能，其前名。

为了确保最佳的保护级别，Microsoft 更新允许快速发布，这意味着经常下载量较小。 Windows服务器更新服务、Microsoft Endpoint Configuration Manager、Microsoft 安全智能更新和平台更新源提供的更新频率较低。 因此，增量可能会更大，从而导致更大的下载。

> [!NOTE]
> 安全智能更新包含引擎更新，并按每月节奏发布。
安全智能更新也每天提供多次，但此包不包含引擎。


> [!IMPORTANT]
> 如果在Windows服务器更新服务或 Microsoft 更新后将 [Microsoft 安全智能页面](https://www.microsoft.com/security/portal/definitions/adl.aspx)更新设置为回退源，则仅当当前更新被视为过期时，才会从安全智能更新和平台更新下载更新。  (默认情况下，这是连续七天无法从Windows服务器更新服务或 Microsoft 更新服务) 应用更新。
> 但是，可以 [将保护报告为过期之前的天数进行设置](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)。<p>
> 从 2019 年 10 月 21 日星期一开始，安全智能更新和平台更新将专门签署 SHA-2。 必须更新设备以支持 SHA-2 才能获取最新的安全智能更新和平台更新。 若要了解详细信息，请参阅[针对 Windows 和 WSUS 的 2019 SHA-2 代码签名支持要求](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)。

每个源都有一些典型方案，这些方案取决于网络的配置方式，以及它们发布更新的频率，如下表所述：

<br/><br/>

|位置|示例应用场景|
|---|---|
|Windows服务器更新服务|你正在使用Windows服务器更新服务来管理网络的更新。|
|Microsoft Update|希望终结点直接连接到 Microsoft 更新。 对于不规则地连接到企业网络的终结点，或者如果不使用Windows服务器更新服务来管理更新，这可能很有用。|
|文件共享|有非 Internet 连接的设备 (，例如 VM) 。 可以使用连接 Internet 的 VM 主机将更新下载到网络共享，VM 可以从中获取更新。 请参阅 [VDI 部署指南](deployment-vdi-microsoft-defender-antivirus.md) ，了解如何在虚拟桌面基础结构 (VDI) 环境中使用文件共享。|
|Microsoft Endpoint Manager|你正在使用Microsoft Endpoint Manager更新终结点。|
|Microsoft Defender 防病毒和其他 Microsoft 反恶意软件的安全智能更新和平台更新 (以前称为 MMPC) |[确保设备已更新以支持 SHA-2](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)。 Microsoft Defender 防病毒安全智能和平台更新通过Windows 更新提供，从 2019 年 10 月 21 日星期一开始，安全智能更新和平台更新将专门签署 SHA-2。 <br/>下载最新的保护更新，因为最近感染或帮助预配强大的基础映像的 [VDI 部署](deployment-vdi-microsoft-defender-antivirus.md)。 此选项通常只应用作最终回退源，而不应用作主源。 仅当在[指定天数](/microsoft-365/security/defender-endpoint/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)内无法从Windows服务器更新服务或 Microsoft 更新下载更新时，才会使用它。|

可以管理将更新源用于组策略、Microsoft Endpoint Configuration Manager、PowerShell cmdlet 和 WMI 的顺序。

> [!IMPORTANT]
> 如果将Windows服务器更新服务设置为下载位置，则必须批准更新，而不考虑用于指定位置的管理工具。 可以使用Windows服务器更新服务设置自动审批规则，这可能非常有用，因为更新每天至少到达一次。 若要了解详细信息，请参阅[独立Windows服务器更新服务中的同步终结点保护更新](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。

本文中的过程首先介绍如何设置顺序，然后介绍如何设置 **文件共享** 选项（如果已启用）。

## <a name="use-group-policy-to-manage-the-update-location"></a>使用组策略管理更新位置

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，然后单击 **"编辑**"。

2. 在 **组策略管理编辑器** 中转到 **计算机配置**。

3. 单击 **"策略** "，然后单击 **"管理模板**"。

4. 展开树以 **Windows组件** \> **Windows Defender** \> **签名更新** 并配置以下设置：

   1. 双击" **定义用于下载安全智能更新设置的源顺序** "，并将选项设置为 **"已启用**"。

   2. 输入源的顺序，用单个管道分隔，例如： `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC`如以下屏幕截图所示。

      :::image type="content" source="../../media/wdav-order-update-sources.png" alt-text="列出源顺序的组策略设置" lightbox="../../media/wdav-order-update-sources.png":::

   3. 选择“确定”。 这将设置保护更新源的顺序。

   4. 双击 **"定义文件共享"以下载安全智能更新** 设置，并将选项设置为 **"已启用**"。

   5. 指定文件共享源。 如果有多个源，请按应使用的顺序输入每个源，用单个管道分隔。 使用 [标准 UNC 表示法](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) 来表示路径，例如： `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name`. 如果未输入任何路径，则在 VM 下载更新时将跳过此源。

   6. 单击“确定”。 这将设置在定义 **源顺序...** 组策略设置中引用该源时的文件共享顺序。

> [!NOTE]
> 对于Windows 10版本 1703（至 1809）和 1809 版本，策略路径 **Windows组件> Microsoft Defender 防病毒 >签名更新** Windows 10版本 1903，策略路径 **Windows组件>Microsoft Defender 防病毒 >安全智能更新**

## <a name="use-configuration-manager-to-manage-the-update-location"></a>使用Configuration Manager管理更新位置

有关配置当前分支) Microsoft Endpoint Manager (的详细信息，请参阅为Endpoint Protection[配置安全智能更新](/configmgr/protect/deploy-use/endpoint-definition-updates)。

## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a>使用 PowerShell cmdlet 管理更新位置

使用以下 PowerShell cmdlet 设置更新顺序。

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```

有关详细信息，请参阅以下文章：

- [Set-MpPreference -SignatureFallbackOrder](/powershell/module/defender/set-mppreference)
- [Set-MpPreference -SignatureDefinitionUpdateFileSharesSource](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [使用 PowerShell cmdlet 配置和运行Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Defender 防病毒 cmdlet](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a>使用 Windows 管理指令 (WMI) 来管理更新位置

对以下属性使用 MSFT_MpPreference 类的 [**Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))：

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

有关详细信息，请参阅以下文章：

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a>使用移动设备管理 (MDM) 管理更新位置

有关配置 MDM 的详细信息，请参阅 [策略 CSP - Defender/SignatureUpdateFallbackOrder](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) 。

## <a name="what-if-were-using-a-third-party-vendor"></a>如果我们使用第三方供应商怎么办？

本文介绍如何配置和管理Microsoft Defender 防病毒的更新。 但是，第三方供应商可用于执行这些任务。

例如，假设 Contoso 已聘请 Fabrikam 来管理其安全解决方案，其中包括Microsoft Defender 防病毒。 Fabrikam 通常使用[Windows管理检测](./use-wmi-microsoft-defender-antivirus.md)、[PowerShell cmdlet](./use-powershell-cmdlets-microsoft-defender-antivirus.md) 或[Windows命令行](./command-line-arguments-microsoft-defender-antivirus.md)来部署修补程序和更新。

> [!NOTE]
> Microsoft 不测试用于管理Microsoft Defender 防病毒的第三方解决方案。

<a id="unc-share"></a>

## <a name="create-a-unc-share-for-security-intelligence-and-platform-updates"></a>为安全智能和平台更新创建 UNC 共享

设置网络文件共享 (UNC/映射驱动器) ，以便使用计划任务从 MMPC 站点下载安全智能和平台更新。

1. 在要预配共享并下载更新的系统上，创建要将脚本保存到的文件夹。

    ```console
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. 创建要将签名更新保存到的文件夹。

    ```console
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. 从 [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4) 下载 PowerShell 脚本。

4. 单击 **"手动下载**"。

5. 单击 **"下载原始 nupkg 文件**"。

6. 提取文件。

7. 将文件SignatureDownloadCustomTask.ps1复制到之前创建 `C:\Tool\PS-Scripts\` 的文件夹。

8. 使用命令行设置计划任务。

   > [!NOTE]
   > 有两种类型的更新：完整更新和增量更新。

   - 对于 x64 增量：

       ```powershell
       Powershell (Run as admin)

       C:\Tool\PS-Scripts\

       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - 对于 x64 完整：

       ```powershell
       Powershell (Run as admin)

       C:\Tool\PS-Scripts\

       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - 对于 x86 增量：

       ```powershell
       Powershell (Run as admin)

       C:\Tool\PS-Scripts\

       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - 对于 x86 完整：

       ```powershell
       Powershell (Run as admin)

       C:\Tool\PS-Scripts\

       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   > [!NOTE]
   > 创建计划任务后，可以在任务计划程序下 `Microsoft\Windows\Windows Defender`方找到这些任务。

9. 手动运行每个任务，并验证你是否具有数据 (`mpam-d.exe`， `mpam-fe.exe`并在 `nis_full.exe` 以下文件夹中)  (你可能选择了不同的位置) ：

   - `C:\Temp\TempSigs\x86`
   - `C:\Temp\TempSigs\x64`

   如果计划的任务失败，请运行以下命令：

    ```console
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64"

    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64"

    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86"

    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86"
    ```

    > [!NOTE]
    > 问题也可能由执行策略导致。

10. 创建指向 (的共享 `C:\Temp\TempSigs` ，例如) `\\server\updates` 。

    > [!NOTE]
    > 至少，经过身份验证的用户必须具有"读取"访问权限。 此要求也适用于域计算机、共享和 NTFS (安全) 。

11. 将策略中的共享位置设置为共享。

    > [!NOTE]
    > 请勿在路径中添加 x64 (或 x86) 文件夹。 mpcmdrun.exe进程会自动添加它。

## <a name="related-articles"></a>相关文章

- [部署Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)
- [管理Microsoft Defender 防病毒更新并应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)
- [管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md)
- [管理移动设备和 VM 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
