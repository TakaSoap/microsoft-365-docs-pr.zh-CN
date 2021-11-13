---
title: 为信息保护配置设备代理和 Internet 连接设置
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 为信息保护配置设备代理和 Internet 连接设置
ms.openlocfilehash: 645bb3eca60e37db817f810992fd5022399e1249
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950812"
---
# <a name="configure-device-proxy-and-internet-connection-settings-for-information-protection"></a>为信息保护配置设备代理和 Internet 连接设置

Microsoft Endpoint 技术使用 Microsoft Windows HTTP (WinHTTP) 报告数据并与 Microsoft 终结点云服务进行通信。 嵌入服务使用 LocalSystem 帐户在系统上下文中运行。

> [!TIP]
> 对于使用正向代理作为 Internet 网关的组织，可以使用网络保护来调查代理背后的情况。 有关详细信息，请参阅[调查正向代理背后发生的连接事件](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy)。

WinHTTP 配置设置独立于 Windows Internet (WinINet) Internet 浏览代理设置，并且只能使用以下自动发现方法来发现代理服务器：

- 透明代理
- Web 代理自动发现协议 (WPAD)

> [!NOTE]
> 如果在网络拓扑中使用透明代理或 WPAD，则不需要特殊的配置设置。 有关代理中 Defender for Endpoint URL 排除的更多信息，请参阅[在代理服务器中启用对 Defender for Endpoint 云服务 URL 的访问](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server)。

- 手动静态代理配置：
  - 基于注册表的配置
  - 使用 netsh 命令配置的 WinHTTP – 仅适用于稳定拓扑中的桌面（例如：同一代理后面的公司网络中的桌面）

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>使用基于注册表的静态代理手动配置代理服务器

对于不允许连接到 Internet 的端点设备，需要配置基于注册表的静态代理。 您需要将其配置为仅允许 Microsoft Endpoint DLP 报告诊断数据并与 Microsoft Endpoint 云服务通信。

静态代理可以通过组策略 (GP) 配置。 可以在以下位置找到组策略：

1. 打开 **“管理模板” > “Windows 组件” > “数据收集和预览版本” > “为连接的用户体验和遥测服务配置经验证的代理用法”**

2. 将其设置为“**已启用**”，然后选择 **禁止使用经验证的代理**：

   ![组策略设置 1 的图像。](../media/atp-gpo-proxy1.png)

3. 打开 **“管理模板” > “Windows 组件” > “数据收集和预览版” > “配置连接的用户体验和遥测”**：

   配置代理

   ![组策略设置 2 的图像。](../media/atp-gpo-proxy2.png)

   策略将注册表项 `HKLM\Software\Policies\Microsoft\Windows\DataCollection` 下的两个注册表值 `TelemetryProxyServer` 设置为 REG\u SZ，`DisableEnterpriseAuthProxy` 设置为 REG\u DWORD。

   注册表值 TelemetryProxyServer 的格式为：\<server name or ip\>\<port\>。 例如：**10.0.0.6:8080**

   此注册表值 `DisableEnterpriseAuthProxy` 应当设置为 1。

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>使用“netsh”命令手动配置代理服务器

使用 netsh 配置系统范围的静态代理。

> [!NOTE]
> 这将影响所有应用程序，包括使用带默认代理的 WinHTTP 的 Windows 服务。 -正在改变拓扑的笔记本电脑（例如：从办公室到家）将出现 netsh 故障。 使用基于注册表的静态代理配置。

1. 打开提升的命令行:
    1. 转到“**开始**”并键入“**cmd**”
    2. 右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

2. 输入以下命令，再按 **Enter**：

   `netsh winhttp set proxy <proxy>:<port>`

   例如：**netsh winhttp set proxy 10.0.0.6:8080**

3. 要重置 winhttp 代理，请输入以下命令并按 **Enter** 键：

   `netsh winhttp reset proxy`

若要了解详细信息。，请参见 [Netsh 命令语法、上下文和格式](/windows-server/networking/technologies/netsh/netsh-contexts)。

## <a name="enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server"></a>在代理服务器中启用对端点 DLP 云服务 URL 的访问

如果代理或防火墙在默认情况下阻止所有通信，并且只允许特定域通过，请将可下载工作表中列出的域添加到允许的域列表中。

此[可下载的电子表格](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)列出了网络必须能够连接到的服务及其关联的 URL。 应该确保没有防火墙或网络过滤规则会拒绝访问这些 URL，或者可能需要专门为它们创建允许规则。

如果代理或防火墙启用了 HTTPS 扫描（SSL 检查），则从 HTTPS 扫描中排除上表中列出的域。
如果代理或防火墙阻止匿名通信，因为端点 DLP 是从系统上下文连接的，请确保前面列出的 URL 中允许匿名通信。

## <a name="verify-client-connectivity-to-microsoft-cloud-service-urls"></a>验证客户端与 Microsoft 云服务 URL 的连接

验证代理配置是否成功完成，WinHTTP 是否可以在你的环境中发现代理服务器并通过代理服务器进行通信，以及代理服务器是否允许到 Defender for Endpoint 服务 URL 的通信。

1. 将 [MDATP 客户端分析器工具](https://aka.ms/mdatpanalyzer)下载到运行端点 DLP 的电脑上。
2. 提取设备上 MDATPClientAnalyzer.zip 的内容。
3. 打开提升的命令行:
    1. 转到“**开始**”并键入“**cmd**”。
    1. 右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。
4. 输入以下命令，再按 **Enter**：

   `HardDrivePath\MDATPClientAnalyzer.cmd`

   例如，用下载 MDATPClientAnalyzer 工具的路径替换 *HardDrivePath*

   **C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**

5. 在 _HardDrivePath* 中使用的文件夹中提取由工具创建的 **MDATPClientAnalyzerResult.zip** _ 文件。

6. 打开 **MDATPClientAnalyzerResult.txt** 并验证是否已执行代理配置步骤以启用服务器发现和对服务 URL 的访问。  该工具检查 Defender for Endpoint 客户端配置为与之交互的 Defender for Endpoint 服务 URL 的连接性。 然后，它将结果打印到每个可能用于与 Defender for Endpoint 服务进行通信的 URL 的 **MDATPClientAnalyzerResult.txt** 文件中。 例如：

   ```DOS
   Testing URL: https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command-line proxy: Doesn't exist
   ```

如果至少有一个连接选项返回 (200) 状态，则 Defender for Endpoint 客户端可以使用此连接方法与测试的 URL 正确通信。

但是，如果连接检查结果显示失败，则会显示 HTTP 错误（请参阅 HTTP 状态代码）。 然后可以使用[启用对端点 DLP 云服务 URL 的访问](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server)中所示的表中的 URL。 你将使用的 URL 将取决于载入过程中选择的区域。

> [!NOTE]
>
> Connectivity Analyzer 工具与 ASR 规则不兼容[阻止源自 PSExec 和 WMI 命令的进程创建](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules)。 需要暂时禁用此规则才能运行连接工具。
>
> 在注册表中或通过组策略设置 TelemetryProxyServer 时，如果 Defender for Endpoint 无法访问定义的代理，它将回退到 direct。相关主题：
>
> - 载入 Windows 10 设备
> - Microsoft Endpoint DLP 登录问题疑难解答

## <a name="see-also"></a>另请参阅

- [了解终结点数据丢失防护](endpoint-dlp-learn-about.md)
- [使用终结点数据丢失防护](endpoint-dlp-using.md)
- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [活动资源管理器入门](data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](/windows/security/threat-protection/)
- [Windows 10 设备的装载工具和方法](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [已建立 Azure AD 联接的设备](/azure/active-directory/devices/concept-azure-ad-join)
- [下载基于 Chromium 的新 Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
