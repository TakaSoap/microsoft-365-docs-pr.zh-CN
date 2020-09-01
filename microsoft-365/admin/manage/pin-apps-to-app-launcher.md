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
# <a name="pin-apps-to-your-users-app-launcher"></a><span data-ttu-id="8d519-103">将应用程序固定到用户的应用启动器</span><span class="sxs-lookup"><span data-stu-id="8d519-103">Pin apps to your users' app launcher</span></span>

<span data-ttu-id="8d519-104">您可以使用 Azure Active Directory 门户中的控件将三个应用程序固定到 Office.com，并将应用启动器用于组织中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="8d519-104">You can use controls in the Azure Active Directory portal to pin up to three apps to Office.com and the app launcher for all the users in your organization.</span></span> <span data-ttu-id="8d519-105">您还可以组织应用程序组。</span><span class="sxs-lookup"><span data-stu-id="8d519-105">You can also organize groups of applications.</span></span> <span data-ttu-id="8d519-106">您添加的任何应用程序稍后都会被用户取消固定。</span><span class="sxs-lookup"><span data-stu-id="8d519-106">Any app you add can later be unpinned by the user at any time.</span></span> <span data-ttu-id="8d519-107">若要为您的用户固定应用程序，您必须是云应用程序管理员或 Azure Active Directory 中的应用程序管理员或 Office 365 中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="8d519-107">To pin an app for your users, you must be a Cloud application administrator, or Application administrator in Azure Active Directory, or a Global administrator in Office 365.</span></span> <span data-ttu-id="8d519-108">有关管理员角色的详细信息，请参阅[Microsoft 365](../add-users/about-admin-roles.md)中的 Azure Active Directory 和管理员角色[中的管理员角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="8d519-108">For more information about admin roles, see [admin roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [admin roles in Microsoft 365](../add-users/about-admin-roles.md).</span></span> 

<span data-ttu-id="8d519-109">有关应用启动器和 Office.com 的详细信息，请参阅 [app 启动器](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) 和 [updates to office.com And the-Office 365 app 启动器](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) 博客文章。</span><span class="sxs-lookup"><span data-stu-id="8d519-109">For more information about the app launcher and Office.com, see [meet the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and [updates to office.com and the-Office 365 app launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blog article.</span></span>

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a><span data-ttu-id="8d519-110">使用 Azure Active Directory 门户来固定应用程序</span><span class="sxs-lookup"><span data-stu-id="8d519-110">Use the Azure Active Directory portal to pin apps</span></span>

1. <span data-ttu-id="8d519-111">转到 Microsoft 365 管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="8d519-111">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="8d519-112">在左侧导航中，选择 " **全部显示**"，然后在 " **管理中心**" 下选择 " **Azure Active Directory**"。</span><span class="sxs-lookup"><span data-stu-id="8d519-112">In the left nav, choose **Show all**, and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="8d519-113">在 " **Azure Active Directory**" 中，选择 "**企业应用程序**"  >  **用户设置**。</span><span class="sxs-lookup"><span data-stu-id="8d519-113">In **Azure Active Directory**, choose **Enterprise applications** > **User settings**.</span></span>
4. <span data-ttu-id="8d519-114">在 " **Office 365 设置** " 部分，选择 " **添加应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="8d519-114">In the **Office 365 Settings** section, choose **Add application**.</span></span>
5. <span data-ttu-id="8d519-115">选择要固定到用户的应用启动器的应用程序，然后选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="8d519-115">Choose the applications you want to pin to the users' app launcher, and then choose **Add**.</span></span>

:::image type="content" source="../../media/add-apps.png" alt-text="用于固定应用程序的 Microsoft 365 设置。":::

### <a name="pin-a-custom-app"></a><span data-ttu-id="8d519-117">固定自定义应用程序</span><span class="sxs-lookup"><span data-stu-id="8d519-117">Pin a custom app</span></span>

> [!NOTE]
> <span data-ttu-id="8d519-118">用户界面将指示是否需要购买其他 Azure AD 许可证才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="8d519-118">The user interface will indicate if you need need to purchase additional Azure AD licenses to use this feature.</span></span> <span data-ttu-id="8d519-119">有关详细信息，请参阅 [Azure Active Directory 定价](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="8d519-119">For more information see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

1. <span data-ttu-id="8d519-120">在 " **Azure Active Directory**" 中，选择 "所有应用程序" 页顶部的 "**企业应用程序**  >  **新应用程序**"。 **All applications**</span><span class="sxs-lookup"><span data-stu-id="8d519-120">In **Azure Active Directory**, choose **Enterprise applications** > **New application** on the top of the **All applications** page.</span></span>
2. <span data-ttu-id="8d519-121">如果位于 Azure Active Directory 的预览版本中，请在 " **添加应用程序** " 页上，选择 " **非库应用程序** " 或 " **创建您自己的应用程序** "。</span><span class="sxs-lookup"><span data-stu-id="8d519-121">On the **Add an application** page, choose **Non-gallery application** or **Create your own application** if you are in the preview version of Azure Active Directory.</span></span> 
3. <span data-ttu-id="8d519-122">键入应用程序的名称，然后在 " **用户和组** " 选项卡中分配用户。</span><span class="sxs-lookup"><span data-stu-id="8d519-122">Type a name for the application and then assign user in the **Users and groups** tab.</span></span>
4. <span data-ttu-id="8d519-123">使用 " **属性** " 选项卡上传应用程序的图标。</span><span class="sxs-lookup"><span data-stu-id="8d519-123">Use the **Properties** tab to upload an icon for the app.</span></span>
5. <span data-ttu-id="8d519-124">若要为应用程序分配 URL，请在 " **单一登录** " 选项卡中选择 " **链接** "，然后输入 URL。</span><span class="sxs-lookup"><span data-stu-id="8d519-124">To assign a URL to the app, in the **Single sign-on** tab, choose **Linked** and then enter a URL.</span></span>
6. <span data-ttu-id="8d519-125">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="8d519-125">Choose **Save**.</span></span>

## <a name="create-application-collections"></a><span data-ttu-id="8d519-126">创建应用程序集合</span><span class="sxs-lookup"><span data-stu-id="8d519-126">Create application collections</span></span>

<span data-ttu-id="8d519-127">您还可以为组织中的用户创建应用程序集合。</span><span class="sxs-lookup"><span data-stu-id="8d519-127">You can also create application collections for the users in your organization.</span></span> <span data-ttu-id="8d519-128">有关说明，请参阅 [Azure 门户中的我的应用门户上的创建集合](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections)。</span><span class="sxs-lookup"><span data-stu-id="8d519-128">For instructions, see [create collections on the My Apps portal in the Azure portal](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).</span></span>