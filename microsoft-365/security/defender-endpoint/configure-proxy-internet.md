---
title: 配置设备代理和 Internet 连接设置
description: 配置Microsoft Defender for Endpoint代理和 Internet 设置以启用与云服务的通信。
keywords: 配置， 代理， Internet， Internet 连接， 设置， 代理设置， netsh， winhttp， 代理服务器
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 787da143bdbbc2d21610ba14d0fe7c955e4e976d
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823369"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a>配置设备代理和 Internet 连接设置

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)。

Defender for Endpoint 传感器要求 Microsoft Windows HTTP (WinHTTP) 报告传感器数据并与 Defender for Endpoint 服务通信。 嵌入式 Defender for Endpoint 传感器使用 LocalSystem 帐户在系统上下文中运行。 传感器使用 Microsoft Windows HTTP 服务 (WinHTTP) 来启用与 Defender for Endpoint 云服务的通信。

> [!TIP]
> 对于使用转发代理作为 Internet 网关的组织，可以使用网络保护 [来调查前向代理后面发生的连接事件](investigate-behind-proxy.md)。

WinHTTP 配置设置独立于 Windows Internet (WinINet) 浏览代理设置 (请参阅[，WinINet 与 WinHTTP](/windows/win32/wininet/wininet-vs-winhttp)) 。 它只能使用以下发现方法发现代理服务器：

- 自动发现方法：

  - 透明代理
  
  - Web 代理自动发现协议 (WPAD)

    > [!NOTE]
    > 如果在网络拓扑中使用透明代理或 WPAD，则不需要特殊的配置设置。 有关代理中的 Defender for Endpoint URL 排除项的详细信息，请参阅 [启用对代理服务器中的 Defender for Endpoint 服务 URL 的访问](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)

- 手动静态代理配置：

  - 基于注册表的配置
  
  - 使用 netsh 命令配置的 WinHTTP：仅适用于稳定拓扑 (中的桌面，例如：同一代理后的企业网络中的桌面) 

> [!NOTE]
> 可以独立设置 Defender 防病毒和EDR代理。  在下面的部分中，请注意这些区别。

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>使用基于注册表的静态代理手动配置代理服务器

为 Defender for Endpoint 检测和响应配置基于注册表的静态代理， (EDR) 传感器报告诊断数据，并在不允许计算机连接到 Internet 时与 Defender for Endpoint 服务通信。

> [!NOTE]
> 在 Windows 10、Windows 11 或 Windows Server 2019 或 Windows Server 2022 上使用此选项时，建议在生成和累积更新汇总) 具有以下 (或更高版本：
>
> - Windows 11
> - Windows 10 版本 1809或Windows服务器 2019 或 Windows Server 2022 -<https://support.microsoft.com/kb/5001384>
> - Windows 10版本 1909 -<https://support.microsoft.com/kb/4601380>
> - Windows 10版本 2004 -<https://support.microsoft.com/kb/4601382>
> - Windows 10版本 20H2 -<https://support.microsoft.com/kb/4601382>
>
> 这些更新提高了 CnC (命令和控制) 通道的连接性和可靠性。

静态代理可通过组策略 (GP) 进行配置，组策略值下的两个设置都应配置为代理服务器以使用EDR。 组策略在管理模板中可用。

- **管理模板> Windows组件>数据收集和预览版本>配置已连接用户体验和遥测服务的身份验证代理使用** 情况。

  将其设置为 **“已启用**”，然后选择 **“禁用经过身份验证的代理使用”。**

  :::image type="content" source="images/atp-gpo-proxy1.png" alt-text="组策略 setting1 状态窗格" lightbox="images/atp-gpo-proxy1.png":::

- **管理模板> Windows组件>数据收集和预览版本>配置连接的用户体验和遥测**：

  配置代理。

  :::image type="content" source="images/atp-gpo-proxy2.png" alt-text="组策略 setting2 状态窗格" lightbox="images/atp-gpo-proxy2.png":::


| 组策略 | 注册表项 | 注册表项 | 值 |
|:---|:---|:---|:---|
| 为连接的用户体验和遥测服务配置经过身份验证的代理使用情况 | `HKLM\Software\Policies\Microsoft\Windows\DataCollection` | `DisableEnterpriseAuthProxy` | 1 (REG_DWORD)  |
| 配置连接的用户体验和遥测 | `HKLM\Software\Policies\Microsoft\Windows\DataCollection` | `TelemetryProxyServer` | ```servername:port or ip:port``` <br> <br> 例如： ```10.0.0.6:8080``` (REG_SZ)  |

## <a name="configure-a-static-proxy-for-microsoft-defender-antivirus"></a>为Microsoft Defender 防病毒配置静态代理

Microsoft Defender 防病毒[云提供的保护](cloud-protection-microsoft-defender-antivirus.md)可提供近乎即时的自动保护，防范新威胁和新出现的威胁。 请注意，当 Defender 防病毒是主动的反恶意软件解决方案时， [自定义指示](manage-indicators.md) 器需要连接。 对于[在阻止模式下EDR在](edr-in-block-mode.md)使用非 Microsoft 解决方案时具有主要的反恶意软件解决方案。

使用管理模板中提供的组策略配置静态代理：

1. **管理模板> Windows组件> Microsoft Defender 防病毒 >定义用于连接到网络的代理服务器**。 

2. 将其设置为 **“已启用”** 并定义代理服务器。 请注意，URL 必须具有 http:// 或 https://。 有关 https:// 支持的版本，请参阅[“管理Microsoft Defender 防病毒更新](manage-updates-baselines-microsoft-defender-antivirus.md)”。

   :::image type="content" source="images/proxy-server-mdav.png" alt-text="用于Microsoft Defender 防病毒的代理服务器" lightbox="images/proxy-server-mdav.png":::

3. 在注册表项 `HKLM\Software\Policies\Microsoft\Windows Defender`下，策略将注册表值 `ProxyServer` 设置为REG_SZ。 

   注册表值 `ProxyServer` 采用以下字符串格式：

    ```text
    <server name or ip>:<port>

    For example: http://10.0.0.6:8080
    ```

> [!NOTE]
>
> 出于复原目的和云提供的保护的实时性质，Microsoft Defender 防病毒将缓存最后一个已知的工作代理。 确保代理解决方案不执行 SSL 检查。 这会中断安全的云连接。 
>
> Microsoft Defender 防病毒不会使用静态代理连接到Windows 更新或 Microsoft 更新以下载更新。 相反，如果配置为使用Windows 更新或根据配置的[回退顺序](manage-protection-updates-microsoft-defender-antivirus.md)配置的内部更新源，它将使用系统范围的代理。 
>
> 如果需要，可以使用 **管理模板> Windows组件> Microsoft Defender 防病毒 >定义用于连接到网络的代理自动配置 (.pac)**。 如果需要使用多个代理设置高级配置，请使用 **管理模板> Windows组件> Microsoft Defender 防病毒 >定义地址** 以绕过代理服务器，并防止Microsoft Defender 防病毒使用这些目标的代理服务器。 
>
> 可以将 PowerShell 与 `Set-MpPreference` cmdlet 配合使用来配置以下选项： 
>
> - ProxyBypass 
> - ProxyPacUrl 
> - ProxyServer 

> [!NOTE]
> 若要正确使用代理，请配置以下三个不同的代理设置：
>  - Microsoft Defender for Endpoint (MDE) 
>  - AV (防病毒) 
>  - 终结点检测和响应 (EDR) 

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>使用 netsh 命令手动配置代理服务器

使用 netsh 配置系统范围的静态代理。

> [!NOTE]
>
> - 这将影响所有应用程序，包括使用带默认代理的 WinHTTP 的 Windows 服务。</br>
> - 例如，正在更改拓扑的笔记本电脑 (：从办公室到家庭) 将因 netsh 命令而发生故障。 使用基于注册表的静态代理配置。

1. 打开提升的命令行:
   1. 转到“**开始**”并键入“**cmd**”。
   1. 右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

2. 输入以下命令，再按 **Enter**：

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   例如：`netsh winhttp set proxy 10.0.0.6:8080`

要重置 winhttp 代理，请输入以下命令并按 **Enter** 键：

```PowerShell
netsh winhttp reset proxy
```

若要了解详细信息。，请参见 [Netsh 命令语法、上下文和格式](/windows-server/networking/technologies/netsh/netsh-contexts)。

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a>启用对代理服务器中Microsoft Defender for Endpoint服务 URL 的访问

默认情况下，如果代理或防火墙默认阻止所有流量并仅允许特定域，则将可下载表中列出的域添加到允许的域列表。

以下可下载电子表格列出了网络必须能够连接的服务及其关联 URL。 确保没有防火墙或网络筛选规则来拒绝这些 URL 的访问。 可选，可能需要专门为其创建 *允许* 规则。

<br>

|域列表的电子表格| 说明|
|---|---|
|商业客户Microsoft Defender for Endpoint URL 列表| 针对商业客户的服务位置、地理位置和 OS 的特定 DNS 记录的电子表格。 <p> [在此处下载电子表格。](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Microsoft Defender for Endpoint Gov/GCC/DoD 的 URL 列表 | 适用于 Gov/GCC/DoD 客户的服务位置、地理位置和 OS 的特定 DNS 记录的电子表格。 <p> [在此处下载电子表格。](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

如果代理或防火墙启用了 HTTPS 扫描（SSL 检查），则从 HTTPS 扫描中排除上表中列出的域。
在防火墙中，打开地理列为 WW 的所有 URL。 对于地理列不是 WW 的行，请打开特定数据位置的 URL。 若要验证数据位置设置，请参阅[“验证数据存储位置并更新数据保留设置”以获取Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/data-retention-settings)。

> [!NOTE]
> Windows运行版本 1803 或更低版本的`settings-win.data.microsoft.com`设备。  <br>
>
> 仅当Windows运行版本 1803 或更高版本的设备时，才需要包含 v20 的 URL。 例如，`us-v20.events.data.microsoft.com`运行版本 1803 或更高版本并载入到美国数据存储区域的Windows设备是必需的。
>

如果代理或防火墙阻止匿名流量作为 Defender for Endpoint 传感器，并且它正在从系统上下文进行连接，以确保在以前列出的 URL 中允许匿名流量。

> [!NOTE]
> Microsoft 不提供代理服务器。 可通过配置的代理服务器访问这些 URL。

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a>Microsoft Monitoring Agent (MMA) - 旧版Windows客户端或Windows服务器的代理和防火墙要求

代理和防火墙配置信息列表中的信息是与 Log Analytics 代理通信所必需的， (通常称为早期版本的Windows的Microsoft Monitoring Agent) ，例如 Windows 7 SP1、Windows 8.1 和 Windows Server 2008 R2*。

<br>

****

|代理资源|端口|方向|绕过 HTTPS 检查|
|---|---|---|---|
|*.ods.opinsights.azure.com|端口 443|出站|是|
|*.oms.opinsights.azure.com|端口 443|出站|是|
|*.blob.core.windows.net|端口 443|出站|是|
|*.azure-automation.net|端口 443|出站|是|

> [!NOTE]
> *这些连接要求适用于以前的Windows Server 2016 Microsoft Defender for Endpoint，Windows Server 2012需要 MMA 的 R2。 使用新的统一解决方案载入这些操作系统的说明位于[载入Windows服务器上](configure-server-endpoints.md)，或在 [Microsoft Defender for Endpoint 中的服务器迁移方案中](/microsoft-365/security/defender-endpoint/server-migration)迁移到新的统一解决方案。

> [!NOTE]
> 作为基于云的解决方案，IP 范围可能会更改。 建议移动到 DNS 解析设置。

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a>确认 Microsoft Monitoring Agent (MMA) 服务 URL 要求 

 请参阅以下指南，以消除对以前版本的Windows使用 Microsoft Monitoring Agent (MMA) 时特定环境的通配符 (*) 要求。

1. 使用 Microsoft Monitoring Agent (MMA 将以前的操作系统) 载入 Defender for Endpoint (中，了解详细信息，请参阅[在 Defender for Endpoint 和](https://go.microsoft.com/fwlink/p/?linkid=2010326)[载入Windows服务器](configure-server-endpoints.md)上载入早期版本的 Windows，) 。

2. 确保计算机已成功报告到Microsoft 365 Defender门户。

3. 从“C：\Program Files\Microsoft Monitoring Agent\Agent”运行TestCloudConnection.exe工具来验证连接，并获取特定工作区的必需 URL。

4. 查看Microsoft Defender for Endpoint URL 列表，了解区域要求的完整列表 (请参阅服务 URL [电子表格](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)) 。

   :::image type="content" source="images/admin-powershell.png" alt-text="Windows PowerShell中的管理员" lightbox="images/admin-powershell.png":::

.ods.opinsights.azure.com \* 、\*.oms.opinsights.azure.com 和 \*.agentsvc.azure-automation.net URL 终结点中\*使用的通配符 () 可替换为特定的工作区 ID。 工作区 ID 特定于环境和工作区。 可以在Microsoft 365 Defender门户中租户的“载入”部分中找到它。

\*.blob.core.windows.net URL 终结点可以替换为测试结果的“防火墙规则：\*.blob.core.windows.net”部分中显示的 URL。

> [!NOTE]
> 在通过Microsoft Defender for Cloud载入时，可以使用多个工作区。 需要在每个工作区 (的载入计算机上执行TestCloudConnection.exe过程，以确定工作区) 之间的 *.blob.core.windows.net URL 是否有任何更改。

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a>验证客户端与Microsoft Defender for Endpoint服务 URL 的连接

验证代理配置是否已成功完成。 然后，WinHTTP 可以发现并通过环境中的代理服务器进行通信，然后代理服务器将允许流量流向 Defender for Endpoint 服务 URL。

1. 将[Microsoft Defender for Endpoint客户端分析器工具](https://aka.ms/mdeanalyzer)下载到运行 Defender for Endpoint 传感器的电脑。 对于下层服务器，使用最新的预览版可[下载Microsoft Defender for Endpoint客户端分析器工具 Beta](https://aka.ms/BetaMDEAnalyzer)。

2. 提取设备上MDEClientAnalyzer.zip的内容。

3. 打开提升的命令行:
   1. 转到“**开始**”并键入“**cmd**”。
   1. 右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

4. 输入以下命令，再按 **Enter**：

    ```PowerShell
    HardDrivePath\MDEClientAnalyzer.cmd
    ```

    将 *HardDrivePath* 替换为下载 MDEClientAnalyzer 工具的路径。 例如：

    ```PowerShell
    C:\Work\tools\MDEClientAnalyzer\MDEClientAnalyzer.cmd
    ```

5. 该工具创建并提取要在 *HardDrivePath* 中使用的文件夹中的 *MDEClientAnalyzerResult.zip* 文件。

6. 打开 *MDEClientAnalyzerResult.txt* 并验证是否已执行代理配置步骤，以启用服务器发现和访问服务 URL。

   该工具检查 Defender for Endpoint 服务 URL 的连接性。 确保 Defender for Endpoint 客户端配置为交互。 该工具将打印每个 URL *的MDEClientAnalyzerResult.txt* 文件中的结果，这些 URL 可能用于与 Defender for Endpoint 服务通信。 例如：

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

如果任一连接选项返回 (200) 状态，则 Defender for Endpoint 客户端可以使用此连接方法正确地与测试的 URL 通信。

但是，如果连接检查结果显示失败，则会显示 HTTP 错误（请参阅 HTTP 状态代码）。 然后，可以使用表中显示的 URL，这些 URL 在 [代理服务器中启用对 Defender for Endpoint 服务 URL 的访问](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。 可用 URL 将取决于在载入过程中选择的区域。

> [!NOTE]
> 连接分析器工具的云连接检查与 [源自 PSExec 和 WMI 命令](attack-surface-reduction-rules-reference.md#block-process-creations-originating-from-psexec-and-wmi-commands)的攻击面减少规则阻止进程创建不兼容。 需要暂时禁用此规则才能运行连接工具。 或者，在运行分析器时，可以暂时添加 [ASR 排除项](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules) 。
>
> 在注册表中或通过 组策略 设置 TelemetryProxyServer 时，Defender for Endpoint 将回退，无法访问定义的代理。

## <a name="related-articles"></a>相关文章

- [使用组策略设置配置和管理Microsoft Defender 防病毒](use-group-policy-microsoft-defender-antivirus.md)
- [载入 Windows 设备](configure-endpoints.md)
- [排查Microsoft Defender for Endpoint载入问题](troubleshoot-onboarding.md)
