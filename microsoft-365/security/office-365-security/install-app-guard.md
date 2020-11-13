---
title: '适用于 Office 365 的应用程序防护 (针对管理员的公共预览版) '
keywords: 应用程序防护、保护、隔离、独立容器、硬件隔离
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 获取最新的基于硬件的隔离。 阻止目前和新兴攻击（如入侵或恶意链接）中断员工工作效率和企业安全性。
ms.openlocfilehash: c9b31ff91521b6badda31b6eb3202f370769a0fd
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49021069"
---
# <a name="application-guard-for-office-public-preview-for-admins"></a>Office 的应用程序防护 (公共预览版) 的管理员

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**适用于：** 适用于 Microsoft 365 的 Word、Excel 和 PowerPoint，Windows 10 企业版

>[!IMPORTANT]
>一些信息与 prereleased 产品相关，在正式发布之前，可能会对其进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

适用于 Office 的 Microsoft Defender 应用程序防护 (Office) 的应用程序防护可帮助防止不受信任的文件访问受信任的资源，从而使您的企业免受新的和新兴的攻击。 本文将指导管理员为 Office 的应用程序防护的预览设置设备。 它提供了有关系统要求和安装步骤的信息，以在设备上启用 Office 的应用程序防护。

## <a name="prerequisites"></a>先决条件

### <a name="minimum-hardware-requirements"></a>最低硬件要求

* **CPU** ： 64-位、4核 (物理或虚拟) 、虚拟化扩展 (Intel VT-x 或 AMD-V) 、Core i5 等效项或更高版本建议
* **物理内存** ： 8 GB RAM
* **硬盘** ：系统驱动器上有 10 GB 的可用空间 (SSD 建议) 

### <a name="minimum-software-requirements"></a>最低软件要求

* **Windows 10** ： Windows 10 企业版，客户端内部版本 2004 (20H1) 内部版本19041
* **Office** ： Office Beta 频道内部版本 2008 16.0.13212 或更高版本
* **更新包** ： Windows 10 累积的每月安全更新 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

有关系统要求的详细信息，请参阅 [Microsoft Defender 应用程序防护的系统要求](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)。 若要了解有关 Office 预览体验成员预览版的详细信息，请参阅 [部署 Office 预览体验成员内部版本](https://insider.office.com/business/deploy)入门。

### <a name="licensing-requirements"></a>许可要求

* Microsoft 365 E5 或 Microsoft 365 E5 安全

## <a name="deploy-application-guard-for-office"></a>部署适用于 Office 的应用程序防护

### <a name="enable-application-guard-for-office"></a>启用 Office 应用程序防护

1. 下载并安装 **Windows 10 累积的每月安全更新 KB4571756** 。

2. 在 Windows 功能下选择 " **Microsoft Defender 应用程序防护** "，然后选择 **"确定"** 。 启用应用程序防护功能将提示系统重新启动。 可以选择立即重新启动，也可以选择在步骤3之后重新启动。

   ![显示 AG 的 "Windows 功能" 对话框](../../media/ag03-deploy.png)

   还可以通过以管理员身份运行以下 PowerShell 命令来启用此功能：

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. 在 " **计算机配置 \\ 管理模板" \\ Windows 组件 " \\ Microsoft defender 应用程序防护** " 中，查找位于托管模式组策略中的 Microsoft defender 应用程序防护。 通过将 "选项" 下的值设置为 **2** 或 **3** ，然后选择 **"确定" 或 "** **应用** "，打开此策略。

   ![在托管模式下打开 AG](../../media/ag04-deploy.png)

   或者，您可以设置相应的 CSP 策略：

   OMA-URI： **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**<br/>
   数据类型： **Integer**<br/>
   值： **2**

4. 重新启动系统。

### <a name="set-diagnostics--feedback-to-send-full-data"></a>设置诊断 & 反馈以发送完整数据

此步骤可确保确定和修复问题所需的数据正在到达 Microsoft。 按照以下步骤在你的 Windows 设备上启用诊断：

1. 打开 "开始" 菜单中的 " **设置** "。

   ![“开始”菜单](../../media/ag05-diagnostic.png)

2. 在 " **Windows 设置** " 中，选择 " **隐私** "。

   ![Windows 设置菜单](../../media/ag06-diagnostic.png)

3. 在 "隐私" 下，选择 " **诊断 & 反馈** " 并选择 " **可选诊断数据** "。

   ![诊断和反馈菜单](../../media/ag07a-diagnostic.png)

有关配置 Windows 诊断设置的详细信息，请参阅 [在组织中配置 windows 诊断数据](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)。

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>确认 Office 相关应用程序防护已启用且正常工作

在确认已启用 Office 的应用程序防护功能之前，请在已部署策略的设备上启动 Word、Excel 或 PowerPoint。 请确保 Office 已激活。 您可能需要使用您的工作标识，以便先激活 Office 产品。

若要确认 Office 的应用程序防护功能现已启用，请启动 Word、Excel 或 PowerPoint 并打开不受信任的文档。 例如，您可以打开从 internet 下载的文档或从组织外部的某个人的电子邮件附件。

在第一次启动不受信任的文件时，您可能会看到如下所示的 Office 初始屏幕。 它可能会在激活 Office 的应用程序防护和打开文件时显示一段时间。 随后启动不受信任的文件的速度应更快。

![Office 应用程序初始屏幕](../../media/ag08-confirm.png)

打开文件时，该文件应显示文件在 Office 应用程序防护中打开的一些可视指示器：

* 功能区中的标注

  ![显示小型应用程序防护注释的文档文件](../../media/ag09-confirm.png)

* 在任务栏中带有屏蔽的应用程序图标

  ![任务栏中的图标](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>配置适用于 Office 的应用程序防护

Office 支持以下策略，以使您能够配置适用于 Office 的应用程序防护功能。 可以通过组策略或 Office 云策略服务配置这些策略。

> [!NOTE]
> 这些策略很快就会推出。
> 此外，配置这些策略可以对在 Office 应用程序防护中打开的文件禁用某些功能。

|Policy|Description|
|---|---|
|禁用 Office 应用程序防护|启用此策略将强制 Word、Excel 和 PowerPoint 使用受保护的视图隔离容器，而不是应用程序防护 Office。 此策略可用于临时禁用 Office 的应用程序防护（如果在使其处于启用状态时出现问题）。|
|对在应用程序防护中打开的文档禁用复制/粘贴|启用此策略将阻止用户从 Office 应用程序防护中打开的文档中复制和粘贴内容，并将其粘贴到在其外部打开的文档中。|
|阻止用户删除文件上的应用程序防护保护|启用此策略将删除 Office 应用程序体验) 中的选项 (，以禁用应用程序防护保护或在应用程序防护外部打开文件。 <p> **注意：** 用户仍然可以通过手动删除文件中的标记 web 属性或将文档移到受信任位置来绕过此策略。|
|限制在应用程序防护中打开的文档打印|启用此策略将限制用户可以从在 Office 的应用程序防护中打开的文件打印到的打印机。 例如，可以使用此策略将用户限制为仅打印到 PDF。|
|对在应用程序防护中打开的文档关闭相机和麦克风访问|启用此策略将删除 Office 的应用程序防护中对相机和麦克风的访问权限。|
|

> [!NOTE]
> 以下策略将要求用户注销并重新登录到 Windows 以使其生效：
>
> * 对在应用程序防护中打开的文档禁用复制/粘贴
> * 限制对在应用程序防护中打开的文档的打印
> * 关闭在应用程序防护中打开的对文档的摄像头和麦克风访问

## <a name="submit-feedback"></a>提交反馈

### <a name="submit-feedback-via-feedback-hub"></a>通过反馈中心提交反馈

如果您在启动 Office 的应用程序防护时遇到任何问题，则建议您通过反馈中心提交反馈：

1. 打开 " **反馈中心" 应用** 并登录。

2. 如果在启动应用程序防护时收到错误对话框，请在错误对话框中选择 " **报告给 Microsoft** " 以启动新的反馈提交。 否则，导航到 <https://aka.ms/wdagoffice-fb> 以选择 "应用程序防护" 的正确类别，然后选择 "+ 在右上角 **添加新反馈** "。

3. 如果尚未填写您的反馈框，请填写 " **汇总您的反馈** " 框。

4. 在 " **详细** 说明" 框中填写你遇到的问题的详细说明和所需的步骤，然后选择 " **下一步** "。

5. 选择 "问题" 旁边的气泡。 确保选择的类别是 **安全和隐私 \> Microsoft Defender 应用程序防护– Office** ，然后选择 " **下一步** "。

6. 依次选择 " **新反馈** " 和 " **下一步** "。

7. 收集有关此问题的跟踪：

   1. 展开 " **重新创建我的问题** " 磁贴。

   2. 如果在运行应用程序防护时遇到问题，请打开应用程序防护实例。 执行此操作后，将从应用程序防护容器中收集其他跟踪。

   3. 选择 " **开始录制** " 并等待磁贴停止旋转并说出 " *停止录制* "。

   4. 使用应用程序防护完全重现问题。 这可能包括尝试启动应用程序防护实例并等待它失败，或在正在运行的应用程序防护实例中再现问题。

   5. 选择 " **停止录制** " 磁贴。

   6. 保持任何正在运行的应用程序防护实例/s 处于打开状态，即使在提交之后几分钟，也可以收集容器诊断。

8. 附加与问题相关的任何相关的屏幕截图或文件。

9. 选择“ **提交** ”。

### <a name="submit-feedback-via-office-customer-voice"></a>通过 Office 客户语音提交反馈

如果在应用程序防护中打开 Office 文档时出现问题，则还可以从 Office 中提交反馈。 有关提交反馈的信息，请参阅 [Office 预览体验手册](https://insider.office.com/handbook) 。

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>与 Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 的集成

适用于 Office 的应用程序防护将与 Microsoft Defender for Endpoint 集成，以提供有关隔离环境中发生的恶意活动的监视和警报。

Microsoft Defender for Endpoint 是一种安全平台，旨在帮助企业网络阻止、检测、调查和响应高级威胁。 有关此平台的更多详细信息，请访问 [Microsoft Defender For Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) 页。 有关将设备加入到此平台的详细信息，请参阅 [Microsoft Defender For Endpoint service 的板载设备](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)。

您还可以配置 Microsoft Defender for Office 365 以使用适用于终结点的 Defender。 请参阅将 [适用于 Office 365 的 defender 与 Microsoft Defender For Endpoint 集成](integrate-office-365-ti-with-wdatp.md)。

## <a name="limitations-and-considerations"></a>限制和注意事项

* 适用于 Office 的应用程序防护是一种限制模式，它将不受信任的文档与访问受信任的公司资源、intranet、用户标识和计算机上的任意文件隔离。 因此，如果用户尝试访问依赖于此类访问的功能（例如，从磁盘上的本地文件中插入图片），它将会失败，并生成如下所示的提示。 若要使不受信任的文档能够访问受信任的资源，用户必须从文档中删除应用程序防护保护。

  ![对话框说为帮助您保持安全，此功能不可用](../../media/ag10-limitations.png)

  > [!NOTE]
  > 建议仅当用户信任文件及其来源或来自何处时才删除保护。

* 在 Office 相关应用程序防护中禁用了宏和 ActiveX 控件等文档中的活动内容。 用户需要删除应用程序防护保护以启用活动内容。

* 从其他组织以只读方式在应用程序防护中打开的网络共享或从 OneDrive、OneDrive for business 或 SharePoint Online 共享的文件中打开的不受信任文件。 用户可以保存此类文件的本地副本，以继续在容器中工作或取消保护以直接使用原始文件。

* 受信息权限管理 (IRM 保护的文件) 继续在受保护的视图中打开。

* 在用户注销并重新登录或重新启动设备后，Office 应用程序防护中 Office 应用程序的任何自定义设置都不会保留。

* 只有使用 UIA 框架的辅助功能工具才能为在 Office 应用程序防护中打开的文件提供可访问的体验。

* 安装后首次启动应用程序防护时，需要网络连接。 这是应用程序防护验证许可证所必需的。

* 在文档的 "信息" 部分中，" *上次修改者* " 属性可能会显示 "WDAGUtilityAccount" 作为用户。 这是在应用程序防护中配置的匿名用户，在应用程序防护容器中不共享桌面用户的标识。

## <a name="performance-optimizations-for-application-guard"></a>应用程序防护的性能优化

本节概述了在 Office 相关应用程序防护中使用的性能优化。 此信息可帮助管理员在启用应用程序防护时，诊断与 Office 性能或整个系统相关的用户的报告。

应用程序防护使用虚拟化容器将不受信任的文档隔离在系统之外。 在用户打开不受信任的文档时，创建容器并将应用程序防护容器设置为打开 Office 文档的过程可能会对用户体验产生负面影响。

若要向用户提供预期的文件打开体验，应用程序防护在系统上满足以下试探法时使用逻辑来预创建容器：用户在过去28天内打开了受保护的视图或应用程序防护中的文件。

当满足此启发时，Office 将在用户登录到 Windows 之后预先为该用户创建应用程序防护容器。 在此预创建操作进行过程中，系统可能会遇到性能降低的情况。 此操作将在操作完成后立即解决。

> [!NOTE]
> 用于预创建容器的启发所需的提示是由 Office 应用程序在用户使用时生成的。 如果用户在启用了应用程序防护的新系统上安装 Office，则在用户第一次在系统上打开不受信任的文档之前，Office 将不会预先创建该容器。 用户将会发现，在应用程序防护中打开第一个文件需要的时间较长。

## <a name="known-issues-in-preview"></a>预览中的已知问题

* 单击 "web 链接" (`http` 或 `https`) 不会打开浏览器。
* .NET 更新会导致文件无法在应用程序防护中打开。 作为一种解决方法，当遇到此问题时，用户可以重新启动其设备。 了解有关在 [尝试打开 Windows Defender 应用程序防护或 Windows 沙盒时收到错误消息时](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)的问题的详细信息。
