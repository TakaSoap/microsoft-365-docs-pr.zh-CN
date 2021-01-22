---
title: 从德国 Microsoft 云进行迁移的前期工作
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/18/2020
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
description: 摘要：从德国 Microsoft 云 (德国) 迁移到新的德国数据中心区域中的 Office 365 服务时，工作前工作。
ms.openlocfilehash: cd32ce21e18b16660c4292c98ebcc0f7cb982173
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921562"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>从德国 Microsoft 云进行迁移的前期工作


使用这些链接可了解与组织相关的工作前步骤：

- 对于所有订阅，请 [执行以下步骤](#applies-to-everyone)。
- 如果使用的是 Exchange Online 或 Exchange 混合，请 [执行此步骤](#exchange-online)。
- 如果使用的是 SharePoint Online，请 [执行此步骤](#sharepoint-online)。
- 如果你使用 MDM 解决方案的第三方移动设备 (，) [执行此步骤](#mobile)。
- 如果你使用的是第三方服务或业务线 (LOB) 与 Office 365 集成的应用，请 [执行此步骤](#line-of-business-apps)。
- 如果你还使用除 Office 365 订阅中包含的服务之外的 Azure 服务，请 [执行此步骤](#azure)。
- 如果你还使用 Dynamics 365，请 [执行此步骤](#dynamics365)。
- 如果你还使用 Power BI，请 [执行此步骤](#power-bi)。
- 对于 DNS 更改，请 [执行此步骤](#dns)。
- 如果使用的是联合身份，请 [执行以下步骤](#federated-identity)。

## <a name="applies-to-everyone"></a>适用于所有人

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 确保与 [Office 365 服务 URL 和 IP 地址的网络连接](https://aka.ms/o365urls)。 | 客户托管用于访问 Office 365 服务的所有客户端和服务都必须能够访问 Office 365 服务终结点。 | 所有转换客户以及网络访问权限仅限于德国 Microsoft 云的客户。 | 必需操作。 不操作可能会导致服务或客户端软件出现故障。 |
| 查看并准备与迁移相关的 DNS 更改。 | 客户为 Exchange Online 和 Exchange Online Protection (MX 记录等准备 DNS ) 。 | Exchange Online 客户 | 这是建议的操作。 任何操作都意味着迁移的客户的电子邮件可能通过 Microsoft 云德国路由，直到 Microsoft 云德国服务被禁用。 |
| 查看并准备与迁移相关的 DNS 更改。 | Skype for Business Online 的客户拥有的 DNS 区域更改。 | Skype For Business Online 客户 | - 建议将任何客户拥有的域 DNS 记录的生存时间 (TTL) 更新为 5 分钟，以加快 DNS 记录的刷新。 但是，与此 DNS 更改关联的 Microsoft 管理的转换可能会随时在提供的 24 小时更改时段内发生。 <br><br> - 将来可能会中断服务。 用户将无法登录 Skype for Business，并且将被重定向到 Office 365 服务中迁移的 Teams 体验。 |
| 准备最终用户和管理培训和准备过渡到 Microsoft Teams。 | 通过规划用户通信和准备情况，成功从 Skype 过渡到 Teams。 | Skype For Business Online 客户 | - 客户端需要了解新服务及其在转换为 Office 365 服务后如何使用。 <br><br> - 在客户虚域和初始域都进行了 DNS 更改后，用户将登录到 Skype for Business，并查看他们现在已迁移到 Teams。 这还会在后台下载 Teams 的桌面客户端。 |
| 准备最终用户和管理培训，以便用户删除其帐户并重新添加到 Microsoft Outlook for iOS 和 Outlook for Android。 | 使用德国 Microsoft 云中的邮箱配置的 Microsoft Outlook for iOS 和 Android 帐户可能需要删除并再次添加到 Outlook，才能正确同步新的 Office 365 服务配置。 | Microsoft Outlook for iOS 和 Android 客户 | 以前为德国 Microsoft 云配置的 Outlook 邮箱可能不会选取新的 Office 365 服务配置，从而导致其他用户体验的错误和性能降低。 如果迁移后出现登录或同步邮件的问题，建议 IT 管理员提供主动指示用户删除帐户，并将其添加到 Microsoft Outlook for iOS 和 Outlook for Android 的文档。 |
| 准备通知用户在迁移后重新启动和登录客户端以及登录和退出客户端。 | 在迁移过程中，Office 客户端许可将从 Microsoft 云德国转换为 Office 365 服务。 客户端在登录 Office 客户端和登录 Office 客户端后获取新的有效许可证。 | Microsoft 365 应用版客户 |  用户的 Office 产品需要刷新 Office 365 服务中的许可证。 如果未刷新许可证，Office 产品可能会遇到许可证验证错误。 |
| 取消任何试用订阅。 | 试用版订阅将不会迁移，并且将阻止付费订阅的转移。 | 所有客户 | 如果取消后用户访问试用版服务，则试用服务已过期且无法正常工作。 |
| 为在德国访问 Skype for Business 的用户部署 Teams 桌面客户端。 | 迁移将用户移至 Teams 进行协作、通话和聊天。 部署 Teams 桌面客户端或确保受支持的浏览器可用。 | Skype for Business 客户 | 不操作将导致 Teams 协作服务不可用。 |
| 分析 Microsoft 云德国与 Office 365 服务之间的许可证功能差异。 | Office 365 服务包括当前 Microsoft 云德国中不可用的其他功能和服务。 在订阅转移期间，用户可以使用新功能。 | 所有客户 | - 分析 Microsoft 云德国和 Office 365 服务的许可证提供的不同功能。 从 [Office 365 平台服务说明开始](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)。 <br><br> - 确定是否应最初禁用 Office 365 服务的任何新功能，以限制对用户或用户更改管理的影响，并根据需要更改用户许可证分配。 <br><br> - 为用户和技术支持人员准备 Office 365 服务提供的新服务和功能。 |
| 创建组织范围的 [保留策略](https://docs.microsoft.com/microsoft-365/compliance/retention) ，防止在迁移过程中意外删除内容。  | - 为了确保迁移过程中最终用户不会无意中删除内容，客户可以选择启用组织范围的保留策略。 <br><br> - 尽管不需要保留，但因为迁移期间随时放置的保留应按预期工作，但保留策略是一种备份安全机制。 同时，保留策略可能不会由所有客户使用，特别是关注保留的客户。 | Office 客户 | 应用保留策略，如 [了解保留策略和保留标签中所述](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)。 |
| [针对灾难恢复方案的 Active Directory 联合身份验证服务 (AD FS) ](ms-cloud-germany-transition-add-adfs.md#backup) 服务器场的备份。 | 客户需要适当地备份 AD FS 场，以确保可以在不接触域的颁发者 URI 的情况下还原对全局 & Germany 终结点的信赖方信任。 如有必要，Microsoft 建议使用 AD FS 快速还原来备份服务器场和相应的还原。 | 联合身份验证组织 | 必需操作。 如果客户的 AD FS 场失败，则不操作将导致迁移期间的服务影响。 |


## <a name="exchange-online"></a>Exchange Online

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 通知外部合作伙伴即将过渡到 Office 365 服务。 | 可用性地址空间配置允许与 Office 365 共享忙/闲信息。 | 已启用共享日历和可用性地址空间的 Exchange Online 客户。 | 必需操作。  如果不这样做，可能会导致客户迁移的稍后阶段出现服务或客户端故障。 |
|||||

<!--
Reworked as text:

**Step:** Notify external partners of the upcoming transition to Office 365 services.

**Description:** Availability address space configurations allow sharing of free/busy information with Office 365. | Exchange Online customers who have enabled sharing calendar and availability address space.

**Applies to:** Exchange Online customers who have enabled sharing calendar and availability address space.

**Impact:** Required action.  Failure to do so may result in service or client failure at a later phase of customer migration.

- **Step:** Notify external partners of the upcoming transition to Office 365 services.

- **Description:** Availability address space configurations allow sharing of free/busy information with Office 365. | Exchange Online customers who have enabled sharing calendar and availability address space.

- **Applies to:** Exchange Online customers who have enabled sharing calendar and availability address space.

- **Impact:** Required action.  Failure to do so may result in service or client failure at a later phase of customer migration.

--> 


### <a name="for-hybrid-exchange"></a>对于混合 Exchange

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 卸载以前版本的混合配置向导 (HCW) ，然后从安装并执行最新版本 17.0.5378.0。 [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) | HCW 的最新版本包括必要的更新，以支持从德国 Microsoft 云过渡到 Office 365 服务的客户。 <br><br> 更新包括对发送连接器和接收连接器本地证书设置的更改。 | 运行混合部署的 Exchange Online 客户 | 必需操作。 否则可能会导致服务或客户端失败。 |
|||||

<!--
Reworked as text:

**Step:** Uninstall previous versions of Hybrid Configuration wizard (HCW), and then install and execute the latest version, 17.0.5378.0, from [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard).

**Description:** The latest version of the HCW includes necessary updates to support customers who are transitioning from Microsoft Cloud Deutschland to Office 365 Services. <br><br> Updates include changes to on-premises certificate settings for Send connector and Receive connector.

**Applies to:** Exchange Online customers running Hybrid deployment

**Impact:** Required action. Failure to do so may result in service or client failure.
-->


## <a name="sharepoint-online"></a>SharePoint Online

如果你有 SharePoint 2013：

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 限制 SharePoint 2013 工作流，在 SharePoint Online 迁移过程中使用。 | 在转换之前减少 SharePoint 2013 工作流并完成运行中的工作流。 | SharePoint Online 客户 | 不操作可能会导致用户混淆和技术支持呼叫。 |
|||||

## <a name="mobile"></a>移动版

如果你在 MDM 解决方案中 (第三方) 管理：

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 确定迁移后是否要求任何重新配置。 | MDM 解决方案可能面向 `outlook.de` 终结点。 在此到 Office 365 服务的转换中，客户端配置文件应更新为 Office 365 服务 `outlook.office365.com` URL。 | Exchange Online 和 MDM 客户 | 当终结点可访问时，客户端可能会继续运行，但如果 Microsoft 云德国终结点不再可用，客户端 `outlook.de` 将失败。 |
|||||

## <a name="line-of-business-apps"></a>业务线应用

如果你使用的是第三方服务或业务线 (与 Office 365) LOB 应用： 

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 确定迁移后是否要求任何重新配置。 | 与 Office 365 集成的第三方服务和应用程序可能编码为 Microsoft 云德国 IP 地址和 URL。 | 所有客户 | 必需操作。 不操作可能会导致服务或客户端软件出现故障。 |
|||||

## <a name="azure"></a>Azure 

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 通过与合作伙伴合作，确定使用哪些 Azure 服务并准备将来从德国迁移到 Office 365 服务租户。 按照 Azure 迁移操作手册 [中所述的步骤操作](https://docs.microsoft.com/azure/germany/germany-migration-main)。 | Azure 资源的迁移是客户的责任，需要按照规定步骤手动完成。 了解组织中使用的服务是成功迁移 Azure 服务的关键。 <br><br> 如果 Office 365 Germany 客户拥有同一标识分区 (组织) 必须按照 Microsoft 规定的顺序开始订阅和服务迁移。 | Azure 客户 | - 客户可能有多个 Azure 订阅，每个订阅包含基础结构、服务和平台组件。 <br><br> - 管理员应确定订阅和利益干系人，以确保作为此迁移事件的一部分进行快速迁移和验证。 <br><br> 未能在规定时间线内成功完成这些订阅和 Azure 组件的迁移将影响 Office 和 Azure AD 到 Office 365 服务的转换完成，并可能导致数据丢失。  <br><br> - 消息中心通知将指示客户引导迁移可以开始的点。 |
|||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](https://docs.microsoft.com/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. 

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:** 

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. 
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

## <a name="dynamics-365"></a>Dynamics 365

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 对于 Dynamics 365 沙盒订阅，请务必从 Microsoft 云德国的 Dynamics 365 订阅下载 Dynamics SQL 实例的生产环境。 应在沙盒迁移之前将最新的生产备份还原到沙盒。 | Dynamics 365 的迁移要求客户确保使用最新的生产数据库刷新沙盒环境。 | Microsoft Dynamics 客户 | FastTrack 团队将帮助客户执行干运行，以验证版本从 8.x 升级到 9.1.x。 |
|||||

## <a name="power-bi"></a>Power BI

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 从 Power BI 订阅删除不会从 Power BI Microsoft 云德国迁移到 Office 365 服务的对象。 | 迁移 Power BI 服务需要客户操作来删除某些项目，如数据集和仪表板。 | Power BI 客户 | 管理员可能必须删除其订阅中的以下项目： <br> - Real-Time数据集 (，例如流式处理或推送)  <br> - Power BI 本地数据网关配置和数据源 |
|||||

## <a name="dns"></a>DNS

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 如果在 Azure AD 剪切之前随时存在 MSOID 和 CName，请从客户拥有的 DNS 中删除它。 可以设置 5 分钟的 TTL，以便更改可以快速生效。 | 客户拥有的 DNS 区域更改 | Office 客户端服务客户 | 
|||||

## <a name="federated-identity"></a>联合身份

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 向现有信赖方信任 (SSO) 单一登录的标识符，并禁用 AD FS 元数据自动更新。 | 在开始迁移之前，必须将 ID 添加到 AD FS 信赖方信任中。 为了避免意外删除信赖方标识符，请禁用元数据更新的自动更新。 <br><br> 在 AD FS 服务器上运行此命令： <br> `Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de','https://login.microsoftonline.de/extSTS.srf','https://login.microsoftonline.de') -AutoUpdate $False` | 联合身份验证组织 | 必需操作。 Inaction will result in service impact during the migration.  |
| 为全局 Azure AD 终结点生成信赖方信任。 | 客户需要手动创建依赖方信任 (RPT) [到全局](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) 终结点。 这是通过 GUI 添加新的 RPT，方法为利用全局联合元数据 URL，然后使用 AD FS 帮助) 中的 [Azure AD RPT](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) 声明规则 (生成声明规则，然后将它们导入 RPT。 | 联合身份验证组织 | 必需操作。 Inaction will result in service impact during the migration. |
|||||

## <a name="more-information"></a>更多信息

入门：

- [从德国 Microsoft 云迁移到新的德国数据中心区域的 Office 365 服务](ms-cloud-germany-transition.md)
- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)
- [迁移期间客户体验](ms-cloud-germany-transition-experience.md)

在转换过程中移动：

- [迁移阶段操作和影响](ms-cloud-germany-transition-phases.md)
- [其他预工作](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。

云应用：

- [Dynamics 365 迁移计划信息](https://aka.ms/d365ceoptin)
- [Power BI 迁移计划信息](https://aka.ms/pbioptin)
- [开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)
