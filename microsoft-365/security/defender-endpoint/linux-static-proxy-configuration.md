---
title: Linux 静态代理发现上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何在 Linux 上为终结点配置 Microsoft Defender，以用于静态代理发现。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 安装， 代理
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
ms.openlocfilehash: 3b5061f0230a9704cb0fb9b80752c4d38954ad12
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168532"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a>在 Linux 上为静态代理发现配置 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

Microsoft Defender for Endpoint 可以使用环境变量发现 `HTTPS_PROXY` 代理服务器。 必须在安装 **时和安装** 产品后配置此设置。

## <a name="installation-time-configuration"></a>安装时间配置

在安装过程中 `HTTPS_PROXY` ，必须将环境变量传递给程序包管理器。 程序包管理器可以通过以下任一方式读取此变量：

- 变量 `HTTPS_PROXY` 用以下 `/etc/environment` 行定义：

  ```bash
  HTTPS_PROXY="http://proxy.server:port/"
  ```

- 变量 `HTTPS_PROXY` 在程序包管理器全局配置中定义。 例如，在 Ubuntu 18.04 中，可以将以下行添加到 `/etc/apt/apt.conf.d/proxy.conf` ：

  ```bash
  Acquire::https::Proxy "http://proxy.server:port/";
  ```

  > [!CAUTION]
  > 请注意，上述两种方法可定义要用于系统上其他应用程序的代理。 请谨慎使用此方法，或仅在本该配置是一般全局配置时使用此方法。

- 变量 `HTTPS_PROXY` 位于安装或卸载命令的之前。 例如，对于 APT 程序包管理器，在安装适用于 Endpoint 的 Microsoft Defender 时，按如下所示在变量前预置：

  ```bash
  HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
  ```

  > [!NOTE]
  > 请勿在环境变量定义和 apt 之间添加变量，否则不会传播变量。

在 `HTTPS_PROXY` 卸载过程中，环境变量可能同样定义。

请注意，如果需要代理但不配置代理，则安装和卸载不一定失败。 但是，将不会提交遥测，由于网络超时，操作可能需要更长时间。

## <a name="post-installation-configuration"></a>安装后配置

安装后，必须在 Defender for Endpoint 服务文件中 `HTTPS_PROXY` 定义环境变量。 为此，请运行 `sudo systemctl edit --full mdatp.service` 。
然后，可以通过以下两种方式之一将变量传播到服务：

- 取消注释行并 `#Environment="HTTPS_PROXY=http://address:port"` 指定静态代理地址。

- 添加一行 `EnvironmentFile=/path/to/env/file` 。 此路径可以指向 `/etc/environment` 或自定义文件，其中任一文件都需要添加以下行：

  ```bash
  HTTPS_PROXY="http://proxy.server:port/"
  ```

修改 `mdatp.service` 后，保存文件并重新启动服务，以便可以使用以下命令应用更改：

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```
