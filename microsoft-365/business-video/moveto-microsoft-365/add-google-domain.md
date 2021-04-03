---
title: 添加 Google Workspace 域
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何将域从 Google Workspace 移动到 Microsoft 365 商业版。
ms.openlocfilehash: 814e714527467bb6e7008ea141989f3117ddcdd8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578767"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>将 Google Workspace 域添加到 Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

将 Google Workspace 域添加到 Microsoft 365 商业版，以便你可以继续使用你的企业电子邮件地址。

## <a name="try-it"></a>试一试！

1. 转到 [Microsoft 365 管理中心](https://admin.microsoft.com)。
1. 在 Microsoft 365 管理中心的左侧导航中，选择"显示全部"和"**设置**"，然后选择"**域"。**
1. 选择 **"添加域**"，输入您的域名，然后选择"**使用此域"。** 
1. 选择" **将 TXT 记录添加到域 DNS** 记录"，选择" **继续**"，然后复制 TXT 值。 
1. 返回到 Google [管理](https://admin.google.com)控制台，选择"域"，"管理域"，"查看详细信息 **"，"** 管理域 **"，"DNS"，** 然后向下滚动到"**自定义资源记录"。** 
1. 打开记录类型下拉列表，选择 **"TXT"，** 粘贴复制的 TXT 值，然后选择"添加 **"。** 

    更新通常需要几分钟时间，但最多可能需要 48 小时。 
1. 返回到 Microsoft 365 管理中心，选择 **"验证**"，然后选择"关闭 **"。** 
1. 若要将域设置为用户的主电子邮件，请在左侧导航中，选择"用户""  >  **活动用户"。** 
1. Choose a user， select **Manage username and email**， **Edit**， select your domain from the dropdown， then select **Done** and **Save changes**. 
1. 对每个用户重复此过程。 

    完成后，即可安装 Office 应用，将电子邮件和日历项目迁移到 Microsoft 365。 