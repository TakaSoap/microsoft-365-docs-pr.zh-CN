---
title: Microsoft 365 企业版业务连续性管理缓解措施
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 服务事件情景的一些缓解措施示例。
ms.openlocfilehash: ea9804d4f22a11ea9ffcda9d9939d70574c2e87e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601059"
---
# <a name="service-incident-mitigation-strategies"></a>服务事件缓解策略

下面的一些策略和情景说明了如何缓解 Microsoft 365 服务事件对业务流程产生的影响。

## <a name="service-incident-scenarios-and-potential-mitigations"></a>服务事件情景和可能的缓解措施

|Microsoft 365 依赖项|可能的缓解措施|
|---------|---------|
|事件管理系统需要通过 Exchange Online 联系待命的工程师和事件管理员。|确保事件管理系统支持多通道通信（如并行电子邮件、电话联络和短信通知）以及呼叫树层次结构（以便在主要的待命工程师未响应的情况下，由系统自动启用备用人员）。 还应在每条通知中包括备用人员联系方法，从而嵌入备用通信方法以方便参考。 如果事件管理服务不可用，则可使用其他通信方法（如 Yammer）进行紧急协作。|
|使用 Microsoft Teams 来存储通过客户端访问的文件。|Teams 将上传到客户端的文件存储在 SharePoint Online 文档库中。 仍可通过 SharePoint Online 访问文件。 告知用户 SharePoint Online 中的文件位置。|
|常规通信和事件管理会审过程需要使用 Microsoft Teams 电话会议。|使用第三方提供商建立备用的会议解决方案。|
|VoIP 电话用作辅助通信方式。|实现支持 PSTN 通话的非 VoIP 电话，尤其对于事件期间的网络和服务运营中心。 将员工移动电话号码添加到公司目录，以便通过移动数据网络联系关键人员。|
|文件存储和用户高效工作需要使用 OneDrive for Business。 配置[文件随选](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/OneDrive-Files-On-Demand-For-The-Enterprise/ba-p/117234)来释放本地用户驱动器上的空间。|OneDrive 同步功能提供了组策略，允许管理员要求在本地同步特定内容或在需要时释放空间。 若要缓解无法访问文档的风险，请配置此策略以便在本地同步重要文档。 告知用户对重要文档手动应用“始终在此设备上保留”设置。|
|使用 Exchange Online 与客户和供应商沟通业务中断情况。|公用的第三方社交网络可用作大量通信的替代方法。

## <a name="leveraging-mobile-app-access"></a>利用移动应用访问方法

随着移动应用的剧增，出现了全新的沟通方式，而 Microsoft 365 移动应用程序可作为复原策略的关键一环。 因为这些应用程序通过移动数据提供商网络连接到云服务，所以它们不依赖于组织内部的网络基础结构。

我们以 Outlook 为例。 根据所使用的电子邮件应用，用户可以通过不同的网络协议（https 或 MAPI）连接到其 Exchange Online 邮箱。 如果有一个服务事件涉及到其中一种协议，比如桌面客户端使用的 MAPI，那么你的用户仍可通过 Outlook Mobile 应用或 Outlook 网页版访问其邮箱。
  
如果你决定允许用户通过其移动设备连接到 Microsoft 365 服务，则可以使用 Microsoft Intune 安全地配置和管理这些设备。 在移动管理解决方案中注册用户帐户和设备后，请确保已下载并配置应用。
