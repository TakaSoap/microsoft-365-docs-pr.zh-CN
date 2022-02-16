---
title: 将你的域连接到 Microsoft 365
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
description: 了解如何将域连接到Microsoft 365。
ms.openlocfilehash: d54b3bbf00dd0cf37006924e2884f2861c345d3e
ms.sourcegitcommit: 559df2c86a7822463ce0597140537bab260c746a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2022
ms.locfileid: "62825537"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>连接域Microsoft 365企业

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

设置邮箱并Microsoft 365 Google Workspace 中移动电子邮件数据后，可以将你的域连接到Microsoft 365。 

首先，你需要从 Google 中删除现有 DNS 记录，然后我们可以从 Microsoft 365。

## <a name="try-it"></a>试一试！

1. 登录到 Google Workspace 管理控制台，[admin.google.com。](https://admin.google.com)
1. 选择 **左侧** 导航 **中的**"域"、"管理域"、查看详细信息 **、**"管理域"和"**DNS**"。
1. 向下滚动到" **综合记录**"，打开 **"Google Workspace"**，选择" **删除**"，然后 **再次"删除** "。
1. 向下滚动到 **"自定义资源** 记录"，并删除出现的任何现有 DNS 记录，包括之前可能为自定义资源Microsoft 365。
1. 转到[Microsoft 365 管理中心。](https://admin.microsoft.com)
1. 在左侧导航中，**选择"全部** 显示 > **设置** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**域"**</a>。
1. 然后选择默认域。
1. 选择 **"继续** 设置"，然后，若要连接域，请选择"继续  **"**。
1. 向下滚动以查看需要复制到 Google 的 DNS 记录。
1. 打开 **"MX 记录"**，在"指向 **地址或值**"下复制记录。
1. 返回到 Google，在"自定义资源记录"部分，打开记录类型下拉列表并选择 **"MX"**。
1. 在 **"数据** "字段中，粘贴复制的记录。
1. 然后，选择“**添加**”。
1. 对 CNAME 和 TXT 记录重复此过程，并添加 Google DNS 管理页中的值。
1. 返回到"Microsoft 365 管理中心，然后选择"继续 **"**。

    您的域设置已完成。