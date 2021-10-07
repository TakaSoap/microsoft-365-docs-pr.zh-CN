---
title: 解决 Linux 上的 Microsoft Defender for Endpoint 的性能问题
description: 解决 Linux 上的 Microsoft Defender for Endpoint 中的性能问题。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 性能
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6a37c5e1594567d96d7517b1e1be7e082e620cb9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210981"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a>解决 Linux 上的 Microsoft Defender for Endpoint 的性能问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

本文提供了一些常规步骤，可用于缩小与 Linux 上的 Defender for Endpoint 相关的性能问题。

RTP 实时 (RTP) 是 Linux 上 Defender for Endpoint 的一项功能，可持续监视你的设备并保护设备免受威胁。 它包含文件和进程监视以及其他启发。

根据你正在运行的应用程序和设备特征，在 Linux 上运行 Defender for Endpoint 时可能会遇到性能不优化的问题。 特别是，在短时间内访问许多资源的应用程序或系统进程可能会导致 Linux 上的 Defender for Endpoint 中的性能问题。

在启动 **之前，请确保其他安全产品当前未在设备上运行**。 多个安全产品可能会发生冲突并影响主机性能。

以下步骤可用于排查并缓解这些问题：

1. 使用下列方法之一禁用实时保护并观察性能是否提高。 此方法有助于缩小 Linux 上的 Defender for Endpoint 是否导致性能问题。

    如果你的设备不是由组织管理的，可以通过命令行禁用实时保护：

    ```bash
    mdatp config real-time-protection --value disabled
    ```

    ```Output
    Configuration property updated
    ```

    如果你的设备由你的组织管理，则管理员可以使用在 Linux 上设置 Defender for Endpoint 的首选项中的说明禁用 [实时保护](linux-preferences.md)。

    如果实时保护关闭时性能问题仍然存在，则问题的原因可能是终结点检测和响应组件。 在这种情况下，请联系客户支持部门，了解进一步说明和缓解措施。

2. 若要查找触发最多扫描的应用程序，可以使用 Defender for Endpoint 在 Linux 上收集实时统计信息。

    > [!NOTE]
    > 此功能在版本 100.90.70 或更高版本中可用。

    默认情况下，在 和 频道上 `Dogfood` 启用 `InsiderFast` 此功能。 如果使用的是其他更新通道，可以通过命令行启用此功能：

    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    此功能需要启用实时保护。 若要检查实时保护的状态，请运行以下命令：

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    验证条目 `real_time_protection_enabled` 是 `true` 。 否则，请运行以下命令以启用它：

    ```bash
    mdatp config real-time-protection --value enabled
    ```

    ```Output
    Configuration property updated
    ```

    若要收集当前统计信息，请运行：

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > 使用 ```--output json``` (请注意双) 短划线可确保输出格式已准备好进行分析。

    此命令的输出将显示所有进程及其关联的扫描活动。

3. 在 Linux 系统中，使用 命令下载 **python high_cpu_parser.py** 示例：

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    此命令的输出应类似于以下内容：

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. 接下来，键入以下命令：

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      以上输出是性能问题的主要参与者的列表。 第一列是 PID (的进程标识符) ，第二列是进程名称，最后一列是扫描的文件数，按影响排序。
    例如，该命令的输出如下所示： 

    ```Output
    ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
    27432 None 76703
    73467 actool     1249
    73914 xcodebuild 1081
    73873 bash 1050
    27475 None 836
    1    launchd    407
    73468 ibtool     344
    549  telemetryd_v1   325
    4764 None 228
    125  CrashPlanService 164
    ```

    若要提高 Linux 上 Defender for Endpoint 的性能，请在行下找到编号最高的一个， `Total files scanned` 并添加排除项。 有关详细信息，请参阅在 Linux 上配置并验证 [Defender for Endpoint 的排除项](linux-exclusions.md)。

    > [!NOTE]
    > 应用程序将统计信息存储在内存中，并仅跟踪自文件启动和启用实时保护以来的文件活动。 在实时保护关闭之前或期间启动的进程不计入在内。 此外，仅计算触发扫描的事件。

5. 在 Linux 上配置 Microsoft Defender for Endpoint，排除导致性能问题的进程或磁盘位置，并重新启用实时保护。

    有关详细信息，请参阅 [并验证 Microsoft Defender for Endpoint 在Linux上的排除](linux-exclusions.md)。

## <a name="see-also"></a>另请参阅

- [调查代理运行状况问题](health-status.md)
