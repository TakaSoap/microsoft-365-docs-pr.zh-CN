---
title: 创建文件指示器
ms.reviewer: ''
description: 创建文件哈希的指示器，以定义实体的检测、防范和排除。
keywords: 文件， 哈希， 管理， 允许， 阻止， 阻止， 清理， 恶意， 文件哈希， ip 地址， url， 域
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
ms.openlocfilehash: 4edff7a9c7f541e31363519e4bafc2a21602e011
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056321"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="94ae8-104">创建文件指示器</span><span class="sxs-lookup"><span data-stu-id="94ae8-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="94ae8-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="94ae8-105">**Applies to:**</span></span>
- [<span data-ttu-id="94ae8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="94ae8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="94ae8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94ae8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



><span data-ttu-id="94ae8-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="94ae8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="94ae8-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="94ae8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="94ae8-110">通过禁止潜在恶意文件或可疑恶意软件，可防止攻击在组织中进一步传播。</span><span class="sxs-lookup"><span data-stu-id="94ae8-110">You can prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="94ae8-111">如果你知道 PE 文件中可能存在恶意 (可执行) ，可以阻止它。</span><span class="sxs-lookup"><span data-stu-id="94ae8-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="94ae8-112">此操作将阻止在组织中计算机上读取、写入或执行该操作。</span><span class="sxs-lookup"><span data-stu-id="94ae8-112">This operation will prevent it from being read, written, or executed on machines in your organization.</span></span>

<span data-ttu-id="94ae8-113">有两种方法可以创建文件指示器：</span><span class="sxs-lookup"><span data-stu-id="94ae8-113">There are two ways you can create indicators for files:</span></span>
- <span data-ttu-id="94ae8-114">通过设置页面创建指示器</span><span class="sxs-lookup"><span data-stu-id="94ae8-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="94ae8-115">通过使用文件详细信息页面中的"添加指示器"按钮创建上下文指示器</span><span class="sxs-lookup"><span data-stu-id="94ae8-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="94ae8-116">准备工作</span><span class="sxs-lookup"><span data-stu-id="94ae8-116">Before you begin</span></span>
<span data-ttu-id="94ae8-117">在创建文件指示器之前，了解以下先决条件很重要：</span><span class="sxs-lookup"><span data-stu-id="94ae8-117">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="94ae8-118">如果你的组织使用防病毒和基于云的Windows Defender，此功能可用。</span><span class="sxs-lookup"><span data-stu-id="94ae8-118">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="94ae8-119">有关详细信息，请参阅通过云提供的保护使用 [Microsoft Defender 防病毒中的下一代技术](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="94ae8-119">For more information, see [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="94ae8-120">反恶意软件客户端版本必须为 4.18.1901.x 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="94ae8-120">The Antimalware client version must be 4.18.1901.x or later.</span></span>
- <span data-ttu-id="94ae8-121">在 Windows 10 版本 1703 或更高版本、Windows Server 2016 和 2019 上的计算机上受支持。</span><span class="sxs-lookup"><span data-stu-id="94ae8-121">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="94ae8-122">若要开始阻止文件，首先需要打开"设置"[**中的"阻止或**](advanced-features.md)允许"功能。</span><span class="sxs-lookup"><span data-stu-id="94ae8-122">To start blocking files, you first need to [turn the **Block or allow** feature on](advanced-features.md) in Settings.</span></span>
- <span data-ttu-id="94ae8-123">此功能旨在防止从 web (可疑恶意软件) 潜在恶意文件。</span><span class="sxs-lookup"><span data-stu-id="94ae8-123">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="94ae8-124">它当前支持可移植的可执行 (PE) 文件，包括 _.exe_ 和 _.dll_ 文件。</span><span class="sxs-lookup"><span data-stu-id="94ae8-124">It currently supports portable executable (PE) files, including _.exe_ and _.dll_ files.</span></span> <span data-ttu-id="94ae8-125">覆盖范围将随着时间的推移而延长。</span><span class="sxs-lookup"><span data-stu-id="94ae8-125">The coverage will be extended over time.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="94ae8-126">如果文件分类存在于允许或阻止操作之前的设备的缓存中，则不能对文件执行允许或阻止功能</span><span class="sxs-lookup"><span data-stu-id="94ae8-126">The allow or block function cannot be done on files if the file's classification exists on the device's cache prior to the allow or block action</span></span> 
>- <span data-ttu-id="94ae8-127">受信任的已签名文件将受到不同的处理。</span><span class="sxs-lookup"><span data-stu-id="94ae8-127">Trusted signed files will be treated differently.</span></span> <span data-ttu-id="94ae8-128">Defender for Endpoint 经过优化，可处理恶意文件。</span><span class="sxs-lookup"><span data-stu-id="94ae8-128">Defender for Endpoint is optimized to handle malicious files.</span></span> <span data-ttu-id="94ae8-129">在某些情况下，尝试阻止受信任的已签名文件可能有性能影响。</span><span class="sxs-lookup"><span data-stu-id="94ae8-129">Trying to block trusted signed files, in some cases, may have performance implications.</span></span>

 
>[!NOTE]
><span data-ttu-id="94ae8-130">通常，文件块将在几分钟内强制执行，但可能需要 30 分钟以上的时间。</span><span class="sxs-lookup"><span data-stu-id="94ae8-130">Typically, file blocks are enforced within a couple of minutes, but can take upwards of 30 minutes.</span></span>

### <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="94ae8-131">从设置页创建文件指示器</span><span class="sxs-lookup"><span data-stu-id="94ae8-131">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="94ae8-132">在导航窗格中，选择"**设置**  >  **""指示器"。**</span><span class="sxs-lookup"><span data-stu-id="94ae8-132">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="94ae8-133">选择" **文件哈希"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="94ae8-133">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="94ae8-134">选择 **"添加指示器"。**</span><span class="sxs-lookup"><span data-stu-id="94ae8-134">Select **Add indicator**.</span></span>

4. <span data-ttu-id="94ae8-135">指定以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="94ae8-135">Specify the following details:</span></span>
   - <span data-ttu-id="94ae8-136">Indicator - 指定实体详细信息并定义指示器的过期时间。</span><span class="sxs-lookup"><span data-stu-id="94ae8-136">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="94ae8-137">操作 - 指定要采取的操作并提供说明。</span><span class="sxs-lookup"><span data-stu-id="94ae8-137">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="94ae8-138">Scope - 定义计算机组的范围。</span><span class="sxs-lookup"><span data-stu-id="94ae8-138">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="94ae8-139">查看"摘要"选项卡中的详细信息，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="94ae8-139">Review the details in the Summary tab, then click **Save**.</span></span>

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="94ae8-140">从文件详细信息页面创建上下文指示器</span><span class="sxs-lookup"><span data-stu-id="94ae8-140">Create a contextual indicator from the file details page</span></span>
<span data-ttu-id="94ae8-141">对文件执行响应 [操作的选项](respond-file-alerts.md) 之一是添加文件指示器。</span><span class="sxs-lookup"><span data-stu-id="94ae8-141">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> 

<span data-ttu-id="94ae8-142">为文件添加指示器哈希时，可以选择引发警报，并阻止组织中计算机尝试运行该文件。</span><span class="sxs-lookup"><span data-stu-id="94ae8-142">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a machine in your organization attempts to run it.</span></span>

<span data-ttu-id="94ae8-143">由指示器自动阻止的文件不会显示在文件的"操作中心"中，但警报仍显示在警报队列中。</span><span class="sxs-lookup"><span data-stu-id="94ae8-143">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>


## <a name="related-topics"></a><span data-ttu-id="94ae8-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="94ae8-144">Related topics</span></span>
- [<span data-ttu-id="94ae8-145">创建指示器</span><span class="sxs-lookup"><span data-stu-id="94ae8-145">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="94ae8-146">为 IP 和 URL/域创建指示器</span><span class="sxs-lookup"><span data-stu-id="94ae8-146">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="94ae8-147">创建基于证书的指示器</span><span class="sxs-lookup"><span data-stu-id="94ae8-147">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="94ae8-148">管理指示器</span><span class="sxs-lookup"><span data-stu-id="94ae8-148">Manage indicators</span></span>](indicator-manage.md)
