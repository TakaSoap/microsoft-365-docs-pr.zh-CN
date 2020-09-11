---
title: 基本移动性和安全性的功能
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 基本移动性和安全性可帮助您保护和管理移动设备。
ms.openlocfilehash: a88afd539209d20046a778f8c6d16cadd51b5a9a
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430097"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>基本移动性和安全性的功能

基本移动性和安全性可帮助您保护和管理移动设备，如 Iphone、Ipad、Androids 和 Windows phone （由组织中的许可 Microsoft 365 用户使用）。 您可以使用设置来创建移动设备管理策略，这些策略可帮助控制对受支持的移动设备和应用程序的 Microsoft 365 电子邮件和文档的访问。 如果设备丢失或被盗，可以远程擦除设备以删除敏感的组织信息。

## <a name="supported-devices"></a>支持的设备

您可以使用基本移动性和安全性来保护和管理以下设备。

- iOS 11.0 或更高版本
    
- Android 5.0 或更高版本<sup>3</sup>
    
- Windows 8.1<sup>1</sup>
    
- Windows 8.1 RT<sup>1</sup>
    
- Windows 10<sup>2</sup>
    
- Windows 10 移动版<sup>2</sup>   

<sup>1</sup>Windows 8.1 RT 设备的访问控制仅限于 Exchange ActiveSync。

<sup>2</sup>Windows 8.1 RT 设备的访问控制仅限于 Exchange ActiveSync。
Windows 10 的访问控制需要一个包含 Azure AD Premium 的订阅，并且该设备需要加入 Azure Active Directory。

<sup>3</sup>Windows 8.1 RT 设备的访问控制仅限于 Exchange ActiveSync。
6月2020日之后，如果 Android 版本低于9，则无法管理除 Samsung Knox 设备之外的密码设置。

>[!NOTE]
>已注册早期 OS 版本的设备将继续正常运行，但功能可能会更改，恕不另行通知。

如果组织中的人员使用的是基本移动性和安全性不支持的移动设备，则可能需要阻止 Exchange ActiveSync 应用程序对这些设备的 Microsoft 365 电子邮件的访问权限，以帮助使组织的数据更加安全。 有关阻止 Exchange ActiveSync 的步骤，请参阅 [Manage device access settings In Basic 可移动性 And Security](manage-device-access-settings.md)。

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Microsoft 365 电子邮件和文档的访问控制

下表中不同类型的移动设备的受支持的应用程序提示用户注册基本移动性和安全性，其中包含一个新的移动设备管理策略，该策略适用于用户的设备，并且用户以前未注册该设备。 如果用户的设备不符合策略，则可能会阻止用户访问这些应用程序中的 Microsoft 365 资源，或者可能会阻止用户访问，但 Microsoft 365 会报告违反策略的情况。

|**产品**|**iOS 10.0 或更高版本**|**Android 5.0 或更高版本**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync 包括内置电子邮件和第三方应用程序（如 TouchDown），后者使用 Exchange ActiveSync 版本14.1 或更高版本。 |邮件 |电子邮件 |
|**Office**  和 **OneDrive For business** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**在电话和平板电脑上**：<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **仅电话：** <br/> Office Mobile |

>[!NOTE]
- >对 iOS 10.0 及更高版本的支持包括 iPhone 和 iPad 设备。
- >适用于 Microsoft 365 的移动设备管理不支持 BlackBerry OS 设备的管理。 使用 BlackBerry Business 云服务 (BBCS) 来自 BlackBerry，以管理 BlackBerry OS 设备。 支持运行 Android OS 的 Blackberry 设备作为标准 Android 设备
- >如果用户使用移动浏览器访问 Microsoft 365 SharePoint 网站、Office Online 中的文档或 Outlook Web App 中的电子邮件，则不会提示用户进行注册，也不会将其报告为 "违反策略"。
    
下图显示了具有新设备的用户登录到支持具有基本移动性和安全性的访问控制的应用时，会发生什么情况。 阻止用户访问应用程序中的 Microsoft 365 资源，直到他们注册其设备。

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本移动性和安全访问控制":::

注意：在 MDM for Microsoft 365 商业标准中创建的策略和访问规则将替代 exchange ActiveSync 移动设备邮箱策略和在 Exchange 管理中心中创建的设备访问规则。 在 MDM for Microsoft 365 商业标准中注册设备后，应用于该设备的任何 Exchange ActiveSync 移动设备邮箱策略或设备访问规则都将被忽略。 若要了解有关 Exchange ActiveSync 的详细信息，请参阅 exchange [Online 中的 Exchange ActiveSync](https://go.microsoft.com/fwlink/p/?LinkId=524380)。

## <a name="policy-settings-for-mobile-devices"></a>移动设备的策略设置

如果您创建一个策略以阻止打开某些设置的访问，则在使用 [microsoft 365 电子邮件和文档的访问控制](capabilities.md)中列出的受支持的应用程序时，将阻止用户访问 microsoft 365 资源。 

可以阻止用户访问 Microsoft 365 资源的设置包括以下部分：

- 安全性
    
- 加密
    
- 越狱断开
    
- 托管电子邮件配置文件  

例如，下图显示了具有已注册设备的用户不符合应用于其设备的移动设备管理策略中的安全设置时会发生的情况。 用户使用基本移动性和安全性登录到支持访问控制的应用程序。 阻止他们访问应用程序中的 Microsoft 365 资源，直到其设备符合安全设置。

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="基本移动性和安全性合规性邮件":::

以下各节列出了可用于帮助保护和管理连接到 Microsoft 365 组织资源的移动设备的策略设置。

## <a name="security-settings"></a>安全设置

|**设置名称**|**iOS 7.1 及更高版本**|**Android 5 及更高版本**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|要求使用密码|是|是|是|
|阻止简单密码|是|否|否|
|需要字母数字密码|是|否|否|
|最短密码长度 |是|是|是|
|擦除设备之前的登录失败次数 |是|是|是|
|设备锁定之前的不活动分钟数 |是|是|是|
|密码过期 (天)  |是|是|是|
|记住密码历史记录并防止重复使用 |是|是|是|

## <a name="encryption-settings"></a>加密设置 

|**设置名称**|**iOS 7.1 及更高版本**|**Android 5 及更高版本**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|要求设备<sup>1</sup>上的数据加密 |否|是|是|

<sup>1</sup>使用 Samsung Knox，还可以要求对存储卡加密。 

## <a name="jail-broken-setting"></a>越狱中断设置 

|**设置名称**|**iOS 7.1 及更高版本**|**Android 5 及更高版本**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|设备不能越狱断开或根 |是|是|是|

## <a name="managed-email-profile-option"></a>托管电子邮件配置文件选项 

如果用户使用手动创建的电子邮件配置文件，则可通过以下选项阻止用户访问其 Microsoft 365 电子邮件。 IOS 设备上的用户必须先删除其手动创建的电子邮件配置文件，然后才能访问其电子邮件。 删除配置文件后，系统会自动在该设备上创建一个新的配置文件。 有关最终用户如何符合标准的说明，请参阅 [找到现有的电子邮件帐户](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)。

|**设置名称**|**iOS 7.1 及更高版本**|**Android 5 及更高版本**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|电子邮件配置文件已管理 |是|否|否|

## <a name="cloud-settings"></a>云设置 

|**设置名称**|**iOS 7.1 及更高版本**|**Android 5 及更高版本**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|需要加密备份 |是|否|否|
|阻止云备份 |是|否|否|
|阻止文档同步 |是|否|否|
|阻止照片同步  |是|否|否|
|允许 Google 备份  |不适用|否|是|
|允许 Google 帐户自动同步  |不适用|否|是|

## <a name="system-settings"></a>系统设置 

|**设置名称**|**iOS 7.1 及更高版本**|**Android 5 及更高版本**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|阻止屏幕捕获 |是|否|是|
|阻止从设备发送诊断数据 |是|否|是|

## <a name="application-settings"></a>应用程序设置 

|**设置名称**|**iOS 7.1 及更高版本**|**Android 5 及更高版本**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|阻止设备上的视频会议 |是|否|否|
|阻止对应用商店的访问 |是|否|是|
|在访问应用商店时需要密码 |否|是|是|

## <a name="device-capabilities-settings"></a>设备功能设置 

|**设置名称**|**iOS 7.1 及更高版本**|**Android 5 及更高版本**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|阻止与可移动存储的连接 |是|是|否|
|阻止蓝牙连接 |是|是|否|

##  <a name="additional-settings"></a>其他设置 

您可以使用 PowerShell cmdlet 设置以下附加策略设置。 有关详细信息，请参阅 [Security & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)。

|**设置名称**|**iOS 7.1 及更高版本**|**Android 5 及更高版本**|
|:-----|:-----|:-----|
|CameraEnabled|是|是|
|RegionRatings|是|否|
|MoviesRatings|是|否|
|TVShowsRating |是|否|
|AppsRatings |是|否|
|AllowVoiceDialing |是|否|
|AllowVoiceAssistant |是|否|
|AllowAssistantWhileLocked  |是|否|
|AllowPassbookWhileLocked |是|否|
|MaxPasswordGracePeriod |是|否|
|PasswordQuality |否|是|
|SystemSecurityTLS  |是|否|
|WLANEnabled  |否|否|

## <a name="settings-supported-by-windows"></a>Windows 支持的设置 

你可以通过将 Windows 10 设备注册为移动设备来管理这些设备。 部署适用的策略后，在首次使用内置电子邮件应用访问其 Microsoft 365 电子邮件时，将需要具有 Windows 10 设备的用户注册基本移动性和安全性 (需要 Azure AD 高级订阅) 。

已注册为移动设备的 Windows 10 设备支持以下设置。 这些设置不会阻止用户访问 Microsoft 365 资源。

### <a name="security-settings"></a>安全设置

- 需要字母数字密码

- 最短密码长度
    
- 擦除设备之前的登录失败次数
    
- 设备锁定之前的不活动分钟数
    
- 密码过期 (天) 
    
- 记住密码历史记录并防止重复使用   

>[!NOTE]
>以下设置控制密码仅控制本地 Windows 帐户。 通过加入域或 Azure Active Directory 提供的 Windows 帐户不受这些设置的影响。

### <a name="system-settings"></a>系统设置

阻止从设备发送诊断数据。

### <a name="additional-settings"></a>其他设置

您可以使用 PowerShell cmdlet 设置这些附加策略设置：

- AllowConvenienceLogon
    
- UserAccountControlStatus
    
- FirewallStatus
    
- AutoUpdateStatus
    
- AntiVirusStatus   

- AntiVirusSignatureStatus
    
- SmartScreenEnabled
    
- WorkFoldersSyncUrl
    

## <a name="remotely-wipe-a-mobile-device"></a>远程擦除移动设备

如果设备丢失或被盗，可以通过执行从 Security & 合规中心 >**数据丢失防护**  >  **设备管理**中的擦除操作，来删除敏感的组织数据并帮助阻止对 Microsoft 365 组织资源的访问。 您可以执行选择性擦除以仅删除组织数据或完全擦除以删除设备中的所有信息，并将其还原到其出厂设置。

有关详细信息，请参阅 [在基本移动和安全中擦除移动设备](wipe-mobile-device.md)。

## <a name="related-topics"></a>相关主题

[Microsoft 365 的基本移动性和安全性概述](overview.md)

[在基本移动性和安全性中创建设备安全策略](create-device-security-policies.md)