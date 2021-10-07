---
title: 从德国 Microsoft 云迁移的迁移前活动
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 05/12/2021
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
description: 摘要：从德国 Microsoft 云 (德国) 迁移到新的德国数据中心Office 365服务前工作。
ms.openlocfilehash: 04d94cb8cd95d55ccccec388e10be49541828270
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189065"
---
# <a name="pre-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>从德国 Microsoft 云迁移的迁移前活动

使用这些链接可了解与组织相关的迁移前步骤。

如果你使用的是

- **Office 365德国 Microsoft 云中，** 请 [执行以下步骤](#general-tenant-migration-considerations)。
- **自定义域**，执行 [此步骤](#dns-entries-for-custom-domains)。
- **Office应用，** 请考虑 [此步骤](#office-apps)。
- **SharePoint Online，** 请 [执行此步骤](#sharepoint-online)。
- **Exchange Online** 或 **Exchange混合，** 请 [执行此步骤](#exchange-online)。
- **Skype for Business Online，** 请 [执行此步骤](#skype-for-business-online)。
- **Dynamics 365，**[执行此步骤](#dynamics-365)。
- **Power BI，** 请 [执行此步骤](#power-bi)。
- **Active Directory Federation Services** for Azure AD 连接，请 [执行以下步骤](#active-directory-federation-services-ad-fs)。
- **与应用集成的第** 三方服务或业务 (**LOB) ，Office 365**[执行此步骤](#line-of-business-apps)。
- MDM 解决方案的第三方移动设备 (，) 执行 [此步骤](#mobile-device-management)。
- **Azure 服务** 与 Office 365订阅一起，[执行此步骤](#microsoft-azure)。

## <a name="general-tenant-migration-considerations"></a>一般租户迁移注意事项

**适用于：** 使用 Microsoft Office 365云实例的所有客户

Office 365保留租户和用户标识符。 Azure AD 服务调用从德国 Microsoft 云重定向到Office 365全局服务，并且对 azure AD 服务Office 365透明。

- GDPR (一般数据保护) 数据主体请求 (DSR) 从 Azure 管理门户执行，供将来请求使用。 在 30 天后或之前，将删除位于德国 Microsoft 云的任何旧诊断数据或非客户诊断数据。

- 使用 Microsoft Authenticator 的多重身份验证 (MFA) 请求显示为用户 ObjectID (GUID) 而租户复制到 Office 365 服务。 尽管存在此显示行为，MFA 请求仍然会执行预期。  Microsoft Authenticator服务终结点激活Office 365帐户将显示 UPN (用户) 。  使用德国 Microsoft 云终结点添加的帐户将显示用户 ObjectID，但将同时用于德国 Microsoft 云Office 365服务终结点。

<br>

****

|步骤 (步骤) |说明|影响|
|---|---|---|
|准备通知用户迁移后重启客户端并登录和退出客户端。|Office许可将在迁移过程中从德国 Microsoft 云Office 365服务转换。 客户端在从客户端登录并登录后，将Office许可证。|用户的Office产品需要刷新来自服务Office 365许可证。 如果未刷新许可证，Office产品可能会遇到许可证验证错误。|
|确保与 Office 365 [URL 和 IP 地址的网络连接](https://aka.ms/o365urls)。|由客户托管的用于访问 Office 365 服务的所有客户端和服务必须能够访问 Office 365 全局服务终结点。 <p> 如果您或您的协作合作伙伴已制定防火墙规则，阻止访问 Office 365 服务 URL 中列出的 URL 和 IP 地址，[则 IP](https://aka.ms/o365urls)地址必须更改防火墙规则以允许访问 Office 365 全局服务终结点|如果未在阶段 4 之前完成此操作，则可能会发生服务或客户端软件故障|
|取消任何试用订阅。|试用版订阅将不会迁移，并且将阻止传输付费订阅。|如果取消后用户访问试用服务，则试用服务已过期且无法正常工作。|
|分析德国 Microsoft 云与 Microsoft 全球服务之间Office 365差异。|Office 365服务包括当前德国 Microsoft 云中不可用的其他功能和服务。 在订阅转移期间，用户可以使用新功能。|<ul><li>分析 Microsoft 云德国和 microsoft 全球服务的许可证Office 365功能。 从"Office 365[服务说明"开始](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)。</li><li>确定是否应最初禁用 Office 365服务的任何新功能，以限制对用户或用户更改管理的影响，并根据需要更改用户许可证分配。</li><li>让用户和技术支持人员准备好使用由 Office 365 服务提供的新服务和功能。</li></ul>|
|创建组织范围的 [保留策略](/microsoft-365/compliance/retention) ，防止在迁移过程中意外删除内容。|<ul><li>为确保最终用户不会在迁移过程中意外删除内容，客户可以选择启用组织范围的保留策略。</li><li>尽管不需要保留，因为迁移过程中随时设置保留应按预期工作，但保留策略是一种备份安全机制。 同时，保留策略可能不会由所有客户使用，尤其是关注保留的客户。</li></ul>|应用保留策略，如 [了解保留策略和保留标签中所述](/microsoft-365/compliance/retention-policies)。 如果未在阶段 4/9 之前完成此操作，则可能会发生服务或客户端软件故障。|


## <a name="dns-entries-for-custom-domains"></a>自定义域的 DNS 条目

<!-- before phase 9 -->

**适用于：** 在其自己的 DNS 域中设置自定义 _msoid_ CNAME 或者使用域进行自定义Exchange Online

如果配置 _，msoid_ CNAME 将仅影响使用 Office Desktop client (Microsoft 365 应用版，Office 365 专业增强版， Office 2019， 2016， ...) 的客户。

如果你拥有一个或多个 DNS 命名空间中设置了名为 _msoid_ 的 DNS CNAME，必须删除 CNAME，直到最晚阶段 8 结束。 可以在阶段 8 结束之前随时删除 CNAME _msoid。_

若要验证是否在你的 DNS 命名空间中设置了 CNAME，请按照以下步骤操作，contoso.com替换为你自己的域名：

```console
nslookup -querytype=CNAME msoid.contoso.com
```

如果命令行返回 DNS 记录，请从 _域中删除 msoid_ CNAME。

> [!NOTE]
> 如果使用自定义域进行Exchange Online，则需要具有对 DNS 托管提供商的访问权限。 请确保可以访问和编辑 DNS 设置，您将在迁移过程中修改 DNS 记录。

## <a name="office-apps"></a>Office应用

**适用于：** 使用 Office 应用的客户，尤其是在 Windows 客户端上 <br>
**应用后**：阶段 9 之前的任何时间

Office 365迁移到"德国"地区的租户要求所有用户在租户迁移到达阶段 9 后关闭、注销 Office 365，然后重新登录所有 Office 桌面应用程序 (Word、Excel、PowerPoint、Outlook 等 ) 和 OneDrive for Business 客户端。 通过登录和登录，Office服务从全局 Azure AD 服务获取新的身份验证令牌。

这一点对于所有客户端都是必需的。 为了确保流畅的迁移体验，强烈建议提前通知和指示所有受影响的用户有关此即将开始的活动。

具有托管Windows客户端的客户可以使用[WINDOWS COVER](https://github.com/microsoft/OCCT)工具Office OCCT (准备) 。 OCCT 旨在定期在 Windows 客户端上运行，直到租户达到迁移的第 9 阶段。 当阶段 9 已到达时，OCCT 将自动在计算机中执行所有必要的更改，而无需用户交互。

在阶段 9 之前，Windows在客户端上部署 OCCT。 如果 OCCT 应支持迁移体验，我们建议尽快启动部署，以便安装最大数量的客户端。

## <a name="active-directory-federation-services-ad-fs"></a>Active Directory 联合身份验证服务 (AD FS)

**适用于：** 使用本地 AD FS 验证连接到 Microsoft Office 365<br>
**应用后**：阶段 2 之前的任何时间

阅读和应用 [ADFS 迁移步骤](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

**适用于：** 在本地使用 SharePoint 2013 的客户<br>
**应用时**：阶段 4 之前的任何时间

<br>

****

|步骤 (步骤) |说明|影响|
|---|---|---|
|限制SharePoint 2013 工作流，在 SharePoint Online 迁移期间使用。|在SharePoint之前减少 2013 工作流和完成运行中的工作流。|不操作可能会导致用户混淆和技术支持呼叫。| 
如果SharePoint修改，导出搜索配置。 |将不会SharePoint搜索配置。 如果已应用SharePoint任何修改，请确保记下任何更改并导出搜索配置。 完成切换后，必须SharePoint导入这些设置。|在重新应用搜索修改之前，任何基于修改的搜索架构的自定义解决方案将不可用。|


## <a name="exchange-online"></a>Exchange Online

<!-- before phase 5 -->

**适用于：** Exchange Online客户<br>
**应用时**：阶段 9 结束之前的任何时间

<br>

****

|步骤 (步骤) |说明|影响|
|---|---|---|
|通知外部合作伙伴即将过渡到 Office 365 服务。|客户必须通知已启用共享日历和可用性地址空间配置的合作伙伴 (允许与用户共享忙/闲Office 365) 。 完成迁移后，需要[Office 365全球终结点](/microsoft-365/enterprise/urls-and-ip-address-ranges)Exchange Online配置。|如果不这样做，可能会导致客户迁移的稍后阶段出现服务或客户端故障。|
|通知用户所需的 IMAP4/POP3/SMTP 客户端更改。|对于客户端协议 IMAP4、POP3 和 SMTP，具有 Microsoft 云德国终结点的设备连接的用户需要手动更新其客户端设备以切换到 Exchange Online[服务器名称](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/pop3-and-imap4#settings-users-use-to-set-up-pop3-or-imap4-access-to-their-exchange-online-mailboxes)。|向这些协议的用户预传达此依赖关系，并确保他们在此迁移期间Outlook或Outlook 网页版移动设备。 迁移用户邮箱时，更新客户端终结点失败将导致德国 Microsoft 云的客户端连接失败。|


### <a name="exchange-online-hybrid-customers"></a>Exchange Online混合客户

**适用于：** 使用活动混合配置的所有Exchange混合配置Exchange本地服务器<br>
**应用时**：阶段 5 之前的任何时间

Enterprise混合部署 Exchange Online 和本地 Exchange Server 的客户运行混合配置向导 (HCW) 和 AAD 连接 来维护和建立混合设置。
Exchange Online作为此转换的一部分，混合管理员 (**HCW**) 多次执行混合配置向导。
从德国 Microsoft 云过渡到德国 Office 365 区域时，管理员必须在 Office 365 Germany 模式下重新运行 HCW 的最新内部版本，然后才能开始 Exchange 迁移 (阶段) 。 然后，在完成第 5 阶段后，以"Office 365全球"模式再次运行 HCW，以使用 Office 365 区域设置完成本地部署。 HCW 运行在第 5 阶段期间不得执行，在阶段 5 完成之前运行 HCW 很重要。
Directory 属性通过 AAD Office 365在 Azure AD 与本地部署之间连接。

<br>

**

|步骤 () |说明|影响|
|---|---|---|
|使用德国设置重新Office 365 HCW <p> _在收到消息中心通知你的租户迁移已开始Office 365租户迁移的第 1 阶段 (立即启动) 。_|在第 5 阶段之前卸载并重新运行 HCW (17.0.5378.0 或更高版本) 将确保本地配置已准备好与德国 Microsoft 云用户和迁移到 Office 365 Germany 区域的用户一起发送和接收邮件。 <https://aka.ms/hybridwizard> <p> In the HCW， for the list box below **My Office 365 organization is hosted by**， select Office 365 **Germany.**|如果未能在阶段 5 [Exchange 迁移] 开始之前完成此任务，可能会导致本地部署和部署之间路由邮件的 EXCHANGE NDR Office 365。|
|保留共享邮箱设置|一些混合客户使用命令将云用户邮箱转换为"共享Exchange Online邮箱。 此云邮箱配置将写入邮箱和本地 Exchange Online 目录，但是，它不会通过 AAD 连接 同步回客户的 Active Directory。 结果是邮箱 RemoteRecipientType 和 RemoteDisplayType 值的 Active Directory 表示形式不同，在将邮箱Exchange Online为共享时存在差异。 <p> 客户负责确保使用 、或 正确预配所有共享 `New-RemoteMailbox -Shared` `Enable-RemoteMailbox -Shared` 邮箱 `Set-RemoteMailbox -Shared` 。 请参阅此参考，了解如何 [在混合环境中转换用户邮箱](/microsoft-365/admin/email/convert-user-mailbox-to-shared-mailbox)。|在阶段 5 [Exchange Online 迁移] 之前未能完成此任务可能会导致共享邮箱的 NDR 转换回未授权邮箱，并丢失受影响邮箱的共享访问权限。 [在 Exchange](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)混合部署中运行目录同步后，共享邮箱意外转换为用户邮箱，其中概述了在迁移完成之前不Exchange Online此操作的影响。|


## <a name="skype-for-business-online"></a>Skype for Business Online

<!-- before phase 7 -->

**适用于：** Skype For Business Online 客户<br>
**应用时**：阶段 7 之前的任何时间

<br>

****

|步骤 () |说明|影响|
|---|---|---|
|为Teams德国的用户部署桌面Skype for Business客户端。|迁移将Skype for Business用户Microsoft Teams进行协作、通话和聊天。 部署桌面Microsoft Teams或确保受支持的浏览器可用。|Inaction will result inavailability of Microsoft Teams collaboration services.|
|查看并准备与迁移相关的 DNS 更改。|Skype for Business Online 的客户拥有的 DNS 区域更改。|<ul><li>建议将任何客户拥有的域 DNS 记录的生存时间 (TTL) 更新为 5 分钟，以加快 DNS 记录的刷新。 但是，与此 DNS 更改关联的 Microsoft 管理的转换可能在提供的 24 小时更改时段内随时发生。</li><li>未来可能会中断服务。 用户将无法登录到 Skype for Business，并重定向到 Teams 服务中迁移Office 365体验。</li></ul>|
|准备最终用户和管理培训和准备过渡到Microsoft Teams。|通过规划用户沟通和准备情况Skype成功Teams迁移目标。|<ul><li>客户端需要了解新服务，以及一旦其服务转换到新服务后如何使用Office 365服务。</li><li>为客户虚域和初始域都进行了 DNS 更改后，用户将登录到 Skype for Business并查看他们现在已迁移到 Teams。 这还会在后台下载桌面Teams桌面客户端。</li></ul>|


## <a name="mobile-device-management"></a>移动设备管理

<!-- before phase 5 -->
**适用于：** 使用 MDM 解决方案的第三方移动设备 () 客户<br>
**应用时**：阶段 5 之前的任何时间

<br>

****

|步骤 () |说明|适用对象|影响|
|---|---|---|---|
|准备最终用户和管理培训，以便用户删除其帐户并重新将其帐户Outlook iOS 和 Android。|Outlook德国 Microsoft 云中配置邮箱的 Microsoft Outlook for iOS 和 Android 帐户可能需要删除并再次添加到 Outlook 才能正确同步新的 Office 365 服务配置。|Microsoft Outlook for iOS 和 Android 客户|Outlook为德国 Microsoft 云配置的新邮箱可能不会选取新的 Office 365 服务配置，从而导致其他用户体验的错误和性能下降。 如果迁移后登录或同步邮件时出现问题，建议 IT 管理员提供文档，以主动指示用户删除其帐户，并将其添加到 Microsoft Outlook for iOS 和 Android。|
|确定迁移后是否要求任何重新配置。|移动设备管理 (MDM) 解决方案可能面向 `outlook.de` 终结点。 在此到 Office 365 服务的转换中，客户端配置文件应更新为 Office 365 服务 `outlook.office365.com` URL。|Exchange Online和 MDM 客户|当终结点可访问时，客户端可能会继续运行，但如果 Microsoft 云德国终结点不再可用，客户端将 `outlook.de` 失败。|


## <a name="line-of-business-apps"></a>业务线应用

**适用于：** 使用业务线或 LOB (LOB) Microsoft 云德国提供终结点的应用<br>
**应用后**：阶段 2 完成之后和阶段 9 结束之前

如果你使用的是与 Office 365 集成的第三方服务或业务线 (LOB) 应用，则必须解决 Microsoft 云德国实例提供的终结点上的任何依赖项。 例如，如果你的 LOB 应用连接到 `https://graph.microsoft.de/` ，则必须将 终结点更改为 `https://graph.microsoft.com/` 。 第 2 阶段Microsoft Office 365租户可以使用全局服务的终结点。

在迁移期间，当您的组织介于阶段 2 和阶段 9 之间时，您不能向组织添加任何使用 MTA (第三) 租户应用程序。 迁移完成第 9 阶段后，可以恢复为组织添加或同意 MTA 应用程序。


| 步骤 ()  | 说明 | 影响 |
|:-------|:-------|:-------|
| 确定迁移后是否要求任何重新配置。 | 第三方服务和应用程序与 Office 365可能编码为预期 Microsoft 云德国 IP 地址和 URL。 | 必需操作。 不操作可能会导致服务或客户端软件失败。 |


|步骤 () |说明|影响|
|---|---|---|
|确定迁移后是否要求任何重新配置。|第三方服务和应用程序与 Office 365可能编码为预期 Microsoft 云德国 IP 地址和 URL。|必需操作。 不操作可能会导致服务或客户端软件失败。|


## <a name="dynamics-365"></a>Dynamics 365

**适用于：** 使用 Microsoft Dynamics 365 的客户

<br>

****

|步骤 () |说明|影响|
|---|---|---|
|对于 Dynamics 365 沙盒订阅，请务必从 Microsoft 云德国的 Dynamics 365 订阅下载 Dynamics SQL 实例的生产环境。 应在沙盒迁移之前将最新的生产备份还原到沙盒。|Dynamics 365 的迁移要求客户确保使用最新的生产数据库刷新沙盒环境。|FastTrack团队将帮助客户执行干运行，以验证版本从 8.x 升级到 9.1.x。|


## <a name="power-bi"></a>Power BI

**适用于：** 使用 Power BI

<br>

****

|步骤 (步骤) |说明|影响|
|---|---|---|
|从 Microsoft Power BI迁移到德国的订阅Power BI对象Office 365服务。|迁移Power BI需要客户操作来删除某些项目，如数据集和仪表板。|管理员可能必须删除其订阅中的以下项目： <ul><li>Real-Time数据集 (，例如流式处理或推送) </li><li>Power BI本地数据网关配置和数据源 </li></ul>|


## <a name="microsoft-azure"></a>Microsoft Azure

如果你正在为德国 Microsoft 云实例中的 Office 365 和 Microsoft Azure 使用相同的 Azure Active Directory 标识分区，请确保你正在准备客户驱动的 Microsoft Azure 服务迁移。

> [!NOTE]
> 在 Office 365 租户进入迁移阶段 9 之前，可能无法开始迁移 Microsoft Azure 服务，并且必须在开始迁移阶段 10 之前完成迁移。

使用 Office 365 和 Azure (例如网络、计算和存储) 的客户将执行资源到 Office 365 服务实例的迁移。 此迁移是客户的责任。 消息中心帖子将发出开始信号。 必须先完成迁移，然后才能在 Azure AD 服务环境中完成Office 365组织。 有关 Azure 迁移，请参阅 Azure 迁移操作手册 [（Azure 德国的迁移指南概述](/azure/germany/germany-migration-main)）。

<br>

****

|步骤 (步骤) |说明|影响|
|---|---|---|
|通过与合作伙伴合作，确定使用哪些 Azure 服务，并准备将来从德国迁移到 Office 365 服务租户。 按照 Azure 迁移操作手册 [中所述的步骤操作](/azure/germany/germany-migration-main)。|<ul><li>Azure 资源的迁移是客户的责任，需要按照规定步骤执行手动操作。 了解组织中使用的服务是成功迁移 Azure 服务的关键。</li><li>Office 365如果德国客户在组织中具有同一标识 (Azure) ，则必须按照 Microsoft 规定的顺序开始订阅和服务迁移。</li></ul>|<ul><li>客户可能有多个 Azure 订阅，每个订阅包含基础结构、服务和平台组件。</li><li>管理员应确定订阅和利益干系人，以确保作为此迁移事件的一部分，可以进行快速迁移和验证。</li><li>未能成功完成这些订阅的迁移，且在规定时间线内的 Azure 组件将影响 Office 和 Azure AD 到 Office 365 服务的转换完成，并可能导致数据丢失。</li><li>消息中心通知将指示客户引导的迁移可以开始的时间点。</li></ul>|


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

- [从德国 Microsoft 云迁移到Office 365新的德国数据中心区域部署服务](ms-cloud-germany-transition.md)
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
