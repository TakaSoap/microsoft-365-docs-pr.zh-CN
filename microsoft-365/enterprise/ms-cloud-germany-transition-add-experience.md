---
title: 从 Microsoft 云德国迁移的其他体验信息
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
description: 摘要：从 Microsoft (云) 德国移动到新的德国数据中心区域中的 Office 365 服务时，其他客户体验信息。
ms.openlocfilehash: 1eef8be624a92bf2dcaba8f0df2147697202be3a
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560834"
---
# <a name="additional-experience-information-for-the-migration-from-microsoft-cloud-deutschland"></a>从 Microsoft 云德国迁移的其他体验信息 

以下各节提供了有关客户体验的其他信息。

## <a name="services"></a>服务

### <a name="azure-ad"></a>Azure AD

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| Microsoft 云德国中的 Azure AD 租户已复制到 Office 365 服务中。 | Azure AD 将租户复制到 Office 365 服务。 保留租户和用户标识符。 Azure AD 服务呼叫从 Microsoft 云德国重定向到 Office 365 服务，并对服务是透明的。 | 所有 Office 客户 | -常规数据保护法规 (GDPR) 数据主体请求 (Dsr) 从 Azure 管理门户执行，以供将来请求使用。 驻留在 Microsoft 云德国中的任何旧版或非客户诊断数据都会在30天内或之前的30天内删除。 <br><br> -将联合身份验证与 Active Directory 联合身份验证服务 (AD FS 结合使用的客户) 不应对在迁移期间与内部部署 Active Directory 进行的所有身份验证使用的颁发者 Uri 进行更改。 更改颁发者 Uri 将导致域中用户的身份验证失败。 颁发者 Uri 可以直接在 AD FS 中更改，也可以在将域从 _托管_ 转换为 _联合_ 时进行更改，反之亦然。 我们建议客户不要在已迁移的 Azure AD 租户中添加、删除或转换联合域。 在迁移完全完成后，可以更改颁发者 Uri。 <br><br> -将租户复制到 Office 365 服务时，使用 Microsoft 身份验证器显示的多重身份验证 (MFA) 请求将显示为用户 ObjectID (GUID) 。 尽管此显示行为，否则 MFA 请求将按预期执行。  使用 Office 365 服务终结点激活的 Microsoft 身份验证器帐户将显示用户主体名称 (UPN) 。  使用 Microsoft 云德国终结点添加的帐户将显示用户的 ObjectID，但将同时适用于 Microsoft 云德国和 Office 365 服务终结点。  |
| 建立指向全局 STS 服务的本地 Get-authserver。 | 这样可确保迁移到 Microsoft 云德国的用户的请求对面向混合本地环境的 Exchange 可用性请求进行身份验证，以访问本地服务。 同样，这将确保从本地到 Office 365 服务终结点的请求的身份验证。 | 具有混合 (本地) 部署的 Exchange Online 客户 | Azure AD 迁移完成后，内部部署 Exchange (混合) 拓扑的管理员必须为 Office 365 服务添加新的身份验证服务终结点。 使用 Exchange PowerShell 中的此命令，将替换 `<TenantID>` 为您组织的租户 ID (在 **Azure Active Directory**) 上的 azure 门户中找到。 <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> 无法完成此任务可能会导致混合忙/闲请求无法为已从 Microsoft 云德国迁移到 Office 365 服务的邮箱用户提供信息。  |
| 迁移 Azure 资源。 | 使用 Office 365 和 Azure 资源的客户 (例如，网络、计算和存储) 将执行将资源迁移到 Office 365 服务实例。 此迁移是客户的责任。 消息中心发布将发出信号。 必须先完成迁移，然后才能在 Office 365 服务环境中终止 Azure AD 组织。 | Azure 客户 | 有关 Azure 迁移的详细内容，请参阅 Azure 迁移行动手册， [Azure 德国迁移指南概述](https://docs.microsoft.com/azure/germany/germany-migration-main)。 |
|||||

<!--
[Reference: Experience][Data Protection] Experience][
[Reference: Experience][Federation] 
[Reference: Experience][MFA]  


[Reference: Experience – Post Migration][Hybrid]    
        

[Reference: Experience – During Migration] [Azure] 
-->

### <a name="exchange-online"></a>Exchange Online

如果使用的是 **set-userphoto**：

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 新的德国区域将添加到现有的组织设置中，并将邮箱移动到 Office 365 服务。 | Exchange Online 配置将新的本地德语区域添加到正在转换的组织中。 此 Office 365 服务区域设置为默认值，这使内部负载平衡服务能够将邮箱重新分配到 Office 365 服务中的相应默认区域。 在此转换中，任何一侧 (德国或 Office 365 服务) 的用户都在同一组织中，并且可以使用 URL 终结点。 |  Exchange Online | 如果用户邮箱已迁移，但管理员邮箱尚未迁移，则管理员将无法运行 **set-userphoto**（PowerShell cmdlet）。 在这种情况下，管理员必须通过 `ConnectionUri` 使用以下语法在建立连接过程中传递其他字符串： <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> 其中 `<user_email>` ，是需要使用 **set-userphoto** 更改其照片的用户的电子邮件 ID 的占位符。 |
|||||

<!--
[Reference: Experience][Exchange Online]  [if using Set-UserPhoto] 
-->  

如果使用的是混合本地部署，请执行以下操作：

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
|停止或删除邮箱的任何载入或脱离移动。  | 这样可确保移动请求不会失败，并出现错误。 | 具有混合 (本地) 部署的 Exchange Online 客户 | 必需的操作。 如果不这样做，可能会导致服务或软件客户端出现故障。 |
|||||

<!--
[Reference: Experience][Hybrid] 
--> 


### <a name="dynamics"></a>Dynamics

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| Microsoft Dynamics 资源 | Microsoft Dynamics 的客户将参与工程或 FastTrack，以将动态转换为 Office 365 服务实例。 * | Microsoft Dynamics 365 客户 | -迁移后，管理员将对组织进行验证。 <br><br> -管理员根据需要修改工作流。 <br><br> -管理员根据需要清除 AdminOnly 模式。 <br><br> -管理员根据需要更改了 _沙箱_ 中的组织类型 <br><br> -通知最终用户新 URL (组织) 的访问实例。 <br><br> -更新到新终结点 URL 的任何入站连接。 <br><br> -在过渡期间，用户将无法使用 Dynamics 服务。 <br><br> -在迁移每个组织后，需要用户验证组织运行状况和功能。  |
|||||

\* (我) 使用 Microsoft Dynamics 365 的客户必须在此迁移方案中采取措施，如提供的迁移过程所定义。 客户执行操作时，)  (ii 将意味着 Microsoft 无法完成迁移。  (iii) 当 Microsoft 由于客户的 inaction 无法完成迁移时，客户的订阅将于2021年10月29日过期。 


### <a name="power-bi"></a>Power BI

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| Power BI 资源的迁移 | 在手动触发现有 PBI 迁移工具以将 Power BI 转换为 Office 365 服务实例后，将通过工程或 FastTrack 参与 Microsoft Power BI 的客户。\*\* | Microsoft Power BI 客户 | -将 _不_ 会转换以下 Power BI 项目，必须重新创建这些项目： <br><br> -实时数据集 (例如，流式传输或推送数据集) 。 <br> -Power BI 本地数据网关配置和数据源。 <br> -在迁移后，基于实时数据集生成的报告将不可用，并且需要重新创建。 <br><br> -Power BI 服务将在过渡期间对用户不可用。 服务不可用不应超过24个小时。 <br><br> -在迁移后，用户将需要使用 Power BI 服务重新配置数据源及其本地数据网关。  在执行此操作之前，用户将无法使用这些数据源对这些数据源执行计划的刷新和/或直接查询。 <br><br> -无法迁移 "容量" 和 "特优" 工作区。 客户需要在迁移前删除所有容量并在迁移后重新创建它们。 根据需要将工作区移回容量。  |
|||||

\*\* (我) 使用 Microsoft Power BI 的客户必须在此迁移方案中采取措施，如提供的迁移过程所定义。 客户执行操作时，)  (ii 将意味着 Microsoft 无法完成迁移。  (iii) 当 Microsoft 由于客户的 inaction 无法完成迁移时，客户的订阅将于2021年10月29日过期。 


### <a name="office-apps"></a>Office 应用程序

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 客户端，office Online 中的 office Online 切换时，Azure AD 将租户作用域终结以指向 Office 365 服务。 | 此配置更改使 Office 客户端能够更新并指向 Office 365 服务终结点。 | 所有 Office 客户 | -从客户拥有的 DNS 中删除 MSOID CName （如果存在）。 <br><br> -通知用户关闭 _所有_ Office 应用，然后重新登录 (或强制客户端重新启动，并强制用户登录) ，以使 Office 客户端能够选取更改。 <br><br> -通知用户和技术支持人员用户 *可能会* 看到一个 office 横幅，提示他们在发生转换的72小时内重新激活 office 应用。 <br><br> -必须关闭个人计算机上的所有 Office 应用程序，并且用户必须注销，然后重新登录。 在黄色激活栏中，登录以重新针对 Office 365 服务。 <br><br> -共享计算机将需要类似于个人计算机的操作，并且不需要特殊的过程。 <br><br> -在移动设备上，用户必须注销应用程序，关闭它们，然后重新登录。 |
|||||

<!--
[Reference: Experience][Office Apps]
--> 

## <a name="during-migration"></a>在迁移过程中


### <a name="exchange-online"></a>Exchange Online

对于电子数据展示：

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 在迁移过程中，电子数据展示搜索将失败或返回已迁移的 SharePoint Online、OneDrive for business 和 Exchange Online 位置的0个结果。 | 在迁移过程中，客户可以继续在 [安全 & 合规性中心](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)（包括 [内容搜索](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)）中创建事例、保留、搜索和导出。  但是，对已迁移的 SharePoint Online、OneDrive for Business 和 Exchange Online 位置的搜索将返回0个结果或产生一个错误。 若要获取修正，请参阅 _影响_ 列。 | 使用电子数据展示的所有客户 |  如果在迁移过程中搜索返回0个结果或错误，请对 SharePoint Online 执行以下操作： <br><br>  按照 [从 OneDrive 或 SharePoint 下载文件和文件夹](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)中的说明，直接从 SharePoint Online/OneDrive for business 网站下载网站。 此方法将需要 SharePoint Online 管理员权限或网站上的只读权限。 <br><br> 如果超出了 [从 OneDrive 或 SharePoint 的下载文件和文件夹](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)中所述的限制，客户可以使用 Onedrive for business 同步客户端，方法是按照 "将 [SharePoint 和团队文件与您的计算机同步](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)" 中的指南进行。 <br><br> -Exchange Online <br><br> - [Exchange Server 中的就地电子数据展示](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||

<!--
[Reference: Experience – During Migration][ [eDiscovery]
-->          


### <a name="sharepoint-online"></a>SharePoint Online

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| SharePoint 和 OneDrive 已转换。 | 在此阶段中，SharePoint 和 OneDrive 将从 Microsoft 云德国迁移到 Office 365 服务。 现有的 Microsoft 云德国 Url 将保留 (`contoso.sharepoint.de`) 。 Microsoft 云德国或 Office 365 服务颁发的令牌在转换过程中有效。 | SharePoint 客户 | Inflight SharePoint 2013 工作流在迁移过程中将会中断，并且在迁移后必须重新发布。 |
|||||

<!--
[Reference: Experience – During Migration][ [SPO]
-->  

### <a name="skype-for-business-online"></a>Skype for Business Online

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 将 Skype for Business 迁移到团队。 | 现有的 Skype for Business 客户将迁移到欧洲的 Office 365 服务，并在 Office 365 服务的德国地区转换为 Microsoft 团队。 | Skype for Business 客户 |  PowerShell 将用于管理租户和用户的设置和策略。 在连接到 PowerShell 会话时，请添加以下内容： <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||

<!--
[Reference: Experience – During Migration][ [SfBO]
-->  


## <a name="post-migration"></a>迁移后

### <a name="azure-ad"></a>Azure AD

对于混合：

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 更新 Azure AD Connect。 | 完成到 Azure AD 的切换后，组织完全使用 Office 365 服务，并且不再连接到 Microsoft 云德国。 在这种情况下，客户需要确保增量同步过程已完成，然后在此过程之后，将德国中的字符串值 `AzureInstance` (从 Microsoft Cloud) 更改为注册表路径中的 0 `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` 。 | 混合 Azure AD –连接的组织 | 更改 `AzureInstance` 注册表项的值。 如果不这样做，则会导致在 Microsoft 云德国终结点不再可用后，不会同步对象。 |
|||||

<!--
[Reference: Experience – Post Migration][Hybrid]
--> 

对于联合身份验证：

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 从 Microsoft 云德国 AD FS 删除信赖方信任。 | 完成到 Azure AD 的切换后，组织完全使用 Office 365 服务，并且不再连接到 Microsoft 云德国。 在这种情况下，客户需要删除对 Microsoft 云德国终结点的信赖方信任。 仅当将 Azure AD 用作标识提供程序 (IdP) 时，才可以执行此操作，而不会有客户的应用程序指向 Microsoft 云德国终结点。 | 联合身份验证组织 | 无。 |
|||||

<!--
[Reference: Experience – Post Migration][Federated]
-->             

对于 Azure AD：

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 如果原始请求未得到批准，则需要再次请求在迁移前的最后30天内加入 Azure AD 组的请求。 | 最终用户需要使用访问面板提交请求，以便在迁移之前的30天内未批准的请求再次加入 Azure AD 组。 | 在最近30天内未批准 Azure AD 组审批请求的最终用户。迁移前30天 |  作为最终用户： <ol><li>导航到 ["访问面板"](https://account.activedirectory.windowsazure.com/r#/joinGroups)。</li><li>在迁移前的30天内查找成员身份审批挂起的 Azure AD 组。</li><li>请求再次加入 Azure AD 组。</li></ol> 在迁移之前，不能批准在迁移前将处于活动状态少于30天的用户加入的请求，除非它们在迁移后重新请求。 |
|||||

<!--
[Reference: Experience – Post Migration][Azure AD]
--> 

对于 DNS：

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 更新适用于 Office 365 服务终结点的本地 DNS 服务。 | 指向 Office 365 德国的客户托管的 DNS 条目需要更新，以指向 Office 365 服务终结点。 | 所有 Office 客户 | 必需的操作。 如果不这样做，可能会导致服务或软件客户端出现故障。 |
|||||

<!--
 [Reference: Experience – Post Migration][DNS]
-->

对于 Office 365 服务终结点的第三方服务：

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 为 Office 365 服务终结点更新合作伙伴和第三方服务。 | -指向 Office 365 德国的第三方服务和合作伙伴需要更新，以指向 Office 365 服务终结点。 示例：重新注册，与供应商和合作伙伴保持一致，应用程序的库应用版本（如果可用）。 <br><br> -将利用 Graph API 的所有自定义应用程序指向 `graph.microsoft.de` `graph.microsoft.com` 。 其他具有更改的终结点的 Api 也需要更新（如果利用）。 <br><br> -更改所有非第三方企业应用程序以重定向到全球终结点。  | 所有 Office 客户 | 必需的操作。 如果不这样做，可能会导致服务或软件客户端出现故障。 |
|||||

<!--
 [Reference: Experience – Post Migration][]
--> 

### <a name="exchange-online"></a>Exchange Online

如果使用的是混合 Exchange 配置：

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 对 Office 365 服务 (HCW) 重新运行 "混合配置" 向导。 | 现有的 HCW 配置旨在支持 Microsoft 云德国。 在 Exchange 服务迁移完成的情况下，我们会将本地配置与 Microsoft 云德国进行分离。 | 正在运行混合部署的 Exchange Online 客户 | -必需的操作。 如果不这样做，可能会导致服务或软件客户端出现故障。 在开始迁移 Exchange 邮箱 (之前有5天或更多次的通知) ，请通知客户端应停止并删除其邮箱的任何载入或脱离移动。  如果不是，他们将在移动请求中看到错误。 <br><br> -Exchange 邮箱迁移完成后，通知客户端他们可以恢复加入和脱离移动。 <br> 在从 Microsoft 云德国迁移到 Office 365 服务期间，运行 **MigrationServerAvailabiilty**（PowerShell cmdlet）可能不起作用。 但是，迁移完成后，它将正常工作。 <br><br> 如果客户端在迁移邮箱后遇到凭据或授权问题，则用户可以通过运行来在迁移终结点中重新输入其内部部署管理员凭据 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` ，或者通过使用 Exchange 控制面板 (ECP) 设置相同的设置。  |

<!--
[Reference: Experience – Post Migration][Hybrid]  
[Reference: Experience – Post Migration][Exchange Online]
--> 

对于电子数据展示：

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
|  所有 SharePoint Online、OneDrive for Business 和 Exchange Online 位置均已迁移，同时 (SCC) 的安全与合规中心。 | 应从全球租户运行所有电子数据展示活动。 搜索现在将为100% 成功。  任何失败或错误都应遵循正常的支持通道。 | 使用电子数据展示的所有客户 | 无。 |
| 删除在迁移前步骤中创建的组织范围的保留策略 | 客户可以删除在客户迁移前工作中创建的组织范围的保留策略。 | 在迁移前步骤中应用保留策略的所有客户。 | 无。 |
|||||

<!--
 [Reference: Experience – Post Migration][ [eDiscovery]             

[Reference: Experience – Post Migration][ [eDiscovery]
-->             

### <a name="sharepoint-online"></a>SharePoint Online

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 重新发布 SharePoint 2013 工作流。 | 在迁移前的工作中，我们减少了 SharePoint 2013 工作流的数量。 现在完成迁移，客户可以重新发布工作流。 | 所有 Office 客户 | 这是必需的操作。 如果不这样做，可能会导致用户混淆和技术支持呼叫。 |
| 通过 Outlook 共享项目 | 在租户转换后，通过 Outlook 共享项目将不再起作用。 | SharePoint Online 和 OneDrive for Business | -在 SharePoint Online 和 OneDrive for business 中，可以通过 Outlook 共享项目。 按 Outlook 按钮后，会创建一个可共享的链接并将其推送到 Outlook Web App 中的新邮件中。 <br><br> -租户转换后，此共享方法将不起作用。 我们认识到这是一个已知问题。 但是，由于此 Outlook 功能位于弃用的路径中，因此在弃用即将推出之前，不会计划修复该问题。 |

<!--
 [Reference: Experience – Post Migration][ [SPO]
-->

## <a name="next-step"></a>后续步骤

[了解迁移阶段的操作和影响](ms-cloud-germany-transition-phases.md)

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
