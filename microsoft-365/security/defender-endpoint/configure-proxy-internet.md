---
title: 配置设备代理和 Internet 连接设置
description: 配置 Microsoft Defender for Endpoint 代理和 Internet 设置以启用与云服务的通信。
keywords: 配置， 代理， Internet， Internet 连接， 设置， 代理设置， netsh， winhttp， 代理服务器
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: caefcd7ce19073a10139a9f4d6d84c49e93c392f
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2021
ms.locfileid: "53623344"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a>配置设备代理和 Internet 连接设置

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)。

Defender for Endpoint 传感器需要 Microsoft Windows HTTP (WinHTTP) 报告传感器数据并与 Defender for Endpoint 服务通信。

嵌入的 Defender for Endpoint 传感器使用 LocalSystem 帐户在系统上下文中运行。 该传感器使用 Microsoft Windows Http Services (WinHTTP) 启用与 Defender for Endpoint 云服务的通信。

> [!TIP]
> 对于使用正向代理作为 Internet 网关的组织，可以使用网络保护来调查代理背后的情况。 有关详细信息，请参阅[调查正向代理背后发生的连接事件](investigate-behind-proxy.md)。

WinHTTP 配置设置独立于 Windows Internet (WinINet) Internet 浏览代理设置，并且只能使用下列发现方法发现代理服务器：

- 自动发现方法：
  - 透明代理
  - Web 代理自动发现协议 (WPAD)

    > [!NOTE]
    > 如果在网络拓扑中使用的是透明代理或 WPAD，则不需要特殊的配置设置。 有关代理中的 Defender 终结点 URL 排除项详细信息，请参阅在代理服务器中启用对 [Defender for Endpoint 服务 URL 的访问](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。

- 手动静态代理配置：

  - 基于注册表的配置
  - 使用 netsh 命令配置的 WinHTTP：仅适用于稳定拓扑中的桌面 (例如：企业网络中位于同一代理服务器后面的桌面) 

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>使用基于注册表的静态代理手动配置代理服务器

配置基于注册表的静态代理，以允许仅 Defender for Endpoint 传感器报告诊断数据，并与 Defender for Endpoint 服务进行通信（如果不允许计算机连接到 Internet）。

> [!NOTE]
> 在 Windows 10 或 Windows Server 2019 上使用此选项时，建议将以下 (或更高版本) 内部版本和累积更新汇总：
>
> - Windows 10 版本 1809或 Windows Server 2019 -<https://support.microsoft.com/kb/5001384>
> - Windows 10，版本 1909 -<https://support.microsoft.com/kb/4601380>
> - Windows 10，版本 2004 -<https://support.microsoft.com/kb/4601382>
> - Windows 10，版本 20H2 -<https://support.microsoft.com/kb/4601382>
>
> 这些更新改进了 CnC (Command and Control) 连接和可靠性。

静态代理可以通过组策略 (GP) 配置。 可以在以下位置找到组策略：

- **管理模板> Windows数据收集>预览>配置连接的用户体验和遥测服务的已验证代理使用情况**

  将其设置为"**已启用"，** 然后选择 **"禁用经过身份验证的代理用法"。**

  ![组策略设置的图像1](images/atp-gpo-proxy1.png)

- **配置连接> Windows遥测>数据收集** 和预览>管理模板和组件：

  配置代理

  ![组策略设置 2 的图像](images/atp-gpo-proxy2.png)

  该策略在注册表项 下REG_SZ `TelemetryProxyServer` `DisableEnterpriseAuthProxy` 和 REG_DWORD两个注册表值 `HKLM\Software\Policies\Microsoft\Windows\DataCollection` 。

  注册表值 `TelemetryProxyServer` 采用以下字符串格式：

  ```text
  <server name or ip>:<port>
  ```

  例如：10.0.0.6:8080

  此注册表值 `DisableEnterpriseAuthProxy` 应当设置为 1。

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>使用 netsh 命令手动配置代理服务器

使用 netsh 配置系统范围的静态代理。

> [!NOTE]
>
> - 这将影响所有应用程序，包括使用带默认代理的 WinHTTP 的 Windows 服务。</br>
> - 更改拓扑结构（例如 (：从办公室到家庭) netsh 将发生故障。 使用基于注册表的静态代理配置。

1. 打开提升的命令行：
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

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a>在代理服务器中启用对 Microsoft Defender for Endpoint 服务 URL 的访问

如果代理或防火墙在默认情况下阻止所有通信，并且只允许特定域通过，请将可下载工作表中列出的域添加到允许的域列表中。

以下可下载的电子表格列出了网络必须能够连接到的服务及其关联 URL。 应确保没有拒绝访问这些 URL 的防火墙或网络筛选规则，或者您可能需要专门为它们创建允许规则。 

<br>

**** 
|域列表电子表格|说明|
|---|---|
|![适用于终结点 URL 电子表格的 Microsoft Defender 缩略图](images/mdatp-urls.png)|服务位置、地理位置和操作系统的特定 DNS 记录的电子表格。 <p> [在此处下载电子表格。](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)|
|

如果代理或防火墙启用了 HTTPS 扫描（SSL 检查），则从 HTTPS 扫描中排除上表中列出的域。

> [!NOTE]
> settings-win.data.microsoft.com 运行版本 1803 或Windows 10的设备时，才需要此配置。<br>
>
> 仅在运行版本 1803 或更高版本的设备Windows 10包含 v20 的 URL 才需要。 例如，运行版本 1803 或Windows 10并载入到美国数据安全中心区域的设备 `us-v20.events.data.microsoft.com` 存储。
>
> 如果你正在Microsoft Defender 防病毒，请参阅配置与 Microsoft Defender 防病毒[云服务的网络连接](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)。

如果代理或防火墙阻止匿名流量，因为 Defender for Endpoint 传感器从系统上下文连接，请确保允许匿名流量位于前面列出的 URL 中。

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a>Microsoft Monitoring Agent (MMA) Windows - 旧版客户端或 Windows 服务器的代理和防火墙要求

以下信息列出了与 Log Analytics 代理通信所需的代理和防火墙配置信息 (对于早期版本的 Windows（如 Windows 7 SP1、Windows 8.1、Windows Server 2008 R2、Windows Server 2012 R2 和 Windows Server 2016）通常称为 Microsoft Monitoring Agent) 。

<br>

****

|代理资源|端口|方向|绕过 HTTPS 检查|
|---|---|---|---|
|*.ods.opinsights.azure.com|端口 443|出站|是|
|*.oms.opinsights.azure.com|端口 443|出站|是|
|*.blob.core.windows.net|端口 443|出站|是|
|*.azure-automation.net|端口 443|出站|是|

> [!NOTE]
> 作为基于云的解决方案，IP 范围可能会更改。 建议移动到 DNS 解析设置。

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a>确认Microsoft Monitoring Agent (MMA) 服务 URL 要求 

请参阅以下指南，在将 Microsoft Monitoring Agent (MMA) 用于早期版本的 Windows 时，为特定环境消除通配符 (*) 要求。

1. 有关使用 Microsoft Monitoring Agent (MMA) 的以前操作系统载入到 Defender for Endpoint (中有关详细信息，请参阅在[Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326)上载入以前版本的 Windows 和[载入 Windows 服务器](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)。

2. 确保计算机已成功报告到 Microsoft 365 Defender 门户。

3. 从"C：\Program Files\Microsoft Monitoring Agent\Agent"运行 TestCloudConnection.exe 工具，以验证连接并查看特定工作区所需的 URL。

4. 请查看 Microsoft Defender 终结点 URL 列表，了解你的地区要求的完整 (请参阅服务 URL[电子表格) 。](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

    ![网站中的管理员Windows PowerShell](images/admin-powershell.png)

. () .ods.opinsights.azure.com、.oms.opinsights.azure.com 和 .agentsvc.azure-automation.net URL 终结点中使用的通配符可以替换为 \* \* \* \* 特定的工作区 ID。 工作区 ID 特定于你的环境和工作区，可在租户门户内的"载入"Microsoft 365 Defender部分。

.blob.core.windows.net URL 终结点可以替换为测试结果的"防火墙规则 \* ： \* .blob.core.windows.net"部分中显示的 URL。

> [!NOTE]
> 如果通过 Azure Defender 载入，可能使用多个工作区。 你需要在每个工作区 (的已载入计算机上执行上述 TestCloudConnection.exe 过程，以确定工作区和工作区之间的 *.blob.core.windows.net URL) 。

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a>验证与 Microsoft Defender for Endpoint 服务 URL 的客户端连接

验证代理配置是否成功完成，WinHTTP 是否可以在你的环境中发现代理服务器并通过代理服务器进行通信，以及代理服务器是否允许到 Defender for Endpoint 服务 URL 的通信。

1. 将 [Micrsofot Defender for Endpoint Client Analyzer](https://aka.ms/mdeanalyzer) 工具下载到运行 Defender for Endpoint 传感器的电脑。

2. 提取设备上MDEClientAnalyzer.zip内容。

3. 打开提升的命令行：
   1. 转到“**开始**”并键入“**cmd**”。
   1. 右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

4. 输入以下命令，再按 **Enter**：

    ```PowerShell
    HardDrivePath\MDEClientAnalyzer.cmd
    ```

    将 *HardDrivePath* 替换为下载 MDEClientAnalyzer 工具的路径，例如：

    ```PowerShell
    C:\Work\tools\MDEClientAnalyzer\MDEClientAnalyzer.cmd
    ```

5. 提取 *MDEClientAnalyzerResult.zip**在 HardDrivePath* 中使用的文件夹中创建的文件。

6. 打开 *MDEClientAnalyzerResult.txt* 并验证是否执行了代理配置步骤，以启用服务器发现和访问服务 URL。

   该工具检查 Defender for Endpoint 客户端配置为与之交互的 Defender for Endpoint 服务 URL 的连接性。 然后，它会将每个 URL的结果输出到MDEClientAnalyzerResult.txt文件中，这些 URL 可能用于与 Defender for Endpoint 服务进行通信。 例如：

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

如果至少有一个连接选项返回 (200) 状态，则 Defender for Endpoint 客户端可以使用此连接方法与测试的 URL 正确通信。

但是，如果连接检查结果显示失败，则会显示 HTTP 错误（请参阅 HTTP 状态代码）。 然后，可以使用在代理服务器 中启用对 Defender [for Endpoint 服务 URL](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)的访问中显示的表中的 URL。 将使用的 URL 取决于在载入过程中选择的区域。

> [!NOTE]
> 连接分析器工具云连接检查与攻击面减少规则阻止源自 [PSExec](/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules.md#block-process-creations-originating-from-psexec-and-wmi-commands)和 WMI 命令的进程创建不兼容。 需要暂时禁用此规则才能运行连接工具。 或者，可以在运行分析器时临时添加 [ASR](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction.md#exclude-files-and-folders) 排除项。
>
> 当在注册表中或通过组策略设置 TelemetryProxyServer 时，如果 Defender for Endpoint 无法访问定义的代理，它将回退到直接。

## <a name="related-topics"></a>相关主题

- [载入 Windows 10 设备](configure-endpoints.md)
- [Microsoft Defender 终结点载入问题疑难解答](troubleshoot-onboarding.md)
