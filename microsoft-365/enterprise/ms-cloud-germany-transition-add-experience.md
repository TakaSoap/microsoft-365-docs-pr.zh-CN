---
title: 从德国 Microsoft 云迁移的迁移后活动
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：从德国 Microsoft 云迁移到新的德国数据中心 (Microsoft 云) Office 365迁移后活动。
ms.openlocfilehash: 349b9aa756a67d823e95ec2d999a04b12863d0fb
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2021
ms.locfileid: "60586201"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>从德国 Microsoft 云迁移的迁移后活动

以下各节提供从德国 Microsoft 云迁移到新的德国数据中心区域 (德国 microsoft 云) Office 365多个服务的迁移后活动。

## <a name="azure-ad"></a>Azure AD
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a>Azure AD AD FS 进行联合身份验证
**适用于：** 使用 AD FS 联合身份验证的所有客户

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 从 Microsoft 云德国 AD FS 中删除信赖方信任。 | 完成到德国Azure AD后，组织将完全使用Office 365服务，并且不再连接到德国 Microsoft 云。 此时，客户需要删除对德国 Microsoft 云终结点的信赖方信任。 只有在将 Azure AD 用作标识提供程序或 IdP) 时，客户的应用程序均不指向德国 Microsoft 云终结点，才能 (此操作。 | 联合身份验证组织 | 
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a>组审批
**适用于：** 迁移前Azure AD 30 天内未批准其组审批请求的最终用户 

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 如果原始请求Azure AD批准，则需要再次请求迁移前 30 天内加入组的请求。 | 如果迁移前的最后 30 天内未批准这些请求，最终用户客户将需要使用访问面板再次提交加入 Azure AD 组的请求。 |  作为最终用户： <ol><li>导航到 ["访问"面板](https://account.activedirectory.windowsazure.com/r#/joinGroups)。</li><li>查找一Azure AD迁移前 30 天内其成员身份审批挂起的组。</li><li>再次请求加入Azure AD组。</li></ol> 在迁移前 30 天内加入活动组的请求无法获得批准，除非迁移后再次请求。 |
||||

## <a name="custom-dns-updates"></a>自定义 DNS 更新
**适用于：**  管理自己的 DNS 区域的所有客户

| 步骤 (步骤)  | 说明 | 影响 |
|:------|:-------|:-------|
| 更新本地 DNS 服务以Office 365服务终结点。 | 指向德国 Microsoft 云的客户托管 DNS 条目需要更新为指向 Office 365 全局服务终结点。 请参阅域中[的域Microsoft 365 管理中心](https://admin.microsoft.com/Adminportal/Home#/Domains)并应用 DNS 配置中的更改。 | 如果不这样做，可能会导致服务或软件客户端失败。 |
||||
   > [!NOTE]
   > 该Microsoft 365 管理中心将指示转换客户为) 区域下的新域设置邮件交换 (MX outlook.de 记录。 示例：consoto-com.mail.protection.outlook.de。 对于新域，将自定义 MX 记录指向的预期/正确值位于 outlook.com 下。 使用同一示例，正确的条目 consoto-com.mail.protection.outlook.com。 正在进行修复，以更正已转换组织的域的此行为。
   
## <a name="third-party-services"></a>第三方服务
**适用于：** 将第三方服务用于 Office 365 服务终结点的客户

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 更新合作伙伴和第三方服务，Office 365服务终结点。 | <ul><li>指向德国的第三方服务和合作伙伴Office 365更新为指向 Office 365 服务终结点。 示例：重新注册应用程序库应用程序版本（如果可用）以与供应商和合作伙伴一致。 </li><li>将利用 api 的所有自定义Graph从 指向 `graph.microsoft.de` `graph.microsoft.com` 。 如果利用，还需要更新终结点已更改的其他 API。 </li><li>更改所有非第一方企业应用程序以重定向到全球终结点。 </li></ul>| 必需操作。 如果不这样做，可能会导致服务或软件客户端失败。 |
||||
