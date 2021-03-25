---
title: 部署适用于 Linux 的 Microsoft Defender ATP 的更新
ms.reviewer: ''
description: 介绍如何在企业环境中部署适用于 Linux 的 Microsoft Defender ATP 更新。
keywords: microsoft， defender， atp， linux， 更新， 部署
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ad37427e8134c574690c3b3553d7fb9b8507593c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187717"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="f32b9-104">部署适用于 Linux 的 Microsoft Defender for Endpoint 的更新</span><span class="sxs-lookup"><span data-stu-id="f32b9-104">Deploy updates for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f32b9-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f32b9-105">**Applies to:**</span></span>
- [<span data-ttu-id="f32b9-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f32b9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f32b9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f32b9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f32b9-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="f32b9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f32b9-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f32b9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="f32b9-110">Microsoft 会定期发布软件更新，以提高性能、安全性和提供新功能。</span><span class="sxs-lookup"><span data-stu-id="f32b9-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="f32b9-111">适用于 Linux 的 Defender for Endpoint 的每个版本都有一个过期日期，此后它将不再继续保护你的设备。</span><span class="sxs-lookup"><span data-stu-id="f32b9-111">Each version of Defender for Endpoint for Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="f32b9-112">必须在此日期之前更新产品。</span><span class="sxs-lookup"><span data-stu-id="f32b9-112">You must update the product prior to this date.</span></span> <span data-ttu-id="f32b9-113">若要检查到期日期，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f32b9-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```

<span data-ttu-id="f32b9-114">若要手动更新适用于 Linux 的 Defender for Endpoint，请执行以下命令之一：</span><span class="sxs-lookup"><span data-stu-id="f32b9-114">To update Defender for Endpoint for Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="f32b9-115">CentOS 和 Oracle Linux (RHEL 和) </span><span class="sxs-lookup"><span data-stu-id="f32b9-115">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="f32b9-116">SLES 和变量</span><span class="sxs-lookup"><span data-stu-id="f32b9-116">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="f32b9-117">Ubuntu 和 Debian 系统</span><span class="sxs-lookup"><span data-stu-id="f32b9-117">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
