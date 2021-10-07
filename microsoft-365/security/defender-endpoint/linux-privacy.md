---
title: Linux 上的 Microsoft Defender for Endpoint 的隐私
description: 隐私控制，如何配置影响隐私的策略设置，以及 Linux 上的 Microsoft Defender for Endpoint 中收集的诊断数据信息。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 隐私， 诊断
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1c15e5ba5b48380e20ddfd6c291df5c5afafa251
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191751"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-on-linux"></a>Linux 上的 Microsoft Defender for Endpoint 的隐私

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

Microsoft 致力于提供你在 Linux 上使用 Defender for Endpoint 时，选择收集和使用数据方式时需要的信息和控件。

本主题介绍产品内可用的隐私控件、如何使用策略设置管理这些控件，以及所收集的数据事件的更多详细信息。

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-on-linux"></a>Linux 上的 Microsoft Defender for Endpoint 中的隐私控件概述

本部分介绍 Linux 上的 Defender for Endpoint 收集的不同类型的数据的隐私控制。

### <a name="diagnostic-data"></a>诊断数据

诊断数据用于使 Defender for Endpoint 保持安全和最新，检测、诊断和修复问题，并改进产品。

某些诊断数据是必需的，而某些诊断数据是可选的。 我们允许你选择是否通过使用隐私控件（如组织的策略设置）向我们发送必需或可选的诊断数据。

对于 Defender for Endpoint 客户端软件，有两个级别的诊断数据可供选择：

- **必需**：帮助使 Defender for Endpoint 保持安全、最新以及按预期在安装了终结点的设备上按预期运行所需的最低数据。
- **可选**：帮助 Microsoft 改进产品并提供增强信息以帮助检测、诊断和修正问题的其他数据。

默认情况下，仅向 Microsoft 发送必需的诊断数据。

### <a name="cloud-delivered-protection-data"></a>云提供的保护数据

云提供的保护用于通过访问云中的最新保护数据来提供更高和更快的保护。

启用云保护服务是可选的，但强烈建议这样做，因为它可提供针对终结点和整个网络的恶意软件的重要保护。

### <a name="sample-data"></a>示例数据

示例数据用于通过发送 Microsoft 可疑示例来改进产品的保护功能，以便可以分析它们。 启用自动示例提交是可选的。

有三个级别用于控制示例提交：

- **无**：不会向 Microsoft 提交任何可疑样本。
- **保险箱：** 只有不包含个人身份信息或个人身份信息的可疑 (将自动) 提交。 这是此设置的默认值。
- **全部**：所有可疑示例都提交到 Microsoft。

## <a name="manage-privacy-controls-with-policy-settings"></a>通过策略设置管理隐私控件

如果您是 IT 管理员，您可能希望在企业级别配置这些控件。

The privacy controls for the various types of data described in the preceding section are described in [Set preferences for Defender for Endpoint on Linux](linux-preferences.md).

与任何新策略设置一样，应在受限的受控环境中仔细测试它们，以确保在组织中更广泛地实现策略设置之前，所配置的设置具有所需的效果。

## <a name="diagnostic-data-events"></a>诊断数据事件

本节介绍哪些内容被视为必需诊断数据，哪些内容被视为可选诊断数据，以及收集的事件和字段的说明。

### <a name="data-fields-that-are-common-for-all-events"></a>所有事件常用的数据字段

无论类别或数据子类型如何，所有事件都有一些共同的与事件相关的信息。

以下字段被视为通用于所有事件：

|字段|说明|
|---|---|
|平台|应用运行平台的广泛分类。 允许 Microsoft 确定在哪些平台上可能会发生问题，以便可以正确地确定问题的优先级。|
|machine_guid|与设备关联的唯一标识符。 允许 Microsoft 确定问题是否影响一组选定安装以及有多少用户受到影响。|
|sense_guid|与设备关联的唯一标识符。 允许 Microsoft 确定问题是否影响一组选定安装以及有多少用户受到影响。|
|org_id|与设备所属的企业关联的唯一标识符。 允许 Microsoft 确定问题是否影响一组选定企业以及有多少企业受到影响。|
|hostname|本地设备名称 (DNS 后缀) 。 允许 Microsoft 确定问题是否影响一组选定安装以及有多少用户受到影响。|
|product_guid|产品的唯一标识符。 允许 Microsoft 区分影响不同产品风格的问题。|
|app_version|Linux 应用程序上的 Defender for Endpoint 的版本。 允许 Microsoft 确定哪些版本的产品显示问题，以便可以正确地确定问题的优先级。|
|sig_version|安全智能数据库的版本。 允许 Microsoft 标识显示问题的安全智能版本，以便可以正确地确定问题的优先级。|
|supported_compressions|应用程序支持的压缩算法列表，例如 `['gzip']` 。 允许 Microsoft 了解在与应用程序通信时可以使用的压缩类型。|
|release_ring|设备与设备关联的圈， (Insider Fast、Insider Slow、Production) 。 允许 Microsoft 识别可能在哪个发布环上发生问题，以便可以正确地确定问题的优先级。|

### <a name="required-diagnostic-data"></a>必需诊断数据

**必需诊断** 数据是帮助使 Defender for Endpoint 保持安全、最新，并按预期在安装它的设备上执行所需的最少数据。

必需的诊断数据有助于识别与设备或软件配置相关的 Microsoft Defender for Endpoint 问题。 例如，它可以帮助确定 Defender for Endpoint 功能在特定操作系统版本、新引入的功能上崩溃的频率是否更频繁，或者何时禁用某些 Defender for Endpoint 功能。 必需的诊断数据可帮助 Microsoft 更快速地检测、诊断和修复这些问题，以便降低对用户或组织的影响。

#### <a name="software-setup-and-inventory-data-events"></a>软件安装和清单数据事件

**Microsoft Defender for Endpoint 安装/卸载**：

将会收集以下字段：

|字段|说明|
|---|---|
|correlation_id|与安装关联的唯一标识符。|
|version|程序包的版本。|
|severity|邮件严重性，例如 (信息) 。|
|code|描述操作的代码。|
|text|与产品安装相关的其他信息。|

**Microsoft Defender for Endpoint 配置**：

将会收集以下字段：

|字段|说明|
|---|---|
|antivirus_engine.enable_real_time_protection|是否在设备上启用实时保护。|
|antivirus_engine.passive_mode|是否在设备上启用被动模式。|
|cloud_service.enabled|是否在设备上启用云保护。|
|cloud_service.timeout|当应用程序与 Defender for Endpoint 云通信时，将退出。|
|cloud_service.heartbeat_interval|产品发送到云的连续检测信号之间的间隔。|
|cloud_service.service_uri|用于与云通信的 URI。|
|cloud_service.diagnostic_level|设备诊断级别 (可选) 。|
|cloud_service.automatic_sample_submission|设备的自动示例提交级别 (无、安全、) 。|
|cloud_service.automatic_definition_update_enabled|是否启用自动定义更新。|
|edr.early_preview|设备是否应该运行EDR早期预览功能。|
|edr.group_id|检测和响应组件使用的组标识符。|
|edr.tags|用户定义的标记。|
|功能。 \[可选功能名称\]|预览功能列表，以及是否已启用。|

#### <a name="product-and-service-usage-data-events"></a>产品和服务使用情况数据事件

**安全智能更新报告**：

将会收集以下字段：

|字段|说明|
|---|---|
|from_version|原始安全智能版本。|
|to_version|新的安全智能版本。|
|status|指示成功或失败的更新的状态。|
|using_proxy|更新是否通过代理完成。|
|error|更新失败时的错误代码。|
|reason|更新失败时出现错误消息。|

#### <a name="product-and-service-performance-data-events-for-required-diagnostic-data"></a>必需诊断数据的产品或服务性能数据事件

**内核扩展统计信息**：

将会收集以下字段：

|字段|说明|
|---|---|
|version|Linux 上适用于终结点的 Defender 版本。|
|instance_id|内核扩展启动时生成的唯一标识符。|
|trace_level|内核扩展的跟踪级别。|
|subsystem|用于实时保护的基础子系统。|
|ipc.connects|内核扩展接收的连接请求数。|
|ipc.rejects|内核扩展拒绝的连接请求数。|
|ipc.connected|是否有到内核扩展的活动连接。|

#### <a name="support-data"></a>支持数据

**诊断日志**：

仅在用户同意的情况下收集诊断日志作为反馈提交功能一部分。 将收集以下文件作为支持日志的一部分：

- */var/log/microsoft/mdatp 下的所有文件*
- */etc/opt/microsoft/mdatp* 下由 Linux 上的 Defender for Endpoint 创建和使用的文件的子集
- */var/log/microsoft_mdatp_ \* .log 下的产品安装和卸载日志*

### <a name="optional-diagnostic-data"></a>可选诊断数据

**可选诊断** 数据是可帮助 Microsoft 改进产品并提供增强信息以帮助检测、诊断和修复问题的其他数据。

如果你选择向我们发送可选诊断数据，则还需要包括必需的诊断数据。

可选诊断数据的示例包括 Microsoft 收集有关产品配置 (例如，在设备) 上设置的排除数以及产品性能 (聚合了有关产品配置组件性能) 。

#### <a name="software-setup-and-inventory-data-events-for-optional-diagnostic-data"></a>可选诊断数据的软件安装和清单数据事件

**Microsoft Defender for Endpoint 配置**：

将会收集以下字段：

|字段|说明|
|---|---|
|connection_retry_timeout|与云通信时的连接重试时间。|
|file_hash_cache_maximum|产品缓存的大小。|
|crash_upload_daily_limit|每日上载的崩溃日志的限制。|
|antivirus_engine.exclusions[].is_directory|扫描排除项是否是目录。|
|antivirus_engine.exclusions[].path|从扫描中排除的路径。|
|antivirus_engine.exclusions[].extension|从扫描中排除的扩展。|
|antivirus_engine.exclusions[].name|从扫描中排除的文件的名称。|
|antivirus_engine.scan_cache_maximum|产品缓存的大小。|
|antivirus_engine.maximum_scan_threads|用于扫描的最大线程数。|
|antivirus_engine.threat_restoration_exclusion_time|从隔离区还原的文件可以再次检测到之前，该时间已过。|
|antivirus_engine.threat_type_settings|产品如何处理不同威胁类型的配置。|
|filesystem_scanner.full_scan_directory|完全扫描目录。|
|filesystem_scanner.quick_scan_directories|快速扫描中使用的目录列表。|
|edr.latency_mode|检测和响应组件使用的延迟模式。|
|edr.proxy_address|检测和响应组件使用的代理地址。|

**Microsoft 自动更新配置**：

将会收集以下字段：

|字段|说明|
|---|---|
|how_to_check|确定如何检查产品更新 (例如自动或手动) 。|
|channel_name|更新与设备关联的通道。|
|manifest_server|用于下载更新的服务器。|
|update_cache|用于存储更新的缓存的位置。|

### <a name="product-and-service-usage"></a>产品和服务使用情况

#### <a name="diagnostic-log-upload-started-report"></a>诊断日志上载开始报告

将会收集以下字段：

|字段|说明|
|---|---|
|sha256|支持日志的 SHA256 标识符。|
|大小|支持日志的大小。|
|original_path|始终 (在 */var/opt/microsoft/mdatp/wdavdiag/)* 下的支持日志路径。|
|format|支持日志的格式。|

#### <a name="diagnostic-log-upload-completed-report"></a>诊断日志上载已完成报告

将会收集以下字段：

|字段|说明|
|---|---|
|request_id|支持日志上载请求的相关 ID。|
|sha256|支持日志的 SHA256 标识符。|
|blob_sas_uri|应用程序用于上载支持日志的 URI。|

#### <a name="product-and-service-performance-data-events-for-product-service-and-usage"></a>产品服务和使用情况的产品和服务性能数据事件

**应用程序意外退出 (崩溃) ：**

应用程序意外退出以及发生这种情况时的应用程序状态。

**内核扩展统计信息**：

将会收集以下字段：

|字段|说明|
|---|---|
|pkt_ack_timeout|以下属性是聚合的数值，表示自内核扩展启动后发生的事件数。|
|pkt_ack_conn_timeout||
|ipc.ack_pkts||
|ipc.nack_pkts||
|ipc.send.ack_no_conn||
|ipc.send.nack_no_conn||
|ipc.send.ack_no_qsq||
|ipc.send.nack_no_qsq||
|ipc.ack.no_space||
|ipc.ack.timeout||
|ipc.ack.ackd_fast||
|ipc.ack.ackd||
|ipc.recv.bad_pkt_len||
|ipc.recv.bad_reply_len||
|ipc.recv.no_waiter||
|ipc.recv.copy_failed||
|ipc.kauth.vnode.mask||
|ipc.kauth.vnode.read||
|ipc.kauth.vnode.write||
|ipc.kauth.vnode.exec||
|ipc.kauth.vnode.del||
|ipc.kauth.vnode.read_attr||
|ipc.kauth.vnode.write_attr||
|ipc.kauth.vnode.read_ex_attr||
|ipc.kauth.vnode.write_ex_attr||
|ipc.kauth.vnode.read_sec||
|ipc.kauth.vnode.write_sec||
|ipc.kauth.vnode.take_own||
|ipc.kauth.vnode.link||
|ipc.kauth.vnode.create||
|ipc.kauth.vnode.move||
|ipc.kauth.vnode.mount||
|ipc.kauth.vnode.denied||
|ipc.kauth.vnode.ackd_before_deadline||
|ipc.kauth.vnode.missed_deadline||
|ipc.kauth.file_op.mask||
|ipc.kauth_file_op.open||
|ipc.kauth.file_op.close||
|ipc.kauth.file_op.close_modified||
|ipc.kauth.file_op.move||
|ipc.kauth.file_op.link||
|ipc.kauth.file_op.exec||
|ipc.kauth.file_op.remove||
|ipc.kauth.file_op.unmount||
|ipc.kauth.file_op.fork||
|ipc.kauth.file_op.create||

## <a name="resources"></a>资源

- [Microsoft 隐私](https://privacy.microsoft.com/)
