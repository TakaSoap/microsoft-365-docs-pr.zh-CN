---
title: 敏感度标签在 Office 应用中的工作方式
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 使用敏感度标签，可以对敏感内容进行分类和保护，同时确保组织内人员的工作效率和协作能力不受阻碍。敏感度标签可用于强制执行保护设置，如对已标记内容设置加密或水印。
ms.openlocfilehash: 1de7eadfcf95a54917c1d5e2cc0d42cc1ad486a5
ms.sourcegitcommit: c7f7ff463141f7d7f0970b64e5a04341db7e4fa8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2019
ms.locfileid: "37378645"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a>敏感度标签在 Office 应用中的工作方式

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a>在 Office 应用程序中使用敏感度标签有哪些先决条件？

### <a name="common-requirements"></a>常见要求 

- [必须在安全与合规中心配置和发布](https://aka.ms/managemip)统一的敏感度标签
- 用户必须使用其工作帐户登录到 Office。
- 用户必须分配有 Office 365 E3 或更高版本的许可证。

### <a name="additional-requirements-for-office-for-windows"></a>针对 Office for Windows 的其他要求 

- Azure 信息保护客户端必须未在 Office 中运行。 另请参阅：[敏感度标签能否与 Azure 信息保护客户端一起在 Office for Windows 中运行？](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows)。

### <a name="additional-requirements-for-outlook-on-all-platforms"></a>针对所有平台上的 Outlook 的其他要求 

- 在标签配置中，如果已打开内容标记，则必须为要在传输中插入的内容标记使用 Exchange Online。

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a>Office 目前支持哪些敏感度标签功能？ 

<table border="1" cellspacing="0" cellpadding="0">
<th><font size="-1">功能<th><font size="-1">Windows<th><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</tr>
<tr><td>

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint<br>
Outlook


<td><font size="-1"> Word<br>
Excel<br>
PowerPoint<br>
Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook </b>
</tr>

<tr>
<td><font size="-1">手动应用、更改或删除标签<td><font size="-1"><b>是</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>是</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>是</b><br><font size="-1">2.21+</font>
<td><font size="-1">即将推出<sup>3</sup>
<td><font size="-1"><b>是</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">即将推出<sup>3</sup>
<td><font size="-1">即将推出<sup>3</sup><td><font size="-1">即将推出<sup>3</sup>

<tr>
<td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">应用默认标签</a>
<td><font size="-1"><b>是</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>是</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>是</b><br><font size="-1">2.21+</font>
<td><font size="-1">即将推出<sup>3</sup>
<td><font size="-1"><b>是</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">即将推出<sup>3</sup>
<td><font size="-1">即将推出<sup>3</sup>
<td><font size="-1">即将推出<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">要求提供更改标签的理由</a><sup>1</sup>
<td><font size="-1"><b>是</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>是</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>是</b><br><font size="-1">2.21+</font>
<td><font size="-1">即将推出<sup>3</sup>
<td><font size="-1"><b>是</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">即将推出<sup>3</sup>
<td><font size="-1">即将推出<sup>3</sup>
<td><font size="-1">即将推出<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">为自定义帮助页面提供帮助链接</a>
<td><font size="-1"><b>是</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>是</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>是</b><br><font size="-1">2.21+</font>
<td><font size="-1">即将推出<sup>3</sup>
<td><font size="-1"><b>是</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">即将推出<sup>3</sup>
<td><font size="-1">即将推出<sup>3</sup>
<td><font size="-1">即将推出<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">标记内容</a>
<td><font size="-1"><b>是</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>是</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>是</b><br><font size="-1">2.21+</font>
<td><font size="-1">即将推出<sup>3</sup>
<td><font size="-1"><b>是</b><br><font size="-1">16.0.11231+</font
><td><font size="-1">即将推出<sup>3</sup>
<td><font size="-1">即将推出<sup>3</sup>
<td><font size="-1">即将推出<sup>3</sup>

<tr><td><font size="-1">分配预定义的权限
<td><font size="-1"><b>是</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>是</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>是</b><br><font size="-1">2.21+</font>
<td><font size="-1">即将推出<sup>3</sup>
<td><font size="-1"><b>是</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">即将推出<sup>3</sup>
<td><font size="-1">即将推出<sup>3</sup>
<td><font size="-1">即将推出<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">允许用户分配权限</a>
<td><font size="-1"><b>是</b><sup>2</sup><br><font size="-1">1910+</font>

<td><font size="-1"><b>是</b><sup>2</sup><br><font size="-1">16.21.0+</font>

<td><font size="-1">待定
<td><font size="-1">即将推出<sup>3</sup>
<td><font size="-1">待定<td
><font size="-1">即将推出<sup>3</sup>
<td><font size="-1">待定
<td><font size="-1">即将推出<sup>3</sup>

<tr><td><font size="-1">向管理员发送<a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">标签分析</a>数据
<td><font size="-1">待定

<td><font size="-1">待定

<td><font size="-1">待定
<td><font size="-1">待定
<td><font size="-1">待定
<td><font size="-1">待定
<td><font size="-1">待定
<td><font size="-1">待定

<tr><td><font size="-1">要求用户为其电子邮件和文档应用标签
<td><font size="-1">待定

<td><font size="-1">待定

<td><font size="-1">待定
<td><font size="-1">待定
<td><font size="-1">待定
<td><font size="-1">待定
<td><font size="-1">待定
<td><font size="-1">待定

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">将敏感度标签自动应用于内容</a>
<td><font size="-1">待定

<td><font size="-1">待定

<td><font size="-1">待定
<td><font size="-1">待定
<td><font size="-1">待定
<td><font size="-1">待定
<td><font size="-1">待定
<td><font size="-1">待定
</table>

<br><sup>1</sup>如果已配置，将提示用户提供标签降级的理由。 但是，尚未向管理员提供理由数据。 当支持“向管理员发送标签分析数据”功能时，它才可用。
<br><sup>2</sup>目前，仅在 Outlook for Windows 和 Outlook for Mac 中允许用户分配权限。 针对 Word、Excel 和 PowerPoint 的可用性待定。
<br><sup>3</sup>预计为 2019 日历年第 4 季度。

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a>在为内容提供敏感度标签后，何时应用内容标记或加密？

| 应用程序 | 内容标记 | 加密
| --- | --- | --- |
| 所有平台上的 Word、Excel 和 PowerPoint | 立即 | 立即 |
| Outlook for PC 和 Outlook for Mac | 通过 Exchange Online 发送电子邮件之后 | 立即 |
| 所有平台上的 Word、Excel 和 PowerPoint | 通过 Exchange Online 发送电子邮件之后 | 通过 Exchange Online 发送电子邮件之后 |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a>敏感度标签能否与 Azure 信息保护客户端一起在 Office for Windows 中运行？

否。 如果在 Office for Windows 中加载 Azure 信息保护客户端，则会关闭敏感度标签。

如果你已安装了 Azure 信息保护客户端，但你希望改为使用敏感度标签，则可以执行以下操作：

1. 配置“ **使用 Office 中的“敏感度”功能应用并查看敏感度标签**”组策略设置，可在“**用户配置/管理模板/Microsoft Office 2016/安全设置**”下方找到该设置。

  >注意：可通过传统的组策略部署机制或 [Office 云策略服务](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)来部署此设置。 
 
  或者，你也可以卸载或 [禁用](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) Azure 信息保护客户端。 

2. 重新启动所有 Office 应用程序。

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a>Office 的非订阅版本（例如 Office 2016 或 Office 2019）是否支持敏感度标签？

否。 敏感度标签仅在 Office 365 订阅中受支持，在任何非订阅版本中均不受支持。 但是，可在非订阅版本的 Office 中使用 Azure 信息保护统一标记客户端。 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a>在设置敏感度标签之前，我曾部署过保护模板。 它们去哪儿了？

启用敏感度标签后，管理员定义的[保护模板](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)将在 Office 用户体验中隐藏，因为对于已启用加密的敏感度标签而言，它们是多余的。 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a>文件或电子邮件能否具有多个分类？

用户一次只能为每个文档或电子邮件选择一个标签，这通常只会导致一个分类。 但是，如果用户选择一个子标签，则实际上同时应用了两个标签，即主要标签和次要标签。 通过使用子标签，文件可以具有两个分类，分别表示父级/子级关系，以实现更高级别的控制。 

例如，标签 **机密** 可能包含 **法律** 和 **财务**等子标签。 可将不同的分类视觉标记和不同的权限管理模板应用于这些子标签。 用户不能自行选择 **机密** 标签，只能选择其子标签之一，例如 **法律**。 因此，他们看到的标签是 **机密** / **法律**。 该文件的元数据包括 **机密**的一个自定义文本属性、 **法律**的一个自定义文本属性以及另一个包含两个值（**机密和法律**）的属性。 

使用子标签时，请不要在主要标签上配置视觉标记、保护和条件。 使用子级别时，仅在子标签上配置这些设置。 如果在主要标签及其子标签上配置这些设置，则子标签上的设置优先。

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a>标记电子邮件后，任何附件会自动获得相同的标记吗？

否。 标记带附件的电子邮件时，这些附件不会继承相同的标签。 附件要么没有标签，要么保留单独应用的标签。 但是，如果电子邮件标签应用了保护，则该保护将应用于 Office 附件。

## <a name="additional-resources"></a>其他资源

[有关 Azure 信息保护中分类和标记的常见问题](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[将敏感度标签应用于 Office 文档和电子邮件](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)