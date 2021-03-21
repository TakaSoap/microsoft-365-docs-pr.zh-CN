---
title: 设置 Microsoft Viva 主题
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: 了解如何设置 Microsoft Viva 主题
ms.openlocfilehash: 629008e083d71e09632b05e21eaefb011d7d9ce2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929440"
---
# <a name="set-up-microsoft-viva-topics"></a>设置 Microsoft Viva 主题

可以使用 Microsoft 365 管理中心来设置和配置 [主题](topic-experiences-overview.md)。 

规划在环境中设置和配置主题的最佳方法非常重要。 在开始本文中的过程之前，请务必阅读 Plan [for Microsoft Viva](plan-topic-experiences.md) Topics。

您必须订阅 [Viva 主题](https://www.microsoft.com/microsoft-viva/topics) ，并且必须是全局管理员或 SharePoint 管理员才能访问 Microsoft 365 管理中心并设置主题。

如果已配置 SharePoint 以 [需要托管设备](/sharepoint/control-access-from-unmanaged-devices)，请确保从托管设备设置主题。

## <a name="video-demonstration"></a>视频演示

此视频演示在 Microsoft 365 中设置主题的过程。

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a>设置主题

设置主题

1. 在 [Microsoft 365 管理中心](https://admin.microsoft.com)中，选择" **设置"，** 然后查看" **文件和内容"** 部分。
2. 在"**文件和内容"部分**，单击"**将人员连接到知识"。**

    ![将人员与知识连接](../media/admin-org-knowledge-options.png) 

3. 在" **将人员连接到知识"页上** ， **单击"** 开始"以完成设置过程。

    ![入门](../media/k-get-started.png) 

4. 在" **选择 Viva 主题如何查找** 主题"页上，您将配置主题发现。 在" **选择 SharePoint 主题源** "部分，选择要在发现期间作为主题源对哪些 SharePoint 网站进行爬网。 从以下项中进行选择：
    - **所有网站**：组织的所有 SharePoint 网站。 这包括当前网站和未来网站。
    - **全部，所选网站除外**：键入要排除的网站的名称。  还可以上载想要从发现中退出的网站列表。 将来创建的网站将包含为主题发现源。 
    - **仅选定网站**：键入要包含的网站的名称。 您还可以上载网站列表。 将来创建的网站不会作为主题发现源包含在内。
    - **无网站**：不包括任何 SharePoint 网站。

    ![选择如何查找主题](../media/ksetup1.png) 
   
5. 在" **按名称排除** 主题"部分，可以添加要从主题发现中排除的主题的名称。 使用此设置可防止敏感信息作为主题包含在内。 选项包括：
    - **不排除任何主题** 
    - **按名称排除主题**

    ![排除主题](../media/topics-excluded-by-name.png) 

     (发现之后，知识管理员还可以排除主题中心) 

    #### <a name="how-to-exclude-topics-by-name"></a>如何按名称排除主题    

    如果需要排除主题，在选择"按名称排除主题"后，下载 .csv 模板，然后使用要从发现结果中排除的主题列表更新它。

    ![排除 CSV 模板中的主题](../media/exclude-topics-csv.png) 

    在 CSV 模板中，输入有关要排除的主题的以下信息：

    - **名称**：键入要排除的主题的名称。 可通过 2 种方法执行此操作：
        - 完全匹配：可以包含确切的名称或缩写词 (例如 *Contoso* 或 *ATL*) 。
        - 部分匹配：可以排除其中包含特定单词的所有主题。  例如 *，arc 将* 排除包含单词 *arc* 的所有主题，如弧 *形圆*、*弧* 形圆或 *培训弧*。请注意，它将不会排除将文本作为单词的一部分包含的主题，例如体系结构 *。*
    - **代表 (可选**) ：如果要排除首字母缩写词，请键入首字母缩写词代表的单词。
    - **MatchType-Exact/Partial**：键入您输入 *的名称是精确* 匹配类型还是 *部分* 匹配类型。

    完成并保存 .csv 文件后， **选择"浏览** "找到并选择它。
    
    选择“下一步”。

6. 在 **"谁可以看到主题以及** 他们在哪里可以看到主题"页面上，你将配置主题可见性。 在" **谁可以看到** 主题"设置中，选择谁有权访问主题详细信息，例如突出显示的主题、主题卡片、搜索中的主题答案和主题页面。 可以选择：
    - **我的组织中的每个人**
    - **仅选定人员或安全组**
    - **没人**

    ![谁可以看到主题](../media/ksetup2.png)  

    > [!Note] 
    > 虽然此设置允许你选择组织的任何用户，但只有分配了主题体验许可证的用户才能查看主题。

7. 在" **主题管理的权限** "页中，选择能够创建、编辑或管理主题的用户。 在" **谁可以创建和编辑主题** "部分，可以选择：
    - **我的组织中的每个人**
    - **仅选定人员或安全组**
    - **没人**

    ![主题管理权限，可以创建和编辑主题](../media/ksetup3.png) 

8. 在" **谁可以管理主题** "部分，可以选择：
    - **我的组织中的每个人**
    - **仅选定人员或安全组**

    ![主题管理的权限](../media/km-setup-create-edit-topics.png) 

    选择“下一步”。

9. 在 **"创建主题中心** "页上，您可以创建主题中心网站，可在其中查看主题页面并管理主题。 在" **网站名称"** 框中，键入主题中心的名称。 可以选择在"说明"框中键入 **简短** 说明。 

   选择“下一步”。

   ![创建知识中心](../media/ksetup4.png)  

10. 在 **审查并完成** 页面上，可查看所选设置并选择进行更改。 如果对你的选择感到满意，请选择 **激活**。

11. 将显示 **"Viva 主题已激活** "页，确认系统现在开始分析所选主题网站并创建主题中心网站。 选择“**完成**”。

12. 你将返回到"将人员连接到 **知识"** 页面。 在此页面中，可选择 **管理**，对配置设置进行任何更改。 

    ![应用的设置](../media/ksetup7.png)    

请注意，首次启用主题发现时，所有建议的主题最多可能需要两周时间才能显示在"管理主题"视图中。 主题发现将在新内容或内容更新时继续。 在 Viva 主题评估新信息时，组织中的建议主题数量通常有波动。

## <a name="assign-licenses"></a>分配许可证

配置主题体验后，必须为使用主题的用户分配许可证。 只有具有许可证的用户才能查看有关主题的信息，包括突出显示、主题卡片、主题页面和主题中心。 

以分配许可证：

1. 在Microsoft 365 管理中心中，在 **用户** 下，点击 **活动用户**。

2. 选择要许可的用户，然后单击"许可证 **和应用"。**

3. 在 **"许可证"** 下，**选择"Viva 主题"。**

4. 在 **"应用"** 下，确保已选中"带索引 (**的 Graph** 连接器搜索") "Viva 主题"和 **"Viva** 主题"。

   > [!div class="mx-imgBorder"]
   > ![Microsoft 365 管理中心中的 Microsoft Viva 主题许可证](../media/topic-experiences-licenses.png)

5. 单击“**保存更改**”。

## <a name="manage-topic-experiences"></a>管理主题体验

设置主题后，可以在 [Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)管理中心中更改在设置期间选择的设置。 请参阅以下参考：

- [在 Microsoft Viva 主题中管理主题发现](topic-experiences-discovery.md)
- [在 Microsoft Viva 主题中管理主题可见性](topic-experiences-knowledge-rules.md)
- [在 Microsoft Viva 主题中管理主题权限](topic-experiences-user-permissions.md)
- [在 Microsoft Viva 主题中更改主题中心的名称](topic-experiences-administration.md)

## <a name="see-also"></a>另请参阅

[主题体验概述](topic-experiences-overview.md)
