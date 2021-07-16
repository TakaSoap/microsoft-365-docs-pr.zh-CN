---
title: 管理自动化文件夹排除
description: 添加自动化文件夹排除项，以控制从自动调查中排除的文件。
keywords: 管理， 自动化， 排除， 阻止， 清理， 恶意
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 05c103cba051c7d5e7f45e5dd3feb288013ee367
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454813"
---
# <a name="manage-automation-folder-exclusions"></a><span data-ttu-id="8392d-104">管理自动化文件夹排除</span><span class="sxs-lookup"><span data-stu-id="8392d-104">Manage automation folder exclusions</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8392d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8392d-105">**Applies to:**</span></span>
- [<span data-ttu-id="8392d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8392d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8392d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8392d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8392d-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="8392d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8392d-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="8392d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

<span data-ttu-id="8392d-110">自动文件夹排除项允许你指定自动调查将跳过的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8392d-110">Automation folder exclusions allow you to specify folders that the Automated investigation will skip.</span></span> 

<span data-ttu-id="8392d-111">可以控制要跳过的文件夹的以下属性：</span><span class="sxs-lookup"><span data-stu-id="8392d-111">You can control the following attributes about the folder that you'd like to be skipped:</span></span>
- <span data-ttu-id="8392d-112">Folders</span><span class="sxs-lookup"><span data-stu-id="8392d-112">Folders</span></span> 
- <span data-ttu-id="8392d-113">文件的扩展名</span><span class="sxs-lookup"><span data-stu-id="8392d-113">Extensions of the files</span></span>
- <span data-ttu-id="8392d-114">文件名</span><span class="sxs-lookup"><span data-stu-id="8392d-114">File names</span></span>


<span data-ttu-id="8392d-115">**Folders**</span><span class="sxs-lookup"><span data-stu-id="8392d-115">**Folders**</span></span><br>
<span data-ttu-id="8392d-116">可以指定要跳过的文件夹及其子文件夹。</span><span class="sxs-lookup"><span data-stu-id="8392d-116">You can specify a folder and its subfolders to be skipped.</span></span> 


>[!NOTE]
><span data-ttu-id="8392d-117">目前尚不支持使用通配符作为排除目录下的文件的方法。</span><span class="sxs-lookup"><span data-stu-id="8392d-117">At this time, use of wild cards as a way to exclude files under a directory is not yet supported.</span></span> 


<span data-ttu-id="8392d-118">**Extensions**</span><span class="sxs-lookup"><span data-stu-id="8392d-118">**Extensions**</span></span><br>
<span data-ttu-id="8392d-119">可以指定要排除在特定目录中的扩展。</span><span class="sxs-lookup"><span data-stu-id="8392d-119">You can specify the extensions to exclude in a specific directory.</span></span> <span data-ttu-id="8392d-120">扩展是阻止攻击者使用排除文件夹隐藏攻击的一种方法。</span><span class="sxs-lookup"><span data-stu-id="8392d-120">The extensions are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="8392d-121">扩展明确定义要忽略的文件。</span><span class="sxs-lookup"><span data-stu-id="8392d-121">The extensions explicitly define which files to ignore.</span></span> 

<span data-ttu-id="8392d-122">**文件名**</span><span class="sxs-lookup"><span data-stu-id="8392d-122">**File names**</span></span><br>
<span data-ttu-id="8392d-123">可以指定要排除在特定目录中的文件名。</span><span class="sxs-lookup"><span data-stu-id="8392d-123">You can specify the file names that you want to be excluded in a specific directory.</span></span> <span data-ttu-id="8392d-124">名称是阻止攻击者使用排除文件夹隐藏攻击的一种方法。</span><span class="sxs-lookup"><span data-stu-id="8392d-124">The names are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="8392d-125">名称明确定义要忽略的文件。</span><span class="sxs-lookup"><span data-stu-id="8392d-125">The names explicitly define which files to ignore.</span></span> 



## <a name="add-an-automation-folder-exclusion"></a><span data-ttu-id="8392d-126">添加自动化文件夹排除</span><span class="sxs-lookup"><span data-stu-id="8392d-126">Add an automation folder exclusion</span></span>
1. <span data-ttu-id="8392d-127">在导航窗格中，**选择"设置**  >    >  **终结点规则**  >  **自动化文件夹排除项"。**</span><span class="sxs-lookup"><span data-stu-id="8392d-127">In the navigation pane, select **Settings** > **Endpoints** > **Rules** > **Automation folder exclusions**.</span></span>  

2. <span data-ttu-id="8392d-128">单击 **"新建文件夹排除"。**</span><span class="sxs-lookup"><span data-stu-id="8392d-128">Click **New folder exclusion**.</span></span>  

3. <span data-ttu-id="8392d-129">输入文件夹详细信息：</span><span class="sxs-lookup"><span data-stu-id="8392d-129">Enter the folder details:</span></span>

    - <span data-ttu-id="8392d-130">文件夹</span><span class="sxs-lookup"><span data-stu-id="8392d-130">Folder</span></span>
    - <span data-ttu-id="8392d-131">扩展</span><span class="sxs-lookup"><span data-stu-id="8392d-131">Extensions</span></span>
    - <span data-ttu-id="8392d-132">文件名</span><span class="sxs-lookup"><span data-stu-id="8392d-132">File names</span></span>
    - <span data-ttu-id="8392d-133">说明</span><span class="sxs-lookup"><span data-stu-id="8392d-133">Description</span></span>

4. <span data-ttu-id="8392d-134">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="8392d-134">Click **Save**.</span></span>

>[!NOTE]
> <span data-ttu-id="8392d-135">用于收集或检查已排除文件的 Live Response 命令将失败，并出现错误："已排除文件"。</span><span class="sxs-lookup"><span data-stu-id="8392d-135">Live Response commands to collect or examine excluded files will fail with error: "File is excluded".</span></span> <span data-ttu-id="8392d-136">此外，自动调查将忽略排除的项目。</span><span class="sxs-lookup"><span data-stu-id="8392d-136">In addition, automated investigations will ignore the excluded items.</span></span>

## <a name="edit-an-automation-folder-exclusion"></a><span data-ttu-id="8392d-137">编辑自动化文件夹排除</span><span class="sxs-lookup"><span data-stu-id="8392d-137">Edit an automation folder exclusion</span></span> 
1. <span data-ttu-id="8392d-138">在导航窗格中，**选择"设置**  >    >  **终结点规则**  >  **自动化文件夹排除项"。**</span><span class="sxs-lookup"><span data-stu-id="8392d-138">In the navigation pane, select **Settings** > **Endpoints** > **Rules** > **Automation folder exclusions**.</span></span> 

2. <span data-ttu-id="8392d-139">单击 **文件夹** 排除上的"编辑"。</span><span class="sxs-lookup"><span data-stu-id="8392d-139">Click **Edit** on the folder exclusion.</span></span>  

3. <span data-ttu-id="8392d-140">更新规则的详细信息，**然后单击保存。**</span><span class="sxs-lookup"><span data-stu-id="8392d-140">Update the details of the rule and click **Save**.</span></span>

## <a name="remove-an-automation-folder-exclusion"></a><span data-ttu-id="8392d-141">删除自动化文件夹排除</span><span class="sxs-lookup"><span data-stu-id="8392d-141">Remove an automation folder exclusion</span></span> 
1. <span data-ttu-id="8392d-142">在导航窗格中，**选择"设置**  >    >  **终结点规则**  >  **自动化文件夹排除项"。**</span><span class="sxs-lookup"><span data-stu-id="8392d-142">In the navigation pane, select **Settings** > **Endpoints** > **Rules** > **Automation folder exclusions**.</span></span>  
2. <span data-ttu-id="8392d-143">单击 **"删除排除"。**</span><span class="sxs-lookup"><span data-stu-id="8392d-143">Click **Remove exclusion**.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="8392d-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="8392d-144">Related topics</span></span>
- [<span data-ttu-id="8392d-145">管理允许/阻止的自动化列表</span><span class="sxs-lookup"><span data-stu-id="8392d-145">Manage automation allowed/blocked lists</span></span>](manage-indicators.md)
- [<span data-ttu-id="8392d-146">管理自动化文件上载</span><span class="sxs-lookup"><span data-stu-id="8392d-146">Manage automation file uploads</span></span>](manage-automation-file-uploads.md)
