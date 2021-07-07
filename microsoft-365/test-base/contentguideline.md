---
title: 测试包指南
description: 查看有关测试包的指南
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
ms.openlocfilehash: b6842f793627bddeab842bbd9570c9c3481699a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322514"
---
# <a name="test-package-guidelines"></a><span data-ttu-id="63252-103">测试包指南</span><span class="sxs-lookup"><span data-stu-id="63252-103">Test package guidelines</span></span>

## <a name="1---script-referencing"></a><span data-ttu-id="63252-104">1. 脚本引用</span><span class="sxs-lookup"><span data-stu-id="63252-104">1.   Script referencing</span></span>

<span data-ttu-id="63252-105">当您将.zip文件上载到门户时，我们会将该文件的所有内容解压缩到根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="63252-105">When you upload a .zip file to the portal, we unzip all the content of that file into a root folder.</span></span> <span data-ttu-id="63252-106">无需编写任何代码来执行此初始解压缩操作。</span><span class="sxs-lookup"><span data-stu-id="63252-106">You do not need to write any code to do this initial unzip operation.</span></span> <span data-ttu-id="63252-107">您还可以通过使用相对于上载的 zip 文件.zip文件内的任何文件。</span><span class="sxs-lookup"><span data-stu-id="63252-107">You also can reference any file within the .zip by using the path relative to the zip file uploaded.</span></span>

<span data-ttu-id="63252-108">在下面的示例中，我们显示了如何从"任务"选项卡的输入字段引用二进制文件/脚本。应该将蓝色文本输入到" **脚本路径** "字段中 **，而不使用引号。**</span><span class="sxs-lookup"><span data-stu-id="63252-108">In the example below, we show how you can reference your binaries/scripts from the input field in the Tasks tab. The text in blue should be entered into the **Script path** field **without the quotation marks.**</span></span>

<span data-ttu-id="63252-109">在上载 zip 文件之前，了解其中的内容非常重要。</span><span class="sxs-lookup"><span data-stu-id="63252-109">It is important you are aware of the content within your zip file before uploading it.</span></span> <span data-ttu-id="63252-110">通常，压缩文件夹时，本地计算机将在 zip 文件下创建主文件夹。</span><span class="sxs-lookup"><span data-stu-id="63252-110">Often when zipping a folder, your local machine will create a main folder underneath the zip file.</span></span> <span data-ttu-id="63252-111">在这种情况下，引用将如下所示 **，以粗体** 显示：</span><span class="sxs-lookup"><span data-stu-id="63252-111">In this case, the referencing will be as shown in **bold** below:</span></span>

 <span data-ttu-id="63252-112">**Contoso_App_Folder.zip**</span><span class="sxs-lookup"><span data-stu-id="63252-112">**Contoso_App_Folder.zip**</span></span>
~~~ 
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│        ├── file3.exe

│        ├── script.ps1
~~~

  - <span data-ttu-id="63252-113">ScriptX.ps1 – **"Contoso_App_Folder/ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="63252-113">ScriptX.ps1 – **“Contoso_App_Folder/ScriptX.ps1”**</span></span>
  - <span data-ttu-id="63252-114">Script.ps1 - **"Contoso_App_Folder/folder1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="63252-114">Script.ps1 – **“Contoso_App_Folder/folder1/script.ps1”**</span></span>

<span data-ttu-id="63252-115">其他时候，zip 文件可能正下方有文件或内容，即没有 2nd 级文件夹：</span><span class="sxs-lookup"><span data-stu-id="63252-115">Other times, your zip file may have your files or content right underneath it i.e. no 2nd-level folder:</span></span>

 <span data-ttu-id="63252-116">**Zip_file_uploaded.zip**</span><span class="sxs-lookup"><span data-stu-id="63252-116">**Zip_file_uploaded.zip**</span></span>
~~~ 
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - <span data-ttu-id="63252-117">ScriptX.ps1 – **"ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="63252-117">ScriptX.ps1 – **“ScriptX.ps1”**</span></span>
  - <span data-ttu-id="63252-118">Script.ps1 - **"folder1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="63252-118">Script.ps1 – **“folder1/script.ps1”**</span></span>
  
## <a name="2---script-execution"></a><span data-ttu-id="63252-119">2. 脚本执行</span><span class="sxs-lookup"><span data-stu-id="63252-119">2.   Script execution</span></span>

<span data-ttu-id="63252-120">**Out-of-Box 测试：** 应用程序包至少需要包含三个 PowerShell 脚本，这些脚本将执行无人参与安装、启动和关闭应用程序及其依赖项。</span><span class="sxs-lookup"><span data-stu-id="63252-120">**Out-of-Box tests:** The application package needs to contain at least three PowerShell scripts that will execute unattended installing, launching, and closing of the application and its dependencies.</span></span> <span data-ttu-id="63252-121">每个脚本都应检查自己的必备组件，验证成功，并在必要时 (清理) 。</span><span class="sxs-lookup"><span data-stu-id="63252-121">Each script should handle checking its own prerequisites, validating it succeeded, as well as cleaning up after itself (if necessary).</span></span>

<span data-ttu-id="63252-122">**功能测试：** 应用程序包至少需要包含一个 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="63252-122">**Functional tests:** The application package needs to contain at least one PowerShell script.</span></span> <span data-ttu-id="63252-123">如果提供了多个脚本，脚本将按上载顺序运行，并且特定脚本中的失败将阻止后续脚本执行。</span><span class="sxs-lookup"><span data-stu-id="63252-123">Where more than one script is provided, the scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>

### <a name="script-requirements"></a><span data-ttu-id="63252-124">脚本要求</span><span class="sxs-lookup"><span data-stu-id="63252-124">Script requirements</span></span>

<span data-ttu-id="63252-125">• PowerShell 版本 5.1 及以上</span><span class="sxs-lookup"><span data-stu-id="63252-125">•   PowerShell Version 5.1+</span></span>     

<span data-ttu-id="63252-126">• 无人参与执行</span><span class="sxs-lookup"><span data-stu-id="63252-126">•   Unattended execution</span></span>    

<span data-ttu-id="63252-127">• 错误返回代码</span><span class="sxs-lookup"><span data-stu-id="63252-127">•   Error return code</span></span>               

<span data-ttu-id="63252-128">• 验证成功</span><span class="sxs-lookup"><span data-stu-id="63252-128">•   Validate success</span></span>            

<span data-ttu-id="63252-129">• 记录以编写特定日志文件夹的脚本</span><span class="sxs-lookup"><span data-stu-id="63252-129">•   Logging to script specific log folder</span></span>

<span data-ttu-id="63252-130">每个脚本都需要完全无人参与运行，以在测试管道中成功执行。</span><span class="sxs-lookup"><span data-stu-id="63252-130">Each script needs to run completely unattended to successfully execute in the test pipeline.</span></span>

> [!Note]
> <span data-ttu-id="63252-131">脚本应在成功完成时返回"0"，如果在执行期间发生任何错误，则返回非零错误代码。</span><span class="sxs-lookup"><span data-stu-id="63252-131">Scripts should return “0” on successful completion and a non-zero error code if any error occurs during execution.</span></span>

<span data-ttu-id="63252-132">每个脚本应验证其是否成功运行。</span><span class="sxs-lookup"><span data-stu-id="63252-132">Each script should validate that it ran successfully.</span></span> <span data-ttu-id="63252-133">例如，</span><span class="sxs-lookup"><span data-stu-id="63252-133">E.g.</span></span> <span data-ttu-id="63252-134">安装程序二进制文件执行完成后，安装脚本应检查系统上是否存在某些二进制文件和/或注册表项，以确保在合理的置信度下安装成功。</span><span class="sxs-lookup"><span data-stu-id="63252-134">the install script should check for the existence of certain binaries and/or registry keys on the system, after the installer binary finishes executing to ensure with a reasonable degree of confidence that the installation was successful.</span></span> 

<span data-ttu-id="63252-135">这是正确诊断在测试运行期间发生错误（例如，无法成功安装应用程序与无法启动应用程序）所必需的。</span><span class="sxs-lookup"><span data-stu-id="63252-135">This is necessary to properly diagnose where errors occur during a test run, e.g. unable to install the application successfully versus being unable to launch it.</span></span>

> [!Important]
> <span data-ttu-id="63252-136">**避免以下事项：** 脚本不应重新启动计算机，如果需要重新启动，请在上载脚本期间指定此参数。</span><span class="sxs-lookup"><span data-stu-id="63252-136">**Avoid the following:** Scripts should not reboot the machine, if a reboot is necessary please specify this during the upload of your scripts.</span></span>

## <a name="3---log-collection"></a><span data-ttu-id="63252-137">3. 日志集合</span><span class="sxs-lookup"><span data-stu-id="63252-137">3.   Log collection</span></span>

<span data-ttu-id="63252-138">每个脚本都应将生成的任何日志输出到名为 的文件夹中 ```logs``` 。</span><span class="sxs-lookup"><span data-stu-id="63252-138">Each script should output any logs it generates into a folder named ```logs```.</span></span> <span data-ttu-id="63252-139">将复制目录中名为 的所有文件夹， ```logs``` 并呈现在页面上进行 ```Test Results``` 下载。</span><span class="sxs-lookup"><span data-stu-id="63252-139">All folders in the directory named ```logs``` will be copied and presented for download on the ```Test Results``` page.</span></span>

<span data-ttu-id="63252-140">例如，可能位于 **App/scripts/install** 目录) 中的安装脚本 (可以将其日志输出到 **：logs/install.log，** 这样最终日志将位于 **：Apps/scripts/install/logs/install.log**</span><span class="sxs-lookup"><span data-stu-id="63252-140">For example, the installation script (which may be located in the **App/scripts/install** directory) can output its logs to: **logs/install.log**, such that the final log will be at: **Apps/scripts/install/logs/install.log**</span></span>

<span data-ttu-id="63252-141">系统将选取文件以及其他文件夹中的其他文件， ```install.log``` ```logs``` 并整理该文件进行下载。</span><span class="sxs-lookup"><span data-stu-id="63252-141">The system will pick up the ```install.log``` file along with other files within other ```logs``` folders and collate it for download.</span></span>


## <a name="4---application-binaries"></a><span data-ttu-id="63252-142">4. 应用程序二进制文件</span><span class="sxs-lookup"><span data-stu-id="63252-142">4.   Application binaries</span></span>

<span data-ttu-id="63252-143">任何二进制文件和依赖项都应包含在单个 zip 文件中。</span><span class="sxs-lookup"><span data-stu-id="63252-143">Any binaries and dependencies should be included in the single zip file.</span></span> 

<span data-ttu-id="63252-144">这些应包括安装应用程序所需的一切 (，例如应用程序安装程序) ;如果应用程序依赖任何框架（如 .NET Core/Standard 或 .NET Framework），则这些文件应包含在文件中，并正确引用提供的脚本。</span><span class="sxs-lookup"><span data-stu-id="63252-144">These should include everything necessary for installation of the application (e.g. the application installer); if the application has a dependency on any frameworks, such as .NET Core/Standard or .NET Framework, these should be included in the file and referenced correctly in the provided scripts.</span></span>


> [!Note]
> <span data-ttu-id="63252-145">上载的 zip 文件的名称中不能包含任何空格或特殊字符</span><span class="sxs-lookup"><span data-stu-id="63252-145">The uploaded zip file cannot have any spaces or special characters in its name</span></span>

## <a name="next-steps"></a><span data-ttu-id="63252-146">后续步骤</span><span class="sxs-lookup"><span data-stu-id="63252-146">Next steps</span></span>

<span data-ttu-id="63252-147">前进到下一篇文章以查看一些常见问题 (**常见问题)**</span><span class="sxs-lookup"><span data-stu-id="63252-147">Advance to the next article to view some **Frequently Asked Questions (FAQ)**</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="63252-148">后续步骤</span><span class="sxs-lookup"><span data-stu-id="63252-148">Next step</span></span>](faq.md)
