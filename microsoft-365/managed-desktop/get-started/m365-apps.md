---
title: Microsoft 365 Apps for enterprise
description: 如何部署Microsoft 365 应用版、如何更新它们以及如何管理设置
keywords: 修订记录
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: f6df4ed3568be232927b7c427341d16eb869b7ed
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199821"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 企业应用版

## <a name="initial-deployment"></a>初始部署

Microsoft 托管桌面可确保Microsoft 365 企业应用版 (64) 作为映像的一部分安装在所有[程序设备上](../service-description/device-list.md)。 以下所有应用程序应在交付时存在于设备上：

- Word
- Excel
- PowerPoint
- Outlook
- 发布者
- Access
- Skype for Business
- OneNote

此方法最大限度地减少了网络影响，并确保用户一收到其设备就可以提高工作效率。 然后，我们将向托管设备部署更多策略，以设置供使用的应用程序。

> [!NOTE]
> Microsoft Teams独立于Microsoft 365 企业应用版部署，并且不包含在基本映像中。 

### <a name="available-deployment-to-users"></a>可供用户使用的部署

如果用户由于任何原因Microsoft 365 应用版未连接到设备，可以使用程序包将设备返回到其预期状态。 将用户添加到新式 **工作区Office-Office365_Install** 组，应用将在 公司门户 中变为公司门户。

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365 企业应用版 (32 位) 

Microsoft 托管桌面不支持部署 32 位版本的 M365 企业应用版。

## <a name="updates-to-microsoft-365-apps"></a>更新Microsoft 365 应用版

Microsoft 365 应用版设置为在每月频道上[Enterprise更新](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)。 此做法每月为用户提供新的Office功能，但他们将按可预测的发布计划每月仅接收一次更新。 更新在当月的第二个星期二发布;这些更新可以包括功能、安全性和质量更新。 这些更新会自动发生，并直接从特定频道Office CDN提取。

Microsoft 托管桌面每个版本错开，以确定环境中的任何潜在问题。 我们在从应用产品组发布后 28 Microsoft 365推出。 Microsoft 托管桌面计划向不同组发布更新，以留出验证和测试时间，如下所示： 

- 测试：零天
- 第一个：零天
- 快速：3 天
- 广泛：7 天

Microsoft 托管桌面设置设备的[七天更新](/deployoffice/configure-update-settings-microsoft-365-apps)截止时间。 更新可用后，必须在七天内安装更新。 系统会通知 [用户在](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 几个位置需要更新：应用程序在截止时间前 12 小时在系统托盘中，在截止时间前 15 分钟收到警告。 必须Microsoft 365 应用版所有项目才能完成更新。

### <a name="pausing-or-rolling-back-an-update"></a>暂停或回滚更新

如果你需要出于任何原因暂停或回滚Microsoft 365更新，请通过管理门户提交管理员Microsoft 托管桌面请求。 [](../working-with-managed-desktop/admin-support.md)

在发布期间，Microsoft 托管桌面监视所有Microsoft 365 应用版。 如果我们注意到新版本及其前置版本之间的质量显著差异，我们可能会通过管理门户Microsoft 托管桌面联系。 根据严重性，我们将询问您是否要暂停发布，或告知您我们已采取措施来缓解问题。 

### <a name="delivery-optimization"></a>传递优化

传递优化是一种可用于企业或企业Windows 10。 它允许设备共享设备通过 Internet 从 Microsoft 下载的内容（如更新）。 使用它有助于减少网络带宽，因为设备可以从本地网络的另一台设备获取部分更新，而无需从 Microsoft 完全下载更新。

[默认情况下，](/deployoffice/delivery-optimization)在运行 Windows 10 企业版 或 Windows 10 教育版 版本上启用传递优化。 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>设置由 Microsoft 托管桌面

Microsoft 将某些设置作为服务的一部分管理。 Microsoft 托管桌面不会管理Office安全基线，但你可以按照你管理的安全性部分中的设置[设置一个](#settings-you-manage)基线。

### <a name="update-settings"></a>更新设置

Microsoft 托管桌面维护[托管设备的所有](/deployoffice/configure-update-settings-microsoft-365-apps)更新设置，并且应修改这些设置。

### <a name="set-updates-to-occur-automatically"></a>设置自动进行的更新

**默认值：** 已启用

配置此策略是为了确保所有Office设备在云中保持最新状态。 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>设置必须应用更新的截止时间

**默认值：7** 天

**UpdateDeadline** 策略用于配置用户在设备上强制执行更新之前具有的宽限期。 此截止时间策略还会 [向用户](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 触发通知，以通知用户其设备上所需的更改。  

### <a name="defer-updates-on-a-device-for-a-period"></a>将设备的更新延迟一段时间

此策略针对每个更新管理设备组进行不同的配置，并且要求Microsoft 托管桌面满足其更新目标：  

- 测试：零天
- 第一个：零天
- 快速 7 天
- 广泛：21 天

### <a name="update-notifications-settings"></a>更新通知设置

**默认值：False**

在设备上，"隐藏更新通知"Microsoft 托管桌面设置为 **False，** 以在需要更新时通知用户，以提供最佳更新体验。 [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)

### <a name="specify-a-location-to-look-for-updates"></a>指定用于查找更新的位置

**默认值：** 每月频道Enterprise频道

根据需要使用 **UpdatePath** 和 **UpdateChannel** 策略的组合来实现更新计划。 这些策略设置为确保所有设备Office接收来自每月频道频道CDN更新Enterprise更新。

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>指定目标版本Microsoft 365 应用版

目标版本策略有时由 Microsoft 托管桌面 用于回滚或固定特定版本的Office。 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>隐藏启用或禁用自动更新Office选项

**默认值：** 已启用

若要使用户满足Microsoft 托管桌面应用程序的更新目标，Microsoft 365此设置。 

### <a name="first-run-settings"></a>首次运行设置 

首次运行时，有几个设置Office行为。

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>代表最终用户接受许可条款

**默认值：** 已禁用

用户第一次打开 Microsoft 365 应用时，系统会提示他们接受许可条款。 如果要代表用户接受许可条款，请向 Microsoft 托管桌面 Operations 团队提出服务请求，要求启用此设置。 

### <a name="suppress-outlook-mobile-check-box"></a>禁止Outlook移动复选框

**默认值：** 已禁用

用户首次打开时Outlook系统会提示他们安装Outlook移动版。 如果你不希望用户看到该复选框，请向 Microsoft 托管桌面 Operations 团队提出服务请求，要求为设备启用此设置。 

## <a name="other-settings"></a>其他设置

还有其他Microsoft 365应用设置Microsoft 托管桌面可以代表你进行配置。 

### <a name="disable-personal-onedrive"></a>禁用个人OneDrive

**默认值：** 已禁用

一些组织关注用户可以访问其设备上公司和个人文件。 您可以向要求启用此设置的 Microsoft 托管桌面 Operations 团队提出服务请求。 

## <a name="settings-you-manage"></a>设置管理

有许多其他策略Microsoft 托管桌面尚未设置为服务的一部分。 可以使用使用云策略服务Microsoft Intune配置[Office策略。](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) 若要设置这些策略，请按照以下步骤操作：

1. 登录到管理Microsoft Endpoint Manager中心。
2. 为 **要>的应用选择Office策略>应用**
3. 在" **创建策略** 配置"页上，执行以下操作：
    - 输入名称。
    - 提供可选 (说明) 。
    - 在 **分配** 中，选择此策略是应用于 Microsoft 365 企业应用版 所有用户，还是仅应用于使用 Office 网页版 匿名访问文档的用户。
    - 选择分配给策略配置的基于 AAD 的安全组。 每个策略配置只能分配给一个组，并且只能为每个组分配一个策略配置。
    - 配置要包含在策略配置中的策略设置。 可以搜索策略设置名称以查找要配置的策略设置。 还可以筛选应用程序、策略是否是建议的安全基线以及策略是否已配置。 平台列指示策略是应用于Microsoft 365 企业应用版设备Windows还是Office 网页版应用。
4. 做出选择后，选择"创建 **"。**

> [!NOTE]
> Office配置策略仅支持基于用户的部署
