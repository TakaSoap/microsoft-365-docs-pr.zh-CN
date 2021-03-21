---
title: 从德国 Microsoft 云进行迁移的前期工作
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/09/2021
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：从德国 Microsoft 云 (德国) 迁移到新的德国数据中心区域中的 Office 365 服务时，需要提前工作。
ms.openlocfilehash: 37fde0119dfc84cbe9120cf922cbac469a0a50f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923834"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>从德国 Microsoft 云进行迁移的前期工作

使用这些链接可了解与组织相关的预工作步骤：

- 对于在 Microsoft 云德国使用 Office 365 的所有客户，请 [执行以下步骤](#applies-to-everyone)。
- 如果使用的是 Exchange Online 或 Exchange 混合，请 [执行此步骤](#exchange-online)。
- 如果使用的是 SharePoint Online，请 [执行此步骤](#sharepoint-online)。
- 如果你使用 MDM 解决方案的第三方移动设备 (，) 执行 [此步骤](#mobile)。
- 如果你使用的是与 Office 365 集成的第三方服务或业务线 (LOB) ，请执行 [此步骤](#line-of-business-apps)。
- 如果你使用的是除 Office 365 订阅中包含的服务之外的 Azure 服务，请 [执行此步骤](#microsoft-azure)。
- 如果你还使用 Dynamics 365，请 [执行此步骤](#dynamics365)。
- 如果你还使用 Power BI，请 [执行此步骤](#power-bi)。
- 对于 DNS 更改，请 [执行此步骤](#dns)。
- 如果使用的是联合身份，请 [执行以下步骤](#federated-identity)。

## <a name="applies-to-everyone"></a>适用于所有人

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 准备通知用户迁移后重启客户端并登录和退出客户端。 | 迁移过程中，Office 客户端许可将从德国 Microsoft 云转换为 Office 365 服务。 客户端在退出并登录 Office 客户端后获取新的有效许可证。 | 用户的 Office 产品需要刷新 Office 365 服务中的许可证。 如果未刷新许可证，Office 产品可能会遇到许可证验证错误。 |
| 确保与 [Office 365 服务 URL 和 IP 地址的网络连接](./urls-and-ip-address-ranges.md)。 | 客户托管用于访问 Office 365 服务的所有客户端和服务都必须能够访问 Office 365 全局服务终结点。 <br>在这种情况下，你或你的协作伙伴已制定防火墙规则，以阻止访问 [Office 365](./urls-and-ip-address-ranges.md) 服务 URL 中列出的 URL 和 IP 地址，并且 IP 地址必须更改防火墙规则，以允许访问 Office 365 全局服务终结点| 如果未在阶段 4 之前完成此操作，则可能会发生服务或客户端软件故障  |
| 取消任何试用订阅。 | 试用版订阅将不会迁移，并且将阻止传输付费订阅。 | 如果取消后用户访问试用服务，则试用服务已过期且无法正常工作。 |
| 分析德国 Microsoft 云与 Office 365 服务之间的许可证功能差异。 | Office 365 服务包括当前德国 Microsoft 云中不可用的其他功能和服务。 在订阅转移期间，用户可以使用新功能。 | <ul><li> 分析 Microsoft 云德国和 Office 365 服务的许可证提供的不同功能。 从 Office [365 平台服务说明开始](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)。 </li><li> 确定是否应最初禁用 Office 365 服务的任何新功能，以限制对用户或用户更改管理的影响，并根据需要更改用户许可证分配。 </li><li>为用户和技术支持人员准备 Office 365 服务提供的新服务和功能。 |
| 创建组织范围的 [保留策略](../compliance/retention.md) ，防止在迁移过程中意外删除内容。  |<ul><li>为确保最终用户不会在迁移过程中意外删除内容，客户可以选择启用组织范围的保留策略。 </li><li>尽管不需要保留，因为迁移过程中随时设置保留应按预期工作，但保留策略是一种备份安全机制。 同时，保留策略可能不会由所有客户使用，尤其是关注保留的客户。</li></ul>| 应用保留策略，如 [了解保留策略和保留标签中所述](../compliance/retention.md)。 如果未在阶段 4/9 之前完成此操作，则可能会发生服务或客户端软件故障。 </li></ul>|
| 正确的许可证过度使用 | 在某些情况下，客户可能能够使用比购买的服务更多的服务。 此条件称为许可证过度使用。 Microsoft 无法将许可证过度使用条件的客户从德国 Microsoft 云迁移到德国数据中心区域。 为了确保对服务和数据的持续访问，每个分配的用户都需要许可证。 | 所有客户 | 客户必须通过购买其他许可证或取消分配用户许可证来评估和解决许可证过度分配情况。 |
|||||

## <a name="active-directory-federation-services-ad-fs"></a>Active Directory 联合身份验证服务 (AD FS)

**适用于：** 使用本地 AD FS 验证连接到 Microsoft Office 365 的用户的客户

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| [针对灾难恢复方案的 Active Directory 联合身份验证 (AD FS) ](ms-cloud-germany-transition-add-adfs.md#backup) 备份。 | 客户需要适当地备份 AD FS 场，以确保可以还原对全局 & Germany 终结点的信赖方信任，而不会接触域的颁发者 URI。 如有必要，Microsoft 建议使用 AD FS 快速还原来备份服务器场和相应的还原。 | 必需操作。 如果客户的 AD FS 场失败，则 Inaction 将导致迁移期间的服务影响。 有关详细信息，请参阅 [ADFS 迁移步骤](./ms-cloud-germany-transition-add-adfs.md) |
||||

## <a name="exchange-online"></a>Exchange Online

**适用于：** 已启用共享日历和可用性地址空间的 Exchange Online 客户。

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 通知外部合作伙伴即将过渡到 Office 365 服务。 | 可用性地址空间配置允许与 Office 365 共享忙/闲信息。 | 如果不这样做，可能会导致客户迁移的稍后阶段出现服务或客户端故障。 |
|||||

### <a name="exchange-online-hybrid-configuration"></a>Exchange Online 混合配置

**适用于：** 具有活动 Exchange 混合配置的 Exchange Online 客户

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 在租户进入迁移阶段 5 之前 (更新到最新版本的混合配置向导 (HCW) 。 你可以在收到消息中心通知 Office 365 租户迁移已开始后立即启动此活动。<br><br> Microsoft Cloud Deutschland hybrid Exchange Online customers must uninstall previous versions of HCW， and then install and execute the latest version (17.0.5378.0 or higher) from [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) . |<ul><li>HCW 的最新版本包括必要的更新，以支持从德国 Microsoft 云过渡到 Office 365 服务的客户。</li><li> 更新包括更改发送连接器和接收连接器本地证书设置。</li><li> Exchange 管理员必须在第 5 阶段（9 月 9 日）开始前随时重新安装 HCW (Exchange) 迁移。<br>在阶段 5 之前执行 HCW 时，在"Office _365 Exchange Online"_ 下 HCW 的第 2 页中选择"Office 365 Germany"，在"我的 Office 365 组织"下的列表框中选择  _"Office 365 Germany"，_</li><li>**注意**：完成 Office 365 租户迁移后，将再次删除并重新安装 HCW，这次使用 HCW 第 2 页上的"Office 365 全球"设置，通过 Exchange Online 全局服务完成混合设置。</li></ul>|在 Exchange 迁移迁移阶段 5 之前 (HCW) 可能会导致服务或客户端故障。 |
||||

## <a name="sharepoint-online"></a>SharePoint Online

**适用于：** 在本地使用 SharePoint 2013 的客户


| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 限制 SharePoint 2013 工作流，在 SharePoint Online 迁移过程中使用。 | 在转换之前减少 SharePoint 2013 工作流并完成运行中的工作流。 | 不操作可能会导致用户混淆和技术支持呼叫。 |
||||

## <a name="skype-for-business-online"></a>Skype for Business Online

**适用于：Skype** For Business Online 客户

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 为在德国访问 Skype for Business 的用户部署 Teams 桌面客户端。 | 迁移将 Skype for Business 用户移至 Microsoft Teams 进行协作、通话和聊天。 部署 Microsoft Teams 桌面客户端或确保受支持的浏览器可用。 | 不操作将导致 Microsoft Teams 协作服务不可用。 |
| 查看并准备与迁移相关的 DNS 更改。 | Skype for Business Online 的客户拥有的 DNS 区域更改。 |<ul><li>建议将任何客户拥有的域 DNS 记录的生存时间 (TTL) 更新为 5 分钟，以加快 DNS 记录的刷新。 但是，与此 DNS 更改关联的 Microsoft 管理的转换可能在提供的 24 小时更改时段内随时发生。 </li><li>未来可能会中断服务。 用户将无法登录 Skype for Business，并重定向到 Office 365 服务中迁移的 Teams 体验。 </li></ul>|
| 准备最终用户和管理培训和准备过渡到 Microsoft Teams。 | 通过规划用户沟通和准备情况，成功从 Skype 过渡到 Teams。 | <ul><li>客户端需要了解新服务，以及一旦其服务转换到 Office 365 服务后如何使用。 </li><li>在客户虚域和初始域都进行了 DNS 更改后，用户将登录到 Skype for Business，并看到他们现在已迁移到 Teams。 这还会在后台下载 Teams 桌面客户端。 </li></ul>|
||||

## <a name="mobile"></a>移动版

如果你使用 MDM 解决方案的第三方移动设备 () 解决方案：

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 准备最终用户和管理培训，了解用户删除帐户并重新将其帐户添加到 Microsoft Outlook for iOS 和 Outlook for Android。 | 使用德国 Microsoft 云中的邮箱配置的 Microsoft Outlook for iOS 和 Android 帐户可能需要删除并再次添加到 Outlook，才能正确同步新的 Office 365 服务配置。 | Microsoft Outlook for iOS 和 Android 客户 | 以前为德国 Microsoft 云配置的 Outlook 邮箱可能不会选取新的 Office 365 服务配置，从而导致其他用户体验的错误和性能下降。 如果迁移后出现登录或同步邮件的问题，建议 IT 管理员提供文档，以主动指示用户删除帐户，并将其添加到 Microsoft Outlook for iOS 和 Outlook for Android。 |
| 确定迁移后是否要求任何重新配置。 | 移动设备管理 (MDM) 解决方案可能面向 `outlook.de` 终结点。 在此到 Office 365 服务的转换中，客户端配置文件应更新为 Office 365 服务 `outlook.office365.com` URL。 | Exchange Online 和 MDM 客户 | 当终结点可访问时，客户端可能会继续运行，但如果 Microsoft 云德国终结点不再可用，客户端将 `outlook.de` 失败。 |
|||||

## <a name="line-of-business-apps"></a>业务线应用

如果你使用的是第三方服务或业务线 (与 Office 365) LOB 应用： 

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 确定迁移后是否要求任何重新配置。 | 与 Office 365 集成的第三方服务和应用程序可能编码为预期 Microsoft 云德国 IP 地址和 URL。 | 必需操作。 不操作可能会导致服务或客户端软件失败。 |
||||

## <a name="dynamics-365"></a>Dynamics 365

**适用于：** 使用 Microsoft Dynamics 的客户

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 对于 Dynamics 365 沙盒订阅，请务必从 Microsoft 云德国的 Dynamics 365 订阅下载 Dynamics SQL 实例的生产环境。 应在沙盒迁移之前将最新的生产备份还原到沙盒。 | Dynamics 365 的迁移要求客户确保使用最新的生产数据库刷新沙盒环境。 | FastTrack 团队将帮助客户执行干运行，以验证版本从 8.x 升级到 9.1.x。 |
||||

## <a name="power-bi"></a>Power BI

**适用于 ：** Power BI 客户 

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 从 Power BI 订阅删除不会从 Power BI Microsoft 云德国迁移到 Office 365 服务的对象。 | Power BI 服务的迁移需要客户操作来删除某些项目，如数据集和仪表板。 | <ul><li>管理员可能必须删除其订阅中的以下项目： </li><li>Real-Time数据集 (，例如流式处理或推送)  </li><li>Power BI 本地数据网关配置和数据源 </li></ul>|
||||

## <a name="dns"></a>DNS

**适用于**：使用 Office 桌面客户端 (Microsoft 365 应用版、Office 365 专业增强版、Office 2019、2016、...) <br>
在 Azure Active Directory (Azure AD 之前随时从客户拥有的 DNS) CName。 可以设置 5 分钟的 TTL，以便更改可以快速生效。

## <a name="federated-identity"></a>联合身份

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 向现有信赖方信任 (SSO) 单一登录的标识符，并禁用 AD FS 元数据自动更新。 | 在开始迁移之前，必须将 ID 添加到 AD FS 信赖方信任中。 为了避免意外删除信赖方标识符，请禁用元数据更新的自动更新。 <br><br> 在 AD FS 服务器上，将此命令作为单个命令行运行： <br>`Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de', 'https://login.microsoftonline.de/extSTS.srf', 'https://login.microsoftonline.de') -AutoUpdate $False`
| 联合身份验证组织 | 必需操作。 在 SharePoint 9 (阶段 4 之前) 操作将导致迁移期间的服务影响。  |
| 为全局 Azure AD 终结点生成信赖方信任。 | 客户需要手动创建依赖方信任 (RPT) [全局](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) 终结点。 这是通过 GUI 添加新的 RPT，从而利用全局联合元数据 URL，然后使用 AD FS 帮助) 中的 [Azure AD RPT](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) 声明规则 (生成声明规则并导入到 RPT 中来完成此操作。 | 联合身份验证组织 | 必需操作。 Inaction will result in service impact during the migration. |
|||||

## <a name="microsoft-azure"></a>Microsoft Azure

如果你正在为德国 Microsoft 云实例中的 Office 365 和 Microsoft Azure 使用相同的 Azure Active Directory 标识分区，请确保你正在准备客户驱动的 Microsoft Azure 服务迁移。
在 Office 365 租户进入迁移阶段 3 之前，不得启动 Microsoft Azure 服务的迁移，并且必须在迁移阶段 8 完成之前完成迁移。

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 通过与合作伙伴合作，确定使用哪些 Azure 服务，并准备将来从德国迁移到 Office 365 服务租户。 按照 Azure 迁移操作手册 [中所述的步骤操作](/azure/germany/germany-migration-main)。 |<ul><li>Azure 资源的迁移是客户的责任，需要按照规定步骤执行手动操作。 了解组织中使用的服务是成功迁移 Azure 服务的关键。 </li><li> 在组织 (组织) 下拥有 Azure 订阅的 Office 365 Germany 客户在可以开始订阅和服务迁移时必须遵循 Microsoft 规定的顺序。</li></ul>|<ul><li>客户可能有多个 Azure 订阅，每个订阅包含基础结构、服务和平台组件。 </li><li> 管理员应确定订阅和利益干系人，以确保作为此迁移事件的一部分，可以进行快速迁移和验证。 </li><li>未能成功完成这些订阅和 Azure 组件在规定时间线内的迁移将影响 Office 和 Azure AD 到 Office 365 服务的转换完成，并可能导致数据丢失。 </li><li> 消息中心通知将指示客户引导的迁移可以开始的时间点。 </li></ul>|
||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. 

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:** 

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. 
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

## <a name="more-information"></a>更多信息

入门：

- [从德国 Microsoft 云迁移到新的德国数据中心区域的 Office 365 服务](ms-cloud-germany-transition.md)
- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)
- [迁移期间客户体验](ms-cloud-germany-transition-experience.md)

在转换过程中移动：

- [迁移阶段操作和影响](ms-cloud-germany-transition-phases.md)
- [其他前期工作](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。

云应用：

- [Dynamics 365 迁移计划信息](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 迁移计划信息](/power-bi/admin/service-admin-migrate-data-germany)
- [开始 Microsoft Teams 升级](/microsoftteams/upgrade-start-here)