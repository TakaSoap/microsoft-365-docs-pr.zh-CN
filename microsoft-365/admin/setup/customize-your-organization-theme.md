---
title: 自定义组织的主题
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8275da91-7a48-4591-94ab-3123a3f79530
description: 了解如何在Microsoft 365中更改导航栏顶部的默认主题，并自定义它以匹配公司徽标或颜色。
ms.openlocfilehash: 263f6e91fb995daa61fe220a94b6948c6f782400
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783042"
---
# <a name="customize-the-microsoft-365-theme-for-your-organization"></a>为组织自定义Microsoft 365主题

作为组织的管理员，你可以为组织中的人员创建多个主题，并选择哪些主题适用于组织的不同成员。 组织主题是组织中人员的顶部导航栏中显示的内容。

可以添加或更新适用于组织内所有人的默认主题。还可以创建最多四个可分配给多个Microsoft 365组的附加组主题。
  
## <a name="add-or-update-your-organizations-theme"></a>添加或更新组织的主题

1. 在管理中心，转到 **设置** \> **组织设置** 页，然后选择 **“组织配置文件**”选项卡。

2. 在 **“组织配置文件** ”选项卡上，选择 **“自定义”主题**。

可以使用以下选项卡自定义所有组织主题。

|选项卡|What can you do?|
|---|---|
|[常规](#general-modify-a-theme)|修改主题名称，并分配最多五组 (（如果适用）) 。|
|[标志](#logos-specify-your-theme-logos)|添加组织徽标，包括深色主题的备用徽标。|
|[Colors](#colors-choose-theme-colors)|通过指定导航栏、主题、文本和图标颜色自定义配色方案。|

## <a name="general-modify-a-theme"></a>常规：修改主题

“常规”选项卡上的体验取决于是添加还是修改默认主题还是组主题。

### <a name="update-the-default-theme"></a>更新默认主题

默认主题是显示的第一个主题。  

1. 如果以前为组织自定义主题，请选择 **“默认主题** ”并使用保存的自定义项之一，或者选择 **“添加主题**”。
2. 在 **“常规** ”页上，可以阻止用户重写其主题并显示用户的显示名称。
3. 选择“**保存**”以保存所做的更改。  

> [!IMPORTANT]
> 默认主题是唯一的，无法重命名它，并且适用于组织中的所有人。 若要删除默认主题，必须先删除所有其他主题。

:::image type="content" source="../../media/Default_Theme_Panel1.png" alt-text="屏幕截图：显示组织的默认主题的“常规”选项卡":::

### <a name="create-a-group-theme"></a>创建组主题

最多可以创建四个其他组主题。

1. 在 **“常规** ”页上，输入新主题的名称。

2. 在 **“组**”下，最多可以选择 5 个可查看组主题的Microsoft 365 组，而不是使用默认主题。 还可以阻止用户重写其主题并显示用户的显示名称。

3. 选择“**保存**”。

:::image type="content" source="../../media/default-theme-general-users1.png" alt-text="屏幕截图：显示组织中一组用户的默认主题的“常规”选项卡":::

## <a name="logos-specify-your-theme-logos"></a>徽标：指定主题徽标

在 **“徽标”页上** ，可以添加徽标，并指定用户选择徽标时将导航到的 URL。

- **默认徽标**：添加指向徽标的 URL 位置。 确保 URL 使用 HTTPS。 添加允许匿名访问且不需要身份验证的 HTTPS 映像 URL。 对于默认主题，还可以选择上传小于 10kb 的徽标图像。 默认徽标可以采用 JPG、PNG、GIF 或 SVG 格式。 对于 SVG 映像，它们的大小将调整为垂直容纳 24 像素。 JPG、PNG、GIF 映像将缩放为适合 200 x 48 像素。 将始终保留徽标纵横比。
- **备用徽标**：添加指向徽标的 URL 位置。 备用徽标应经过优化，以便在深Office主题中使用。 与默认徽标的要求相同。
- **单击链接**：添加指向徽标的 URL 位置。 可以使用徽标作为指向任何公司资源（例如公司网站）的链接。 如果未为徽标选择 URL 位置，则默认为Office主页。

选择“**保存**”以保存所做的更改。

:::image type="content" source="../../media/Logos_Tab.png" alt-text="屏幕截图：显示徽标选项的“徽标”选项卡":::

可以随时删除徽标。 只需返回到 **“徽标”** 页，然后选择 **“删除**”。
  
## <a name="colors-choose-theme-colors"></a>颜色：选择主题颜色

在 **“颜色”** 页上，可以设置默认颜色，并选择应使用哪个徽标。

- **导航栏颜色**：选择要用于导航栏背景的颜色。 导航栏显示在每一页的顶部。
- **文本和图标颜色**：选择要用于顶部导航栏上的文本和图标的颜色。
- **着色**：选取一个在白色或浅色背景上显示良好的颜色。 强调色用于着色显示在白色或浅色背景上的某些链接和按钮。 例如，重音颜色用于在用户的收件箱及其Office.com 门户页上为元素着色。
- **重置颜色**：选择此链接以将颜色重置为默认颜色。

:::image type="content" source="../../media/default-theme-colors1.png" alt-text="屏幕截图：显示组织默认主题颜色的“颜色”选项卡":::

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="my-organization-already-has-a-theme-for-all-employees-how-will-this-change"></a>我的组织已经为所有员工提供了一个主题。 此操作将如何更改？

默认主题将继续显示给所有员工。 添加新的组主题将仅提供给与该主题关联的Microsoft 365组。

### <a name="why-dont-i-see-group-themes-in-the-admin-center"></a>为什么在管理中心看不到组主题？

只有全局管理员才能自定义公司主题。 全局阅读器具有只读访问权限。

### <a name="how-many-different-themes-can-i-set-up-for-my-organization"></a>我可以为组织设置多少个不同的主题？  

最多可以创建五个主题。 默认主题和四个组主题。  

### <a name="can-i-use-security-groups-or-distribution-groups-instead-of-microsoft-365-groups"></a>是否可以使用安全组或通讯组而不是Microsoft 365 组？

否，新组主题必须映射到一个或多个Microsoft 365组，而不是安全组或通讯组。

> [!NOTE]
> 可以在Outlook中[将通讯组转换为Microsoft 365组](../manage/upgrade-distribution-lists.md)。

### <a name="can-i-manually-assign-a-theme-independent-of-microsoft-365-groups"></a>是否可以手动分配独立于Microsoft 365 组的主题？  

否，必须将新的组主题映射到一个或多个Microsoft 365组。 作为Microsoft 365组成员的用户将获得应用于其组的主题。 可以通过转到管理中心 [中的设置组，创建新成员并将其添加](../create-groups/create-groups.md)到 **Microsoft 365** > **组**。

### <a name="what-happens-if-a-user-is-assigned-to-multiple-group-themes"></a>如果将用户分配到多个组主题，会发生什么情况？  

分配到多个组主题的用户将显示默认主题。  

### <a name="why-cant-i-delete-the-default-theme"></a>为什么无法删除默认主题？  

默认主题只能在删除所有组主题后删除。 在尝试删除组主题之前，请确保删除所有组主题。

### <a name="why-am-i-receiving-an-error-message-every-time-i-upload-a-logo-url"></a>为什么每次上传徽标 URL 时都会收到错误消息。  

确保所使用的徽标指定为可公开寻址的 URL。 请按照以下步骤将[徽标上传到Azure Blob 存储](/azure/storage/blobs/storage-upload-process-images?tabs=dotnet)或[使用 SharePoint Online Office 365 内容分发网络](../../enterprise/use-microsoft-365-cdn-with-spo.md)。

### <a name="why-am-i-receiving-the-message-doesnt-meet-minimum-color-contrast-ratio-of-451"></a>为什么收到消息“不符合 4.5：1 的最低颜色对比度”？

文本、图标或按钮颜色和背景色之间的建议对比度为 4.5：1。 可以重写此建议，并仍保存主题，因为这不是一项要求。

### <a name="if-i-define-a-theme-which-places-in-microsoft-365-will-this-be-used"></a>如果我定义一个主题，Microsoft 365将使用哪个位置？

作为Microsoft 365套件标头的一部分，任何主题都显示在组织中每个人的顶部导航栏中。  
  
## <a name="related-content"></a>相关内容

[将自定义磁贴添加到“我的应用”页面和应用启动器](../manage/customize-the-app-launcher.md) (文章) \
管理员[Microsoft 365 组概述 (](../create-groups/office-365-groups.md)文章) 
