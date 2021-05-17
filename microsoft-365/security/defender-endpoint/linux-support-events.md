---
title: 解决 Linux 上的 Microsoft Defender for Endpoint 的缺失事件或警报问题
description: 解决 Linux 上的 Microsoft Defender for Endpoint 中缺少的事件或警报问题。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 事件
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
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7de216c1397a7cc4806af8221257eeedd2290830
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933309"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="724b9-104">解决 Linux 上的 Microsoft Defender for Endpoint 的缺失事件或警报问题</span><span class="sxs-lookup"><span data-stu-id="724b9-104">Troubleshoot missing events or alerts issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="724b9-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="724b9-105">**Applies to:**</span></span>

- [<span data-ttu-id="724b9-106">Microsoft Defender for Endpoint on Linux</span><span class="sxs-lookup"><span data-stu-id="724b9-106">Microsoft Defender for Endpoint on Linux</span></span>](microsoft-defender-endpoint-linux.md)

<span data-ttu-id="724b9-107">本文提供了一些常规步骤，以减少安全中心门户中丢失的事件 [或](https://securitycenter.windows.com/) 警报。</span><span class="sxs-lookup"><span data-stu-id="724b9-107">This article provides some general steps to mitigate missing events or alerts in the [security center](https://securitycenter.windows.com/) portal.</span></span>

<span data-ttu-id="724b9-108">在 **设备上** 正确安装 Microsoft Defender for Endpoint 后 _，将在门户_ 中生成设备页面。</span><span class="sxs-lookup"><span data-stu-id="724b9-108">Once **Microsoft Defender for Endpoint** has been installed properly on a device, a _device page_ will be generated in the portal.</span></span> <span data-ttu-id="724b9-109">可以在设备页面的时间线选项卡或高级搜寻页面中查看所有记录的事件。</span><span class="sxs-lookup"><span data-stu-id="724b9-109">You can review all recorded events in the timeline tab in the device page, or in advanced hunting page.</span></span> <span data-ttu-id="724b9-110">本节将解决缺失某些或所有预期事件的情况。</span><span class="sxs-lookup"><span data-stu-id="724b9-110">This section troubleshoots the case of some or all expected events are missing.</span></span>
<span data-ttu-id="724b9-111">例如，如果缺少 _所有 CreatedFile_ 事件。</span><span class="sxs-lookup"><span data-stu-id="724b9-111">For instance, if all _CreatedFile_ events are missing.</span></span>

## <a name="missing-network-and-login-events"></a><span data-ttu-id="724b9-112">缺少网络和登录事件</span><span class="sxs-lookup"><span data-stu-id="724b9-112">Missing network and login events</span></span>

<span data-ttu-id="724b9-113">Microsoft Defender for Endpoint 利用 `audit` linux 中的框架跟踪网络和登录活动。</span><span class="sxs-lookup"><span data-stu-id="724b9-113">Microsoft Defender for Endpoint utilized `audit` framework from linux to track network and login activity.</span></span>

1. <span data-ttu-id="724b9-114">确保审核框架正常工作。</span><span class="sxs-lookup"><span data-stu-id="724b9-114">Make sure audit framework is working.</span></span>

    ```bash
    service auditd status
    ```

    <span data-ttu-id="724b9-115">预期输出：</span><span class="sxs-lookup"><span data-stu-id="724b9-115">expected output:</span></span>

    ```output
    ● auditd.service - Security Auditing Service
    Loaded: loaded (/usr/lib/systemd/system/auditd.service; enabled; vendor preset: enabled)
    Active: active (running) since Mon 2020-12-21 10:48:02 IST; 2 weeks 0 days ago
        Docs: man:auditd(8)
            https://github.com/linux-audit/audit-documentation
    Process: 16689 ExecStartPost=/sbin/augenrules --load (code=exited, status=1/FAILURE)
    Process: 16665 ExecStart=/sbin/auditd (code=exited, status=0/SUCCESS)
    Main PID: 16666 (auditd)
        Tasks: 25
    CGroup: /system.slice/auditd.service
            ├─16666 /sbin/auditd
            ├─16668 /sbin/audispd
            ├─16670 /usr/sbin/sedispatch
            └─16671 /opt/microsoft/mdatp/sbin/mdatp_audisp_plugin -d
    ```

2. <span data-ttu-id="724b9-116">如果 `auditd` 标记为已停止，请启动它。</span><span class="sxs-lookup"><span data-stu-id="724b9-116">If `auditd` is marked as stopped, start it.</span></span>

    ```bash
    service auditd start
    ```

<span data-ttu-id="724b9-117">**在 SLES** 系统上，默认情况下可能会禁用 中的 SYSCALL 审核，并可以说明 `auditd` 缺少事件。</span><span class="sxs-lookup"><span data-stu-id="724b9-117">**On SLES** systems, SYSCALL auditing in `auditd` might be disabled by default and can be accounted for missing events.</span></span>

1. <span data-ttu-id="724b9-118">若要验证 SYSCALL 审核是否未禁用，请列出当前的审核规则：</span><span class="sxs-lookup"><span data-stu-id="724b9-118">To validate that SYSCALL auditing is not disabled, list the current audit rules:</span></span>

    ```bash
    sudo auditctl -l
    ```

    <span data-ttu-id="724b9-119">如果存在以下行，请将其删除或编辑它以允许 Microsoft Defender for Endpoint 跟踪特定的 SYSCALLs。</span><span class="sxs-lookup"><span data-stu-id="724b9-119">if the following line is present, remove it or edit it to enable Microsoft Defender for Endpoint to track specific SYSCALLs.</span></span>

    ```output
    -a task, never
    ```

    <span data-ttu-id="724b9-120">审核规则位于 `/etc/audit/rules.d/audit.rules` 。</span><span class="sxs-lookup"><span data-stu-id="724b9-120">audit rules are located at `/etc/audit/rules.d/audit.rules`.</span></span>

## <a name="missing-file-events"></a><span data-ttu-id="724b9-121">缺少文件事件</span><span class="sxs-lookup"><span data-stu-id="724b9-121">Missing file events</span></span>

<span data-ttu-id="724b9-122">文件事件通过框架 `fanotify` 收集。</span><span class="sxs-lookup"><span data-stu-id="724b9-122">File events are collected with `fanotify` framework.</span></span> <span data-ttu-id="724b9-123">如果缺少某些或所有文件事件，请确保在设备上启用并且 `fanotify` 文件系统受 [支持](microsoft-defender-endpoint-linux.md#system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="724b9-123">In case some or all file events are missing, make sure `fanotify` is enabled on the device and that the file system is [supported](microsoft-defender-endpoint-linux.md#system-requirements).</span></span>

<span data-ttu-id="724b9-124">列出计算机上具有以下项的文件系统：</span><span class="sxs-lookup"><span data-stu-id="724b9-124">List the filesystems on the machine with:</span></span>

```bash
df -Th
```
