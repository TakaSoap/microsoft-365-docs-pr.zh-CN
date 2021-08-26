---
title: 验证数据存储位置并更新数据保留设置
description: 验证数据存储位置并更新 Microsoft Defender for Endpoint 的数据保留设置
keywords: 数据， 存储， 设置， 保留， 更新
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fbf9561e214be2180d57b3b4dcd2369061d7a7d6
ms.sourcegitcommit: 6c342a956b2dbc32be33bac1a23a5038490f1b40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58532843"
---
# <a name="verify-data-storage-location-and-update-data-retention-settings-for-microsoft-defender-for-endpoint"></a>验证数据存储位置并更新 Microsoft Defender for Endpoint 的数据保留设置

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-gensettings-abovefoldlink)。

在载入过程中，向导将让你完成 Defender for Endpoint 的数据存储和保留设置。 

完成载入后，可以在"数据保留设置"页中验证选择。

## <a name="verify-data-storage-location"></a>验证数据存储位置
在 [设置阶段](production-deployment.md)，你已选择存储数据的位置。 


可以通过导航到"常规"菜单下的"终结点设置数据保留 (\>  \> **验证) 。**


## <a name="update-data-retention-settings"></a>更新数据保留设置

可以更新数据保留设置。 默认情况下，保留期为 180 天。 

1. 在导航窗格中，选择"常规设置 \> **下 (** 终结点数据 \> ) 。 

2. 从下拉列表中选择数据保留期限。

    > [!NOTE]
    > 其他设置不可编辑。

3. 单击 **保存首选项**。

## <a name="related-topics"></a>相关主题
- [更新数据保留设置](data-retention-settings.md)
- [在 Defender for Endpoint 中配置警报通知](configure-email-notifications.md)
- [配置高级功能](advanced-features.md)
