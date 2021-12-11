---
title: 管理接收更新Microsoft Defender 防病毒和位置
description: 管理如何接收保护更新Microsoft Defender 防病毒回退顺序。
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
ms.openlocfilehash: 2636756a3a91156041843c1375211a8640c5e701
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168506"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a>管理 Microsoft Defender 防病毒软件保护更新源

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

使防病毒保护保持最新至关重要。 有两个组件可以管理适用于Microsoft Defender 防病毒：

- *从* 何处下载更新;和
- *下载* 和应用更新时。

本文介绍如何指定从何处下载更新 (这也称为回退) 。 请参阅[管理Microsoft Defender 防病毒](manage-updates-baselines-microsoft-defender-antivirus.md)更新和应用基线主题，大致了解更新如何工作以及如何配置更新的其他方面 (如计划更新) 。

> [!IMPORTANT]
> Microsoft Defender 防病毒安全更新通过 Windows Update 提供，并且从 2019 年 10 月 21 日星期一开始，所有安全智能更新都将由 SHA-2 专门签名。 必须更新设备以支持 SHA-2，才能更新安全智能。 若要了解更多信息，请参阅适用于 Windows 和[WSUS 的 2019 SHA-2 代码签名支持要求](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)。

<a id="fallback-order"></a>

## <a name="fallback-order"></a>回退顺序

通常，根据网络配置，将终结点配置为从主源单独下载更新，然后按优先级顺序下载其他源。 更新按指定的顺序从源获取。 如果源不可用，将立即使用列表中的下一个源。

发布更新时，会应用一些逻辑以最大程度地减小更新的大小。 在大多数情况下，仅下载并应用最新更新与当前安装的 (这称为) 增量更新。 但是，增量的大小取决于两个主要因素：

- 设备上上次更新的年数;和
- 用于下载和应用更新的源。

终结点上的更新越旧，下载越大。 但是，您还必须考虑下载频率。 更频繁的更新计划可能会导致更多的网络使用率，而不频繁的计划可能会导致每个下载的文件大小更大。

可以在五个位置指定终结点应获取更新的位置：

- [Microsoft Update](https://support.microsoft.com/help/12373/windows-update-faq)
- [Windows服务器更新服务](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus) <sup> [[1](#fn1)]<sup></sup>  
- [Microsoft Endpoint Configuration Manager](/configmgr/core/servers/manage/updates)
- [网络文件共享](#unc-share)
- [Microsoft 反恶意软件Microsoft Defender 防病毒安全智能更新](https://www.microsoft.com/wdsi/defenderupdates) <sup> [[2](#fn1)]<sup></sup>

 (<a id="fn1">1</a>) Intune 内部定义更新服务器 - 如果使用 SCCM/SUP 获取 Microsoft Defender 防病毒 的定义更新，并且需要在客户端设备上访问阻止的 Windows 更新，你可以转换到共同管理，将终结点保护工作负载卸载到 Intune。 在 Intune 中配置的反恶意软件策略中，有一个"内部定义更新服务器"选项，可以配置为使用本地 WSUS 作为更新源。 这可以帮助您控制批准企业使用的官方 WU 服务器中的哪些更新，还有助于代理网络流量并将其保存到官方 Windows UPdates 网络。

 (<a id="fn1">2</a>) 策略和注册表中可能Microsoft 恶意软件防护中心 (MMPC) 名称中列出。

为了确保最佳保护级别，Microsoft 更新允许快速发布，这意味着频繁进行较小的下载。 Windows服务器更新服务、Microsoft Endpoint Configuration Manager和 Microsoft 安全智能更新源提供频率较少的更新。 因此，增量可能会更大，从而导致下载量更大。

> [!IMPORTANT]
> 如果在 Windows Server Update Service 或 Microsoft Update 之后将[Microsoft](https://www.microsoft.com/security/portal/definitions/adl.aspx)安全智能页面更新设置为回退源，则仅在认为当前更新过期时，才从安全智能更新下载更新。  (默认情况下，这是连续七天无法从 Windows Server Update Service 或 Microsoft Update Services 应用更新) 。
> 但是，你可以设置保护报告为过期 [前的天数](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)。<p>
> 从 2019 年 10 月 21 日星期一开始，安全智能更新将专门签署 SHA-2。 必须更新设备以支持 SHA-2，才能获取最新的安全智能更新。 若要了解更多信息，请参阅适用于 Windows 和[WSUS 的 2019 SHA-2 代码签名支持要求](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)。

每个源都有一些典型方案，这些方案取决于网络的配置方式，以及发布更新的频繁情况，如下表所述：

<br/><br/>

|位置|示例应用场景|
|---|---|
|Windows 服务器更新服务|使用 Windows 服务器更新服务管理网络更新。|
|Microsoft Update|希望终结点直接连接到 Microsoft 更新。 这可用于不定期连接到企业网络的终结点，或者如果您没有使用 Windows Server Update Service 管理更新。|
|文件共享|你拥有未连接 Internet 的设备 (VM) 。 可以使用连接 Internet 的 VM 主机将更新下载到网络共享，VM 可从该共享获取更新。 请参阅 [VDI 部署指南](deployment-vdi-microsoft-defender-antivirus.md) ，了解如何在虚拟桌面基础结构和 VDI (中使用) 文件共享。|
|Microsoft Endpoint Manager|你正在使用Microsoft Endpoint Manager更新终结点。|
|安全智能更新Microsoft Defender 防病毒 Microsoft 反恶意软件 (以前称为 MMPC) |[确保你的设备已更新以支持 SHA-2。](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus) Microsoft Defender 防病毒安全更新通过 Windows Update 提供，从 2019 年 10 月 21 日（星期一）开始，将专门签署 SHA-2。 <br/>下载最新的保护更新，因为最近的感染或有助于为 VDI 部署预配强大的 [基本映像](deployment-vdi-microsoft-defender-antivirus.md)。 此选项通常只用作最终回退源，而不是主源。 只有在指定的天数内无法从 Windows 服务器更新服务或 Microsoft Update 下载更新时，才能[使用。](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)|

可以管理更新源与组策略、Microsoft Endpoint Configuration Manager、PowerShell cmdlet 和 WMI 一同使用的顺序。

> [!IMPORTANT]
> 如果将 Windows 服务器更新服务设置为下载位置，则必须批准更新，而不考虑用于指定位置的管理工具。 您可以使用 Windows Update Service 设置自动审批规则，当更新每天至少到达一次时，这非常有用。 若要了解更多信息，请参阅[在独立 Windows Server Update Service 中同步终结点保护更新](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。

本文中的过程首先介绍如何设置顺序，然后介绍如何设置文件共享选项（如果已启用此选项）。 

## <a name="use-group-policy-to-manage-the-update-location"></a>使用组策略管理更新位置

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**

2. 在组 **策略管理编辑器中** ，转到计算机 **配置**。

3. 单击 **"策略****"，然后单击"管理模板"。**

4. 展开树以Windows **签名** \> **Windows Defender** \> **组件并** 配置以下设置：

   1. 双击定义 **下载安全智能更新** 的源的顺序设置，将选项设置为 **已启用**。

   2. 输入源的顺序，用单个管道分隔，例如： `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC` ，如以下屏幕截图所示。

      :::image type="content" source="../../media/wdav-order-update-sources.png" alt-text="列出源顺序的组策略设置。":::

   3. 选择“**确定**”。 这将设置保护更新源的顺序。

   4. 双击"定义 **文件共享以下载安全智能** 更新"设置，并设置该选项为 **"已启用"。**

   5. 指定文件共享源。 如果有多个源，则按使用顺序输入每个源，用单个管道分隔。 使用 [标准 UNC](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) 表示法表示路径，例如 `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name` ：。 如果未输入任何路径，则 VM 下载更新时将跳过此源。

   6. 单击“**确定**”。 这将在定义源的顺序...组策略设置中引用该源时设置文件共享的顺序。

> [!NOTE]
> 对于 Windows 10 版本 1703（包括 1809）来说，策略路径是 **Windows Components > Microsoft Defender 防病毒 > Signature Updates** For Windows 10， version 1903， the policy path is Windows Components **>Microsoft Defender 防病毒 >安全智能更新**

## <a name="use-configuration-manager-to-manage-the-update-location"></a>使用 Configuration Manager 管理更新位置

有关[配置当前分支Endpoint Protection](/configmgr/protect/deploy-use/endpoint-definition-updates)的详细信息，请参阅 Configure Security intelligence Updates for Microsoft Endpoint Manager (for) 。

## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a>使用 PowerShell cmdlet 管理更新位置

使用以下 PowerShell cmdlet 设置更新顺序。

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```

有关详细信息，请参阅以下文章：

- [Set-MpPreference -SignatureFallbackOrder](/powershell/module/defender/set-mppreference)
- [Set-MpPreference -SignatureDefinitionUpdateFileSharesSource](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [使用 PowerShell cmdlet 配置并运行Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Defender 防病毒 cmdlet](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a>使用 Windows Management Instruction (WMI) 管理更新位置

对 [**以下** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

有关详细信息，请参阅以下文章：

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a>使用移动设备管理 (MDM) 管理更新位置

有关[配置 MDM 的详细信息，请参阅策略 CSP - Defender/SignatureUpdateFallbackOrder。](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder)

## <a name="what-if-were-using-a-third-party-vendor"></a>如果我们使用的是第三方供应商，该做什么？

本文介绍如何配置和管理更新程序Microsoft Defender 防病毒。 但是，第三方供应商可用于执行这些任务。

例如，假定 Contoso 已雇用 Fabrikam 来管理其安全解决方案，其中包括Microsoft Defender 防病毒。 Fabrikam 通常Windows [Management Instrumentation、PowerShell](./use-wmi-microsoft-defender-antivirus.md) [cmdlet](./use-powershell-cmdlets-microsoft-defender-antivirus.md)或 Windows[命令行](./command-line-arguments-microsoft-defender-antivirus.md)来部署修补程序和更新。

> [!NOTE]
> Microsoft 不会测试第三方解决方案来管理Microsoft Defender 防病毒。

<a id="unc-share"></a>

## <a name="create-a-unc-share-for-security-intelligence-updates"></a>为安全智能更新创建 UNC 共享

使用 UNC/映射 (设置网络文件共享) 计划任务从 MMPC 站点下载安全智能更新。

1. 在要预配共享和下载更新的系统上，创建一个要保存脚本的文件夹。

    ```console
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. 创建将保存签名更新的文件夹。

    ```console
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. 从 下载 PowerShell [脚本](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4。

4. 单击 **"手动下载"。**

5. 单击 **下载原始 nupkg 文件**。

6. 提取文件。

7. 将文件SignatureDownloadCustomTask.ps1之前创建的文件夹 C：\Tool\PS-Scripts\ 。

8. 使用命令行设置计划任务。

   > [!NOTE]
   > 有两种类型的更新：完全更新和增量更新。

   - 对于 x64 delta：

       ```powershell
       Powershell (Run as admin)

       C:\Tool\PS-Scripts\

       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - 对于 x64 完整版：

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

   - 对于 x86 完整版：

       ```powershell
       Powershell (Run as admin)

       C:\Tool\PS-Scripts\

       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   > [!NOTE]
   > 创建计划任务后，可以在 Microsoft\Windows\Windows Defender

9. 手动运行每个任务并验证以下文件夹中是否具有数据（mpam-d.exe、mpam-fe.exe 和 nis_full.exe)  (您可能选择了不同的) ：

   - C：\Temp\TempSigs\x86
   - C：\Temp\TempSigs\x64

   如果计划任务失败，请运行以下命令：

    ```console
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64"

    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64"

    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86"

    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86"
    ```

    > [!NOTE]
    > 问题还可能是由于执行策略。

10. 创建一个指向 C：\Temp\TempSigs (例如 \\ server\updates) 。

    > [!NOTE]
    > 经过身份验证的用户至少必须具有"读取"访问权限。

11. 将策略中的共享位置设置为共享。

    > [!NOTE]
    > 请勿在路径中添加 x64 (或 x86) 文件夹。 进程mpcmdrun.exe自动添加它。

## <a name="related-articles"></a>相关文章

- [部署Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)
- [管理Microsoft Defender 防病毒更新并应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)
- [管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md)
- [管理移动设备和 VM 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
