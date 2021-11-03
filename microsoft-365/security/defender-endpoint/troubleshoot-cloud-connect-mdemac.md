---
title: 解决 macOS 上的 Microsoft Defender for Endpoint 的云连接问题
description: 本主题介绍如何解决 macOS 上的 Microsoft Defender for Endpoint 的云连接问题
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， 部署， 卸载， intune， jamf， macos， catalina， mojave， high sierra
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0cdf2bbedb7dbfb5d3a87d6b28b441998283f3cb
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60659380"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a>解决 macOS 上的 Microsoft Defender for Endpoint 的云连接问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**平台** macOS

本主题介绍如何解决 macOS 上的 Microsoft Defender for Endpoint 的云连接问题。

## <a name="run-the-connectivity-test"></a>运行连接测试
若要测试 Mac 上的 Defender for Endpoint 能否通过当前网络设置与云通信，请从命令行运行连接测试：

```Bash
mdatp connectivity test
```

预期输出：
```Bash
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

如果连接测试失败，请检查设备是否具有 Internet 访问权限，以及[](microsoft-defender-endpoint-mac.md#network-connections)代理或防火墙是否阻止了产品所需的任何终结点。

错误 35 或 60 的失败指示证书固定被拒绝，这表明 SSL 或 HTTPS 检查存在潜在问题。 请参阅以下有关 SSL 检查配置的说明。

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a>无代理或无代理自动配置的环境疑难解答步骤 (PAC) 或 Web 代理自动发现协议 (WPAD) 
使用以下过程可测试在没有代理的环境中，或者没有代理自动配置 (PAC) 或与 Web 代理自动发现协议 (WPAD) 的连接未被阻止。

如果代理或防火墙阻止匿名流量，请确保允许匿名流量位于前面列出的 URL 中。

> [!WARNING]
> 不支持经过身份验证的代理。 确保仅使用 PAC、WPAD 或静态代理。 出于安全考虑，也不支持 SSL 检查和截获代理。 为 SSL 检查和代理服务器配置例外，以将数据从 macOS 上的 Microsoft Defender for Endpoint 直接传递到相关 URL，而不会拦截。 将拦截证书添加到全局存储将不允许拦截。
若要测试连接是否未阻止：在浏览器（如 Microsoft Edge for Mac 或 Safari）中打开 https://x.cp.wd.microsoft.com/api/report https://cdn.x.cp.wd.microsoft.com/ping 和 。

（可选）在终端中，运行以下命令：

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

此命令的输出应类似于：
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
