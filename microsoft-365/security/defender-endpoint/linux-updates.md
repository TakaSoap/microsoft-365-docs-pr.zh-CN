---
title: 在 Linux 上部署 Microsoft Defender for Endpoint 更新
ms.reviewer: ''
description: 介绍如何在企业环境中为 Linux 上的 Microsoft Defender for Endpoint 部署更新。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 更新， 部署
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
ms.openlocfilehash: fc5a64f4be1b782c423c2ae9e2222a1424be97e0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274720"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="5be1d-104">在 Linux 上部署 Microsoft Defender for Endpoint 更新</span><span class="sxs-lookup"><span data-stu-id="5be1d-104">Deploy updates for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5be1d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5be1d-105">**Applies to:**</span></span>
- [<span data-ttu-id="5be1d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5be1d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5be1d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5be1d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5be1d-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="5be1d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5be1d-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="5be1d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="5be1d-110">Microsoft 会定期发布软件更新，以提高性能、安全性和提供新功能。</span><span class="sxs-lookup"><span data-stu-id="5be1d-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="5be1d-111">Linux 上的每个版本的 Defender for Endpoint 都有一个过期日期，此后它将不再继续保护你的设备。</span><span class="sxs-lookup"><span data-stu-id="5be1d-111">Each version of Defender for Endpoint on Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="5be1d-112">必须在此日期之前更新产品。</span><span class="sxs-lookup"><span data-stu-id="5be1d-112">You must update the product prior to this date.</span></span> <span data-ttu-id="5be1d-113">若要检查到期日期，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5be1d-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```


<span data-ttu-id="5be1d-114">无论用于部署 (Beta (预览体验成员) 、预览版 (External) 、Current (Production) ) 的 Microsoft Defender for Endpoint 功能都等效。</span><span class="sxs-lookup"><span data-stu-id="5be1d-114">Generally available Microsoft Defender for Endpoint capabilities are equivalent regardless update channel used for a deployment (Beta (Insider), Preview (External), Current (Production)).</span></span>


<span data-ttu-id="5be1d-115">若要手动更新 Linux 上的 Defender for Endpoint，请执行以下命令之一：</span><span class="sxs-lookup"><span data-stu-id="5be1d-115">To update Defender for Endpoint on Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="5be1d-116">CentOS 和 Oracle Linux (RHEL 和) </span><span class="sxs-lookup"><span data-stu-id="5be1d-116">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="5be1d-117">SLES 和变量</span><span class="sxs-lookup"><span data-stu-id="5be1d-117">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="5be1d-118">Ubuntu 和 Debian 系统</span><span class="sxs-lookup"><span data-stu-id="5be1d-118">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
