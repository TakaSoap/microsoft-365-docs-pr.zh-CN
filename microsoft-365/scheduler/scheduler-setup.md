---
title: 为计划程序设置Microsoft 365。
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: 为计划程序设置Microsoft 365。
ms.openlocfilehash: 36d273dc75dbb2ff208c4f5036915b1b241de0b743f8ca6c95498a110daf8334
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53884915"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>设置 Microsoft 365 专属计划员


若要为计划程序设置Microsoft 365，先决条件如下：

| 我需要什么？ | 说明 |
|-------------------|-------------|
|Cortana邮箱 |租户管理员需要将邮箱设置为"Cortana"邮箱 (，即 cortana@yourdomain.com) 。         |
|Exchange Online 邮箱 |用户必须拥有Exchange Online日历         |
|计划程序许可证 |有关许可和定价信息，请参阅[Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing)。        |

## <a name="create-a-mailbox-for-cortana"></a>为邮箱创建Cortana

租户Exchange邮箱充当租户发送和接收Cortana发送和接收电子邮件的邮箱Cortana。 根据保留策略Cortana发送到租户的所有电子邮件Cortana租户的邮箱中。

- 使用 Microsoft 365 管理中心创建用户邮箱。 建议使用 30 天的保留策略。 
- 使用邮箱Cortana SMTP 地址中的名称。 "Cortana@yourdomain.com"、"CortanaScheduler@contoso.com"或"Cortana"等名称。Scheduler@yourdomain.com"。

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>将邮箱指定为计划程序助理

创建计划程序Cortana邮箱后，必须将该邮箱指定为Microsoft 365邮箱。 指定计划Cortana邮箱后，可以代表用户安排会议。

若要指定Cortana计划程序邮箱，授权管理员必须运行一行 PowerShell 命令。 

1. 连接组织Microsoft 365远程 PowerShell 运行空间。

2. 运行以下 PowerShell 脚本为计划程序指定邮箱：

    ```powershell
    Set-mailbox cortana@contoso.com -SchedulerAssistant:$true
    ```
    
    在计划程序邮箱上运行此Cortana"命令后，将在邮箱上设置一个新的"PersistedCapability"，以表明此邮箱是"SchedulerAssistant"。

> [!NOTE]
> 如果之前未执行这些步骤，请按照以下步骤将组织连接到[PowerShell：连接 PowerShell Microsoft 365进行连接](../enterprise/connect-to-microsoft-365-powershell.md)。

若要发现组织中当前将哪个邮箱设置为 Cortana计划程序助理，请运行 get 函数：

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> 计划程序邮箱可能需要最多两个小时才能完成完全设置，才能设置 SchedulerAssistant 功能。

## <a name="exchange-online-mailbox"></a>Exchange Online 邮箱
计划程序许可证是会议Microsoft 365的加载项，它使会议组织者能够将其会议计划任务委派给计划程序助理。 若要使计划程序正常工作，通常Microsoft 365许可证，会议组织者需要以下组件：

- 指定为计划程序助理邮箱的邮箱
- 计划程序许可证
- Exchange Online邮箱和日历

与会者不需要计划程序或Microsoft 365许可证。

## <a name="scheduler-end-user-license-requirements"></a>计划程序最终用户许可证要求

计划程序许可证需要以下许可证之一：

- Microsoft 365 E3、A3、E5、A5
- Business Basic、Business、Business Standard、Business 高级版
- Office 365 E1、A1、E3、A3、E5、A5
- 商业基本信息、商业高级版
- Exchange Online计划 1 或计划 2 许可证。 

> [!Note]

> Microsoft 365计划程序仅适用于英语的全球多租户环境。 **用户Microsoft 365** 计划程序：

- Microsoft 365由世纪银行在中国运营
- Microsoft 365使用数据被信任方德国电信的德国云
- 政府云，GCC、消费者、GCC高或 DoD

计划程序支持其数据位置不在德国数据中心的德国用户。
