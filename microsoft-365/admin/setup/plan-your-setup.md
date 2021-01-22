---
title: 规划 Microsoft 365 商业版设置
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: 了解移动到 Microsoft 365 商业版的要求和注意事项。
ms.openlocfilehash: 9158ad5a56b78fd8173ae81a2e9e4a5bd51633ca
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926818"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>规划 Microsoft 365 商业版设置

本文适用于订阅 Microsoft 365 商业版计划的人。
  
在将组织迁移到 Microsoft 365 之前，需要满足一些要求、需要获得的信息以及必须做出的决策。


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>运行安装向导之前要拥有的信息

当你准备好运行安装向导，将域移动到 Microsoft 365 时，你需要获得以下信息：
  
- 要添加到 Microsoft 365 中的人员列表。 即使已将它们添加到 Microsoft 365，如果要更新域信息，也需要在此处输入其名称。

- 如何通知员工其用户 ID 和密码，以便他们可以登录。 是否要打电话通知他们此信息？ 或是将信息发送到他们的个人电子邮件地址？ 他们无法访问其电子邮件，因此你无法使用它。

- 如果你的组织拥有域名 (例如 contoso.com) 并且计划使用 Microsoft 电子邮件，则需要知道域的注册位置并拥有登录信息。

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>运行 Microsoft 365 安装向导时会发生什么情况

安装向导将指导你在你的计算机上安装 Microsoft 365 应用、添加和验证域、添加用户并为其分配许可证，以及连接域。

> [!NOTE]
> 如果需要将 [Microsoft 365](../add-users/assign-admin-roles.md) 商业版中的管理员角色分配给在向导中添加的用户，可以在稍后的"用户"页面上 **执行** 。 
  
如果未完成安装向导，则你随时都可以从管理中心安装程序 [完成设置](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **任务**。 你可以在此处从另一个电子邮件服务迁移电子邮件和联系人、更改管理员帐户的域、管理帐单信息、添加或删除用户、重置密码以及执行其他业务功能。 有关安装向导和安装页之间的差异，请参阅 Microsoft  [365](o365-setup-wizard-and-setup-page.md)安装向导和安装页之间的差异。

如果遇到问题，请致电我们。 [我们在此提供帮助！](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>何时不使用设置向导？Active Directory 同步和混合环境

有两种方案包括从本地环境迁移数据或用户，或设置包含目录同步的混合系统。 如果属于任一类别，请按照以下文章中的说明操作：
  
- 若要设置与本地 Active Directory 的目录同步，请参阅"为 [Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)设置目录同步"，并了解 Microsoft 365 中的不同标识模型，请阅读"了解 [Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity)标识和 Azure Active Directory"。

- 若要设置 Exchange 混合，可在此处找到完整的相关说明，该说明指导用户使用不同方法来完成混合 Exchange的设置（包括设置 DNS 记录）：[Exchange Server 部署助理](https://aka.ms/exdeploy)

- 若要设置 SharePoint 混合，特别是混合搜索和站点功能，请参阅 [SharePoint 中的混合搜索](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint)。

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>一次或分步全部移动到 Microsoft 365

- **是否要将组织一次全部移动到 Microsoft 365？** 如果是，请计划将域马上移动到 Microsoft 365。 首先运行 Microsoft 365 安装向导;它将提示你设置域。

- **是否要逐步移动到 Microsoft 365？** 如果你想要分步移动到 Microsoft 365，请跳过运行 Microsoft 365 安装向导，并考虑按以下顺序采用 Microsoft 365 功能：

    1. [将员工添加到 Microsoft 365，](../add-users/add-users.md) 以便他们可以下载和安装 Office 应用。

    2. [下载和安装 Office 应用](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)以在你的计算机和设备上使用 Word、Excel 和 PowerPoint。

    3. [设置 Microsoft Teams](#plan-for-teams) 以用于会议。

    4. [将内容移动到 OneDrive](set-up-file-storage-and-sharing.md) 或 SharePoint (Microsoft 365 云) 。

    5. 准备就绪后，在管理中心选择左侧[](https://go.microsoft.com/fwlink/p/?linkid=2024339)导航窗格中的"设置"，然后使用"设置"页移动[域和电子邮件](add-domain.md)。

## <a name="check-that-your-devices-meet-system-requirements"></a>检查你的设备是否满足系统要求

组织中的每个人都可以在最多五台电脑和 Mac 上安装 Office 2016 (Word、Excel、PowerPoint 等) 套件。 请参阅安装 [Office 2016 套件](https://go.microsoft.com/fwlink/?LinkId=534827)商业版的操作系统和计算机要求。
  
移动应用可以安装在 iOS、Android 和 Windows 设备上。 可在 [Office 的系统需求](https://go.microsoft.com/fwlink/?LinkId=534827)中找到有关移动设备和浏览器支持的信息。
  
## <a name="plan-for-email"></a>计划电子邮件

如果计划从现有电子邮件服务移动到 Microsoft 365，通常需要两天的时间进行切换。
  
### <a name="plan-for-email-downtime"></a>考虑电子邮件故障时间
  
如果你要使用 Microsoft 365 作为电子邮件：
  
- 若要将企业 (例如 *rob \@ contoso.com*) 从另一个电子邮件服务移动到 Microsoft 365，需要将邮件传递到新的 Microsoft 365 邮箱。 为此，在"设置"页上选择"迁移用户数据"，我们将指导你逐步完成在域主机上需要的更新。

- 更新域主机后，所做更改通常在一小时或两小时后生效。 但请注意，有时可能需要 72 小时才能通过 Internet 更新更改。

- 由于电子邮件可能会停机，我们建议你计划晚上或周末在接收较少电子邮件时切换到 Microsoft 电子邮件。

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>计划移动你的现有电子邮件、联系人和日历
  
如果你要使用 Microsoft 365 作为电子邮件帐户，你可以将现有电子邮件、联系人和日历带在一起。 The **Setup** page helps you move your existing email and contacts for most scenarios. 我们还提供了分步指南来移动一个或多个邮箱。
  
|**多少个邮箱？**|**建议**|
|:-----|:-----|
|仅几个  <br/> |如果不想使用"安装"页迁移邮箱，可以允许邮箱所有者迁移自己的电子邮件和联系人。 请参阅 [将电子邮件和联系人迁移到 Microsoft 365 商业版](migrate-email-and-contacts-admin.md)。  <br/> |
|多个  <br/> |如果要从 Gmail 迁移，请参阅"将 G Suite 邮箱迁移到[Microsoft 365"。](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)  <br/> 如果你正在从另一个电子邮件提供商（包括 Exchange）迁移，请参阅将多个电子邮件帐户迁移到 [Microsoft 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)。  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>计划文件存储和迁移

Microsoft 365 为个人、小型组织和企业提供云存储。 有关存储位置的指南，请参阅可在 [Microsoft 365 中存储文档的位置](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790)。
  
- **你可以将数百个文件移动到** [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) 或 [SharePoint 团队网站](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242)。 一次可以上传 100 个文件。 请避免上传超过 2 GB 的文件，这是默认最大文件大小。
  
- **如果要将数千个文件** 移动到 Microsoft 365 存储，请查看 [SharePoint Online 限制](https://go.microsoft.com/fwlink/p/?LinkID=856113)。 建议使用迁移工具或考虑雇用[合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)来帮助进行迁移。 有关如何迁移大量文件的信息，请参阅 [SharePoint Online 和 OneDrive 迁移用户指南](https://go.microsoft.com/fwlink/?LinkId=723574)。
  
## <a name="plan-for-teams"></a>规划 Teams

可以使用 Microsoft Teams 呼叫组织中订阅的其他人员。 例如，如果你的组织有 10 个人，则无需任何特殊设置，即可使用 Teams 相互呼叫和即时消息。 有关详细信息，请参阅 [Microsoft Teams 入门](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start)。

对于大型组织，或者如果你从 Skype for Business、本地或混合部署开始，请参阅如何推出[Microsoft Teams。](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams)
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>计划与 Active Directory 或其他软件集成

- **是否想要与你的本地 Active Directory 集成？** 可以使用 Azure Active Directory Connect 将本地 Active Directory 与 Microsoft 365 集成。 有关说明，请参阅 [设置 Microsoft 365 的目录同步](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)。
  
- **是否要将 Microsoft 365 与其他公司生产的软件集成？** 如果你需要将 Microsoft 365 与组织的其他软件集成，我们建议你考虑雇用合作伙伴[](https://go.microsoft.com/fwlink/?linkid=391089)来帮助你进行部署。
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>你是否希望有人帮助你设置 Microsoft 365？

- **如果你的员工不到 50 人：**

  - **寻求帮助，我们将致电你**。 购买 Microsoft 365 后，你可以访问管理中心 (无需运行安装程序就可以访问) 。 在管理中心底部，选择" **需要帮助"** 描述你的问题，我们将致电你。 
  - **如果 [有疑问，致电 Microsoft 365](../contact-support-for-business-products.md) 商业版支持人员**。 We're here to help! 
  - **考虑雇用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)** 。 如果你的时间很短，或者具有高级要求 (例如将成千上万个文件移动到 Microsoft 365 云存储或与其他软件) 集成，有经验的合作伙伴可能会大有帮助。 

- **如果你的员工超过 50 人** ，则 [FastTrack 实施中心](https://go.microsoft.com/fwlink/?LinkId=517115)可对你的部署提供帮助。 
