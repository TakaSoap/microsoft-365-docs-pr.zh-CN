---
title: 邮件加密常见问题解答
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 05/22/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: 对新的邮件保护功能如何工作有疑问？ 请在此处查看答案。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2ad0ef4f16e5b458da80227b93fab574e3ce8dde
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394680"
---
# <a name="message-encryption-faq"></a>邮件加密常见问题解答

对新的邮件保护功能如何工作有疑问？ 请在此处查看答案。 此外，请参阅 Azure[](/information-protection/get-started/faqs-rms)信息保护中有关数据保护的常见问题解答，以解答有关 Azure 信息保护中数据保护服务（Azure 权限管理）的问题。

## <a name="what-is-office-365-message-encryption-ome"></a>什么是 Office 365 邮件加密 (OME) ？

OME 结合了电子邮件加密和权限管理功能。 权限管理功能由 Azure 信息保护提供支持。

## <a name="who-can-use-ome"></a>谁可以使用 OME？

在下列情况下，可以使用 OME 的新功能：
  
- 如果从未在 Office 365 中为 Exchange Online 设置 OME 或 IRM。

- 如果已设置 OME 和 IRM，则如果你使用的是 Azure 信息保护中的 Azure 权限管理服务，可以使用这些步骤。

- 如果将 Exchange Online 与 Active Directory 权限管理服务 (AD RMS) ，则不能马上启用这些新功能。 相反，你需要首先 [将 AD RMS 迁移到 Azure 信息保护](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) 。 完成迁移后，可以成功设置 OME。

  如果选择将本地 AD RMS 与 Exchange Online 一同使用，而不是迁移到 Azure 信息保护，将无法使用这些新功能。

## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>使用新的 OME 功能需要哪些订阅？

若要使用新的 OME 功能，你需要以下计划之一：
  
- Office 365 邮件加密作为 Office 365 企业版 E3 和 E5、Microsoft 企业版 E3 和 E5、Microsoft 365 商业高级版、Office 365 A1、A3 和 A5 以及 Office 365 政府版 G3 和 G5 的一部分提供。 客户无需其他许可证，就无需获得 Azure 信息保护支持的新保护功能。

- 还可以将 Azure 信息保护计划 1 添加到以下计划，以接收新的 Office 365 邮件加密功能：Exchange Online 计划 1、Exchange Online 计划 2、Office 365 F1、Microsoft 365 商业基础版、Microsoft 365 商业标准版或 Office 365 企业版 E1。

- 从 Office 365 邮件加密受益的每个用户都需要获得许可，以涵盖此功能。

- 有关完整列表，请参阅 [Office](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) 365 邮件加密的 Exchange Online 服务说明。

## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>能否将 Exchange Online 与在 Azure 信息保护 (BYOK) 自己的密钥一起使用？

是的。 Microsoft 建议在设置 OME 之前完成设置 BYOK 的步骤。
  
有关 BYOK 的信息，请参阅 [规划和实现 Azure 信息保护租户密钥](/information-protection/plan-design/plan-implement-tenant-key)。
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>使用 Azure 信息保护的 OME 和 BYOK 是否更改了 Microsoft 对第三方数据请求（如子请求）的方法？

不正确。 OME 以及提供和控制你自己的加密密钥的选项（称为 BYOK）来自 Azure 信息保护，并非旨在响应执法机构的子请求。 OME 和用于 Azure 信息保护的 BYOK 专为以合规性为中心的客户设计。 Microsoft 非常重视客户数据的第三方请求。 作为云服务提供商，我们始终宣传客户数据的隐私。 如果我们收到一个副发，我们始终尝试将第三方重定向到客户以获取信息。  (Brad Smith 的博客：保护客户数据免受 [政府](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/) 窥探) 。 我们会定期发布收到的请求的详细信息。 有关第三方数据请求详细信息，请参阅响应访问 Microsoft[](https://www.microsoft.com/trustcenter/privacy/govt-requests-for-data)信任中心上的客户数据的政府请求和执法机构请求。 另请参阅 OST 联机服务条款中的"客户数据 ([披露) 。 ](https://www.microsoft.com/Licensing/product-licensing/products.aspx)
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>此功能与旧版 Office 365 邮件加密 (OME) 和信息权限管理 (IRM) 功能相关？

Office 365 邮件加密的新功能是现有 IRM 和旧 OME 解决方案演变的。 下表提供了更多详细信息。
  
**旧版 OME、IRM 和新 OME 功能的比较**

| 功能 | OME 的以前版本 | IRM | 新的 OME 功能 |
|:-----|:-----|:-----|:-----|
|**发送加密电子邮件**|仅通过 Exchange 邮件流规则|从 Outlook for Windows、Outlook for Mac 或 Web 上的 Outlook 启动的最终用户;或通过 Exchange 邮件流规则|从 Outlook for Windows、Outlook for Mac 或 Web 上的 Outlook 启动的最终用户;或邮件流规则|
|**版权管理**|-|"不要转发"选项和自定义模板|"不要转发"选项、仅加密选项、默认模板和自定义模板|
|**支持的收件人类型**|仅外部收件人|仅内部收件人|内部和外部收件人|
|**收件人体验**|外部收件人收到一条 HTML 邮件，该消息在浏览器或已下载的移动应用中下载并打开。|内部收件人仅收到 Outlook for Windows、Outlook for Mac 和 Outlook 网页中的加密电子邮件。|内部和外部收件人在 Outlook for Windows、Outlook for Mac、Outlook 网页版、Outlook for Android 和 Outlook for iOS 中接收电子邮件，或者通过 Web 门户接收电子邮件，而不管他们是否在同一个组织或任何组织中。 OME 门户无需单独下载。|
|**自带密钥支持**|不可用|不可用| BYOK 支持|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>如何为组织启用新的 OME 功能？

请参阅 [设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>OME 的以前版本将被弃用吗？

你仍然可以使用以前版本的 OME，目前不会弃用它。 但是，我们强烈建议组织使用新的和改进的 OME 解决方案。 尚未部署 OME 的客户无法设置以前版本的 OME 的新部署。
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>我的组织使用 Active Directory 权限管理，我能否使用此功能？

不正确。 如果将 Exchange Online 与 Active Directory 权限管理服务 (AD RMS) ，则不能马上启用这些新功能。 相反，你需要首先 [将 AD RMS 迁移到 Azure 信息保护](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) 。
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>我的组织具有 Exchange 混合部署。 我可以使用此功能吗？

本地用户可以使用 Exchange Online 邮件流规则发送加密邮件。 为此，您需要通过 Exchange Online 路由电子邮件。 有关详细信息，请参阅第[2 部分：将邮件配置为从您的电子邮件服务器流向 Microsoft 365。](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>我需要使用什么电子邮件客户端才能创建 OME 加密邮件？ 哪些应用程序支持发送受保护的邮件？

可以从 Outlook 2016、Outlook 2013 for Windows 和 Mac 以及 Outlook 网页版创建受保护的邮件。 有关发送加密邮件的信息，请参阅在 Outlook for PC 中发送、查看和回复 [加密邮件](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-us&rs=en-us&ad=us)。
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>支持哪些电子邮件客户端阅读和回复受保护的电子邮件？

Microsoft 365 用户可以从 Outlook for Windows 和 Mac (2013 和 2016) 、Outlook 网页版以及 Outlook Mobile (Android 和 iOS) 进行读取和响应。 如果组织允许，您还可以使用 iOS 本机邮件客户端。 如果你不是 Microsoft 365 用户，可以通过 Web 浏览器读取和回复 Web 上的加密邮件。

## <a name="what-email-clients-support-the-encrypt-only-protected-emails"></a>哪些电子邮件客户端支持仅加密保护的电子邮件？

Microsoft 365 用户可以使用 Outlook for PC 版本 2019 和 Microsoft 365 创建受仅加密策略保护的邮件。  这意味着应用了新的仅加密策略的邮件可以直接在 Outlook 网页版、Outlook for iOS 和 Outlook for Android 以及 Outlook for PC 版本 2019 和 Microsoft 365 中读取。

## <a name="is-there-a-size-limit-for-messages-you-can-send-with-ome"></a>可以使用 OME 发送的邮件是否有大小限制？

是。 可以与 OME 一起发送的最大邮件大小（包括附件）为 25 MB。 有关详细信息，请参阅邮件 [限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits-1)。

## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>受保护的电子邮件中支持哪些文件类型作为附件？ 附件是否继承了与受保护的电子邮件相关联的保护策略？

您可以将任何文件类型附加到受保护的邮件。 有一个例外，保护策略仅适用于 Azure 信息保护客户端支持的文件类型中提到的 [文件格式](/information-protection/rms-client/client-admin-guide-file-types)。 OME 不支持以下 Office 程序 97-2003 版本：Word (.doc) 、Excel (.xls) 和 PowerPoint (.ppt) 。

如果支持文件格式（如 Word、Excel 或 PowerPoint 文件），则文件将始终受到保护，即使收件人已下载附件。 例如，假设附件受"请勿转发"保护。 原始收件人下载文件，创建一封邮件给新收件人并附加到该文件。 当新收件人收到该文件时，该收件人将无法打开受保护的文件。
  
## <a name="are-pdf-file-attachments-supported"></a>PDF 文件附件是否受支持？

简短回答是"是"！ PDF 加密允许您通过安全通信或安全协作来保护敏感的 PDF 文档。 发送电子邮件时，Office 365 服务加密 PDF 文件附件，而不是 Outlook 客户端。

对于 Outlook 网页版、Outlook for iOS 和 Outlook for Android，无需任何步骤即可加密发送的 PDF。 这些客户端本机支持 PDF 加密。

Outlook 桌面在本机不支持加密 PDF 文件附件。 相反，您需要设置 Exchange 邮件流规则或 DLP，以首先将加密应用于 PDF 附件。 当您从 Outlook 桌面版发送带 PDF 附件的邮件时，客户端会首先将包含附件的邮件发送到服务。 当服务收到文件时，该服务在 Exchange Online 中对数据丢失防护应用 OME 保护 (DLP) 策略或邮件流规则。 接下来，Exchange Online 发送带受保护 PDF 文件附件的邮件。

若要启用 PDF 附件加密，请运行 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中的以下命令：

```powershell
Set-IRMConfiguration -EnablePdfEncryption $true
```

PDF 加密允许您通过安全通信或安全协作来保护敏感的 PDF 文档。 对于所有 Outlook 客户端，邮件和未受保护的 PDF 附件继承 Exchange Online 中数据丢失防护 (DLP) 策略或邮件流规则的 OME 保护。 此外，如果 Outlook 网页版用户附加到未受保护的 PDF 文档，并应用对邮件的保护，则邮件将继承对邮件的保护。 用户只能在支持受保护 PDF 的应用程序中打开加密的附件 (例如，OME 门户和 Azure 信息保护查看器) 。

> [!IMPORTANT]
> Outlook 桌面客户端不支持 PDF 加密。

## <a name="are-onedrive-for-business-attachments-supported"></a>OneDrive for Business 附件是否受支持？

Not yet. 不支持 OneDrive for Business 附件，最终用户无法加密包含云 OneDrive for Business 附件的邮件。
  
## <a name="what-email-clients-support-preview-of-encrypted-attachments-in-protected-emails"></a>哪些电子邮件客户端支持预览受保护的电子邮件中的加密附件？

当附件受受保护邮件保护时，Outlook 客户端将提供直接预览文档的能力。 Outlook 支持预览 office 文档 (docx、xlsx、pptx、doc、xls、ppt) 。 Outlook 网页版支持预览 office 文档 (docx、xlsx、pptx) 和 PDF。  

## <a name="what-email-clients-support-revocation-of-protected-emails"></a>哪些电子邮件客户端支持吊销受保护的电子邮件？

Outlook 网页页面支持吊销受保护的邮件。  有关详细信息 [，请参阅如何撤销已发送的加密](revoke-ome-encrypted-mail.md#how-to-revoke-an-encrypted-message-that-you-sent) 邮件。

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>我能否通过设置策略自动加密邮件？

是。 使用 Exchange Online 中的邮件流规则根据某些条件自动加密邮件。 例如，可以创建基于收件人 ID、收件人域或邮件正文或主题内容的策略。 请参阅 [定义邮件流规则以加密 Office 365 中的电子邮件](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail"></a>能否自动删除传入和传出邮件的加密？

管理员可以设置邮件流规则以删除传出邮件的加密。 不能设置规则来删除传入邮件的加密。

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>我能否通过安全与合规中心在"数据丢失防护" (DLP) 设置策略来自动 &amp; 加密邮件？

是的。 您可以在 Exchange Online 中设置邮件流规则，或在安全与合规中心内使用 DLP &amp; 设置邮件流规则。
  
## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>我可以使用我的公司品牌自定义加密邮件吗？

是的。 有关自定义电子邮件和 OME 门户的信息，请参阅将组织的品牌添加到加密邮件。 请参阅[将组织的品牌添加到加密邮件。](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>是否有加密电子邮件的报告功能或见解？

安全与合规中心有一个加密报告。 请参阅 [查看安全与合规中心&电子邮件安全报告](../security/office-365-security/view-email-security-reports.md)。
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>能否将邮件加密与电子数据展示等合规性功能一同使用？

是。 Microsoft 365 合规性功能可发现所有加密电子邮件。

## <a name="can-i-remove-encryption-from-email"></a>能否从电子邮件中删除加密？

管理员可以设置邮件流规则以删除加密。 不能从另一个组织应用的邮件中删除使用邮件流规则的加密，除非使用仅加密保护对邮件进行加密。

## <a name="is-delegated-access-supported"></a>是否支持委派访问？

此时不作用。

## <a name="can-i-send-as-a-shared-mailbox-and-encrypt-emails"></a>我能否以共享邮箱形式发送并加密电子邮件？

当某人发送与加密邮件流规则匹配的电子邮件时，该邮件在发送之前已加密。

## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>我能否打开发送到共享邮箱的加密邮件？

是的。 共享邮箱支持加密邮件。

- 用户可以在共享邮箱中打开受保护的邮件，其中共享邮箱收到受保护的邮件作为通讯组的一部分。

- 用户在使用 Outlook for Windows、Outlook for Mac 和 Web 上的 Outlook 时可以查看继承电子邮件保护的附件。

下表列出了共享邮箱支持的客户端。

| 平台 | 阅读邮件 | 查看电子邮件附件 |
|----------|-----------|------------------------|
| Outlook 网页版 | 是 | 是                |
| Outlook for Windows| 是 | 是                |
| Outlook for Mac    | 是 | 是                |
| Outlook for Android| 是 | 否                 |
| Outlook for iOS    | 是 | 否                 |
|

目前存在两个已知限制：

- 无法打开使用 Outlook 移动版在移动设备上接收的电子邮件的附件。

- 我们不支持通过启用电子邮件的安全组进行分配。 我们仅支持通过直接用户分配对共享邮箱的访问权限，并且为 Exchange Online 启用自动映射。 默认情况下，为 Exchange Online 启用自动映射。

**将用户分配给共享邮箱**

1. [使用远程 PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?v=exchg.150).aspx) 。

2. 使用 Automapping Add-MailboxPermission运行该 cmdlet。 本示例向 Ayla 授予对支持邮箱的完全访问权限。

   ```powershell
   Add-MailboxPermission -Identity support@contoso.onmicrosoft.com -User ayla@contoso.com -AccessRights FullAccess -AutoMapping $true
   ```

## <a name="can-i-open-encrypted-messages-sent-to-another-users-mailbox-with-fullaccess"></a>我能否使用 Fullaccess 打开发送到其他用户邮箱的加密邮件？

只要获得直接访问并启用自动映射，用户就可以打开加密邮件。 如果访问权限是通过启用电子邮件的安全组授予的，则不允许访问。

## <a name="what-do-i-do-if-i-dont-receive-the-one-time-pass-code-after-i-requested-it"></a>如果我在请求后没有收到一次传递代码，该怎么办？

首先，检查电子邮件客户端中的垃圾邮件文件夹。 组织的 DKIM 和 DMARC 设置可能会导致这些电子邮件最终被筛选为垃圾邮件。

接下来，在安全与合规中心&隔离。 通常，包含一次传递代码的邮件（尤其是组织收到的第一批邮件）最终被隔离。