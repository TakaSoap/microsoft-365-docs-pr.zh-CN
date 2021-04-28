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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8275da91-7a48-4591-94ab-3123a3f79530
description: '了解如何更改 Microsoft 365 的默认主题并对其进行自定义以匹配你的公司徽标或颜色。 '
ms.openlocfilehash: b7a0b142b8bd465a9e3258aaaeb951b72bc53fc7
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52060898"
---
# <a name="customize-the-microsoft-365-theme-for-your-organization"></a>为组织自定义 Microsoft 365 主题

作为组织的管理员，你可以为组织成员创建多个主题，并选择哪些主题适用于组织的不同成员。 组织主题是显示在组织中人员的顶部导航栏中的主题。

可以添加或更新适用于组织内部所有人的默认主题。还可以创建最多四个可分配给多个 Microsoft 365 组的附加组主题。
  
## <a name="add-or-update-your-organizations-theme"></a>添加或更新组织的主题

1. 在管理中心，转到"设置 \> **""组织设置"** 页，然后选择"**组织配置文件"** 选项卡。

2. 在"**组织配置文件"** 选项卡上，选择"**组织主题"。**

可以使用以下选项卡自定义所有主题。

|**Tab**|**What can you do?**|
|:-----|:-----|
|[常规](#general-modify-a-theme) <br/> |修改主题名称，并分配最多五个组 (（如果适用) ）。  <br/> |
|[徽标](#logos-specify-your-theme-logos) <br/> |添加主题徽标，包括 Office 深色主题和移动选项。  <br/> |
|[Colors](#colors-choose-theme-colors) <br/> |通过指定导航栏、强调文字、文本和图标颜色自定义配色方案。 <br/> |

## <a name="general-modify-a-theme"></a>常规：修改主题

"常规"选项卡上的体验取决于是添加还是修改默认主题或组主题。

### <a name="update-the-default-theme"></a>更新默认主题

默认主题是显示的第一个主题。  

1. 如果以前为组织自定义了主题，请选择"默认主题"并使用保存的自定义项之一，或者选择"**添加主题"。**
2. 在 **"常规** "页上，可以阻止用户覆盖其主题，并显示用户显示名称。
3. 选择 **保存** 以保存所做的更改。  

> [!IMPORTANT]
> 默认主题是唯一的，不能重命名，并且适用于组织内部的每个人。 若要删除默认主题，您必须首先删除所有其他主题。

:::image type="content" source="../../media/default-theme-general.png" alt-text="Screenshot： General tab showing the default theme for your organization":::

### <a name="create-a-group-theme"></a>创建组主题

你最多可以创建四个其他组主题。

1. 在 **"常规** "页上，输入主题的名称。

2. 在 **"** 组"下，可以选择最多 5 个可以看到组主题的 Microsoft 365 组，而不是使用默认主题。 您还可以阻止用户覆盖其主题和显示用户显示名称。

3. 选择 **保存**。

:::image type="content" source="../../media/default-theme-general-users.png" alt-text="Screenshot： General tab showing the default theme for a group of users in your organization":::

## <a name="logos-specify-your-theme-logos"></a>徽标：指定主题徽标

在 **"徽标"** 页上，您可以添加徽标，并指定用户在选择徽标时将导航到的 URL。

- **默认徽标**：添加指向徽标的 URL 位置。 请确保 URL 使用 HTTPS，并且图像至少为 200 x 30 像素。 默认徽标可以是 JPG、PNG、GIF 或 SVG 格式。
- **备用徽标**：添加指向徽标的 URL 位置。 应优化备用徽标，以用于 Office 深色主题。 与默认徽标的要求相同。
- **小型默认徽标**：添加指向徽标的 URL 位置。 图像必须至少为 48 x 48 像素。 你可以缩放此图像，以便它适合较小的或移动设备上。
- **小型备用徽标**：添加指向徽标的 URL 位置。 此图像具有与小型默认徽标相同的要求。
- **单击链接**：添加指向徽标的 URL 位置。 可以将徽标用作指向任何公司资源（例如，贵公司的网站）的链接。

选择 **保存** 以保存所做的更改。

你随时都可以删除徽标。 只需返回到"**徽标"页** 并选择"删除 **"。**

:::image type="content" source="../../media/default-theme-logos.png" alt-text="Screenshot： Logos tab showing default theme logo for your organization":::

> [!NOTE]
> 默认情况下，我们首先显示大多数组织使用的徽标选择。 To see all the logo selections， go to the bottom of the list and select **See advanced options**.
  
## <a name="colors-choose-theme-colors"></a>颜色：选择主题颜色

在 **"颜色** "页上，可以设置默认颜色并选择应该使用的徽标。

- **导航栏颜色**：选择要用于导航栏背景的颜色。 导航栏显示在每页的顶部。
- **文本和图标颜色**：选择要用于顶部导航栏上的文本和图标的颜色。
- **主题色**：选择一个在白色或浅色背景上显示良好的颜色。 主题色用于为在白色或浅色背景上显示的链接和按钮设置颜色。 例如，主题色用于为用户收件箱和用户收件箱中的 Office.com 颜色。
- **重置颜色**：选择此链接将颜色重置为默认颜色。
- **应该使用哪种徽标？：** 选择默认徽标或您自己创建的其他徽标。

:::image type="content" source="../../media/default-theme-colors.png" alt-text="Screenshot： Colors tab showing default theme colors for your organization":::

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="my-organization-already-has-a-theme-for-all-employees-how-will-this-change"></a>我的组织已有一个针对所有员工的主题。 这将如何更改？

默认主题将继续向所有员工显示。添加新的组主题将仅适用于与该主题关联的 Microsoft 365 组。

### <a name="whydont-isee-group-themes-in-the-admin-center"></a>为什么我在管理中心看不到组主题？

只有全局管理员可以自定义公司主题。全局读者具有只读访问权限。

### <a name="how-many-different-themes-can-i-set-up-for-my-organization"></a>我可以为组织设置多少个不同的主题？  

最多可创建五个主题。 默认主题和四个组主题。  

### <a name="can-i-use-security-groups-or-distribution-groups-instead-of-microsoft-365-groups"></a>能否使用安全组或通讯组而不是 Microsoft 365 组？

否，必须将新组主题映射到一个或多个 Microsoft 365 组，而不是安全组或通讯组。

> [!NOTE]
> 可以在 Outlook [中将通讯组转换为 Microsoft 365](../manage/upgrade-distribution-lists.md) 组。

### <a name="can-imanually-assign-a-theme-independent-ofmicrosoft-365-groups"></a>能否手动分配独立于 Microsoft 365 组的主题？  

否，新的组主题必须映射到一个或多个 Microsoft 365 组。 作为 Microsoft 365 组的成员的用户将获取应用于其组的主题。 可以通过访问管理中心中的"设置组"，创建新成员并将其添加到[Microsoft 365](../create-groups/create-groups.md)  ****   >  **** 组。

### <a name="what-happens-if-a-user-is-assigned-to-multiple-group-themes"></a>如果将用户分配给多个组主题，会发生什么情况？  

分配给多个组主题的用户将显示默认主题。  

### <a name="why-cant-i-delete-the-default-theme"></a>为什么无法删除默认主题？  

只有在删除所有组主题后，才能删除默认主题。 在尝试删除组主题之前，请确保删除所有组主题。

### <a name="why-am-i-receiving-an-error-message-every-time-i-uploadalogo-url"></a>为什么我每次上载徽标 URL 时都会收到错误消息。  

请确保你使用的徽标指定为可公开地址 URL。 请按照以下步骤将徽标 [上载](/azure/storage/blobs/storage-upload-process-images?tabs=dotnet) 到 Azure Blob 存储或具有 SharePoint Online 的 [Office 365 内容交付网络](../../enterprise/use-microsoft-365-cdn-with-spo.md)。

### <a name="why-am-i-receiving-themessagedoesnt-meet-minimum-color-contrast-ratio-of-451"></a>为什么我收到消息"不满足最小颜色对比率 4.5：1"？

文本、图标或按钮颜色与背景色之间的建议对比率为 4.5：1。 你可以替代此建议，但仍保存主题，因为这不是一项要求。

### <a name="if-i-define-a-theme-which-places-in-microsoft-365-will-this-be-used"></a>如果我定义主题，将在 Microsoft 365 中的哪些位置使用该主题？

任何主题都将作为 Microsoft 365 套件标头的一部分显示在组织中每个人的顶部导航栏中。  
  
## <a name="related-articles"></a>相关文章

[向"我的应用"页面和应用启动器添加自定义磁贴](../manage/customize-the-app-launcher.md)

[面向管理员的 Microsoft 365 组概述](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups)