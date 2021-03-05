---
title: '迁移阶段操作和影响从 Microsoft 云德国 (高级) '
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
description: 摘要：从德国 Microsoft 云 (德国 Microsoft 云) 迁移到新的德国数据中心区域中的 Office 365 服务时的其他客户体验信息。
ms.openlocfilehash: 26db69583bac68723d5d57b07abb856c8190d9b1
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454463"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>迁移阶段操作和影响从 Microsoft 云德国 (高级)  

从 Microsoft 云德国到 Microsoft Office 365 服务德国地区的租户迁移作为一组阶段及其针对每个工作负载的配置操作执行。 此图显示了迁移到新的德国数据中心的九个阶段。

![迁移到新德国数据中心的九个阶段](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

以下各节提供有关从德国 Microsoft 云 (德国 Microsoft 云) 迁移到新的德国数据中心区域中的 Office 365 服务的客户体验的其他信息。

## <a name="services"></a>服务

在阶段 2/9 和阶段 3/9 之间，合作伙伴门户可能无法访问。 在此期间，合作伙伴可能无法访问合作伙伴门户上的租户信息。 由于每次迁移都不同，因此辅助功能的持续时间可能为小时。 

### <a name="azure-ad-phase-2-of-9"></a>Azure AD (阶段 2/9) 

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| Microsoft 云德国的 Azure AD 租户已复制到 Office 365 服务。 | Azure AD 将租户复制到 Office 365 服务。 保留租户和用户标识符。 Azure AD 服务调用从 Microsoft 云德国重定向到 Office 365 服务，并且对服务透明。 | 所有 Office 客户 | - GDPR (一般数据保护) 数据主体请求 (DSR) 从 Azure 管理门户执行，用于将来请求。 任何驻留在 Microsoft 云德国的旧式或非客户诊断数据都将在 30 天后或之前删除。 <br><br> - 将联合身份验证与 Active Directory 联合身份验证服务 (AD FS) 一同使用的客户不应在迁移期间对用于本地 Active Directory 的所有身份验证的颁发者 URI 进行更改。 更改颁发者 URI 将导致域中用户的身份验证失败。 可以在 AD FS 中直接更改颁发者 URI，或在将域从托管域转换为联合域时更改，反之亦然。 我们建议客户不要添加、删除或转换已迁移的 Azure AD 租户中的联合域。 在迁移完成之后，可更改颁发者 URI。 <br><br> - MFA (MFA) 请求，当租户复制到 Office 365 服务时，将 Microsoft Authenticator 显示为用户 ObjectID (GUID) 。 MFA 请求将执行预期，尽管此显示行为。  使用 Office 365 服务终结点激活的 Microsoft Authenticator 帐户将显示 UPN (用户) 。  使用 Microsoft 云德国终结点添加的帐户将显示用户 ObjectID，但将同时用于 Microsoft 云德国和 Office 365 服务终结点。  |
| 建立指向全局 STS 服务的 AuthServer 本地服务器。 | 这可确保向迁移到 Microsoft 云德国的用户提出的针对混合本地环境的 Exchange 可用性请求的请求进行身份验证，以访问本地服务。 同样，这将确保对从本地到 Office 365 服务终结点的请求进行身份验证。 | 混合部署本地部署 (Exchange Online)  | Azure AD 迁移完成后，本地 Exchange (混合) 拓扑的管理员必须为 Office 365 服务添加新的身份验证服务终结点。 使用 Exchange PowerShell 中的此命令，替换在 `<TenantID>` Azure **Active Directory** (Azure 门户中的组织的租户 ID) 。 <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> 未能完成此任务可能会导致混合忙/闲请求无法为从 Microsoft 云德国迁移到 Office 365 服务的邮箱用户提供信息。  |
| Azure 资源的迁移。 | 使用 Office 365 和 Azure 资源 (例如，网络、计算和存储) 将执行资源迁移到 Office 365 服务实例。 此迁移是客户的责任。 消息中心帖子将发出开始信号。 在 Office 365 服务环境中完成 Azure AD 组织之前，必须完成迁移。 | Azure 客户 | 有关 Azure 迁移，请参阅 Azure 迁移手册 [，Azure Germany 的迁移指南概述](https://docs.microsoft.com/azure/germany/germany-migration-main)。 |
|||||

### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (阶段 5/9) 

如果使用 **Set-UserPhoto：**

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 新的德国区域将添加到现有组织设置中，邮箱将移动到 Office 365 服务。 | Exchange Online 配置将新的德国本地区域添加到转换组织。 此 Office 365 服务区域设置为默认区域，这使内部负载平衡服务能够将邮箱重新分发到 Office 365 服务中的相应默认区域。 在此转换中，位于德国 (Office 365 服务) 位于同一组织中，并且可以使用任一 URL 终结点。 |  Exchange Online | 如果用户邮箱已迁移，但尚未迁移管理员邮箱，或者反之亦然，则管理员将无法运行 **Set-UserPhoto（PowerShell** cmdlet）。 在这种情况下，管理员必须在使用以下语法设置连接期间传递其他 `ConnectionUri` 字符串： <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> 其中 `<user_email>` ，是需要通过使用 **Set-UserPhoto** 更改其照片的用户的电子邮件 ID 的占位符。 |
|||||

如果你使用的是混合本地部署：

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
|停止或删除邮箱的任何载入或载出移动。  | 这可确保移动请求不会失败并出现错误。 | 混合部署本地部署 (Exchange Online)  | 必需操作。 如果不这样做，可能会导致服务或软件客户端出现故障。 |
|||||

### <a name="dynamics-phase-8-of-9"></a>Dynamics (Phase 8 of 9) 

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| Microsoft Dynamics 资源 | 使用 Microsoft Dynamics 的客户将参与工程或 FastTrack，以将 Dynamics 转换为 Office 365 服务实例。* | Microsoft Dynamics 365 客户 | - 迁移后，管理员验证组织。 <br><br> - 管理员在必要时修改工作流。 <br><br> - 管理员会在适当时清除 AdminOnly 模式。 <br><br> - 管理员根据情况从 _沙_ 盒更改组织类型 <br><br> - 通知最终用户新 URL 以访问组织 (实例) 。 <br><br> - 更新到新终结点 URL 的任何入站连接。 <br><br> - 在转换期间，Dynamics 服务将不可用。 <br><br> - 用户需要在每个组织迁移后验证组织运行状况和功能。  |
|||||

\* () Microsoft Dynamics 365 的客户必须按照提供的迁移过程定义，在此迁移方案中采取措施。  (ii) 操作失败将意味着 Microsoft 无法完成迁移。  (iii) 如果 Microsoft 由于客户的不作为无法完成迁移，则客户的订阅将于 2021 年 10 月 29 日到期。 


### <a name="power-bi-phase-8-of-9"></a>Power BI (阶段 8/9) 

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| Power BI 资源的迁移 | 在手动触发现有 PBI 迁移工具将 Power BI 转换为 Office 365 服务实例后，工程或 FastTrack 将让使用 Microsoft Power BI 的客户参与。\*\* | Microsoft Power BI 客户 | - 不会转换以下 Power  BI 项，并且必须重新创建这些项目： <br><br> - 实时数据集 (，例如流式处理或推送) 。 <br> - Power BI 本地数据网关配置和数据源。 <br> - 基于实时数据集构建的报告在迁移后将不可用，需要重新创建。 <br><br> - Power BI 服务在转换期间将不可用。 服务的不可用时间不应超过 24 小时。 <br><br> - 迁移后，用户需要使用 Power BI 服务重新配置数据源及其本地数据网关。  在执行此操作之前，用户将无法使用这些数据源来针对这些数据源执行计划刷新和/或直接查询。 <br><br> - 无法迁移容量和高级工作区。 客户需要在迁移之前删除所有容量，在迁移后重新创建它们。 将工作区移回所需的容量。  |
|||||

\*\* (我) Microsoft Power BI 的客户必须按照提供的迁移过程定义，在此迁移方案中采取措施。  (ii) 操作失败将意味着 Microsoft 无法完成迁移。  (iii) 如果 Microsoft 由于客户的不作为无法完成迁移，则客户的订阅将于 2021 年 10 月 29 日到期。 



## <a name="during-migration"></a>在迁移过程中

### <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (阶段 4/9) 

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| SharePoint 和 OneDrive 已转换。 | 在此阶段，SharePoint 和 OneDrive 从 Microsoft 云德国迁移到 Office 365 服务。 现有的 Microsoft 云德国 URL `contoso.sharepoint.de` () 。 由 Microsoft 云德国或 Office 365 服务颁发的令牌在转换期间有效。 | SharePoint 客户 | Inflight SharePoint 2013 workflows will be broken during migration and must be republished after migration. |
|||||


### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (阶段 5/9) 

对于电子数据展示：

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 在迁移过程中，电子数据展示搜索将失败或返回已迁移的 SharePoint Online、OneDrive for Business 和 Exchange Online 位置的 0 个结果。 | 在迁移过程中，客户可以在安全与合规中心（包括内容搜索）&案例[、保留、搜索和](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)[导出](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)。  但是，针对已迁移的 SharePoint Online、OneDrive for Business 和 Exchange Online 位置的搜索将返回 0 个结果或生成错误。 有关修正，请参阅"影响 _"_ 列。 | 使用电子数据展示的所有客户 |  如果搜索在迁移过程中返回 0 个结果或错误，请对 SharePoint Online 执行以下操作： <br><br>  按照从 OneDrive 或 SharePoint 下载文件和文件夹中的说明，直接从 SharePoint Online/OneDrive for Business 网站 [下载网站](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)。 此方法需要 SharePoint Online 管理员权限或网站的只读权限。 <br><br> 如果超出限制，如从 OneDrive 或 [SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)下载文件和文件夹所解释，客户可以按照在将 [SharePoint](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)和 Teams 文件与计算机同步中的指南使用 OneDrive for Business 同步客户端。 <br><br> - Exchange Online <br><br> - [In-Place eDiscovery in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||


### <a name="skype-for-business-online-phase-7-of-9"></a>Skype for Business Online (阶段 7/9) 

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 将 Skype for Business 迁移到 Teams。 | 现有 Skype for Business 客户将迁移到欧洲 Office 365 服务，然后转换到 Office 365 服务德国地区的 Microsoft Teams。 | Skype for Business 客户 |  PowerShell 将用于管理租户和用户的设置和策略。 连接到 PowerShell 会话时，添加以下内容： <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||


## <a name="post-migration"></a>迁移后

### <a name="azure-ad-phase-9-of-9"></a>Azure AD (阶段 9/9) 

对于混合：

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 更新 Azure AD Connect。 | 完成到 Azure AD 的剪切后，组织将完全使用 Office 365 服务，并且不再连接到德国 Microsoft 云。 此时，客户需要确保增量同步过程已完成，然后，在注册表路径中将字符串值从 `AzureInstance` 3 (Microsoft Cloud Deutschland) 更改为 0。 `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` | 已连接 Azure AD 的混合组织 | 更改 `AzureInstance` 注册表项的值。 如果不这样做，将导致在 Microsoft 云德国终结点不再可用后无法同步对象。 |
|||||

对于联合身份验证：

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 从 Microsoft 云德国 AD FS 中删除信赖方信任。 | 完成到 Azure AD 的剪切后，组织将完全使用 Office 365 服务，并且不再连接到德国 Microsoft 云。 此时，客户需要删除对 Microsoft 云德国终结点的信赖方信任。 只有在客户没有将 Azure AD 用作标识提供程序或 IdP (时，才能) 。 | 联合身份验证组织 | 无。 |
|||||

对于 Azure AD：

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 如果原始请求未获得批准，则需要再次请求迁移前 30 天内加入 Azure AD 组的请求。 | 如果迁移前 30 天内未批准这些请求，最终用户客户将需要使用访问面板提交重新加入 Azure AD 组的请求。 | 迁移前 30 天内未批准 Azure AD 组审批请求的最终用户 |  作为最终用户： <ol><li>导航到 [Access 面板](https://account.activedirectory.windowsazure.com/r#/joinGroups)。</li><li>查找在迁移前 30 天内等待其成员身份审批的 Azure AD 组。</li><li>再次请求加入 Azure AD 组。</li></ol> 无法批准在迁移前 30 天内加入活动组的请求，除非在迁移后重新请求。 |
|||||

对于 DNS：

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 更新 Office 365 服务终结点本地 DNS 服务。 | 需要更新指向 Office 365 Germany 的客户管理的 DNS 条目，以指向 Office 365 服务终结点。 | 所有 Office 客户 | 必需操作。 如果不这样做，可能会导致服务或软件客户端出现故障。 |
|||||

对于 Office 365 服务终结点的第三方服务：

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 更新 Office 365 服务终结点的合作伙伴和第三方服务。 | - 需要更新指向 Office 365 Germany 的第三方服务和合作伙伴，以指向 Office 365 服务终结点。 示例：重新注册库应用版本（如果可用）以与供应商和合作伙伴一致。 <br><br> - 将利用 Graph API 的所有自定义应用程序指向 `graph.microsoft.de` `graph.microsoft.com` 。 其他具有已更改终结点的 API 也需要更新（如果已利用）。 <br><br> - 更改所有非第一方企业应用程序以重定向到全球终结点。  | 所有 Office 客户 | 必需操作。 如果不这样做，可能会导致服务或软件客户端出现故障。 |
|||||

### <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (阶段 4/9) 

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 重新发布 SharePoint 2013 工作流。 | 在迁移前的工作中，我们减少了 SharePoint 2013 工作流的数量。 迁移完成后，客户可以重新发布工作流。 | 所有 Office 客户 | 这是一项必需操作。 如果不这样做，可能会导致用户混淆和技术支持呼叫。 |
| 通过 Outlook 共享项目 | 租户直接转换后，通过 Outlook 共享项目不再有效。 | SharePoint Online 和 OneDrive for Business | - 在 SharePoint Online 和 OneDrive for Business 中，可以通过 Outlook 共享项目。 按 Outlook 按钮后，会创建可共享的链接，并推送到邮件Outlook Web App。 <br><br> - 租户转换后，这种共享方法将不起作用。 我们意识到这是一个已知问题。 但是，由于此 Outlook 功能已弃用，因此在推出弃用之前，不会计划修复该问题。 |


### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (阶段 5/9) 

如果使用的是混合 Exchange 配置：

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 针对 Office 365 服务重新 (HCW) 混合配置向导。 | 现有 HCW 配置旨在支持 Microsoft 云德国。 随着 Exchange 服务的迁移完成，我们将本地配置与 Microsoft 云德国分离。 | 运行混合部署的 Exchange Online 客户 | - 必需操作。 如果不这样做，可能会导致服务或软件客户端出现故障。 在 Exchange 邮箱迁移 (5 天或 5) ，通知客户端应停止并删除其邮箱的任何载入或载出移动。  如果没有，他们将在移动请求中看到错误。 <br><br> - Exchange 邮箱迁移完成后，通知客户端可以恢复载入和载出移动。 <br> 在将 Exchange 从 Microsoft 云德国迁移到 Office 365 服务期间运行 **Test-MigrationServerAvailabiilty（PowerShell** cmdlet）可能不起作用。 但是，迁移完成后它将正常工作。 <br><br> 如果客户端在迁移邮箱后遇到凭据或授权问题，则用户可以通过运行或通过使用 Exchange 控制面板 (ECP) 来在迁移终结点 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` 中重新输入其本地管理员凭据。  |

对于电子数据展示：

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
|  所有 SharePoint Online、OneDrive for Business 和 Exchange Online 位置都随安全与合规中心 (SCC) 。 | 所有电子数据展示活动都应从全球租户运行。 搜索现在将 100% 成功。  任何失败或错误都应遵循正常支持渠道。 | 使用电子数据展示的所有客户 | 无。 |
| 删除在迁移前步骤中创建的组织范围的保留策略 | 客户可以删除在客户迁移前工作期间创建的组织范围的保留策略。 | 作为迁移前步骤的一部分应用保留策略的所有客户。 | 无。 |
|||||



## <a name="next-step"></a>后续步骤

[了解迁移阶段的操作和影响](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>更多信息

入门：

- [从德国 Microsoft 云迁移到新的德国数据中心区域的 Office 365 服务](ms-cloud-germany-transition.md)
- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)
- [迁移期间客户体验](ms-cloud-germany-transition-experience.md)

在转换过程中移动：

- [迁移阶段操作和影响](ms-cloud-germany-transition-phases.md)
- [其他预工作](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)[和 AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。

云应用：

- [Dynamics 365 迁移计划信息](https://aka.ms/d365ceoptin)
- [Power BI 迁移计划信息](https://aka.ms/pbioptin)
- [开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)
