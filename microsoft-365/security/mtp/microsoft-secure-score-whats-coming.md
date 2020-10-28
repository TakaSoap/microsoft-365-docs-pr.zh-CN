---
title: 即将推出的 Microsoft 安全分数
description: 介绍 Microsoft 365 安全中心中的 Microsoft 安全分数的新更改。
keywords: microsoft 安全分数，安全分数，office 365 安全分数，microsoft 安全分数，microsoft 365 安全中心，改进操作
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 82ec67cae86525c055b2232667cccb603830d15f
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779244"
---
# <a name="whats-coming-to-microsoft-secure-score"></a>即将推出的 Microsoft 安全分数

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

我们在不久的将来进行一些更改，让 [Microsoft 安全](microsoft-secure-score.md) 成为你的安全状态的更好代表并提高可用性。 你的分数和可能的最大分数可能会发生变化。

## <a name="proposed-changes"></a>建议的更改

### <a name="november-2020"></a>2020年11月

通过转到 **共享 > ServiceNow** ，删除通过安全分数创建 ServiceNow 票证的能力。

- ServiceNow 连接器的预览周期即将结束。 2020的结尾将不再提供此功能。 感谢你的反馈，并在我们确定后续步骤时继续提供支持。

添加与 Microsoft Defender for Endpoint (之前的 Microsoft Defender ATP) 相关的18个改进操作：

攻击面降低 (ASR) 相关建议：
- 阻止来自电子邮件客户端和 web 邮件的可执行内容
- 阻止所有 Office 应用程序创建子进程
- 阻止 Office 应用程序创建可执行内容
- 阻止 Office 应用程序将代码注入其他进程
- 阻止 JavaScript 或 VBScript 启动下载的可执行内容
- 阻止执行可能模糊的脚本
- 阻止来自 Office 宏的 Win32 API 调用
- 阻止可执行文件运行，除非它们满足流行、年龄或受信任的列表条件
- 对勒索软件使用高级防护
- 阻止从 Windows 本地安全颁发机构子系统中盗取凭据 ( # A0) 
- 阻止进程创建源自 PSExec 和 WMI 命令
- 阻止从 USB 运行的不受信任和未签名的进程
- 阻止 Office 通信应用程序创建子进程
- 阻止 Adobe Reader 创建子流程
- 通过 WMI 事件订阅阻止持久化

与服务相关的建议：
- 修复 Windows 服务的无引号服务路径
- 将服务可执行路径更改为常见的受保护位置
- 更改服务帐户以避免 windows 注册表中的缓存密码

## <a name="related-resources"></a>相关资源

- [Microsoft 安全评分概述](microsoft-secure-score.md)
- [评估你的安全状况](microsoft-secure-score-improvement-actions.md)
- [跟踪你的 Microsoft 安全分数历史记录并实现目标](microsoft-secure-score-history-metrics-trends.md)
- [新增功能](microsoft-secure-score-whats-new.md)
