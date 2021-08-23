---
title: Microsoft Defender for Endpoint 中的新增功能
description: 请参阅最新版本的 Microsoft Defender for Endpoint (GA) 中通常提供哪些功能，以及 Windows 10 和 Windows Server 中的安全功能。
keywords: 适用于终结点的 Microsoft Defender 中的新增功能， ga， 通用， 功能， 可用， 新
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6f38c052c6c1755c0717d8b64987dd69b1a5826d
ms.sourcegitcommit: f2381c3bb3351235aaca977c57a46c654b9b0657
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2021
ms.locfileid: "58387136"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 中的新增功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)。

以下功能在最新版本的 Microsoft Defender for Endpoint (GA) 中通常可用，Windows 10 Windows Server 中的安全功能。

有关预览功能的详细信息，请参阅预览 [功能](preview.md)。


> [!TIP]
> RSS 源：在此页面更新时收到通知，方法为将以下 URL 复制并粘贴到源阅读器中：
>
> ```https
> https://docs.microsoft.com/api/search/rss?search=%22features+are+generally+available+%28GA%29+in+the+latest+release+of+Microsoft+Defender+for+Endpoint%22&locale=en-us&facet=
> ```

## <a name="june-2021"></a>2021 年 6 月

- [Delta 导出软件漏洞评估](get-assessment-methods-properties.md#31-methods) API <br> 导出漏洞和安全配置 API 集合 [评估的](get-assessment-methods-properties.md) 新增内容。 <br> 与完整的软件漏洞评估 (JSON 响应) （用于按设备获取组织的软件漏洞评估的完整快照）不同，增量导出 API 调用仅用于获取所选日期和当前日期之间发生的更改 ("delta"API 调用) 。 您不会每次获取包含大量数据的完全导出，而只会获取有关新的、已修复和更新的漏洞的特定信息。 Delta 导出 API 调用还可用于计算不同的 KPI，例如"修复了多少漏洞"或"向组织添加了多少新漏洞"。

- [导出漏洞和安全配置评估](get-assessment-methods-properties.md) API <br> 添加 API 集合，用于危险和漏洞管理提取数据。 不同的 API 调用用于获取不同类型的数据：安全配置评估、软件清单评估和软件漏洞评估。 每个 API 调用都包含组织中设备的必要数据。

- [修正活动](get-remediation-methods-properties.md) API <br>  添加包含响应的 API 集合，危险和漏洞管理已在租户中创建的修正活动。 响应信息类型包括一个按 ID 的修正活动、所有修正活动以及一个修正活动的公开设备。

- [设备发现](device-discovery.md) <br> 帮助你查找连接到公司网络的非托管设备，而无需额外的设备或繁琐的流程更改。 使用载入的设备，可以在网络中查找非托管设备，并评估漏洞和风险。 然后，你可以载入发现的设备，以减少与网络中具有非托管终结点相关的风险。

   > [!IMPORTANT]
   > 从 2021 年 7 月 19 日开始，标准发现将成为所有客户的默认模式。 你可以选择通过设置页保留基本模式。

- [现在，设备](/microsoft-365/security/defender-endpoint/machine-groups) 组定义可以包括每个条件的多个值。 你可以将多个标记、设备名称和域设置为单个设备组的定义。

- [移动应用程序管理支持](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-new-capabilities-on-android-and-ios/ba-p/2442730) <br> 当 Intune 用于管理移动应用程序时，此增强功能使 Microsoft Defender for Endpoint 能够保护托管应用程序中的组织数据。 有关移动应用程序管理详细信息，请参阅 [本文档](/microsoft-365/mem/intune/apps/mam-faq)。

- [Microsoft TunnelVPN 集成](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-new-capabilities-on-android-and-ios/ba-p/2442730) <br> Microsoft TunnelVPN 功能现已与适用于 Android 的 Microsoft Defender for Endpoint 应用集成。 这种统一使组织能够通过一个安全应用提供简化的最终用户体验 ，同时提供移动威胁防护和从移动设备访问地资源的能力，同时安全和 IT 团队可以保持他们熟悉的相同管理体验。

- [iOS 上的越狱检测](/microsoft-365/security/defender-endpoint/ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios) <br> 适用于 iOS 上的终结点的 Microsoft Defender 中的越狱检测功能现已普遍可用。 这将添加到已存在的网络钓鱼防护中。  有关详细信息，请参阅基于 [设备风险信号设置条件访问策略](/microsoft-365/security/defender-endpoint/ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios)。


## <a name="march-2021"></a>2021 年 3 月
- [使用管理程序管理防Microsoft Defender 安全中心](prevent-changes-to-security-settings-with-tamper-protection.md#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal) <br> 您可以使用一种称为租户附加 的方法在 Windows 10 server 2019 Windows Server 2016、Windows Server 2019 上管理防 *篡改保护设置*。


## <a name="january-2021"></a>2021 年 1 月

- [Windows 虚拟桌面](https://azure.microsoft.com/services/virtual-desktop/) <br> Microsoft Defender for Endpoint 现在增加了对虚拟Windows的支持。

## <a name="december-2020"></a>2020 年 12 月

- [iOS 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-ios.md) <br> Microsoft Defender for Endpoint 现在增加了对 iOS 的支持。 了解如何在 iOS 上安装、配置、更新和使用 Microsoft Defender for Endpoint。

## <a name="september-2020"></a>2020 年 9 月

- [Android 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-android.md) <br> Microsoft Defender for Endpoint 现在增加了对 Android 的支持。 了解如何在 Android 上安装、配置、更新和使用 Microsoft Defender for Endpoint。
- [威胁和 漏洞管理 macOS 支持](tvm-supported-os.md)<br> 适用于 macOS 漏洞管理威胁和漏洞现在公开预览版，它将持续检测 macOS 设备上漏洞，以帮助你通过关注风险确定修复优先级。 从此[Microsoft Tech Community博客文章 了解更多信息](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-for-endpoint-adds-depth-and-breadth-to-threat/ba-p/1695824)。

## <a name="august-2020"></a>2020 年 8 月

- [Android 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-android.md) <br> Microsoft Defender for Endpoint 现在增加了对 Android 的支持。 了解如何在 Android 上安装、配置和使用 Microsoft Defender for Endpoint。

## <a name="july-2020"></a>2020 年 7 月

- [创建证书指示器](manage-indicators.md) <br> 创建指示器以允许或阻止证书。

## <a name="june-2020"></a>2020 年 6 月

- [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md) <br> Microsoft Defender for Endpoint 现在增加了对 Linux 的支持。 了解如何在 Linux 上安装、配置、更新和使用 Microsoft Defender for Endpoint。

- [评估实验室中的攻击模拟器](evaluation-lab.md#threat-simulator-scenarios) <br> Microsoft Defender for Endpoint 已与各种威胁模拟平台合作，让你可以方便地从门户内测试平台的功能。

## <a name="april-2020"></a>2020 年 4 月

- [威胁&漏洞管理 API 支持](exposed-apis-list.md) <BR>运行威胁&漏洞管理相关的 API 调用，例如获取组织的威胁暴露分数或设备安全分数、软件和设备漏洞清单、软件版本分布、设备漏洞信息、安全建议信息。 从此[Microsoft Tech Community博客文章 了解更多信息](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615)。

## <a name="november-december-2019"></a>November-December 2019 年

- [macOS 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md) <BR> macOS 上的 Microsoft Defender for Endpoint 为 Mac 设备带来了下一代保护。 统一终结点安全平台的核心组件现在可用于 Mac 设备，包括 [终结点检测和响应](microsoft-defender-endpoint-mac.md)。

- [威胁&漏洞管理应用程序和应用程序版本生命周期结束信息](tvm-security-recommendation.md) <BR>已进入生命周期结束的应用程序和应用程序版本会进行标记或标记，以便你了解它们将不再受支持，并且可以采取措施卸载或替换它们。 这样做有助于降低因应用程序未修补导致的各种漏洞暴露的风险。

- [威胁&漏洞管理高级搜寻架构](advanced-hunting-schema-reference.md) <BR>使用高级&中的威胁和漏洞管理表查询软件清单、漏洞知识库、安全配置评估和安全配置知识库。

 - [威胁&漏洞管理基于角色的访问控制](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) <BR>使用新权限可允许最大灵活性创建面向 SecOps 的角色、面向威胁 & 漏洞管理的角色或混合角色，以便仅授权用户访问特定数据以执行任务。 通过指定威胁 &和漏洞管理角色是只能查看与漏洞相关的数据，还是可以创建和管理修正和异常，还可以进一步实现粒度。

- [设备运行状况和合规性报告](machine-reports.md) <br/> 设备运行状况和合规性报告提供有关组织中设备的高级别信息。

## <a name="october-2019"></a>2019 年 10 月

- [IP 地址、URL/域指示器](manage-indicators.md) <BR> 你现在可以使用自己的威胁情报允许或阻止 URL/域。

- [Microsoft 威胁专家 - 专家按需](microsoft-threat-experts.md) <BR> 现在，可以选择咨询门户Microsoft 威胁专家多个位置的管理员，以帮助你在调查上下文中使用。

- [连接的 Azure AD 应用程序](connected-applications.md)<br> "已连接应用程序"页提供有关连接到组织中 Microsoft Defender for Endpoint 的 Azure AD 应用程序的信息。

- [API 资源管理器](api-explorer.md)<br> 通过 API 资源管理器，可以轻松构造和执行 API 查询、测试和发送任何可用 Microsoft Defender 终结点 API 终结点的请求。

## <a name="september-2019"></a>2019 年 9 月

- [使用 Intune 的防篡改保护设置](prevent-changes-to-security-settings-with-tamper-protection.md) <br/> 你现在可以在 Microsoft 365 Device Management Portal (Intune (中为组织打开或) 防篡改) 。

- [实时响应](live-response.md) <BR> 使用远程命令行管理程序连接即时访问设备。 开展深入调查工作，并立即采取响应操作，以立即包含识别的威胁- 实时。

- [评估实验室](evaluation-lab.md) <BR> Microsoft Defender for Endpoint 评估实验室旨在消除设备和环境配置的复杂性，以便你可以专注于评估平台的功能、运行模拟，并查看操作中的防护、检测和修正功能。

- [Windows Server 2008 R2 SP1](configure-server-endpoints.md) <BR> 现在，您可以载入 Windows Server 2008 R2 SP1。

## <a name="june-2019"></a>2019 年 6 月

- [威胁&漏洞管理](next-gen-threat-and-vuln-mgt.md) <BR> 新的内置功能，使用基于风险的方法发现、确定终结点漏洞和错误配置的优先顺序并修正。

- [设备运行状况和合规性报告](machine-reports.md)  设备运行状况和合规性报告提供有关组织中设备的高级别信息。

## <a name="may-2019"></a>2019 年 5 月

- [威胁防护报告](threat-protection-reports.md)<BR>威胁防护报告提供有关在组织中生成的警报的高级别信息。

- [Microsoft 威胁专家](microsoft-threat-experts.md)<BR> Microsoft 威胁专家是 Microsoft Defender for Endpoint 中新增的托管威胁搜寻服务，可提供主动搜寻、优先顺序和其他上下文和见解，进一步使安全运营中心 (SOC) 可以快速准确地识别和响应威胁。 它提供了其他专业技能和光学系统层，Microsoft 客户可以利用这些层来增强安全操作功能，这是 Microsoft 365。

- [指示器](ti-indicator.md) <BR> 指示器的 API 现已普遍可用。

- [互操作性](partner-applications.md) <BR> Microsoft Defender for Endpoint 支持第三方应用程序，以帮助增强平台的检测、调查和威胁智能功能。

## <a name="april-2019"></a>2019 年 4 月

- [Microsoft 威胁专家目标攻击通知功能](microsoft-threat-experts.md) <BR> Microsoft 威胁专家目标攻击通知警报专为组织定制，可提供尽可能多的信息，从而引起人们注意其网络中的关键威胁，包括时间线、入侵范围和入侵方法。

- [Microsoft Defender for Endpoint API](apis-intro.md) <BR> Microsoft Defender for Endpoint 通过一组编程 API 公开其大部分数据和操作。 这些 API 将使您能够基于 Microsoft Defender for Endpoint 功能自动执行工作流创新。

## <a name="february-2019"></a>2019 年 2 月

- [事件](view-incidents-queue.md) <BR> 事件是 Microsoft Defender for Endpoint 中的一个新实体，将所有相关警报和相关实体汇集在一起，以讲述更广泛的攻击案例，使分析人员可以更好地了解复杂威胁的可能性。

- [载入以前版本的 Windows](onboard-downlevel.md)<BR> 载入受支持的Windows设备，以便它们可以将传感器数据发送到 Microsoft Defender for Endpoint 传感器。

## <a name="october-2018"></a>2018 年 10 月

- [攻击面减少规则](attack-surface-reduction.md)<BR>所有攻击面减少规则现在在 Windows Server 2019 上受支持。

- [受控文件夹访问](enable-controlled-folders.md)<BR> 现在，Windows Server 2019 支持受控文件夹访问权限。

- [自定义检测](manage-indicators.md)<BR>通过自定义检测，你可以创建自定义查询来监视任何类型的行为（如可疑或新出现的威胁）的事件。 这可以通过创建自定义检测规则来利用高级搜寻功能实现。

- [与 Azure Defender 集成](configure-server-endpoints.md)<BR> Microsoft Defender for Endpoint 与 Azure Defender 集成，以提供全面的服务器保护解决方案。 借助此集成，Azure Defender 可以利用 Microsoft Defender for Endpoint 功能，为 Windows 服务器提供改进的威胁检测。

- [托管安全服务提供程序 (MSSP) 支持](mssp-support.md)<BR> Microsoft Defender for Endpoint 通过提供 MSSP 集成添加了对此方案的支持。 此集成将允许 MSSP 执行以下操作：获取对 MSSP 客户的 Microsoft Defender 安全中心 门户的访问权限、获取电子邮件通知，以及使用 SIEM) 工具通过安全信息和事件管理获取 (警报。

- [可移动设备控件](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/19/windows-defender-atp-has-protections-for-usb-and-removable-devices/)<BR>Microsoft Defender for Endpoint 提供了多个监视和控制功能，以帮助防止来自可移动设备的威胁，包括允许或阻止特定硬件 ID 的新设置。

- [支持 iOS 和 Android 设备](configure-endpoints-non-windows.md)<BR> iOS 和 Android 设备现在受支持，可以载入到服务。

- [威胁分析](threat-analytics.md)<BR>
威胁分析是 Microsoft Defender for Endpoint 研究团队在发现新出现的威胁和爆发后尽快发布的一组交互式报告。 这些报告可帮助安全运营团队评估对环境的影响，并提供包含、提高组织恢复能力并防止特定威胁的建议操作。

- 版本 1809 Windows 10中的新增功能，有两个新的攻击面减少规则：
  - 阻止 Adobe Reader 创建子进程
  - 阻止Office应用程序创建子进程。

- [Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
  - 反恶意软件扫描接口 (AMSI) 扩展为覆盖Office VBA 宏。 [Office VBA + AMSI：将恶意宏上的程序分在一起](https://cloudblogs.microsoft.com/microsoftsecure/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/)。
  - Microsoft Defender 防病毒版本 1809 中新增Windows 10，现在可以在沙盒 (预览) [](https://www.microsoft.com/security/blog/2018/10/26/windows-defender-antivirus-can-now-run-in-a-sandbox)运行，从而提升其安全性。
  - [配置扫描的 CPU](configure-advanced-scan-types-microsoft-defender-antivirus.md) Microsoft Defender 防病毒设置。

## <a name="march-2018"></a>2018 年 3 月

- [高级搜寻](advanced-hunting-overview.md)

   在 Microsoft Defender for Endpoint 中使用高级搜寻查询数据。

- [攻击面减少规则](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)

  新的攻击面减少规则：

  - 使用高级防护抵御勒索软件
  - 阻止本地安全机构子系统Windows窃取凭据 (lsass.exe) 
  - 阻止源自 PSExec 和 WMI 命令的进程创建
  - 阻止从 USB 运行的不受信任的和未签名的进程
  - 阻止来自电子邮件客户端和 Webmail 的可执行内容

- [自动调查和修正](automated-investigations.md)<BR> 使用自动调查来调查和修正威胁。

    > [!NOTE]
    > 可从 Windows 10 版本 1803 或更高版本获得。

- [条件访问](conditional-access.md) <br> 启用条件访问以更好地保护用户、设备和数据。

- [Microsoft Defender for Endpoint Community 中心](community.md)<BR>
    Microsoft Defender for Endpoint Community 中心是社区成员可以学习、协作和共享产品体验的地方。

- [受控文件夹访问](enable-controlled-folders.md)<BR>
你现在可以使用受控文件夹访问权限阻止不受信任的进程写入磁盘扇区。

- [载入非 Windows 设备](configure-endpoints-non-windows.md)<BR>
    Microsoft Defender for Endpoint 为用户和非 Windows平台提供了集中式安全Windows体验。 你将能够查看来自各种受支持操作系统和操作系统警报 (操作系统) Microsoft Defender 安全中心更好地保护组织的网络。

- [基于角色的访问控制 (RBAC)](rbac.md)<BR>
    使用基于角色的访问控制 (RBAC) ，可以在安全操作团队内创建角色和组，以授予对门户的适当访问权限。


- [Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)<BR>
Microsoft Defender 防病毒服务之间共享检测状态Microsoft 365 Microsoft Defender for Endpoint 进行互操作。 有关详细信息，请参阅通过云保护在 Microsoft Defender 防病毒[中使用下一代技术](cloud-protection-microsoft-defender-antivirus.md)。

    "首次看到时阻止"现在可以阻止不可移植的可执行 (，例如 JS、VBS 或宏) 可执行文件。 有关详细信息，请参阅启用 [首次看到时阻止](configure-block-at-first-sight-microsoft-defender-antivirus.md)。
