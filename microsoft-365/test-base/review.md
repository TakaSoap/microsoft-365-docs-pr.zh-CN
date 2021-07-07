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
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 3bbd4959dd2f595e6e33e7967a719cf64072c06f
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322643"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a>步骤 6：查看选择以创建程序包。

1.  在此选项卡上，该服务显示测试详细信息并运行快速完成性检查。 

    A ```Validation passed``` 或 message shows whether you can proceed to next steps or ```Validation failed``` not.

2.  查看测试详细信息，如果满意，请单击 ```Create``` 按钮。 

![查看验证](Media/validation.png)

3.  这会将程序包载入测试基础环境。 如果成功创建程序包，将触发用于验证是否可以在 Azure 上成功执行程序包的自动测试。

![成功结果](Media/successful.png)

> [!Note]
> 你将从 Azure 门户收到通知，通知程序包验证是成功还是失败。 
>
> 请注意，此过程最多可能需要 24 小时，因此，如果您未在网页上处于活动状态，您的网页可能会超时，因此，通知不会通知您此按需运行完成。 

  - 如果发生这种情况，可以在选项卡上查看程序包 ```Manage packages``` 的状态。

![用于管理程序包的图像](Media/managepackages.png)

  - 对于成功测试，可以按计划间隔（通常在上传后几天开始）通过 和 页面查看其结果 ```Test Summary``` ```Security Updates Results``` ```Feature Updates Results``` 。
  
  - 测试失败时，需要上传新程序包。 
  
    可以从 和 ```test logs``` 页面下载 以进一 ```Security update results``` 步 ```Feature updates results``` 分析。

  - 如果遇到重复测试失败，请联系 testbasepreview@microsoft.com 并提供有关错误的详细信息。 

## <a name="next-steps"></a>后续步骤

通过下面的链接发现我们的内容指南。
> [!div class="nextstepaction"]
> [后续步骤](contentguideline.md)
