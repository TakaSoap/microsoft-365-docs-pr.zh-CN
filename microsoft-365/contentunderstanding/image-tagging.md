---
title: SharePoint Syntex 中的图像标记
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: MET150
localization_priority: Priority
description: 了解 SharePoint Syntex 中的图像标记
ms.openlocfilehash: 7b41422633934593de881bdb0c04f0a845a3fe5f
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321249"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="2f7ef-103">SharePoint Syntex 中的图像标记</span><span class="sxs-lookup"><span data-stu-id="2f7ef-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="2f7ef-104">借助 SharePoint Syntex 中的图像标记，用户可以通过搜索图像标记来查找图像，并基于图像标记创建工作流。</span><span class="sxs-lookup"><span data-stu-id="2f7ef-104">With image tagging in SharePoint Syntex, users can find images through search by searching on image tags, and create workflows based on image tags.</span></span> <span data-ttu-id="2f7ef-105">默认情况下，SharePoint 和 OneDrive 的基本图像标记处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="2f7ef-105">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="2f7ef-106">将自动扫描已上载到任一位置的图像，并从 37 个基本标记的列表中应用标记（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="2f7ef-106">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="2f7ef-107">用户可通过搜索图像标记查找图像。</span><span class="sxs-lookup"><span data-stu-id="2f7ef-107">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="2f7ef-108">用户上传图像时，将自动运行标记过程。</span><span class="sxs-lookup"><span data-stu-id="2f7ef-108">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="2f7ef-109">如果已编辑图像，则标记进程将再次运行以更新标记。</span><span class="sxs-lookup"><span data-stu-id="2f7ef-109">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="2f7ef-110">拥有映像文件权限的用户可以在文件信息面板或搜索结果页面中查看和编辑标记。</span><span class="sxs-lookup"><span data-stu-id="2f7ef-110">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="2f7ef-111">用户编辑图像标记后，即使已对其进行编辑，系统将不再自动标记该图像。</span><span class="sxs-lookup"><span data-stu-id="2f7ef-111">Once a user edits an image's tags, the system no longer auto-tags that image, even if it's edited.</span></span>

<span data-ttu-id="2f7ef-112">如果关闭了标记，将不再自动标记图像。</span><span class="sxs-lookup"><span data-stu-id="2f7ef-112">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="2f7ef-113">不会删除现有标记。</span><span class="sxs-lookup"><span data-stu-id="2f7ef-113">Existing tags won't be removed.</span></span>

> [!NOTE]
> <span data-ttu-id="2f7ef-114">系统生成的标记可能会随图像或标记技术的更新而变化。</span><span class="sxs-lookup"><span data-stu-id="2f7ef-114">System generated tags may change with updates to the image or our tag technology.</span></span>


## <a name="configure-image-tagging"></a><span data-ttu-id="2f7ef-115">配置映像标记</span><span class="sxs-lookup"><span data-stu-id="2f7ef-115">Configure image tagging</span></span>

<span data-ttu-id="2f7ef-116">[设置 SharePoint Syntex](set-up-content-understanding.md) 后，可在 Microsoft 365 管理中心中配置图像标记。</span><span class="sxs-lookup"><span data-stu-id="2f7ef-116">After you [set up SharePoint Syntex](set-up-content-understanding.md), you can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="2f7ef-117">打开或关闭图像标记</span><span class="sxs-lookup"><span data-stu-id="2f7ef-117">To turn image tagging on or off</span></span>

1. <span data-ttu-id="2f7ef-118">在 Microsoft 365 管理员中心中，单击 **“设置”**。</span><span class="sxs-lookup"><span data-stu-id="2f7ef-118">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="2f7ef-119">在**组织知识**下，单击 **“自动化内容理解”**。</span><span class="sxs-lookup"><span data-stu-id="2f7ef-119">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="2f7ef-120">单击“**管理**”。</span><span class="sxs-lookup"><span data-stu-id="2f7ef-120">Click **Manage**.</span></span>

4. <span data-ttu-id="2f7ef-121">在 **"图像标记"** 选项卡上，单击 **"编辑"**。</span><span class="sxs-lookup"><span data-stu-id="2f7ef-121">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="2f7ef-122">选择允许 **“基本标记”** 或 **“关闭”** 标记。</span><span class="sxs-lookup"><span data-stu-id="2f7ef-122">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="2f7ef-123">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="2f7ef-123">Click **Save**.</span></span>

    ![图像标记控件的屏幕截图](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)
