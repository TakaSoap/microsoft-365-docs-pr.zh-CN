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
description: 摘要：从德国 Microsoft 云迁移到新的德国数据中心 (德国) Office 365 服务时的其他客户体验信息。
ms.openlocfilehash: ecc549ca4d0bb8122de3bf092c004c919e958d5e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165641"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>迁移阶段操作和影响从德国 Microsoft 云 (高级) 

从德国 Microsoft 云到 Microsoft Office 365 服务德国地区的租户迁移作为一组阶段执行，并针对每个工作负载执行其配置的操作。 此图显示了迁移到新的德国数据中心的九个阶段。

![迁移到新德国数据中心的九个阶段](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

以下各节提供有关从德国 Microsoft 云 (德国) 迁移到新的德国数据中心区域 Office 365 服务的客户体验的其他信息。

## <a name="office-365-portal-services-between-phase-2-and-phase-3"></a>第 2 阶段至第 3 阶段的 Office 365 门户服务

在第 2 阶段至第 3 阶段之间，合作伙伴门户可能无法访问。 在此期间，合作伙伴可能无法访问合作伙伴门户上的租户信息。 由于每次迁移都不同，因此辅助功能的持续时间可能为小时。

### <a name="ediscovery-phase-4-to-the-end-of-phase-9"></a>电子数据展示阶段 4 至阶段 9 结束

**适用于：** 使用电子数据展示的所有客户

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 从阶段 4 开始到阶段 9 完成，电子数据展示搜索将失败或返回已迁移的 SharePoint Online、OneDrive for Business 和 Exchange Online 位置的 0 个结果。 | 在迁移过程中，客户可以在安全与合规中心（包括内容搜索）&案例、保留、 [搜索](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)和 [导出](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)。 但是，针对已迁移的 SharePoint Online、OneDrive for Business 和 Exchange Online 位置的搜索将返回 0 个结果或产生错误。 有关修正， _请参阅影响列_ 。 | 如果搜索在迁移过程中返回零结果或错误，请对 SharePoint Online 执行以下操作： <ul><li>按照从 OneDrive 或 SharePoint 下载文件和文件夹中的说明，直接从 SharePoint Online 或 OneDrive for Business 网站 [下载网站](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)。 此方法需要 SharePoint Online 管理员权限或网站的只读权限。</li><li>如果超出限制，如从 OneDrive 或 [SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)下载文件和文件夹中介绍，客户可以按照将 SharePoint 和 Teams 文件与计算机同步中的指导使用 OneDrive for Business [同步客户端](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)。</li><li>有关详细信息，请参阅  [In-Place eDiscovery in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
||||

## <a name="exchange-online-set-userphoto-during-phase-5"></a>阶段 5 Set-UserPhoto Exchange Online 服务

**适用于：** 在 Exchange Online 中存储用户照片且正在使用 **Set-UserPhoto 的所有客户**：

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 新区域"Germany"将添加到现有 Exchange Online 组织设置中，邮箱将移动到 Office 365 服务。 | Exchange Online 配置将新的德国本地区域添加到转换组织。 此 Office 365 服务区域设置为默认区域，这允许内部负载平衡服务将邮箱重新分发到 Office 365 服务中的相应默认区域。 在此转换中，位于德国 (或 Office 365) 位于同一组织中，并且可以使用任一 URL 终结点。 | 如果用户邮箱已迁移，但尚未迁移管理员邮箱，则管理员将无法运行 **Set-UserPhoto**（PowerShell cmdlet）。 在这种情况下，管理员必须在连接设置期间通过以下语法传递其他 `ConnectionUri` 字符串： <br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br> 其中 `<user_email>` 是需要通过使用 **Set-UserPhoto** 更改其照片的用户的电子邮件 ID 的占位符。 |
||||

## <a name="post-migration"></a>迁移后

### <a name="azure-ad-phase-9"></a>Azure AD 阶段 9

**适用于：** 所有客户使用 Azure AD 连接同步标识

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 更新 Azure AD Connect。 | 完成到 Azure AD 的剪切后，组织将完全使用 Office 365 服务，并且不再连接到德国 Microsoft 云。 此时，客户需要确保增量同步过程已完成，此后，在注册表路径 中将字符串值从 3 (Microsoft 云德国) 更改为 `AzureInstance` `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` 0。 | 更改 注册表 `AzureInstance` 项 的值。 如果不这样做，将导致在 Microsoft 云德国终结点不再可用后对象无法同步。 |
|||||

**适用于：** 使用 ADFS 联合身份验证的所有客户

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 从 Microsoft 云德国 AD FS 中删除信赖方信任。 | 完成到 Azure AD 的切分后，组织将完全使用 Office 365 服务，并且不再连接到德国 Microsoft 云。 此时，客户需要删除对德国 Microsoft 云终结点的信赖方信任。 只有在将 Azure AD 用作标识提供程序 (IdP) 时，客户的应用程序均不指向德国 Microsoft 云终结点，才能完成此操作。 | 联合身份验证组织 | 无。 |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**适用于：** 迁移前的最后 30 天内未批准其 Azure AD 组审批请求的最终用户 

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 如果原始请求未获得批准，则需要再次请求迁移前 30 天内加入 Azure AD 组的请求。 | 如果迁移前的最后 30 天内未批准这些请求，最终用户客户将需要使用访问面板再次提交加入 Azure AD 组的请求。 |  作为最终用户： <ol><li>导航到 ["访问"面板](https://account.activedirectory.windowsazure.com/r#/joinGroups)。</li><li>查找在迁移前 30 天内等待其成员身份审批的 Azure AD 组。</li><li>再次请求加入 Azure AD 组。</li></ol> 在迁移前 30 天内加入活动组的请求无法获得批准，除非迁移后再次请求。 |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**适用于：**  管理自己的 DNS 区域的所有客户

| 步骤 (步骤)  | 说明 | 影响 |
|:------|:-------|:-------|
| 为 Office 365 服务终结点更新本地 DNS 服务。 | 指向德国 Microsoft 云的客户托管 DNS 条目需要更新为指向 Office 365 全局服务终结点。 | 如果不这样做，可能会导致服务或软件客户端失败。 |
||||

**适用于：** 为 Office 365 服务终结点使用第三方服务的客户

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 更新 Office 365 服务终结点的合作伙伴和第三方服务。 | <ul><li>指向 Office 365 Germany 的第三方服务和合作伙伴需要进行更新，以指向 Office 365 服务终结点。 示例：重新注册应用程序库应用版本（如果可用）以与供应商和合作伙伴一致。 </li><li>将利用 Graph API 的所有自定义应用程序从 指向 `graph.microsoft.de` `graph.microsoft.com` 。 如果利用，还需要更新终结点已更改的其他 API。 </li><li>更改所有非第一方企业应用程序以重定向到全球终结点。 </li></ul>| 必需操作。 如果不这样做，可能会导致服务或软件客户端失败。 |
||||

### <a name="sharepoint-online-post-migration"></a>迁移后 SharePoint Online

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 重新发布 SharePoint 2013 工作流。 | 在迁移前工作中，我们减少了 SharePoint 2013 工作流的数量。 迁移完成后，客户可以重新发布工作流。 | 这是一项必需操作。 如果不这样做，可能会导致用户混淆和技术支持呼叫。 |
| 通过 Outlook 共享项目 | 租户切换后，通过 Outlook 共享 SharePoint Online 和 OneDrive for Business 中的项目不再起作用。 |<ul><li>在 SharePoint Online 和 OneDrive for Business 中，可以通过 Outlook 共享项目。 按 Outlook 按钮后，会创建一个可共享的链接，并推送到邮件Outlook Web App。</li><li>租户转换后，这种共享方法将不起作用。 我们意识到这是一个已知问题。 但是，由于此 Outlook 功能位于弃用路径中，因此在推出弃用之前，不会计划修复问题。 </li></ul>|
||||

### <a name="exchange-online-post-migration"></a>Exchange Online 迁移后

如果使用的是混合 Exchange 配置：

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 针对 Office 365 服务 (HCW) 重新运行混合配置向导。 | 现有 HCW 配置旨在支持德国 Microsoft 云。 完成 Exchange 服务的迁移后，我们将本地配置与德国 Microsoft 云分离。 |<ul><li>必需操作。 如果不这样做，可能会导致服务或软件客户端失败。 在 Exchange 邮箱迁移 (5 天或 5) ，通知客户端应停止并删除其邮箱的任何载入或载出移动。  如果没有，他们将在移动请求中看到错误。 </li><li>Exchange 邮箱迁移完成后，通知客户端他们可以恢复载入和载出移动。 <br> 在将 Exchange 从德国 Microsoft 云迁移到 Office 365 服务期间，运行 **Test-MigrationServerAvailabiilty（PowerShell** cmdlet）可能不起作用。 但是，迁移完成后它将正常工作。 </li><li>如果客户端在迁移邮箱后遇到凭据或授权问题，则用户可以通过运行 或通过使用 Exchange 控制面板 (ECP) ，在迁移终结点中重新输入其本地管理员 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` 凭据。 </li></ul>|

### <a name="ediscovery-post-migration"></a>迁移后电子数据展示

**适用于：** 使用电子数据展示的所有客户

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
|  所有 SharePoint Online、OneDrive for Business 和 Exchange Online 位置已随安全与合规中心 (SCC) 。 | 所有电子数据展示活动都应从全球租户运行。 搜索现在将 100% 成功。  任何失败或错误应遵循正常支持渠道。 | 无 |
||||

**适用于：**  作为迁移前步骤的一部分应用保留策略的所有客户

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 删除在迁移前步骤期间创建的组织范围内的保留策略 | 客户可以删除在客户迁移前工作期间创建的组织范围的保留策略。 | 无 |
||||

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
- [其他前期工作](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。

云应用：

- [Dynamics 365 迁移计划信息](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 迁移计划信息](/power-bi/admin/service-admin-migrate-data-germany)
- [开始 Microsoft Teams 升级](/microsoftteams/upgrade-start-here)