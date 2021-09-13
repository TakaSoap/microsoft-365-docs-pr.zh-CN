---
title: 常见问题解答Microsoft 365计划程序
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: 常见问题解答Microsoft 365计划程序
ms.openlocfilehash: 423660785e51a61cbff9fa2849b9466feddfc1c1
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59161987"
---
# <a name="scheduler-for-microsoft-365-faqs"></a>常见问题解答Microsoft 365计划程序

**问题：** 计划程序如何与其他Cortana功能集成，例如Cortana、Windows电子邮件和播放 *我的电子邮件*？ </br>
计划程序是独立于其他功能Cortana服务。 其他Cortana功能可以在租户级别禁用，并且仍可使用租户电子邮件地址启用计划 cortana@yourdomain.com 计划程序。 目前，用户只能通过电子邮件与计划程序交互。

**问题：** 这是否仅适用于Outlook？ 是否支持其他电子邮件产品？</br>
只要拥有许可证，除上述三项要求外，用户就可以 cortana@yourdomain.com 任何设备的电子邮件客户端发送电子邮件。

**问题：** 联系人能否位于 Outlook GAL 或其他公司等效项上的个人联系人列表中？</br>
与会者可以是公司内外具有电子邮件地址的任何人。 遗憾的是，计划程序无法通过现在在 GAL 中查找来自动将名称转换为电子邮件地址/别名。

**问题：** 能否将计划程序与已安装的版本 (本地) 版本Outlook？</br>
计划程序需要Exchange Online。 不能与Exchange Server (一) 。 适用于任何电子邮件客户端、Outlook桌面、OWA、iOS、android、gmail 等。

**问题：** Outlook必须在后台打开吗？</br>
Outlook不需要在后台打开。 只需向邮件Cortana并依赖邮件执行大量工作。

## <a name="frequently-asked-trust-and-privacy-questions"></a>常见信任和隐私问题

**问题：** 计划程序如何工作？</br>
计划程序使用日程安排智能 (AI) 人员助理进行扩充。 如果 AI 模型需要在与用户通信的自然语言Cortana支持，会议请求将升级为人工审阅和完成。

**问题** Who审阅已升级请求的人吗？ </br>
计划程序助理是 Microsoft 供应商安全和隐私保证 (SSPA) 个人信息和高度机密信息的认证。

**问题：** SSPA 助理可以查看哪些信息？</br>
计划程序与 SSPA 助理可以查看发送到电子邮件Cortana。 在线程电子邮件交换中，只会处理包含 Cortana 电子邮件地址的电子邮件，不会处理主题中之前添加Cortana的电子邮件。

**问题：** 客户数据是否保留在计划程序的数据记录Flow？ </br>
计划程序根据 GDPR 准则、Microsoft 365信任&策略和租户电子邮件策略，在租户边界内存储所有客户内容并保留数据。

**问题：** 计划程序如何处理内部与会者的忙/闲数据？ </br>
计划程序自动化使用 *findMeetingTimes* 服务来标识与会者和组织者可相互使用的时间。 此服务支持Outlook *会议表单中的* 建议时间Outlook体验。 忙/闲与会者信息不会明确用作忙/闲块。

**问题：** 计划程序 GDPR 是否符合？ </br>
能。

**问题** Who是否有权访问Cortana邮箱？ </br>
计划程序将处理发送到租户邮箱的会议请求Cortana电子邮件。 除非根据租户管理员的请求通过密码箱审批，否则 Microsoft 对 Cortana 邮箱没有任何其他访问权限。

**问题：** 客户数据是否用于培训 AI 模型？</br>
Scheduler for Microsoft 365中任何客户内容都不得用于数据培训集。 所有客户内容都驻留在客户租户中。

**问题：** 计划程序将处理加密邮件吗？</br>
否，计划程序工作流将拒绝加密邮件。
