---
title: 使用 Microsoft Defender for Endpoint Client Analyzer 解决传感器运行状况问题
description: 解决设备上传感器的运行状况问题，以确定影响传感器数据或功能的潜在配置、环境、连接或遥测问题。
keywords: 传感器， 传感器运行状况， 错误配置， 非活动， 无传感器数据， 传感器数据， 通信受损， 通信
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 0de2fbe98527d8fe36f2b8c5d5db0453988501a7
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63323495"
---
# <a name="troubleshoot-sensor-health-using-microsoft-defender-for-endpoint-client-analyzer"></a>使用 Microsoft Defender for Endpoint Client Analyzer 解决传感器运行状况问题

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

在运行 Windows、Linux 或 macOS 的已载入设备上诊断传感器运行状况或可靠性问题时，Microsoft Defender for Endpoint Client Analyzer (MDECA) 可能会很有用。[](/microsoft-365/security/defender-endpoint/onboard-configure) 例如，根据安全门户中显示的传感器运行状况 [状态 (非](/microsoft-365/security/defender-endpoint/fix-unhealthy-sensors) 活动、无传感器数据或通信受损) ，你可能想要在看起来不正常的计算机上运行分析器。

除了明显的传感器运行状况问题外，MDECA 还可以收集其他跟踪、日志和诊断信息，以对复杂方案进行故障排除，例如：

- AppCompat (应用程序) 、性能、网络连接或
- 与终结点数据丢失 [防护相关的意外行为](/microsoft-365/compliance/endpoint-dlp-learn-about)。

## <a name="privacy-notice"></a>隐私声明

- Microsoft 客户支持服务 (CSS) 会定期使用 Microsoft Defender for Endpoint 客户端分析工具收集有助于解决你在使用 Microsoft Defender for Endpoint 时可能遇到的问题的信息。

- 收集的数据可能包含个人身份信息 (PII) 和/或敏感数据，如 (但不限于) IP 地址、电脑名称和用户名。

- 数据收集完成后，该工具会将数据本地保存在计算机中的子文件夹和压缩 zip 文件中。

- 系统不会自动向 Microsoft 发送任何数据。 如果您在协作处理支持问题期间使用该工具，系统可能会要求您使用安全文件文件将压缩数据Exchange以加快问题调查。

有关安全文件保护Exchange，请参阅如何使用安全文件Exchange [Microsoft 支持人员交换文件](/troubleshoot/azure/general/secure-file-exchange-transfer-files)

有关我们的隐私声明详细信息，请参阅 [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)。

## <a name="requirements"></a>要求

- 在运行分析器之前，我们建议确保代理或防火墙配置允许访问 [Microsoft Defender for Endpoint 服务 URL](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。

- 在载入 Microsoft Defender for Endpoint 之前，分析[](minimum-requirements.md#supported-windows-versions)器可以在受支持的 Windows、[Linux](microsoft-defender-endpoint-linux.md#system-requirements) 或 [macOS](microsoft-defender-endpoint-mac.md#system-requirements) 版本上运行。

- 对于 Windows 设备，如果你直接在特定的计算机上运行分析器，而不是通过实时响应远程运行，则 SysInternals [PsExec.exe](/sysinternals/downloads/psexec) 至少应允许 () 运行。[](/microsoft-365/security/defender-endpoint/troubleshoot-collect-support-log) 分析器调用 PsExec.exe 工具以本地系统方式运行云连接检查，并模拟 SENSE 服务的行为。

    > [!NOTE]
    > 在 Windows 设备上，如果使用攻击面减少 (ASR) 规则阻止源自 [PSExec 和 WMI](attack-surface-reduction-rules-reference.md#block-process-creations-originating-from-psexec-and-wmi-commands) 命令的进程创建，则可能需要暂时禁用该规则或配置 [ASR](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) 规则的排除项，以允许分析器按预期运行到云的连接检查。
