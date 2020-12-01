---
title: 升级自 SharePoint 2010
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- WSU140
- OSU140
ms.assetid: 985a357f-6db7-401f-bf7a-1bafdf1f312c
f1.keywords:
- NOCSH
description: 查找要从 SharePoint 2010 和 Sharepoint Server 2010 升级的信息和资源。 支持在2021年4月13日结束。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fba095a15164f8a09ce1e0a1cbd5ee9cd298aa74
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519759"
---
# <a name="upgrading-from-sharepoint-2010"></a>升级自 SharePoint 2010

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

Microsoft SharePoint 2010 和 SharePoint Server 2010 将在 **年4月 13 2021 日** 到达支持的末尾。 本文提供的资源可帮助您将现有的 SharePoint Server 2010 数据迁移到 Microsoft 365 中的 SharePoint Online 或升级本地 SharePoint Server 2010 环境。

## <a name="what-is-end-of-support"></a>什么是 *支持结束*？

大多数 Microsoft 产品都有支持生命周期，在此期间，它们获取新功能、缺陷修补程序、安全修补程序等。 在支持结束日期后，产品不会停止工作，但 Microsoft 不再提供：

- 可能出现的问题的技术支持。

- 针对可能会影响服务器稳定性和可用性的问题的 Bug 修补程序。

- 安全修补程序可能会使服务器易受安全漏洞破坏。

- 时区更新。

这意味着产品 (不会有进一步的更新、修补程序或修补程序，包括安全修补程序/修复) 。 Microsoft 支持已将其支持工作完全转移到了更新的最新版本。

随着对 SharePoint Server 2010 方法的支持，在升级产品和迁移重要数据之前，请先删除不再需要的数据。

> [!NOTE]
> 软件生命周期通常会在最初发布10年后持续。 [Microsoft 解决方案提供商](https://go.microsoft.com/fwlink/?linkid=841249) 可以帮助您升级到下一个版本的软件或迁移到 Microsoft 365 迁移 (或这两个) 。 确保您了解关键基础技术的支持结束日期，尤其是您在 SharePoint 中使用的 Microsoft SQL Server 版本。 有关详细信息，请参阅 [固定生命周期策略](https://support.microsoft.com/help/14085)。

## <a name="plan-ahead"></a>提前规划

检查 [产品生命周期网站](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010)上支持的结束日期。 请考虑使用这些日期规划升级或迁移。 请注意，你的产品不会在列出的日期 *停止工作* 。 但是，由于在该日期后将不再对安装进行修补，因此您需要规划到产品的下一个版本的平稳过渡。

此矩阵有助于在迁移选项之间绘制课程：

|支持产品的结束|较好 |最好|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (本地) |SharePoint Online|
||SharePoint Server 2013 与 SharePoint Online 的混合|SharePoint Server 2016 (本地) |
|||SharePoint 云混合搜索|

如果您在规模的低端) 选择一个选项 (好的，则在从 SharePoint Server 2010 迁移之后，您需要立即开始规划另一次升级。

若要避免停止 SharePoint Server 2010 支持，可以采用三种途径。

![SharePoint Server 2010 升级路径](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> SharePoint Server 2010 和 SharePoint Foundation 2010 的支持当前计划于4月13日，2021。 但请务必检查 [产品生命周期网站](https://support.microsoft.com/lifecycle) ，了解最新日期。

## <a name="whats-next"></a>下一步做什么？

可以在自己的服务器上的本地安装 SharePoint Server 2013 和 SharePoint Foundation 2013。 或者，您可以使用 SharePoint Online，这是 Microsoft 365 中的一种联机服务。 您可以选择执行以下操作：

- 迁移到 SharePoint Online。

- 本地升级 SharePoint Server 或 SharePoint Foundation。

- 执行上述两项操作。

- 实现 [SharePoint 混合](https://docs.microsoft.com/sharepoint/hybrid/hybrid) 解决方案。

考虑维护服务器场的隐藏成本，包括维护或迁移自定义项以及升级硬件。 如果你已考虑这些因素，则在本地升级会更容易。 如果在未进行大量自定义的旧版 SharePoint 服务器上运行服务器场，则可以从计划迁移到 SharePoint Online 中获益。 对于本地 SharePoint Server 环境，您还可以考虑在 SharePoint Online 中移动一些数据，以减少硬件管理开销。

> [!NOTE]
> SharePoint 管理员可以创建 Microsoft 365 订阅，设置新的 SharePoint Online 网站，然后干净地从 SharePoint Server 2010 中剪切出来，仅将基本文档用于新网站。 然后，任何剩余的数据都可以从 SharePoint Server 2010 网站排出到内部部署存档中。

|SharePoint Online|SharePoint Server 本地|
|---|---|
|高成本的时间 (规划/执行/验证) |高成本的时间 (规划/执行/验证) |
|降低资金成本， (不购买硬件) |资金 (硬件购买时的成本较高) |
|迁移的一次性成本|每次迁移时重复的一次性成本|
|低总拥有成本/维护|高总拥有成本/维护|

在对数据进行组织和确定要执行的操作的过程中，对 Microsoft 365 的一次性移动将会有更高的成本。 但在迁移数据之后，未来的升级将自动进行，因为您不再需要管理硬件和软件更新。 您的服务器场的启动时间将由 [Microsoft 服务级别协议 (SLA) ](https://go.microsoft.com/fwlink/?linkid=843153)支持。

### <a name="migrate-to-sharepoint-online"></a>迁移到 SharePoint Online

确保 SharePoint Online 提供你所需的所有功能。 请参阅 [SharePoint 服务说明](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description)。

您不能直接从 SharePoint Server 2010 (或 SharePoint Foundation 2010) 迁移到 SharePoint Online。 如此多的迁移工作是手动完成的。 但这一阶段让您有机会删除移动前不再需要的数据和网站。 您可以将其他数据存档到存储中。 

请记住，SharePoint Server 2010 和 SharePoint Foundation 2010 在支持结束时不会停止工作。 因此，如果他们的客户忘记移动一些数据，则管理员可能会有一段时间在仍处于运行状态。

如果升级到 SharePoint Server 2013 或 SharePoint Server 2016 并决定将数据放入 SharePoint Online 中，则可以使用 [SharePoint 迁移 API](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) 将信息迁移到 OneDrive for business 中。

|SharePoint Online 优势|SharePoint Online 的缺点|
|---|---|
|Microsoft 提供 SPO 硬件和所有硬件管理。|可用功能在本地 SharePoint Server 和 SPO 之间可能有所不同。|
|你是订阅的全局管理员，并且可以将管理员分配给 SPO 网站。|在 Microsoft 365 中的 SharePoint 管理员角色中，不存在 (或不) 需要在 SharePoint Server 内部部署中的服务器场管理员使用的某些操作。 但 SharePoint 管理、网站集管理和网站所有权对你的组织来说是本地的。|
|Microsoft 对底层硬件和软件应用修补程序、修补程序和更新，包括运行 SharePoint Online 的 SQL server。|由于在服务中没有对基础文件系统的访问权限，因此自定义项受到限制。|
|Microsoft 发布 [服务级别协议](https://go.microsoft.com/fwlink/?linkid=843153) 并快速移动以解决服务级别事件。|SharePoint Online 中的服务将自动执行备份和还原以及其他恢复选项。 如果不使用备份，则将其覆盖。|
|Microsoft 在服务中连续执行安全测试和服务器性能调整。|对用户界面和其他 SharePoint 功能的更改由服务安装，并且可能需要开启或关闭。|
|Microsoft 365 符合多种行业标准： [microsoft 合规性服务](https://go.microsoft.com/fwlink/?linkid=843165)。|迁移的[FastTrack](https://go.microsoft.com/fwlink/?linkid=518597)协助受到限制。  <br/> 大部分升级都是手动进行的，也可以通过 [SharePoint Online 和 OneDrive 迁移内容路线图](https://go.microsoft.com/fwlink/?linkid=843184)中介绍的 SPO 迁移 API 进行。|
|Microsoft 支持工程师和数据中心员工对你的订阅没有无限制的管理员访问权限。|如果需要升级硬件基础结构以支持较新版本的 SharePoint，或者如果升级需要辅助服务器场，则可能会有额外的成本。|
|解决方案提供商可帮助解决将数据迁移到 SharePoint Online 的一次性作业。|并非对 SharePoint Online 所做的所有更改都在您的控制范围内。 迁移之后，菜单、库和其他功能中的设计差异可能会暂时影响可用性。|
|在线产品通过服务自动更新。 功能可能弃用，但不存在真正的支持生命周期的结束。|SharePoint Server 或 SharePoint Foundation 的支持生命周期以及基础 SQL server。|

如果你已决定创建新的 Microsoft 365 网站，并将向其手动迁移数据，请查看你的 [Microsoft 365 选项](https://www.microsoft.com/microsoft-365/)。

### <a name="upgrade-sharepoint-server-on-premises"></a>升级本地 SharePoint Server

从 SharePoint Server 2019 开始，升级必须以  *串行* 方式进行。 没有办法直接从 SharePoint Server 2010 升级到 SharePoint Server 2016 或 SharePoint 2019。 串行升级路径：

- SharePoint Server 2010 sharepoint server \> 2013 \> sharepoint server 2016

将需要一些时间，并计划遵循从 SharePoint 2010 到 SharePoint Server 2016 的完整路径。 升级涉及硬件的成本 (SQL server 也必须升级) 、软件和管理。 此外，自定义项可能需要升级甚至放弃。 在升级 SharePoint Server 服务器场之前，请务必记录关键自定义项。

> [!NOTE]
> 可以维护您的 "支持最终 SharePoint 2010" 服务器场，在新硬件上安装 SharePoint Server 2016 场 (因此，单独的服务器场并行运行) ，然后规划和执行内容 (的手动迁移，以下载和重新上载内容，例如) 。 但是，这些手动移动可能存在缺陷，例如来自2010的文档具有当前上次修改的帐户，该帐户具有手动移动的帐户别名。 且某些工作必须提前完成，如重新创建网站、子网站、权限和列表结构。 请务必在升级之前清理环境。 考虑可以移动到存储或不再需要的数据。 这样可以降低迁移的影响。 请确保你的现有服务器场在升级之前可以正常运行，在停止之前 (肯定) 了！

请记住查看 *支持的和不受支持的升级路径*：

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

如果您具有 *自定义*，则在迁移路径中规划每个步骤至关重要：

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|内部部署优势|本地缺点|
|---|---|
|从服务器硬件上完全控制 SharePoint 场 (及其 SQL) 的所有方面。|所有中断和修复都是贵公司的责任。 但是，如果你的产品尚不支持，你可以接洽 "付费 Microsoft 支持"。|
|SharePoint Server 本地的完整功能集以及通过混合将本地服务器场连接到 SharePoint Online 订阅的选项。|SharePoint Server 及其 SQL 服务器场的升级、修补程序、安全修补程序、硬件升级和所有维护均在本地进行管理。|
|对比 SharePoint Online 更高的自定义选项的完全访问权限。|[Microsoft 合规性产品](https://go.microsoft.com/fwlink/?linkid=843165) 必须在本地手动配置。|
|安全测试和服务器性能调整在您的内部部署下执行。|Microsoft 365 可能会对 SharePoint Online 可用的功能，这些功能不能与本地 SharePoint Server 进行互操作。|
|解决方案提供商可以帮助将数据迁移到 SharePoint Server 的下一个版本 (和) 之外。|您的 SharePoint Server 网站不会自动使用在 SharePoint Online 中显示的 [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) 证书。|
|在本地 SharePoint Server 中完全控制命名约定、备份和还原以及其他恢复选项。|本地 SharePoint Server 对产品生命周期非常敏感。|

### <a name="upgrade-resources"></a>升级资源

首先比较硬件和软件要求。 如果当前环境不符合基本要求，您可能必须先升级服务器场或 SQL server 中的硬件。 

你可以决定将一些网站移动到 SharePoint Online 的 "长绿" 硬件。 完成评估后，请遵循受支持的升级途径和方法。

- *的硬件/软件要求：*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- *的软件边界和限制：*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *以下项的升级过程概述：*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>创建具有 SharePoint Online 和本地 SharePoint Server 的混合解决方案

混合安装程序提供了内部部署和联机状态的最佳，以满足一些迁移需求。 您可以将 SharePoint Server 2013、2016或2019场连接到 SharePoint Online 以创建 SharePoint 混合： [了解 sharepoint 混合解决方案](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)。

如果混合 SharePoint 服务器场是迁移目标，请确定联机移动的网站和用户以及需要在本地进行的操作。 将 SharePoint Server 服务器场内容的排名设为高、中或低对公司的影响有助于做出此决定。 您可能只需要与 SharePoint Online 共享用户帐户的登录名和 SharePoint Server 搜索索引。 但在您查看如何使用您的网站之前，此因素可能并不明确。 如果你的公司后来决定将所有内容迁移到 SharePoint Online，你可以将所有剩余的帐户和数据联机移动，并使你的本地服务器场退役。 从该点开始，SharePoint 场的管理/管理将通过 Microsoft 365 控制台完成。

确保熟悉现有的混合类型，以及如何配置您的本地 SharePoint 场和 Microsoft 365 订阅之间的连接。

|选项|说明|
|---|---|
|[Microsoft 合规性服务](https://go.microsoft.com/fwlink/?linkid=843165)。|迁移的[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)协助受到限制。<br/><br/> 大部分升级都是手动进行的，也可以通过 [SharePoint Online 和 OneDrive 迁移内容路线图](https://go.microsoft.com/fwlink/?linkid=843184)中介绍的 SPO 迁移 API 进行。|
|Microsoft 支持工程师和数据中心员工对你的订阅没有无限制的管理员访问权限。|如果需要升级硬件基础结构以支持较新版本的 SharePoint，或者需要辅助服务器场，则可能会有额外的成本。|
|合作伙伴可协助将数据迁移到 SharePoint Online 的一次性作业。||
|在线产品通过服务自动更新。 功能可能弃用，但不存在真正的支持终止。||

如果您已决定创建一个新的 Microsoft 365 网站，并根据需要手动将数据迁移到该网站，请检查您的 [Microsoft 365 选项](https://www.microsoft.com/microsoft-365/)。

### <a name="upgrade-sharepoint-server-on-premises"></a>升级本地 SharePoint Server

没有办法跳过 SharePoint 升级中的版本。 这意味着升级以串行方式进行：

- SharePoint 2007 \> Sharepoint server 2010 \> sharepoint server 2013 \> sharepoint server 2016

从 SharePoint 2007 到 SharePoint Server 2016 的完整路径意味着需要大量的时间，并将涉及硬件 (SQL server 也必须升级) 、软件和管理成本。 根据功能的关键程度，需要升级或放弃自定义项。

> [!NOTE]
> 可以维护您的生命期结束的 SharePoint 2007 场，将 SharePoint Server 2016 场安装在新的硬件 (，以便单独的服务器场并行运行) ，然后规划和执行内容 (的手动迁移，以下载和重新上载内容，例如) 。 但这些手动移动存在一些缺陷，例如，文档移动将上次修改的帐户替换为手动移动的帐户别名。 必须提前完成大量工作，如重新创建网站、子网站、权限和列表结构。 在任何情况下，请考虑可以移动到存储中的数据，或者不再需要减少迁移的影响。

请确保在升级之前清理环境。 一定要确保现有服务器场在升级之前正常运行，当然不应在停止之前运行！

请记住查看 *支持的和不受支持的升级路径*：

- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

如果您具有 *自定义项*，则在迁移路径中为每个步骤规划升级至关重要：

- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|本地 pro|本地 con|
|---|---|
|从服务器硬件上完全控制 SharePoint 场的各个方面。|所有中断和修复都是贵公司的责任。  (但如果你的产品尚不支持，你可以与付费 Microsoft 支持人员接洽。 ) |
|SharePoint Server 本地的完整功能集以及通过混合将本地服务器场连接到 SharePoint Online 订阅的选项。|在本地托管的 SharePoint Server 的升级、修补程序、安全修补程序和所有维护。|
|完全访问权限以进行更好的自定义。|[Microsoft 合规性产品](https://go.microsoft.com/fwlink/?linkid=843165) 必须在本地手动配置。|
|在您的内部部署中执行安全测试和服务器性能调整。|Microsoft 365 可能会对 SharePoint Online 可用的功能，这些功能不能与本地 SharePoint Server 进行互操作。|
|合作伙伴可以帮助将数据迁移到 SharePoint Server 的下一个版本 (和) 之外。|您的 SharePoint Server 网站不会自动使用在 SharePoint Online 中显示的 [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) 证书。|
|在本地 SharePoint Server 中完全控制命名约定、备份和还原以及其他恢复选项。|本地 SharePoint Server 对产品生命周期非常敏感。|

### <a name="upgrade-resources"></a>升级资源

先知道您是否满足硬件和软件要求，然后再遵循受支持的升级方法。

- *的硬件/软件要求*：

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- *的软件边界和限制*：

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- 以下项 *的升级过程概述*：

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>在 SharePoint Online 和本地部署之间创建 SharePoint 混合解决方案

如果迁移的答案需要在本地提供的控件与 SharePoint Online 提供的更低的所有权之间，则可以通过混合将 SharePoint Server 2013 或2016场连接到 SharePoint Online。 [了解 SharePoint 混合解决方案](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

如果你确定混合 SharePoint 服务器场将对你的业务有益，请熟悉现有的混合类型，以及如何配置你的本地 SharePoint 场和 Microsoft 365 订阅之间的连接。

您可能需要创建 Microsoft 365 开发/测试环境，您可以使用 [测试实验室指南](m365-enterprise-test-lab-guides.md)对其进行设置。 在获取试用版或购买的 Microsoft 365 订阅后，可以在 SharePoint Online 中创建可将数据迁移到的网站集、web 和文档库。 您可以通过使用迁移 API 手动迁移，或者如果要通过混合向导将我的网站内容迁移到 OneDrive for business，则可以进行手动迁移。

> [!NOTE]
> 若要使用 "混合" 选项，您的 SharePoint Server 2010 服务器场必须先在本地升级到 SharePoint Server 2013 或2016。 SharePoint Foundation 2010 和 SharePoint Foundation 2013 不支持与 SharePoint Online 的混合连接。

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Office 2010 客户端和服务器以及 Windows 7 的选项的摘要

有关 Office 2010 客户端和服务器以及 Windows 7 的升级、迁移和移动到云选项的直观摘要，请参阅[终止支持海报](../downloads/Office2010Windows7EndOfSupport.pdf)。

[![对 Office 2010 客户端和服务器和 Windows 7 海报的支持结束](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

此海报说明了您可以采取的各种途径以避免 Office 2010 客户端和服务器产品和 Windows 7 的支持，并突出显示了 Microsoft 365 企业版中的首选路径和选项支持。

您还可以 [下载](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) 此海报并在信件、法律或 tabloid (11 x 17) 格式打印它。

## <a name="related-articles"></a>相关文章

[可帮助您从 Office 2007 或2010服务器和客户端进行升级的资源](upgrade-from-office-2010-servers-and-products.md)

[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](https://technet.microsoft.com/library/mt493301%28v=office.16%29.aspx)

[从 SharePoint 2010 升级到 SharePoint 2013 的最佳做法](https://technet.microsoft.com/library/mt493305%28v=office.16%29.aspx)

[在 SharePoint 2013 中解决数据库升级问题](https://go.microsoft.com/fwlink/?linkid=843195)

[搜索 Microsoft 解决方案提供商以帮助你进行升级](https://go.microsoft.com/fwlink/?linkid=841249)

[SharePoint 2013 的更新产品服务策略](https://technet.microsoft.com/library/mt493253%28v=office.16%29.aspx)

[SharePoint Server 2016 的更新产品服务策略](https://technet.microsoft.com/library/mt782882%28v=office.16%29.aspx)
