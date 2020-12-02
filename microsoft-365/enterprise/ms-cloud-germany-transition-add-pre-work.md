---
title: 从 Microsoft 云德国迁移的其他预备工作信息
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: 摘要：从 Microsoft (云) 德国移动到新的德国数据中心区域中的 Office 365 服务时，其他预备工作信息。
ms.openlocfilehash: 41953aa9d91faa91bd983fbbc8d93baf08c172ed
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551703"
---
# <a name="additional-pre-work-information-for-the-migration-from-microsoft-cloud-deutschland"></a>从 Microsoft 云德国迁移的其他预备工作信息

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 确保与 [Office 365 服务 url 和 IP 地址](https://aka.ms/o365urls)的网络连接。 | 由客户托管的用于访问 Office 365 服务的所有客户端和服务必须能够访问 Office 365 服务终结点。 | 所有正在转换的客户和网络访问限制为 Microsoft 云德国的客户。 | 必需的操作。 Inaction 可能会导致服务或客户端软件出现故障。 |
| 查看并准备迁移相关的 DNS 更改。 | Customer 为 Exchange Online 和 Exchange Online Protection (MX 记录等 DNS 条目做准备 ) 。 | Exchange Online 客户 | 这是建议的操作。 无操作意味着迁移客户的电子邮件可能通过 Microsoft 云德国路由，直到 Microsoft 云德国服务被禁用。 |
| 查看并准备迁移相关的 DNS 更改。 | 对 Skype for business Online 的客户拥有的 DNS 区域更改。 | Skype For Business Online 客户 | -建议您将任何客户拥有的域 DNS 记录的生存时间 (TTL) 更新为5分钟，以加快 DNS 记录的刷新。 但是，与此 DNS 更改关联的 Microsoft 托管转换可能会在所提供的24小时更改窗口中随时发生。 <br><br> -将来可能会中断服务。 用户将无法登录到 Skype for Business，并将重定向到 Office 365 服务中的已迁移团队体验。 |
| 准备最终用户和管理培训以及准备迁移到 Microsoft 团队。 | 通过规划用户通信和准备情况，从 Skype 到团队的过渡成功。 | Skype For Business Online 客户 | -客户端需要了解新服务以及如何在将其服务转换为 Office 365 服务时使用。 <br><br> -在对客户虚域和初始域进行 DNS 更改之后，用户将登录到 Skype for Business，并查看它们现在是否已迁移到团队。 这也会在后台为工作组下载桌面客户端。 |
| 准备最终用户和管理培训，了解如何将用户的帐户删除并重新添加到 Microsoft Outlook for iOS 和 Outlook for Android。 | Microsoft Outlook for iOS 和使用 Microsoft 云德国邮箱配置的 Android 帐户可能必须删除并重新添加到 Outlook，以便正确同步新的 Office 365 服务配置。 | 适用于 iOS 和 Android 客户的 Microsoft Outlook | 以前为 Microsoft 云德国配置的 Outlook 邮箱可能无法获取新的 Office 365 服务配置，从而导致其他用户体验的错误和性能下降。 鼓励 IT 管理员提供文档，以主动指导用户删除帐户并将其重新添加到 Microsoft Outlook for iOS 和 Outlook 中，如果在迁移之后登录或同步邮件时出现问题。 |
| 准备在迁移后通知用户重新启动和登录客户端。 | Office 客户端许可将从 Microsoft 云德国转换到迁移中的 Office 365 服务。 客户端在注销和签入到 Office 客户端后，会选取新的有效许可证。 | Microsoft 365 应用客户 |  用户的 Office 产品需要刷新 Office 365 服务中的许可证。 如果不刷新许可证，Office 产品可能会遇到许可证验证错误。 |
| 取消任何试用订阅。 | 试用订阅将不会迁移，并将阻止付费订阅的传输。 | 所有客户 | 试用服务已过期，如果用户在取消后访问，则无法正常运行。 |
| 为在德国访问 Skype for Business 的用户部署团队桌面客户端。 | 迁移将用户移动到团队进行协作、通话和聊天。 或者，部署团队桌面客户端，或确保支持的浏览器可用。 | Skype for Business 客户 | Inaction 将导致团队协作服务不可用。 |
| 分析 Microsoft 云德国与 Office 365 服务之间的许可证功能之间的差异。 | Office 365 服务包括当前 Microsoft 云德国中不可用的其他功能和服务。 在订阅转移过程中，用户将可以使用新功能。 | 所有客户 | -分析 Microsoft 云德国和 Office 365 服务的许可证提供的不同功能。 从 [Office 365 平台服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)开始。 <br><br> -确定是否应最初禁用 Office 365 服务的任何新功能，以限制对用户或用户更改管理的影响，并根据需要更改用户许可证分配。 <br><br> -为用户和技术支持人员准备 Office 365 服务提供的新服务和功能。 |
| 创建组织范围的 [保留策略](https://docs.microsoft.com/microsoft-365/compliance/retention) ，以防止在迁移过程中无意中删除内容。  | -若要确保最终用户在迁移过程中不会意外删除内容，客户可以选择启用组织范围的保留策略。 <br><br> -尽管不需要保留，但在迁移过程中的任何时间放置保留都应按预期工作，保留策略是一种备份安全机制。 同时，不是所有客户都可以使用保留策略，尤其是关心保留策略的人。 | Office 客户 | 按照 [了解保留策略和保留标签](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)中的说明，应用保留策略。 |
| [Active Directory 联合身份验证服务 (AD FS) 场的备份](ms-cloud-germany-transition-add-adfs.md#backup) ，用于灾难恢复方案。 | 客户需要适当地备份 AD FS 服务器场，以确保对全局 & 的信赖方信任可以在不触及域的颁发者 URI 的情况下还原。 Microsoft 建议使用 AD FS 快速还原来备份服务器场和相应的还原（如有必要）。 | 联合身份验证组织 | 必需的操作。 如果客户的 AD FS 服务器场出现故障，Inaction 将导致迁移过程中的服务影响。 |


## <a name="exchange-online"></a>Exchange Online

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 向外部合作伙伴通知即将推出的到 Office 365 服务的过渡。 | 可用性地址空间配置允许与 Office 365 共享忙/闲信息。 | 已启用共享日历和可用性地址空间的 Exchange Online 客户。 | 必需的操作。  如果不这样做，可能会导致在客户迁移的后续阶段发生服务或客户端故障。 |
|||||

如果您具有混合 Exchange：

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
|  (HCW) 中卸载 "混合配置" 向导的早期版本，然后安装并执行最新版本的 17.0.5378.0 [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) 。 | HCW 的最新版本包括必要的更新，以支持从 Microsoft 云德国转换到 Office 365 服务的客户。 <br><br> 更新包括对发送连接器和接收连接器的本地证书设置所做的更改。 | 运行混合部署的 Exchange Online 客户 | 必需的操作。 如果不这样做，可能会导致服务或客户端故障。 |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

如果您有 SharePoint 2013：

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 限制 SharePoint 2013 工作流，在 SharePoint Online 迁移过程中使用。 | 缩短 SharePoint 2013 工作流并在过渡前完成正在进行的工作流。 | SharePoint Online 客户 | Inaction 可能会导致用户混淆和技术支持呼叫。 |
|||||

<!--
[Reference:  If Pre-Work][ SharePoint 2013 ]
--> 

## <a name="mobile"></a>移动版

如果使用的是第三方移动设备管理 (MDM) 解决方案：

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 确定迁移后是否需要重新配置。 | MDM 解决方案可能目标 `outlook.de` 终结点。 在此转换到 Office 365 服务时，客户端配置文件应更新到 Office 365 服务 URL `outlook.office365.com` 。 | Exchange Online 和 MDM 客户 | 在终结点可访问时，客户端可能仍能正常运行 `outlook.de` ，但如果 Microsoft 云德国终结点不再可用，它们将会失败。 |
|||||

<!--
[Reference:  If Pre-Work][ Mobile]
-->             

## <a name="line-of-business-apps"></a>业务线应用程序

如果使用的是第三方服务或业务线 (LOB) 与 Office 365 集成的应用程序： 

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 确定迁移后是否需要重新配置。 | 可以将与 Office 365 集成的第三方服务和应用程序编码为预计 Microsoft 云德国 IP 地址和 Url。 | 所有客户 | 必需的操作。 Inaction 可能会导致服务或客户端软件出现故障。 |
|||||

<!--
[Reference:  If Pre-Work][ LOB]
--> 

## <a name="azure"></a>Azure 

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 通过与您的合作伙伴合作，确定哪些 Azure 服务正在使用，并准备将来从德国迁移到 Office 365 服务租户。 按照 [Azure 迁移行动手册](https://docs.microsoft.com/azure/germany/germany-migration-main)中所述的步骤操作。 | 迁移 Azure 资源是一项客户责任，并需要在规定的步骤后进行手动努力。 了解组织中使用的服务是成功迁移 Azure 服务的关键所在。 <br><br> 拥有 Azure 订阅的 Office 365 德国客户在同一标识分区 (组织) 必须遵循 Microsoft 指定的订单，然后才能开始订阅和服务迁移。 | Azure 客户 | -客户可以有多个 Azure 订阅，每个订阅包含基础结构、服务和平台组件。 <br><br> -管理员应确定订阅和利益干系人，以确保在此迁移事件过程中可以进行提示的迁移和验证。 <br><br> 如果未能成功完成这些订阅和指定时间线中的 Azure 组件的迁移，将会影响 Office 和 Azure AD 转换到 Office 365 服务的完成，并且可能会导致数据丢失。  <br><br> -消息中心通知将通知客户引导迁移开始的点。 |
|||||

<!--
[Reference:  If Azure Pre-Work][ Azure]
-->  

## <a name="dynamics-365"></a>Dynamics 365

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 对于 Dynamics 365 沙盒订阅，请务必从 Microsoft 云德国中的 Dynamics 365 订阅下载 Dynamics SQL 实例的生产环境。 应在沙盒迁移之前将最新的生产备份还原到沙盒。 | 动态365的迁移要求客户确保使用最新的生产数据库刷新沙盒环境。 | Microsoft Dynamics 客户 | FastTrack 团队将帮助客户执行干燥运行，以验证从 8. x 到9.1 的版本升级。 |
|||||

<!--
[Reference: Prework][Dynamics]
-->             

## <a name="power-bi"></a>Power BI

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 从 power BI 订阅删除不会从 Power BI Microsoft 云德国迁移到 Office 365 服务的对象。 | 迁移 Power BI 服务需要客户操作才能删除某些项目，如数据集和仪表板。 | Power BI 客户 | 管理员可能必须从订阅中删除以下项： <br> -Real-Time 数据集的 (例如，流式传输或推送数据集)  <br> -Power BI 本地数据网关配置和数据源 |
|||||

<!--
[Reference: Prework][Power BI]
--> 

## <a name="dns"></a>DNS

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 如果当前 DNS 具有 MSOID CName 条目，请查看并准备 DNS 更改。 | 客户拥有的 DNS 区域更改 | Office 客户端服务客户 | 如果存在 MSOID CName，请将客户拥有的 DNS 记录的生存时间 (TTL) 更新为5分钟。 |
|||||

<!--
[Reference: Prework][DNS]
-->             

## <a name="federated-identity"></a>联合身份

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 为全局 Azure AD 终结点生成信赖方信任。 | 客户需要手动创建信赖方信任 (RPT) 到 [全局](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) 终结点。 这是通过使用全局联合身份验证元数据 URL，然后使用 [AZURE AD RPT 声明规则](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) (AD FS 帮助中) 生成声明规则并将其导入到 RPT 中来通过 GUI 添加新的 RPT 实现的。 | 联合身份验证组织 | 必需的操作。 Inaction 将在迁移过程中导致服务影响。 |
|||||

<!--
[Reference: Prework][Federation]
-->  

## <a name="more-information"></a>详细信息

入门：

- [从 Microsoft 云德国迁移到新的德国数据中心区域中的 Office 365 服务](ms-cloud-germany-transition.md)
- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)
- [迁移过程中的客户体验](ms-cloud-germany-transition-experience.md)

在转换中移动：

- [迁移阶段的操作和影响](ms-cloud-germany-transition-phases.md)
- [其他预备工作](ms-cloud-germany-transition-add-pre-work.md)
- [服务](ms-cloud-germany-transition-add-general.md)、[设备](ms-cloud-germany-transition-add-devices.md)、[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他信息。

云应用：

- [Dynamics 365 迁移计划信息](https://aka.ms/d365ceoptin)
- [Power BI 迁移计划信息](https://aka.ms/pbioptin)
- [开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)
