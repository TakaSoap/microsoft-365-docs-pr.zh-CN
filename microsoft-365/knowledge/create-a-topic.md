---
title: 在 Microsoft Viva 主题中创建新主题
description: 如何在 Microsoft Viva 主题中创建新主题。
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-topics
ms.service: ''
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: fbdd0e9b75e92d8080d9aaf43a2d1eaa8baacbc3
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279374"
---
# <a name="create-a-new-topic"></a>新建主题 

在 Viva 主题中，如果尚未通过索引发现一个主题，或者 AI 技术没有找到足够证据来将主题建立为主题，则您可以创建一个新主题。

> [!Note] 
> 虽然 AI 收集的主题信息经过安全修整，[](topic-experiences-security-trimming.md)但请注意，手动创建的主题中的主题说明和人员信息对有权查看该主题的所有用户可见。 


## <a name="requirements"></a>要求

若要创建新主题，需要：
- 拥有 Viva 主题许可证。
- 对可以创建或 [**编辑主题的 Who 具有权限**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions)。 知识管理员可以在 Viva 主题权限设置中授予用户此权限。 

> [!Note] 
> 具有管理主题中心中主题的权限的用户 (，) 具有创建和编辑主题的权限。

## <a name="to-create-a-topic"></a>创建主题

可以从两个位置创建新主题：

- 主题中心主页：具有"谁可以创建或编辑主题"权限的任何授权用户 (参与者) 可以通过选择"新建"菜单并选择"主题"页，从主题中心<b>创建新</b><b>主题</b>。</br> 

    ![主题中心的新主题](../media/knowledge-management/new-topic.png) </br> 

- 管理主题页面：具有"谁可以管理主题"权限的任何授权用户 (知识经理) 可以通过选择"新建主题"页从主题中心的"管理主题"页<b>创建新主题</b>。</br> 

    ![管理主题中的新主题](../media/knowledge-management/new-topic-topic-center.png) </br> 

### <a name="to-create-a-new-topic"></a>若要创建新主题，请：

1. 在 **"命名本主题"部分** ，键入新主题的名称。

    ![命名本主题](../media/knowledge-management/k-new-topic-page.png) </br> 


2. 在 <b>"备用</b> 名称"部分，键入本主题可能引用的其他任何名称。 

    ![备用名称](../media/knowledge-management/alt-names.png) </br> 
3. 在 <b>"说明</b> "部分，键入几个描述主题的句子。 

    ![主题说明](../media/knowledge-management/description.png)</br>

4. 在 <b>"固定人员</b> "部分，你可以"固定"人员，以将其作为主题专家显示。 首先在添加新用户框中键入其姓名或电子邮件地址，<b></b>然后从搜索结果中选择要添加的用户。 您还可以通过选择用户卡片上的"从列表中删除"<b></b>图标来"取消固定"它们。 还可以拖动人员以更改人员列表的显示顺序。
 
    ![固定人员](../media/knowledge-management/pinned-people.png)</br>


5. 在 <b>"固定的文件和页面</b> "部分，可以添加或"固定"与主题关联的文件或 SharePoint 网站页。

   ![固定的文件和页面](../media/knowledge-management/pinned-files-and-pages.png)</br>
 
    若要添加新文件，请选择 <b>"</b>添加"，从"常用"或"关注的网站"中选择 SharePoint 网站，然后从网站的文档库中选择该文件。

    您还可以通过提供 URL<b></b>使用"从链接"选项添加文件或页面。 

    > [!Note] 
    > 添加的文件和页面必须位于同一 Microsoft 365 租户中。 如果要在主题中添加指向外部资源的链接，可以通过步骤 8 中的画布图标添加该链接。


6.  " <b>相关网站</b> "部分显示包含有关主题的信息的网站。 

    !["相关网站"部分](../media/knowledge-management/related-sites.png)</br>

    您可以通过选择"添加"，然后搜索<b></b>该网站，或者从"常用"或"最近访问"站点列表中选择它来添加相关网站。</br>
    
    ![选择网站](../media/knowledge-management/sites.png)</br>

7. " <b>相关主题</b> "部分显示主题之间的连接。 可以通过选择"连接到相关主题"按钮，然后键入相关<b></b>主题的名称，然后从搜索结果中选择它，来添加到其他主题的连接。 

   ![相关主题](../media/knowledge-management/related-topic.png)</br>  

    然后，你可以提供主题相关说明，然后选择"更新<b>"。</b></br>

   ![相关主题说明](../media/knowledge-management/related-topics-update.png)</br> 

   添加的相关主题将显示为已连接的主题。

   ![已连接的相关主题](../media/knowledge-management/related-topics-final.png)</br> 

   若要删除相关主题，请选择要删除的主题，然后选择" <b>删除主题"</b> 图标。</br>
 
   ![删除相关主题](../media/knowledge-management/remove-related.png)</br>  

   然后选择"<b>删除"。</b></br>

   ![确认删除](../media/knowledge-management/remove-related-confirm.png)</br> 
     
 


8. 您还可以通过选择画布图标（可在简短说明 (找到的画布图标）将静态项目添加到页面) ，如文本、图像或链接。 选择它将打开 SharePoint 工具箱，您可以从中选择要添加到页面的项目。

   ![画布图标](../media/knowledge-management/webpart-library.png)</br> 


9. 选择 **"发布** "保存更改。 

发布页面后，主题名称、备用名称、说明和固定人员将显示给查看主题的所有许可用户。 只有查看者对项目具有 Office 365 权限时，特定文件、页面和网站才将显示在主题页面上。 



## <a name="see-also"></a>另请参阅



  






