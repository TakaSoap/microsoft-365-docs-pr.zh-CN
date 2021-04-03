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
ms.service: o365-administration
localization_priority: Normal
description: 作为全局管理员，你最多可以将三个应用固定到用户的应用启动器。
ms.openlocfilehash: 786368f1236c7a86a6fbd0dd863ad0296cb65fac
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579262"
---
# <a name="pin-apps-to-your-users-app-launcher"></a><span data-ttu-id="822c9-103">将应用固定到用户的应用启动器</span><span class="sxs-lookup"><span data-stu-id="822c9-103">Pin apps to your users' app launcher</span></span>

<span data-ttu-id="822c9-104">可以使用 Azure Active Directory 门户中的控件将最多三个应用固定到 Office.com 组织中所有用户的应用启动器。</span><span class="sxs-lookup"><span data-stu-id="822c9-104">You can use controls in the Azure Active Directory portal to pin up to three apps to Office.com and the app launcher for all the users in your organization.</span></span> <span data-ttu-id="822c9-105">还可以组织应用程序组。</span><span class="sxs-lookup"><span data-stu-id="822c9-105">You can also organize groups of applications.</span></span> <span data-ttu-id="822c9-106">你添加的任何应用稍后都可以由用户随时取消固定。</span><span class="sxs-lookup"><span data-stu-id="822c9-106">Any app you add can later be unpinned by the user at any time.</span></span> <span data-ttu-id="822c9-107">若要为用户固定应用，你必须是云应用程序管理员、Azure Active Directory 中的应用程序管理员或 Office 365 中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="822c9-107">To pin an app for your users, you must be a Cloud application administrator, or Application administrator in Azure Active Directory, or a Global administrator in Office 365.</span></span> <span data-ttu-id="822c9-108">有关管理员角色详细信息，请参阅 [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 中的管理员角色和 [Microsoft 365](../add-users/about-admin-roles.md)中的管理员角色。</span><span class="sxs-lookup"><span data-stu-id="822c9-108">For more information about admin roles, see [admin roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [admin roles in Microsoft 365](../add-users/about-admin-roles.md).</span></span> 

<span data-ttu-id="822c9-109">有关应用启动器和应用启动器 Office.com，请参阅了解应用启动[](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)器和 office.com 和[Office 365](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503)应用启动器博客文章。</span><span class="sxs-lookup"><span data-stu-id="822c9-109">For more information about the app launcher and Office.com, see [meet the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and [updates to office.com and the-Office 365 app launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blog article.</span></span>

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a><span data-ttu-id="822c9-110">使用 Azure Active Directory 门户固定应用</span><span class="sxs-lookup"><span data-stu-id="822c9-110">Use the Azure Active Directory portal to pin apps</span></span>

1. <span data-ttu-id="822c9-111">转到 Microsoft 365 管理中心，位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="822c9-111">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="822c9-112">在左侧导航中，选择"**全部显示**"，在"管理 **中心**"下，选择 **"Azure Active Directory"。**</span><span class="sxs-lookup"><span data-stu-id="822c9-112">In the left nav, choose **Show all**, and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="822c9-113">在 **Azure Active Directory 中**，选择 **"企业应用程序**  >  **""用户设置"。**</span><span class="sxs-lookup"><span data-stu-id="822c9-113">In **Azure Active Directory**, choose **Enterprise applications** > **User settings**.</span></span>
4. <span data-ttu-id="822c9-114">在 **"Office 365 设置"** 部分，选择"**添加应用程序"。**</span><span class="sxs-lookup"><span data-stu-id="822c9-114">In the **Office 365 Settings** section, choose **Add application**.</span></span>
5. <span data-ttu-id="822c9-115">选择要固定到用户的应用启动器的应用程序，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="822c9-115">Choose the applications you want to pin to the users' app launcher, and then choose **Add**.</span></span>

:::image type="content" source="../../media/add-apps.png" alt-text="用于固定应用的 Microsoft 365 设置。":::

### <a name="pin-a-custom-app"></a><span data-ttu-id="822c9-117">固定自定义应用</span><span class="sxs-lookup"><span data-stu-id="822c9-117">Pin a custom app</span></span>

> [!NOTE]
> <span data-ttu-id="822c9-118">用户界面将指示是否需要购买其他 Azure AD 许可证以使用此功能。</span><span class="sxs-lookup"><span data-stu-id="822c9-118">The user interface will indicate if you need need to purchase additional Azure AD licenses to use this feature.</span></span> <span data-ttu-id="822c9-119">有关详细信息，请参阅 [Azure Active Directory 定价](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="822c9-119">For more information see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

1. <span data-ttu-id="822c9-120">在 **Azure Active Directory 中**，选择"所有应用程序"页面顶部的  >  "企业应用程序""**新建应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="822c9-120">In **Azure Active Directory**, choose **Enterprise applications** > **New application** on the top of the **All applications** page.</span></span>
2. <span data-ttu-id="822c9-121">在"**添加应用程序"页上**，选择"非库应用程序"或"创建你自己的应用程序"（如果你位于 Azure Active Directory 的预览版中）。</span><span class="sxs-lookup"><span data-stu-id="822c9-121">On the **Add an application** page, choose **Non-gallery application** or **Create your own application** if you are in the preview version of Azure Active Directory.</span></span> 
3. <span data-ttu-id="822c9-122">键入应用程序的名称，然后在"用户和组"选项卡 **中分配** 用户。</span><span class="sxs-lookup"><span data-stu-id="822c9-122">Type a name for the application and then assign user in the **Users and groups** tab.</span></span>
4. <span data-ttu-id="822c9-123">使用" **属性** "选项卡上传应用的图标。</span><span class="sxs-lookup"><span data-stu-id="822c9-123">Use the **Properties** tab to upload an icon for the app.</span></span>
5. <span data-ttu-id="822c9-124">若要向应用分配 URL，请在"单一登录 **"选项卡中选择** "链接 **"，然后** 输入 URL。</span><span class="sxs-lookup"><span data-stu-id="822c9-124">To assign a URL to the app, in the **Single sign-on** tab, choose **Linked** and then enter a URL.</span></span>
6. <span data-ttu-id="822c9-125">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="822c9-125">Choose **Save**.</span></span>

## <a name="create-application-collections"></a><span data-ttu-id="822c9-126">创建应用程序集合</span><span class="sxs-lookup"><span data-stu-id="822c9-126">Create application collections</span></span>

<span data-ttu-id="822c9-127">您还可以为组织的用户创建应用程序集合。</span><span class="sxs-lookup"><span data-stu-id="822c9-127">You can also create application collections for the users in your organization.</span></span> <span data-ttu-id="822c9-128">有关说明，请参阅 [在 Azure 门户的"我的应用"门户上创建集合](/azure/active-directory/manage-apps/access-panel-collections)。</span><span class="sxs-lookup"><span data-stu-id="822c9-128">For instructions, see [create collections on the My Apps portal in the Azure portal](/azure/active-directory/manage-apps/access-panel-collections).</span></span>