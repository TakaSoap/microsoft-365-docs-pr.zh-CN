---
title: Microsoft 365 企业应用版
description: 如何部署 Microsoft 365 应用程序、如何更新和管理设置
keywords: 修订记录
ms.prod: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: b3843da0d35d78486ed22af6d057930ee4ad5bc9
ms.sourcegitcommit: 89b2ad0793c68415f178b8792a9757b9448345a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2020
ms.locfileid: "47295255"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 企业应用版

## <a name="initial-deployment"></a>初始部署

Microsoft 托管桌面可确保将 Microsoft 365 应用程序的企业 (64 位) 作为映像的一部分安装在所有 [程序设备](../service-description/device-list.md)上。 在设备提供时，设备上应存在以下所有应用程序：

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Access
- Skype for Business
- OneNote

这种方法可最大限度地降低网络影响，并确保用户在收到其设备后能够正常工作。 然后，将其他策略部署到托管设备，以设置要使用的应用程序。

> [!NOTE]
> Microsoft 团队是独立于企业的 Microsoft 365 应用程序部署的，并且不包含在基本映像中。 

### <a name="available-deployment-to-users"></a>向用户提供的部署

如果用户在其设备上没有 Microsoft 365 应用出于任何原因，则可以使用程序包将设备返回到其预期状态。 将用户添加到 **新式工作区-Office Office365_Install** 组，这些应用程序将在公司门户中提供给他们。

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>适用于企业版的 Microsoft 365 应用 (32 位) 

Microsoft 托管桌面不支持部署适用于企业的 M365 应用程序的32位版本。

## <a name="updates-to-microsoft-365-apps"></a>Microsoft 365 应用程序的更新

Microsoft 365 应用程序设置为 [每月企业频道](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)更新。 这种做法每个月为用户提供了新的 Office 功能，但每月仅以可预测的发布计划收到一次更新。 更新是在每月的第二个星期二发布的;这些更新可以包括功能、安全性和质量更新。 这些更新会自动进行，并将直接从 Office CDN 为该特定通道提取。

Microsoft 托管桌面 staggers 每个版本，以确定您的环境中的任何潜在问题。 我们在发布后28天完成 Microsoft 365 应用产品组中的首次推出。 Microsoft 托管桌面计划将更新发布到不同的组，以允许验证和测试的时间如下： 

- 测试：0天
- 第一个：0天
- Fast：7天
- 宽：21天

Microsoft 托管桌面为设备设置为期七天的 [更新期限](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) 。 更新可用后，必须在七天内安装。 [通知](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)用户多个位置需要进行更新：应用程序，在最后期限之前的系统托盘12小时内，他们会在最后期限前收到15分钟警告。 必须关闭所有 Microsoft 365 应用才能完成更新。

### <a name="pausing-or-rolling-back-an-update"></a>暂停或回退更新

如果出于任何原因需要暂停或回滚 Microsoft 365 应用程序更新，请通过 Microsoft 托管桌面门户文件获取 [管理员支持请求](../working-with-managed-desktop/admin-support.md) 。

在发布过程中，Microsoft 托管桌面会监视所有 Microsoft 365 应用的错误率。 如果我们注意到新版本与其早期版本之间的质量有显著差异，我们可能会通过 Microsoft 托管桌面管理门户与您联系。 根据严重性，我们将询问您是要暂停发布还是要通知您我们已采取措施来缓解问题。 

### <a name="delivery-optimization"></a>传递优化

传递优化是 Windows 10 中提供的对等分发技术。 它允许设备共享设备已从 Microsoft 下载的来自 internet 的内容（如更新）。 这有助于减少网络带宽，因为设备可以从其本地网络上的其他设备中获取更新的某些部分，而无需完全从 Microsoft 下载更新。

默认情况下，在运行 Windows 10 企业版或 Windows 10 教育版的设备上启用[传递优化](https://docs.microsoft.com/deployoffice/delivery-optimization)。 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Microsoft 托管桌面管理的设置

Microsoft 将某些设置作为服务的一部分进行管理。 Microsoft 托管桌面不会管理 Office 安全基准，但可以按照 " [管理设置](#settings-you-manage) " 部分中的指导进行设置。

### <a name="update-settings"></a>更新设置

Microsoft 托管桌面维护托管设备的所有 [更新设置](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) ，您应修改这些设置。

### <a name="set-updates-to-occur-automatically"></a>设置自动进行的更新

**默认值**： Enabled

配置此策略是为了确保所有 Office 设备都可以从云保持最新。 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>设置必须应用更新的截止时间

**默认值**：7天

**UpdateDeadline**策略用于配置用户在设备上实施更新前的宽限期。 此截止时间策略还会触发 [通知](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 给用户，以通知其设备上所需的更改。  

### <a name="defer-updates-on-a-device-for-a-period"></a>推迟一段时间内设备上的更新

对于每个更新管理设备组，此策略的配置方式各不相同，Microsoft 托管桌面需要此策略来满足更新目标：  

- 测试：0天
- 第一个：0天
- 7天
- 宽：21天

### <a name="update-notifications-settings"></a>更新通知设置

**默认值**： False

Microsoft 托管桌面设备上的 "隐藏更新通知" 设置为 **False** ，以便在需要更新时向用户提供 [最佳的更新](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) 体验。

### <a name="specify-a-location-to-look-for-updates"></a>指定用于查找更新的位置

**默认值**：每月企业频道

**UpdatePath**和**UpdateChannel**策略的组合将根据需要使用，以实现更新计划。 设置这些策略可确保所有 Office 设备都直接从 CDN 接收更新，以用于每月企业频道。

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>指定 Microsoft 365 应用的目标版本

Microsoft 托管桌面有时使用目标版本策略，以便回滚或固定特定版本的 Office。 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>隐藏用于启用或禁用 Office 自动更新的选项

**默认值**： Enabled

Microsoft 托管桌面需要此设置以满足 Microsoft 365 应用程序的更新目标。 

### <a name="first-run-settings"></a>首次运行设置 

有几种设置会影响首次运行 Office 时的行为。

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>代表最终用户接受许可条款

**默认值**： Disabled

当用户首次打开 Microsoft 365 应用时，系统会提示他们接受许可条款。 如果要代表用户接受许可条款，请向 Microsoft 托管桌面操作团队咨询服务请求，以确保启用此设置。 

### <a name="suppress-outlook-mobile-check-box"></a>"取消 Outlook mobile" 复选框

**默认值**： Disabled

用户首次打开 Outlook 时，系统会提示安装 Outlook Mobile。 如果您不希望您的用户看到该复选框，请向 Microsoft 托管桌面操作团队提供服务请求，要求为您的设备启用此设置。 

## <a name="other-settings"></a>其他设置

Microsoft 托管桌面可以选择代表你配置其他 Microsoft 365 应用设置。 

### <a name="disable-personal-onedrive"></a>禁用个人 OneDrive

**默认值**： Disabled

有些组织担心用户有权访问其设备上的企业和个人文件。 您可以通过 Microsoft 托管桌面操作团队为服务请求提供请求，以启用此设置。 

## <a name="settings-you-manage"></a>您管理的设置

还有许多其他策略，Microsoft 托管桌面尚未将其设置为我们的服务的一部分。 您可以使用 Microsoft Intune （它使用 [Office 云策略](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) 服务）对这些配置进行配置。 为此，请按照下列步骤操作：

1.  登录到 Microsoft 终结点管理器管理中心。
2.  选择 " **应用程序" > Office 应用程序 > 创建策略**
3.  在 " **创建策略** 配置" 页上，执行以下操作：
    - 输入名称。
    - 提供 (可选) 的说明。
    - 在 " **分配**" 中，选择此策略是应用于适用于企业的 Microsoft 365 应用程序的所有用户，还是仅适用于使用 web Office 匿名访问文档的用户。
    - 选择分配给策略配置的基于 AAD 的安全组。 每个策略配置仅可分配给一个组，并且每个组只能分配一个策略配置。
    - 将策略设置配置为包含在策略配置中。 您可以搜索策略设置名称以查找要配置的策略设置。 您还可以在应用程序上进行筛选，这取决于策略是否为建议的安全基准，以及策略是否已配置。 "平台" 列指示是否将策略应用于适用于 Windows 的 Microsoft 365 应用程序、Office for web 或全部。
4.  做出选择后，选择 " **创建**"。

> [!NOTE]
> Office 配置策略仅支持基于用户的部署
