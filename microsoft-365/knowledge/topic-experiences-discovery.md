---
title: '管理您的知识管理网络 (预览)  '
description: 如何设置知识管理。
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 265816a8d3d04b8d10b529f1ea1a0b658aa2931d
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988921"
---
# <a name="manage-your-knowledge-management-network-preview"></a>管理您的知识管理网络 (预览) 

> [!Note] 
> 本文中的内容适用于 Project Cortex 私人预览。 [了解更多关于 Project Cortex的信息](https://aka.ms/projectcortex)。


在 [设置知识管理](set-up-topic-experiences.md)之后，在任何时间之后，管理员都可以通过 Microsoft 365 管理中心对您的配置设置进行调整。

例如，您可能需要调整以下任一项的设置：
- 将新的 SharePoint 源代码添加到 "我的应用" 主题。
- 更改哪些用户将有权访问主题。
- 更改哪些用户具有在主题中心执行任务的权限。
- 更改你的主题中心的名称


## <a name="requirements"></a>Requirements 
您必须具有全局管理员或 SharePoint 管理员权限才能访问 Microsoft 365 管理中心并管理组织知识任务。


## <a name="to-access-knowledge-management-settings"></a>若要访问知识管理设置，请执行以下操作：

1. 在 Microsoft 365 管理中心，选择 " **设置** "，然后查看 " **组织知识库** " 部分。
2. 在 " **组织知识** " 部分，单击 " **将人员连接到知识** "。<br/>

    ![将用户连接到知识](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. 在 " **将用户连接到知识** " 页上，选择 " **管理** " 以打开 " **知识网络设置** " 窗格。<br/>

    ![知识网络-设置](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a>更改知识网络查找主题的方式

如果要为 SharePoint 主题源更新您的选择，请选择 " **主题发现** " 选项卡。 通过此设置，可以选择租户中将对主题进行爬网和挖掘的 SharePoint 网站。

1. 在 " **主题发现** " 选项卡上的 " **选择 SharePoint 主题源** " 下，选择 " **编辑** "。
2. 在 " **选择 SharePoint 主题源** " 页上，选择要在发现过程中将哪些 SharePoint 网站作为主题的源进行爬网。 这包括：</br>
    a. **所有网站** ：租户中的所有 SharePoint 网站。 这将捕获当前和未来的网站。</br>
    b. **所有（选定网站除外）** ：键入要排除的网站的名称。  您还可以上载要从发现中退出的网站列表。 将来创建的网站将作为主题发现的源包括在内。 </br>
    c. **仅选定网站** ：键入要包含的网站的名称。 您还可以上载网站列表。 将来创建的网站不会作为主题发现的源包括在内。 </br>

    ![选择如何查找主题](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    如果您有大量要排除的网站 (如果选择 **"全部" （选择的网站除外** ) 或包含 (）（如果只选择 **了 "选定网站** ) "，则可以选择使用网站名称和 url 上传 CSV 文件。 如果要使用 CSV 模板文件，则可以选择 " **下载网站模板 .csv"。**

3. 选择“保存”。

##  <a name="change-who-can-see-topics-in-your-organization"></a>更改可以查看组织中的主题的用户

如果要更新组织中的哪些用户可以在搜索结果中查看发现的主题以及在 SharePoint 页面等内容中突出显示主题，请选择 " **主题发现** " 选项卡。

1. 在 " **主题发现** " 选项卡上，在 " **谁可以查看知识网络中的主题** " 下，选择 " **编辑** "。
2. 在 " **知识库中可以查看主题** " 页中，选择谁将有权访问主题详细信息，如突出显示的主题、主题卡片、搜索中的主题答案和主题页面。 可以选择：</br>
    a. **组织中的所有人**</br>
    b. **仅选定的人员或安全组**</br>
    c. **没人**</br>

    ![谁可以查看主题](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. 选择“保存”。  
 
> [!Note] 
> 虽然此设置允许您选择组织中的任何用户，但只有分配有知识管理许可证的用户才能查看主题。

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a>更改有权在主题中心执行任务的谁

如果要在 "主题中心" 页中更新有权执行以下操作的用户，请选择 " **主题权限** " 选项卡：

- 哪些用户可以创建和编辑主题：创建在发现或编辑现有主题页面详细信息时找不到的新主题。
- 哪些用户可以管理主题：确认或拒绝已发现的主题。

若要更新有权创建和编辑主题的人士，请执行以下操作：

1. 在 " **主题权限** " 选项卡上，在 " **哪些人员可以创建和编辑主题** " 中，选择 " **编辑** "。</br>
2. 在 " **可以创建和编辑主题的用户** " 页上，您可以选择：</br>
    a. **组织中的所有人**</br>
    b. **仅选定的人员或安全组**</br>

    ![创建和编辑主题](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. 选择“保存”。</br>

若要更新谁有权管理主题，请执行以下操作：

1. 在 " **主题权限** " 选项卡上，在 " **谁可以管理主题** " 中，选择 " **编辑** "。</br>
2. 在 " **谁可以管理主题** " 页上，您可以选择：</br>
    a. **组织中的所有人**</br>
    b. **选定的人员或安全组**</br>

    ![管理主题](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. 选择“保存”。</br>


##  <a name="update-your-topic-center-name"></a>更新你的主题中心名称

如果要更新您的主题中心的名称，请选择 " **主题中心** " 选项卡。 

1. 在 " **主题中心** " 选项卡上的 " **主题中心名称** " 下，选择 " **编辑** "。
2. 在 " **编辑主题中心名称** " 页上的 " **主题居中名称** " 框中，键入您的主题中心的新名称。
3. 选择“ **保存** ”

    ![编辑主题中心名称](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a>另请参阅



  






