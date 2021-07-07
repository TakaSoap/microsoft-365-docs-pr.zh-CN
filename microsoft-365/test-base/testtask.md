---
title: 设置测试任务
description: 设置测试任务
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 64abb5b10e3dc1d52b6baf8ceccd5aff2baacefe
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322495"
---
# <a name="step-4-the-tasks-tab"></a><span data-ttu-id="7abc6-103">步骤 4："任务"选项卡</span><span class="sxs-lookup"><span data-stu-id="7abc6-103">Step 4: The tasks tab</span></span>

<span data-ttu-id="7abc6-104">在"任务"选项卡上，应提供测试脚本的路径，这些脚本位于"二进制文件"选项卡下上载的 zip 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7abc6-104">On the tasks tab, you are expected to provide the paths to your test scripts which are in the zip folder you uploaded under the binaries tab.</span></span>

  - <span data-ttu-id="7abc6-105">**开箱式测试脚本：** 键入安装、启动、关闭和卸载脚本的相对路径。</span><span class="sxs-lookup"><span data-stu-id="7abc6-105">**Out of Box Test Scripts:** Type in the relative paths to your install, launch, close and uninstall scripts.</span></span> <span data-ttu-id="7abc6-106">还可以选择安装脚本的其他设置。</span><span class="sxs-lookup"><span data-stu-id="7abc6-106">You also have the option to select additional settings for the install script.</span></span>
  - <span data-ttu-id="7abc6-107">**功能测试脚本：** 键入上载的每个功能测试脚本的相对路径。</span><span class="sxs-lookup"><span data-stu-id="7abc6-107">**Functional Test Scripts:** Type in the relative path to each functional test script uploaded.</span></span> <span data-ttu-id="7abc6-108">可以使用 按钮添加其他功能测试 ```Add Script``` 脚本。</span><span class="sxs-lookup"><span data-stu-id="7abc6-108">Additional functional test scripts can be added using the ```Add Script``` button.</span></span> <span data-ttu-id="7abc6-109">至少需要一个 1 (1) 脚本，并且可以在 8 个 (8 个) 脚本。</span><span class="sxs-lookup"><span data-stu-id="7abc6-109">You need a minimum of one (1) script and can add up to eight (8) functional test scripts.</span></span> 
  
    <span data-ttu-id="7abc6-110">脚本按上载顺序运行，特定脚本中的失败将停止后续脚本的执行。</span><span class="sxs-lookup"><span data-stu-id="7abc6-110">The scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>
    <span data-ttu-id="7abc6-111">还可以选择为提供的每个脚本选择其他设置。</span><span class="sxs-lookup"><span data-stu-id="7abc6-111">You also have the option of selecting additional settings for each script provided.</span></span>

## <a name="set-script-path"></a><span data-ttu-id="7abc6-112">设置脚本路径</span><span class="sxs-lookup"><span data-stu-id="7abc6-112">Set script path</span></span>

![测试任务的图像](Media/testtask.png)

<span data-ttu-id="7abc6-114">下面是如何在文件夹结构上提供相对路径的示例：</span><span class="sxs-lookup"><span data-stu-id="7abc6-114">Sample of how to provide the relative path on a folder structure is below:</span></span>

<span data-ttu-id="7abc6-115">_**Zip_file_uploaded**_</span><span class="sxs-lookup"><span data-stu-id="7abc6-115">_**Zip_file_uploaded**_</span></span>
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - <span data-ttu-id="7abc6-116">**ScriptX.ps1** 将具有。</span><span class="sxs-lookup"><span data-stu-id="7abc6-116">**ScriptX.ps1** would have.</span></span> <span data-ttu-id="7abc6-117">_ScriptX.ps1_ 作为相对路径。</span><span class="sxs-lookup"><span data-stu-id="7abc6-117">_ScriptX.ps1_ as the relative path.</span></span>
  - <span data-ttu-id="7abc6-118">**Script.ps1** 将 _folder1/script.ps1_ 作为相对路径。</span><span class="sxs-lookup"><span data-stu-id="7abc6-118">**Script.ps1** would have _folder1/script.ps1_ as the relative path.</span></span>


## <a name="next-steps"></a><span data-ttu-id="7abc6-119">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7abc6-119">Next steps</span></span>

<span data-ttu-id="7abc6-120">查看下一篇文章中的"测试选项"选项卡的详细信息</span><span class="sxs-lookup"><span data-stu-id="7abc6-120">View details of the Test Options tab in the next article</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="7abc6-121">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7abc6-121">Next step</span></span>](testoptions.md)
