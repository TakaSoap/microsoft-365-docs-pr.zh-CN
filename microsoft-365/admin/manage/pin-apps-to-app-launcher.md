---
title: 将应用固定到用户的应用启动器
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
- Adm_TOC
ms.service: o365-administration
ms.custom: admindeeplinkMAC
ms.localizationpriority: medium
description: 作为全局管理员，你最多可以将三个应用固定到用户的应用启动器。
ms.openlocfilehash: 7ff85e379198312666f03c2d7d6c8bb42b9e08d0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60171839"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>将应用固定到用户的应用启动器

可以使用 Azure Active Directory 门户中的控件将最多三个应用固定到 Office.com，以及组织中所有用户的应用启动器。 还可以组织应用程序组。 你添加的任何应用稍后都可以由用户随时取消固定。 若要为用户固定应用，你必须是云应用程序管理员、Azure Active Directory应用程序管理员或 Office 365。 有关管理员角色详细信息，请参阅[Azure AD 内置角色](/azure/active-directory/roles/permissions-reference)和 Microsoft 365 中的[管理员角色](../add-users/about-admin-roles.md)。 

有关应用启动器和 Office.com，请参阅了解应用启动器和[](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)office.com 更新和 Office 365[应用](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503)启动器博客文章。

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>使用 Azure Active Directory门户固定应用

1. 转到 上 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> Microsoft 365 管理中心。
2. 在左侧导航中，选择"**全部显示**"，**在"管理** 中心"下，选择"Azure Active Directory"。 
3. In **Azure Active Directory，** choose **Enterprise applications** User  >  **settings**.
4. 在 **"Office 365 设置"** 部分，选择"**添加应用程序"。**
5. 选择要固定到用户的应用启动器的应用程序，然后选择"添加 **"。**

:::image type="content" source="../../media/add-apps.png" alt-text="Microsoft 365设置固定应用。":::

### <a name="pin-a-custom-app"></a>固定自定义应用

> [!NOTE]
> 用户界面将指示是否需要购买其他 Azure AD 许可证以使用此功能。 有关详细信息，请参阅Azure Active Directory[定价](https://azure.microsoft.com/pricing/details/active-directory/)。

1. In **Azure Active Directory，** choose **Enterprise applications**  >  **New application** on the top of the All **applications** page.
2. 在"**添加应用程序"页上**，选择"非库应用程序"或"创建您自己的应用程序"（如果位于 Azure Active Directory 预览版中）。 
3. 键入应用程序的名称，然后在"用户和组"选项卡 **中分配** 用户。
4. 使用" **属性** "选项卡上载应用的图标。
5. 若要向应用分配 URL，请在"单一登录 **"选项卡中选择** "链接 **"，然后** 输入 URL。
6. 选择“保存”。

## <a name="create-application-collections"></a>创建应用程序集合

您还可以为组织的用户创建应用程序集合。 有关说明，请参阅 [在 Azure 门户的"我的应用"门户上创建集合](/azure/active-directory/manage-apps/access-panel-collections)。