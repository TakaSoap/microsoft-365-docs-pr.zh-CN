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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何将域连接到 Microsoft 365。
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925106"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>将域连接到 Microsoft 365 商业版

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

设置 Microsoft 365 并移动来自 Google Workspace 的电子邮件数据后，可以将域连接到 Microsoft 365。 

首先，你需要从 Google 中删除现有 DNS 记录，然后我们可以从 Microsoft 365 添加新的 DNS 记录。

## <a name="try-it"></a>试一试！

1. 登录 Google Workspace 管理控制台[，admin.google.com。](https://admin.google.com)
1. 选择 **域**，**管理域**，**查看详细信息****，管理域**，然后在左侧导航中选择 **DNS。**
1. 向下滚动到综合 **记录**，打开 **Google Workspace，** 选择 **"删除**"，然后 **再次** 删除。
1. 向下滚动到 **自定义资源** 记录并删除显示的任何现有 DNS 记录，包括之前可能为 Microsoft 365 创建的任何 DNS 记录。
1. 转到 [Microsoft 365 管理中心](https://admin.microsoft.com)。
1. 在左侧导航中，选择"显示 **所有"、"****设置"和****"域"。**
1. 然后选择默认域。
1. 选择 **"继续** 设置"，然后，若要连接域，请选择"**继续"。**
1. 向下滚动以查看需要复制到 Google 的 DNS 记录。
1. 打开 **MX 记录**，在"指向 **地址或值**"下复制记录。
1. 返回到 Google，在"自定义资源记录 **"部分，** 打开记录类型下拉列表并选择 **MX。**
1. 在 **"数据** "字段中，粘贴复制的记录。
1. 然后，选择“**添加**”。
1. 对 CNAME 和 TXT 记录重复此过程，并添加 Google DNS 管理页中的值。
1. 返回到 Microsoft 365 管理中心，然后选择"**继续"。**

    域设置已完成。