---
title: 规划 Microsoft 365 商业版安装
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: 了解移动到适用于Microsoft 365的要求和注意事项。
ms.openlocfilehash: 1012e854d514212ae3c5c970347255936ea94f1a
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63312721"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>规划 Microsoft 365 商业版安装

本文适用于已订阅企业Microsoft 365用户。
  
在将组织迁移到Microsoft 365之前，你需要满足一些要求、需要获得的信息以及必须做出的决策。

## <a name="overview-of-microsoft-365-business-premium-setup"></a>Microsoft 365 商业高级版设置概述

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg?autoplay=false]

祝贺你决定使用云将业务移动到Microsoft 365！ 无论你的企业中是否有一个人或 20 个人，进行一些规划都将帮助你在工作Microsoft 365 商业高级版。

## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>运行安装向导之前要拥有的信息

当你准备好运行安装向导，将域移动到 Microsoft 365 时，你需要获取以下信息：
  
- 要添加到其中Microsoft 365。 即使已将它们添加到Microsoft 365，如果要更新域信息，也需要在此处输入其名称。

- 如何通知员工其用户 ID 和密码，以便他们可以登录。 是否要打电话通知他们此信息？ 或是将信息发送到他们的个人电子邮件地址？ 他们无法访问他们的电子邮件，因此你无法使用它。

- 如果你的组织拥有域名 (如 contoso.com) 并且计划使用 Microsoft 电子邮件，则需要知道域的注册位置并拥有登录信息。

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>运行安装向导时Microsoft 365会发生什么情况

安装向导将引导你完成在计算机上安装 Microsoft 365 应用、添加和验证域、添加用户并为其分配许可证以及连接域。

> [!NOTE]
> 如果需要将 Microsoft 365 [企业](../add-users/assign-admin-roles.md)版中的管理员角色分配给在向导中添加的用户，可以在稍后的"用户"页面上 **执行**。 
  
如果未完成安装向导，则你随时都可以从管理中心设置完成 [设置](https://go.microsoft.com/fwlink/p/?linkid=2024339) > **任务**。 你可以在此处从另一个电子邮件服务迁移电子邮件和联系人、更改管理员帐户的域、管理帐单信息、添加或删除用户、重置密码以及执行其他业务功能。 有关安装向导和"安装"页之间的差异详细信息，请参阅安装程序向导Microsoft 365[设置页面之间的差异](o365-setup-wizard-and-setup-page.md)。

如果遇到问题，请致电我们。 [我们在此提供帮助！](../../business-video/get-help-support.md)。
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>何时不使用设置向导？Active Directory 同步和混合环境

有两种方案，包括从本地环境迁移数据或用户或设置包含目录同步的混合系统。 如果属于任一类别，请按照以下文章中的说明操作：
  
- 若要设置与本地 Active Directory 的目录同步，请参阅为 [Microsoft 365](../../enterprise/set-up-directory-synchronization.md) 设置目录同步，并了解 Microsoft 365 中的不同标识模型，请阅读部署 Microsoft 365 的[标识基础结构](../../enterprise/deploy-identity-solution-overview.md)。

- 若要设置 Exchange 混合，可在此处找到完整的相关说明，该说明指导用户使用不同方法来完成混合 Exchange的设置（包括设置 DNS 记录）：[Exchange Server 部署助理](/exchange/exchange-deployment-assistant)

- 若要设置 SharePoint 混合，特别是混合搜索和站点功能，请参阅 [SharePoint 中的混合搜索](/SharePoint/hybrid/hybrid-search-in-sharepoint)。

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>一Microsoft 365或分步移动到所有项目

- **是否要将组织一次Microsoft 365迁移？** 如果是，请计划将域Microsoft 365移动。 首先运行Microsoft 365向导;它将提示你设置域。

- **是否要逐步移动到Microsoft 365迁移？** 如果要分步移动到Microsoft 365，请跳过运行 Microsoft 365 安装向导，并考虑按以下Microsoft 365采用这些功能：

    1. [将员工添加到Microsoft 365](../add-users/add-users.md)，以便他们可以下载并安装Office应用。

    2. [下载和安装 Office 应用](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)以在你的计算机和设备上使用 Word、Excel 和 PowerPoint。

    3. [设置Microsoft Teams](#plan-for-teams)会议使用的组。

    4. [将内容移动到Microsoft 365云](set-up-file-storage-and-sharing.md) (OneDrive或SharePoint团队) 。

    5. 准备就绪后，在管理中心选择左侧[](https://go.microsoft.com/fwlink/p/?linkid=2024339)导航窗格中的"设置"，然后使用"设置"页[移动域和电子邮件](add-domain.md)。

## <a name="check-that-your-devices-meet-system-requirements"></a>检查你的设备是否满足系统要求

组织中的每个人都可以在最多五台电脑和 Mac 上安装 Office 2016 应用套件 (Word、Excel、PowerPoint 等) 。 请参阅安装 [Office 2016 套件](https://go.microsoft.com/fwlink/?LinkId=534827)商业版的操作系统和计算机要求。
  
移动应用可以安装在 iOS、Android 和 Windows设备上。 可在 [Office 的系统需求](https://go.microsoft.com/fwlink/?LinkId=534827)中找到有关移动设备和浏览器支持的信息。
  
## <a name="plan-for-email"></a>计划电子邮件

如果计划从现有电子邮件服务移动到 Microsoft 365，通常需要两天的时间进行切换。
  
### <a name="plan-for-email-downtime"></a>考虑电子邮件故障时间
  
如果你打算将 Microsoft 365用于你的电子邮件：
  
- 若要将企业电子邮件地址 (例如 *rob\@ contoso.com*) 从另一个电子邮件服务移动到 Microsoft 365，需要将邮件发送到新的 Microsoft 365 邮箱。 为此，在"设置"页上选择"迁移用户数据"，我们会逐步指导你在域主机上完成所需的更新。

- 更新域主机后，所做更改通常在一小时或两小时后生效。 但请注意，有时可能需要 72 小时才能通过 Internet 更新更改。

- 由于电子邮件可能会停机，我们建议你计划晚上或周末在接收较少电子邮件时切换到 Microsoft 电子邮件。

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>计划移动你的现有电子邮件、联系人和日历
  
如果你打算将 Microsoft 365用于你的电子邮件帐户，你可以将现有电子邮件、联系人和日历带在一起。 The **Setup** page helps you move your existing email and contacts for most scenarios. 我们还提供了分步指南来移动一个或多个邮箱。
  
|**多少个邮箱？**|**建议**|
|:-----|:-----|
|仅几个  <br/> |如果不想使用"安装"页迁移邮箱，可以允许邮箱所有者迁移自己的电子邮件和联系人。 请参阅[将电子邮件和联系人迁移到Microsoft 365企业。](migrate-email-and-contacts-admin.md)  <br/> |
|多个  <br/> |如果要从 Gmail 迁移，请参阅将 [G Suite 邮箱迁移到 Microsoft 365](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)。  <br/> 如果要从另一个电子邮件提供商（包括 Exchange）进行迁移，请参阅将多个电子邮件帐户[迁移到](/Exchange/mailbox-migration/mailbox-migration) Microsoft 365。  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>计划文件存储和迁移

Microsoft 365为个人、小型组织和企业提供云存储。 有关存储位置的指南，请参阅文档存储位置[Microsoft 365](https://support.microsoft.com/office/d18d21a0-1f9f-4f6c-ac45-d52afa0a4a2e)。
  
- **可以将数百个文件移动到**[OneDrive或移动到](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB)SharePoint [网站](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242)。 一次可以上传 100 个文件。 请避免上传超过 2 GB 的文件，这是默认最大文件大小。
  
- **如果要将数千个文件移动到** Microsoft 365，请查看 SharePoint [Online 限制](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)。 建议使用迁移工具或考虑雇用[合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)来帮助进行迁移。 有关如何迁移大量文件的信息，请参阅 [SharePoint Online 和 OneDrive 迁移用户指南](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)。
  
## <a name="plan-for-teams"></a>规划Teams

可以使用Microsoft Teams呼叫组织中订阅的其他人员。 例如，如果您的组织有 10 个人，则无需任何特殊设置，即可使用 Teams相互呼叫和 IM。 有关详细信息，请参阅开始[Microsoft Teams](/MicrosoftTeams/get-started-with-teams-quick-start)。

对于大型组织，或者如果你从Skype for Business部署、本地部署或混合部署开始，请参阅如何[Microsoft Teams。](/MicrosoftTeams/how-to-roll-out-teams)
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>计划与 Active Directory 或其他软件集成

- **是否想要与你的本地 Active Directory 集成？** 可以使用 Azure Active Directory 连接 将本地 Active Directory 与 Microsoft 365 集成。 有关说明，请参阅[设置目录同步Microsoft 365](../../enterprise/set-up-directory-synchronization.md)。
  
- **您是否希望将Microsoft 365与其他公司所生产的软件集成？** 如果需要将 Microsoft 365与组织的其他软件集成，建议考虑雇用合作伙伴来帮助进行部署。[](https://go.microsoft.com/fwlink/?linkid=391089)
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>是否希望有人帮助你设置Microsoft 365？

- **如果你的员工不到 50 人：**

  - **寻求帮助，我们将致电你**。 购买Microsoft 365后，你无需运行安装程序 (就可以访问管理中心) 。 在管理中心底部，选择" **需要帮助？"** 描述你的问题，我们将致电你。 
  - **如果 [Microsoft 365问题，请致电 Microsoft 365](../../business-video/get-help-support.md) for Business Support**。 We're here to help! 
  - **考虑雇用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)** 。 如果你的时间很短，或者对 (如将成千上万个文件移动到 Microsoft 365 云存储或与其他软件) 集成，经验丰富的合作伙伴可能会大有帮助。 

- **如果你的员工超过 50 人** ，则 [FastTrack 实施中心](https://go.microsoft.com/fwlink/?LinkId=517115)可对你的部署提供帮助。

## <a name="see-also"></a>另请参阅

[保护业务Microsoft 365的十大方法](../security-and-compliance/secure-your-business-data.md)
