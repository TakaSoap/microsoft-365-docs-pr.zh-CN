---
title: 使用基于 SKOS 的格式导入术语集
description: 了解如何使用基于 SKOS 的格式导入术语集
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: aaed88463f690853672780b48a8ee3857a956847
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295795"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a>使用基于 SKOS 的格式导入术语集

您可以使用基于 SKOS 的格式导入术语集。 有关格式的详细信息，请参阅 [SharePoint 分类 SKOS 格式参考](skos-format-reference.md)。

建议将您的导入文件保留为少于20000个术语。 较大的文件可能会增加验证和导入所需的时间。

1. 在 SharePoint 管理中心中，展开 " **内容服务**"，然后单击 " **术语库**"。

2. 选择要在其中导入术语集的术语组。

3. 在命令栏中，单击 " **导入术语集**"。
 
4.  如果要下载用作模板的示例文件，请单击 **sample-metadata** 以获取使用基于 SKOS 的格式的示例文件。
 
5.  创建包含要导入 & 术语的术语集的导入文件。

6.  在 " **文件格式**" 下，选择 " **SKOS ( * ttl) **。

7.  单击 " **浏览** " 并导航到您的导入文件并将其添加。

8.  单击“导入”****。 在导入完成之前，请勿关闭面板。

成功导入文件后，将显示一条成功消息，并且术语库将刷新，并且您可以导航到新创建的术语集。

## <a name="see-also"></a>另请参阅

[托管元数据简介](https://docs.microsoft.com/sharepoint/managed-metadata)

[文档理解概述](document-understanding-overview.md)

[ (网站级别) 导入术语集 ](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)