---
title: 将内容类型推送到中心
description: 了解如何将内容类型推送到中心
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
ms.openlocfilehash: 22d146b1d376bab134e82ad7d1313cb7881ca45b
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "50144967"
---
# <a name="push-content-types-to-a-hub"></a>将内容类型推送到中心

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


若要使重要内容类型与 SharePoint 库和列表更为一致，可将其推送到选择的中心。 推送内容类型操作会自动将内容类型添加到在与中心相关联的网站上创建的所有新列表和库中，以及中心的任何新增网站中。 此功能需要 [SharePoint Syntex](index.md) 许可证。

若要使用此功能，必须已发布正在推送的内容类型。

将内容类型推送到中心

1. 在 SharePoint 管理中心中，展开“**内容服务**”，然后选择“**内容类型库**”。
2. 选择要推送到中心的内容类型。
3. 单击命令栏中的“**编辑**”。
4. 单击“**选择中心网站**”。
5. 选择所需的中心网站，然后选择“**确定**”。
6. 选择“**保存**”。

首次将内容类型推送到现有中心及其现有关联网站时，从访问中心或关联网站开始，最多可能需要一个小时才能更新网站中的设置。 中心的新增关联网站则无需等待这样一段时间，相应设置会在几分钟内体现出来。

更新设置后，具有这些设置的内容类型将在几分钟内在任何与中心新关联的网站中变得可用。 然后，任何新创建的列表或库都将在创建后几分钟内自动添加该内容类型。 仅当推送的内容类型从文档内容类型直接或间接派生时，才会将其添加到文档库，并且仅在它不直接或间接从文档内容类型派生的情况下，才会将内容类型添加到列表中。

## <a name="see-also"></a>另请参阅
