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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 71c689143feca3d8c87d219a55c4ea42b4f9d950
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2022
ms.locfileid: "62767591"
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


无论用于部署 (Beta (预览体验成员) 、预览版 (External) 、Current (Production) ) 的部署更新频道，Microsoft Defender for Endpoint 功能都等效。


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

> [!IMPORTANT]
> 集成 Microsoft Defender for Endpoint 和 Defender for Cloud 时，mdatp 代理将默认自动接收更新。
