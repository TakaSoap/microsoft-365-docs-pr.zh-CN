---
title: Microsoft 365 常见问题解答计划程序
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Microsoft 365 常见问题解答计划程序
ms.openlocfilehash: 12c2c00761b9a10fac6c62bc4d7ff5909ac935a7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286140"
---
# <a name="scheduler-for-microsoft-365-faqs"></a>Microsoft 365 常见问题解答计划程序

**问题：** 计划程序如何与其他 Cortana 功能（如 *Cortana for Windows、**每日简介电子邮件* 和 *播放我的电子邮件）集成*？</br>
计划程序是独立于其他 Cortana 功能的服务。 其他 Cortana 功能可以在租户级别禁用，并且仍可使用 Cortana cortana@yourdomain.com 启用计划程序。 目前，用户只能通过电子邮件与计划程序交互。

**问题：** 这是否仅适用于 Outlook？ 是否支持其他电子邮件产品？</br>
只要你拥有许可证，除上述三项要求外，用户 cortana@yourdomain.com 任何设备上的任何电子邮件客户端发送电子邮件。

**问题：** 联系人可以位于 Outlook 和 GAL 上的个人联系人列表中，也可以位于其他公司等效项中吗？</br>
与会者可以是公司内外具有电子邮件地址的任何人。 遗憾的是，计划程序无法通过现在在 GAL 中查找来自动将名称转换为电子邮件地址/别名。

**问题：** 能否将计划程序与已安装的版本 (内部部署) Outlook 版本？</br>
计划程序需要 Exchange Online。 不能与Exchange Server (一) 。 适用于任何电子邮件客户端、Outlook 桌面、OWA、iOS、android、gmail 等。

**问题：** Outlook 是否必须在后台打开？</br>
Outlook 不需要在后台打开。 你只需向 Cortana 发送一个邮件，并依靠它完成大部分工作。

## <a name="frequently-asked-trust-and-privacy-questions"></a>常见信任和隐私问题

**问题：** 计划程序如何工作？</br>
计划程序使用日程安排智能 (AI) 人员助理进行扩充。 如果 AI 模型需要以与 Cortana 通信的自然语言提供支持，会议请求将升级为人工审阅和完成。

**问题：** 审阅已升级请求的人是谁？ </br>
计划程序助理是 Microsoft 供应商安全和隐私保证 (SSPA) 个人信息和高度机密信息认证的 SSPA。 

**问题：** SSPA 助理可以查看哪些信息？</br>
计划程序与 SSPA 助理可以查看发送到 Cortana 的电子邮件。 在线程电子邮件交换中，只会处理包含 Cortana 电子邮件地址的电子邮件，不会处理主题中添加 Cortana 之前之前的电子邮件。   

**问题：** 客户数据是否保留在计划计划的数据流中？ </br>
计划程序根据 GDPR 准则、Microsoft 365 信任策略和租户电子邮件策略，在租户边界内存储所有客户内容&保留数据。

**问题：** 计划程序如何处理内部与会者的忙/闲数据？ </br>
计划程序自动化使用 *findMeetingTimes* 服务来标识与会者和组织者可相互使用的时间。 此服务支持其他 Outlook *体验，如* Outlook 会议窗体中的建议时间。 忙/闲与会者信息不会明确用作忙/闲块。 

**问题：** 计划程序 GDPR 是否符合？ </br>
是的。

**问题：** 谁有权访问 Cortana 邮箱？ </br>
计划程序处理发送到租户的 Cortana 邮箱的会议请求和关联电子邮件。 Microsoft 对 Cortana 邮箱没有任何其他访问权限，除非根据租户管理员的请求通过密码箱审批。  

**问题：** 客户数据是否用于培训 AI 模型？</br>
计划程序 for Microsoft 365 的客户内容不能用于数据培训集。 所有客户内容都驻留在客户租户中。  

**问题：** 计划程序将处理加密邮件吗？</br>
否，计划程序工作流将拒绝加密邮件。 




