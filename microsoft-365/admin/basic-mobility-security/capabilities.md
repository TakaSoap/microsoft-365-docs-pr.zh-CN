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
description: 基本移动性和安全性可以帮助你保护和管理移动设备。
ms.openlocfilehash: 78cfa4582aa2e25a3b47a12d2e067082e8b41d07
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64781218"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>基本移动性和安全性的功能

基本移动性和安全性可以帮助你保护和管理组织中许可的Microsoft 365用户使用的移动设备，如 iPhone、iPad、Androids 和Windows手机。 可以使用有助于控制对受支持的移动设备和应用的组织Microsoft 365电子邮件和文档的访问的设置创建移动设备管理策略。 如果设备丢失或被盗，可以远程擦除设备以删除敏感的组织信息。

## <a name="supported-operating-systems"></a>支持的操作系统 

按照Microsoft Intune操作系统指南，了解基本移动性和安全性为设备提供的最低支持操作系统。 有关详细信息，请参阅[Intune支持的操作系统](/mem/intune/fundamentals/supported-devices-browsers)。

可以使用基本移动性和安全性来保护和管理以下设备。

- iOS
- Android (包括 Samsung Knox) <sup>1</sup>
- Windows <sup>2、3</sup>

<sup>1</sup>2020 年 6 月之后，9 之后的 Android 版本无法管理密码设置（Samsung Knox 设备上除外）。

<sup>2</sup>Windows 8.1 RT 设备的访问控制仅限于Exchange ActiveSync。

<sup>3</sup>Windows 10的访问控制需要包含Azure AD Premium的订阅，并且需要将设备联接到Azure Active Directory。

> [!NOTE]
> 已注册早期 OS 版本的设备继续运行，但功能可能会在不通知的情况下更改。

如果组织中的人员使用基本移动性和安全性不支持的移动设备，你可能希望阻止Exchange ActiveSync应用访问这些设备Microsoft 365电子邮件，以帮助使组织的数据更安全。 有关阻止Exchange ActiveSync的步骤，请参阅[“基本移动性和安全性”中的“管理设备访问设置](manage-device-access-settings.md)”。

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Microsoft 365电子邮件和文档的访问控制

下表中不同类型的移动设备支持的应用提示用户注册基本移动性和安全性，其中有一个新的移动设备管理策略适用于用户的设备，并且用户以前尚未注册该设备。 如果用户的设备不符合策略，具体取决于设置策略的方式，可能会阻止用户访问这些应用中的Microsoft 365资源，或者他们可能有权访问，但Microsoft 365报告策略冲突。

|产品|iOS|Android|
|---|---|---|
|**Exchange** Exchange ActiveSync包括内置电子邮件和第三方应用（如 TouchDown）使用版本 14.1 或更高版本Exchange ActiveSync。|邮件|电子邮件|
|**Office** 和 **OneDrive for Business**|Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**在手机和平板电脑上**：<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **仅在电话上：** <br/> Office Mobile|

> [!NOTE]
>
> - 对 iOS 10.0 及更高版本的支持包括iPhone和iPad设备。
> - 基本安全和移动性不支持对 BlackBerry OS 设备进行管理。 使用 BlackBerry Business 云服务 (来自 BlackBerry 的 BBCS) 来管理 BlackBerry OS 设备。 运行 Android OS 的黑莓设备支持为标准 Android 设备
> - 如果用户使用移动浏览器访问Microsoft 365 SharePoint网站、Office Online 中的文档或Outlook Web App中的电子邮件，则不会提示用户注册，也不会因为违反策略而被阻止或报告。

下图显示了具有新设备的用户登录到支持使用基本移动性和安全性进行访问控制的应用时会发生什么情况。 阻止用户访问应用中的Microsoft 365资源，直到他们注册其设备。

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本的移动性和安全性访问控制。":::

> [!NOTE]
> 在基本移动性和安全性中为Microsoft 365 商业标准版创建的策略和访问规则将替代Exchange ActiveSync在Exchange管理中心创建的移动设备邮箱策略和设备访问规则。 将设备注册到基本移动性和安全性Microsoft 365 商业标准版后，将忽略应用于设备的任何Exchange ActiveSync移动设备邮箱策略或设备访问规则。 若要详细了解Exchange ActiveSync，请参阅[Exchange Online中的Exchange ActiveSync](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)。

## <a name="policy-settings-for-mobile-devices"></a>移动设备的策略设置

如果创建策略来阻止打开某些设置的访问，则在使用 Access 控件中列出的受支持应用Microsoft 365[电子邮件和文档](capabilities.md)时，将阻止用户访问Microsoft 365资源。

可阻止用户访问Microsoft 365资源的设置包括以下部分：

- 安全

- 加密

- 越狱

- 托管电子邮件配置文件

例如，下图显示了具有已注册设备的用户不符合应用到其设备的移动设备管理策略中的安全设置时会发生什么情况。 用户登录到支持使用基本移动性和安全性进行访问控制的应用。 在设备符合安全设置之前，阻止他们访问应用中的Microsoft 365资源。

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="基本移动性和安全性符合性消息。":::

以下部分列出了可用于保护和管理连接到Microsoft 365组织资源的移动设备的策略设置。

## <a name="security-settings"></a>安全设置

|设置名称|iOS|Android|Samsung Knox|
|---|---|---|---|
|要求使用密码|是|是|是|
|阻止简单密码|是|否|否|
|需要字母数字密码|是|否|否|
|最短密码长度|是|是|是|
|擦除设备之前的登录失败次数|是|是|是|
|设备锁定前处于非活动状态的分钟数|是|是|是|
|密码过期(天数)|是|是|是|
|记住密码历史记录并禁止重复使用|是|是|是|

## <a name="encryption-settings"></a>加密设置

|设置名称|iOS|Android|Samsung Knox|
|---|---|---|---|
|需要设备上的数据加密 <sup>1</sup>|否|是|是|

<sup>1</sup>使用 Samsung Knox，还可以要求对存储卡进行加密。

## <a name="jail-broken-setting"></a>越狱设置

|设置名称|iOS|Android|Samsung Knox|
|---|---|---|---|
|设备不能越狱或生根|是|是|是|

## <a name="managed-email-profile-option"></a>托管电子邮件配置文件选项

如果用户使用手动创建的电子邮件配置文件，则以下选项可以阻止用户访问其Microsoft 365电子邮件。 iOS 设备上的用户必须先删除手动创建的电子邮件配置文件，然后才能访问其电子邮件。 删除配置文件后，会在设备上自动创建新配置文件。 有关最终用户如何合规的说明，请参阅 [找到现有电子邮件帐户](/intune-user-help/existing-company-email-account-found)。

|设置名称|iOS|Android|Samsung Knox|
|---|---|---|---|
|管理电子邮件配置文件|是|否|否|

## <a name="cloud-settings"></a>云设置

|设置名称|iOS|Android|Samsung Knox|
|---|---|---|---|
|需要加密备份|是|否|否|
|阻止云备份|是|否|否|
|阻止文档同步|是|否|否|
|阻止照片同步|是|否|否|
|允许 Google 备份|不适用|否|是|
|允许 Google 帐户自动同步|不适用|否|是|

## <a name="system-settings"></a>系统设置

|设置名称|iOS|Android|Samsung Knox|
|---|---|---|---|
|阻止屏幕捕获|是|否|是|
|阻止从设备发送诊断数据|是|否|是|

## <a name="application-settings"></a>应用程序设置

|设置名称|iOS|Android|Samsung Knox|
|---|---|---|---|
|阻止设备上的视频会议|是|否|否|
|阻止对应用商店的访问|是|否|是|
|访问应用商店时需要密码|否|是|是|

## <a name="device-capabilities-settings"></a>设备功能设置

|设置名称|iOS|Android|Samsung Knox|
|---|---|---|---|
|阻止与可移动存储的连接|是|是|否|
|阻止蓝牙连接|是|是|否|

## <a name="additional-settings"></a>其他设置

可以使用安全&合规中心 PowerShell cmdlet 设置以下附加策略设置。 有关更多信息，参见 [安全与合规中心 PowerShell](/powershell/exchange/scc-powershell)。

|设置名称|iOS|Android|
|---|---|---|
|CameraEnabled|是|是|
|RegionRatings|是|否|
|MoviesRatings|是|否|
|TVShowsRating|是|否|
|AppsRatings|是|否|
|AllowVoiceDialing|是|否|
|AllowVoiceAssistant|是|否|
|AllowAssistantWhileLocked|是|否|
|AllowPassbookWhileLocked|是|否|
|MaxPasswordGracePeriod|是|否|
|PasswordQuality|否|是|
|SystemSecurityTLS|是|否|
|WLANEnabled|否|否|

## <a name="settings-supported-by-windows"></a>Windows支持的设置

可以通过将Windows 10设备注册为移动设备来管理它们。 部署适用的策略后，具有Windows 10设备的用户在首次使用内置电子邮件应用访问其Microsoft 365电子邮件 (时需要注册基本移动性和安全性，) 需要Azure AD高级订阅。

注册为移动设备的Windows 10设备支持以下设置。 这些设置不会阻止用户访问Microsoft 365资源。

### <a name="security-settings"></a>安全设置

- 需要字母数字密码

- 最短密码长度

- 擦除设备之前的登录失败次数

- 设备锁定前处于非活动状态的分钟数

- 密码过期(天数)

- 记住密码历史记录并禁止重复使用

> [!NOTE]
> 以下用于控制密码的设置仅控制本地Windows帐户。 通过加入域或Azure Active Directory提供的Windows帐户不受这些设置的影响。

### <a name="system-settings"></a>系统设置

阻止从设备发送诊断数据。

### <a name="additional-settings"></a>其他设置

可以使用 PowerShell cmdlet 设置这些附加策略设置：

- AllowConvenienceLogon

- UserAccountControlStatus

- FirewallStatus

- AutoUpdateStatus

- AntiVirusStatus

- AntiVirusSignatureStatus

- SmartScreenEnabled

- WorkFoldersSyncUrl

## <a name="remotely-wipe-a-mobile-device"></a>远程擦除移动设备

如果设备丢失或被盗，可以删除敏感的组织数据，并通过从安全&合规中心进行擦除>**数据丢失防护** > **Device 管理** 来帮助防止访问Microsoft 365组织资源。 你可以执行选择性擦除，仅删除组织数据或完全擦除，以从设备中删除所有信息并将其还原到其工厂设置。

有关详细信息，请参阅 [在基本移动性和安全性中擦除移动设备](wipe-mobile-device.md)。

## <a name="related-content"></a>相关内容

Microsoft 365 (文章) \ [的基本移动性和安全性概述](overview.md)
[在基本移动性和安全](create-device-security-policies.md) 性 (文章中创建设备安全策略) 
