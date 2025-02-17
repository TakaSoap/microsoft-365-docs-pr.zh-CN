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
ms.custom: admindeeplinkSPO
ms.localizationpriority: high
ms.openlocfilehash: 4a7a84023f3155c2b6f1405a3da5d8c5776d0047
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63322053"
---
# <a name="push-content-types-to-a-hub"></a>将内容类型推送到中心

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


若要使重要内容类型与 SharePoint 库和列表更为一致，可将其推送到选择的中心。 推送内容类型操作会自动将内容类型添加到在与中心相关联的网站上创建的所有新列表和库中，以及中心的任何新增网站中。 此功能需要 [SharePoint Syntex](index.md) 许可证。

若要使用此功能，必须已发布正在推送的内容类型。

将内容类型推送到中心

1. 在 SharePoint 管理中心中，展开“**内容服务**”，然后选择 <a href="https://go.microsoft.com/fwlink/?linkid=2185074" target="_blank">“**内容类型库**”</a>。
2. 选择要推送到中心的内容类型。
3. 单击命令栏中的“**编辑**”。
4. 单击“**选择中心网站**”。
5. 选择所需的中心网站，然后选择“**确定**”。
6. 选择“**保存**”。

第一次将内容类型推送到现有中心和其现有关联站点时，从访问中心或关联站点开始，可能需要长达一小时的时间才能在站点中更新设置。与中心的任何新关联都不需要此等待，并且将在几分钟内反映设置。

更新设置后，具有这些设置的内容类型将在几分钟内在任何与中心新关联的网站中变得可用。 默认库视图将更改为其中一个自动创建的视图。 如果有多个内容类型推送到同一个库，则最新内容类型（基于将这些内容类型推送到此库所属中心的操作顺序）将设为默认视图。  然后，任何新创建的列表或库都将在创建后几分钟内自动添加该内容类型。 仅当推送的内容类型从文档内容类型直接或间接派生时，才会将其添加到文档库，并且仅在它不直接或间接从文档内容类型派生的情况下，才会将内容类型添加到列表中。

## <a name="see-also"></a>另请参阅
