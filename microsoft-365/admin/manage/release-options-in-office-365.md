---
title: 设置标准或定向发布选项
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: 了解如何在发布中设置新产品和功能更新的发布Microsoft 365 管理中心。
ms.openlocfilehash: d053530b5b3ec0500783679ceb1823ce93992fae
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173051"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>设置标准或定向发布选项

> [!IMPORTANT]
> 本文Microsoft 365更新适用于 Microsoft 365、SharePoint Online 和 Exchange Online。 这些发布选项是发布对 Microsoft 365 更改的有针对性的最佳方法，但不能保证在所有时间或所有更新中都可用。 它们不适用于Microsoft 365 应用版、Skype for Business Microsoft Teams服务。 有关发布选项的信息，Microsoft 365 应用版[有关更新频道Microsoft 365 应用版。](/deployoffice/overview-update-channels)

使用 Microsoft 365，您可以在新产品更新和功能可用时收到它们，而不是每隔几年进行一次代价高昂的更新。 你可以管理组织接收这些更新的方式。 例如，你可以注册抢先体验新发布版本，保证组织能够第一时间接收到更新。 你可以指定只有某几个人接收更新。 或者，你可以保留默认的发布计划，稍后接收更新。 本文介绍了不同的发布选项以及如何为组织使用它们。

## <a name="how-it-works---release-validation"></a>工作原理 - 发布验证

任何新版本首先由功能团队进行测试和验证，然后由整个Microsoft 365团队进行测试和验证，然后由所有 Microsoft 进行测试和验证。 内部测试和验证后，下一步是向选择加入的客户" **定向发布**"（以前称为首次发布）。 在每个发布环节，Microsoft 都会收集反馈，通过监视关键的使用情况指标验证质量。 采取逐步进行的一系列验证，确保全球范围内发布的版本尽可能的稳定。 发布环节如下图所示。 
  
![发布适用于 Microsoft 365 的验证Microsoft 365。](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
对于重大更新，客户最初会通过"Microsoft 365[通知。](https://products.office.com/business/office-365-roadmap) 随着更新的推出越来越接近，它将通过你的Microsoft 365[中心进行通信](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)。

> [!NOTE]
> 你需要一Microsoft 365 Azure AD 帐户才能通过管理中心[访问消息中心](/office365/admin/admin-overview/about-the-admin-center)。 Microsoft 365家庭计划用户没有管理中心。


## <a name="standard-release"></a>标准发布

这是你和用户广泛发布给所有客户时接收最新更新的默认选项。
  
最佳做法是让大多数用户留在标准版中，让IT 专业人员和高级用户在定向发布中评估新功能，并准备团队以支持业务用户和管理人员。 
  
> [!NOTE]
> 如果你从定向发布切换回标准发布计划，你的用户可能无法再次访问那些尚未进入标准发布的功能。 
  
## <a name="targeted-release"></a>定向发布

使用此选项，你和你的用户可以抢先体验最新更新，并通过提供早期反馈帮助改进产品。你可以选择让某几个人或整个组织先接收更新。
  
> [!IMPORTANT]
> 大型或复杂更新所需的时间可能比其他更新所需的周期时间更长，以确保不会有任何用户受到负面影响。 我们不保证确切的发布时间线。 
  
### <a name="targeted-release-for-entire-organization"></a>针对整个组织的定向发布

如果你在 [管理中心中](#set-up-the-release-option-in-the-admin-center) 设置此选项的发布选项，你的所有用户都将获得定向发布体验。 对于拥有 300 名用户以上的组织，我们建议使用此选项的测试订阅。 有关测试订阅信息，请联系你的 Microsoft 联系人。 
  
### <a name="targeted-release-for-selected-users"></a>针对选定用户的定向发布

如果在 [管理中心](#set-up-the-release-option-in-the-admin-center) 中设置此选项的发布选项，你可以定义特定用户（通常是高级用户）以接收对特性和功能的早期访问。 
  
## <a name="benefits-of-targeted-release"></a>定向发布的优势

定向发布允许管理员、变更经理或其他负责更新Microsoft 365，让他们：
  
- 在新的更新面向组织中的所有用户发布之前，测试并验证这些更新。
    
- 在全球范围内发布更新前准备好用户通知和文档。
    
- 为即将到来的更新准备好内部技术支持。
    
- 仔细检查合规性和安全性审查。
    
- 在适用的位置使用功能控件，控制向最终用户发布的更新。
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>在管理中心设置发布选项

你可以按照以下步骤更改组织接收Microsoft 365更新。 你必须是全局管理员Microsoft 365才能选择加入。
  
> [!IMPORTANT]
> 以下更改可能需要 24 小时才能在 Microsoft 365。 如果你在启用定向发布之后选择退出，你的用户可能无法再次访问那些尚未进入发布计划的功能。 
  
1. 在管理中心中，转到"设置组织设置 **"，在"组织配置文件"** 选项卡下，选择  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank"></a>"**发布首选项"。**

5. 若要禁用定向发布，请选择"**标准发布"，** 然后选择"**保存更改"。** 
    
6. 若要为组织中所有用户启用定向发布，请选择"面向所有人的发布"，然后选择"保存 **更改"。** 
    
7. 若要为组织中某些人员启用定向发布，请选择所选用户的定向发布，然后选择保存 **更改**。 
    
8. 选择 **"选择** 用户"以一次添加一个用户 **，Upload用户进行** 批量添加。
    
9. 添加完用户后，请选择"**保存更改"。**
  
## <a name="next-steps"></a>后续步骤

了解如何在[邮件Microsoft 365](/office365/admin/manage/message-center)[管理](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)邮件，以获取有关即将推出的 Microsoft 365 更新和发布的通知。

## <a name="related-content"></a>相关内容

[加入 Office 预览体验计划](https://insider.office.com/join/windows) (文章) 
