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
ms.collection: enabler-strategic
search.appverid: ''
ms.localizationpriority: high
ms.openlocfilehash: 6f472754484d7bb41485b94d65689009d2c615fd
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189209"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a>使用基于 SKOS 的格式导入术语集

可以使用基于 SKOS 的格式导入术语集。 有关格式的详细信息，请参阅 [SharePoint 分类 SKOS 格式参考](skos-format-reference.md)。 此功能需要 [SharePoint Syntex](index.md) 许可证。

建议将导入文件保持在 20,000 个术语以下。 较大的文件可能会增加验证和导入所需的时间。

1. 在 SharePoint 管理中心中，展开“**内容服务**”，然后单击“**术语库**”。

2. 选择要导入术语集的术语组。

3. 在命令栏中，单击“**导入术语集**”。

4. 若要下载用作模板的示例文件，请单击 **sample-metadata.ttl** 以获取使用基于 SKOS 的格式的示例文件。

5. 创建包含了要导入的术语集和术语的导入文件。

6. 在“**文件格式**”下，选择 **SKOS (*.ttl)**。

7. 单击“**浏览**”，然后导航到添加导入文件的地方。

8. 单击“**导入**”。在导入完成前，请勿关闭面板。

成功导入文件时，将显示一条成功消息，并且将刷新术语库，以及可以导航到新创建的术语集。

## <a name="see-also"></a>另请参阅

[托管元数据简介](/sharepoint/managed-metadata)

[文档理解概述](document-understanding-overview.md)

[导入术语集（网站级别）](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)
