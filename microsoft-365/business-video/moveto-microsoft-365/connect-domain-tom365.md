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
description: 了解如何将域连接到Microsoft 365。
ms.openlocfilehash: b91b6fcc297449906e54a8f61f52b9d3c8b01ca6d009d43fa69a5873b81eb873
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53887859"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>连接域Microsoft 365企业

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

设置邮箱并Microsoft 365 Google Workspace 中移动电子邮件数据后，可以将你的域连接到Microsoft 365。 

首先，你需要从 Google 中删除现有 DNS 记录，然后我们可以从 Microsoft 365。

## <a name="try-it"></a>试一试！

1. 登录到 Google Workspace 管理控制台[，admin.google.com。](https://admin.google.com)
1. 选择 **"域****"、"管理域****"、"查看详细信息**"和"**管理域**"，然后在左侧导航中选择 **"DNS"。**
1. 向下滚动到" **综合记录"，** 打开 **"Google Workspace"，** 选择" **删除**"，然后 **再次"删除** "。
1. 向下滚动到 **"自定义资源** 记录"并删除出现的任何现有 DNS 记录，包括之前可能为自定义资源Microsoft 365。
1. 转到["Microsoft 365 管理中心"。](https://admin.microsoft.com)
1. 在左侧导航中，选择"全部 **显示****"，设置，"****域"。**
1. 然后选择默认域。
1. 选择 **"继续设置**"，然后，若要连接域，请选择"继续 **"。**
1. 向下滚动以查看需要复制到 Google 的 DNS 记录。
1. 打开 **"MX 记录"，** 在" **指向地址或值**"下复制记录。
1. 返回到 Google，在"自定义 **资源记录**"部分，打开记录类型下拉列表并选择 **"MX"。**
1. 在 **"数据** "字段中，粘贴复制的记录。
1. 然后，选择“**添加**”。
1. 对 CNAME 和 TXT 记录重复此过程，并添加 Google DNS 管理页中的值。
1. 返回到中心Microsoft 365 管理 **选择继续。**

    您的域设置已完成。