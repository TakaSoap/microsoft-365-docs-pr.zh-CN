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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6f7a3404ec0ae64e3dcdc4d6a3072e7fc2936646
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2022
ms.locfileid: "62172447"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a>解决 Linux 上的 Microsoft Defender for Endpoint 的性能问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

本文档提供有关如何使用可用诊断工具缩小与 Linux 上的 Defender for Endpoint 相关的性能问题的说明，以便了解并减少现有资源不足以及使系统进入此类情况的过程。 性能问题主要由一个或多个硬件子系统中的瓶颈引起，具体取决于系统资源利用率的配置文件。 有时，应用程序对磁盘 I/O 资源很敏感，并且可能需要更多的 CPU 容量，有时某些配置是非持久的，并且可能会触发太多新进程，并打开过多文件描述符。

根据你正在运行的应用程序和设备特征，在 Linux 上运行 Defender for Endpoint 时可能会遇到性能不优化的问题。 特别是，在短时间内访问许多资源（如 CPU、磁盘和内存）的应用程序或系统进程可能会导致 Linux 上的 Defender for Endpoint 中的性能问题。

> [!WARNING]
> 在启动 **之前，请确保其他安全产品当前未在设备上运行**。 多个安全产品可能会发生冲突并影响主机性能。

## <a name="troubleshoot-performance-issues-using-real-time-protection-statistics"></a>使用实时保护统计信息解决性能问题

**适用于：**
- 仅与 AV 相关的性能问题

RTP (RTP) 是 Linux 上 Defender for Endpoint 的一项功能，可持续监视你的设备并保护设备免受威胁。 它包含文件和进程监视以及其他启发。

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

    > [!NOTE]
    > 如果实时保护关闭时性能问题仍然存在，则问题根源可能是终结点检测和响应 (EDR) 组件。 在这种情况下，请按照本文使用 **Microsoft Defender for Endpoint Client Analyzer** 解决性能问题部分中的步骤操作。

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

## <a name="troubleshoot-performance-issues-using-microsoft-defender-for-endpoint-client-analyzer"></a>使用 Microsoft Defender for Endpoint Client Analyzer 解决性能问题

**适用于：**
- 所有适用于终结点组件的可用 Defender（如 AV 和 EDR  

Microsoft Defender for Endpoint Client Analyzer (MDECA) 可以收集跟踪、日志和诊断信息，以便解决 Linux 上[](/microsoft-365/security/defender-endpoint/onboard-configure)载入的设备的性能问题。

> [!NOTE]
> Microsoft 客户支持服务 (CSS) 会定期使用 Microsoft Defender for Endpoint 客户端分析器工具收集 (但不限于) IP 地址、可帮助解决 Microsoft Defender for Endpoint 可能遇到的问题的电脑名称。 有关我们的隐私声明详细信息，请参阅 Microsoft [隐私声明](https://privacy.microsoft.com/privacystatement)。

### <a name="requirements"></a>要求

- 客户端分析器可以在载入 Microsoft Defender for Endpoint 之前或之后在支持的 [Linux](microsoft-defender-endpoint-linux.md#system-requirements) 发行版上运行。
- 从可在此处下载的最新预览版下载适用于 Linux 的客户端分析器： <https://aka.ms/XMDEClientAnalyzer>
- 如果设备位于代理后面，则只需将代理服务器作为环境变量传递到 mde_support_tool.sh 脚本。 例如：`https_proxy=https://myproxy.contoso.com:8080 ./mde_support_tool.sh"`

### <a name="run-the-client-analyzer-on-linux"></a>在 Linux 上运行客户端分析器

打开相关计算机中的终端或 SSH 并运行以下命令：

1. `wget --quiet -O XMDEClientAnalyzer.zip https://aka.ms/XMDEClientAnalyzer`
2. `unzip -q XMDEClientAnalyzer.zip`
3. `cd XMDEClientAnalyzer`
4. `chmod +x mde_support_tool.sh`
5. 作为非根使用运行以安装所需的管道和 lxml 组件： `./mde_support_tool.sh`
6. 若要收集实际的诊断包并生成结果存档文件，请再次作为根运行： `./mde_support_tool.sh -d` 示例：

   ![命令行示例的图像。](images/4ca188f6c457e335abe3c9ad3eddda26.png)

> [!NOTE]
> - 分析器需要"lxml"来生成结果输出。 如果未安装，分析器将尝试从下面的 python 包的官方存储库获取它： <https://files.pythonhosted.org/packages/\*/lxml\*.whl>
> 
> - 此外，该工具当前需要安装 Python 版本 3 或更高版本。
>
> - 如果在无法使用 Python 3 或提取 lxml 组件计算机上运行，可以下载没有任何要求的基于二进制版本的分析器 [：XMDE Client Analyzer Binary](https://aka.ms/XMDEClientAnalyzerBinary)

### <a name="additional-syntax-help"></a>其他语法帮助：

**-h** \# 帮助<br>
\# 显示帮助消息

**性能** \# 性能<br>
\# 收集大量跟踪，以分析可按需重现的性能问题。 用于 `--length=<seconds>` 指定基准的持续时间。

**-o** \# 输出<br>
\# 指定结果文件的目标路径

**-nz** \# No-Zip<br>
\# 如果设置，将创建目录，而不是生成的存档文件

**-f** \# Force<br>
\# 如果输出在目标路径中已存在，则覆盖

### <a name="result-package-contents"></a>结果包内容

- report.html

  说明：主 HTML 输出文件，其中包含计算机上运行的分析器脚本可以生成的结果和指导。

- mde_diagnostic.zip

  说明：在 Linux 上运行 *mdatp 诊断创建时生成的相同*[诊断输出](/windows/security/threat-protection/microsoft-defender-atp/linux-resources#collect-diagnostic-information)

- mde.xml

  说明：运行时生成的 XML 输出，用于生成 html 报告文件。

- Processes_information.txt

  说明：包含系统上运行的 Microsoft Defender 终结点相关进程的详细信息。

- Log.txt

  说明：包含数据收集期间在屏幕上写入的相同日志消息。

- Health.txt

  说明：与运行 *mdatp* 运行状况命令时显示的基本运行状况输出相同。

- Events.xml

  说明：生成 HTML 报告时分析器使用的其他 XML 文件。

- Auditd_info.txt

  说明：有关 Linux OS 的已审核服务和相关 [组件](/windows/security/threat-protection/microsoft-defender-atp/linux-support-events) 的详细信息

- perf_benchmark.tar.gz

  说明：性能测试报告。 只有在使用 performance 参数时，才能看到此参数。

> [!NOTE]
> 如果执行上述步骤后，性能问题仍然存在，请联系客户支持，了解进一步说明和缓解措施。



## <a name="see-also"></a>另请参阅

- [调查代理运行状况问题](health-status.md)
