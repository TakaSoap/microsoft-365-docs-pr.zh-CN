---
title: 审阅
description: 载入后查看部分。
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 3bb6ef605d360e259ef9fa91ed51da35506a2942
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208813"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a>步骤 6：查看选择以创建程序包。

1. 在此选项卡上，该服务显示测试详细信息并运行快速完成性检查。

    "**验证通过****"或**"验证失败"消息显示是否可以继续执行下一步。

2. 查看测试详细信息，如果满意，请单击"创建 **"** 按钮。

    :::image type="content" alt-text="查看验证。" source="Media/validation.png" lightbox="Media/validation.png":::

3. 这会将程序包载入测试基础环境。 如果成功创建程序包，将触发一个自动测试，用于验证是否可以在 Azure 上成功执行程序包。

    ![成功结果。](Media/successful.png)

    > [!NOTE]
    > 你将从 Azure 门户收到通知，通知程序包验证是成功还是失败。
    >
    > 请注意，此过程最多可能需要 24 小时，因此，如果您未在网页上处于活动状态，您的网页可能会超时，因此，通知不会通知您此按需运行完成。

    - 如果发生这种情况，可以在"管理程序包"选项卡上查看 **程序包** 的状态。

      :::image type="content" alt-text="用于管理程序包的图像。" source="Media/managepackages.png" lightbox="Media/managepackages.png":::

    - 为了成功进行测试，可以按计划间隔（通常在上传后几天开始）通过"测试摘要"、"安全更新结果"和"**功能** 更新结果"页面查看测试结果。
  
    - 测试失败时，需要上传新程序包。 

      可以从"**安全更新结果"和**"功能更新结果"页下载测试日志以 **进一步分析**。

    - 如果遇到重复测试失败，请联系 testbasepreview@microsoft.com 并输入错误的详细信息。

## <a name="next-steps"></a>后续步骤

通过下面的链接发现我们的内容指南。

> [!div class="nextstepaction"]
> [下一步](contentguideline.md)
