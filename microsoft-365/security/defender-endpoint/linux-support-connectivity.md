---
title: 解决 Linux 上的 Microsoft Defender for Endpoint 的云连接问题
ms.reviewer: ''
description: 了解如何解决 Linux 上的 Microsoft Defender for Endpoint 的云连接问题
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 云， 连接， 通信
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4f547e6701e0b22c2d55d0fa68a236f85b821a11
ms.sourcegitcommit: 43adb0d91af234c34e22d450a9c1d26aa745c2ca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2021
ms.locfileid: "60478909"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a>解决 Linux 上的 Microsoft Defender for Endpoint 的云连接问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

## <a name="run-the-connectivity-test"></a>运行连接测试

若要测试 Linux 上的 Defender for Endpoint 能否通过当前网络设置与云通信，请从命令行运行连接测试：

```bash
mdatp connectivity test
```

预期输出：

```output
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

如果连接测试失败，请检查设备是否具有 Internet 访问权限，以及[](microsoft-defender-endpoint-linux.md#network-connections)代理或防火墙是否阻止了产品所需的任何终结点。

错误 35 或 60 的失败表示证书固定被拒绝。 请检查连接是否位于 SSL 或 HTTPS 检查下。 如果是这样，将 Microsoft Defender for Endpoint 添加到允许列表。

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a>无代理或具有透明代理的环境疑难解答步骤

若要测试在没有代理或具有透明代理的环境中连接是否被阻止，在终端中运行以下命令：

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

此命令的输出应类似于：

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a>使用静态代理的环境疑难解答步骤

> [!WARNING]
> 不支持 PAC、WPAD 和经过身份验证的代理。 确保仅使用静态代理或透明代理。
>
> 出于安全考虑，也不支持 SSL 检查和截获代理。 为 SSL 检查和代理服务器配置例外，以将数据从 Linux 上的 Defender for Endpoint 直接传递到相关 URL，而不会拦截。 将拦截证书添加到全局存储将不允许拦截。

如果需要静态代理，则向上述命令添加代理参数，其中 `proxy_address:port` 对应于代理地址和端口：

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

确保使用与文件中配置相同的代理地址和 `/lib/system/system/mdatp.service` 端口。 如果上述命令出错，请检查代理配置。

若要设置 mdatp 的代理，请使用以下命令：

```bash
mdatp config proxy set --value http://address:port 
```


成功后，尝试从命令行进行另一个连接测试：

```bash
mdatp connectivity test
```

如果问题仍然存在，请联系客户支持部门。

## <a name="resources"></a>资源

- 若要详细了解如何将产品配置为使用静态代理，请参阅为静态代理发现配置[Microsoft Defender for Endpoint。](linux-static-proxy-configuration.md)
