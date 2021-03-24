---
title: 管理自动化文件上载
description: 启用内容分析并配置将提交进行分析的文件扩展名和电子邮件附件扩展名
keywords: 自动化， 文件， 上传， 内容， 分析， 文件， 扩展名， 电子邮件， 附件
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 72405ad7500bf5d672f66ea64634e60c29ad1704
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056611"
---
# <a name="manage-automation-file-uploads"></a>管理自动化文件上载

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

启用内容分析功能，以便某些文件和电子邮件附件可以自动上载到云，以便自动调查进行其他检查。

通过指定文件扩展名和电子邮件附件扩展名来标识文件和电子邮件附件。 

例如，如果将 *exe* 和 *bat* 添加为文件或附件扩展名，则具有这些扩展名的所有文件或附件将自动发送到云，以在自动调查期间进行其他检查。 

## <a name="add-file-extension-names-and-attachment-extension-names"></a>添加文件扩展名和附件扩展名。

1. 在导航窗格中，选择"**设置**  >  **""自动化文件上载"。** 

2. 在开和 **关之间切换** 内容分析 **设置**。

3. 使用逗号配置以下扩展名和单独的扩展名：
   - **文件扩展名** 名称 - 将提交除电子邮件附件以外的可疑文件进行其他检查
  

## <a name="related-topics"></a>相关主题
- [管理自动化文件夹排除项](manage-automation-folder-exclusions.md)
