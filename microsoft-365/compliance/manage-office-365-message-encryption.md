---
title: 管理 Office 365 邮件加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.date: 03/04/2022
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 完成设置 OME Office 365 邮件加密 (OME) ，了解如何以多种方式自定义部署。
ms.openlocfilehash: 49a3957eb4bc2cf1123f04ab0dea77d2adb638b0
ms.sourcegitcommit: a216617d6ff27fe7d3089a047fbeaac5d72fd25c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "63512166"
---
# <a name="manage-office-365-message-encryption"></a>管理 Office 365 邮件加密

完成 OME Office 365 邮件加密 (OME) 后，可以通过多种方式自定义部署配置。 例如，可以配置是否启用一次传递代码、在邮件中显示"加密"Outlook 网页版等。 本文中的任务介绍了操作方法。

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>管理 Google、Yahoo 和 Microsoft 帐户收件人是否可以使用这些帐户登录 Office 365 邮件加密门户

当您设置新的 Office 365 邮件加密 功能时，您组织中的用户可以向组织外部的收件人发送邮件。 如果收件人使用 Google 帐户、Yahoo 帐户或 Microsoft 帐户等社交 *ID* ，则收件人可以使用社交 ID 登录 OME 门户。 如果需要，可以选择不允许收件人使用社交 ID 登录 OME 门户。
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>管理收件人是否可以使用社交 ID 登录 OME 门户
  
1. [连接远程Exchange Online PowerShell 进行连接](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 运行Set-OMEConfiguration SocialIdSignIn 参数的 cmdlet，如下所示：

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   例如，若要禁用社交 ID，请：

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   若要启用社交 ID，需要：

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>管理对应用门户的一Office 365 邮件加密代码的使用

如果由 OME 加密的邮件的收件人不使用 Outlook，则无论收件人使用的帐户是什么，收件人都会收到一个限时 Web 视图链接，允许他们阅读邮件。 此链接包括一次传递代码。 作为管理员，你可以决定收件人能否使用一次传递代码登录 OME 门户。
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>管理 OME 是否生成一次通过代码
  
1. 使用在组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 运行Set-OMEConfiguration OTPEnabled 参数的 cmdlet：

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -OTPEnabled <$true|$false>
   ```

   例如，若要禁用一次传递代码：

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   若要启用一次传递代码，请：

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>管理"加密"按钮在Outlook 网页版

作为管理员，您可以管理是否向最终用户显示此按钮。
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>管理"加密"按钮是否显示在Outlook 网页版
  
1. 使用在组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 使用 -SimplifiedClientAccessEnabled 参数运行 Set-IRMConfiguration cmdlet：

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   例如，若要禁用"加密 **"按钮** ：

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   启用"加密 **"** 按钮：

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>为 iOS 邮件应用程序用户启用电子邮件的服务器端解密

iOS 邮件应用程序无法解密受邮件安全Office 365 邮件加密。 作为Microsoft 365管理员，您可以对传递到 iOS 邮件应用程序的邮件应用服务器端解密。 当你选择使用服务器端解密时，该服务会向 iOS 设备发送邮件的解密副本。 客户端设备存储邮件的解密副本。 即使 iOS 邮件应用程序不向用户应用客户端使用权限，邮件也会保留有关使用权限的信息。 即使用户最初没有权限复制或打印邮件，也可以复制或打印邮件。 但是，如果用户尝试完成需要 Microsoft 365 邮件服务器的操作（如转发邮件），则如果用户最初没有使用权限，则服务器将不允许该操作。 但是，最终用户可以通过从 iOS 邮件应用程序内的不同帐户转发邮件来绕开"不要转发"使用限制。 无论你是否设置邮件的服务器端解密，在 iOS 邮件应用程序中均无法查看加密邮件的附件和受权限保护的邮件。
  
如果选择不允许将解密的邮件发送给 iOS 邮件应用程序用户，则用户会收到一条消息，指出他们没有查看邮件的权利。 默认情况下，不启用电子邮件的服务器端解密。
  
有关详细信息，以及客户端体验的视图，请参阅在客户端或客户端上查看iPhone [iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)。
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>管理 iOS 邮件应用程序用户能否查看受邮件Office 365 邮件加密
  
1. 使用在组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 使用 AllowRMSSupportForUnenlightenedApps 参数运行 Set-ActiveSyncOrganizations cmdlet：

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   例如，若要将服务配置为先解密邮件，然后再将其发送到非轻型应用（如 iOS 邮件应用程序）：

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   或者，若要将服务配置为不将解密的邮件发送到非轻型应用：

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> OWA/ActiveSync) 中的单个邮箱策略 (OWA/ActiveSync (，即，如果在各自的 OWA 邮箱策略或 ActiveSync 邮箱策略中将 -IRMEnabled 设置为 False，则这些配置将不会应用) 。 (

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>为 Web 浏览器邮件客户端启用电子邮件附件的服务器端解密

通常，在使用加密Office 365，附件会自动加密。 作为管理员，您可以为用户从 Web 浏览器下载的电子邮件附件应用服务器端解密。
  
使用服务器端解密时，服务会向设备发送文件的解密副本。 邮件仍加密。 即使浏览器不向用户应用客户端使用权限，电子邮件附件也会保留有关使用权限的信息。 用户可以复制或打印电子邮件附件，即使他们最初没有权限这样做。 但是，如果用户尝试完成需要 Microsoft 365 邮件服务器的操作（如转发附件）时，如果用户最初没有使用权限，则服务器将不允许此操作。
  
无论您是否设置附件的服务器端解密，用户均无法查看 iOS 邮件应用程序中加密和权限保护的邮件的任何附件。
  
如果选择不允许解密的电子邮件附件（这是默认设置），则用户会收到一条消息，指出他们没有查看附件的权利。
  
有关如何使用"Microsoft 365"选项对电子邮件和电子邮件附件Encrypt-Only加密，请参阅电子邮件的"仅加密["选项。](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>管理从 Web 浏览器下载时是否解密电子邮件附件
  
1. 使用在组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 使用 DecryptAttachmentForEncryptOnly 参数Set-IRMConfiguration cmdlet：

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   例如，若要将服务配置为在用户从 Web 浏览器下载电子邮件附件时解密这些附件，请执行以下操作：

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   若要将服务配置为在下载时保留加密电子邮件附件，请运行以下操作：

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>确保所有外部收件人使用 OME 门户读取加密邮件

您可以使用自定义品牌模板强制收件人接收包装邮件，以指示他们阅读 OME 门户中的加密电子邮件，而不是使用 Outlook 或 Outlook 网页版。 如果您希望更好地控制收件人使用他们接收的邮件，您可能需要这样做。 例如，如果外部收件人在 Web 门户中查看电子邮件，您可以设置电子邮件的到期日期，并可以撤销该电子邮件。 这些功能仅支持通过 OME 门户。 在创建邮件流规则时，可以使用"加密"选项和"不要转发"选项。

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>使用自定义模板强制所有外部收件人使用 OME 门户和加密电子邮件

1. 使用在组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 运行 New-TransportRule cmdlet：

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    其中：

   - `mail flow rule name` 是您想要用于新邮件流规则的名称。

   - `option name` 为 或 `Encrypt` `Do Not Forward`。

   - `template name` 是赋予自定义品牌模板的名称，例如 `OME Configuration`。

   若要使用"OME 配置"模板加密所有外部电子邮件，并应用Encrypt-Only选项：

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   若要使用"OME 配置"模板加密所有外部电子邮件并应用"不要转发"选项：

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>自定义电子邮件和 OME 门户的外观

若要详细了解如何为组织自定义 OME，请参阅将组织的 [品牌添加到加密邮件中](add-your-organization-brand-to-encrypted-messages.md)。 为了能够跟踪和撤销加密邮件，必须将自定义品牌添加到 OME 门户。
  
## <a name="disable-the-new-capabilities-for-ome"></a>禁用 OME 的新功能

我们希望它不会实现，但如果需要，禁用 OME 的新功能非常简单。 首先，需要删除已创建使用新 OME 功能的任何邮件流规则。 有关删除邮件流规则的信息，请参阅 [管理邮件流规则](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。 然后，在 PowerShell 中Exchange Online这些步骤。
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>禁用 OME 的新功能
  
1. 使用在组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 如果启用了"加密"按钮，Outlook 网页版使用 SimplifiedClientAccessEnabled 参数运行 Set-IRMConfiguration cmdlet 来禁用它。 否则，请跳过此步骤。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. 通过运行 AzureRMSLicensingEnabled 参数设置为 false 的 Set-IRMConfiguration cmdlet 禁用 OME 的新功能：

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
