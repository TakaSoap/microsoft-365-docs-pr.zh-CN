---
title: 存档第三方数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: 了解如何将第三方数据从社交媒体平台、即时消息平台和文档协作平台导入到 Microsoft 365 邮箱。
ms.openlocfilehash: 0db7019b607388b7c62fe19210b85b8410083f32
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035480"
---
# <a name="archive-third-party-data"></a>存档第三方数据

Microsoft 365 使管理员能够从社交媒体平台、即时消息平台和文档协作平台将第三方数据导入和存档到 Microsoft 365 组织中的邮箱。 可以导入到 Microsoft 365 的第三方数据源示例包括以下服务： 
  
- **社交：** Facebook、LinkedIn、Twitter 和 Yammer

- **即时消息：** Yahoo Messenger 和 GoogleTalk

- **文档协作：** Box 和 DropBox

- **纵向行业：** 客户关系管理（如 Salesforce Chatter）和金融服务（如 Bloomberg 和 Thomson Reuters）

- **短信/短信服务：** BlackBerry

导入第三方数据后，可以将 Microsoft 365 合规性功能（如诉讼保留、电子数据展示、就地存档、审核、通信合规性和保留策略）应用于此类数据。 例如，当将邮箱置于诉讼保留状态时，将保留第三方数据。 您可以使用 Microsoft 电子数据展示工具搜索第三方数据。 或者，您可以将存档和保留策略应用于第三方数据，就像 Microsoft 数据一样。 简言之，在 Microsoft 365 中存档第三方数据可帮助您的组织遵守政府和法规策略。

有两种方法可在 Microsoft 365 中导入和存档第三方数据：

- **在安全 & 合规性中心中使用第三方数据连接器：** 使用 Microsoft 365 合规性中心提供的自定义数据连接器。 在设置并配置连接器后，它会连接到第三方数据源，将项目的内容转换为电子邮件格式，然后将该项目导入到 Microsoft 365 中的邮箱中。 目前，您可以实现连接器以导入和存档来自 Facebook 商业页面、公司 Twitter 帐户、LinkedIn、即时 Bloomberg 和组织的人力资源（HR）数据的数据。 有关设置这些连接器之一的分步说明，请参阅：

   - **Facebook：** [使用连接器存档 Facebook 数据](archive-facebook-data-with-sample-connector.md)

   - **Twitter：** [使用连接器存档 Twitter 数据](archive-twitter-data-with-sample-connector.md)

   - **LinkedIn：** [设置用于存档 LinkedIn 数据的连接器](archive-linkedin-data.md)

   - **即时 Bloomberg：** [设置连接器以存档即时 Bloomberg 数据](archive-instant-bloomberg-data.md)

   - **HR 数据：** [设置连接器以导入 HR 数据](import-hr-data.md)

- **与 Microsoft 合作伙伴合作：** 您的组织与 Microsoft 合作伙伴合作，该合作伙伴将提供一个自定义连接器，该连接器将配置为定期从第三方数据源提取项目，然后通过第三方 API 连接到 Microsoft 云，并将这些项目导入到 Microsoft 365。 合作伙伴连接器还将项目的内容从第三方数据源转换为电子邮件，然后将其导入到 Microsoft 365 中的邮箱。 有关您可以使用的合作伙伴列表和此方法的分步过程，请参阅[在 Microsoft 365 中使用合作伙伴存档第三方数据](work-with-partner-to-archive-third-party-data.md)。
