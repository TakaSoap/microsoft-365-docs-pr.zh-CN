---
title: 在Microsoft Defender for Endpoint中提交可疑文件
description: 了解如何使用Microsoft 365 Defender中的统一提交功能向 Microsoft 提交可疑的电子邮件、URL、电子邮件附件和文件以进行扫描。
keywords: 防病毒、垃圾邮件、网络钓鱼、文件、警报、Microsoft Defender for Endpoint、误报、假负、阻止文件、阻止 URL、提交、提交、报告
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.date: 06/15/2021
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
manager: dansimp
localization_priority: Normal
audience: ITPro
ms.topic: how-to
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
- m365solution-scenario
- m365scenario-fpfn
ms.custom: FPFN
ms.openlocfilehash: eaf16c08711f6c91c5ca7f3301cf1afd07cd4b9a
ms.sourcegitcommit: dd7e5b67ff4ae4e7f74490e437c1795933c74cc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64731730"
---
# <a name="submit-suspicious-files-in-microsoft-defender-for-endpoint"></a>在Microsoft Defender for Endpoint中提交可疑文件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用对象**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146806)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>希望体验 Microsoft Defender for Endpoint？ [注册免费试用](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-usewdatp-abovefoldlink)版。

在Microsoft Defender for Endpoint中，管理员可以使用统一提交功能将文件和文件哈希 (SHA) 提交给 Microsoft 以供审阅。 统一提交体验是一个一站式的商店，用于在一种易于使用的提交体验中提交电子邮件、URL、电子邮件附件和文件。 管理员可以使用Microsoft 365 Defender门户或Microsoft Defender for Endpoint警报页提交可疑文件。  

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 新的统一提交体验仅适用于包含 Microsoft 365 Defender、Microsoft Defender for Endpoint 计划 2 或 Microsoft Defender for Office 计划 2 的订阅。

- 若要将文件提交到 Microsoft，需要成为以下角色组之一的成员：

  - [Microsoft 365 Defender门户](../office-365-security/permissions-microsoft-365-security-center.md)中的 **组织管理****或安全管理员**。

- 有关如何向 Microsoft 提交垃圾邮件、网络钓鱼、URL 和电子邮件附件的详细信息，请参阅 [Microsoft 的报表消息和文件](../office-365-security/report-junk-email-messages-to-microsoft.md)。

## <a name="report-suspicious-items-to-microsoft-from-the-portal"></a>从门户向 Microsoft 报告可疑项目

如果你有一个文件，你怀疑可能是恶意软件或被错误地检测到，你可以提交给 Microsoft 进行分析使用Microsoft 365 Defender门户在https://security.microsoft.com/。

### <a name="submit-a-suspected-file-or-file-hash"></a>提交可疑文件或文件哈希

1. 打开Microsoft 365 Defender，<https://security.microsoft.com/>单击"**操作"&提交**，单击 **"提交**"，转到 **"文件"** 选项卡，然后选择 **"添加新提交**"。 

    > [!div class="mx-imgBorder"]
    > ![添加新提交](../../media/unified-admin-submission-new.png) 

2. 使用 **提交项到 Microsoft 以查看** 显示为提交 **文件** 或 **文件哈希** 的浮出控件。  

3. 在 **"选择提交类型** "框中，从下拉列表中选择 **"文件** "或 **"文件哈希** "。 

4. 提交文件时，单击 **"浏览文件**"。 在打开的对话框中，找到并选择该文件，然后单击 **"打开**"。 请注意，对于 **文件哈希** 提交，必须复制或键入文件哈希。 

5. 在此 **文件中，应将此文件归类为** 部分，选择 **恶意软件** (假负) 或 **不需要的软件**，或 **清理** (误报) 。
  
6. 接下来， **选择优先级**。 请注意，对于 **文件哈希** 提交， **低批量文件或文件哈希提交** 是唯一的选择，并且会自动选择。

    > [!div class="mx-imgBorder"]
    > ![将项目提交到 Microsoft 以供审阅](../../media/unified-admin-submission-file.png) 

8. 单击 **“提交”**。 
 
   如果要查看提交的详细信息，请从 **"提交"名称列表中** 选择提交，以打开 **"结果详细信息** "浮出控件。

## <a name="report-suspicious-items-to-microsoft-from-the-alerts-page"></a>从"警报"页向 Microsoft 报告可疑项目

还可以直接从 **"警报"** 页上的警报列表提交文件或文件哈希。 

1. 打开Microsoft 365 Defender，<https://security.microsoft.com/>单击 **事件&警报**，然后单击 **"警报**"查看警报列表。

2. 选择要报告的警报。 请注意，你正在提交嵌套在警报中的文件。  

3. 单击 **"管理警报"** 旁边的省略号以查看其他选项。 选择 **"将项目提交到 Microsoft 以供审阅**"。

    > [!div class="mx-imgBorder"]
    > ![从警报队列提交项目](../../media/unified-admin-submission-alerts-queue.png) 

4. 在打开的下一个浮出控件中，选择提交类型。 

    > [!div class="mx-imgBorder"]
    > ![完成所需的字段](../../media/unified-admin-submission-alert-queue-flyout.png) 

    如果选择 **"文件** "作为提交类型，请上传文件，对提交进行分类，然后选择优先级。
  
    如果选择 **"文件哈希** "作为提交类型，请从下拉列表中选择可用的文件哈希。 可以选择多个文件哈希。 
 
5. 单击 **“提交”**。 

## <a name="related-information"></a>相关信息

- [Microsoft 365 Defender中的Microsoft Defender for Endpoint](../defender/microsoft-365-security-center-mde.md)
- [解决误报/负数](defender-endpoint-false-positives-negatives.md)
- [在Microsoft Defender for Endpoint中查看和组织警报队列](alerts-queue.md)