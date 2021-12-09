---
title: 在两个帐户之间手动传输数据
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: 了解如何在更改计划或公司名称，或将多个订阅组合为一Microsoft 365两个帐户之间手动传输数据。
ms.openlocfilehash: aea01982d9cb6a42f382a23a50baf2e1bfa041cc
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61369992"
---
# <a name="transfer-data-manually-between-two-accounts"></a>在两个帐户之间手动传输数据

准备在日历上汇总并阻止一段时间：在两个 Microsoft 365 帐户之间传输数据是一个手动、复杂且耗时的过程。 这不是自动化或受支持的过程。 我们将开始。
  
> [!CAUTION]
> 在此过程期间，电子邮件、Skype for Business上托管的公共网站Microsoft 365将不起作用。 用户将获取新的用户名和密码，并且他们需要重置Outlook。

**仅在以下条件之一适用时，使用本主题中的说明手动传输数据：**
  
- 您需要更改为其他服务系列中的计划。

- 您的公司名称已更改，您决定创建新订阅并迁移数据，因为您想要使用不同的初始域名。

- 你需要将多个订阅合并为一个新订阅。

> [!IMPORTANT]
> 如果你需要更改订阅计划[](../../commerce/subscriptions/switch-to-a-different-plan.md)，并且可以使用切换计划向导，或者如果需要转移到同一订阅系列中的新订阅计划，即使切换计划向导不起作用，也无需手动传输数据，并且没有故障时间。

|**Tasks**|**Steps**|
|:-----|:-----|
|购买要移动到的计划。  <br/> |注册时，指定要用于初始域名的公司名称  *：yourcompany*  *.onmicrosoft.com、yourcompany*  -public.sharepoint.com 和  *yourcompany*  .sharepoint.com。 你需要使用与任何现有  *订阅*  不同的公司名称。  <br/> > [!NOTE]>取消订阅后，通常需要至少几个月的时间从系统发布使用  *你的*  公司的初始域名。 即使你计划从旧 Microsoft 365 订阅中保存所有数据并取消该订阅，旧的 *company* 值不会立即用于新订阅。           |
|从旧订阅中删除自定义Microsoft 365域。  <br/> | 在 [删除域](remove-a-domain.md) 之前，请按照所需步骤从用户电子邮件地址中删除域名，并删除电子邮件的 DNS 记录以及自定义域的 Lync 记录。 如果在主机上托管公共Microsoft 365，则还需要删除指向它的 CNAME 记录。  <br/> > [!IMPORTANT]>删除将电子邮件路由到此自定义域的 MX 记录后，电子邮件将停止工作，直到你将域添加到新帐户、设置新的 MX 记录并设置用户。 删除 Lync 的 DNS 记录时，Lync 将停止工作。 删除指向公共网站的 CNAME 记录后，该记录将不可用。           [删除域](remove-a-domain.md) 。  <br/> |
|设置新订阅的自定义域，并设置用户。  <br/> | 设置新订阅，包括为自定义域创建所需的 DNS 记录。  <br/>  使用自定义域上的电子邮件地址创建用户。  <br/> |
|将数据从旧订阅转移到新订阅。  <br/> | 在单独的浏览器窗口中登录这两个帐户：  <br/>  右键单击浏览器图标，然后打开两个专用浏览器窗口。 可以在两个窗口中使用不同的凭据登录这两个帐户。  <br/> [在订阅之间传输管理设置](#email) <br/> [转移团队网站结构和数据](#transfer-team-site-structure-and-data) <br/> [在订阅之间传输公共网站](#transfer-a-public-website-between-subscriptions) <br/> [在订阅之间传输管理设置](#email) <br/> |
|通过致电 Microsoft 支持团队取消你已完成计划的Microsoft 365。  <br/> | 验证新订阅是否正常工作，并且所有数据已转移。  <br/>  [联系客户支持](../../business-video/get-help-support.md) 以取消旧订阅。  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>在订阅之间传输管理设置

转到每个帐户上的以下页面，然后根据旧帐户的设置设置新帐户。
  
如果要将数据从企业或Microsoft 365 Microsoft 365中型企业版Microsoft 365 企业版，则管理页面的结构会有所不同。 观看视频[：介绍Microsoft 365 企业版，](../index.yml)然后转到以下位置查看管理员设置。
  
对于Microsoft 365 企业版和Microsoft 365中型企业：
  
|**位置**|**用途**|
|:-----|:-----|
|**管理员** \>**Microsoft 365** \> **服务设置** <br/> |为邮件、网站、Lync、用户软件、密码、社区、权限管理和移动设置选择每个选项卡。  <br/> |
|**管理员** \>**Exchange** <br/> | Exchange Online设置  <br/> |
|**管理员** \>**SharePoint** <br/> | SharePoint Online 设置  <br/> |
|**管理员** \>**Skype for Business** <br/> |其他Skype for Business设置  <br/> |

For Microsoft 365 Small Business
  
|**位置**|**用途**|
|:-----|:-----|
|**管理员** \>**管理组织范围的设置** <br/> |管理设置  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>在订阅之间传输公共网站

如果你有一个公共网站托管在 Microsoft 365，你需要保存它，然后在你的新订阅上重新创建它。
  
> [!NOTE]
> 如果公共网站托管在 DNS 托管提供商中，则无需进行更改。 它将不会受你的转换影响。
  
若要将文档库或列表内容从 SharePoint Online 环境保存到文件共享或本地计算机，请参阅手动迁移 SharePoint [Online 内容](/sharepoint/troubleshoot/migration-tool/content-manual-migration)。
  
> [!NOTE]
> 公共网站迁移应用程序无法将数据转移到其他订阅。
  
## <a name="transfer-team-site-structure-and-data"></a>转移团队网站结构和数据

有几种方法可以保存或传输团队网站数据：
  
- 可以将旧网站另存为模板，将模板导入新网站。

- 若要传输文档，请首先手动在新建网站上重新创建层次结构。 然后，您可以同时打开SharePoint网站，使用资源管理器打开这两Windows库，并复制和粘贴文档。 请参阅 [视频：使用资源管理器打开来复制或移动库文件](https://support.microsoft.com/office/d18d21a0-1f9f-4f6c-ac45-d52afa0a4a2e)。

- 若要传输列表数据，请保存 [列表模板](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393)，并使用保存的模板在新建网站上重新创建列表。

- 若要将 SharePoint Online 环境 (OneDrive for Business 或工作组网站) 中的文档库或列表内容保存到文件共享或本地计算机，请参阅有关手动迁移[SharePoint Online 内容的信息](/sharepoint/troubleshoot/migration-tool/content-manual-migration)。

## <a name="transfer-users-data-between-subscriptions"></a>在订阅之间传输用户数据

### <a name="email"></a>电子邮件：

要求用户在 [设置新订阅](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) 后移动其电子邮件、联系人、任务和日历信息。 他们可以使用其初始用户名访问旧电子邮件，例如 sue@contoso.onmicrosoft.com。
  
### <a name="onedrive-for-business-data"></a>OneDrive for Business数据：

要求用户将内容复制[/OneDrive for Business同步到其计算机](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd)，然后将内容添加回其新订阅。

### <a name="onenote"></a>OneNote 

要求用户[备份OneNote](https://support.microsoft.com/office/back-up-notes-f58b34b0-611d-435e-87fa-7942a1767af4?ui=en-us&rs=en-us&ad=us)[将笔记从](https://support.microsoft.com/en-us/office/restore-notes-from-a-backup-5daf9cb0-6769-4998-a5de-f044fdd0d831?ui=en-us&rs=en-us&ad=us)备份还原到其新订阅。
