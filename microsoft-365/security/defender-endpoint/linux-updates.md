---
title: 部署 Linux 版 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何在企业环境中为 Linux 上的 Microsoft Defender for Endpoint 部署更新。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 更新， 部署
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fe979da9c3f1144e595f31048689cbb6f6f4e959
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61166850"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a>部署 Linux 版 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

Microsoft 会定期发布软件更新，以提高性能、安全性和提供新功能。

> [!WARNING]
> Linux 上的每个版本的 Defender for Endpoint 都有一个过期日期，此后它将不再继续保护你的设备。 必须在此日期之前更新产品。 若要检查到期日期，请运行以下命令：
> ```bash
> mdatp health --field product_expiration
> ```


适用于终结点的 Microsoft Defender 的公开发布功能是等效的，无论用于部署 (Beta (预览体验成员) 、预览版 (External) 、Current (Production) ) 的更新频道。


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
