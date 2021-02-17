---
title: 适用于管理员的 Office 365 应用程序防护
keywords: 应用程序防护， 保护， 隔离， 隔离容器， 硬件隔离
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 获取基于硬件的最新隔离。 防止当前和新出现的攻击（如攻击或恶意链接）干扰员工工作效率和企业安全。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 50065c4c0b9cbac9dee29892d9ebb0c7ce5f20f8
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261521"
---
# <a name="application-guard-for-office-for-admins"></a>适用于管理员的 Office 应用程序防护

**适用于：** Word、Excel 和 PowerPoint for Microsoft 365、Windows 10 企业版

适用于 Office (的 Microsoft Defender 应用程序防护) 有助于防止不受信任的文件访问受信任的资源，确保企业不受新的和新出现的攻击。 本文将指导管理员设置设备以预览 Office 应用程序防护。 它提供有关在设备上启用 Office 应用程序防护的系统要求和安装步骤的信息。

## <a name="prerequisites"></a>先决条件

### <a name="minimum-hardware-requirements"></a>最低硬件要求

* CPU：64 位、4 核 (物理或虚拟) 、虚拟化扩展 (Intel VT-x 或 AMD-V) 、Core i5 等效或更高推荐
* **物理内存**：8 GB RAM
* **硬盘：** 系统驱动器上 10 GB 的可用空间 (SSD) 

### <a name="minimum-software-requirements"></a>最低软件要求

* **Windows 10：Windows** 10 企业版、客户端内部版本 2004 (20H1) 版本 19041 或更高版本
* **Office**：Office Current Channel Build 版本 2011 16.0.13530.10000 或更高版本。 支持 32 位和 64 位版本的 Office。
* **更新程序包**：Windows 10 累积每月安全更新 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

有关详细的系统要求，请参阅 [Microsoft Defender 应用程序防护的系统要求](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)。 若要了解有关 Office 更新频道的更多信息，请参阅 [Microsoft 365 更新频道概述](https://docs.microsoft.com/deployoffice/overview-update-channels)。

### <a name="licensing-requirements"></a>许可要求

* Microsoft 365 E5 或 Microsoft 365 E5 安全

## <a name="deploy-application-guard-for-office"></a>部署 Office 应用程序防护

### <a name="enable-application-guard-for-office"></a>启用 Office 应用程序防护

1. 下载并安装 **Windows 10 累积每月安全更新 KB4571756**。

2. 在 **Windows 功能下选择 Microsoft Defender** 应用程序防护，然后选择"**确定"。** 启用应用程序防护功能将提示系统重新启动。 你可以选择立即或步骤 3 后重新启动。

   ![显示 AG 的 Windows 功能对话框](../../media/ag03-deploy.png)

   还可以以管理员角色运行以下 PowerShell 命令来启用该功能：

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. 在托管模式下搜索 **Microsoft Defender 应用程序防护**，计算机 **配置管理模板 Windows 组件 Microsoft Defender \\ \\ \\ 应用程序防护中的组策略**。 打开此策略，将"选项"下的值设置为 **2** 或 **3，** 然后选择"确定 **"或"****应用"。**

   ![在托管模式下打开 AG](../../media/ag04-deploy.png)

   相反，你可以设置相应的云解决方案提供商策略：

   > **OMA-URI：./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** <br> 数据类型 **：Integer** <br> 值 **：2**

4. 重新启动系统。

### <a name="set-diagnostics--feedback-to-send-full-data"></a>设置诊断&反馈以发送完整数据

此步骤可确保识别并修复问题所需的数据已到达 Microsoft。 请按照以下步骤在 Windows 设备上启用诊断：

1. 从 **"** 开始"菜单打开"设置"。

   ![“开始”菜单](../../media/ag05-diagnostic.png)

2. 在 **"Windows 设置"** 上，选择 **"隐私"。**

   ![Windows 设置菜单](../../media/ag06-diagnostic.png)

3. Under Privacy， select **Diagnostics & feedback** and select **Optional diagnostic data.**

   ![诊断和反馈菜单](../../media/ag07a-diagnostic.png)

有关配置 Windows 诊断设置的信息，请参阅在组织中配置 [Windows 诊断数据](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)。

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>确认 Office 应用程序防护已启用且正常工作

在确认启用了 Office 应用程序防护之前，在已部署策略的设备上启动 Word、Excel 或 PowerPoint。 确保 Office 已激活。 你可能需要先使用工作标识激活 Office 产品。

若要确认 Office 应用程序防护已启用，请启动 Word、Excel 或 PowerPoint，然后打开不受信任的文档。 例如，您可以打开从 Internet 下载的文档或组织外部人员的电子邮件附件。

首次打开不受信任的文件时，你可能会看到 Office 初始屏幕，如以下示例所示。 它可能在 Office 应用程序防护被激活且文件正在打开时显示一段时间。 随后打开不受信任的文件应更快。

![Office 应用初始屏幕](../../media/ag08-confirm.png)

打开后，文件应显示几个可视指示器，指示文件是在 Office 应用程序防护内打开的：

* 功能区中的标注

  ![显示小 App Guard 注释的文档文件](../../media/ag09-confirm.png)

* 任务栏中带防护的应用程序图标

  ![任务栏中的图标](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>为 Office 配置应用程序防护

Office 支持以下策略，使您能够配置 Office 应用程序防护的功能。 可以通过组策略或 Office 云策略服务配置这些策略。

> [!NOTE]
> 配置这些策略可以禁用在 Office 应用程序防护中打开的文件的一些功能。

|Policy|说明|
|---|---|
|请勿使用 Office 应用程序防护|启用此策略将强制 Word、Excel 和 PowerPoint 使用受保护的视图隔离容器，而不是 Office 应用程序防护。 当存在使 Office 应用程序防护为 Microsoft Edge 启用的问题时，可以使用此策略临时禁用它。|
|为 Office 容器预创建配置应用程序防护|此策略确定是否预先创建了用于隔离不受信任的文件的应用程序防护容器，以提高运行时性能。 如果启用此设置，您可以指定继续预创建容器的天数，或允许 Office 内置启发式预创建容器。
|不允许复制/粘贴在 Office 应用程序防护中打开的 Office 文档|启用此策略将阻止用户将内容从在 Office 应用程序防护中打开的文档复制并粘贴到它外部打开的文档。|
|在 Office 应用程序防护中禁用硬件加速|此策略控制 Office 应用程序防护是否使用硬件加速来呈现图形。 如果启用此设置，Office 应用程序防护将使用基于软件的 (CPU) 呈现，并且不会加载任何第三方图形驱动程序，也不会与任何连接的图形硬件交互。
|在 Office 应用程序防护中禁用不支持的文件类型保护|此策略控制 Office 应用程序防护是否阻止打开不支持的文件类型，或者是否启用重定向到受保护的视图。
|关闭在 Office 应用程序防护中打开的文档的相机和麦克风访问|启用此策略将删除 Office 对 Office 应用程序防护内的相机和麦克风的访问。|
|限制打印在 Office 应用程序防护中打开的文档|启用此策略将限制用户可从 Office 应用程序防护中打开的文件打印到的打印机。 例如，可以使用此策略将用户限制为仅打印为 PDF。|
|阻止用户删除文件上的 Office 保护应用程序防护|启用此策略将删除 Office (体验中的选项) 禁用 Office 保护的应用程序防护或打开 Office 应用程序防护之外的文件。 <p> **注意：** 用户仍可以通过从文件手动删除 Web 标记属性或将文档移动到受信任位置来绕过此策略。|
|

> [!NOTE]
> 以下策略将要求用户注销并再次登录到 Windows 以生效：
>
> * 在 Office 应用程序防护中打开的文档禁用复制/粘贴
> * 限制在 Office 应用程序防护中打开的文档的打印
> * 关闭对 Office 应用程序防护中打开的文档的相机和麦克风访问

## <a name="submit-feedback"></a>提交反馈

### <a name="submit-feedback-via-feedback-hub"></a>通过反馈中心提交反馈

如果在启动 Office 应用程序防护时遇到任何问题，建议通过反馈中心提交反馈：

1. 打开 **"反馈中心"应用** 并登录。

2. 如果在启动应用程序防护时看到错误对话框，请在错误对话框中选择"向 **Microsoft** 报告"以启动新的反馈提交。 否则，导航到为应用程序防护选择正确的类别，然后选择"在右上方附近 <https://aka.ms/mdagoffice-fb> 添加新反馈"。 **+ &nbsp;**

3. 如果尚未填写反馈 **框，请在** "汇总反馈"框中输入摘要。

4. 输入你遇到问题的详细说明，以及你在"详细说明"框中执行的步骤，然后选择"下一 **步"。**

5. 选择"问题"旁边的 **气泡**。 确保所选的类别是安全和隐私 **Microsoft \> Defender 应用程序防护 - Office，** 然后选择"下 **一步"。**

6. 选择 **"新建反馈"，** 然后选择"**下一步"。**

7. 收集有关问题的跟踪：

   1. 展开" **重新创建我的问题"** 磁贴。

   2. 如果在应用程序防护运行时遇到问题，请打开应用程序防护实例。 打开实例允许从应用程序防护容器内收集其他跟踪。

   3. 选择 **"开始** 录制"，然后等待磁贴停止旋转，说 *"停止录制"。*

   4. 使用应用程序防护完全重现问题。 复制可能包括尝试启动应用程序防护实例并等待它失败，或在正在运行的应用程序防护实例中重现问题。

   5. 选择 **"停止录制"** 磁贴。

   6. 使任何正在运行的应用程序防护 (保持) 打开状态，即使在提交后几分钟内，也可以收集容器诊断。

8. 附加与问题相关的任何相关屏幕截图或文件。

9. 选择“**提交**”。

### <a name="submit-feedback-via-office-customer-voice"></a>通过 Office 客户语音提交反馈

如果问题在应用程序防护中打开 Office 文档时发生，您还可以从 Office 内提交反馈。 请参阅 [Office 预览体验成员手册](https://insider.office.com/handbook) 以提交反馈。

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>与 Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 集成

Office 应用程序防护与 Microsoft Defender for Endpoint 集成，以提供对隔离环境中发生的恶意活动的监视和警报。

Microsoft Defender for Endpoint 是一个安全平台，旨在帮助企业网络预防、检测、调查和响应高级威胁。 有关此平台的更多详细信息，请参阅[Microsoft Defender for Endpoint。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) 若要了解有关将设备载入此平台的信息，请参阅 [将设备载入到 Microsoft Defender for Endpoint 服务](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)。

还可以将 Microsoft Defender for Office 365 配置为与 Defender for Endpoint 一起工作。 有关详细信息，请参阅 [将 Defender for Office 365 与 Microsoft Defender for Endpoint 集成](integrate-office-365-ti-with-wdatp.md)。

## <a name="limitations-and-considerations"></a>限制和注意事项

* Office 应用程序防护是一种受限模式，可隔离不受信任的文档，以便它们无法访问受信任的公司资源、Intranet、用户标识和计算机上的任意文件。 因此，如果用户尝试访问依赖此类访问的功能（例如，从磁盘上的本地文件插入图片）访问将失败并生成类似以下示例的提示。 若要使不受信任的文档能够访问受信任的资源，用户必须从文档中删除应用程序防护保护。

  ![对话框显示"为了帮助你保持安全，此功能不可用"](../../media/ag10-limitations.png)

  > [!NOTE]
  > 建议用户仅在信任文件及其源或文件来源时删除保护。

* 宏和控件等文档中的活动ActiveX在 Office 应用程序防护中处于禁用状态。 用户需要删除应用程序防护保护才能启用活动内容。

* 来自网络共享或来自不同组织的 OneDrive、OneDrive for Business 或 SharePoint Online 共享的不受信任的文件在应用程序防护中以只读方式打开。 用户可以保存此类文件的本地副本以继续在容器中工作，或删除保护以直接使用原始文件。

* 默认情况下，将阻止受信息权限管理 (IRM) 文件。 如果用户想要在受保护的视图中打开此类文件，管理员必须为组织配置不受支持的文件类型的策略设置。

* 在用户退出并再次登录或设备重启后，Office 应用程序在 Office 应用程序防护中的任何自定义不会保留。

* 只有使用 UIA 框架的辅助功能工具才能为在 Office 应用程序防护中打开的文件提供辅助体验。

* 安装后首次启动应用程序防护需要网络连接。 应用程序防护需要连接才能验证许可证。

* 在文档的信息部分中 *，"上次修改* 者"属性可能会将 **WDAGUtilityAccount 显示为** 用户。 WDAGUtilityAccount 是在应用程序防护中配置的匿名用户。 桌面用户的标识不在应用程序防护容器内共享。

## <a name="performance-optimizations-for-application-guard-for-office"></a>Office 应用程序防护的性能优化

本节概述 Office 应用程序防护中使用的性能优化。 此信息可以帮助管理员在启用应用程序防护时诊断来自用户的报告，这些报告与 Office 或整个系统的性能相关。

应用程序防护使用虚拟化容器将不受信任的文档与系统隔离。 创建容器和设置应用程序防护容器以打开 Office 文档的过程具有性能开销，在用户打开不受信任的文档时可能会对用户体验产生负面影响。

为了为用户提供预期的文件打开体验，当在系统上满足以下启发性要求时，应用程序防护使用逻辑预创建容器：用户在过去 28 天内在受保护的视图或应用程序防护中打开了文件。

当满足此启发式要求时，Office 将在用户登录 Windows 后为用户预创建应用程序防护容器。 虽然此预创建操作正在进行中，但系统可能会遇到性能缓慢的问题，但操作完成后，效果将立即解决。

> [!NOTE]
> 预创建容器的启发式提示由 Office 应用程序在用户使用时生成。 如果用户在启用了应用程序防护的新系统中安装 Office，则 Office 不会预先创建容器，直到用户第一次在系统上打开不受信任的文档。 用户将观察到，在应用程序防护中打开第一个文件需要更长时间。

## <a name="known-issues"></a>已知问题

* 选择 (`http` 或 `https`) 链接不会打开浏览器。
* 目前不支持 (RTF 格式) 应用程序防护打开的 Office 文档中的内容或图像。
* .NET 更新会导致文件在应用程序防护中无法打开。 作为一种解决方法，用户可以在遇到此故障时重新启动其设备。 了解有关尝试打开应用程序防护或 Windows 沙盒时收到错误消息 [Windows Defender的详细信息](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)。
