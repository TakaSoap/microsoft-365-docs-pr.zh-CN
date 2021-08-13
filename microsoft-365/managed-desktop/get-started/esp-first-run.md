---
title: 使用 Autopilot 和注册状态页的首次运行体验
description: 如何部署 ESP 体验、使用的设置和配置更改
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: c9cbcd9ef9e4557e30409cd471d80cbcca5a2947438ef988c7892c18eddd8a2d
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53890969"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>使用 Autopilot 和注册状态页的首次运行体验

Microsoft 托管桌面使用[Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot)和 Microsoft Intune 的注册状态[页面 (ESP) ](/windows/deployment/windows-autopilot/enrollment-status)为用户提供可能的最佳首次运行体验。

## <a name="initial-deployment"></a>初始部署

若要提供 ESP 体验，你必须在 Microsoft 托管桌面 服务中注册设备。 有关注册的信息，请参阅自己 [注册新设备](../get-started/register-devices-self.md) 或合作伙伴 [注册设备的步骤](../get-started/register-devices-partner.md)。
默认情况下，"注册状态"页和预预配部署的 Autopilot 在 Microsoft 托管桌面。

## <a name="autopilot-profile-settings"></a>Autopilot 配置文件设置

Microsoft 托管桌面在用于用户设备的 Autopilot 配置文件中使用这些设置：

<br>

****

|设置|值|
|---|---|
|部署模式|用户驱动|
|作为 加入 Azure AD|已加入 Azure AD|
|语言 (区域) |用户选择|
|自动配置键盘|否|
|Microsoft 软件许可条款|隐藏|
|隐私设置|隐藏|
|隐藏更改帐户选项|Show|
|用户帐户类型|标准|
|允许白手套 OOBE|是|
|应用设备名称模板|是|
|输入名称|MMD-%RAND：11%|
|

## <a name="enrollment-status-page-settings"></a>注册状态页面设置

Microsoft 托管桌面注册状态页面体验使用这些设置：

<br>

****

|设置|值|
|---|---|
|显示应用和配置文件配置进度|是|
|当安装时间超过指定分钟数时显示错误|60|
|在出现时间限制错误时显示自定义消息|否|
|允许用户收集有关安装错误的日志|是|
|仅在 OOBE 设备上通过开箱使用体验预配 (页面) |是|
|在安装所有应用和配置文件之前阻止设备使用|是|
|允许用户在出现安装错误时重置设备|是|
|发生安装错误时允许用户使用设备|是|
|阻止设备使用，直到安装这些必需的应用（如果它们已分配给用户/设备）|现代工作场所 - 时间更正|现代工作区 - 客户端库|
|

注册状态页面体验分三个阶段进行。 有关详细信息，请参阅注册 [状态页面跟踪信息](/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)。

体验将按如下方式进行：

1. Autopilot 体验将启动，并且用户输入其凭据。
2. 设备打开注册状态页，然后继续执行设备准备和设备设置阶段。 帐户设置 (第) 步骤当前在 Microsoft 托管桌面 配置中已跳过，因为用户 ESP 已禁用。 设备重新启动。
3. 重新启动后，设备将打开Windows其他用户登录 **页面**。
4. 用户再次输入其凭据，桌面将打开。

> [!NOTE]
> Win32 应用仅在版本为 1903 或更高版本Windows 10 ESP 期间部署。

![Autopilot 设置的起始页显示"设备准备"和"设备设置"阶段。](../../media/mmd-autopilot-screenshot.png)


## <a name="additional-prerequisites-for-autopilot-for-pre-provisioned-deployment"></a>用于预预配部署的 Autopilot 的其他先决条件

- 设备必须具有有线网络连接。
- 如果你有在 2020 年 8 月之前使用 Microsoft 托管桌面 门户注册的设备，请取消注册并再次注册它们。
- 设备必须具有包含 2020 年 11 月累积更新[19H1/19H2 2020.11C](https://support.microsoft.com/topic/november-19-2020-kb4586819-os-builds-18362-1237-and-18363-1237-preview-25cbb849-74af-b8b8-29b8-68aa925e8cc3)或[20H1 2020.11C](https://support.microsoft.com/topic/november-30-2020-kb4586853-os-builds-19041-662-and-19042-662-preview-8fb07fb8-a7dd-ea62-d65e-3305da09f92e)的出厂映像（如果已安装）或必须用最新的 Microsoft 托管桌面 映像进行重新映像。
- 物理设备必须支持 TPM 2.0 和设备证明。 不支持虚拟机。 预配过程使用 autopilot Windows部署功能，因此需要 TPM 2.0。 TPM 证明过程还要求访问每个 TPM 提供程序唯一的一组 HTTPS URL。 有关详细信息，请参阅 Autopilot 自部署模式条目和 Autopilot 网络要求中的 Autopilot Windows[预配部署](/mem/autopilot/networking-requirements#tpm)。

## <a name="sequence-of-events-in-autopilot-for-pre-provisioned-deployment"></a>用于预预配部署的 Autopilot 中的事件序列

1. IT 管理员根据需要重置设备映像或重置设备。
2. IT 管理员启动设备，达到开箱即用体验，然后按 Windows键五次。
3. IT 管理员选择Windows Autopilot 预配"，然后选择"继续 **"。** 在Windows Autopilot 配置屏幕上，将显示有关设备的信息。
4. IT 管理员选择 **预配** 以开始预配过程。
5. 设备启动 ESP 并完成设备准备和设置阶段。 在设备设置阶段，你将看到显示 x 的应用安装 **x， (** ESP 配置文件设置的准确) 。
6. 帐户设置步骤当前已跳过Microsoft 托管桌面配置中，因为我们禁用了用户 ESP。
7. 设备重新启动。

重新启动后，设备将显示绿色状态屏幕，并添加 **"重新封装"** 按钮。

> [!IMPORTANT]
> 已知问题：
>
> - ESP 在 Autopilot 用于预预配的部署封装函数之后不会再次运行。
> - 对于预先预配的部署，Autopilot 不会重命名设备。 设备只有在经过 ESP 用户流后才能重命名。

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>更改为 Autopilot 和注册状态页面设置

如果你使用的安装程序Microsoft 托管桌面你的需求完全匹配，可以通过管理门户提交支持[票证](https://portal.azure.com/)。 下面是您可能需要的配置类型的一些示例：

### <a name="autopilot-settings-change"></a>Autopilot 设置更改

你可能想要请求其他设备名称模板。 但是，你无法更改部署模式、加入 Azure AD As、隐私设置或用户帐户类型。

### <a name="enrollment-status-page-settings-change"></a>注册状态页面设置更改

- "安装所花的时间超过指定分钟数时显示错误"设置的分钟数较长。
- 显示的错误消息。
- 在"阻止设备使用，直到安装这些必需的应用（如果它们已分配给用户/设备）"设置中添加或删除应用程序。

## <a name="required-applications"></a>必需的应用程序

- 你必须面向新式工作区设备组 Test、First、Fast 和 Broad 中的应用程序。 应用程序必须安装在"系统"上下文中。 在将 ESP 分配给所有组之前，请确保使用测试组中 ESP 完成测试。
- 任何应用程序都不应要求重新启动设备。 建议在生成应用程序包时将应用程序设置为"不执行任何操作"（如果需要重新启动）。
- 将所需应用程序限制为仅在用户登录到设备时立即需要的核心应用程序。
- 将所有应用程序的总大小统一保持在 1 GB 以下，以避免在应用程序安装阶段超时。
- 理想情况下，应用不应有任何依赖关系。 如果你有 *必须具有依赖项* 的应用，请确保在 ESP 评估中配置、测试和验证它们。
- Microsoft Teams包含在 ESP 中。
