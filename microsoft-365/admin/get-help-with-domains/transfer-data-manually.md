---
title: 在两个帐户之间手动传输数据
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: 了解在更改计划或公司名称时如何在两个 Microsoft 365 帐户之间手动转移数据，或将多个订阅组合为一个。
ms.openlocfilehash: 69476687915024accabdce2a603ebdd7e8b653af
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399868"
---
# <a name="transfer-data-manually-between-two-accounts"></a>在两个帐户之间手动传输数据

准备汇总你的 sleeves，并在日历上阻止一段时间：在两个 Microsoft 365 帐户之间传输数据是一个手动、复杂且耗时的过程。 这不是自动或受支持的过程。 我们将开始着手。
  
> [!CAUTION]
> 在流程的过程中，Microsoft 365 上托管的电子邮件、Skype for Business 和公共网站将不起作用。 用户将获取新的用户名和密码，并将需要重置 Outlook。

**如果应用了以下任一情况，则仅使用本主题中的说明手动传输数据：**
  
- 您需要更改为其他服务系列中的计划。

- 您的公司名称已更改，并且您决定创建新的订阅并迁移数据，因为您要使用不同的初始域名称。

- 您需要将多个订阅合并为一个新的。

> [!IMPORTANT]
> 如果您需要[更改订阅计划](../../commerce/subscriptions/switch-to-a-different-plan.md)并可以使用 "切换计划向导"，或者如果您需要转移到同一订阅系列中的新订阅计划，即使 "切换计划向导" 不起作用，您也不需要手动传输数据，并且没有停机时间。

|**Tasks**|**Steps**|
|:-----|:-----|
|购买要移到的计划。  <br/> |当你注册时，请在初始域名中指定要使用的公司名称： *yourcompany* 、 *yourcompany* -public.sharepoint.com 和*yourcompany* 。 您需要使用与为任何现有订阅所做的*yourcompany*不同的名称。  <br/> > [!NOTE]> 在取消订阅以释放从我们的系统中使用*yourcompany*的初始域名时，通常至少需要几个月。 即使您计划保存旧 Microsoft 365 订阅中的所有数据，并取消该订阅，旧的*yourcompany*值也不会立即可用于新的订阅。           |
|从旧 Microsoft 365 订阅中删除你的自定义域。  <br/> | 在删除域以从用户电子邮件地址中删除域名并删除自定义域的电子邮件和 Lync 的 DNS 记录之前，请执行[所需的步骤](remove-a-domain.md)。 如果你在 Microsoft 365 上托管你的公共网站，你还需要删除指向它的 CNAME 记录。  <br/> > [!IMPORTANT]> 删除了将电子邮件路由到此自定义域的 MX 记录后，电子邮件将停止工作，直到您向新帐户添加了域、设置新的 MX 记录并设置您的用户。 当您删除 Lync 的 DNS 记录时，Lync 将停止工作。 删除指向公共网站的 CNAME 记录后，该记录将不可用。           [删除域](remove-a-domain.md)。  <br/> |
|为新订阅设置自定义域，并设置您的用户。  <br/> | 设置新的订阅，包括为自定义域创建所需的 DNS 记录。  <br/>  创建您的用户并在自定义域上使用电子邮件地址。  <br/> |
|将数据从旧订阅传输到新订阅。  <br/> | 在单独的浏览器窗口中登录两个帐户：  <br/>  右键单击 "Internet Explorer" 图标，然后打开两个 "InPrivate 浏览器" 窗口。 您可以在两个窗口中使用不同的凭据登录这两个帐户。  <br/> [在订阅之间传输管理设置](#email) <br/> [传输团队网站结构和数据](#transfer-team-site-structure-and-data) <br/> [在订阅之间传输公共网站](#transfer-a-public-website-between-subscriptions) <br/> [在订阅之间传输管理设置](#email) <br/> |
|通过调用 microsoft Microsoft Microsoft 支持 for Microsoft 365，取消已完成计划的订阅。  <br/> | 验证新订阅是否正常工作以及是否已传输所有数据。  <br/>  [联系客户支持](../contact-support-for-business-products.md)以取消旧订阅。  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>在订阅之间传输管理设置

转到每个帐户上的以下页面，并根据旧帐户的设置设置新帐户。
  
如果要将数据从 Microsoft 365 传输到 Microsoft 365 中型企业版或 Microsoft 365 企业版，则管理页面的结构各不相同。 观看[视频：介绍 Microsoft 365 企业版](https://docs.microsoft.com/microsoft-365/admin/)，并转到以下位置以查看管理员设置。
  
对于 Microsoft 365 企业版和 Microsoft 365 中型企业版：
  
|**Location**|**用途**|
|:-----|:-----|
|**管理员** \>**Microsoft 365** \>**服务设置** <br/> |选择每个选项卡，以获取邮件、网站、Lync、用户软件、密码、社区、权限管理和移动的设置。  <br/> |
|**管理员** \>**Exchange** <br/> | Exchange Online 设置  <br/> |
|**管理员** \>**SharePoint** <br/> | SharePoint Online 设置  <br/> |
|**管理员** \>**Skype For business** <br/> |其他 Skype for Business 设置  <br/> |

适用于 Microsoft 365 小型企业版
  
|**Location**|**用途**|
|:-----|:-----|
|**管理员** \>**管理组织范围的设置** <br/> |管理设置  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>在订阅之间传输公共网站

如果在 Microsoft 365 上托管了一个公共网站，则需要将其保存并在新订阅上重新创建它。
  
> [!NOTE]
> 如果您的公共网站托管在 DNS 托管提供商处，则不需要进行任何更改。 您的转换不会受到影响。
  
若要将文档库或列表内容从 SharePoint Online 环境保存到文件共享或本地计算机，请参阅[SharePoint online 内容的手动迁移](https://go.microsoft.com/fwlink/p/?LinkId=402910)。
  
> [!NOTE]
> 公共网站迁移应用无法将数据传输到其他订阅。
  
## <a name="transfer-team-site-structure-and-data"></a>传输团队网站结构和数据

有几种方法可以保存或传输团队网站数据：
  
- 您可以将旧网站另存为模板，并将该模板导入到新网站。

- 若要传输文档，请首先手动在新网站上重新创建层次结构。 然后，您可以同时打开这两个 SharePoint 团队网站，同时使用 Windows 资源管理器打开文档库，并复制并粘贴文档。 请参阅[视频：使用 "使用资源管理器打开" 复制或移动库文件](https://support.office.com/article/where-to-store-files-c7c20284-bc94-47f4-9728-d28e9daf0790)。

- 若要转移列表数据，请保存[列表模板](https://support.microsoft.com/en-us/office/manage-list-templates-c3884ad1-bc49-44b8-b3d6-3bc6a01eb393)，并使用保存的模板在新网站上重新创建列表。

- 若要将文档库或列表内容从 SharePoint Online 环境（OneDrive for Business 或工作组网站）保存到文件共享或本地计算机，请参阅[有关手动迁移 Sharepoint online 内容的信息](https://support.microsoft.com/kb/2783484)。

## <a name="transfer-users-data-between-subscriptions"></a>在订阅之间传输用户数据

### <a name="email"></a>电子邮件：

在设置新的订阅之后，要求用户[移动其电子邮件、联系人、任务和日历信息](https://support.office.com/article/0996ece3-57c6-49bc-977b-0d1892e2aacc.aspx)。 他们可以使用其初始用户名（如 sue@contoso.onmicrosoft.com）访问其旧的电子邮件。
  
### <a name="onedrive-for-business-data"></a>OneDrive For Business 数据：

请用户将 OneDrive for business 内容复制/同步[到其计算机](https://support.office.com/article/59b1de2b-519e-4d3a-8f45-51647cf291cd.aspx)，然后将其添加回其新订阅。
