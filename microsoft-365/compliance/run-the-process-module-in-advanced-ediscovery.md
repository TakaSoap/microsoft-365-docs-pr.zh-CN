---
title: 在高级电子数据展示中运行进程模块
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: 了解准备数据案例文件以使用高级电子数据展示进行分析的准则。
ms.openlocfilehash: 3773833d9d0af993b4ccb35bcd18276800c4081f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662807"
---
# <a name="run-the-process-module-in-advanced-ediscovery-classic"></a><span data-ttu-id="1bc8c-103">在经典电子数据展示高级电子数据展示 (进程) </span><span class="sxs-lookup"><span data-stu-id="1bc8c-103">Run the Process module in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="1bc8c-104">在准备过程中，将案例文件加载到高级 **电子数据** \> **展示中**。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-104">Case files are loaded into the Advanced eDiscovery during **Prepare** \> **Process**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1bc8c-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a><span data-ttu-id="1bc8c-107">指南：为高级电子数据展示准备数据</span><span class="sxs-lookup"><span data-stu-id="1bc8c-107">Guidelines: Preparing data for Advanced eDiscovery</span></span>

- <span data-ttu-id="1bc8c-108">**质量**：清楚地标识与案例相关的案例文件总体。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-108">**Quality**: Clearly identify the case file population pertinent to the case.</span></span>
    
- <span data-ttu-id="1bc8c-109">**Load**： Load the files into a location that is accessible accessiblediscovery.</span><span class="sxs-lookup"><span data-stu-id="1bc8c-109">**Loads**: Load the files into a location that is accessible to Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="1bc8c-110">**文件 ID：** 高级电子数据展示中的唯一文件标识符。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-110">**File ID**: A unique file identifier in Advanced eDiscovery.</span></span> <span data-ttu-id="1bc8c-111">如果未导入任何文件标识符，则高级电子数据展示将自动生成 ID。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-111">If no file identifier is imported, Advanced eDiscovery automatically generates the ID.</span></span> <span data-ttu-id="1bc8c-112">如果在后续进程加载中映射 ID，并映射与初始进程加载不同的路径，则高级电子数据展示将替换路径 (，而不是在) 。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-112">If you map the ID in a subsequent Process load, and map a different path than in the initial Process load, Advanced eDiscovery will replace the path (rather than add a new file entry).</span></span> <span data-ttu-id="1bc8c-113">ID 可在导出过程中用作引用。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-113">The ID can be used as a reference in the Export process.</span></span> <span data-ttu-id="1bc8c-114">ID 值不应为"-1"。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-114">The ID value should not be "-1".</span></span>
    
- <span data-ttu-id="1bc8c-115">**MD5：** 此签名用于区分两 (文件不被视为完全相同的重复项，除非它们具有相同的 MD5) 。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-115">**MD5**: This signature is used to differentiate between files (two files are not considered exact duplicates unless they have the same MD5).</span></span> <span data-ttu-id="1bc8c-116">默认情况下，高级电子数据展示计算文件的 MD5。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-116">By default, Advanced eDiscovery calculates the MD5 of files.</span></span> <span data-ttu-id="1bc8c-117">当加载的文件是文本文件时，建议加载和映射原始 MD5 值，而不是在高级电子数据展示中计算该值。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-117">When the loaded files are text files, it is recommended to load and map the original MD5 value instead of calculating it in Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="1bc8c-118">**文件类型和名称**：</span><span class="sxs-lookup"><span data-stu-id="1bc8c-118">**File type and name**:</span></span>
    
  - <span data-ttu-id="1bc8c-119">高级电子数据展示可以处理各种格式的文件，将加载的本机文件提取为标准格式，例如 \* 。TXT、HTML 或 。XML。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-119">Advanced eDiscovery can process files of various formats and extract loaded native files into a standard format, such as \*.TXT, HTML, or .XML.</span></span> <span data-ttu-id="1bc8c-120">文本文件的处理速度比本机文件快。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-120">Processing of text files is faster than native files.</span></span> <span data-ttu-id="1bc8c-121">提取的文本文件存储在 case 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-121">Extracted text files are stored in the case folder.</span></span>
    
  - <span data-ttu-id="1bc8c-122">不要加载无法提取的文件，如系统文件或图形图像。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-122">Do not load files that cannot be extracted, such as system files or graphic images.</span></span> <span data-ttu-id="1bc8c-123">这些文件可能会延迟处理。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-123">These files may delay processing.</span></span>
    
  - <span data-ttu-id="1bc8c-124">验证文件名的命名和路径是否正确。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-124">Verify that file names are significantly named and paths are correct.</span></span>
    
- <span data-ttu-id="1bc8c-125">**文件路径**：高级电子数据展示可以加载路径长度最多为 400 个字符的文件。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-125">**File path**: Advanced eDiscovery can load files with path lengths up to 400 characters.</span></span>
    
- <span data-ttu-id="1bc8c-126">文本提取：从本机文件提取文本时，除了正常文本之外，还会提取以下内容：隐藏文本 (Excel 和 .doc) 、隐藏列 (Excel) 、跟踪更改 (.doc) 、扬声器备注 (.ppt) 、嵌入对象 (例如，.ppt) 中的 Excel 对象。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-126">**Text extraction**: When extracting text from native files, in addition to normal text, the following are also extracted: hidden text (Excel and .doc), hidden columns (Excel), track changes (.doc), speaker notes (.ppt), embedded objects (for example, Excel objects in a .ppt).</span></span> <span data-ttu-id="1bc8c-127">可以在文本编辑器中查看这些文本。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-127">These can be viewed in the Text editor.</span></span>
    
- <span data-ttu-id="1bc8c-128">**忽略文本**：此可选功能在进程运行后和分析之前定义。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-128">**Ignore Text**: This optional feature is defined after Process is run and before Analyze.</span></span> <span data-ttu-id="1bc8c-129">应谨慎使用忽略文本，因为它的使用可能会降低文件分析的性能。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-129">Ignore text should be used with caution because its use may reduce the performance of file analysis.</span></span>
    
- <span data-ttu-id="1bc8c-130">**多语言文本**：高级电子数据展示当前不处理标记、保管人和问题的多语言名称。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-130">**Multilingual text**: Advanced eDiscovery does not currently handle multilingual names for tags, custodian, and issues.</span></span>
    
- <span data-ttu-id="1bc8c-131">**元数据**：确定是否有要保存在案例数据库中供将来参考的元数据，例如日期范围、文件大小、文件类型、保管人和主题。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-131">**Metadata**: Determine if there is metadata that you want to save in the case database for future reference, such as date range, file size, file type, custodian, and subject.</span></span> <span data-ttu-id="1bc8c-132">可以在加载文件后加载元数据，而无需重新运行清单或增加重新处理开销。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-132">Metadata can be loaded after files were already loaded without rerunning the inventory or adding reprocessing overhead.</span></span> 
    
  - <span data-ttu-id="1bc8c-133">如果文件最初是按路径加载的，则稍后导入元数据时映射路径列。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-133">If the files were originally loaded by path, map the path column when later importing metadata.</span></span> <span data-ttu-id="1bc8c-134">可以按 ID 引用文件并映射其他路径。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-134">It is possible to refer to the file by ID and to map a different path.</span></span> <span data-ttu-id="1bc8c-135">当文件路径更改时，这是一个有用的方案。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-135">This is a useful scenario when the file paths change.</span></span>
    
  - <span data-ttu-id="1bc8c-136">如果文件最初由文件 ID 加载，则加载元数据时映射 ID 列。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-136">If the files were originally loaded by File ID, map the ID column when loading metadata.</span></span> <span data-ttu-id="1bc8c-137">按路径引用文件 (而不是 ID) 将导致使用其他 ID 重新加载文件。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-137">Referring to the file by path (instead of ID) will cause files to be re-loaded with a different ID.</span></span> <span data-ttu-id="1bc8c-138">高级电子数据展示会创建文件的副本，而不是加载现有文件的元数据。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-138">Advanced eDiscovery creates copies of the files rather that loading metadata of the existing files.</span></span>
    
- <span data-ttu-id="1bc8c-139">**家庭**：没有其父级或家庭 (无法加载) 。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-139">**Families**: It is not possible to load a family without its parent (head of family).</span></span> 
    
- <span data-ttu-id="1bc8c-140">**文件大小**：对加载到高级电子数据展示的文件的大小没有限制。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-140">**File size**: There is no limitation on the size of files loaded to Advanced eDiscovery.</span></span> <span data-ttu-id="1bc8c-141">对于分析 (分析、相关性等) ，提取的文本限制为 5，242，880 个字符。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-141">For analysis (Analyze, Relevance, etc.), the limit is 5,242,880 characters of extracted text.</span></span> <span data-ttu-id="1bc8c-142">较大的文件 (例如，在相关性中，文件不参与相关性培训过程，在批计算后不会获得相关性分数) 。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-142">Larger files are ignored (for example, in Relevance, files do not participate in the Relevance training process and do not receive a Relevance score after batch calculation).</span></span>
    
- <span data-ttu-id="1bc8c-143">**文件数量**：在单个情况下可以处理的文件数量没有建议的限制。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-143">**File quantity**: There is no recommended limit on the number of files that can be handled in a single case.</span></span> <span data-ttu-id="1bc8c-144">性能取决于系统资源。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-144">Performance depends on the resources of your system.</span></span> 
    
## <a name="filtering-files"></a><span data-ttu-id="1bc8c-145">筛选文件</span><span class="sxs-lookup"><span data-stu-id="1bc8c-145">Filtering files</span></span>

<span data-ttu-id="1bc8c-146">用户定义的标签可以与一组文件相关联，以将其从进程或其他任务中排除。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-146">A user-defined label can be associated with a set of files to exclude them from Process or other tasks.</span></span> <span data-ttu-id="1bc8c-147">每个进程会话都与一个批处理 ID 相关联。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-147">Each Process session is associated with a batch ID.</span></span> <span data-ttu-id="1bc8c-148">虽然批量 ID 对相关性专家不可见，但可通过为当前批处理添加筛选器，并标记所有具有用户定义标签的适当文件，使用搜索实用工具完成此操作。</span><span class="sxs-lookup"><span data-stu-id="1bc8c-148">Although the batch ID is not visible to the expert in Relevance, this can be done using a search utility, by adding a filter for the current batch and tagging all appropriate files with a user-defined label.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1bc8c-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1bc8c-149">See also</span></span>

[<span data-ttu-id="1bc8c-150">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="1bc8c-150">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="1bc8c-151">运行进程模块并加载数据</span><span class="sxs-lookup"><span data-stu-id="1bc8c-151">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[<span data-ttu-id="1bc8c-152">查看进程模块结果</span><span class="sxs-lookup"><span data-stu-id="1bc8c-152">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

