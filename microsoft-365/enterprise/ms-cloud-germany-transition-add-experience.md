---
title: 从德国 Microsoft 云迁移的迁移后活动
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
description: 摘要：从德国 Microsoft 云 (德国) 迁移到新的德国数据中心区域中的 Office 365 服务的迁移后活动。
ms.openlocfilehash: 745589c1c997540094fc4a770e437de89015f88a
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591752"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>从德国 Microsoft 云迁移的迁移后活动

以下各节提供从德国 Microsoft 云迁移到新的德国数据中心 (Office 365 服务) 多个服务的迁移后活动。

## <a name="azure-ad"></a>Azure AD

### <a name="azure-ad-connect"></a>Azure AD Connect
**适用于：** 所有客户使用 Azure AD 连接同步标识

| 步骤 (步骤)  | Description | 影响 |
|:-------|:-------|:-------|
| 更新 Azure AD Connect。 | 完成到 Azure AD 的剪切后，组织将完全使用 Office 365 服务，并且不再连接到德国 Microsoft 云。 此时，客户需要确保增量同步过程已完成，此后，在注册表路径 中将字符串值从 3 (Microsoft 云德国) 更改为 `AzureInstance` `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` 0。 | 更改 注册表 `AzureInstance` 项 的值。 如果不这样做，将导致在 Microsoft 云德国终结点不再可用后对象无法同步。 |
|||||

### <a name="azure-ad-federated-authentication-with-ad-fs"></a>使用 AD FS 的 Azure AD 联合身份验证
**适用于：** 使用 AD FS 联合身份验证的所有客户

| 步骤 (步骤)  | Description | 影响 |
|:-------|:-------|:-------|
| 从 Microsoft 云德国 AD FS 中删除信赖方信任。 | 完成到 Azure AD 的切分后，组织将完全使用 Office 365 服务，并且不再连接到德国 Microsoft 云。 此时，客户需要删除对德国 Microsoft 云终结点的信赖方信任。 只有在将 Azure AD 用作标识提供程序 (IdP) 时，客户的应用程序均不指向德国 Microsoft 云终结点，才能完成此操作。 | 联合身份验证组织 | 无。 |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a>组审批
**适用于：** 迁移前的最后 30 天内未批准其 Azure AD 组审批请求的最终用户 

| 步骤 (步骤)  | Description | 影响 |
|:-------|:-------|:-------|
| 如果原始请求未获得批准，则需要再次请求迁移前 30 天内加入 Azure AD 组的请求。 | 如果迁移前的最后 30 天内未批准这些请求，最终用户客户将需要使用访问面板再次提交加入 Azure AD 组的请求。 |  作为最终用户： <ol><li>导航到 ["访问"面板](https://account.activedirectory.windowsazure.com/r#/joinGroups)。</li><li>查找在迁移前 30 天内等待其成员身份审批的 Azure AD 组。</li><li>再次请求加入 Azure AD 组。</li></ol> 在迁移前 30 天内加入活动组的请求无法获得批准，除非迁移后再次请求。 |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
## <a name="custom-dns-updates"></a>自定义 DNS 更新
**适用于：**  管理自己的 DNS 区域的所有客户

| 步骤 (步骤)  | Description | 影响 |
|:------|:-------|:-------|
| 为 Office 365 服务终结点更新本地 DNS 服务。 | 指向德国 Microsoft 云的客户托管 DNS 条目需要更新为指向 Office 365 全局服务终结点。 | 如果不这样做，可能会导致服务或软件客户端失败。 |
||||

## <a name="third-party-services"></a>第三方服务
**适用于：** 为 Office 365 服务终结点使用第三方服务的客户

| 步骤 (步骤)  | Description | 影响 |
|:-------|:-------|:-------|
| 更新 Office 365 服务终结点的合作伙伴和第三方服务。 | <ul><li>指向 Office 365 Germany 的第三方服务和合作伙伴需要进行更新，以指向 Office 365 服务终结点。 示例：重新注册应用程序库应用版本（如果可用）以与供应商和合作伙伴一致。 </li><li>将利用 Graph API 的所有自定义应用程序从 指向 `graph.microsoft.de` `graph.microsoft.com` 。 如果利用，还需要更新终结点已更改的其他 API。 </li><li>更改所有非第一方企业应用程序以重定向到全球终结点。 </li></ul>| 必需操作。 如果不这样做，可能会导致服务或软件客户端失败。 |
||||

## <a name="sharepoint-online"></a>SharePoint Online
**适用于：** 使用 SharePoint 2013 工作流的客户

| 步骤 (步骤)  | Description | 影响 |
|:-------|:-------|:-------|
| 重新发布 SharePoint 2013 工作流。 | 在迁移前工作中，我们减少了 SharePoint 2013 工作流的数量。 迁移完成后，客户可以重新发布工作流。 | 这是一项必需操作。 如果不这样做，可能会导致用户混淆和技术支持呼叫。 |
| 通过 Outlook 共享项目 | 租户切换后，通过 Outlook 共享 SharePoint Online 和 OneDrive for Business 中的项目不再起作用。 |<ul><li>在 SharePoint Online 和 OneDrive for Business 中，可以通过 Outlook 共享项目。 按 Outlook 按钮后，会创建一个可共享的链接，并推送到邮件Outlook Web App。</li><li>租户转换后，这种共享方法将不起作用。 我们意识到这是一个已知问题。 但是，由于此 Outlook 功能位于弃用路径中，因此在推出弃用之前，不会计划修复问题。 </li></ul>|
||||

## <a name="exchange-online"></a>Exchange Online
**适用于：** 使用混合 Exchange 配置的客户

| 步骤 (步骤)  | Description | 影响 |
|:-------|:-------|:-------|
| 针对 Office 365 服务 (HCW) 重新运行混合配置向导。 | 现有 HCW 配置旨在支持德国 Microsoft 云。 完成 Exchange 服务的迁移后，我们将本地配置与德国 Microsoft 云分离。 |<ul><li>必需操作。 如果不这样做，可能会导致服务或软件客户端失败。 在 Exchange 邮箱迁移 (5 天或 5) ，通知客户端应停止并删除其邮箱的任何载入或载出移动。  如果没有，他们将在移动请求中看到错误。 </li><li>Exchange 邮箱迁移完成后，通知客户端他们可以恢复载入和载出移动。 <br> 在将 Exchange 从德国 Microsoft 云迁移到 Office 365 服务期间，运行 **Test-MigrationServerAvailabiilty（PowerShell** cmdlet）可能不起作用。 但是，迁移完成后它将正常工作。 </li><li>如果客户端在迁移邮箱后遇到凭据或授权问题，则用户可以通过运行 或通过使用 Exchange 控制面板 (ECP) ，在迁移终结点中重新输入其本地管理员 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` 凭据。 </li></ul>|
