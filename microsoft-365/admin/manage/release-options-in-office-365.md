---
title: 设置标准或目标发布选项
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: 了解如何为 Microsoft 365 管理中心中的新产品和功能更新设置发布选项。
ms.openlocfilehash: 4b26a3e95b11feb5c6a5894702b86e74f82bde03
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399688"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>设置标准或目标发布选项

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

在 Microsoft 365 中，你将收到新的产品更新和功能，因为它们变为可用，而不是每几年进行一次成本更新。 你可以管理组织接收这些更新的方式。 例如，你可以注册抢先体验新发布版本，保证组织能够第一时间接收到更新。 你可以指定只有某几个人接收更新。 或者，你可以保留默认的发布计划，稍后接收更新。 本文介绍不同的发布选项，以及如何将它们用于您的组织。
  
> [!IMPORTANT]
> 本文中所述的 Microsoft 365 更新适用于 Microsoft 365、SharePoint Online 和 Exchange Online。 这些更新不适用于 Skype for Business 及相关服务。 这些发布选项的目标是，将更改发布到 Microsoft 365 的最佳方法是，但不能始终保证，也不能保证所有更新。 
  
## <a name="how-it-works---release-validation"></a>工作原理 - 发布验证

任何新版本都会先由功能团队进行测试和验证，然后由整个 Microsoft 365 功能团队进行测试，然后再访问所有 Microsoft。 内部测试和验证后，下一步是向选择加入的客户" **定向发布**"（以前称为首次发布）。 在每个发布环节，Microsoft 都会收集反馈，通过监视关键的使用情况指标验证质量。 采取逐步进行的一系列验证，确保全球范围内发布的版本尽可能的稳定。 发布环节如下图所示。 
  
![Microsoft 365 的发布验证环](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
对于重要更新， [Microsoft 365 路线图](https://products.office.com/business/office-365-roadmap)最初会通知客户。 随着更新越接近，将通过[Microsoft 365 消息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)进行传递。

> [!NOTE]
> 你需要 Microsoft 365 或 Azure AD 帐户，才能通过[管理中心](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)访问你的消息中心。 Microsoft 365 家庭版计划用户没有管理中心。


## <a name="standard-release"></a>标准发布

这是默认选项，当你和你的用户广泛发布到所有客户时，你和你的用户将收到最新的更新。
  
一种很好的做法是将大多数用户留在**标准版的版本**中，将 IT 专业人员和高级用户保留在**目标版本**中，以评估新功能并准备团队以支持业务用户和执行官。 
  
> [!NOTE]
> 如果你从定向发布切换回标准发布计划，你的用户可能无法再次访问那些尚未进入标准发布的功能。 
  
## <a name="targeted-release"></a>定向发布

使用此选项，你和你的用户可以抢先体验最新更新，并通过提供早期反馈帮助改进产品。你可以选择让某几个人或整个组织先接收更新。
  
> [!IMPORTANT]
> 大型或复杂更新所需的时间可能比其他更新所需的周期时间更长，以确保不会有任何用户受到负面影响。 我们不保证确切的发布时间线。 
  
### <a name="targeted-release-for-entire-organization"></a>针对整个组织的定向发布

如果在管理中心为此选项设置了 "[发布" 选项](#set-up-the-release-option-in-the-admin-center)，则所有用户都将获得目标发布体验。 对于拥有 300 名用户以上的组织，我们建议使用此选项的测试订阅。 有关测试订阅信息，请联系你的 Microsoft 联系人。 
  
### <a name="targeted-release-for-selected-users"></a>针对选定用户的定向发布

如果在[管理中心中设置](#set-up-the-release-option-in-the-admin-center)了 "发布" 选项，则可以定义特定用户（通常为高级用户），以接收对功能和功能的早期访问权限。 
  
## <a name="benefits-of-targeted-release"></a>定向发布的优势

目标发布允许管理员、变更管理者或任何其他人负责 Microsoft 365 更新，以准备即将进行的更改，具体方法是让他们：
  
- 在新的更新面向组织中的所有用户发布之前，测试并验证这些更新。
    
- 在全球范围内发布更新前准备好用户通知和文档。
    
- 为即将到来的更新准备好内部技术支持。
    
- 仔细检查合规性和安全性审查。
    
- 在适用的位置使用功能控件，控制向最终用户发布的更新。
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>在管理中心中设置 "发布" 选项

您可以按照以下步骤更改您的组织接收 Microsoft 365 更新的方式。 您必须是 Microsoft 365 中的全局管理员才能自愿加入。
  
> [!IMPORTANT]
> 可能需要长达24小时才能使以下更改在 Microsoft 365 中生效。 如果你在启用定向发布之后选择退出，你的用户可能无法再次访问那些尚未进入发布计划的功能。 
  
1. 在管理中心中，转到 "**设置**" "  >  **组织设置**"，在 "**组织配置文件**" 选项卡下，选择 "**发布首选项**"。

5. 若要禁用目标发布，请选择 "**标准发布**"，然后选择 "**保存更改**"。 
    
6. 若要为组织中的所有用户启用目标版本，请为 "所有人" 选择 "**目标版本**"，然后选择 "**保存更改**"。 
    
7. 若要为组织中的某些人员启用目标发布，请选择 "选择**的用户的目标发布**"，然后选择 "**保存更改**"。 
    
8. 选择 "**选择用户**" 可一次添加一个用户，或**上传用户**以批量添加用户。
    
9. 添加完用户后，请选择 "**保存更改**"。


  
## <a name="learn-more"></a>了解详细信息

了解如何管理[Microsoft 365 消息中心](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)中的[邮件](https://docs.microsoft.com/office365/admin/manage/message-center)，以获取有关即将推出的 Microsoft 365 更新和版本的通知。
