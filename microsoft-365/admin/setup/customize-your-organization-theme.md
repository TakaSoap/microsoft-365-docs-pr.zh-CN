---
title: 为组织自定义主题
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
description: 了解如何更改导航栏中导航栏顶部的默认主题Microsoft 365自定义它以匹配你的公司徽标或颜色。
ms.openlocfilehash: 307d322c441a2f56e43e02abb947c6c9ba8cff2d
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2022
ms.locfileid: "62171055"
---
# <a name="customize-the-microsoft-365-theme-for-your-organization"></a>自定义Microsoft 365主题

作为组织的管理员，你可以为组织成员创建多个主题，并选择哪些主题适用于组织的不同成员。 组织主题是显示在组织中人员的顶部导航栏中的主题。

可以添加或更新适用于组织内部所有人的默认主题。还可以创建最多四个其他组主题，这些主题可分配给多个Microsoft 365组。
  
## <a name="add-or-update-your-organizations-theme"></a>添加或更新组织的主题

1. 在管理中心中，转到"设置 \> **组织** 设置"页面，然后选择"组织 **配置文件"** 选项卡。

2. 在"**组织配置文件"** 选项卡上，选择"**自定义主题"。**

可以使用以下选项卡自定义所有组织主题。

|**Tab**|**What can you do?**|
|:-----|:-----|
|[常规](#general-modify-a-theme) <br/> |修改主题名称并分配最多五个组 (如果适用) 。  <br/> |
|[徽标](#logos-specify-your-theme-logos) <br/> |添加组织徽标，包括深色主题的备用徽标。  <br/> |
|[Colors](#colors-choose-theme-colors) <br/> |通过指定导航栏、强调文字和图标颜色自定义配色方案。 <br/> |

## <a name="general-modify-a-theme"></a>常规：修改主题

"常规"选项卡上的体验取决于是添加还是修改默认主题或组主题。

### <a name="update-the-default-theme"></a>更新默认主题

默认主题是显示的第一个主题。  

1. 如果以前为组织自定义了主题，请选择"默认主题"，然后使用保存的自定义项之一，或者选择"**添加主题"。**
2. 在 **"常规** "页上，可以阻止用户覆盖其主题，并显示用户显示名称。
3. 选择 **保存** 以保存所做的更改。  

> [!IMPORTANT]
> 默认主题是唯一的，不能重命名，并且适用于组织内部的每个人。 若要删除默认主题，您必须首先删除所有其他主题。

:::image type="content" source="../../media/Default_Theme_Panel1.png" alt-text="Screenshot： General tab showing the default theme for your organization":::

### <a name="create-a-group-theme"></a>创建组主题

你最多可以创建四个其他组主题。

1. 在 **"常规** "页面上，输入新主题的名称。

2. 在 **"** 组"下，Microsoft 365查看你的组主题的最多 5 个组，而不是使用默认主题。 还可以阻止用户覆盖其主题和显示用户显示名称。

3. 选择“**保存**”。

:::image type="content" source="../../media/default-theme-general-users1.png" alt-text="Screenshot： General tab showing the default theme for a group of users in your organization":::

## <a name="logos-specify-your-theme-logos"></a>徽标：指定主题徽标

在 **"徽标"** 页上，您可以添加徽标，并指定用户在选择徽标时将导航到的 URL。

- **默认徽标**：添加指向徽标的 URL 位置。 确保 URL 使用 HTTPS。 添加允许匿名访问且不需要身份验证的 HTTPS 图像 URL。 对于默认主题，还可以选择上传小于 10kb 的徽标图像。 默认徽标可以是 JPG、PNG、GIF 或 SVG 格式。 对于 SVG 图像，它们的大小将调整为垂直调整为 24 像素。 JPG、PNG、GIF 图像将缩放为 200 x 48 像素。 徽标纵横比将始终保留。
- **备用徽标**：添加指向徽标的 URL 位置。 应优化备用徽标，以用于Office主题。 与默认徽标的要求相同。
- **单击链接**：添加指向徽标的 URL 位置。 可以将徽标用作指向任何公司资源（例如，贵公司的网站）的链接。 如果未选择徽标的 URL 位置，它将默认为 Office主页。

选择 **保存** 以保存所做的更改。

:::image type="content" source="../../media/Logos_Tab.png" alt-text="Screenshot： Logos tab showing the logo options":::

你随时都可以删除徽标。 只需返回到"**徽标"页** 并选择"删除 **"。**
  
## <a name="colors-choose-theme-colors"></a>颜色：选择主题颜色

在 **"颜色** "页上，可以设置默认颜色并选择应该使用的徽标。

- **导航栏颜色**：选择要用于导航栏背景的颜色。 导航栏显示在每页的顶部。
- **文本和图标颜色**：选择要用于顶部导航栏上的文本和图标的颜色。
- **主题色**：选择一个在白色或浅色背景上显示良好的颜色。 主题色用于为在白色或浅色背景上显示的链接和按钮设置颜色。 例如，主题色用于为用户收件箱及其 Office.com 门户页面上的元素设置颜色。
- **重置颜色**：选择此链接以将颜色重置为默认颜色。

:::image type="content" source="../../media/default-theme-colors1.png" alt-text="Screenshot： Colors tab showing default theme colors for your organization":::

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="my-organization-already-has-a-theme-for-all-employees-how-will-this-change"></a>我的组织已有一个针对所有员工的主题。 这将如何更改？

默认主题将继续向所有员工显示。添加新的组主题将仅对与该主题Microsoft 365组可用。

### <a name="whydont-isee-group-themes-in-the-admin-center"></a>为什么我在管理中心看不到组主题？

只有全局管理员可以自定义公司主题。全局读者具有只读访问权限。

### <a name="how-many-different-themes-can-i-set-up-for-my-organization"></a>我可以为组织设置多少个不同的主题？  

最多可创建五个主题。 默认主题和四个组主题。  

### <a name="can-i-use-security-groups-or-distribution-groups-instead-of-microsoft-365-groups"></a>能否使用安全组或通讯组，而不是Microsoft 365组？

否，必须将新组主题映射到一个或多个Microsoft 365组，而不是安全组或通讯组。

> [!NOTE]
> 可以将通讯[组转换为Microsoft 365组Outlook。](../manage/upgrade-distribution-lists.md)

### <a name="can-imanually-assign-a-theme-independent-ofmicrosoft-365-groups"></a>能否手动分配独立于组Microsoft 365主题？  

否，必须将新组主题映射到一个或多个Microsoft 365组。 作为组Microsoft 365用户将获取应用于其组的主题。 可以通过[在管理中心](../create-groups/create-groups.md)中Microsoft 365组 ****   >  **"设置"组"，** 将新成员添加到组。

### <a name="what-happens-if-a-user-is-assigned-to-multiple-group-themes"></a>如果将用户分配给多个组主题，会发生什么情况？  

分配给多个组主题的用户将显示默认主题。  

### <a name="why-cant-i-delete-the-default-theme"></a>为什么无法删除默认主题？  

只有在删除所有组主题后，才能删除默认主题。 在尝试删除组主题之前，请确保删除所有组主题。

### <a name="why-am-i-receiving-an-error-message-every-time-i-uploadalogo-url"></a>为什么我每次上载徽标 URL 时都会收到错误消息。  

请确保你使用的徽标指定为可公开地址 URL。 请按照以下步骤将徽标上传到[Azure Blob](/azure/storage/blobs/storage-upload-process-images?tabs=dotnet)存储或 Office 365 内容分发网络 Online [SharePoint应用](../../enterprise/use-microsoft-365-cdn-with-spo.md)。

### <a name="why-am-i-receiving-themessagedoesnt-meet-minimum-color-contrast-ratio-of-451"></a>为什么我收到消息"不满足最小颜色对比率 4.5：1"？

文本、图标或按钮颜色与背景色之间的建议对比率为 4.5：1。 你可以替代此建议，但仍保存主题，因为这不是一项要求。

### <a name="if-i-define-a-theme-which-places-in-microsoft-365-will-this-be-used"></a>如果定义了主题，将在Microsoft 365哪个位置？

任何主题都作为套件标题的一部分显示在组织的顶部导航Microsoft 365中。  
  
## <a name="related-content"></a>相关内容

[向"我的应用"页面和应用启动器](../manage/customize-the-app-launcher.md) 添加自定义磁贴 (文章) \
[管理员Microsoft 365组概述 (](../create-groups/office-365-groups.md)文章) 
