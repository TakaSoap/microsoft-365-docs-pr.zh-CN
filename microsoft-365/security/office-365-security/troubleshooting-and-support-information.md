---
title: 疑难解答信息和支持信息
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5d9f75f5-bb7f-458c-ad30-5c8eae0b0e4e
ms.collection:
- M365-security-compliance
description: 本主题介绍了针对最终用户和管理员的疑难解答步骤，并提供了有关如何联系技术支持以寻求帮助的信息。
ms.openlocfilehash: c87744608930603f70e6be1132a0b405e9646b57
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441189"
---
# <a name="troubleshooting-and-support-information"></a>疑难解答信息和支持信息

本主题介绍了针对最终用户和管理员的疑难解答步骤，并提供了有关如何联系技术支持以寻求帮助的信息。

## <a name="troubleshooting-for-users"></a>用户的疑难解答

有时，添加垃圾电子邮件报告外接端后，Microsoft Outlook 可能会遇到问题。 以下是您可能遇到的问题以及解决这些问题的提示。

- Nothing happens when you click **Report Junk**

- 当您选择一封电子邮件之后，Outlook 停止响应

- 由于收到"未送达"回复，报告的垃圾邮件无法传递

若要解决此问题，请执行以下步骤：

1. 关闭并重新启动 Outlook。

2. 验证您是否能够创建和发送测试邮件。要执行此操作，您可以发送一封测试邮件到另一个您负责的电子帐户，然后验证是否收到该电子邮件。

如果问题仍然存在，请与管理员联系。

> [!TIP]
> 您还可以将垃圾邮件直接提交给 Microsoft，电子邮件地址为 [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com)；或者将误报邮件提交至 [not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com)。 有关详细信息，请参阅[将垃圾邮件、非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。

## <a name="troubleshooting-for-administrators"></a>管理员的疑难解答

作为管理员，您可能会遇到使用 Outlook 的垃圾电子邮件报告外接程序的用户的问题。 以下是解决您可能遇到的问题的提示。

### <a name="problem-an-error-message-asking-users-to-contact-their-system-administrator-continually-appears"></a>问题：会出现一条错误消息，询问用户是否持续联系其系统管理员

1. 设置以下注册表项的值为"详细"：

   - **32 位 Outlook 安装在32位操作系统上**：

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **32 位 Outlook 安装在64位操作系统上**：

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **64 位 Outlook （始终安装在64位操作系统上）**：

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

2. 重新启动 Outlook 并要求用户在看到错误消息时报告回来。

3. 收集在以下位置找到的日志信息：

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. 联系 Exchange Online Protection 技术支持并向他们提供日志信息。

### <a name="problem-users-choose-not-to-receive-a-confirmation-when-they-submit-an-email-as-junk-and-now-they-want-the-option-back"></a>问题：当用户将电子邮件提交为垃圾邮件时，用户选择不接收确认，现在他们想要返回该选项

1. 将以下注册表项的值设置为 "True" `HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk`：。

2. 重新启动 Outlook。

## <a name="support-information"></a>支持信息

如果你需要有关加载项的安装、配置或卸载的帮助，请使用 Microsoft 365 管理中心中的 "支持" 页面上的 "新建服务请求" 链接联系技术支持。 有关其他选项，包括通过电话提交服务请求和自助支持选项，请参阅[Help and support FOR EOP](help-and-support-for-eop.md)。

## <a name="for-more-information"></a>详细信息

[启用报告消息加载项](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)

[向 Microsoft 报告垃圾邮件](report-junk-email-messages-to-microsoft.md)
