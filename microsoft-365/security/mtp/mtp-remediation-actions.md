---
title: Microsoft 威胁防护中的自动调查和响应功能中的补救措施
description: 简要了解 Microsoft 威胁防护中的自动调查和响应功能
keywords: 自动化, 调查, 警报, 触发器, 操作, 修正
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 65ace4bda091b3e000d25a984b706f26fe9c8696
ms.sourcegitcommit: 48b69caf6550e68cb14472ea8cfc76b53e7ae9c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42225480"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Microsoft 威胁防护中的自动调查和响应功能中的补救措施

**适用于：**
- Microsoft 威胁防护

Microsoft 威胁防护中的自动化调查和响应功能包括某些修正操作。 对设备（也称为终结点）执行某些类型的修正操作。 对电子邮件内容执行其他补救措施。

下表汇总了 Microsoft 威胁防护当前支持的补救措施： 

|终结点修正操作  |电子邮件修正操作  |
|---------|---------|
|隔离<br/>删除注册表项<br/>终止进程 <br/>停止服务 <br/>禁用驱动程序 <br/>删除计划任务      |软删除电子邮件或群集<br/>阻止 URL（单击时）<br/>关闭外部邮件转发          |

在[操作中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)中，可以查看更正操作（无论是等待审批还是已完成）。

## <a name="next-steps"></a>后续步骤

- [批准或拒绝与自动调查和响应相关的操作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [详细了解操作中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
