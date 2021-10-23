---
title: 使用事件查看器查看事件和错误
description: 获取 Microsoft Defender 终结点服务 (报告) 事件的说明和进一步疑难解答步骤。
keywords: 疑难解答， 事件查看器， 日志摘要， 故障代码， 失败， Microsoft Defender for Endpoint 服务， 无法启动， 断开， 无法启动
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
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: 92a9a1f01ad8747719ecf41f16e1fb1f1c4f8625
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2021
ms.locfileid: "60552688"
---
# <a name="review-events-and-errors-using-event-viewer"></a>使用事件查看器查看事件和错误

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- 事件查看器
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)。

可以在各个设备上的事件查看器 [中查看](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) 事件 ID。

例如，如果设备未显示在"设备"列表中，你可能需要在设备上查找事件 ID。 然后，可以使用此表确定进一步的疑难解答步骤。

**打开事件查看器并查找 Microsoft Defender for Endpoint 服务事件日志：**

1. 单击 **菜单** 上的"开始 **Windows，键入事件查看器**，然后按 **Enter。**

2. 在日志列表中的"日志 **摘要"** 下，滚动到看到 **Microsoft-Windows-SENSE/Operational。** 双击该项以打开日志。

   您还可以通过展开"应用程序和服务日志 \> **"Microsoft** Windows SENSE 并单击 \> **"操作"来访问** \> **日志**。

   > [!NOTE]
   > SENSE 是内部名称，用于引用支持 Microsoft Defender for Endpoint 的行为传感器。

3. 服务记录的事件将显示在日志中。 有关服务记录的事件的列表，请参阅下表。

   <br>

   ****

   |事件 ID|邮件|说明|Action|
   |---|---|---|---|
   |1|Microsoft Defender for Endpoint 服务 (版本 `variable`) 。|在系统启动、关闭和载入期间发生。|正常操作通知;无需任何操作。|
   |2|Microsoft Defender for Endpoint 服务关闭。|在设备关闭或载出时发生。|正常操作通知;无需任何操作。|
   |3|Microsoft Defender for Endpoint 服务启动失败。 失败代码 `variable` ：。|服务未启动。|查看其他消息以确定可能的原因和疑难解答步骤。|
   |4 |Microsoft Defender for Endpoint 服务与 位于 的服务器联系 `variable` 。|变量 = 适用于终结点处理服务器的 Defender 的 URL。 <p> 此 URL 将匹配防火墙或网络活动中显示的内容。|正常操作通知;无需任何操作。|
   |5|Microsoft Defender for Endpoint 服务无法连接到 位于 的服务器 `variable` 。|变量 = 适用于终结点处理服务器的 Defender 的 URL。 <p> 该服务无法通过该 URL 与外部处理服务器联系。|检查与 URL 的连接。 请参阅 [配置代理和 Internet 连接](configure-proxy-internet.md)。|
   |6 |Microsoft Defender for Endpoint 服务未载入，并且未找到任何载入参数。|设备未正确载入，不会向门户报告。|在启动该服务之前，必须运行载入。 <p> 检查载入设置和脚本是否正确部署。 尝试重新部署配置包。 <p> 请参阅[载入Windows 10设备](configure-endpoints.md)。|
   |7 |Microsoft Defender for Endpoint 服务无法读取载入参数。 失败 `variable` ：。|变量 = 详细的错误描述。 设备未正确载入，不会向门户报告。|检查载入设置和脚本是否正确部署。 尝试重新部署配置包。 <p> 请参阅[载入Windows 10设备](configure-endpoints.md)。|
   |8 |Microsoft Defender for Endpoint 服务无法清理其配置。 失败代码 `variable` ：。|**载入期间：** 服务在载入期间未能清理其配置。 载入过程继续进行。 <p> **在载出期间：** 该服务在载出过程中未能清理其配置。 载出过程已完成，但服务继续运行。|**载入：** 无需任何操作。 <p> **载出：** 重新启动系统。 <p> 请参阅[载入Windows 10设备](configure-endpoints.md)。|
   |9 |Microsoft Defender for Endpoint 服务未能更改其启动类型。 失败代码 `variable` ：。|**载入期间：** 设备未正确载入，不会向门户报告。 <p>**在载出期间：** 未能更改服务启动类型。 载出过程继续进行。 |检查载入设置和脚本是否正确部署。 尝试重新部署配置包。 <p> 请参阅[载入Windows 10设备](configure-endpoints.md)。|
   |10 |Microsoft Defender for Endpoint 服务无法保留载入信息。 失败代码 `variable` ：。|设备未正确载入，不会向门户报告。|检查载入设置和脚本是否正确部署。 尝试重新部署配置包。 <p> 请参阅[载入Windows 10设备](configure-endpoints.md)。|
   |11|已完成 Defender for Endpoint 服务的载入或重新载入。|设备已正确载入。|正常操作通知;无需任何操作。 <p> 设备可能需要几个小时才能显示在门户中。|
   |12 |Microsoft Defender for Endpoint 无法应用默认配置。|服务无法应用默认配置。|此错误应在短时间内解决。|
   |13|计算得出的 Microsoft Defender for Endpoint 设备 `variable` ID：。|正常操作过程。|正常操作通知;无需任何操作。|
   |15 |Microsoft Defender for Endpoint 无法使用 URL 启动命令通道 `variable` ：。|变量 = 适用于终结点处理服务器的 Defender 的 URL。 <p> 该服务无法通过该 URL 与外部处理服务器联系。|检查与 URL 的连接。 请参阅 [配置代理和 Internet 连接](configure-proxy-internet.md)。|
   |17 |Microsoft Defender for Endpoint 服务未能更改连接用户体验和遥测服务位置。 失败代码 `variable` ：。|遥测服务Windows错误。|[确保诊断数据服务已启用](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">确保诊断数据服务已启用。 <p> 检查载入设置和脚本是否正确部署。 尝试重新部署配置包。 <p> 请参阅[载入Windows 10设备](configure-endpoints.md)。|
   |18 |OOBE (Windows完成) 欢迎使用。|只有在任何更新完成安装Windows服务才能启动。|正常操作通知;无需任何操作。|
   |19|OOBE (Windows欢迎) 尚未完成。|只有在任何更新完成安装Windows服务才能启动。|正常操作通知;无需任何操作。 <p> 如果此错误在系统重新启动后仍然存在，请确保Windows安装完整更新。|
   |20|无法等待 OOBE (Windows欢迎) 完成。 失败代码 `variable` ：。|内部错误。|如果此错误在系统重新启动后仍然存在，请确保Windows安装完整更新。|
   |25|Microsoft Defender for Endpoint 服务无法重置注册表中的运行状况状态。 失败代码 `variable` ：。|设备未正确载入。 它将报告给门户，但该服务可能不会显示为在 SCCM 或注册表中注册。|检查载入设置和脚本是否正确部署。 尝试重新部署配置包。 <p> 请参阅[载入Windows 10设备](configure-endpoints.md)。|
   |26|Microsoft Defender for Endpoint 服务未能在注册表中设置载入状态。 失败代码 `variable` ：。|设备未正确载入。 <p> 它将报告给门户，但该服务可能不会显示为在 SCCM 或注册表中注册。|检查载入设置和脚本是否正确部署。 尝试重新部署配置包。 <p> 请参阅[载入Windows 10设备](configure-endpoints.md)。|
   |27|Microsoft Defender for Endpoint 服务未在终结点中启用 SENSE 感知Microsoft Defender 防病毒。 载入过程失败。 失败代码 `variable` ：。|通常，Microsoft Defender 防病毒设备正常运行，并且设备正在向 Defender for Endpoint 报告其他实时反恶意软件产品，则此设备将进入特殊的被动状态。|检查载入设置和脚本是否正确部署。 尝试重新部署配置包。 <p> 请参阅[载入Windows 10设备](configure-endpoints.md)。 <p> 确保实时反恶意软件保护运行正常。|
   |28|Microsoft Defender 终结点连接用户体验和遥测服务注册失败。 失败代码 `variable` ：。|遥测服务Windows错误。|[确保诊断数据服务已启用](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)。 <p> 检查载入设置和脚本是否正确部署。 尝试重新部署配置包。 <p> 请参阅[载入Windows 10设备](configure-endpoints.md)。|
   |29|未能读取 offboarding参数。 错误类型：%1，错误代码：%2，说明：%3|当系统无法读取载出参数时，将发生此事件。|确保设备可以访问 Internet，然后再次运行整个载出过程。 确保载出包尚未过期。|
   |30|Microsoft Defender for Endpoint 服务在运行中无法禁用 SENSE 感知Microsoft Defender 防病毒。 失败代码 `variable` ：。|通常，Microsoft Defender 防病毒设备正常运行，并且设备正在向 Defender for Endpoint 报告其他实时反恶意软件产品，则此设备将进入特殊的被动状态。|检查载入设置和脚本是否正确部署。 尝试重新部署配置包。 <p> 请参阅[载入Windows 10设备](configure-endpoints.md)。 <p> 确保实时反恶意软件保护运行正常。|
   |31|Microsoft Defender 终结点连接用户体验和遥测服务注销失败。 失败代码 `variable` ：。|载入期间，Windows遥测服务出错。 载出过程继续进行。|[检查遥测服务 Windows错误](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)。|
   |32|Microsoft Defender for Endpoint 服务在离开进程后无法请求自行停止。 失败代码：%1|在载出期间出错。|重新启动设备。|
   |33|Microsoft Defender for Endpoint 服务无法保留 SENSE GUID。 失败代码 `variable` ：。|唯一标识符用于表示向门户报告的每个设备。 <p> 如果标识符未保留，同一设备可能在门户中出现两次。|检查设备的注册表权限，以确保服务可以更新注册表。|
   |34|Microsoft Defender for Endpoint 服务无法将自身添加为对连接用户体验和遥测服务的依赖，从而导致载入过程失败。 失败代码 `variable` ：。|遥测服务Windows错误。|[确保诊断数据服务已启用](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)。 <p> 检查载入设置和脚本是否正确部署。 尝试重新部署配置包。 <p> 请参阅[载入Windows 10设备](configure-endpoints.md)。|
   |35|Microsoft Defender for Endpoint 服务无法删除自身作为连接用户体验和遥测服务依赖项。 失败代码 `variable` ：。|在载出期间Windows遥测服务出错。 载出过程继续进行。|检查诊断数据服务Windows错误。|
   |36|Microsoft Defender 终结点连接用户体验和遥测服务注册成功。 完成代码 `variable` ：。|为终结点注册已成功完成连接用户体验和遥测服务的 Defender。|正常操作通知;无需任何操作。|
   |37|Microsoft Defender for Endpoint A 模块即将超过其配额。 模块：%1，配额：{%2} {%3}，配额使用率百分比：%4。|设备几乎已使用当前 24 小时时段的已分配配额。 即将被限制。|正常操作通知;无需任何操作。|
   |38|网络连接标识为低。 Microsoft Defender for Endpoint 将每 %1 分钟与服务器联系一次。 按流量计费的连接：%2，Internet 可用：%3，可用网络：%4。|设备使用按流量计费/付费网络，并且与服务器联系的频率将较低。|正常操作通知;无需任何操作。|
   |39|网络连接被标识为正常连接。 Microsoft Defender for Endpoint 将每 %1 分钟与服务器联系一次。 按流量计费的连接：%2，Internet 可用：%3，可用网络：%4。|设备没有使用按流量计费/付费的连接，将照常与服务器联系。|正常操作通知;无需任何操作。|
   |40|电池状态标识为低。 Microsoft Defender for Endpoint 将每 %1 分钟与服务器联系一次。 电池状态：%2。|设备具有低电池电量，并且与服务器的联系频率较低。|正常操作通知;无需任何操作。|
   |41|电池状态标识为正常。 Microsoft Defender for Endpoint 将每 %1 分钟与服务器联系一次。 电池状态：%2。|设备没有低电池电量，将照常与服务器联系。|正常操作通知;无需任何操作。|
   |42|Microsoft Defender for Endpoint 组件无法执行操作。 组件：%1，操作：%2，异常类型：%3，异常消息：%4|内部错误。 服务启动失败。|如果此错误仍然存在，请联系支持人员。|
   |43|Microsoft Defender for Endpoint 组件无法执行操作。 组件：%1，操作：%2，异常类型：%3，异常错误：%4，异常消息：%5|内部错误。 服务启动失败。|如果此错误仍然存在，请联系支持人员。|
   |44|已完成 Defender for Endpoint Service 的载出。|服务已载出。|正常操作通知;无需任何操作。|
   |45|未能注册和启动事件跟踪会话 [%1]。 错误代码：%2|创建 ETW 会话时服务启动出错。 这导致了服务启动失败。|如果此错误仍然存在，请联系支持人员。|
   |46|由于缺少资源，无法注册和启动事件跟踪会话 [%1]。 错误代码：%2。 这很可能是因为活动事件跟踪会话过多。 该服务将在 1 分钟内重试。|创建 ETW 会话时，服务启动出错，因为缺少资源。 该服务已启动且正在运行，但在启动 ETW 会话之前不会报告任何传感器事件。|正常操作通知;无需任何操作。 该服务将尝试每分钟启动会话。|
   |47|已成功注册并启动事件跟踪会话 - 在上一次尝试失败后恢复。|在成功启动 ETW 会话后，此事件跟在上一个事件之后。|正常操作通知;无需任何操作。|
   |48|未能将提供程序 [%1] 添加到事件跟踪会话 [%2]。 错误代码：%3。 这意味着不会报告来自此提供程序的事件。|未能将提供程序添加到 ETW 会话。 因此，不会报告提供程序事件。|检查错误代码。 如果错误仍然存在，请联系支持人员。|
   |49|收到并忽略无效的云配置命令。 版本：%1，状态：%2，错误代码：%3，消息：%4|从已忽略的云服务收到无效的配置文件。|如果此错误仍然存在，请联系支持人员。|
   |50|已成功应用新的云配置。 版本：%1。|已成功应用云服务中的新配置。|正常操作通知;无需任何操作。|
   |51|新云配置应用失败，版本：%1。 已成功应用上一个已知良好的配置版本 %2。|从云服务收到错误配置文件。 已成功应用上一个已知良好的配置。|如果此错误仍然存在，请联系支持人员。|
   |52|新云配置应用失败，版本：%1。 还未能应用上一个已知良好的配置版本 %2。 已成功应用默认配置。|从云服务收到错误配置文件。 未能应用上一个已知的良好配置，并且应用了默认配置。|该服务将尝试在 5 分钟内下载新的配置文件。 如果看不到事件 50 - 请联系支持人员。|
   |53|从持久性存储加载的云配置，版本：%1。|配置是在服务启动时从永久性存储加载的。|正常操作通知;无需任何操作。|
   |55|未能创建安全 ETW 自动记录器。 失败代码：%1|未能创建安全的 ETW 记录器。|重新启动设备。 如果此错误仍然存在，请联系支持人员。|
   |56|未能删除安全 ETW 自动记录器。 失败代码：%1|在载出时未能删除安全 ETW 会话。|联系支持人员。|
   |57|捕获计算机快照以进行故障排除。|正在收集调查包（也称为取证包）。|正常操作通知;无需任何操作。|
   |59|启动命令：%1|开始执行响应命令。|正常操作通知;无需任何操作。|
   |60|未能运行命令 %1，错误：%2。|未能执行响应命令。|如果此错误仍然存在，请联系支持人员。|
   |61|数据收集命令参数无效：SasUri：%1，compressionLevel：%2。|未能读取或分析数据集合命令参数， (无效) 。|如果此错误仍然存在，请联系支持人员。|
   |62|无法启动连接用户体验和遥测服务。 失败代码：%1|连接用户体验和遥测 (diagtrack) 服务无法启动。 不会从此计算机发送非 Microsoft Defender for Endpoint 遥测。|在事件日志中查找更多疑难解答提示：Microsoft-Windows-UniversalTelemetryClient/Operational。|
   |63|更新外部服务的启动类型。 名称：%1，实际开始类型：%2，预期开始类型：%3，退出代码：%4|更新了外部服务的启动类型。|正常操作通知;无需任何操作。|
   |64|启动已停止的外部服务。 名称：%1，退出代码：%2|启动外部服务。|正常操作通知;无需任何操作。|
   |65|未能加载 Microsoft 安全事件组件微筛选器驱动程序。 失败代码：%1|未能加载MsSecFlt.sys微筛选器。|重新启动设备。 如果此错误仍然存在，请联系支持人员。|
   |66|策略更新：延迟模式 - %1|更新C&C 连接频率策略。|正常操作通知;无需任何操作。|
   |68|服务的启动类型是意外的。 服务名称：%1，实际启动类型：%2，预期启动类型：%3|意外的外部服务启动类型。|修复外部服务启动类型。|
   |69|服务已停止。 服务名称：%1|外部服务已停止。|启动外部服务。|
   |70|策略更新：允许示例集合 - %1|示例集合策略已更新。|正常操作通知;无需任何操作。|
   |71|成功运行命令：%1|命令已成功执行。|正常操作通知;无需任何操作。|
   |72|尝试发送第一个完整的计算机配置文件报告。 结果代码：%1|仅供参考。|正常操作通知;无需任何操作。|
   |73|从平台开始感知：%1|仅供参考。|正常操作通知;无需任何操作。|
   |74|注册表中的设备标记超出长度限制。 标记名称：%2。 长度限制：%1。|设备标记超出长度限制。|使用较短的设备标记。|
   |81|未能为终结点 ETW 自动记录器创建 Microsoft Defender。 失败代码：%1|未能创建 ETW 会话。|重新启动设备。 如果此错误仍然存在，请联系支持人员。|
   |82|未能删除适用于 Endpoint ETW 自动记录器 Microsoft Defender。 失败代码：%1|未能删除 ETW 会话。|联系支持人员。|
   |84|设置Windows Defender 防病毒模式。 强制被动模式：%1，结果代码：%2。|将 defender 运行模式设置为 (主动或被动) 。|正常操作通知;无需任何操作。|
   |85|未能触发 Microsoft Defender for Endpoint 可执行文件。 失败代码：%1|Starring SenseIR 可执行文件失败。|重新启动设备。 如果此错误仍然存在，请联系支持人员。|
   |86|再次启动已停止应启动的外部服务。 名称：%1，退出代码：%2|再次启动外部服务。|正常操作通知;无需任何操作。|
   |87|无法启动外部服务。 名称：%1|无法启动外部服务。|联系支持人员。|
   |88|再次更新外部服务的启动类型。 名称：%1，实际开始类型：%2，预期开始类型：%3，退出代码：%4|更新了外部服务的启动类型。|正常操作通知;无需任何操作。|
   |89|无法更新外部服务的启动类型。 名称：%1，实际开始类型：%2，预期开始类型：%3|无法更新外部服务的启动类型。|联系支持人员。|
   |90|未能将 System Guard 运行时监视器配置为连接到地理位置 %1 中的云服务。 失败代码：%2|System Guard 运行时监视器不会向云服务发送证明数据。|检查注册路径上的权限："HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm"。 如果没有问题，请联系支持人员。|
   |91|未能删除 System Guard 运行时监视器地理位置信息。 失败代码：%1|System Guard 运行时监视器不会向云服务发送证明数据。|检查注册路径上的权限："HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm"。 如果没有问题，请联系支持人员。|
   |92|由于超过数据配额，停止发送传感器网络数据配额。 配额期通过后，将恢复发送。 状态掩码：%1|超过限制。|正常操作通知;无需任何操作。|
   |93|恢复发送传感器网络数据。 状态掩码：%1|恢复网络数据提交。|正常操作通知;无需任何操作。|
   |94|Microsoft Defender for Endpoint 可执行文件已启动|SenseCE 可执行文件已启动。|正常操作通知;无需任何操作。|
   |95|Microsoft Defender for Endpoint 可执行文件已结束|SenseCE 可执行文件已结束。|正常操作通知;无需任何操作。|
   |96|Microsoft Defender for Endpoint Init 已调用。 结果代码：%2|SenseCE 可执行文件称为 MCE 初始化。|正常操作通知;无需任何操作。|
   |97|DLP 方案的云存在连接问题|存在影响 DLP 分类流的网络连接问题。|检查网络连接。|
   |98|已还原与 DLP 方案的云的连接|已还原与网络的连接，DLP 分类流可以继续。|正常操作通知;无需任何操作。|
   |99|与服务器通信时，Sense 遇到以下错误： (%1) 。 结果： (%2) |发生通信错误。|检查事件日志中的以下事件，了解更多详细信息。|
   |100|Microsoft Defender for Endpoint 可执行文件无法启动。 失败代码：%1|SenseCE 可执行文件无法启动。|重新启动设备。 如果此错误仍然存在，请联系支持人员。|
   |102|适用于终结点网络检测和响应可执行文件的 Microsoft Defender 已启动|SenseNdr 可执行文件已启动。|正常操作通知;无需任何操作。|
   |103|适用于终结点网络检测和响应可执行文件的 Microsoft Defender 已结束|SenseNdr 可执行文件已结束。|正常操作通知;无需任何操作。|
   |

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)。

## <a name="see-also"></a>另请参阅
- [载入 Windows 10 设备](configure-endpoints.md)
- [配置设备代理和 Internet 连接设置](configure-proxy-internet.md)
- [Microsoft Defender for Endpoint 疑难解答](troubleshoot-onboarding.md)
- [客户端分析器概述](overview-client-analyzer.md)
- [下载并运行分析器](download-client-analyzer.md)
- [了解分析器 HTML 报表](analyzer-report.md)