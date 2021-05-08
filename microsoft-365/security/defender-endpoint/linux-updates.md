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
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a>在 Linux 上部署 Microsoft Defender for Endpoint 更新

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft 会定期发布软件更新，以提高性能、安全性和提供新功能。

> [!WARNING]
> Linux 上的每个版本的 Defender for Endpoint 都有一个过期日期，此后它将不再继续保护你的设备。 必须在此日期之前更新产品。 若要检查到期日期，请运行以下命令：
> ```bash
> mdatp health --field product_expiration
> ```


无论用于部署 (Beta (预览体验成员) 、预览版 (External) 、Current (Production) ) 的 Microsoft Defender for Endpoint 功能都等效。


若要手动更新 Linux 上的 Defender for Endpoint，请执行以下命令之一：

## <a name="rhel-and-variants-centos-and-oracle-linux"></a>CentOS 和 Oracle Linux (RHEL 和) 

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a>SLES 和变量

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a>Ubuntu 和 Debian 系统

```bash
sudo apt-get install --only-upgrade mdatp
```
