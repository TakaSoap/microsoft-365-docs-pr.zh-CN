---
title: SharePoint Syntex 中的图像标记
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: 了解 SharePoint Syntex 中的图像标记
ms.openlocfilehash: 38b9ad6823aa5f63a4ddec87bab7fec52a37f163
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295800"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="11e34-103">SharePoint Syntex 中的图像标记</span><span class="sxs-lookup"><span data-stu-id="11e34-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="11e34-104">默认情况下，SharePoint 和 OneDrive 的基本图像标记处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="11e34-104">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="11e34-105">将自动扫描已上载到任一位置的图像，并从 37 个基本标记的列表中应用标记（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="11e34-105">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="11e34-106">用户可通过搜索图像标记查找图像。</span><span class="sxs-lookup"><span data-stu-id="11e34-106">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="11e34-107">用户上传图像时，将自动运行标记过程。</span><span class="sxs-lookup"><span data-stu-id="11e34-107">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="11e34-108">如果已编辑图像，则标记进程将再次运行以更新标记。</span><span class="sxs-lookup"><span data-stu-id="11e34-108">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="11e34-109">拥有映像文件权限的用户可以在文件信息面板或搜索结果页面中查看和编辑标记。</span><span class="sxs-lookup"><span data-stu-id="11e34-109">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="11e34-110">用户编辑图像标记后，系统将不再对该图像执行自动标记，即使已对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="11e34-110">Once a user edits an image's tags, the system no longer performs auto-tagging on that image, even if it is edited.</span></span>

<span data-ttu-id="11e34-111">如果关闭了标记，将不再自动标记图像。</span><span class="sxs-lookup"><span data-stu-id="11e34-111">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="11e34-112">不会删除现有标记。</span><span class="sxs-lookup"><span data-stu-id="11e34-112">Existing tags will not be removed.</span></span>

## <a name="configure-image-tagging"></a><span data-ttu-id="11e34-113">配置映像标记</span><span class="sxs-lookup"><span data-stu-id="11e34-113">Configure image tagging</span></span>

<span data-ttu-id="11e34-114">可在 Microsoft 365 管理中心配置图像标记。</span><span class="sxs-lookup"><span data-stu-id="11e34-114">You can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="11e34-115">打开或关闭图像标记</span><span class="sxs-lookup"><span data-stu-id="11e34-115">To turn image tagging on or off</span></span>

1. <span data-ttu-id="11e34-116">在 Microsoft 365 管理员中心中，单击 **“设置”**。</span><span class="sxs-lookup"><span data-stu-id="11e34-116">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="11e34-117">在**组织知识**下，单击 **“自动化内容理解”**。</span><span class="sxs-lookup"><span data-stu-id="11e34-117">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="11e34-118">单击“**管理**”。</span><span class="sxs-lookup"><span data-stu-id="11e34-118">Click **Manage**.</span></span>

4. <span data-ttu-id="11e34-119">在 **"图像标记"** 选项卡上，单击 **"编辑"**。</span><span class="sxs-lookup"><span data-stu-id="11e34-119">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="11e34-120">选择允许 **“基本标记”** 或 **“关闭”** 标记。</span><span class="sxs-lookup"><span data-stu-id="11e34-120">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="11e34-121">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="11e34-121">Click **Save**.</span></span>

    ![图像标记控件的屏幕截图](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)

## <a name="see-also"></a><span data-ttu-id="11e34-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11e34-123">See also</span></span>

[<span data-ttu-id="11e34-124">设置内容理解</span><span class="sxs-lookup"><span data-stu-id="11e34-124">Set up content understanding</span></span>](set-up-content-understanding.md)