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
ms.openlocfilehash: f09d1f51ed8a868712c22fbd7a641b35f5d29073
ms.sourcegitcommit: b6e63febe24ef1f1793dfb3ecc5ed41a4e730578
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2021
ms.locfileid: "53309342"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>设置 Microsoft 365 专属计划员


若要为计划程序设置Microsoft 365，先决条件如下：

|**我需要什么？** |**说明** |
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
> 如果之前未执行这些步骤，请按照以下步骤将组织连接到 PowerShell：连接 powerShell Microsoft 365 [- Microsoft 365 企业版 |Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)

若要发现组织中当前将哪个邮箱设置为 Cortana计划程序助理，请运行 get 函数：
 
```powershell

Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}

```

> [!IMPORTANT]
> 计划程序邮箱可能需要最多两个小时才能完成完全设置，才能设置 SchedulerAssistant 功能。

## <a name="exchange-online-mailbox"></a>Exchange Online 邮箱
计划程序是加载项Microsoft 365。 会议组织者必须拥有Exchange Online邮箱和日历，计划程序正常工作。

## <a name="exchange-requirements"></a>Exchange 要求

除了许可计划程序之外，还必须具有以下许可证之一：

- Microsoft 365 E3、A3、E5、A5
- Business Basic、Business、Business Standard、Business 高级版
- Office 365 E1、A1、E3、A3、E5、A5
- 商业基本信息、商业高级版
- Exchange Online计划 1 或计划 2 许可证。 

> [!Note]
> **目前，Microsoft 365** 计划程序可用于全球多租户，仅提供英语版本。</br>
>
>它不适用于由中国世纪Office 365运营的 Microsoft 365 的用户，或者使用数据被信任方德国电信的德国云的 Microsoft 365 用户。 身处德国但其数据位置不在德国数据中心的用户仍然可以使用。
>
>政府云（包括 GCC、消费者、GCC 高或 DoD）的用户也不支持此功能。
