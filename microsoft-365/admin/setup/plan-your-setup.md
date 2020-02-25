---
title: 规划 Office 365 商业版的设置
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: 了解设置 Office 365 for business 所需的操作。
ms.openlocfilehash: 3b38f0092b323175c6a12170105e781fab21934d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240229"
---
# <a name="plan-your-setup-of-office-365-for-business"></a>规划 Office 365 商业版的设置

本文适用于已订阅 Office 365 商业版计划的人员。
  
将组织移动到 Office 365 之前，需要确定一些事项，并提供需要的信息。
  
## <a name="info-to-have-on-hand-before-you-run-the-office-365-setup-wizard"></a>运行 Office 365 设置向导前需要掌握的信息

如果已准备好运行 Office 365 设置向导并将域移动到 Office 365，以下是需掌握的信息：
  
- 想要添加到 Office 365 的人员列表。即使已将他们添加到了 Office 365，但如果要更新域信息，则需在此输入他们的姓名。

- 以何种方式通知员工知悉他们的 Office 365 用户 ID 和密码，以便可以登录。是否要打电话通知他们此信息？或是将信息发送到他们的个人电子邮件地址？他们没有权限访问其 Office 365 电子邮件，因此不能使用该邮件地址。

- 如果您的组织具有域名（例如 contoso.com），**并且**您计划使用 Office 365 电子邮件，则需要知道您的域的注册位置并具有登录信息。

## <a name="what-happens-when-you-run-the-office-365-setup-wizard"></a>运行 Office 365 设置向导时会发生的情况

安装向导引导您完成在您的计算机上安装 Office 365 应用程序、添加和验证您的域、添加用户并向其分配许可证以及连接您的域。

> [!NOTE]
> 如果需要将[Office 365 for business 中的管理员角色分配](../add-users/assign-admin-roles.md)给您在向导中添加的用户，可以在稍后在 "**用户**" 页上执行此操作。 
  
如果未完成设置向导，则可以随时通过[管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339) > **安装**程序完成安装任务。 从这里，您可以从其他电子邮件服务迁移电子邮件和联系人、更改管理员帐户的域、管理付费信息、添加或删除用户、重置密码和执行其他业务功能。 有关安装向导和**setup**页面之间的差异的详细信息，请参阅[Office 365 安装向导和设置页面之间的差异](o365-setup-wizard-and-setup-page.md)。

如果你有任何一点，请拨打我们的电话。 [我们在这里为你提供帮助！](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>何时不使用设置向导？Active Directory 同步和混合环境

有几种方案，其中包括从本地环境迁移数据或用户，或者设置包含目录同步的混合系统。 如果你处于任一类别，请按照以下文章中的说明操作：
  
- 若要设置与本地 Active Directory 的目录同步，请参阅[在 Office 365 中设置目录同步](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)，若要了解 Office 365 中的不同标识模型，请参阅[了解 Office 365 标识和 Azure Active Directory](https://docs.microsoft.com/office365/enterprise/about-office-365-identity)。

- 若要设置 Exchange 混合，可在此处找到完整的相关说明，该说明指导用户使用不同方法来完成混合 Exchange的设置（包括设置 DNS 记录）：[Exchange Server 部署助理](https://aka.ms/exdeploy)

- 若要设置 SharePoint 混合，特别是混合搜索和站点功能，请参阅 [SharePoint 中的混合搜索](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint)。

## <a name="move-to-office-365-all-at-once-or-in-stages"></a>在一次或分阶段移动到 Office 365

- **是否要同时将组织移动到 Office 365？** 如果是这样，则立即计划将域移动到 Office 365。 通过运行 Office 365 设置向导开始，它将提示你设置域。

- **是否要逐步迁移到 Office 365？** 如果想要分阶段移动到 Office 365，则跳过运行 Office 365 设置向导，并考虑按以下顺序采用 Office 365 功能：

    1. [将你的员工添加到 Office 365](../add-users/add-users.md) ，以便他们可以下载和安装 Office 应用。

    2. [下载和安装 Office 应用](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx)以在你的计算机和设备上使用 Word、Excel 和 PowerPoint。

    3. [设置 Microsoft 团队](#plan-for-teams)以供你的会议使用。

    4. [将内容移动到 Office 365 云存储](set-up-file-storage-and-sharing.md)（OneDrive 或 SharePoint 团队网站）。

    5. 准备就绪后，在 "[管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)" 中，选择左侧导航窗格中的 "**安装程序**"，然后使用 "**设置**" 页面[移动您的域和电子邮件](add-domain.md)。

## <a name="check-that-your-devices-meet-system-requirements"></a>检查你的设备是否满足系统要求

组织中的每个人都可以在最大5台电脑和 Mac 上安装 Office 2016 套件应用程序（Word、Excel、PowerPoint 等）。 请参阅安装 [Office 2016 套件](https://go.microsoft.com/fwlink/?LinkId=534827)商业版的操作系统和计算机要求。
  
移动应用可以安装在 iOS、Android 和 Windows 设备上。 可在 [Office 的系统需求](https://go.microsoft.com/fwlink/?LinkId=534827)中找到有关移动设备和浏览器支持的信息。
  
## <a name="plan-for-email"></a>计划电子邮件

如果您计划从现有的电子邮件服务移动到 Office 365，则通常需要两天的时间来进行切换。
  
### <a name="plan-for-email-downtime"></a>考虑电子邮件故障时间
  
如果要对电子邮件使用 Office 365：
  
- 若要将业务电子邮件地址（如*rob@contoso.com*）从其他电子邮件服务移动到 Office 365，您需要将邮件传递到新的 Office 365 邮箱。 若要执行此操作，请选择 "**设置**" 页上的 **"迁移用户的数据"** ，我们将指导您完成需要在域主机上进行的更新（分步步骤）。

- 更新域主机后，所做更改通常在一小时或两小时后生效。 但请注意，有时可能需要长达72小时才能在 internet 上更新更改。

- 由于可能会遭遇电子邮件故障时间，因此建议在接收较少电子邮件的晚上或周末计划切换到 Office 365 电子邮件。

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>计划移动你的现有电子邮件、联系人和日历
  
如果将对你的电子邮件帐户使用 Office 365，可引入现有的电子邮件、联系人和日历。 "**设置**" 页面可帮助您在大多数情况下移动现有电子邮件和联系人。 我们还提供了分步指南来移动一个或多个邮箱。
  
|**多少个邮箱？**|**建议**|
|:-----|:-----|
|仅几个  <br/> |如果不想使用 "**设置**" 页面迁移邮箱，则可以让邮箱所有者迁移其自己的电子邮件和联系人。 请参阅[将电子邮件和联系人迁移到 Office 365 商业版](migrate-email-and-contacts-admin.md)。  <br/> |
|多个  <br/> |如果要从 Gmail 迁移，请参阅[将 G 套件邮箱迁移到 Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)。  <br/> 如果要从其他电子邮件提供商（包括 Exchange）进行迁移，请参阅[将多个电子邮件帐户迁移到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)。  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>计划文件存储和迁移

Office 365 为个人、小型组织和企业提供云存储。 有关将何种文件存储到何处的指导，请参阅[文档在 Office 365 中的存储位置](https://support.office.com/article/c7c20284-bc94-47f4-9728-d28e9daf0790.aspx)。
  
- **你可以将数百个文件移动**到[OneDrive](https://support.office.com/article/45114744-6D42-45CD-8975-F9617819BDEB.aspx)或[SharePoint 团队网站](https://support.office.com/article/da549fb1-1fcb-4167-87d0-4693e93cb7a0.aspx#__toc384119242)。 一次可以上传 100 个文件。 请避免上传超过 2 GB 的文件，这是默认最大文件大小。
  
- **如果想要移动数千个文件** 到 Office 365 存储，请查看 [SharePoint Online 限制](https://go.microsoft.com/fwlink/p/?LinkID=856113)。建议使用迁移工具或考虑雇用[合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)来帮助进行迁移。有关如何迁移大量文件的信息，请参阅 [SharePoint Online 和 OneDrive 迁移用户指南](https://go.microsoft.com/fwlink/?LinkId=723574)。
  
## <a name="plan-for-teams"></a>规划团队

您可以使用 Microsoft 团队向组织中的其他人拨打您的订阅。 例如，如果您的组织有10个人，则无需进行任何特殊设置即可使用团队呼叫和即时消息。 有关详细信息，请参阅[Microsoft 团队入门](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start)。

对于较大的组织或从 Skype for Business、内部部署或混合部署开始，请参阅[如何推出 Microsoft 团队](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams)。
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>计划与 Active Directory 或其他软件集成

- **是否想要与你的本地 Active Directory 集成？** 可以通过使用 Azure Active Directory Connect 将你的本地 Active Directory 与 Office 365 集成。有关说明，请参阅 [在 Office 365 中设置目录同步](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)。
  
- **是否想要将 Office 365 与其他企业制作的软件集成？** 如果需要将 Office 365 与组织中的其他软件集成，建议您考虑[雇用合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)来帮助您进行部署。
  
## <a name="do-you-want-someone-to-help-you-set-up-office-365"></a>是否希望其他人帮助设置 Office 365？

- **如果你的员工不到 50 人：**

  - **寻求帮助，我们将为你打电话**。 购买 Office 365 之后，可以访问管理中心（无需运行安装程序即可获取）。 在管理中心的底部，选择 **"需要帮助？"** 描述你的问题，我们将为你打电话。 
  - **如有问题，请致电[Office 365 For Business 支持部门](../contact-support-for-business-products.md)**。 We're here to help! 
  - **考虑雇用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)** 。如果你的时间很紧或者有高级需求（比如，将成千上万的文件迁移到 Office 365 云存储空间或者与其他软件集成），经验丰富的合作伙伴可以有很大的帮助。 

- **如果你的员工超过 50 人** ，则 [FastTrack 实施中心](https://go.microsoft.com/fwlink/?LinkId=517115)可对你的部署提供帮助。 
