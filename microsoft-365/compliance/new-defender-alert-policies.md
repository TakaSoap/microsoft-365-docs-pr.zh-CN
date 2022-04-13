---
title: Microsoft Defender for Office 365 中新的警报策略
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkDEFENDER
ROBOTS: noindex,nofollow
description: 我们将为 Microsoft Defender for Office 365 发布新的警报策略。 我们还将停用已由新策略替换的两个现有警报策略。
ms.openlocfilehash: afdc547fc658b40c2eee7a92ef2043326e159b32
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64759470"
---
# <a name="new-alert-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中新的警报策略

Microsoft Defender for Office 365 引入了与传递检测相关的新增和改进的警报策略。 这包括与它们关联的自动调查与响应 （AIR） 电子书的增强功能。 此外，我们正在修改六个默认警报策略的严重性分类，以更好地将这些策略生成的警报与它们对于组织的影响对齐。

## <a name="post-delivery-detections"></a>传递后检测

在Microsoft Defender for Office 365零小时自动清除（ZAP）从收件箱中删除邮件之后，我们将引入四个与传递后检测有关的新的默认警报策略。 这四种新的警报策略将替换涵盖 ZAP 方案的现有默认警报策略，并为组织提供有关基础检测和相关指标的增强详细信息。 这些警报（以及将在这些警报中触发的 AIR 播放手册）将准确捕获电子邮件和实体的威胁，包括 URL 是否指向恶意文件或文件是否包含恶意 URL。

下表列出了将删除的新警报策略和现有警报策略。 有关推出 [，请参阅](#how-this-will-affect-your-organization) 对组织的影响"部分。

|新的或现有的警报策略|警报策略名称|警报策略 ID|
|---|---|---|
|新增|**送达后删除的包含恶意 URL 的电子邮件**|8e6ba277-ef39-404e-aaf1-294f6d9a2b88|
|新增|**送达后，删除包含恶意文件的电子邮件**|4b1820ec-39dc-45f3-abf6-5ee80df51fd2|
|新增|**来自活动的电子邮件已送达，随后删除**|c8522cbb-9368-4e25-4ee9-08d8d899dfab|
|新增|**电子邮件在送达后删除**|b8f6b088-5487-4c70-037c-08d8d71a43fe|
|现有（将删除）|**送达后删除的包含钓鱼 URL 的电子邮件**|EA8169FA-0678-4751-8854-AEBEA7ADECEB|
|现有（将删除）|**送达后删除了包含恶意软件的电子邮件**|0179B3F7-3FDA-40C3-8F24-278563978DBB|

## <a name="alert-severity-enhancements"></a>警报严重性增强

下表标识其严重性分类正在进行修改的默认警报策略。我们正在更改这些警报策略的严重性分类，以更好地适应你组织的潜在风险和影响，并帮助安全团队确定通过这些策略生成的警报的优先顺序。

|通知|警报策略 ID|旧严重性|新的严重性|
|---|---|---|---|
|**可疑电子邮件转发活动**|BFD48F06-0865-41A6-85FF-BF746423EBF|中|高|
|**用户报告为恶意软件或网络钓鱼的电子邮件**|B26A5770-0C38-434A-9380-3A3C2C27BBB3|信息|低|
|**报告为钓鱼的电子邮件异常增加**|A00D8C62-9320-4EEA-A7E5-966B9AC09558|High|Medium|
|**管理员提交结果已完成**|AE9B83DD-6039-4EA9-B675-6B0AC3BF4A41|低|信息|
|**创建转发/重定向规则**|D59A8FD4-1272-41EE-9408-86F7BCF72479|低|信息|
|**电子数据展示搜索已启动或已导出**|6FDC5710-3998-47F0-AFBB-57CEFD7378A|Meduim|信息|

## <a name="when-will-these-changes-happen"></a>这些更改将在何时进行

下表确定新的警报策略何时开始触发送达后警报。 下表还确定了删除两个现有警报策略时间。

|警报策略|日期|
|---|---|
|**送达邮件后，删除包含恶意 URL 的电子邮件** （新）|警报将在 2021 年 4 月 11 日触发|
|**送达邮件后，删除包含恶意文件的电子邮件** （新）|警报将在 2021 年 4 月 11 日触发|
|**来自市场活动的电子邮件已发送，随后删除** （新）|警报将在 2021 年 5 月 28 日开始触发|
|**恶意电子邮件已送达，稍后删除**（新增）|警报将在 2021 年 5 月 28 日开始触发|
|**包含网络钓鱼 URL 的电子邮件在送达后删除**（现有，将删除）|警报策略已于 2021 年 6 月删除。 请参阅 [为这些更改做好准备，请执行哪些](#what-you-need-to-do-to-prepare-for-these-changes) 部分。|
|**送达邮件后，删除包含恶意软件的电子邮件** （现有，将删除）|警报策略已于 2021 年 6 月删除。 请参阅[需要为这些更改做哪些准备](#what-you-need-to-do-to-prepare-for-these-changes)部分。|

警报严重性更改将于 2021 年 5 月 14 日之前推广到所有组织。

## <a name="how-this-will-affect-your-organization"></a>这将如何影响你的组织

新的警报将开始触发，并触发组织中以上所列日期的 AIR 调查。 我们将会删除这两种警报，为了降低对已操作这两种警报的安全组织的影响，系统将会在 2021 年 4 月 5 日至 2021 年 5 月 28 日期间 *同时* 显示现有警报策略和新警报策略触发的警报。 这是为安全团队提供处理所需更改的时间。 为了帮助安全团队在此期间提高警报量，现有警报和新警报将关联到相同的 AIR 调查，并关联到同一事件。 更具体地说，这包括以下针对警报、AIR 调查和事件的行为：

- **警报**：按照设计，你将在现有警报和新警报间看到以下警报对：

  - **送达后删除的包含钓鱼 URL 的电子邮件** AND **删除包含恶意 URL 的电子邮件**

  - **送达后，删除含恶意软件的电子邮件** AND **删除包含恶意文件的电子邮件**

  ![新的和现有警报的警报对。](../media/DefenderAlerts.png)

   有关管理这些警报对详细信息，请参阅 [更改准备操作"部分](#what-you-need-to-do-to-prepare-for-these-changes) 操作。

- **AIR Investigations**：警报将关联到单个 AIR Investigation 中，其中一个警报按"触发"分类，另一个警报归类为"重复"。

  ![AIR Investigations 中的警报对。](../media/AIRAlerts.png)

- **事件**：两种警报将关联到同一事件

  ![事件中的警报对。](../media/IncidentsAlerts.png)

## <a name="what-you-need-to-do-to-prepare-for-these-changes"></a>为这些更改做好准备

你的组织如何利用这些警报将决定你需要执行哪些操作来进行准备。如果已操作警报，并且通过 API、警报电子邮件通知或在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心</a>或 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender 门户</a>内正在使用警报，则需要修改工作流。

**如果尚未操作这些警报，可以执行下列操作之一：**

- 禁用以下警报策略（正在删除）以减少组织的警报量：

  - **送达后删除的包含钓鱼 URL 的电子邮件**

  - **送达后删除了包含恶意软件的电子邮件**

- 不执行任何操作。我们将在 2021 年 5 月 28 日禁用现有警报策略。

**如果已操作这些警报：**

- 自 2021 年 5 月 28 日起，在删除现有警报策略后，开始使用新的警报作为工作流的一部分。 如果票证系统中有自定义逻辑、用于接收警报电子邮件通知的安全邮箱或依赖于警报名称或警报策略 ID （CorrelationId） 的 SIEM 解决方案，则需要修改逻辑以适应变化。

  > [!NOTE]
  > 警报、调查和事件的信息尚未更改。 实际上，此信息经过增强，包含与其关联的威胁的其他详细信息。

- 完成修改后，可禁用现有警报策略，减少组织的警报量：

  - **送达后删除的包含钓鱼 URL 的电子邮件**

  - **送达后删除了包含恶意软件的电子邮件**

  或者，你可以将这些警报策略保留为启用状态，直到我们在 2021 年 5 月 28 日将它们删除。
