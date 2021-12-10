---
title: 解决 Linux RHEL6 上的 Microsoft Defender for Endpoint 的问题
ms.reviewer: ''
description: 解决 Linux 上的 Microsoft Defender for Endpoint 的云连接问题
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 云， 连接， 通信
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 43a60d12883dc639c4ee5b831d305010cef58533
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61163634"
---
# <a name="troubleshoot-issues-for-microsoft-defender-for-endpoint-on-linux-rhel6"></a>解决 Linux RHEL6 上的 Microsoft Defender for Endpoint 的问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

本文提供有关如何解决在 Red Hat Linux 6 或 RHEL 6 或更高版本上使用 Microsoft Defender for Linux (可能会遇到) 的指南。 

安装程序包 (mdatp_XXX.XX.XX.XX.x86_64.rpm) 后，采取所提供的操作来验证安装是否成功。 


## <a name="check-the-service-health"></a>检查服务运行状况

使用以下命令检查服务运行状况：

```bash
mdatp health 
```

## <a name="verify-that-the-service-is-running"></a>验证服务是否正在运行

使用以下命令验证服务是否正在运行：

```bash
service mdatp status 
```

预期输出： `mdatp start/running, process 4517`

## <a name="verify-the-distribution-and-kernel-version"></a>验证分发和内核版本
分发和内核版本应位于受支持的列表中。

使用以下命令获取分发版本：

```bash
cat /etc/redhat-release (or /etc/system-release) 
```

使用以下命令获取内核版本：

```bash
uname -r
```
## <a name="check-if-mdatp-audisp-process-is-running"></a>检查 mdatp 的sp进程是否正在运行 
预期输出是进程正在运行。

使用以下命令检查：

```bash
pidof mdatp_audisp_plugin 
```

## <a name="check-talpa-modules"></a>检查 TALPA 模块
应加载九个模块。 

使用以下命令检查：

```bash
lsmod | grep talpa
```

预期输出：已启用

```bash
talpa_pedconnector       878  0 

talpa_pedevice          5189  2 talpa_pedconnector 

talpa_vfshook          32300  1 

talpa_vcdevice          4947  1 

talpa_syscall           9127  0 

talpa_core             90699  4 talpa_vfshook,talpa_vcdevice,talpa_syscall 

talpa_linux            29424  5 talpa_vfshook,talpa_vcdevice,talpa_syscall,talpa_core 

talpa_syscallhookprobe      882  0 

talpa_syscallhook      14987  2 talpa_vfshook,talpa_syscallhookprobe 
```


```bash
lsmod | grep talpa | wc -l 
```

预期输出：9

## <a name="check-talpa-status"></a>检查 TALPA 状态

```bash
cat /proc/sys/talpa/interceptors/VFSHookInterceptor/status 
```

调试日志文件 ("mdatp 诊断创建"捆绑包)  

```bash
/var/log/audit/audit.log 

/var/log/messages 

semanage fcontext -l > selinux.log 
```
 

性能和内存 

```bash
top -p <wdavdaemon pid>      

pmap -x <wdavdaemon pid> 
```

在哪里 `<wdavdaemon pid>` 可以使用 `pidof wdavdaemon` 找到。

