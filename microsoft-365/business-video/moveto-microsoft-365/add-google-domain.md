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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- admindeeplinkMAC
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何将域从 Google Workspace 移动到 Microsoft 365 for business。
ms.openlocfilehash: b41fdf304d0f0b9680f87f40a4564573593d6e75
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60204775"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>将 Google Workspace 域添加到Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

将 Google Workspace 域Microsoft 365商业应用，以便你可以一直使用你的企业电子邮件地址。

## <a name="try-it"></a>试一试！

1. 转到["Microsoft 365 管理中心"。](https://admin.microsoft.com)
1. In the Microsoft 365 管理中心， in the left nav， select **Show all**  >  **设置**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**Domains**</a>.
1. 选择 **"添加域**"，输入您的域名，然后选择"**使用此域"。** 
1. 选择" **将 TXT 记录添加到域 DNS** 记录"，选择" **继续**"，然后复制 TXT 值。 
1. 返回到 Google [管理](https://admin.google.com)控制台 **，选择"** 域"，"**管理** 域"，"查看详细信息"，"管理域"，"DNS"，然后向下滚动到"**自定义资源记录"。**   
1. 打开记录类型下拉列表，选择 **"TXT"，** 粘贴复制的 TXT 值，然后选择"添加 **"。** 

    更新通常需要几分钟时间，但最多可能需要 48 小时。 
1. 返回到管理 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">中心，选择</a>"**验证"，** 然后选择"关闭 **"。** 
1. 若要将域设置为用户的主电子邮件，请在左侧导航中，选择"用户""  >  [**活动用户"。**](https://go.microsoft.com/fwlink/p/?linkid=834822) 
1. Choose a user， select **Manage username and email**， **Edit**， select your domain from the dropdown， then select **Done** and **Save changes**. 
1. 对每个用户重复此过程。 

    完成后，即可安装应用，Office电子邮件和日历项目迁移到Microsoft 365。 