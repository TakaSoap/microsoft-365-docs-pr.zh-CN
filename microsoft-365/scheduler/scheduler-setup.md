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
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286137"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>为计划程序设置Microsoft 365

若要为计划程序设置Microsoft 365，先决条件如下：

|**我需要什么？** |**说明** |
|-------------------|-------------|
|Cortana 邮箱 |租户管理员需要将邮箱设置为充当"Cortana"邮箱 (即 cortana@yourdomain.com) 。         |
|Exchange Online 邮箱 |用户必须拥有Exchange Online日历         |
|计划程序许可证 |有关许可和定价信息，请参阅[Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)。        |

## <a name="create-a-mailbox-for-cortana"></a>为 Cortana 创建邮箱
租户Exchange邮箱充当 Cortana 邮箱，供租户在 Cortana 之间发送和接收电子邮件。 发送到 Cortana 的所有电子邮件将基于保留策略保留在租户的 Cortana 邮箱中。

- 使用 Microsoft 365管理中心创建新邮箱。 建议使用 30 天的保留策略。 在邮箱的主 SMTP 地址中，使用名称 Cortana。 建议使用"Cortana@yourdomain.com"、"CortanaScheduler@contoso.com"或"Cortana.Scheduler@yourdomain.com"等名称。
- 请联系 Microsoft (scheduler_m365@microsoft.com) 启用 Cortana 邮箱。 

> [!IMPORTANT]
> 必须联系 Microsoft 以通过电子邮件将 Cortana 邮箱配置为使用计划程序 scheduler_m365@microsoft.com。 启用 Cortana 邮箱可能需要最多两周的时间。

## <a name="exchange-online-mailbox"></a>Exchange Online 邮箱
计划程序是加载项Microsoft 365。 会议组织者必须拥有Exchange Online邮箱和日历，计划程序正常工作。

## <a name="exchange-requirements"></a>Exchange 要求

除了许可计划程序之外，还必须具有以下许可证之一：

- Microsoft 365 E3、A3、E5、A5
- Business Basic、Business、Business Standard、Business 高级版
- Office 365E1、A1、E3、A3、E5、A5
- 商业基本信息、商业高级版
- Exchange Online计划 1 或计划 2 许可证。 

> [!Note]
> **Microsoft 365** 计划程序不适用于由世纪Office 365运营的 Office 365 的用户。 使用数据被信任方德国电信Microsoft 365德国云的用户也不可用。 身处德国但其数据位置不在德国数据中心的用户仍然可以使用。
>
>政府云（包括 GCC、消费者、GCC 高或 DoD）的用户也不支持此功能。
