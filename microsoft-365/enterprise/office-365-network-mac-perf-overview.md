---
title: 'Microsoft 365 管理中心中的网络连接 (预览) '
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
description: 'Microsoft 365 管理中心预览版中的网络连接 (概述) '
ms.openlocfilehash: 159edf6f95910625c3f924d02c8307d681164df7
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454237"
---
# <a name="network-connectivity-in-the-microsoft-365-admin-center-preview"></a>Microsoft 365 管理中心中的网络连接 (预览) 

Microsoft 365 管理中心现在包括从 Microsoft 365 租户收集的聚合网络连接指标，并且仅可供租户中的管理用户查看。

> [!div class="mx-imgBorder"]
> ![网络连接测试工具](../media/m365-mac-perf/m365-mac-perf-admin-center.png)

**网络评估和****网络见解** 显示在 Microsoft 365 管理中心中的 **"运行状况"|连接**。

> [!div class="mx-imgBorder"]
> ![网络性能页面](../media/m365-mac-perf/m365-mac-perf-page-nav.png)

>[!NOTE]
>网络连接测试工具支持 WW 商业德国的租户，但不支持 GCC 中等、GCC 高、DoD 或中国租户。

首次导航到网络性能页面时，你将看到一个概述窗格，其中包含全局网络性能地图、范围为整个租户的网络评估以及当前问题列表。 从概述中，可以深入了解以按位置查看特定网络性能指标和问题。 有关详细信息，请参阅 [Microsoft 365](#network-connectivity-overview-in-the-microsoft-365-admin-center)管理中心中的网络性能概述。

系统可能会要求你代表组织加入此功能的公共预览版。 接受通常立即发生，然后你将看到网络连接页面。 

在导航到网络连接页面时，你将看到一个概述窗格，其中包含全局网络性能地图、范围为整个租户的网络评估以及当前问题列表。 若要访问此页面，你必须是 Microsoft 365 中组织的管理员。 报表阅读器管理角色将具有对此信息的读取权限。 若要配置网络连接的位置和其他元素，管理员必须是服务器管理员角色（如服务支持管理员角色）的一部分。 从概述中，可以深入了解以按位置查看特定网络性能指标和问题。 有关详细信息，请参阅 [Microsoft 365](#network-connectivity-overview-in-the-microsoft-365-admin-center)管理中心中的网络连接概述。

## <a name="pre-requisites-for-network-connectivity-assessments-to-appear"></a>要显示网络连接评估的先决条件

To get started， turn on your location opt-in setting to automatically collect data from devices using Windows Location Services， go to your Locations list to add or upload location data， or run the Microsoft 365 network connectivity test from your office locations. 尽管可以在整个组织中评估网络连接，但需要针对特定办公地点进行网络设计改进。 确定每个办公室位置后，会提供这些位置的网络连接信息。 有三个选项用于从办公室位置获取网络评估：

### <a name="1-enable-windows-location-services"></a>1. 启用 Windows Location Services

对于此选项，您必须在每个支持先决条件的办公地点至少运行两台计算机。 OneDrive for Windows 版本必须是最新的，并且必须安装在每台计算机中。 有关 OneDrive 版本的信息，请参阅 [OneDrive 发行说明](https://support.office.com/article/onedrive-release-notes-845dcf18-f921-435e-bf28-4e24b95e5fc0)。 计划在近期内在其他 Office 365 客户端应用程序中添加网络测量。

必须在计算机上同意 Windows 位置服务。 可以通过运行地图应用并找到你自己来测试这一点。 可以在具有"设置"选项的单个计算机上 **|隐私|必须** 启用设置 _"允许应用访问你_ 的位置"。 可以使用 MDM 或组策略以及设置 _LetAppsAccessLocation_ 将 Windows Location Services 同意部署到电脑。

无需使用此方法在管理中心中添加位置，因为它们会在城市解决方案中自动标识。 无法使用 Windows 位置服务在一个城市内显示多个办公室位置。 在上载之前，位置信息也会四舍五入到最近的 300 米 300 米，以便无法访问更精确的位置信息。

计算机应具有Wi-Fi网络，而不是以太网电缆。 具有以太网电缆的计算机没有准确的位置信息。

测量示例和办公室位置应在满足这些先决条件后的 24 小时后开始显示。

### <a name="2-add-locations-and-provide-lan-subnet-information"></a>2. 添加位置并提供 LAN 子网信息

对于此选项，不需要 Windows Location Services Wi-Fi配置。 OneDrive for Windows 版本必须处于最新状态，并安装在位于该位置的每台计算机中。

还需要在管理中心网络连接页中添加位置或从 CSV 文件导入位置。 添加的位置必须包含 Office LAN 子网信息。

由于要添加位置，因此可以在一个市/县内定义多个办公室。

客户端计算机的所有测试测量都包括 LAN 子网信息，该信息与已输入的办公地点详细信息相关联。 测量示例和办公室位置应在满足这些先决条件后的 24 小时后开始显示。

### <a name="3-manually-gather-test-reports-with-the-microsoft-365-network-connectivity-test-tool"></a>3. 使用 Microsoft 365 网络连接测试工具手动收集测试报告

对于此选项，你需要在每个位置标识一个人。 让他们在具有管理权限的 Windows 计算机上浏览到 [Microsoft 365](https://connectivity.office.com) 网络连接测试。 在网站中，他们需要登录到想要查看结果的同一组织的 Office 365 帐户。 然后，他们应单击 **"运行测试"。** 测试期间有下载的连接测试 EXE。 他们还需要打开并执行。 测试完成后，测试结果将上载到 Office 365。

如果测试报告是使用 LAN 子网信息添加的，则它将链接到该位置，否则它们仅在城市位置显示。

测试报告完成后，应在 2-3 分钟后开始显示测量示例和办公室位置。 有关详细信息，请参阅[Microsoft 365 网络连接测试 (预览) 。 ](office-365-network-mac-perf-onboarding-tool.md)

## <a name="how-do-i-use-this-information"></a>如何使用此信息？

**网络见解**、其相关的性能建议和网络评估旨在帮助您设计办公地点的网络外围。 每个见解提供有关用户访问租户的每个地理位置的特定常见问题的性能特征的详细信息。 **每个网络** 见解的性能建议都提供您可以进行的特定网络体系结构设计更改，以改进与 Microsoft 365 网络连接相关的用户体验。 网络评估显示网络连接如何影响用户体验，从而可以比较不同的用户位置网络连接。

**网络评估** 将许多网络性能指标聚合到企业网络运行状况的快照中，用 0 到 100 的点值表示。 网络评估的范围为整个租户以及用户连接到租户的每个地理位置，为 Microsoft 365 管理员提供了一种简单方法，可立即掌握企业网络运行状况的全局信息，并快速深入到任何全局办公地点的详细报告。

具有多个办公地点和普通网络外围体系结构的复杂企业可以在初始载入 Microsoft 365 期间从此信息中获益，或修正随着使用率增长发现的网络性能问题。 对于使用 Microsoft 365 的小型企业或任何已经具有简单直接网络连接的企业，通常不需要这样做。 拥有 500 多个用户和多个办公地点的企业预期受益最大。

>[!IMPORTANT]
>Microsoft 365 管理中心中的网络见解、性能建议和评估目前处于预览状态，仅适用于已在功能预览计划注册的 Microsoft 365 租户。

## <a name="enterprise-network-connectivity-challenges"></a>企业网络连接挑战

> [!div class="mx-imgBorder"]
> ![客户网络到云](../media/m365-mac-perf/m365-mac-perf-first-last-mile.png)

许多企业具有网络外围配置，这些配置已随着时间的推移而增长，主要旨在适应大多数网站都未知且不受信任的员工 Internet 网站访问。 当前和必要的焦点是避免来自这些未知网站的恶意软件和钓鱼攻击。 此网络配置策略虽然有助于实现安全目的，但可能会导致 Microsoft 365 用户性能和用户体验下降。

## <a name="how-we-can-solve-these-challenges"></a>我们如何解决这些问题

企业可以通过遵循 [Office 365 连接](https://aka.ms/pnc) 原则以及使用 Microsoft 365 管理中心网络连接功能，改善常规用户体验并保护其环境。 在大多数情况下，遵循这些一般原则将对最终用户延迟、服务可靠性和 Microsoft 365 的总体性能产生显著正面影响。

有时会要求 Microsoft 调查适用于大型企业客户的 Microsoft 365 的网络性能问题，这些问题通常具有与客户网络外围基础结构相关的根本原因。 当找到客户网络外围问题的常见根本原因时，我们寻找识别它的简单测试度量。 具有标识特定问题的测量阈值的测试非常有价值，因为我们可以在任何位置测试相同的度量，判断该根本原因是否存在于该位置，并与管理员共享网络见解。

某些网络见解只是指示需要进一步调查的问题。 我们有足够的测试来显示用于纠正根本原因的特定修正操作的网络见解作为建议 **操作列出**。 这些建议基于显示超出预先确定阈值的值的实际指标，比一般最佳做法建议更有价值，因为它们特定于您的环境，并且将在建议更改后显示实际改进。

## <a name="network-connectivity-overview-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理中心中的网络连接概述

Microsoft 具有多个支持 Microsoft 365 运营的 Office 桌面和 Web 客户端的现有网络度量。 这些度量现在用于提供网络体系结构设计见解和网络评估，这些评估显示在 Microsoft 365管理中心的"网络连接"页中。

默认情况下，与网络测量相关的近似位置信息标识客户端设备所在的城市。 每个位置的网络评估都显示颜色，每个位置的用户的相对数量由圆的大小表示。

> [!div class="mx-imgBorder"]
> ![网络见解概述地图](../media/m365-mac-perf/m365-mac-perf-overview-map.png)

概述页面还将客户的网络评估作为所有办公地点的加权平均值显示。

> [!div class="mx-imgBorder"]
> ![网络评估](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

您可以在"位置"选项卡中查看可以筛选、排序和编辑位置的表视图。具有特定建议的位置可能还包括估计的潜在延迟改进。 计算公式为：在位置采用组织用户的中值延迟，并减去同一城市中所有组织的中值延迟。

> [!div class="mx-imgBorder"]
> ![网络见解位置](../media/m365-mac-perf/m365-mac-perf-locations.png)

## <a name="specific-office-location-network-performance-summary-and-insights"></a>特定办公室位置网络性能摘要和见解

选择一个办公室位置将打开一个特定于位置的摘要页，其中显示从该办公室位置的度量中标识的网络出口的详细信息。

> [!div class="mx-imgBorder"]
> ![按位置的网络见解详细信息](../media/m365-mac-perf/m365-mac-perf-locations-plan-overview.png)

显示位置组织用户的外围网络地图，其中包含以下部分或所有元素：

- **Office 位置** - 所查看页面的办公地点
- **网络外围** - 来自办公室位置的连接的源 IP 地址的位置。 这取决于地理位置 IP 位置数据库的准确性
- **Exchange 最佳服务前端** - 此办公室位置的用户应连接到的推荐 Exchange 服务前门之一
- **Exchange 次最佳前端** - 用户已连接到的 Exchange 服务前端，但不建议这样做
- **SharePoint 最佳服务前端** - 此办公室位置的用户应连接到的推荐 SharePoint 服务前门之一
- **SharePoint 次优化服务前端** - 用户已连接到但不推荐的 SharePoint 服务前端
- **DNS 递归** 解析器服务器 - 检测到用于 Exchange Online (的 DNS 递归解析程序（如果可用）的地理位置 IP) 
- **代理服务器** - 检测到的代理服务器的地理位置 IP 数据库中的 (（如果)  

此外，"办公室位置摘要"页还显示位置的网络评估、网络评估历史记录、此位置的评估与同一城市的其他客户的比较，以及可用于提高网络性能和可靠性的特定见解和建议的列表。

同一城市的客户之间的比较基于以下预期：所有客户都具有相同的网络服务提供商、电信基础结构和附近的 Microsoft 网络接入点的访问权限。

"办公室位置"页上的详细信息选项卡显示用于提供任何见解、建议和网络评估的特定测量结果。 提供此功能，以便网络工程师可以验证其环境中任何约束或具体条件的建议和因素。

> [!div class="mx-imgBorder"]
> ![特定于位置的详细信息](../media/m365-mac-perf/m365-mac-perf-locations-plan-details-all.png)

## <a name="csv-import-for-lan-subnet-office-locations"></a>LAN 子网办公室位置的 CSV 导入

对于 LAN 子网办公室标识，需要提前添加每个位置。 你可以从 CSV 文件导入位置，而不是在"位置"选项卡中添加单独的办公室位置。 你可以从存储该数据的其他位置（如呼叫质量仪表板或 Active Directory 站点和服务）获取此数据

在 CSV 文件中，发现的市/县位置在 userEntered 列中显示为空，手动添加的办公地点将显示为 1。

1. 在"与 _Microsoft 365 的连接_ "主窗口中，单击 **"位置"** 选项卡。

1. 单击 **位置** 列表正上方的"导入"按钮。 将出现 **"导入办公室位置** "飞出。

   > [!div class="mx-imgBorder"]
   > ![CSV 导入消息](../media/m365-mac-perf/m365-mac-perf-import.png)

1. 单击 **"下载当前办公室 (.csv)** 链接，将当前位置列表导出到 CSV 文件，并将其保存到本地硬盘。 这将为您提供格式正确的 CSV 以及列标题，您可以向其中添加位置。 可以将现有导出的位置保留为现有位置;导入更新后的 CSV 时不会复制它们。 如果要更改现有位置的地址，它将在导入 CSV 时更新。 无法更改已发现城市的地址。

1. 打开 CSV 并添加位置，在要添加的每个位置的新行中填写以下字段。 将所有其他字段留空;在其他字段中输入的值将被忽略。

   1. **userEntered** (必需) ：对于新的 LAN 子网办公室位置，必须为 1
   1. **所需的** (地址) ：办公室的物理地址
   1. **Latitude** (可选) ：通过必应地图查找地址填充（如果为空）
   1. **经度** (可选) ：通过必应地图查找地址填充（如果为空）
   1. 出口 IP 地址 **范围 1-5** (可选) ：对于每个范围，输入电路名称后跟有效 IPv4 或 IPv6 CIDR 地址的空格分隔列表。 这些值用于区分使用同一 LAN 子网 IP 地址的多个办公室位置。 出口 IP 地址范围必须为 /24 网络大小，输入中不包含 /24。
   1. **LanIps** (必需) ：列出此办公室位置使用的 LAN 子网范围。 LAN 子网 ID 需要包含 CIDR 网络大小，其中网络大小可以介于 /8 和 /29 之间。 可以使用逗号或分号分隔多个 LAN 子网范围。
   
1. 添加办公室位置并保存文件后，单击"上载已完成"字段旁边的"浏览"按钮，然后选择保存的 CSV 文件。

1. 将自动验证该文件。 如果存在验证错误，你将看到错误消息 _导入文件中存在一些错误。查看错误，更正导入文件，然后重试。_ 单击特定 **字段验证** 错误列表的"打开错误详细信息"链接。

   > [!div class="mx-imgBorder"]
   > ![CSV 导入错误消息](../media/m365-mac-perf/m365-mac-perf-import-error.png)

1. 如果文件中没有任何错误，则会看到消息"报告 _已准备就绪"。找到要添加的 x 位置和要更新的 x 位置。_ 单击 **"导入** "按钮上载 CSV。

   > [!div class="mx-imgBorder"]
   > ![CSV 导入就绪消息](../media/m365-mac-perf/m365-mac-perf-import-ready.png)

## <a name="faq"></a>常见问题

### <a name="what-is-a-microsoft-365-service-front-door"></a>什么是 Microsoft 365 服务前端？

Microsoft 365 服务前端是 Microsoft 全局网络的入口点，Office 客户端和服务将终止其网络连接。 为了获得最佳到 Microsoft 365 的网络连接，建议将网络连接终止到最近的 Microsoft 365 前端。

>[!NOTE]
>Microsoft 365 服务前端与 Azure 市场中提供的 Azure Front Door Service 产品没有直接关系。

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a>什么是最佳的 Microsoft 365 服务前端？

最佳的 Microsoft 365 服务前端是离网络出口最近的入口，通常位于城市或都市区域。 使用 [Microsoft 365 ](office-365-network-mac-perf-onboarding-tool.md) 连接测试工具 (预览) 确定使用中的 Microsoft 365 服务前端的位置和最佳服务前端。 如果该工具确定你的使用中的前端是最佳的，则以最佳方式连接到 Microsoft 的全局网络。

### <a name="what-is-an-internet-egress-location"></a>什么是 Internet 出口位置？

Internet 出口位置是网络流量退出企业网络并连接到 Internet 的位置。 这还将标识为具有网络地址转换 (NAT) 设备的位置，以及通常与 Internet 服务提供商 (ISP) 。 如果看到您的位置和 Internet 出口位置之间的距离很长，则这可能表示 WAN 回程很大。

## <a name="related-topics"></a>相关主题

[Microsoft 365 网络见解 (预览) ](office-365-network-mac-perf-insights.md)

[Microsoft 365 网络评估 (预览) ](office-365-network-mac-perf-score.md)

[Microsoft 365 连接测试工具 (预览) ](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 网络连接位置服务 (预览) ](office-365-network-mac-location-services.md)
