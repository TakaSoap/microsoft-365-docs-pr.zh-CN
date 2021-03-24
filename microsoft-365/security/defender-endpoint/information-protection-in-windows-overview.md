---
title: Windows 中的信息保护概述
ms.reviewer: ''
description: 了解 Windows 中信息保护如何识别和保护敏感信息
keywords: 信息， 保护， dlp， 数据， 丢失， 防护， 保护
search.product: eADQiWindows 10XVcnh
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6d8f76786d4ee0bb96221d765bc1c3de0523c391
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055847"
---
# <a name="information-protection-in-windows-overview"></a><span data-ttu-id="ddbce-104">Windows 中的信息保护概述</span><span class="sxs-lookup"><span data-stu-id="ddbce-104">Information protection in Windows overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ddbce-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ddbce-105">**Applies to:**</span></span>

- [<span data-ttu-id="ddbce-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ddbce-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="ddbce-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ddbce-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ddbce-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="ddbce-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ddbce-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="ddbce-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="ddbce-110">信息保护是 Microsoft 365 企业版套件的组成部分，可提供智能保护，在保证敏感数据安全的同时在工作场所中提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="ddbce-110">Information protection is an integral part of Microsoft 365 Enterprise suite, providing intelligent protection to keep sensitive data secure while enabling productivity in the workplace.</span></span>


>[!TIP]
> <span data-ttu-id="ddbce-111">阅读我们的博客文章，了解如何 [将 Microsoft Defender ATP](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/)与 Microsoft 信息保护集成，以发现、保护和监视 Windows 设备上敏感数据。</span><span class="sxs-lookup"><span data-stu-id="ddbce-111">Read our blog post about how [Microsoft Defender ATP integrates with Microsoft Information Protection to discover, protect, and monitor sensitive data on Windows devices](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/).</span></span>

<span data-ttu-id="ddbce-112">Defender for Endpoint 应用以下方法来发现、分类和保护数据：</span><span class="sxs-lookup"><span data-stu-id="ddbce-112">Defender for Endpoint applies the following methods to discover, classify, and protect data:</span></span>

- <span data-ttu-id="ddbce-113">**数据发现** - 识别 Windows 设备上存在风险的敏感数据</span><span class="sxs-lookup"><span data-stu-id="ddbce-113">**Data discovery** - Identify sensitive data on Windows devices at risk</span></span>
- <span data-ttu-id="ddbce-114">**数据分类** - 根据 Office 365 安全与合规中心 (管理) Microsoft 信息保护& MIP 策略对数据进行自动分类。</span><span class="sxs-lookup"><span data-stu-id="ddbce-114">**Data classification** - Automatically classify data based on common Microsoft Information Protection (MIP) policies managed in Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="ddbce-115">自动分类允许你保护敏感数据，即使最终用户尚未手动分类它。</span><span class="sxs-lookup"><span data-stu-id="ddbce-115">Auto-classification allows you to protect sensitive data even if the end user hasn’t manually classified it.</span></span>


## <a name="data-discovery-and-data-classification"></a><span data-ttu-id="ddbce-116">数据发现和数据分类</span><span class="sxs-lookup"><span data-stu-id="ddbce-116">Data discovery and data classification</span></span>

<span data-ttu-id="ddbce-117">Defender for Endpoint 自动发现具有敏感度标签的文件和包含敏感信息类型的文件。</span><span class="sxs-lookup"><span data-stu-id="ddbce-117">Defender for Endpoint automatically discovers files with sensitivity labels and files that contain sensitive information types.</span></span>

<span data-ttu-id="ddbce-118">敏感度标签分类并帮助保护敏感内容。</span><span class="sxs-lookup"><span data-stu-id="ddbce-118">Sensitivity labels classify and help protect sensitive content.</span></span>

<span data-ttu-id="ddbce-119">DLP 策略实施中的 Office 365 数据丢失防护 (类型) 两类：</span><span class="sxs-lookup"><span data-stu-id="ddbce-119">Sensitive information types in the Office 365 data loss prevention (DLP) implementation fall under two categories:</span></span>

- <span data-ttu-id="ddbce-120">默认</span><span class="sxs-lookup"><span data-stu-id="ddbce-120">Default</span></span>
- <span data-ttu-id="ddbce-121">自定义警报</span><span class="sxs-lookup"><span data-stu-id="ddbce-121">Custom</span></span>

<span data-ttu-id="ddbce-122">默认敏感信息类型包括诸如银行帐号、社会保险号或国家/市/市/区号等信息。</span><span class="sxs-lookup"><span data-stu-id="ddbce-122">Default sensitive information types include information such as bank account numbers, social security numbers, or national IDs.</span></span> <span data-ttu-id="ddbce-123">有关详细信息，请参阅 [敏感信息类型查找什么](https://docs.microsoft.com/office365/securitycompliance/what-the-sensitive-information-types-look-for)。</span><span class="sxs-lookup"><span data-stu-id="ddbce-123">For more information, see [What the sensitive information type look for](https://docs.microsoft.com/office365/securitycompliance/what-the-sensitive-information-types-look-for).</span></span>

<span data-ttu-id="ddbce-124">自定义类型是您定义的类型，旨在保护不同类型的敏感信息，例如 (，例如员工 ID 或项目) 。</span><span class="sxs-lookup"><span data-stu-id="ddbce-124">Custom types are ones that you define and is designed to protect a different type of sensitive information (for example, employee IDs or project numbers).</span></span> <span data-ttu-id="ddbce-125">有关详细信息，请参阅创建自定义 [敏感信息类型](https://docs.microsoft.com/office365/securitycompliance/create-a-custom-sensitive-information-type)。</span><span class="sxs-lookup"><span data-stu-id="ddbce-125">For more information see, [Create a custom sensitive information type](https://docs.microsoft.com/office365/securitycompliance/create-a-custom-sensitive-information-type).</span></span>

<span data-ttu-id="ddbce-126">在 Windows 设备上创建或编辑文件时，Defender for Endpoint 会扫描内容以评估是否包含敏感信息。</span><span class="sxs-lookup"><span data-stu-id="ddbce-126">When a file is created or edited on a  Windows device, Defender for Endpoint scans the content to evaluate if it contains sensitive information.</span></span>

<span data-ttu-id="ddbce-127">启用 Azure 信息保护集成，以便当 Defender for Endpoint 通过标签或信息类型发现包含敏感信息的文件时，该文件会自动从设备转发到 Azure 信息保护。</span><span class="sxs-lookup"><span data-stu-id="ddbce-127">Turn on the Azure Information Protection integration so that when a file that contains sensitive information is discovered by Defender for Endpoint though labels or information types, it is automatically forwarded to Azure Information Protection from the device.</span></span>

![使用 Azure 信息保护的设置页面的图像](images/atp-settings-aip.png)

<span data-ttu-id="ddbce-129">报告的信号可以在 Azure 信息保护 – 数据发现仪表板上查看。</span><span class="sxs-lookup"><span data-stu-id="ddbce-129">The reported signals can be viewed on the Azure Information Protection – Data discovery dashboard.</span></span>

## <a name="azure-information-protection---data-discovery-dashboard"></a><span data-ttu-id="ddbce-130">Azure 信息保护 - 数据发现仪表板</span><span class="sxs-lookup"><span data-stu-id="ddbce-130">Azure Information Protection - Data discovery dashboard</span></span>

<span data-ttu-id="ddbce-131">此仪表板显示 Defender for Endpoint 和 Azure 信息保护发现的数据的汇总发现信息。</span><span class="sxs-lookup"><span data-stu-id="ddbce-131">This dashboard presents a summarized discovery information of data discovered by both Defender for Endpoint and Azure Information Protection.</span></span> <span data-ttu-id="ddbce-132">来自 Defender for Endpoint 的数据标记为"位置类型 - 终结点"。</span><span class="sxs-lookup"><span data-stu-id="ddbce-132">Data from Defender for Endpoint is marked with Location Type - Endpoint.</span></span>

![Azure 信息保护的图像 - 数据发现](images/azure-data-discovery.png)

<span data-ttu-id="ddbce-134">请注意右侧"设备风险"列，此设备风险直接派生自 Defender for Endpoint，指示发现文件的安全设备的风险级别，基于 Defender for Endpoint 检测到的活动安全威胁。</span><span class="sxs-lookup"><span data-stu-id="ddbce-134">Notice the Device Risk column on the right, this device risk is derived directly from Defender for Endpoint, indicating the risk level of the security device where the file was discovered, based on the active security threats detected by Defender for Endpoint.</span></span>

<span data-ttu-id="ddbce-135">单击设备以查看在此设备上观测到的文件列表，及其敏感度标签和信息类型。</span><span class="sxs-lookup"><span data-stu-id="ddbce-135">Click on a device to view a list of files observed on this device, with their sensitivity labels and information types.</span></span>

>[!NOTE]
><span data-ttu-id="ddbce-136">请允许 Azure 信息保护仪表板发现大约 15-20 分钟反映发现的文件。</span><span class="sxs-lookup"><span data-stu-id="ddbce-136">Please allow approximately 15-20 minutes for the Azure Information Protection Dashboard Discovery to reflect discovered files.</span></span>

## <a name="log-analytics"></a><span data-ttu-id="ddbce-137">Log Analytics</span><span class="sxs-lookup"><span data-stu-id="ddbce-137">Log Analytics</span></span>

<span data-ttu-id="ddbce-138">Azure Log [Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)中也提供基于 Defender for Endpoint 的数据发现，你可以在这里对原始数据执行复杂的查询。</span><span class="sxs-lookup"><span data-stu-id="ddbce-138">Data discovery based on Defender for Endpoint is also available in [Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview), where you can perform complex queries over the raw data.</span></span>

<span data-ttu-id="ddbce-139">有关 Azure 信息保护分析详细信息，请参阅 [Azure 信息保护的中央报告](https://docs.microsoft.com/azure/information-protection/reports-aip)。</span><span class="sxs-lookup"><span data-stu-id="ddbce-139">For more information on Azure Information Protection analytics, see [Central reporting for Azure Information Protection](https://docs.microsoft.com/azure/information-protection/reports-aip).</span></span>

<span data-ttu-id="ddbce-140">在 Azure 门户中打开 Azure Log Analytics，然后打开标准 (或经典查询) 。</span><span class="sxs-lookup"><span data-stu-id="ddbce-140">Open Azure Log Analytics in Azure portal and open a query builder (standard or classic).</span></span>

<span data-ttu-id="ddbce-141">若要查看 Defender for Endpoint 数据，请执行包含以下项的查询：</span><span class="sxs-lookup"><span data-stu-id="ddbce-141">To view Defender for Endpoint data, perform a query that contains:</span></span>

```
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

<span data-ttu-id="ddbce-142">**先决条件：**</span><span class="sxs-lookup"><span data-stu-id="ddbce-142">**Prerequisites:**</span></span>

- <span data-ttu-id="ddbce-143">客户必须订阅 Azure 信息保护。</span><span class="sxs-lookup"><span data-stu-id="ddbce-143">Customers must have a subscription for Azure Information Protection.</span></span>
- <span data-ttu-id="ddbce-144">在 Microsoft Defender 安全中心中启用 Azure 信息保护集成：</span><span class="sxs-lookup"><span data-stu-id="ddbce-144">Enable Azure Information Protection integration in Microsoft Defender Security Center:</span></span>
    - <span data-ttu-id="ddbce-145">转到 **Microsoft** Defender 安全中心中的"设置"，单击"常规 **"下的"高级\*\*\*\*设置"。**</span><span class="sxs-lookup"><span data-stu-id="ddbce-145">Go to **Settings** in Microsoft Defender Security Center, click on **Advanced Settings** under **General**.</span></span>



