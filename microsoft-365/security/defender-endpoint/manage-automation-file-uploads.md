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
ms.openlocfilehash: b7d330388dd698cb524c1f4a8edaf9039ba4d16e
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454825"
---
# <a name="manage-automation-file-uploads"></a><span data-ttu-id="aaf8a-104">管理自动化文件上载</span><span class="sxs-lookup"><span data-stu-id="aaf8a-104">Manage automation file uploads</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aaf8a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="aaf8a-105">**Applies to:**</span></span>
- [<span data-ttu-id="aaf8a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="aaf8a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aaf8a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aaf8a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="aaf8a-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="aaf8a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aaf8a-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="aaf8a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

<span data-ttu-id="aaf8a-110">启用内容分析功能，以便某些文件和电子邮件附件可以自动上载到云，以便自动调查进行其他检查。</span><span class="sxs-lookup"><span data-stu-id="aaf8a-110">Enable the content analysis capability so that certain files and email attachments can automatically be uploaded to the cloud for additional inspection in Automated investigation.</span></span>

<span data-ttu-id="aaf8a-111">通过指定文件扩展名和电子邮件附件扩展名来标识文件和电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="aaf8a-111">Identify the files and email attachments by specifying the file extension names and email attachment extension names.</span></span> 

<span data-ttu-id="aaf8a-112">例如，如果将 *exe* 和 *bat* 添加为文件或附件扩展名，则具有这些扩展名的所有文件或附件将自动发送到云，以在自动调查期间进行其他检查。</span><span class="sxs-lookup"><span data-stu-id="aaf8a-112">For example, if you add *exe* and *bat* as file or attachment extension names, then all files or attachments with those extensions will automatically be sent to the cloud for additional inspection during Automated investigation.</span></span> 

## <a name="add-file-extension-names-and-attachment-extension-names"></a><span data-ttu-id="aaf8a-113">添加文件扩展名和附件扩展名。</span><span class="sxs-lookup"><span data-stu-id="aaf8a-113">Add file extension names and attachment extension names.</span></span>

1. <span data-ttu-id="aaf8a-114">在导航窗格中，选择 **"设置**  >    >  **终结点规则**  >  **自动上载"。**</span><span class="sxs-lookup"><span data-stu-id="aaf8a-114">In the navigation pane, select **Settings** > **Endpoints** > **Rules** > **Automation uploads**.</span></span>

2. <span data-ttu-id="aaf8a-115">在开和 **关之间切换** 内容分析 **设置**。</span><span class="sxs-lookup"><span data-stu-id="aaf8a-115">Toggle the content analysis setting between **On** and **Off**.</span></span>

3. <span data-ttu-id="aaf8a-116">使用逗号配置以下扩展名和单独的扩展名：</span><span class="sxs-lookup"><span data-stu-id="aaf8a-116">Configure the following extension names and separate extension names with a comma:</span></span>
   - <span data-ttu-id="aaf8a-117">**文件扩展名** 名称 - 将提交除电子邮件附件以外的可疑文件进行其他检查</span><span class="sxs-lookup"><span data-stu-id="aaf8a-117">**File extension names** -  Suspicious files except email attachments will be submitted for additional inspection</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="aaf8a-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="aaf8a-118">Related topics</span></span>
- [<span data-ttu-id="aaf8a-119">管理自动化文件夹排除</span><span class="sxs-lookup"><span data-stu-id="aaf8a-119">Manage automation folder exclusions</span></span>](manage-automation-folder-exclusions.md)
