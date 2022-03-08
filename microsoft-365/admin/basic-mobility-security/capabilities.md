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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: 基本移动性和安全性可帮助您保护和管理移动设备。
ms.openlocfilehash: 04ee7e7dfbc4937d4add2e4c27e7f686b596fadb
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63314877"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>基本移动性和安全性的功能

基本移动性和安全性可帮助你保护和管理组织中许可的 Microsoft 365 用户使用的移动设备，如 iPhone、iPad、Android 和 Windows 电话。 可以使用设置创建移动设备管理策略，这些设置可帮助控制对支持Microsoft 365和应用的组织电子邮件和文档的访问权限。 如果设备丢失或被盗，你可以远程擦除设备以删除敏感的组织信息。

## <a name="supported-operating-systems"></a>支持的操作系统 

按照Microsoft Intune移动性和安全性支持的最低设备操作系统指南操作。 有关详细信息，请参阅 [Intune 支持的操作系统](/mem/intune/fundamentals/supported-devices-browsers)。

您可以使用基本移动性和安全性保护和管理以下设备。

- iOS
- Android (包括 Samsung Knox) <sup>1</sup>
- Windows <sup>2、3</sup>

<sup>1</sup>2020 年 6 月之后，超过 9 的 Android 版本无法管理密码设置，Samsung Knox 设备上除外。

<sup>2</sup>RT Windows 8.1的访问控制仅限于Exchange ActiveSync。

<sup>3</sup>Windows 10访问控制需要订阅，Azure AD Premium设备需要加入到 Azure Active Directory。

> [!NOTE]
> 已注册较早操作系统版本的设备仍可以继续运行，尽管这些功能可能会在不另行通知的情况下更改。

如果组织成员使用的移动设备不受基本移动性和安全性支持，你可能希望阻止 Exchange ActiveSync 应用访问这些设备的 Microsoft 365 电子邮件，以帮助使组织的数据更安全。 有关阻止访问Exchange ActiveSync，请参阅基本移动性和安全性[中的管理设备访问设置](manage-device-access-settings.md)。

## <a name="access-control-for-microsoft-365-email-and-documents"></a>电子邮件和Microsoft 365访问控制

下表中支持的不同类型的移动设备的应用提示用户注册基本移动性和安全性，其中存在适用于用户设备且用户之前尚未注册该设备的新移动设备管理策略。 如果用户的设备不符合策略，具体取决于策略的设置方式，可能会阻止用户访问这些应用中的 Microsoft 365 资源，或者他们可能具有访问权限，但 Microsoft 365 报告违反策略。

|**产品**|**iOS**|**Android**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync内置电子邮件和第三方应用（如 TouchDown）使用 Exchange ActiveSync 14.1 或更高版本。 |邮件 |电子邮件 |
| Office and  **OneDrive for Business** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**在手机和平板电脑上**：<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **仅在电话上：** <br/> Office Mobile |

> [!NOTE]
>
> - 对 iOS 10.0 及更高版本的支持包括iPhone和iPad设备。
> - 基本安全性和移动性不支持管理 BlackBerry 操作系统设备。 使用 BlackBerry 商业云服务 (BBCS) 管理 BlackBerry 操作系统设备。 运行 Android 操作系统的 Blackberry 设备作为标准 Android 设备受到支持
> - 如果用户使用移动浏览器访问 Microsoft 365 SharePoint 网站、Office Online 中的文档或 Outlook Web App 中的电子邮件，将不会提示用户注册，也不会被阻止或报告违反策略。

下图显示了当具有新设备的用户登录支持具有基本移动性和安全性的访问控制的应用时会发生什么情况。 阻止用户访问应用中Microsoft 365资源，直到用户注册其设备。

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本移动性和安全性访问控制。":::

> [!NOTE]
> 在基本移动性和安全性 for Microsoft 365 商业标准版 中创建的策略和访问规则Exchange ActiveSync移动设备邮箱策略和在 Exchange 管理中心中创建的设备访问规则。 在基本移动性和安全性 for Microsoft 365 商业标准版 注册设备后，Exchange ActiveSync设备的任何邮箱策略或设备访问规则都将被忽略。 若要详细了解Exchange ActiveSync，请参阅Exchange ActiveSync  [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)。

## <a name="policy-settings-for-mobile-devices"></a>移动设备的策略设置

如果创建策略来阻止访问，但某些设置已打开，则当使用 [Microsoft 365](capabilities.md) 电子邮件和文档的访问控制中列出的受支持应用时，将阻止用户访问 Microsoft 365 资源。

以下部分包含可阻止用户访问Microsoft 365资源的设置：

- 安全性

- 加密

- 已越狱

- 托管电子邮件配置文件

例如，下图显示了当已注册设备的用户不符合适用于其设备的移动设备管理策略中的安全设置时会发生什么情况。 用户登录支持具有基本移动性和安全性的访问控制的应用。 阻止他们访问应用中Microsoft 365资源，直到其设备符合该设置。

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="基本移动性和安全性合规性消息。":::

以下各节列出了可用于帮助保护和管理连接到组织资源的移动设备Microsoft 365设置。

## <a name="security-settings"></a>安全设置

|**设置名称**|**iOS** |**Android**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|要求使用密码|是|是|是|
|阻止简单密码|是|否|否|
|需要字母数字密码|是|否|否|
|最短密码长度 |是|是|是|
|擦除设备之前登录失败次数 |是|是|是|
|设备锁定前不活动分钟数 |是|是|是|
|密码过期(天数) |是|是|是|
|记住密码历史记录并禁止重复使用 |是|是|是|

## <a name="encryption-settings"></a>加密设置

|**设置名称**|**iOS** |**Android**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|要求对设备进行数据加密<sup>1</sup> |否|是|是|

<sup>1</sup>使用 Samsung Knox，还可以要求对存储卡进行加密。

## <a name="jail-broken-setting"></a>已越狱设置

|**设置名称**|**iOS** |**Android**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|设备无法越狱或具有 root 权限 |是|是|是|

## <a name="managed-email-profile-option"></a>托管电子邮件配置文件选项

如果用户使用手动创建的电子邮件配置文件Microsoft 365以下选项可以阻止用户访问他们的电子邮件。 iOS 设备上的用户必须先删除手动创建的电子邮件配置文件，然后才能访问电子邮件。 删除配置文件后，将在设备上自动创建一个新配置文件。 有关最终用户如何合规的说明，请参阅已 [找到现有电子邮件帐户](/intune-user-help/existing-company-email-account-found)。

|**设置名称**|**iOS** |**Android**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|管理电子邮件配置文件 |是|否|否|

## <a name="cloud-settings"></a>云设置

|**设置名称**|**iOS** |**Android**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|需要加密备份 |是|否|否|
|阻止云备份 |是|否|否|
|阻止文档同步 |是|否|否|
|阻止照片同步  |是|否|否|
|允许 Google 备份  |不适用|否|是|
|允许 Google 帐户自动同步  |不适用|否|是|

## <a name="system-settings"></a>系统设置

|**设置名称**|**iOS** |**Android**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|阻止屏幕捕获 |是|否|是|
|阻止从设备发送诊断数据 |是|否|是|

## <a name="application-settings"></a>应用程序设置

|**设置名称**|**iOS** |**Android**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|阻止设备上的视频会议 |是|否|否|
|阻止对应用商店的访问 |是|否|是|
|访问应用商店时需要密码 |否|是|是|

## <a name="device-capabilities-settings"></a>设备功能设置

|**设置名称**|**iOS** |**Android**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|阻止与可移动存储的连接 |是|是|否|
|阻止蓝牙连接 |是|是|否|

## <a name="additional-settings"></a>其他设置

您可以使用安全与合规中心 PowerShell cmdlet &其他策略设置。 有关详细信息，请参阅安全与 [&中心 PowerShell](/powershell/exchange/scc-powershell)。

|**设置名称**|**iOS** |**Android**|
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

## <a name="settings-supported-by-windows"></a>设置支持Windows

可以通过将 Windows 10注册为移动设备来管理这些设备。 部署适用的策略后，具有 Windows 10 设备的用户在首次使用内置电子邮件应用访问其 Microsoft 365 电子邮件 (时，需要注册基本移动性和安全性Azure AD高级订阅) 。

注册为移动设备Windows 10设备支持以下设置。 此设置不会阻止用户访问Microsoft 365资源。

### <a name="security-settings"></a>安全设置

- 需要字母数字密码

- 最短密码长度

- 擦除设备之前登录失败次数

- 设备锁定前不活动分钟数

- 密码过期(天数)

- 记住密码历史记录并禁止重复使用

> [!NOTE]
> 以下设置管理密码仅控制本地Windows帐户。 Windows域或用户提供的Azure Active Directory帐户不受这些设置的影响。

### <a name="system-settings"></a>系统设置

阻止从设备发送诊断数据。

### <a name="additional-settings"></a>其他设置

可以使用 PowerShell cmdlet 设置这些额外的策略设置：

- AllowConvenienceLogon

- UserAccountControlStatus

- FirewallStatus

- AutoUpdateStatus

- AntiVirusStatus

- AntiVirusSignatureStatus

- SmartScreenEnabled

- WorkFoldersSyncUrl

## <a name="remotely-wipe-a-mobile-device"></a>远程擦除移动设备

**如果** > 设备丢失或被盗，可以通过从安全与合规中心 > 数据丢失防护设备管理执行擦除来删除敏感的组织数据，并帮助阻止访问 Microsoft 365 & 组织资源。 你可以执行选择性擦除以仅删除组织数据，也可以执行完全擦除，以从设备中删除所有信息，并还原到其出厂设置。

有关详细信息，请参阅基本移动性和安全性 [中的移动设备](wipe-mobile-device.md)。

## <a name="related-content"></a>相关内容

[Microsoft 365 (Overview of Basic Mobility and Security for) ](overview.md)\
[在基本移动性和安全性策略](create-device-security-policies.md) 文章中 (创建设备) 
