---
title: 将应用程序固定到用户的应用启动器
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: 作为全局管理员，你可以将三个应用程序固定到用户的应用启动器。
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310871"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>将应用程序固定到用户的应用启动器

您可以使用 Azure Active Directory 门户中的控件将三个应用程序固定到 Office.com，并将应用启动器用于组织中的所有用户。 您还可以组织应用程序组。 您添加的任何应用程序稍后都会被用户取消固定。 若要为您的用户固定应用程序，您必须是云应用程序管理员或 Azure Active Directory 中的应用程序管理员或 Office 365 中的全局管理员。 有关管理员角色的详细信息，请参阅[Microsoft 365](../add-users/about-admin-roles.md)中的 Azure Active Directory 和管理员角色[中的管理员角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。 

有关应用启动器和 Office.com 的详细信息，请参阅 [app 启动器](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) 和 [updates to office.com And the-Office 365 app 启动器](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) 博客文章。

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>使用 Azure Active Directory 门户来固定应用程序

1. 转到 Microsoft 365 管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。
2. 在左侧导航中，选择 " **全部显示**"，然后在 " **管理中心**" 下选择 " **Azure Active Directory**"。
3. 在 " **Azure Active Directory**" 中，选择 "**企业应用程序**"  >  **用户设置**。
4. 在 " **Office 365 设置** " 部分，选择 " **添加应用程序**"。
5. 选择要固定到用户的应用启动器的应用程序，然后选择 " **添加**"。

:::image type="content" source="../../media/add-apps.png" alt-text="用于固定应用程序的 Microsoft 365 设置。":::

### <a name="pin-a-custom-app"></a>固定自定义应用程序

> [!NOTE]
> 用户界面将指示是否需要购买其他 Azure AD 许可证才能使用此功能。 有关详细信息，请参阅 [Azure Active Directory 定价](https://azure.microsoft.com/pricing/details/active-directory/)。

1. 在 " **Azure Active Directory**" 中，选择 "所有应用程序" 页顶部的 "**企业应用程序**  >  **新应用程序**"。 **All applications**
2. 如果位于 Azure Active Directory 的预览版本中，请在 " **添加应用程序** " 页上，选择 " **非库应用程序** " 或 " **创建您自己的应用程序** "。 
3. 键入应用程序的名称，然后在 " **用户和组** " 选项卡中分配用户。
4. 使用 " **属性** " 选项卡上传应用程序的图标。
5. 若要为应用程序分配 URL，请在 " **单一登录** " 选项卡中选择 " **链接** "，然后输入 URL。
6. 选择“**保存**”。

## <a name="create-application-collections"></a>创建应用程序集合

您还可以为组织中的用户创建应用程序集合。 有关说明，请参阅 [Azure 门户中的我的应用门户上的创建集合](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections)。