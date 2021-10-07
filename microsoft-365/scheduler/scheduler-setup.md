---
title: 为计划程序设置Microsoft 365。
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
ms.localizationpriority: medium
description: 为计划程序设置Microsoft 365。
ms.openlocfilehash: 3315c362a6e6ae1eb4fa9bf54d388a89dd667136
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208033"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>设置 Microsoft 365 专属计划员

租户管理员需要设置计划程序助理邮箱，并获取会议组织者的计划程序许可证，才能为计划程序启用Microsoft 365计划程序。 

## <a name="licensing"></a>授权

了解更多信息[：Microsoft 365计划程序](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)

> [!Note]
> 与会者不需要计划程序或Microsoft 365许可证。 <br>计划程序助理邮箱不需要Microsoft 365计划程序许可证。

## <a name="prerequisites"></a>先决条件

| 先决条件 | 说明 |
|-------------------|-------------|
|租户的计划程序助理邮箱 |一Exchange类型资源邮箱，用作租户的计划程序助理邮箱，用于发送和接收发自 Cortana。 根据保留策略Cortana发送到租户的所有电子邮件Cortana租户邮箱中。 计划程序助理邮箱通常命名为"Cortana"或"Cortana计划程序"，因为助理发送的所有电子邮件都将Cortana。<ul><li>创建资源邮箱Exchange类型</li><li>将邮箱的名称和显示名称 SMTP 地址或 `Cortana <cortana@yourdomain.com>` `Cortana Scheduler <cortana.scheduler@yourdomain.com>` 。</li></ul>**注意：** 计划程序助理邮箱不需要Microsoft 365计划程序许可证。|
|Exchange Online 邮箱 |会议组织者必须拥有一Exchange Online邮箱和日历作为其会议许可证的Microsoft 365一部分。 此外，会议组织者必须具有计划程序许可证。 计划程序许可证使计划程序助理可以使用会议组织者的邮箱和日历来安排其会议。<br/><br/> 有关许可和Microsoft 365，请参阅计划程序。  <br/><br/>**注意：** 与会者不需要计划程序或Microsoft 365许可证。 与会者可以是租户的内部或外部人员。 与会者只需访问电子邮件地址。|


## <a name="setting-up-the-scheduler-assistant-mailbox"></a>设置计划程序助理邮箱

计划程序助理邮箱是一Exchange设备类型邮箱，不需要额外的Microsoft 365许可证。 the 显示名称 and the primary SMTP address of the mailbox should contain Cortana since all the emails from the Scheduler assistant will be signed Cortana (， or `Cortana <cortana@yourdomain.com>` `Cortana Scheduler <cortana.scheduler@yourdomain.com>`) . 创建计划程序助理邮箱后，必须将该邮箱指定为计划程序助理邮箱。 指定计划程序助理邮箱后，Cortana将可以代表用户安排会议。

- 使用 Microsoft 365 管理中心创建用户邮箱。 建议使用 30 天的保留策略。 
- 使用邮箱Cortana SMTP 地址中的名称。 建议使用 、 `Cortana@yourdomain.com` `CortanaScheduler@contoso.com` 或 `Cortana.Scheduler@yourdomain.com` 等名称。

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>将邮箱指定为计划程序助理

创建计划程序Cortana邮箱后，必须将该邮箱指定为Microsoft 365邮箱。 指定计划Cortana邮箱后，将可以代表用户安排会议。

#### <a name="connect-to-powershell"></a>连接 PowerShell

使用 Microsoft 365 管理中心创建用户邮箱。 建议使用 30 天的保留策略。
使用邮箱Cortana SMTP 地址中的名称。 建议使用 、 `Cortana@yourdomain.com` `CortanaScheduler@contoso.com` 或 `Cortana.Scheduler@yourdomain.com` 等名称。

```PowerShell
$domain="yourdomain.com"
$tenantAdmin="<tenantadmin>@$domain"
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $tenantAdmin
```

#### <a name="create-the-scheduler-assistant-mailbox"></a>创建计划程序助理邮箱

```PowerShell
New-Mailbox -Name Cortana -Organization $domain -DisplayName "Cortana Scheduler" -Equipment 
Set-CalendarProcessing Cortana@$domain -DeleteNonCalendarItems $false 
```
    
#### <a name="designate-the-scheduler-assistant-mailbox"></a>指定计划程序助理邮箱

```PowerShell
Set-mailbox cortana@$domain -SchedulerAssistant:$true
```

在 Cortana 计划程序助理邮箱上运行此"set"命令后，将在邮箱上设置一个新的"PersistedCapability"，以表明此邮箱是"SchedulerAssistant"。

> [!Note]
> 若要了解如何将组织连接到 PowerShell，请参阅：连接[Microsoft 365 PowerShell 进行连接](/microsoft-365/enterprise/connect-to-microsoft-365-powershell)

### <a name="verifying-the-scheduler-assistant-mailbox"></a>验证计划程序助理邮箱

验证是否创建了计划程序助理邮箱

```PowerShell
Get-CalendarProcessing cortana@$domain | fl DeleteNonCalendarItems
```

结果应为"false"。

<br>

```PowerShell
Get-Mailbox -Identity cortana@$domain | fl *type*
```

结果应为
- ResourceType：Equipment
- Remote RecipientType：无
- RecipientType：UserMailbox
- RecipientTypeDetails：EquipmentMailbox

<br/>

### <a name="to-discover-which-mailbox-is-the-scheduler-assistant-mailbox"></a>发现哪个邮箱是计划程序助理邮箱

```PowerShell
Get-Mailbox -ResultSize Unlimited | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!Important]
> 计划程序助理邮箱可能需要几个小时才能完成完全设置，才能设置 SchedulerAssistant 功能。


## <a name="exchange-online-mailbox"></a>Exchange Online 邮箱

计划程序许可证是会议Microsoft 365的加载项，它使会议组织者能够将其会议计划任务委派给计划程序助理。 除了将邮箱指定为计划程序助理邮箱之外，会议组织者还需要计划程序许可证和 Exchange Online 邮箱和日历，通常通过 Microsoft 365 许可证计划程序才能工作。 与会者不需要计划程序许可证或Microsoft 365许可证。

若要购买计划程序加载项，需要以下许可证之一：

- Microsoft 365 E3、A3、E5、A5
- Business Basic、Business、Business Standard、Business 高级版
- Office 365 E1、A1、E3、A3、E5、A5
- 商业基本要素、商业高级版
- Exchange Online计划 1 或计划 2 许可证。 

> [!Note]
> Microsoft 365计划程序仅适用于以英语表示的全球多租户环境。 **用户Microsoft 365** 计划程序：
> 
> - Microsoft 365由世纪银行在中国运营
> - Microsoft 365使用数据被信任方德国电信的德国云
> - 政府云，GCC、消费者、GCC高或 DoD
> 
> 计划程序支持其数据位置不是德国数据中心的德国用户。
