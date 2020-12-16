---
title: '迁移阶段操作和影响从德国 Microsoft 云 (高级) '
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
description: 摘要：从德国 Microsoft 云 (移动到新的德国数据中心) Office 365 服务时的其他客户体验信息。
ms.openlocfilehash: 3f22ca9c380b3271d0c186be1f50fae4a0ea5bb9
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688189"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>迁移阶段操作和影响从德国 Microsoft 云 (高级)  

以下各节提供有关从德国 Microsoft 云 (德国) 迁移到新的德国数据中心地区的 Office 365 服务的客户体验的其他信息。

## <a name="services"></a>服务

### <a name="azure-ad"></a>Azure AD

| 步骤 (步骤)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| Microsoft 云德国版中复制到 Office 365 服务的 Azure AD 租户。 | Azure AD 将租户复制到 Office 365 服务。 保留租户和用户标识符。 Azure AD 服务调用从 Microsoft 云德国重定向到 Office 365 服务，并且对服务是透明的。 | 所有 Office 客户 | - GDPR (GDPR) 数据主体请求 (DSR) 从 Azure 管理门户执行，用于将来请求。 驻留在 Microsoft 云德国的任何旧版或非客户诊断数据在 30 天后或之前删除。 <br><br> - 将联合身份验证与 Active Directory 联合身份验证服务 (AD FS) 一起使用的客户不应对在迁移期间用于本地 Active Directory 的所有身份验证的颁发者 URI 进行更改。 更改颁发者 URI 将导致域中用户的身份验证失败。 颁发者 URI 可以直接在 AD FS 中更改，或在域从托管转换为联合时更改，反之亦然。 我们建议客户不要添加、删除或转换已迁移的 Azure AD 租户中的联合域。 在迁移完成之后，可更改颁发者 URI。 <br><br> - 多重身份验证 (MFA) 请求，当租户复制到 Office 365 服务时，将使用 Microsoft Authenticator 显示为用户 ObjectID (GUID) 。 MFA 请求将执行预期，尽管此显示行为。  使用 Office 365 服务终结点激活的 Microsoft Authenticator 帐户将显示 UPN (用户) 。  使用德国 Microsoft 云终结点添加的帐户将显示用户 ObjectID，但将同时用于 Microsoft 云德国和 Office 365 服务终结点。  |
| 建立指向全局 STS 服务的 AuthServer 本地服务器。 | 这将确保迁移到德国 Microsoft 云的用户针对面向混合本地环境的 Exchange 可用性请求的请求经过身份验证，以访问本地服务。 同样，这将确保对从本地到 Office 365 服务终结点的请求进行身份验证。 | 在本地部署中 (Exchange Online) 客户 | Azure AD 迁移完成后，本地 Exchange (混合) 拓扑的管理员必须为 Office 365 服务添加新的身份验证服务终结点。 通过 Exchange PowerShell 中的此命令，将你的组织的租户 ID (`<TenantID>` Azure **Active Directory**) 。 <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> 未能完成此任务可能会导致混合忙/闲请求无法为从 Microsoft 云德国迁移到 Office 365 服务的邮箱用户提供信息。  |
| Azure 资源的迁移。 | 使用 Office 365 和 Azure 资源 (例如，网络、计算和存储) 将执行资源迁移到 Office 365 服务实例。 此迁移是客户的责任。 消息中心帖子将发出开始信号。 迁移必须在 Office 365 服务环境中完成 Azure AD 组织之前完成。 | Azure 客户 | 有关 Azure 迁移，请参阅 Azure 迁移操作手册（Azure [Germany 的迁移指南概述](https://docs.microsoft.com/azure/germany/germany-migration-main)）。 |
|||||

### <a name="exchange-online"></a>Exchange Online

如果你使用的是 **Set-UserPhoto：**

| 步骤 (步骤)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 新的德国区域将添加到现有组织设置中，邮箱将移动到 Office 365 服务。 | Exchange Online 配置将新的德国本地区域添加到转换组织。 此 Office 365 服务区域设置为默认区域，这使内部负载平衡服务能够将邮箱重新分发到 Office 365 服务中的相应默认区域。 在此转换中，位于德国 (Office 365 服务) 位于同一组织中，并且可以使用任一 URL 终结点。 |  Exchange Online | 如果用户邮箱已迁移，但尚未迁移管理员邮箱，则管理员将无法运行 **Set-UserPhoto**（PowerShell cmdlet）。 在这种情况下，管理员必须在连接设置过程中通过以下语法传递其他 `ConnectionUri` 字符串： <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> 其中 `<user_email>` ，是需要通过使用 **Set-UserPhoto** 更改其照片的用户的电子邮件 ID 的占位符。 |
|||||

如果你使用的是混合本地部署：

| 步骤 (步骤)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
|停止或删除邮箱的任何载入或载出移动。  | 这可确保移动请求不会失败并出现错误。 | 在本地部署中 (Exchange Online) 客户 | 必需操作。 如果不这样做，可能会导致服务或软件客户端出现故障。 |
|||||

### <a name="dynamics"></a>Dynamics

| 步骤 (步骤)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| Microsoft Dynamics 资源 | 使用 Microsoft Dynamics 的客户将参与工程或 FastTrack，以将 Dynamics 转换为 Office 365 服务实例。* | Microsoft Dynamics 365 客户 | - 迁移后，管理员验证组织。 <br><br> - 管理员在必要时修改工作流。 <br><br> - 管理员会在适当时清除 AdminOnly 模式。 <br><br> - 管理员根据情况从 _沙_ 盒更改组织类型 <br><br> - 通知最终用户新 URL 以访问组织 (实例) 。 <br><br> - 更新到新终结点 URL 的任何入站连接。 <br><br> - 切换期间，Dynamics 服务将不可用。 <br><br> - 用户需要在每个组织迁移后验证组织运行状况和功能。  |
|||||

\* () Microsoft Dynamics 365 的客户必须按照提供的迁移过程定义，在此迁移方案中采取措施。  (ii) 客户采取操作失败将意味着 Microsoft 无法完成迁移。  (iii) 当 Microsoft 因客户的不作为无法完成迁移时，客户的订阅将于 2021 年 10 月 29 日到期。 


### <a name="power-bi"></a>Power BI

| 步骤 (步骤)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| Power BI 资源的迁移 | 在手动触发现有 PBI 迁移工具将 Power BI 转换到 Office 365 服务实例后，工程或 FastTrack 将让使用 Microsoft Power BI 的客户参与。\*\* | Microsoft Power BI 客户 | - 以下 Power BI 项目 _将不会_ 转换，必须重新创建它们： <br><br> - 实时数据集 (，例如流式处理或推送) 。 <br> - Power BI 本地数据网关配置和数据源。 <br> - 基于实时数据集构建的报告在迁移后将不可用，需要重新创建。 <br><br> - 切换期间，用户无法使用 Power BI 服务。 服务的不可用时间不应超过 24 小时。 <br><br> - 迁移后，用户需要使用 Power BI 服务重新配置数据源及其本地数据网关。  在用户执行此操作之前，用户将无法使用这些数据源来针对这些数据源执行计划刷新和/或直接查询。 <br><br> - 无法迁移容量和高级工作区。 客户需要在迁移之前删除所有容量，在迁移后重新创建它们。 将工作区移回所需的容量。  |
|||||

\*\* () Microsoft Power BI 的客户必须按照提供的迁移过程定义，在此迁移方案中采取措施。  (ii) 客户采取操作失败将意味着 Microsoft 无法完成迁移。  (iii) 当 Microsoft 因客户的不作为无法完成迁移时，客户的订阅将于 2021 年 10 月 29 日到期。 


### <a name="office-apps"></a>Office 应用

| 步骤 (步骤)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 客户端、Office Online（Office 客户端转换期间）和 Azure AD 完成租户范围以指向 Office 365 服务。 | 此配置更改使 Office 客户端能够更新并指向 Office 365 服务终结点。 | 所有 Office 客户 | - 从客户拥有的 DNS 中删除 MSOID CName（如果存在）。 <br><br> - 通知用户关闭 _所有_ Office 应用，然后重新登录 (或强制客户端重新启动，并强制用户登录) 以允许 Office 客户端选取更改。 <br><br> - 通知用户和技术支持人员，用户可能会看到一个 Office 横幅，提示他们在转换后 72 小时内重新激活 Office 应用。 <br><br> - 个人计算机上的所有 Office 应用程序必须关闭，用户必须注销，然后重新登录。 在黄色激活栏中，登录以重新激活 Office 365 服务。 <br><br> - 共享计算机需要类似于个人计算机的操作，并且不需要特殊过程。 <br><br> - 在移动设备上，用户必须注销应用，关闭应用，然后重新登录。 |
|||||

## <a name="during-migration"></a>在迁移过程中


### <a name="exchange-online"></a>Exchange Online

对于电子数据展示：

| 步骤 (步骤)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 在迁移过程中，电子数据展示搜索将失败或返回已迁移的 SharePoint Online、OneDrive for Business 和 Exchange Online 位置的 0 个结果。 | 在迁移过程中，客户可以在安全与合规中心（包括内容搜索）&案例 [、保留、搜索](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)和 [导出](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)。  但是，针对已迁移的 SharePoint Online、OneDrive for Business 和 Exchange Online 位置进行搜索将返回 0 个结果或产生错误。 有关修正，请参阅" _影响"_ 列。 | 使用电子数据展示的所有客户 |  如果搜索在迁移过程中返回 0 个结果或错误，请对 SharePoint Online 执行以下操作： <br><br>  按照从 OneDrive 或 SharePoint 下载文件和文件夹中的说明，直接从 SharePoint Online/OneDrive for Business 网站 [下载网站](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)。 此方法需要 SharePoint Online 管理员权限或网站上只读权限。 <br><br> 如果超出限制，如从 OneDrive 或 [SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)下载文件和文件夹所说明，客户可以按照计算机同步 SharePoint 和 Teams 文件中的指导使用 OneDrive for Business [同步客户端](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)。 <br><br> - Exchange Online <br><br> - [就地电子数据展示Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||


### <a name="sharepoint-online"></a>SharePoint Online

| 步骤 (步骤)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| SharePoint 和 OneDrive 已转换。 | 在此阶段，SharePoint 和 OneDrive 从 Microsoft 云德国迁移到 Office 365 服务。 现有的 Microsoft 云德国 URL 将保留 `contoso.sharepoint.de` () 。 由德国 Microsoft 云或 Office 365 服务颁发的令牌在转换期间有效。 | SharePoint 客户 | 在迁移过程中，SharePoint 2013 Inflight 工作流将中断，并且必须在迁移后重新发布。 |
|||||

### <a name="skype-for-business-online"></a>Skype for Business Online

| 步骤 (步骤)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 将 Skype for Business 迁移到 Teams。 | 现有 Skype for Business 客户将迁移到欧洲 Office 365 服务，然后转换到 Office 365 服务德国地区的 Microsoft Teams。 | Skype for Business 客户 |  PowerShell 将用于管理租户和用户的设置和策略。 连接到 PowerShell 会话时，添加以下内容： <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||


## <a name="post-migration"></a>迁移后

### <a name="azure-ad"></a>Azure AD

对于混合：

| 步骤 (步骤)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 更新 Azure AD Connect。 | 完成到 Azure AD 的剪切后，组织将完全使用 Office 365 服务，并且不再连接到德国 Microsoft 云。 此时，客户需要确保增量同步过程已完成，此后，在注册表路径中将字符串值从 `AzureInstance` 3 (Microsoft Cloud Deutschland) 更改为 0。 `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` | 已连接 Azure AD 的混合组织 | 更改 `AzureInstance` 注册表项的值。 如果不这样做，将导致在 Microsoft 云德国终结点不再可用后不同步对象。 |
|||||

对于联合身份验证：

| 步骤 (步骤)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 从 Microsoft 云德国 AD FS 中删除信赖方信任。 | 完成到 Azure AD 的剪切后，组织将完全使用 Office 365 服务，并且不再连接到德国 Microsoft 云。 此时，客户需要删除对 Microsoft 云德国终结点的信赖方信任。 只有在客户没有应用程序将 Azure AD 用作标识提供程序或 IdP (时，才能) 。 | 联合身份验证组织 | 无。 |
|||||

对于 Azure AD：

| 步骤 (步骤)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 如果原始请求未获得批准，则需要再次请求迁移前 30 天内加入 Azure AD 组的请求。 | 如果迁移前 30 天内未批准这些请求，最终用户客户将需要使用访问面板再次提交加入 Azure AD 组的请求。 | 迁移前 30 天内未批准其 Azure AD 组审批请求的最终用户 |  作为最终用户： <ol><li>导航到 [Access 面板](https://account.activedirectory.windowsazure.com/r#/joinGroups)。</li><li>查找在迁移前 30 天内等待其成员身份审批的 Azure AD 组。</li><li>再次请求加入 Azure AD 组。</li></ol> 无法批准加入在迁移前 30 天内处于活动状态的组的请求，除非在迁移后重新请求。 |
|||||

对于 DNS：

| 步骤 (步骤)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 更新 Office 365 服务终结点本地 DNS 服务。 | 需要更新指向 Office 365 Germany 的客户管理的 DNS 条目，以指向 Office 365 服务终结点。 | 所有 Office 客户 | 必需操作。 如果不这样做，可能会导致服务或软件客户端出现故障。 |
|||||

对于 Office 365 服务终结点的第三方服务：

| 步骤 (步骤)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 更新 Office 365 服务终结点的合作伙伴和第三方服务。 | - 需要更新指向 Office 365 Germany 的第三方服务和合作伙伴，以指向 Office 365 服务终结点。 示例：重新注册应用程序库应用版本（如果可用）以与供应商和合作伙伴一致。 <br><br> - 将利用 Graph API 的所有自定义应用程序指向 `graph.microsoft.de` `graph.microsoft.com` 。 具有已更改终结点的其他 API 也需要更新（如果已利用）。 <br><br> - 更改所有非第一方企业应用程序以重定向到全球终结点。  | 所有 Office 客户 | 必需操作。 如果不这样做，可能会导致服务或软件客户端出现故障。 |
|||||

### <a name="exchange-online"></a>Exchange Online

如果使用的是混合 Exchange 配置：

| 步骤 (步骤)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 针对 Office 365 服务 (HCW) 重新运行混合配置向导。 | 现有 HCW 配置旨在支持德国 Microsoft 云。 完成 Exchange 服务的迁移后，我们将本地配置与德国 Microsoft 云分离。 | 运行混合部署的 Exchange Online 客户 | - 必需操作。 如果不这样做，可能会导致服务或软件客户端出现故障。 在 Exchange 邮箱迁移 (5 天或) 天之前，通知客户端应停止并删除其邮箱的任何载入或载出移动。  如果没有，他们将在移动请求中看到错误。 <br><br> - Exchange 邮箱迁移完成后，通知客户端可以恢复载入和载出移动。 <br> 在将 Exchange 从 Microsoft 云德国迁移到 Office 365 服务期间，运行 **Test-MigrationServerAvailabiilty（PowerShell** cmdlet）可能不起作用。 但是，迁移完成后，它将正常工作。 <br><br> 如果客户端在迁移邮箱后遇到凭据或授权问题，则用户可以通过运行或通过使用 Exchange 控制面板 (ECP) 来在迁移终结点 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` 中重新输入其本地管理员凭据。  |

对于电子数据展示：

| 步骤 (步骤)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
|  所有 SharePoint Online、OneDrive for Business 和 Exchange Online 位置已随安全与合规中心 (SCC) 。 | 所有电子数据展示活动都应从全球租户运行。 现在，搜索将 100% 成功。  任何失败或错误都应遵循正常支持渠道。 | 使用电子数据展示的所有客户 | 无。 |
| 删除在迁移前步骤中创建的组织范围的保留策略 | 客户可以删除在客户迁移前工作期间创建的组织范围的保留策略。 | 作为迁移前步骤的一部分应用保留策略的所有客户。 | 无。 |
|||||

### <a name="sharepoint-online"></a>SharePoint Online

| 步骤 (步骤)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 重新发布 SharePoint 2013 工作流。 | 在迁移前的工作中，我们减少了 SharePoint 2013 工作流的数量。 迁移完成后，客户可以重新发布工作流。 | 所有 Office 客户 | 这是一项必需操作。 如果不这样做，可能会导致用户混淆和技术支持呼叫。 |
| 通过 Outlook 共享项目 | 租户直接转换后，通过 Outlook 共享项目不再有效。 | SharePoint Online 和 OneDrive for Business | - 在 SharePoint Online 和 OneDrive for Business 中，可以通过 Outlook 共享项目。 按 Outlook 按钮后，会创建可共享的链接，并推送到邮件Outlook Web App。 <br><br> - 租户转换后，这种共享方法将不起作用。 我们意识到这是一个已知问题。 但是，由于此 Outlook 功能位于弃用路径中，因此在推出弃用之前不会计划修复该问题。 |

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
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。

云应用：

- [Dynamics 365 迁移计划信息](https://aka.ms/d365ceoptin)
- [Power BI 迁移计划信息](https://aka.ms/pbioptin)
- [开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)
