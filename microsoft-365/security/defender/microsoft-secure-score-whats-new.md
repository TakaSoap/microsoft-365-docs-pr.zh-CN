---
title: Microsoft 安全分数中的新增功能
description: 介绍 Microsoft 安全分数在 microsoft 安全分数门户中Microsoft 365 Defender变化。
keywords: microsoft 安全分数， 安全分数， office 365 安全分数， microsoft 安全分数， Microsoft 365 Defender门户
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 72bd56905392ff89fbcd3209212029d3b33b9a98
ms.sourcegitcommit: cfcdb11cc5d39c6c71a34e09c03e8859cd6708d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60724340"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Microsoft 安全分数中的新增功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

为了更好地代表 Microsoft 安全分数的安全状态，我们进行了一些更改。 若要了解计划更改，请参阅 Microsoft 安全分数 [中即将提供哪些功能？](microsoft-secure-score-whats-coming.md)

可在 Microsoft 安全分数门户 的 Microsoft 365 Defender https://security.microsoft.com/securescore [找到](microsoft-365-defender.md#the-microsoft-365-defender-portal)。

## <a name="july-2021"></a>2021 年 7 月

### <a name="added-improvement-action-related-to-microsoft-teams"></a>添加了与项目相关的改进Microsoft Teams

- 限制拨入用户绕过会议厅
- 限制外部参与者在会议Teams控制权
- 限制匿名用户启动Teams会议
- 要求为会议设置Teams大厅
- 配置允许哪些用户参加Teams会议

### <a name="added-improvement-action-related-to-microsoft-defender-for-endpoint"></a>添加了与 Microsoft Defender for Endpoint 相关的改进操作

- 修复适用于 macOS 的 Microsoft Defender for Endpoint 传感器数据收集
- 修复 MacOS 的终结点通信受损的 Microsoft Defender
- 在 macOS 中将最小密码长度设置为 15 个或多个字符
- 在 macOS 中将"强制实施密码历史记录"设置为"24 (密码) 密码"。
- 在 macOS 中，将"最长密码使用时间"设置为"90 天或更少天，但不设置为 0"
- 在 macOS 中将帐户锁定阈值设置为 5 或更低
- 打开 macOS 上的防火墙
- 启用网关守卫
- 启用系统完整性保护 (SIP) 
- 启用 FileVault 磁盘加密
- 将屏幕设置为在 macOS 中启动屏幕保护程序时锁定
- 确保屏幕保护程序在 macOS 中设置为在 20 分钟内或更先于 20 分钟内启动
- 保护家庭文件夹
- 打开Microsoft Defender 防病毒 macOS 实时保护
- 在 macOS Microsoft Defender 防病毒模式下打开 PUA 保护
- 启用Microsoft Defender 防病毒云提供的 macOS 保护
- 更新 Microsoft Defender 防病毒 macOS 的定义
- 修复适用于 Linux 的 Microsoft Defender for Endpoint 传感器数据收集
- 修复适用于 Linux 的终结点通信受损的 Microsoft Defender
- 无限制访问帐户
- 打开Microsoft Defender 防病毒 Linux 实时保护
- 在 Linux Microsoft Defender 防病毒模式下打开 PUA 保护
- 为 linux Microsoft Defender 防病毒云保护
- 更新Microsoft Defender 防病毒 Linux 的定义

## <a name="june-2021"></a>2021 年 6 月

### <a name="removed-improvement-action-related-to-microsoft-cloud-app-security"></a>删除了与项目相关的改进Microsoft Cloud App Security

- 使用云应用安全检测异常行为。

## <a name="february-2021"></a>2021 年 2 月

### <a name="compatibility-with-graph-api"></a>与 Graph API 的兼容性

通过 Graph API 提供的 Microsoft 安全分数建议的外观和权重将与当前在 Microsoft 365 Defender 门户中看到的建议相同。

## <a name="january-2021"></a>2021 年 1 月

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a>添加了针对安全保护的第一Microsoft Teams

Microsoft Teams安全分数中新增了一项改进操作，客户会看到"限制匿名用户加入会议"。

## <a name="december-2020"></a>2020 年 12 月

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint"></a>为 Microsoft Defender for Endpoint 添加了六个与帐户相关的改进操作：

- 将"最小密码长度"设置为"14 个或多个字符"
- 将"强制实施密码历史记录"设置为"24 (密码) "
- 将"最长密码使用时间"设置为"60 天或更少天，但不设置为 0"
- 将"最短密码使用时间"设置为"1 天或 (天) "
- 禁用内置管理员帐户
- 禁用内置来宾帐户

## <a name="november-2020"></a>2020 年 11 月

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>删除了通过安全分数创建 ServiceNow 票证的能力 

不再提供通过安全分数创建 ServiceNow 票证> **ServiceNow。** 感谢你提供反馈，并继续支持我们确定下一步。

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint"></a>为 Microsoft Defender for Endpoint 添加了三个与服务相关的改进操作：

- 修复服务未标出Windows路径
- 将服务可执行路径更改为公用受保护位置
- 更改服务帐户以避免在 Windows 注册表中缓存密码

## <a name="october-2020"></a>2020 年 10 月

### <a name="removed-improvement-action-related-to-microsoft-defender-for-endpoint"></a>删除了与 Microsoft Defender for Endpoint 相关的改进操作

- 将Microsoft Defender SmartScreen Windows应用商店应用 Web 内容检查设置为警告

## <a name="august-2020"></a>2020 年 8 月

### <a name="updated-improvement-action-for-azure-active-directory"></a>更新了针对 Azure Active Directory

- 启用策略以阻止旧身份验证

## <a name="incompatibility-with-identity-secure-score"></a>与标识安全分数不兼容

在 Microsoft 安全分数的最近版本中，发布了改进的评分模型。 通过这些更改，可以更灵活、准确地查看安全状态。 但是，这些更新使 Microsoft 安全分数暂时与标识安全分数不兼容。

随着时间的推移，Identity Secure Score 将采用新的评分模型。 在此之前，客户将看到 Microsoft 安全分数和标识安全分数报告的分数的差异。 我们对此引起的不便表示抱歉，并致力于确保这些体验在未来更加兼容。

## <a name="updated-improvement-actions"></a>更新后的改进操作

- 添加了Azure Active Directory改进操作
- 添加了 Microsoft Defender for Identity 改进操作
- 支持 Microsoft Defender 终结点 [威胁&漏洞管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 安全建议
    - 现在，TVM 提供的所有已发布安全建议都可用

## <a name="updated-interface-and-functionality"></a>更新的界面和功能

* CISO 和潜在客户级别讨论的所有新指标和趋势视图
* 跟踪分数并衡量分数基准的新增方法
* 更好地跟踪和理解分数回归
* 筛选、标记、搜索和分组改进操作
* 使用分数预测和计划操作管理你的未来目标
* 等等！

## <a name="we-want-to-hear-from-you"></a>欢迎提出宝贵意见

如果有任何问题，请通过发布在安全、隐私和合规性社区中& [告知](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 我们。 We're monitoring the community and will provide help.

## <a name="related-resources"></a>相关资源

- [评估安全状况](microsoft-secure-score-improvement-actions.md)
- [跟踪 Microsoft 安全分数历史记录并实现目标](microsoft-secure-score-history-metrics-trends.md)
- [即将推出的功能](microsoft-secure-score-whats-coming.md)
