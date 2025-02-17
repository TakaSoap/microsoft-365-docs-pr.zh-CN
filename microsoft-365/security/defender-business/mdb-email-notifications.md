---
title: 为安全团队设置电子邮件通知
description: 设置电子邮件通知，告知用户有关 Microsoft Defender for Business 的警报和漏洞
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/15/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection: M365-security-compliance
ms.openlocfilehash: bf11ed140d2e0609f2d12d1da3bcc448ff733235
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63683134"
---
# <a name="set-up-email-notifications"></a>设置电子邮件通知

> [!IMPORTANT]
> 从 2022 年 3 [月](../../business-premium/index.md) 1 Microsoft 365 商业高级版 Microsoft Defender for Business 将推出给客户。 作为独立订阅的 Defender for Business 在预览版中，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 预览 [包括一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

你可以为安全团队设置电子邮件通知。 然后，当生成警报或发现新漏洞时，安全团队中人员将自动收到通知。 

## <a name="what-to-do"></a>需执行的操作

1. [了解电子邮件通知的类型](#types-of-email-notifications)。

2. [查看和编辑电子邮件通知设置](#view-and-edit-email-notifications)。

3. [继续执行下一步](#next-steps)。


>
> **有空吗？**
> 请参加有关 <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business 的简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="types-of-email-notifications"></a>电子邮件通知类型

设置电子邮件通知时，您可以从两种类型中选择，如下表所述： <br/><br/>

| 通知类型  | 说明  |
|---------|---------|
| 漏洞  | 只要检测到任何新的攻击或漏洞事件，收件人就会收到一封电子邮件。 |
| 警报&漏洞  | 当由于在设备上检测到威胁而生成警报时，或者当检测到任何新的攻击或漏洞事件时，收件人将收到一封电子邮件。 |

> [!TIP]
> **电子邮件通知不是安全团队了解** 新警报或漏洞的唯一方式。
> 
> 电子邮件通知是一种有助于实时通知安全团队的便捷方式。 但还有其他功能！ 例如，每当[https://security.microsoft.com](https://security.microsoft.com)安全团队登录 Microsoft 365 Defender 门户 () ，他们将看到突出显示新威胁、警报和漏洞的卡片。 Defender for Business 旨在突出显示安全团队在登录后关注的重要信息。
> 
> 安全团队 **还可以在导航** 窗格中选择"事件"以查看信息。 若要了解更多信息，请参阅 [在 Microsoft Defender for Business 中查看和管理事件](mdb-view-manage-incidents.md)。

## <a name="view-and-edit-email-notifications"></a>查看和编辑电子邮件通知

若要查看或编辑贵公司的电子邮件通知设置，请按照以下步骤操作：

1. 转到"Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 并登录。

2. 在导航窗格中，**选择"设置**"，然后选择"**终结点"**。 然后，在" **常规"** 下，选择 **"电子邮件通知"**。 

3. 查看"警报和 **漏洞****"选项卡上** 的信息。

   - 如果看不到"通知"选项卡上列出的任何项目，可以创建一个规则，在生成通知时通知用户。 若要获取有关此任务的帮助，请参阅 [创建警报通知的规则](../defender-endpoint/configure-email-notifications.md)。

   - 如果看不到"漏洞"选项卡上列出的任何项目，可以创建规则，每当发现新漏洞时通知用户。 若要获取有关此任务的帮助，请参阅 [创建漏洞事件的规则](../defender-endpoint/configure-vulnerability-email-notifications.md)。

   - 如果创建了规则，请选择一个规则进行编辑。 您还可以删除规则。 

## <a name="next-steps"></a>后续步骤

继续：

- [步骤 4：将设备载入 Microsoft Defender for Business](mdb-onboard-devices.md)
