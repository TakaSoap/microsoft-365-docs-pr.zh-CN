---
title: 解决 macOS 上的 Microsoft Defender for Endpoint 的云连接问题
description: 本主题介绍如何解决 macOS 上的 Microsoft Defender for Endpoint 的云连接问题
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， 部署， 卸载， intune， jamf， macos， catalina， mojave， high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 291cd3016dcb4e1a321f39b4d2731ce2068b6544
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935205"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="f1367-104">解决 macOS 上的 Microsoft Defender for Endpoint 的云连接问题</span><span class="sxs-lookup"><span data-stu-id="f1367-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f1367-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f1367-105">**Applies to:**</span></span>
- [<span data-ttu-id="f1367-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f1367-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f1367-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1367-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="f1367-108">**平台** macOS</span><span class="sxs-lookup"><span data-stu-id="f1367-108">**Platform** macOS</span></span>

<span data-ttu-id="f1367-109">本主题介绍如何解决 macOS 上的 Microsoft Defender for Endpoint 的云连接问题。</span><span class="sxs-lookup"><span data-stu-id="f1367-109">This topic describes how to Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on macOS.</span></span>

## <a name="run-the-connectivity-test"></a><span data-ttu-id="f1367-110">运行连接测试</span><span class="sxs-lookup"><span data-stu-id="f1367-110">Run the connectivity test</span></span>
<span data-ttu-id="f1367-111">若要测试 Mac 上的 Defender for Endpoint 能否通过当前网络设置与云通信，请从命令行运行连接测试：</span><span class="sxs-lookup"><span data-stu-id="f1367-111">To test if Defender for Endpoint on Mac can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```Bash
mdatp connectivity test
```

<span data-ttu-id="f1367-112">预期输出：</span><span class="sxs-lookup"><span data-stu-id="f1367-112">expected output:</span></span>
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

<span data-ttu-id="f1367-113">如果连接测试失败，请检查设备是否具有 Internet 访问权限，以及[](microsoft-defender-endpoint-mac.md#network-connections)代理或防火墙是否阻止了产品所需的任何终结点。</span><span class="sxs-lookup"><span data-stu-id="f1367-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-mac.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="f1367-114">错误 35 或 60 的失败指示证书固定被拒绝，这表明 SSL 或 HTTPS 检查存在潜在问题。</span><span class="sxs-lookup"><span data-stu-id="f1367-114">Failures with curl error 35 or 60 indicate certificate pinning rejection, which indicates a potential issue with SSL or HTTPS inspection.</span></span> <span data-ttu-id="f1367-115">请参阅以下有关 SSL 检查配置的说明。</span><span class="sxs-lookup"><span data-stu-id="f1367-115">See instructions below regarding SSL inspection configuration.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a><span data-ttu-id="f1367-116">无代理或带代理自动配置的环境疑难解答步骤 (PAC) 或 Web 代理自动发现协议 (WPAD) </span><span class="sxs-lookup"><span data-stu-id="f1367-116">Troubleshooting steps for environments without proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD)</span></span>
<span data-ttu-id="f1367-117">使用以下过程可测试在没有代理或代理自动配置 (PAC) 或与 Web 代理自动发现协议 (WPAD) 的环境中是否阻止连接。</span><span class="sxs-lookup"><span data-stu-id="f1367-117">Use the following procedure to test that a connection is not blocked in an environment without a proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD).</span></span>

<span data-ttu-id="f1367-118">如果代理或防火墙阻止匿名流量，请确保允许匿名流量位于前面列出的 URL 中。</span><span class="sxs-lookup"><span data-stu-id="f1367-118">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="f1367-119">不支持经过身份验证的代理。</span><span class="sxs-lookup"><span data-stu-id="f1367-119">Authenticated proxies are not supported.</span></span> <span data-ttu-id="f1367-120">确保仅使用 PAC、WPAD 或静态代理。</span><span class="sxs-lookup"><span data-stu-id="f1367-120">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span> <span data-ttu-id="f1367-121">出于安全考虑，也不支持 SSL 检查和截获代理。</span><span class="sxs-lookup"><span data-stu-id="f1367-121">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="f1367-122">为 SSL 检查和代理服务器配置例外，以将数据从 macOS 上的 Microsoft Defender for Endpoint 直接传递到相关 URL，而不会拦截。</span><span class="sxs-lookup"><span data-stu-id="f1367-122">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint on macOS to the relevant URLs without interception.</span></span> <span data-ttu-id="f1367-123">将拦截证书添加到全局存储将不允许拦截。</span><span class="sxs-lookup"><span data-stu-id="f1367-123">Adding your interception certificate to the global store will not allow for interception.</span></span>
<span data-ttu-id="f1367-124">若要测试连接是否未阻止：在 Microsoft Edge for Mac 或 Safari 等浏览器中打开 https://x.cp.wd.microsoft.com/api/report https://cdn.x.cp.wd.microsoft.com/ping 和 。</span><span class="sxs-lookup"><span data-stu-id="f1367-124">To test that a connection is not blocked: In a browser such as Microsoft Edge for Mac or Safari open https://x.cp.wd.microsoft.com/api/report and https://cdn.x.cp.wd.microsoft.com/ping.</span></span>

<span data-ttu-id="f1367-125">（可选）在终端中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f1367-125">Optionally, in Terminal, run the following command:</span></span>

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

<span data-ttu-id="f1367-126">此命令的输出应类似于：</span><span class="sxs-lookup"><span data-stu-id="f1367-126">The output from this command should be similar to:</span></span>
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
