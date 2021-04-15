---
title: 从德国 Microsoft 云迁移的迁移前活动
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
ms.openlocfilehash: ce7aad932482d7a9d1681957c06b85ab22a82149
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760388"
---
# <a name="pre-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>从德国 Microsoft 云迁移的迁移前活动

使用这些链接可了解与组织相关的迁移前步骤。

如果你使用的是

- **德国 Microsoft 云中的 Office 365** 执行 [以下步骤](#general-tenant-migration-considerations)。
- **自定义域**，执行 [此步骤](#dns-entries-for-custom-domains)。

- **SharePoint Online，** 执行 [此步骤](#sharepoint-online)。
- **Exchange Online** 或 **Exchange 混合，** 执行 [此步骤](#exchange-online)。
- **Skype for Business Online**，请 [执行此步骤](#skype-for-business-online)。
- **Dynamics 365，**[执行此步骤](#dynamics365)。
- **Power BI，** 执行 [此步骤](#power-bi)。

- Azure AD Connect 的 **Active Directory** 联合身份验证服务，执行 [以下步骤](#active-directory-federation-services-ad-fs)。
- **与** Office 365 集成的第三方服务或业务 (**LOB)** 应用执行 [此步骤](#line-of-business-apps)。
- MDM 解决方案的第三方移动设备 (，) 执行 [此步骤](#mobile-device-management)。
- **使用 Office** 365 订阅的 Azure 服务，执行 [此步骤](#microsoft-azure)。

## <a name="general-tenant-migration-considerations"></a>一般租户迁移注意事项

**适用于：** 在 Microsoft 德国云实例中使用 Office 365 的所有客户

迁移期间将保留 Office 365 租户和用户标识符。 Azure AD 服务调用从德国 Microsoft 云重定向到 Office 365 全局服务，并且对于 Office 365 服务是透明的。

- GDPR (一) 数据保护条例 (DSR) 从 Azure 管理门户执行，供将来请求使用。 在 30 天后或之前，将删除位于德国 Microsoft 云的任何旧诊断数据或非客户诊断数据。
- 当租户复制到 Office 365 (时，使用 Microsoft Authenticator 的多重身份验证) 请求显示为用户 ObjectID (GUID) 。 尽管存在此显示行为，但 MFA 请求将如期执行。  使用 Office 365 服务终结点激活的 Microsoft Authenticator 帐户将显示 UPN (用户) 。  使用德国 Microsoft 云终结点添加的帐户将显示用户 ObjectID，但将同时用于德国 Microsoft 云和 Office 365 服务终结点。

| 步骤 (步骤)  | 描述 | 影响 |
|:-------|:-------|:-------|
| 准备通知用户迁移后重启客户端并登录和退出客户端。 | 迁移过程中，Office 客户端许可将从德国 Microsoft 云转换为 Office 365 服务。 客户端在退出并登录 Office 客户端后获取新的有效许可证。 | 用户的 Office 产品需要刷新 Office 365 服务中的许可证。 如果未刷新许可证，Office 产品可能会遇到许可证验证错误。 |
| 确保与 [Office 365 服务 URL 和 IP 地址的网络连接](https://aka.ms/o365urls)。 | 客户托管用于访问 Office 365 服务的所有客户端和服务都必须能够访问 Office 365 全局服务终结点。 <br>如果你或你的协作伙伴具有防火墙规则，阻止访问 [Office 365](https://aka.ms/o365urls) 服务 URL 中列出的 URL 和 IP 地址，则 IP 地址必须更改防火墙规则以允许访问 Office 365 全局服务终结点| 如果未在阶段 4 之前完成此操作，则可能会发生服务或客户端软件故障  |
| 取消任何试用订阅。 | 试用版订阅将不会迁移，并且将阻止传输付费订阅。 | 如果取消后用户访问试用服务，则试用服务已过期且无法正常工作。 |
| 分析德国 Microsoft 云与 Office 365 全球服务之间的许可证功能差异。 | Office 365 服务包括当前德国 Microsoft 云中不可用的其他功能和服务。 在订阅转移期间，用户可以使用新功能。 | <ul><li> 分析 Microsoft 云德国和 Office 365 全球服务的许可证提供的不同功能。 从 Office [365 平台服务说明开始](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)。 </li><li> 确定是否应最初禁用 Office 365 服务的任何新功能，以限制对用户或用户更改管理的影响，并根据需要更改用户许可证分配。 </li><li>为用户和技术支持人员准备 Office 365 服务提供的新服务和功能。 |
| 创建组织范围的 [保留策略](https://docs.microsoft.com/microsoft-365/compliance/retention) ，防止在迁移过程中意外删除内容。  |<ul><li>为确保最终用户不会在迁移过程中意外删除内容，客户可以选择启用组织范围的保留策略。 </li><li>尽管不需要保留，因为迁移过程中随时设置保留应按预期工作，但保留策略是一种备份安全机制。 同时，保留策略可能不会由所有客户使用，尤其是关注保留的客户。</li></ul>| 应用保留策略，如 [了解保留策略和保留标签中所述](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)。 如果未在阶段 4/9 之前完成此操作，则可能会发生服务或客户端软件故障。 </li></ul>|
|||||

## <a name="dns-entries-for-custom-domains"></a>自定义域的 DNS 条目

<!-- before phase 9 -->

**适用于：** 在其自己的 DNS 域中设置 _自定义 msoid_ CNAME 或在 Exchange Online 使用域的客户

如果配置 _，msoid_ CNAME 将仅影响使用 Office 桌面客户端 (Microsoft 365 应用版、Office 365 专业增强版、Office 2019、2016...) 的客户。

如果你拥有一个或多个 DNS 命名空间中设置了名为 _msoid_ 的 DNS CNAME，必须删除 CNAME，直到最晚阶段 8 结束。 可以在阶段 8 结束之前随时删除 CNAME _msoid。_

若要验证是否在你的 DNS 命名空间中设置了 CNAME，请按照以下步骤操作，contoso.com替换为你自己的域名：

```console
nslookup -querytype=CNAME msoid.contoso.com
```

如果命令行返回 DNS 记录，请从 _域中删除 msoid_ CNAME。

> [!NOTE]
> 如果对 Exchange Online 使用自定义域，则需要具有对 DNS 托管提供商的访问权限。 请确保可以访问和编辑 DNS 设置，您将在迁移过程中修改 DNS 记录。

## <a name="active-directory-federation-services-ad-fs"></a>Active Directory 联合身份验证服务 (AD FS)

<!-- before phase 4 -->

**适用于：** 使用本地 AD FS 验证连接到 Microsoft Office 365 的用户的客户<br>
**应用时**：阶段 4 之前的任何时间

阅读和应用 [ADFS 迁移步骤](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

<!-- before phase 4 -->

**适用于：** 使用本地 SharePoint 2013 的客户<br>
**应用时**：阶段 4 之前的任何时间

| 步骤 (步骤)  | 描述 | 影响 |
|:-------|:-------|:-------|
| 限制 SharePoint 2013 工作流，在 SharePoint Online 迁移过程中使用。 | 在转换之前减少 SharePoint 2013 工作流并完成运行中的工作流。 | 不操作可能会导致用户混淆和技术支持呼叫。 |
||||

## <a name="exchange-online"></a>Exchange Online

<!-- before phase 5 -->

**适用于：Exchange** Online 客户<br>
**应用时**：阶段 9 结束之前的任何时间

| 步骤 (步骤)  | 描述 | 影响 |
|:-------|:-------|:-------|
| 通知外部合作伙伴即将过渡到 Office 365 服务。 |  客户必须通知已启用共享日历和可用性地址空间配置的合作伙伴， (Office 365 商业版共享忙/闲) 。 完成 Exchange Online 迁移后，可用性配置需要转换以使用 [Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide) 全球终结点。 | 如果不这样做，可能会导致客户迁移的稍后阶段出现服务或客户端故障。 |
| 通知用户所需的 IMAP4/POP3/SMTP 客户端更改。 | 对于客户端协议 IMAP4、POP3、SMTP，具有 Microsoft 云德国终结点的设备连接的用户需要手动更新其客户端设备以切换到 [Exchange Online 服务器名称](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/pop3-and-imap4#settings-users-use-to-set-up-pop3-or-imap4-access-to-their-exchange-online-mailboxes)。 | 预先向这些协议的用户传达此依赖关系，并确保他们在此迁移期间切换为使用 Outlook Mobile 或 Outlook 网页版。 迁移用户邮箱时，更新客户端终结点失败将导致德国 Microsoft 云的客户端连接失败。 |
||||

### <a name="exchange-online-hybrid-customers"></a>Exchange Online 混合客户

**适用于：** 将活动 Exchange 混合配置与本地 Exchange 服务器一同使用的所有客户<br>
**应用时**：阶段 5 之前的任何时间

具有 Exchange Online 混合部署和本地 Exchange Server 的企业客户运行混合配置向导 (HCW) 和 AAD Connect 来维护和建立混合设置。 作为此转换的一部分，Exchange Online 混合管理员 ( **HCW**) 多次执行混合配置向导。 从德国 Microsoft 云过渡到 Office 365 Germany 区域时，管理员必须在 Exchange 迁移 (第 5 阶段) 开始之前，在"Office 365 Germany"模式下重新运行 HCW 的最新内部版本。 然后，在第 5 阶段完成时，再次以"Office 365 全球"模式运行 HCW，以使用 Office 365 Germany 区域设置完成本地部署。 HCW 运行在第 5 阶段期间不得执行，在阶段 5 完成之前运行 HCW 很重要。
目录属性通过 AAD Connect 与本地部署在 Office 365 和 Azure AD 之间同步。 

| 步骤 (步骤)  | 描述 | 影响 |
|:-------|:-------|:-------|
| 使用 Office 365 Germany 设置重新运行 HCW <br><br> <i>收到消息中心通知 Office 365 租户迁移已开始后，你可以立即启动此活动， (第 1 阶段) 。</i>| 在第 5 阶段之前卸载并重新运行 HCW (17.0.5378.0 或更高版本) 将确保本地配置已准备好使用 Microsoft 云德国用户和迁移到 [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) Office 365 Germany 区域的用户发送和接收邮件。 <p><li> In the HCW， for the list box below **My Office 365 organization is hosted by**， select Office **365 Germany.** | 如果未能在阶段 5 [Exchange 迁移] 开始之前完成此任务，可能会导致本地 Exchange 部署和 Office 365 之间路由邮件的NDDR。  
| 保留共享邮箱设置 | 一些混合客户使用 Exchange Online 命令将云用户邮箱转换为"共享"邮箱。 此云邮箱配置将写入邮箱和本地 Exchange Online 目录，但是，它不会通过 AAD Connect 同步回客户的 Active Directory。 结果是邮箱 RemoteRecipientType 和 RemoteDisplayType 值的 Active Directory 表示形式与在 Exchange Online 中将邮箱定义为共享邮箱时存在差异。 <br><br> 客户负责确保使用 、或 正确预配所有共享 `New-RemoteMailbox -Shared` `Enable-RemoteMailbox -Shared` 邮箱 `Set-RemoteMailbox -Shared` 。  请参阅此参考，了解如何 [在混合环境中转换用户邮箱](/microsoft-365/admin/email/convert-user-mailbox-to-shared-mailbox?view=o365-worldwide)。| 在阶段 5 [Exchange Online 迁移] 之前未能完成此任务可能会导致共享邮箱的 NDR 转换回未授权邮箱，并丢失受影响邮箱的共享访问权限。 [在 Exchange](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes) 混合部署中运行目录同步后，共享邮箱意外转换为用户邮箱，其中概述了在 Exchange Online 迁移完成之前不解决这一问题的影响。  
||||

## <a name="skype-for-business-online"></a>Skype for Business Online

<!-- before phase 7 -->

**适用于：Skype** For Business Online 客户<br>
**应用时**：阶段 7 之前的任何时间

| 步骤 (步骤)  | 描述 | 影响 |
|:-------|:-------|:-------|
| 为在德国访问 Skype for Business 的用户部署 Teams 桌面客户端。 | 迁移将 Skype for Business 用户移至 Microsoft Teams 进行协作、通话和聊天。 部署 Microsoft Teams 桌面客户端或确保受支持的浏览器可用。 | 不操作将导致 Microsoft Teams 协作服务不可用。 |
| 查看并准备与迁移相关的 DNS 更改。 | Skype for Business Online 的客户拥有的 DNS 区域更改。 |<ul><li>建议将任何客户拥有的域 DNS 记录的生存时间 (TTL) 更新为 5 分钟，以加快 DNS 记录的刷新。 但是，与此 DNS 更改关联的 Microsoft 管理的转换可能在提供的 24 小时更改时段内随时发生。 </li><li>未来可能会中断服务。 用户将无法登录 Skype for Business，并重定向到 Office 365 服务中迁移的 Teams 体验。 </li></ul>|
| 准备最终用户和管理培训和准备过渡到 Microsoft Teams。 | 通过规划用户沟通和准备情况，成功从 Skype 过渡到 Teams。 | <ul><li>客户端需要了解新服务，以及一旦其服务转换到 Office 365 服务后如何使用。 </li><li>在客户虚域和初始域都进行了 DNS 更改后，用户将登录到 Skype for Business，并看到他们现在已迁移到 Teams。 这还会在后台下载 Teams 桌面客户端。 </li></ul>|
||||

## <a name="mobile-device-management"></a>移动设备管理

<!-- before phase 5 -->
**适用于：** 使用 MDM 解决方案的第三方移动设备 () 客户<br>
**应用时**：阶段 5 之前的任何时间

| 步骤 (步骤)  | 描述 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 准备最终用户和管理培训，了解用户删除帐户并重新将其帐户添加到 Microsoft Outlook for iOS 和 Outlook for Android。 | 使用德国 Microsoft 云中的邮箱配置的 Microsoft Outlook for iOS 和 Android 帐户可能需要删除并再次添加到 Outlook，才能正确同步新的 Office 365 服务配置。 | Microsoft Outlook for iOS 和 Android 客户 | 以前为德国 Microsoft 云配置的 Outlook 邮箱可能不会选取新的 Office 365 服务配置，从而导致其他用户体验的错误和性能下降。 如果迁移后出现登录或同步邮件的问题，建议 IT 管理员提供文档，以主动指示用户删除帐户，并将其添加到 Microsoft Outlook for iOS 和 Outlook for Android。 |
| 确定迁移后是否要求任何重新配置。 | 移动设备管理 (MDM) 解决方案可能面向 `outlook.de` 终结点。 在此到 Office 365 服务的转换中，客户端配置文件应更新为 Office 365 服务 `outlook.office365.com` URL。 | Exchange Online 和 MDM 客户 | 当终结点可访问时，客户端可能会继续运行，但如果 Microsoft 云德国终结点不再可用，客户端将 `outlook.de` 失败。 |
|||||

## <a name="line-of-business-apps"></a>业务线应用

**适用于：** 使用业务线或 LOB (LOB) Microsoft 云德国提供终结点的应用<br>
**应用后**：阶段 2 完成之后和阶段 9 结束之前

如果使用的是与 Office 365 集成的第三方服务或业务线 (LOB) 应用，则必须解决 Microsoft 云德国实例提供的终结点上的所有依赖项。 例如，如果你的 LOB 应用连接到 `https://graph.microsoft.de/` ，则必须将 终结点更改为 `https://graph.microsoft.com/` 。 第 2 阶段Microsoft Office租户可以使用 365 全局服务终结点。

| 步骤 (步骤)  | 描述 | 影响 |
|:-------|:-------|:-------|
| 确定迁移后是否要求任何重新配置。 | 与 Office 365 集成的第三方服务和应用程序可能编码为预期 Microsoft 云德国 IP 地址和 URL。 | 必需操作。 不操作可能会导致服务或客户端软件失败。 |
||||

## <a name="dynamics-365"></a>Dynamics 365

**适用于：** 使用 Microsoft Dynamics 365 的客户

| 步骤 (步骤)  | 描述 | 影响 |
|:-------|:-------|:-------|
| 对于 Dynamics 365 沙盒订阅，请务必从 Microsoft 云德国的 Dynamics 365 订阅下载 Dynamics SQL 实例的生产环境。 应在沙盒迁移之前将最新的生产备份还原到沙盒。 | Dynamics 365 的迁移要求客户确保使用最新的生产数据库刷新沙盒环境。 | FastTrack 团队将帮助客户执行干运行，以验证版本从 8.x 升级到 9.1.x。 |
||||

## <a name="power-bi"></a>Power BI

**适用于：** 使用 Power BI 的客户

| 步骤 (步骤)  | 描述 | 影响 |
|:-------|:-------|:-------|
| 从 Power BI 订阅删除不会从 Power BI Microsoft 云德国迁移到 Office 365 服务的对象。 | Power BI 服务的迁移需要客户操作来删除某些项目，如数据集和仪表板。 | <ul><li>管理员可能必须删除其订阅中的以下项目： </li><li>Real-Time数据集 (，例如流式处理或推送)  </li><li>Power BI 本地数据网关配置和数据源 </li></ul>|
||||

## <a name="microsoft-azure"></a>Microsoft Azure

如果你正在为德国 Microsoft 云实例中的 Office 365 和 Microsoft Azure 使用相同的 Azure Active Directory 标识分区，请确保你正在准备客户驱动的 Microsoft Azure 服务迁移。

> [!NOTE]
> 在 Office 365 租户进入迁移阶段 3 之前，不得启动 Microsoft Azure 服务的迁移，并且必须在迁移阶段 8 完成之前完成迁移。

使用 Office 365 和 Azure (例如网络、计算和存储) 的客户将执行资源到 Office 365 服务实例的迁移。 此迁移是客户的责任。 消息中心帖子将发出开始信号。 迁移必须在 Office 365 服务环境中完成 Azure AD 组织之前完成。 有关 Azure 迁移，请参阅 Azure 迁移操作手册 [（Azure 德国的迁移指南概述](https://docs.microsoft.com/azure/germany/germany-migration-main)）。

| 步骤 (步骤)  | 描述 | 影响 |
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
