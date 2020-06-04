---
title: Microsoft 安全分数中的情况如何？
description: 介绍 microsoft 365 安全中心中的 Microsoft 安全分数、如何计算详细信息以及安全管理员可预期的内容。
keywords: 安全性、恶意软件、Microsoft 365、M365、安全分数、安全中心、改进操作
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
ms.openlocfilehash: f9bca47c6a47468d0a5a37b77e4f587745bf619d
ms.sourcegitcommit: c696852da06d057dba4f5147bbf46521910de3ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2020
ms.locfileid: "44545930"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Microsoft 安全分数中的情况如何？

为了使[Microsoft 安全得分](microsoft-secure-score-new.md)更好地代表安全状况并提高可用性，我们在不久的将来进行一些更改。 你的分数和可能的最大分数都将发生变化。 但是，这并不意味着您的安全状况发生了变化。

若要了解最近所做的更改，请参阅[Microsoft 安全分数中的新增功能？](microsoft-secure-score-new.md#whats-new)

## <a name="june-2020"></a>6月2020

### <a name="remove-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>删除 Microsoft Defender 高级威胁防护的提高操作

* 打开攻击面降低规则

### <a name="add-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>为 Microsoft Defender 高级威胁防护添加改进操作

* 阻止 Adobe Reader 创建子流程
* 对勒索软件使用高级防护
* 阻止所有 Office 应用程序创建子进程
* 阻止 Office 应用程序创建可执行内容
* 阻止 JavaScript 或 VBScript 启动下载的可执行内容
* 阻止执行可能模糊的脚本
* 阻止来自电子邮件客户端和 web 邮件的可执行内容
* 阻止 Office 通信应用程序创建子进程
* 阻止从 USB 运行的不受信任和未签名的进程
* 通过 WMI 事件订阅阻止持久化
* 阻止 Office 应用程序将代码注入其他进程
* 阻止可执行文件运行，除非它们满足流行、年龄或受信任的列表条件
* 阻止进程创建源自 PSExec 和 WMI 命令
* 阻止从 Windows 本地安全颁发机构子系统（lsass.exe）中盗取凭据
* 阻止来自 Office 宏的 Win32 API 调用
