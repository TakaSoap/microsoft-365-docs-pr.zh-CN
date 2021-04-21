---
title: Linux 静态代理发现上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何在 Linux 上为终结点配置 Microsoft Defender，以用于静态代理发现。
keywords: microsoft， defender， atp， linux， 安装， 代理
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e59727b6bb5fca58595764fc003009891546d8f6
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903842"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a><span data-ttu-id="35d79-104">在 Linux 上为静态代理发现配置 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="35d79-104">Configure Microsoft Defender for Endpoint on Linux for static proxy discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="35d79-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="35d79-105">**Applies to:**</span></span>
- [<span data-ttu-id="35d79-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="35d79-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="35d79-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35d79-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="35d79-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="35d79-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="35d79-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="35d79-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="35d79-110">Microsoft Defender for Endpoint 可以使用环境变量发现 ```HTTPS_PROXY``` 代理服务器。</span><span class="sxs-lookup"><span data-stu-id="35d79-110">Microsoft Defender for Endpoint can discover a proxy server using the ```HTTPS_PROXY``` environment variable.</span></span> <span data-ttu-id="35d79-111">必须在安装 **时和安装** 产品后配置此设置。</span><span class="sxs-lookup"><span data-stu-id="35d79-111">This setting must be configured **both** at installation time and after the product has been installed.</span></span>

## <a name="installation-time-configuration"></a><span data-ttu-id="35d79-112">安装时间配置</span><span class="sxs-lookup"><span data-stu-id="35d79-112">Installation time configuration</span></span>

<span data-ttu-id="35d79-113">在安装过程中 ```HTTPS_PROXY``` ，必须将环境变量传递给程序包管理器。</span><span class="sxs-lookup"><span data-stu-id="35d79-113">During installation, the ```HTTPS_PROXY``` environment variable must be passed to the package manager.</span></span> <span data-ttu-id="35d79-114">程序包管理器可以通过以下任一方式读取此变量：</span><span class="sxs-lookup"><span data-stu-id="35d79-114">The package manager can read this variable in any of the following ways:</span></span>

- <span data-ttu-id="35d79-115">变量 ```HTTPS_PROXY``` 在 中定义 ```/etc/environment``` ，并包含以下行：</span><span class="sxs-lookup"><span data-stu-id="35d79-115">The ```HTTPS_PROXY``` variable is defined in ```/etc/environment``` with the following line:</span></span>

    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

- <span data-ttu-id="35d79-116">变量 `HTTPS_PROXY` 在程序包管理器全局配置中定义。</span><span class="sxs-lookup"><span data-stu-id="35d79-116">The `HTTPS_PROXY` variable is defined in the package manager global configuration.</span></span> <span data-ttu-id="35d79-117">例如，在 Ubuntu 18.04 中，可以将以下行添加到 `/etc/apt/apt.conf.d/proxy.conf` ：</span><span class="sxs-lookup"><span data-stu-id="35d79-117">For example, in Ubuntu 18.04, you can add the following line to `/etc/apt/apt.conf.d/proxy.conf`:</span></span>
  
    ```bash
    Acquire::https::Proxy "http://proxy.server:port/";
    ```

    > [!CAUTION]
    > <span data-ttu-id="35d79-118">请注意，上述两种方法可定义要用于系统上其他应用程序的代理。</span><span class="sxs-lookup"><span data-stu-id="35d79-118">Note that above two methods could define the proxy to use for other applications on your system.</span></span> <span data-ttu-id="35d79-119">请谨慎使用此方法，或仅在本该配置是一般全局配置时使用此方法。</span><span class="sxs-lookup"><span data-stu-id="35d79-119">Use this method with caution, or only if this is meant to be a generally global configuration.</span></span>
  
- <span data-ttu-id="35d79-120">变量 `HTTPS_PROXY` 位于安装或卸载命令的之前。</span><span class="sxs-lookup"><span data-stu-id="35d79-120">The `HTTPS_PROXY` variable is prepended to the installation or uninstallation commands.</span></span> <span data-ttu-id="35d79-121">例如，使用 APT 程序包管理器，在安装适用于 Endpoint 的 Microsoft Defender 时，按如下所示在变量前预置：</span><span class="sxs-lookup"><span data-stu-id="35d79-121">For example, with the APT package manager, prepend the variable as follows when installing Microsoft Defender for Endpoint:</span></span> 

    ```bash  
    HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
    ```

    > [!NOTE]
    > <span data-ttu-id="35d79-122">请勿在环境变量定义和 apt 之间添加变量，否则不会传播变量。</span><span class="sxs-lookup"><span data-stu-id="35d79-122">Do not add sudo between the environment variable definition and apt, otherwise the variable will not be propagated.</span></span>

<span data-ttu-id="35d79-123">在 `HTTPS_PROXY` 卸载过程中，环境变量可能同样定义。</span><span class="sxs-lookup"><span data-stu-id="35d79-123">The `HTTPS_PROXY` environment variable may similarly be defined during uninstallation.</span></span>

<span data-ttu-id="35d79-124">请注意，如果需要代理但不配置代理，安装和卸载不一定失败。</span><span class="sxs-lookup"><span data-stu-id="35d79-124">Note that installation and uninstallation will not necessarily fail if a proxy is required but not configured.</span></span> <span data-ttu-id="35d79-125">但是，将不会提交遥测，由于网络超时，操作可能需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="35d79-125">However, telemetry will not be submitted, and the operation could take much longer due to network timeouts.</span></span>

## <a name="post-installation-configuration"></a><span data-ttu-id="35d79-126">安装后配置</span><span class="sxs-lookup"><span data-stu-id="35d79-126">Post installation configuration</span></span>
  
<span data-ttu-id="35d79-127">安装后，必须在 Defender for Endpoint 服务文件中 `HTTPS_PROXY` 定义环境变量。</span><span class="sxs-lookup"><span data-stu-id="35d79-127">After installation, the `HTTPS_PROXY` environment variable must be defined in the Defender for Endpoint service file.</span></span> <span data-ttu-id="35d79-128">为此，在 `/lib/systemd/system/mdatp.service` 作为根用户运行时，在文本编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="35d79-128">To do this, open `/lib/systemd/system/mdatp.service` in a text editor while running as the root user.</span></span> <span data-ttu-id="35d79-129">然后，可以通过以下两种方式之一将变量传播到服务：</span><span class="sxs-lookup"><span data-stu-id="35d79-129">You can then propagate the variable to the service in one of two ways:</span></span>

- <span data-ttu-id="35d79-130">取消注释行并 `#Environment="HTTPS_PROXY=http://address:port"` 指定静态代理地址。</span><span class="sxs-lookup"><span data-stu-id="35d79-130">Uncomment the line `#Environment="HTTPS_PROXY=http://address:port"` and specify your static proxy address.</span></span>

- <span data-ttu-id="35d79-131">添加一行 `EnvironmentFile=/path/to/env/file` 。</span><span class="sxs-lookup"><span data-stu-id="35d79-131">Add a line `EnvironmentFile=/path/to/env/file`.</span></span> <span data-ttu-id="35d79-132">此路径可以指向 `/etc/environment` 或自定义文件，其中任一文件都需要添加以下行：</span><span class="sxs-lookup"><span data-stu-id="35d79-132">This path can point to `/etc/environment` or a custom file, either of which needs to add the following line:</span></span>
  
    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

<span data-ttu-id="35d79-133">修改文件 `mdatp.service` 后，保存并关闭它。</span><span class="sxs-lookup"><span data-stu-id="35d79-133">After modifying the `mdatp.service` file, save and close it.</span></span> <span data-ttu-id="35d79-134">重新启动服务，以便可以应用更改。</span><span class="sxs-lookup"><span data-stu-id="35d79-134">Restart the service so the changes can be applied.</span></span> <span data-ttu-id="35d79-135">在 Ubuntu 中，这包括两个命令：</span><span class="sxs-lookup"><span data-stu-id="35d79-135">In Ubuntu, this involves two commands:</span></span>  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
