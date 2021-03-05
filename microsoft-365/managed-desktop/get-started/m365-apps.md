---
title: Microsoft 365 Apps for enterprise
description: 如何部署 Microsoft 365 应用版、如何更新它们以及如何管理设置
keywords: 修订记录
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 26e62d6e59f1f90e35d9e18e6eed917a66876645
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453917"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 企业应用版

## <a name="initial-deployment"></a>初始部署

Microsoft 托管桌面可确保 Microsoft 365 企业应用 (64 位) 在所有程序设备上作为映像的一 [部分进行安装](../service-description/device-list.md)。 以下所有应用程序在交付时都应存在于设备上：

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Access
- Skype for Business
- OneNote

此方法最大程度地减小了网络影响，并确保用户在收到设备后可提高工作效率。 然后，我们将更多策略部署到托管设备，以设置应用程序以使用。

> [!NOTE]
> Microsoft Teams 独立于 Microsoft 365 企业应用版部署，不包含在基本映像中。 

### <a name="available-deployment-to-users"></a>可供用户使用的部署

如果用户出于任何原因在其设备上没有 Microsoft 365 应用版，可以使用程序包将设备返回到其预期状态。 将用户添加到 **新式工作区-Office-Office365_Install** 组，应用将在公司门户中提供给他们。

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365 企业应用版 (32 位) 

Microsoft 托管桌面不支持部署 32 位版本的 M365 企业应用版。

## <a name="updates-to-microsoft-365-apps"></a>Microsoft 365 应用版更新

Microsoft 365 应用版已设置为在每月企业频道 [上更新](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)。 此做法每月为用户提供新的 Office 功能，但他们将按可预测的发布计划每月仅接收一次更新。 更新在当月的第二个星期二发布;这些更新可能包括功能、安全性和质量更新。 这些更新会自动发生，并直接从该特定频道的 Office CDN 提取。

Microsoft 托管桌面会错开每个版本，以确定环境中的任何潜在问题。 我们在 Microsoft 365 应用产品组发布后的 28 天内完成推出。 Microsoft 托管桌面计划将更新版本更新到不同的组，以留出验证和测试时间，如下所示： 

- 测试：零天
- First： Zero days
- 快速：3 天
- 广泛：7 天

Microsoft 托管桌面为设备设置七 [天更新](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) 截止时间。 更新可用后，必须在七天内安装。 系统会通知 [用户](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 需要更新的几个位置：应用程序在截止时间前 12 小时位于系统托盘中，并且用户在截止时间前收到 15 分钟的警告。 必须关闭所有 Microsoft 365 应用，更新才能完成。

### <a name="pausing-or-rolling-back-an-update"></a>暂停或回滚更新

如果你需要出于任何原因暂停或回滚 Microsoft 365 应用更新，请通过[](../working-with-managed-desktop/admin-support.md)Microsoft 托管桌面门户提交管理员支持请求。

在发布期间，Microsoft 托管桌面将监视所有 Microsoft 365 应用版的错误率。 如果我们注意到新版本及其前置版本之间的质量显著差异，我们可能会通过 Microsoft 托管桌面管理门户联系你。 根据严重性，我们将询问您是否要暂停发布，或告知你我们已采取措施来缓解问题。 

### <a name="delivery-optimization"></a>传递优化

传递优化是 Windows 10 中提供的一种对等分发技术。 它允许设备共享设备通过 Internet 从 Microsoft 下载的内容（如更新）。 使用它可以帮助减少网络带宽，因为设备可以从本地网络上另一台设备获取部分更新，而不必从 Microsoft 完全下载更新。

[默认情况下，](https://docs.microsoft.com/deployoffice/delivery-optimization) 在运行 Windows 10 企业版或 Windows 10 教育版的设备上启用传递优化。 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>由 Microsoft 托管桌面管理的设置

Microsoft 将某些设置作为服务的一部分管理。 Microsoft 托管桌面不会管理 Office 安全基线，但您可以按照"管理设置"部分中的指导操作，自己 [设置一](#settings-you-manage) 个基线。

### <a name="update-settings"></a>更新设置

Microsoft 托管桌面 [维护托管设备](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) 的所有更新设置，您应修改这些设置。

### <a name="set-updates-to-occur-automatically"></a>设置自动进行的更新

**默认值：** 已启用

配置此策略是为了确保所有 Office 设备都可以从云中保持最新。 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>设置必须应用更新的截止时间

**默认值：7** 天

**UpdateDeadline** 策略用于配置用户在设备上强制执行更新之前具有的宽限期。 此截止时间策略还会 [向用户](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 触发通知，以通知用户其设备上所需的更改。  

### <a name="defer-updates-on-a-device-for-a-period"></a>将设备的更新延迟一段时间

此策略针对每个更新管理设备组进行不同的配置，并且 Microsoft 托管桌面必须满足其更新目标：  

- 测试：零天
- First： Zero days
- 快速 7 天
- 广泛：21 天

### <a name="update-notifications-settings"></a>更新通知设置

**默认值：False**

"隐藏更新通知"设置在 Microsoft 托管桌面设备上设置为 **False，** 以便通过通知用户（在需要更新时 [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)通知他们）提供最佳更新体验。

### <a name="specify-a-location-to-look-for-updates"></a>指定用于查找更新的位置

**默认值：** 每月企业频道

根据需要使用 **UpdatePath** 和 **UpdateChannel** 策略的组合来实现更新计划。 设置这些策略是为了确保所有 Office 设备都直接从 CDN 接收每月企业频道的更新。

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>指定 Microsoft 365 应用的目标版本

Microsoft 托管桌面有时使用目标版本策略来回滚或固定特定版本的 Office。 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>隐藏启用或禁用 Office 自动更新的选项

**默认值：** 已启用

若要实现 Microsoft 365 应用程序的更新目标，Microsoft 托管桌面需要此设置。 

### <a name="first-run-settings"></a>首次运行设置 

第一次运行 Office 时，有几个设置会影响行为。

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>代表最终用户接受许可条款

**默认值：** 已禁用

用户首次打开 Microsoft 365 应用时，系统会提示他们接受许可条款。 如果要代表用户接受许可条款，请向 Microsoft 托管桌面运营团队提出服务请求，要求启用此设置。 

### <a name="suppress-outlook-mobile-check-box"></a>禁止 Outlook 移动复选框

**默认值：** 已禁用

用户首次打开 Outlook 时，系统会提示他们安装 Outlook Mobile。 如果不希望用户看到该复选框，请向 Microsoft 托管桌面操作团队提出服务请求，要求为设备启用此设置。 

## <a name="other-settings"></a>其他设置

Microsoft 托管桌面还可以代表你配置其他 Microsoft 365 应用设置。 

### <a name="disable-personal-onedrive"></a>禁用个人 OneDrive

**默认值：** 已禁用

一些组织担心用户可以访问其设备上的公司和个人文件。 你可以向 Microsoft 托管桌面运营团队提出服务请求，要求启用此设置。 

## <a name="settings-you-manage"></a>你管理的设置

Microsoft 托管桌面尚未将许多其他策略设置为服务的一部分。 可以使用使用 Office 云策略服务的 Microsoft Intune 配置 [这些](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) 策略。 若要设置这些策略，请按照以下步骤操作：

1.  登录到 Microsoft Endpoint Manager 管理中心。
2.  Select **Apps > Policies for Office apps > Create**
3.  在 **"创建策略** 配置"页上，执行以下操作：
    - 输入名称。
    - 提供可选 (说明) 。
    - 在 **工作** 分配中，选择此策略是应用于 Microsoft 365 企业应用版所有用户，还是仅适用于使用 Office 网页版匿名访问文档的用户。
    - 选择分配给策略配置的基于 AAD 的安全组。 每个策略配置只能分配给一个组，并且只能为每个组分配一个策略配置。
    - 配置要包含在策略配置中的策略设置。 可以搜索策略设置名称以查找要配置的策略设置。 还可以筛选应用程序、策略是否是建议的安全基线以及策略是否已配置。 平台列指示策略是应用于适用于 Windows 设备的 Microsoft 365 企业应用版、Office 网页版还是全部应用。
4.  做出选择后，选择"创建 **"。**

> [!NOTE]
> Office 配置策略仅支持基于用户的部署
