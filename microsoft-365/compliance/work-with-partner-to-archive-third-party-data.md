---
title: 与合作伙伴联系以存档第三方数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解如何设置自定义连接器以从数据源（如 Salesforce Chatter、Yahoo Messenger 或 Yammer）导入第三方数据。
ms.openlocfilehash: 5b6bbab9ff6ad54440fc84213d3e810c863ebef4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60200181"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a>与合作伙伴联系以存档第三方数据

你可以与 Microsoft 合作伙伴合作，将第三方数据源的数据导入并存档Microsoft 365。 合作伙伴可以为您提供一个自定义连接器，该连接器配置为定期从第三方数据源 (提取项目，) 导入这些项目。 合作伙伴连接器将项目的内容从数据源转换为电子邮件格式，然后将项目存储在邮箱中。 导入第三方数据后，您可以将 Microsoft 365 合规性功能（如诉讼保留、电子数据展示、In-Place 存档、审核和 Microsoft 365 保留策略）应用于此数据。

> [!IMPORTANT]
> Microsoft 365[中的](communication-compliance.md)通信合规性解决方案不能应用于本文中提到的合作伙伴连接器导入的第三方数据。

下面概述了与 Microsoft 合作伙伴合作导入第三方数据所需的过程和步骤。

[Step 1: Find a third-party data partner](#step-1-find-a-third-party-data-partner)

[步骤 2：创建和配置第三方数据邮箱](#step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365)

[Step 3: Configure user mailboxes for third-party data](#step-3-configure-user-mailboxes-for-third-party-data)

[步骤 4：为合作伙伴提供信息](#step-4-provide-your-partner-with-information)

[步骤 5：在网站中注册第三方数据Azure Active Directory](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>第三方数据导入过程的工作原理

下图和说明说明了与合作伙伴合作时第三方数据导入过程的工作方式。

![第三方数据导入过程的工作原理。](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)

1. 客户与所选择的合作伙伴合作，配置连接器，该连接器将提取第三方数据源中的项目，然后将这些项目导入Microsoft 365。

2. 合作伙伴连接器通过计划或配置的第三方 API (连接到第三方数据源) 并从数据源中提取项目。 合作伙伴连接器将项目内容转换为电子邮件格式。 有关 [邮件格式](#more-information) 架构的说明，请参阅详细信息部分。

3. 合作伙伴连接器使用 Exchange Web 服务 (EWS) 连接到 Microsoft 365 中的 Azure 服务。

4. 项目便导入到特定用户的邮箱或“catch-all”第三方数据邮箱。无论项目是导入到特定用户邮箱还是第三方数据邮箱，都要基于以下条件：

   1. **具有与用户帐户对应的用户 ID 的项目：** 如果合作伙伴连接器可以将第三方数据源中项目的用户 ID 映射到 Microsoft 365 中的特定用户 ID，则该项目将复制到用户的"可恢复的项目"文件夹中的 **"** 清除"文件夹。 用户无法访问“清除”文件夹中的项目。 但是，您可以使用电子数据展示工具搜索"清除"文件夹中的项目。

   1. **没有对应于用户帐户的用户 ID 的项目：** 如果合作伙伴连接器无法将项目的用户 ID 映射到特定用户 ID，该项目将复制到第三方数据邮箱的"收件箱"文件夹中。 将项目导入到收件箱允许您或组织中的其他人登录到第三方邮箱来查看和管理这些项目，并查看是否需要在合作伙伴连接器配置中进行任何调整。

## <a name="step-1-find-a-third-party-data-partner"></a>步骤 1：寻找第三方数据合作伙伴

在 Microsoft 365 中存档第三方数据的一个关键组件是查找并与专门捕获来自第三方数据源的数据并导入到第三方数据源的 Microsoft 合作伙伴Microsoft 365。 导入数据后，可以将其与组织的其他 Microsoft 数据（如来自 Exchange 的电子邮件以及来自 SharePoint 和 OneDrive for Business 的文档一起存档和OneDrive for Business。 合作伙伴创建一个连接器，从组织的第三方数据源 (如 BlackBerry、Facebook、Google+、Thomson Reuters、Twitter 和 YouTube) 中提取数据，将数据传递给将项目作为电子邮件导入 Exchange 邮箱的 Microsoft 365 API。

以下各节列出了 Microsoft 合作伙伴 (他们支持的第三方数据源) 参与计划以在 Microsoft 365 中存档第三方数据。

[17a-4 LLC](#17a-4-llc)

[ArchiveSocial](#archivesocial)

[百里达](#veritas)

[OpenText](#opentext)

[Smarsh](#smarsh)

[Verba](#verba)

### <a name="17a-4-llc"></a>17a-4 LLC

[17a-4 LLC](https://www.17a-4.com) 支持以下第三方数据源：

- BlackBerry

- Bloomberg 数据流

- Cisco Jabber

- FactSet

- HipChat

- InvestEdge

- LivePerson

- MessageLabs 数据流

- OpenText

- Oracle/ATG“单击以呼叫”Live 帮助

- Pivot IMTRADER

- Microsoft SharePoint

- MindAlign

- Sitrion One (Newsgator)

- Skype for Business (Lync/OCS)

- Skype for Business Online (Lync Online)

- SQL 数据库

- Squawker

- Thomson Reuters Eikon Messenger

### <a name="archivesocial"></a>ArchiveSocial

[ArchiveSocial](https://www.archivesocial.com) 支持以下第三方数据源：

- Facebook

- Flickr

- Instagram

- 领英

- Pinterest

- Twitter

- YouTube

- Vimeo

### <a name="veritas"></a>百里达

[百](https://www.globanet.com) 年支持以下第三方数据源：

- 使用 Pivot 客户端的 AOL

- BlackBerry 呼叫日志（v5、v10、v12）

- BlackBerry Messenger（v5、v10、v12）

- BlackBerry PIN（v5、v10、v12）

- BlackBerry 短信（v5、v10、v12）

- Bloomberg 聊天

- Bloomberg 邮件

- Box

- 适用于 Salesforce Chatter 的 CipherCloud

- Cisco IM &amp; Presence Server (v10、v10.5.1 SU1、v11.0、v11.5 SU2) 

- Cisco Webex Teams

- Citrix Workspace &amp; ShareFile

- CrowdCompass

- 自定义分隔的文本文件

- 自定义 XML 文件

- Facebook (页面) 

- Factset

- FXConnect

- ICE Chat/YellowJacket

- Jive

- Macgregor XIP

- Microsoft Exchange Server

- Microsoft OneDrive for Business

- Microsoft Teams

- Microsoft Yammer

- Mobile Guard

- Pivot

- Salesforce Chatter

- Skype for Business Online

- Skype for Business，版本 2007 R2 - 2016（本地）

- Slack Enterprise Grid

- Symphony

- Thomson Reuters Eikon

- Thomson Reuters Messenger

- Thomson Reuters Dealings 3000 / FX Trading

- Twitter

- UBS 聊天

- YouTube

### <a name="opentext"></a>OpenText

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) 支持以下第三方数据源：

- Axs Encrypted

- Axs Exchange

- Axs 本地存档

- Axs PlaceHolder

- Axs Signed

- Bloomberg

- Thomson Reuters

### <a name="smarsh"></a>Smarsh

[Smarsh](https://www.smarsh.com) 支持以下第三方数据源：

- AIM

- American Idol

- Apple Juice

- 使用 Pivot 客户端的 AOL

- Ares

- Bazaar Voice

- Bear Share

- Bit Torrent

- BlackBerry 呼叫日志（v5、v10、v12）

- BlackBerry Messenger（v5、v10、v12）

- BlackBerry PIN（v5、v10、v12）

- BlackBerry 短信（v5、v10、v12）

- Bloomberg 邮件

- CellTrust

- Chat Import

- 聊天实时日志记录和策略

- Chatter

- Cisco IM &amp; Presence Server (v9.0.1、v9.1、v9.1.1 SU1、v10、v10.5.1 SU1) 

- Cisco Unified Presence 服务器（v8.6.3、v8.6.4、v8.6.5）

- 协作导入

- 协作实时日志记录

- Direct Connect

- Facebook

- FactSet

- FastTrack

- 符合该规范的

- Google+

- GoToMyPC

- Hopster

- HubConnex

- IBM Connections（v3.0.1、v4.0、v4.5、v4.5 CR3、v5）

- IBM Connections Chat Cloud

- IBM Connections Social Cloud

- IBM SameTime Advanced 8.5.2 IFR1

- IBM SameTime Communicate 9.0

- IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)

- IBM SameTime Complete 9.0

- IBM SameTime Conference 9.0

- IBM SameTime Meeting 8.5.2 IFR1

- ICE/YellowJacket

- 即时消息导入

- 即时消息实时日志记录和策略

- Indii Messenger

- 即时 Bloomberg

- IRC

- Jive

- Jive 6 实时日志记录（v6、v7）

- Jive 导入

- JXTA

- 领英

- Microsoft Lync（2010、2013）

- MFTP

- Microsoft Lync 2013 语音

- Microsoft SharePoint（2010、2013）

- Microsoft SharePoint Online

- Microsoft UC（统一通信）

- MindAlign

- Mobile Guard

- MSN

- My Space

- 完成

- Microsoft 365Lync Dedicated

- Microsoft 365共享 IM

- Pinterest

- Pivot

- QQ

- Skype for Business 2015

- SoftEther

- Symphony

- Thomson Reuters Eikon

- Thomson Reuters Messenger

- Tor

- TTT

- Twitter

- WinMX

- Winny

- Yahoo

- Yammer

- YouTube


### <a name="verba"></a>Verba

[Verba](https://www.verba.com) 支持以下第三方数据源：

- Avaya Aura 视频

- Avaya Aura 语音

- Avtec 调频广播

- Bosch/Telex 调频广播

- BroadSoft 视频

- BroadSoft 语音

- Centile 语音

- Cisco Jabber 即时消息

- Cisco UC 视频

- Cisco UC 语音

- Cisco UCCX/UCCE 视频

- Cisco UCCX/UCCE 语音

- ESChat 调频广播

- Geoman 联络专家

- IP Trade 语音

- Luware LUCS 联络中心

- Microsoft UC（统一通信）

- 适用于 Lync 的 Mitel MiContact 中心 (prairieFyre)

- Oracle / Acme 数据包会话边界控制器视频

- Oracle / Acme 数据包会话边界控制器语音

- Singtel Mobile 语音

- SIPREC 视频

-  SIPREC 语音

- Skype for Business/Lync 即时消息

- Skype for Business/Lync 视频

- Skype for Business/Lync 语音

- Speakerbus 语音

- 标准 SIP/H.323 视频

- 标准 SIP/H.323 语音

- Truphone 语音

- TwistedPair 调频广播

- Windows 桌面计算机屏幕

## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365"></a>步骤 2：在邮箱中创建和配置第三方数据Microsoft 365

以下是创建和配置第三方数据邮箱以将数据导入到 Microsoft 365。 如上所述，如果合作伙伴连接器无法将项目的用户 ID 映射到用户帐户，则项目将导入到此邮箱。

 **在任务分配中Microsoft 365 管理中心**

1. 创建用户帐户并将其分配给Exchange Online 2 许可证;请参阅[将用户添加到Microsoft 365。](../admin/add-users/add-users.md) 需要计划 2 许可证才能将邮箱置于诉讼保留状态或启用存储配额高达 1.5 TB 的存档邮箱。

2. 将第三方数据邮箱的用户帐户添加到 Exchange **管理员** Microsoft 365角色;请参阅 [分配管理员角色Microsoft 365。](../admin/add-users/assign-admin-roles.md)

    > [!TIP]
    > 写下此用户帐户的凭据。您需要将它们提供给您的合作伙伴，如步骤 4 中所述。

 **在管理中心Exchange这些任务**

1. 在组织的通讯簿和其他地址列表中隐藏第三方数据邮箱;请参阅 [管理用户邮箱](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes)。 或者，可以运行以下 PowerShell 命令：

    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. 为第三方数据邮箱分配 **FullAccess** 权限，以便管理员或合规部官员可以在桌面客户端中Outlook第三方数据邮箱;请参阅 [管理收件人的权限](https://go.microsoft.com/fwlink/p/?LinkId=692104)。

3. 为第三方数据邮箱启用以下合规性相关功能：

    - 启用存档邮箱;请参阅[启用存档邮箱和](enable-archive-mailboxes.md)[启用自动扩展存档](enable-autoexpanding-archiving.md)。 这样，您通过设置存档策略（将第三方数据项目移动到存档邮箱）释放主邮箱中的存储空间。 这为第三方数据提供了高达 1.5 TB 的存储。

    - 将第三方数据邮箱置于诉讼保留的位置。 您还可以在安全Microsoft 365中心应用策略策略。 保留此邮箱会无限期保留第三 (或保留指定的持续时间) 并阻止将其从邮箱中清除。 请参阅下列主题之一：

      - [将邮箱置于诉讼保留状态](./create-a-litigation-hold.md)

      - [了解保留策略和保留标签](retention.md)

    - 为所有者、代理人和第三方数据邮箱的管理员访问权限启用邮箱审核日志记录;请参阅 [启用邮箱审核](enable-mailbox-auditing.md)。 这允许您审核有权访问第三方数据邮箱的任何用户执行的所有活动。

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>步骤 3：为第三方数据配置用户邮箱

下一步是配置用户邮箱以支持第三方数据。 使用管理中心或相应的 Exchange cmdlet 完成Windows PowerShell任务。

1. 为每个用户启用存档邮箱;请参阅[启用存档邮箱和](enable-archive-mailboxes.md)[启用自动扩展存档](enable-autoexpanding-archiving.md)。

2. 将用户邮箱置于诉讼保留或应用Microsoft 365保留策略;请参阅下列主题之一：

    - [将邮箱置于诉讼保留状态](./create-a-litigation-hold.md)

    - [了解保留策略和保留标签](retention.md)

    如前所述，在将邮箱置于保留时，您可以设置保留第三方数据源中项目的时长，或者也可以选择无限期保留这些项目。

## <a name="step-4-provide-your-partner-with-information"></a>步骤 4：为合作伙伴提供信息

最后一步是向合作伙伴提供以下信息，以便他们可以配置连接器以连接到您的组织以将数据导入到用户邮箱和第三方数据邮箱。

- 用于连接到 Azure 中 Azure 服务的终结点Microsoft 365：

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- 登录凭据 (Microsoft 365步骤 2) 创建的第三方数据邮箱的用户 ID 和密码。 这些凭据是必需的，以便合作伙伴连接器可以访问并将项目导入用户邮箱和第三方数据邮箱。

## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>步骤 5：在网站中注册第三方数据Azure Active Directory

从 2018 年 9 月 30 开始，Microsoft 365 中的 Azure 服务将开始使用 Exchange Online 中的新式验证来验证尝试连接到组织以导入数据的第三方数据连接器。 进行此更改的原因是，新式身份验证提供比当前方法更多的安全性，当前方法基于使用前面所述的终结点连接到 Azure 服务的第三方连接器的允许列表。

若要使第三方数据连接器能够使用新的新式Microsoft 365连接到服务器，您组织的管理员必须同意在 Azure Active Directory 中将连接器注册为受信任的服务应用程序。 这是通过接受允许连接器访问组织中组织数据的权限请求Azure Active Directory。 接受此请求后，第三方数据连接器将添加为企业应用程序以Azure Active Directory表示为服务主体。 有关同意过程详细信息，请参阅租户  [管理员同意](/skype-sdk/trusted-application-api/docs/tenantadminconsent)。

以下是访问和接受连接器注册请求的步骤：

1. 转到 [此页面，](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) 然后使用全局管理员的凭据登录。

   将显示以下对话框。 可以展开插入文件，查看将分配给连接器的权限。

   ![将显示权限请求对话框。](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. 单击“Accept”。

接受请求后， [将显示 Azure](https://portal.azure.com) 门户。 若要查看组织的应用程序列表，请单击 **"Azure Active Directory Enterprise**  >  **应用程序"。** 第Microsoft 365第三方数据连接器列于"Enterprise **应用程序"边栏** 选项卡上。

> [!IMPORTANT]
> 2018 年 9 月 30 日之后，如果您没有在 Azure Active Directory 中注册第三方数据连接器，则第三方数据将不再导入到您组织的邮箱中。 请注意，在 2018 (2018 年 9 月 30) 之前创建的现有第三方数据连接器也必须按照步骤 5 中的过程在 Azure Active Directory 中注册。

### <a name="revoking-consent-for-a-third-party-data-connector"></a>撤销第三方数据连接器的同意

在贵组织同意在 Azure Active Directory 中注册第三方数据连接器的权限请求后，组织可以随时撤销该同意。 但是，撤销对连接器的同意意味着来自第三方数据源的数据将不再导入Microsoft 365。

若要撤销第三方数据连接器的同意，可以在 Azure 门户使用 **Enterprise** 应用程序边栏选项卡，或者使用 Microsoft 365 PowerShell 中的 [Remove-MsolServicePrincipal](/powershell/module/msonline/remove-msolserviceprincipal)从 Azure Active Directory 中删除相应的服务主体) ，以删除应用程序 (。 您还可以在 PowerShell 中使用[Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet Azure Active Directory Cmdlet。

## <a name="more-information"></a>更多信息

- 如前所述，第三方数据源中的项目将作为电子邮件导入到 Exchange 邮箱。 合作伙伴连接器使用 Microsoft 365 API 所需的架构导入项目。 下表介绍了第三方数据源中的项目作为电子邮件导入到 Exchange 邮箱之后的邮件属性。 该表还指出该邮件属性是否是强制属性。 必须填充强制属性。 如果某个项目缺少强制属性，则它不会导入到Microsoft 365。 导入过程返回一条错误消息，说明未导入项目的原因以及缺少的属性。<br/><br/>

    |**邮件属性**|**强制？**|**说明**|**示例值**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |是  <br/> |最初创建或发送第三方数据源中的项目的用户。 合作伙伴连接器尝试将源项目的用户 ID (例如 Twitter 句柄) 映射到"FROM"和"TO"字段中 (用户的所有参与者的用户帐户) 。 邮件的副本将导入到每个参与者的邮箱中。 如果无法将此项目中的参与者映射到用户帐户，该项目将导入到 Microsoft 365 中第三方存档邮箱。  <br/> <br/> 被标识为项目发件人的参与者在将项目导入到的组织中必须具有活动邮箱。 如果发件人没有活动邮箱，则会返回以下错误：<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |是  <br/> |接收项目的用户（如果适用于数据源中的项目）。  <br/> | `bob@contoso.com` <br/> |
    |**主题** <br/> |否  <br/> |源项目中的主题。  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**DATE** <br/> |是  <br/> |最初在客户数据源中创建或发布项目的日期。 例如，Twitter 消息推文的日期。  <br/> | `01 NOV 2015` <br/> |
    |**BODY** <br/> |否  <br/> |消息或帖子的内容。 对于某些数据源，此属性的内容可能与“主题”属性的内容相同。 在导入过程中，合作伙伴连接器会尝试尽可能保持内容源的完全保真度。 如果可能，源项目正文中的文件、图形或其他内容会包含在此属性中。 否则，源项目中的内容会包含在“附件”属性中。 此属性的内容取决于合作伙伴连接器和源平台的功能。  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**ATTACHMENT** <br/> |否  <br/> |如果数据源中的项目 (Twitter 中的推文或即时消息对话) 具有附加文件或包含图像，合作伙伴连接将首先尝试在 **BODY** 属性中包括附件。 如果不可能，则它将被添加到 ** ATTACHMENT ** 属性。 其他附件示例包括 Facebook 中的点赞，内容源中的元数据，以及对消息或帖子的回复。  <br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |是  <br/> | 这是一个多值属性，由合作伙伴连接器创建和填充。 此属性的格式为  `IPM.NOTE.Source.Event` 。  (此属性必须以 开头  `IPM.NOTE` 。 此格式类似于邮件类的格式  `IPM.NOTE.X` 。) 此属性包含以下信息：  <br/><br/>`Source`：指示第三方数据源;例如，Twitter、Facebook 或 BlackBerry。  <br/> <br/>  `Event`：指示在生成项目的第三方数据源中执行的活动类型;例如，Twitter 中的推文或 Facebook 中的帖子。 事件特定于数据源。  <br/> <br/>  此属性的一个目的是基于项目源自的数据源或基于事件类型筛选特定项目。 例如，在电子数据展示搜索中，您可以创建一个搜索查询来查找特定用户发布的所有微博。  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |

- 当项目成功导入到 Microsoft 365 中的邮箱时，唯一标识符作为 HTTP 响应的一部分返回给调用方。 合作伙伴可以将此标识符（称为 ）用于后续疑难解答目的，以便  `x-IngestionCorrelationID` 对项目进行端到端跟踪。 建议合作伙伴捕获此信息，并在他们的所在端相应地记录此信息。 下面是显示此标识符的 HTTP 响应的示例：

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT
    ```

- 您可以使用安全与合规中心的内容搜索工具搜索已导入到第三方数据源中的邮箱的项目。 若要专门搜索这些导入的项目，可以在内容搜索的关键字框中使用以下邮件属性值对。

  - **`kind:externaldata`**：使用此属性值对搜索所有第三方数据类型。 例如，若要搜索从第三方数据源导入并包含在导入项目的 Subject 属性中的单词"contoso"的项目，您可以使用关键字查询  `kind:externaldata AND subject:contoso` 。

  - **`itemclass:ipm.externaldata.<third-party data type>`**：使用此属性值对仅搜索第三方数据的指定类型。 例如，若要仅搜索 Subject 属性中包含单词"contoso"的 Facebook 数据，您可以使用关键字查询  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` 。

  有关用于属性的第三方数据类型的值的完整列表，请参阅使用内容搜索搜索导入到第三方 `itemclass` Microsoft 365。 [](use-content-search-to-search-third-party-data-that-was-imported.md)

   有关如何使用内容搜索以及创建关键字搜索查询的详细信息，请参阅：

  - [内容搜索](content-search.md)

  - [内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)