---
title: 管理自动化文件上载
description: 启用内容分析并配置将提交进行分析的文件扩展名和电子邮件附件扩展名
keywords: 自动化， 文件， 上传， 内容， 分析， 文件， 扩展名， 电子邮件， 附件
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
ms.openlocfilehash: 72405ad7500bf5d672f66ea64634e60c29ad1704
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056611"
---
# <a name="manage-automation-file-uploads"></a><span data-ttu-id="2cd1b-104">管理自动化文件上载</span><span class="sxs-lookup"><span data-stu-id="2cd1b-104">Manage automation file uploads</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2cd1b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2cd1b-105">**Applies to:**</span></span>
- [<span data-ttu-id="2cd1b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2cd1b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="2cd1b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2cd1b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2cd1b-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="2cd1b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2cd1b-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="2cd1b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

<span data-ttu-id="2cd1b-110">启用内容分析功能，以便某些文件和电子邮件附件可以自动上载到云，以便自动调查进行其他检查。</span><span class="sxs-lookup"><span data-stu-id="2cd1b-110">Enable the content analysis capability so that certain files and email attachments can automatically be uploaded to the cloud for additional inspection in Automated investigation.</span></span>

<span data-ttu-id="2cd1b-111">通过指定文件扩展名和电子邮件附件扩展名来标识文件和电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="2cd1b-111">Identify the files and email attachments by specifying the file extension names and email attachment extension names.</span></span> 

<span data-ttu-id="2cd1b-112">例如，如果将 *exe* 和 *bat* 添加为文件或附件扩展名，则具有这些扩展名的所有文件或附件将自动发送到云，以在自动调查期间进行其他检查。</span><span class="sxs-lookup"><span data-stu-id="2cd1b-112">For example, if you add *exe* and *bat* as file or attachment extension names, then all files or attachments with those extensions will automatically be sent to the cloud for additional inspection during Automated investigation.</span></span> 

## <a name="add-file-extension-names-and-attachment-extension-names"></a><span data-ttu-id="2cd1b-113">添加文件扩展名和附件扩展名。</span><span class="sxs-lookup"><span data-stu-id="2cd1b-113">Add file extension names and attachment extension names.</span></span>

1. <span data-ttu-id="2cd1b-114">在导航窗格中，选择"**设置**  >  **""自动化文件上载"。**</span><span class="sxs-lookup"><span data-stu-id="2cd1b-114">In the navigation pane, select **Settings** > **Automation file uploads**.</span></span> 

2. <span data-ttu-id="2cd1b-115">在开和 **关之间切换** 内容分析 **设置**。</span><span class="sxs-lookup"><span data-stu-id="2cd1b-115">Toggle the content analysis setting between **On** and **Off**.</span></span>

3. <span data-ttu-id="2cd1b-116">使用逗号配置以下扩展名和单独的扩展名：</span><span class="sxs-lookup"><span data-stu-id="2cd1b-116">Configure the following extension names and separate extension names with a comma:</span></span>
   - <span data-ttu-id="2cd1b-117">**文件扩展名** 名称 - 将提交除电子邮件附件以外的可疑文件进行其他检查</span><span class="sxs-lookup"><span data-stu-id="2cd1b-117">**File extension names** -  Suspicious files except email attachments will be submitted for additional inspection</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="2cd1b-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="2cd1b-118">Related topics</span></span>
- [<span data-ttu-id="2cd1b-119">管理自动化文件夹排除项</span><span class="sxs-lookup"><span data-stu-id="2cd1b-119">Manage automation folder exclusions</span></span>](manage-automation-folder-exclusions.md)
