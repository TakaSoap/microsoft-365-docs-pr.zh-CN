---
title: 配置和验证适用于 Mac 的 Microsoft Defender ATP 的排除项
description: 提供并验证适用于 Mac 的 Microsoft Defender ATP 的排除项。 可以针对文件、文件夹和进程设置排除项。
keywords: microsoft， defender， atp， mac， 排除， 扫描， 防病毒
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b1282543a68ce4cb5c322423656d33c5db12b97b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688581"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="aa35a-105">在 macOS 上配置和验证适用于终结点的 Microsoft Defender 的排除项</span><span class="sxs-lookup"><span data-stu-id="aa35a-105">Configure and validate exclusions for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="aa35a-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="aa35a-106">**Applies to:**</span></span>
- [<span data-ttu-id="aa35a-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="aa35a-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aa35a-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aa35a-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="aa35a-109">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="aa35a-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aa35a-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="aa35a-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="aa35a-111">本文提供有关如何定义适用于按需扫描以及实时保护和监视的排除项的信息。</span><span class="sxs-lookup"><span data-stu-id="aa35a-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

>[!IMPORTANT]
><span data-ttu-id="aa35a-112">本文中介绍的排除项不适用于其他 Defender for Mac 功能，包括终结点检测和响应 (EDR) 。</span><span class="sxs-lookup"><span data-stu-id="aa35a-112">The exclusions described in this article don't apply to other Defender for Endpoint for Mac capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="aa35a-113">使用本文中所述的方法排除的文件仍可以触发 EDR 警报和其他检测。</span><span class="sxs-lookup"><span data-stu-id="aa35a-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="aa35a-114">你可以从 Defender for Endpoint for Mac 扫描中排除某些文件、文件夹、进程和进程打开的文件。</span><span class="sxs-lookup"><span data-stu-id="aa35a-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint for Mac scans.</span></span>

<span data-ttu-id="aa35a-115">排除项可用于避免对组织唯一或自定义的文件或软件进行错误检测。</span><span class="sxs-lookup"><span data-stu-id="aa35a-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="aa35a-116">它们还可用于缓解由 Defender for Endpoint for Mac 引起的性能问题。</span><span class="sxs-lookup"><span data-stu-id="aa35a-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint for Mac.</span></span>

>[!WARNING]
><span data-ttu-id="aa35a-117">定义排除项会降低 Defender for Endpoint for Mac 所提供的保护。</span><span class="sxs-lookup"><span data-stu-id="aa35a-117">Defining exclusions lowers the protection offered by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="aa35a-118">您应始终评估与实施排除项相关的风险，并且只应排除您确信不是恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="aa35a-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="aa35a-119">支持的排除类型</span><span class="sxs-lookup"><span data-stu-id="aa35a-119">Supported exclusion types</span></span>

<span data-ttu-id="aa35a-120">下表显示了 Defender for Endpoint for Mac 支持的排除类型。</span><span class="sxs-lookup"><span data-stu-id="aa35a-120">The follow table shows the exclusion types supported by Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="aa35a-121">排除</span><span class="sxs-lookup"><span data-stu-id="aa35a-121">Exclusion</span></span> | <span data-ttu-id="aa35a-122">定义</span><span class="sxs-lookup"><span data-stu-id="aa35a-122">Definition</span></span> | <span data-ttu-id="aa35a-123">示例</span><span class="sxs-lookup"><span data-stu-id="aa35a-123">Examples</span></span>
---|---|---
<span data-ttu-id="aa35a-124">文件扩展名</span><span class="sxs-lookup"><span data-stu-id="aa35a-124">File extension</span></span> | <span data-ttu-id="aa35a-125">计算机上任意位置具有扩展名的所有文件</span><span class="sxs-lookup"><span data-stu-id="aa35a-125">All files with the extension, anywhere on the machine</span></span> | `.test`
<span data-ttu-id="aa35a-126">文件</span><span class="sxs-lookup"><span data-stu-id="aa35a-126">File</span></span> | <span data-ttu-id="aa35a-127">由完整路径标识的特定文件</span><span class="sxs-lookup"><span data-stu-id="aa35a-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="aa35a-128">Folder</span><span class="sxs-lookup"><span data-stu-id="aa35a-128">Folder</span></span> | <span data-ttu-id="aa35a-129">指定文件夹下的所有 (以递归) </span><span class="sxs-lookup"><span data-stu-id="aa35a-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="aa35a-130">流程</span><span class="sxs-lookup"><span data-stu-id="aa35a-130">Process</span></span> | <span data-ttu-id="aa35a-131">特定进程 (的完整路径或文件名指定，) 它打开的所有文件</span><span class="sxs-lookup"><span data-stu-id="aa35a-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

<span data-ttu-id="aa35a-132">文件、文件夹和进程排除项支持以下通配符：</span><span class="sxs-lookup"><span data-stu-id="aa35a-132">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="aa35a-133">通配符</span><span class="sxs-lookup"><span data-stu-id="aa35a-133">Wildcard</span></span> | <span data-ttu-id="aa35a-134">说明</span><span class="sxs-lookup"><span data-stu-id="aa35a-134">Description</span></span> | <span data-ttu-id="aa35a-135">示例</span><span class="sxs-lookup"><span data-stu-id="aa35a-135">Example</span></span> | <span data-ttu-id="aa35a-136">匹配</span><span class="sxs-lookup"><span data-stu-id="aa35a-136">Matches</span></span> | <span data-ttu-id="aa35a-137">不匹配</span><span class="sxs-lookup"><span data-stu-id="aa35a-137">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="aa35a-138">匹配任意数目的任何字符，包括无 (请注意，当在路径内使用此通配符时，它将仅替换一个) </span><span class="sxs-lookup"><span data-stu-id="aa35a-138">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/*/*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="aa35a-139">?</span><span class="sxs-lookup"><span data-stu-id="aa35a-139">?</span></span> | <span data-ttu-id="aa35a-140">匹配任何单个字符</span><span class="sxs-lookup"><span data-stu-id="aa35a-140">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

>[!NOTE]
><span data-ttu-id="aa35a-141">产品在评估排除项时尝试解析固定链接。</span><span class="sxs-lookup"><span data-stu-id="aa35a-141">The product attempts to resolve firmlinks when evaluating exclusions.</span></span> <span data-ttu-id="aa35a-142">当排除项包含通配符或目标文件 (卷上不存在时，) `Data` 解析不起作用。</span><span class="sxs-lookup"><span data-stu-id="aa35a-142">Firmlink resolution does not work when the exclusion contains wildcards or the target file (on the `Data` volume) does not exist.</span></span>

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="aa35a-143">如何配置排除项列表</span><span class="sxs-lookup"><span data-stu-id="aa35a-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="aa35a-144">从管理控制台</span><span class="sxs-lookup"><span data-stu-id="aa35a-144">From the management console</span></span>

<span data-ttu-id="aa35a-145">若要详细了解如何配置 JAMF、Intune 或其他管理控制台中的排除项，请参阅为适用于 Mac 的 [Defender 终结点设置首选项](mac-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="aa35a-145">For more information on how to configure exclusions from JAMF, Intune, or another management console, see [Set preferences for Defender for Endpoint for Mac](mac-preferences.md).</span></span>

### <a name="from-the-user-interface"></a><span data-ttu-id="aa35a-146">从用户界面</span><span class="sxs-lookup"><span data-stu-id="aa35a-146">From the user interface</span></span>

<span data-ttu-id="aa35a-147">打开 Defender for Endpoint 应用程序并导航到"管理 **设置**  >  **""** 添加或删除排除..."，如以下屏幕截图所示：</span><span class="sxs-lookup"><span data-stu-id="aa35a-147">Open the Defender for Endpoint application and navigate to **Manage settings** > **Add or Remove Exclusion...**, as shown in the following screenshot:</span></span>

![管理排除项屏幕截图](images/mdatp-37-exclusions.png)

<span data-ttu-id="aa35a-149">选择要添加的排除类型并按照提示操作。</span><span class="sxs-lookup"><span data-stu-id="aa35a-149">Select the type of exclusion that you wish to add and follow the prompts.</span></span>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="aa35a-150">使用 EICAR 测试文件验证排除列表</span><span class="sxs-lookup"><span data-stu-id="aa35a-150">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="aa35a-151">可以使用 下载测试文件来验证排除列表 `curl` 是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="aa35a-151">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="aa35a-152">在下面的 Bash 代码段中， `test.txt` 将 替换为符合排除规则的文件。</span><span class="sxs-lookup"><span data-stu-id="aa35a-152">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="aa35a-153">例如，如果已排除扩展 `.testing` ，请将 替换为 `test.txt` `test.testing` 。</span><span class="sxs-lookup"><span data-stu-id="aa35a-153">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="aa35a-154">如果要测试路径，请确保在此路径内运行命令。</span><span class="sxs-lookup"><span data-stu-id="aa35a-154">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="aa35a-155">如果 Defender for Endpoint for Mac 报告恶意软件，则规则无法工作。</span><span class="sxs-lookup"><span data-stu-id="aa35a-155">If Defender for Endpoint for Mac reports malware, then the rule is not working.</span></span> <span data-ttu-id="aa35a-156">如果没有恶意软件报告，并且下载的文件存在，则排除将正常工作。</span><span class="sxs-lookup"><span data-stu-id="aa35a-156">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="aa35a-157">你可以打开文件以确认内容与 EICAR 测试文件网站上 [介绍的内容相同](http://2016.eicar.org/86-0-Intended-use.html)。</span><span class="sxs-lookup"><span data-stu-id="aa35a-157">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="aa35a-158">如果您无法访问 Internet，您可以创建自己的 EICAR 测试文件。</span><span class="sxs-lookup"><span data-stu-id="aa35a-158">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="aa35a-159">使用下面的 Bash 命令将 EICAR 字符串写入新的文本文件：</span><span class="sxs-lookup"><span data-stu-id="aa35a-159">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="aa35a-160">还可以将字符串复制到空白文本文件中，并尝试使用文件名或试图排除的文件夹中保存它。</span><span class="sxs-lookup"><span data-stu-id="aa35a-160">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="aa35a-161">允许威胁</span><span class="sxs-lookup"><span data-stu-id="aa35a-161">Allow threats</span></span>

<span data-ttu-id="aa35a-162">除了将某些内容排除在扫描之外，还可以将产品配置为不检测某些威胁 (由威胁名称标识) 。</span><span class="sxs-lookup"><span data-stu-id="aa35a-162">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="aa35a-163">使用此功能时应谨慎，因为它可能会使设备处于未保护状态。</span><span class="sxs-lookup"><span data-stu-id="aa35a-163">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="aa35a-164">若要将威胁名称添加到允许列表，请执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="aa35a-164">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="aa35a-165">可以使用以下命令获取与设备上检测关联的威胁名称：</span><span class="sxs-lookup"><span data-stu-id="aa35a-165">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="aa35a-166">例如，若要 (与 EICAR 检测关联的威胁) 添加到允许列表中，请 `EICAR-Test-File (not a virus)` 执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="aa35a-166">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
