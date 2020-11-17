---
title: 使用 Autopilot 和注册状态页的首次运行体验
description: 如何部署 ESP 体验、使用的设置以及配置更改
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5e2340c7c0bf00165bb43740d3d095b5b0402fc0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126621"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>使用 Autopilot 和注册状态页的首次运行体验

Microsoft 托管桌面使用 [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) 和 Microsoft Intune 的 [注册状态页 (ESP) ](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) 为您的用户提供最佳的首次运行体验。

注册状态页面当前处于公共预览版中。

## <a name="initial-deployment"></a>初始部署

若要提供 ESP 体验，必须在 Microsoft 托管桌面服务中注册设备。 有关注册的详细信息，请参阅 [自行注册新设备](../get-started/register-devices-self.md) 或 [合作伙伴的步骤以注册设备](../get-started/register-devices-partner.md)。

在将设备注册到服务后，可以通过 [管理门户](https://portal.azure.com/)存档支持票证，从而为 Microsoft 托管桌面设备启用 ESP。 在您对票证进行文件存档时，我们将最初将 ESP 配置部署到测试组。 它将部署到其他后续部署组中，每24个小时 (第一个、更快、更广泛的) 。 若要暂停部署，请文件另一个票证请求操作保留。

## <a name="autopilot-profile-settings"></a>Autopilot 配置文件设置

Microsoft 托管桌面在用于您的用户设备的 Autopilot 配置文件中使用这些设置：


|Setting  |值  |
|---------|---------|
|部署模式 |  用户驱动       |
|加入 Azure AD as     |  Azure AD 已加入       |
|语言 (区域)      | 操作系统默认值        |
|自动配置键盘     | 否        |
|Microsoft 软件许可条款     |  隐藏       |
|隐私设置     | 隐藏        |
|隐藏更改帐户选项     | Show        |
|用户帐户类型     |  标准       |
|允许将白色 Glove OOBE     |  是       |
|应用设备名称模板     | 是        |
|输入名称     | MMD-% RAND：11%        |

> [!NOTE]
> 仅对启用了 ESP 的客户启用 "白色 glove" 设置，Microsoft 托管桌面目前不支持此功能。

## <a name="enrollment-status-page-settings"></a>注册状态页面设置

Microsoft 托管桌面在注册状态页面体验中使用以下设置：


|Setting  |值  |
|---------|---------|
|显示应用和配置文件配置进度     | 是        |
|当安装时间超过指定的分钟数时显示一个错误     |  60       |
|出现时间限制错误时显示自定义消息     |  是       |
|错误消息     | 是的，设置你的设备所花时间比预期时间稍长。 单击下方以开始操作，我们将在后台完成设置        |
|允许用户收集有关安装错误的日志     |  是       |
|仅向设备显示由 (OOBE 的现成体验设置的页面)      | 是        |
|在安装所有应用和配置文件之前阻止设备使用     |  是       |
|如果出现安装错误，则允许用户重置设备     |  是       |
|允许用户在发生安装错误时使用设备     |  是       |
|如果这些必需的应用程序已分配给用户/设备，则阻止设备使用     |  新式工作区-时间更正       |



注册状态页面体验分三个阶段发生。 有关详细信息，请参阅 [注册状态页面跟踪信息](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)。

经验如下所示：

1. Autopilot 体验启动，用户输入他们的凭据。
2. 设备将打开 "注册状态" 页，并继续完成 "设备准备" 和 "设备设置" 阶段。 由于禁用了用户 ESP，因此第三步 (帐户安装) 当前在 Microsoft 托管桌面配置中被 *跳过* 。 设备将重新启动。
3. 重新启动后，设备将使用 **其他用户** 打开 Windows 登录页。
4. 用户再次输入其凭据，并打开桌面。

> [!NOTE]
> 如果 Windows 10 版本是1903或更高版本，则仅在 ESP 期间部署 Win32 应用程序。

![Autopilot 安装程序的起始页，显示 "设备准备" 和 "设备安装" 阶段。](../../media/mmd-autopilot-screenshot.png)

## <a name="white-glove-provisioning"></a>白色 glove 设置

Microsoft 托管桌面目前不支持 Windows Autopilot 的 "白色 glove" 功能。

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>更改为 Autopilot 和注册状态页面设置

如果 Microsoft 托管桌面使用的安装程序不能完全满足您的需求，则可以通过 [管理门户](https://portal.azure.com/)为其提供支持票证。 下面是可能需要的配置类型的一些示例：

### <a name="autopilot-settings-change"></a>Autopilot 设置更改

您可能需要请求一个不同的设备名称模板。 但是，您不能更改部署模式、将 Azure AD 加入 "隐私设置" 或 "用户帐户类型"。

### <a name="enrollment-status-page-settings-change"></a>注册状态页面设置更改

- "当安装时间超过指定的分钟数时显示错误" 设置的较长分钟数。
- 显示的错误消息
- 在 "阻止设备使用" 中添加或删除应用程序，直到这些必需的应用程序已被分配给用户/设备 "设置。

## <a name="required-applications"></a>必需的应用程序

- 您必须将应用程序定位在新式的工作区 *设备组* 测试、第一次、快速和广泛的应用中。 应用程序必须安装在 "系统" 上下文中。 在将测试组中的 ESP 分配给所有组之前，请务必先完成对该测试组中的 ESP 的测试。
- 任何应用程序都不需要重新启动设备。 建议在生成应用程序包时，将应用程序设置为 "无任何操作"，如果它们需要重新启动。
- 仅在用户登录设备时所需的核心应用程序中限制所需的应用程序。
- 将所有应用程序的总大小保持在 1 GB 之下，以避免在应用程序安装阶段超时。
- 理想情况下，应用程序不应具有任何依赖项。 如果您有 *必须* 具有依赖项的应用程序，请务必在 ESP 评估中对其进行配置、测试和验证。
- 没有需要 "用户" 上下文的应用程序 (例如，团队) 可以包含在 ESP 的公共预览版中。
