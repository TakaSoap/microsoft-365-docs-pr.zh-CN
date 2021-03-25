---
title: 创建基于证书的指示器
ms.reviewer: ''
description: 根据定义实体的检测、防范和排除的证书创建指示器。
keywords: ioc， 证书， 证书， 管理， 允许， 阻止， 阻止， 清理， 恶意， 文件哈希， ip 地址， url， 域
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
ms.openlocfilehash: 8cf611e38bc781c2302f70f6491bb827410235b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164677"
---
# <a name="create-indicators-based-on-certificates"></a><span data-ttu-id="da197-104">创建基于证书的指示器</span><span class="sxs-lookup"><span data-stu-id="da197-104">Create indicators based on certificates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="da197-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="da197-105">**Applies to:**</span></span>
- [<span data-ttu-id="da197-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="da197-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="da197-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="da197-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="da197-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="da197-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="da197-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="da197-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="da197-110">你可以为证书创建指示器。</span><span class="sxs-lookup"><span data-stu-id="da197-110">You can create indicators for certificates.</span></span> <span data-ttu-id="da197-111">一些常见用例包括：</span><span class="sxs-lookup"><span data-stu-id="da197-111">Some common use cases include:</span></span>

- <span data-ttu-id="da197-112">当你需要部署阻止技术（如攻击面减少规则和受控文件夹[](attack-surface-reduction.md)访问权限）但需要允许[](controlled-folders.md)已签名应用程序的行为时，需要在允许列表中添加证书。</span><span class="sxs-lookup"><span data-stu-id="da197-112">Scenarios when you need to deploy blocking technologies, such as [attack surface reduction rules](attack-surface-reduction.md) and [controlled folder access](controlled-folders.md) but need to allow behaviors from signed applications by adding the certificate in the allow list.</span></span>
- <span data-ttu-id="da197-113">阻止在整个组织中使用特定的已签名应用程序。</span><span class="sxs-lookup"><span data-stu-id="da197-113">Blocking the use of a specific signed application across your organization.</span></span> <span data-ttu-id="da197-114">通过创建用于阻止应用程序证书的指示器，Windows Defender AV 将阻止文件执行 (并修正) 自动调查和修正的行为相同。</span><span class="sxs-lookup"><span data-stu-id="da197-114">By creating an indicator to block the certificate of the application, Windows Defender AV will prevent file executions (block and remediate) and the Automated Investigation and Remediation behave the same.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="da197-115">准备工作</span><span class="sxs-lookup"><span data-stu-id="da197-115">Before you begin</span></span>

<span data-ttu-id="da197-116">在创建证书指示器之前，了解以下要求很重要：</span><span class="sxs-lookup"><span data-stu-id="da197-116">It's important to understand the following requirements prior to creating indicators for certificates:</span></span>

- <span data-ttu-id="da197-117">如果你的组织使用防病毒和基于云的Windows Defender，此功能可用。</span><span class="sxs-lookup"><span data-stu-id="da197-117">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="da197-118">有关详细信息，请参阅 [管理基于云的保护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="da197-118">For more information, see [Manage cloud-based protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="da197-119">反恶意软件客户端版本必须为 4.18.1901.x 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="da197-119">The Antimalware client version must be  4.18.1901.x or later.</span></span>
- <span data-ttu-id="da197-120">在 Windows 10 版本 1703 或更高版本、Windows Server 2016 和 2019 上的计算机上受支持。</span><span class="sxs-lookup"><span data-stu-id="da197-120">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="da197-121">病毒和威胁防护定义必须最新的。</span><span class="sxs-lookup"><span data-stu-id="da197-121">The virus and threat protection definitions must be up to date.</span></span>
- <span data-ttu-id="da197-122">此功能当前支持输入 。CER 或 。PEM 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="da197-122">This feature currently supports entering .CER or .PEM file extensions.</span></span>

>[!IMPORTANT]
> - <span data-ttu-id="da197-123">有效的叶证书是具有有效证书路径的签名证书，必须链接至 Microsoft 信任的 (CA) 根证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="da197-123">A valid leaf certificate is a signing certificate that has a valid certification path and must be chained to the Root Certificate Authority (CA) trusted by Microsoft.</span></span>  <span data-ttu-id="da197-124">或者，只要自定义 (自签名) 证书受客户端信任 (根 CA 证书安装在本地计算机"受信任的根证书颁发机构") 下。</span><span class="sxs-lookup"><span data-stu-id="da197-124">Alternatively, a custom (self-signed) certificate can be used as long as it's trusted by the client (Root CA certificate is installed under the Local Machine 'Trusted Root Certification Authorities').</span></span>
>- <span data-ttu-id="da197-125">允许/阻止证书 IOC 的子级或父级不包括在允许/阻止 IoC 功能中，仅支持叶证书。</span><span class="sxs-lookup"><span data-stu-id="da197-125">The children or parent of the allow/block certificate IOCs are not included in the allow/block IoC functionality, only leaf certificates are supported.</span></span>
>- <span data-ttu-id="da197-126">无法阻止 Microsoft 签名的证书。</span><span class="sxs-lookup"><span data-stu-id="da197-126">Microsoft signed certificates cannot be blocked.</span></span>

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a><span data-ttu-id="da197-127">从设置页面创建证书指示器：</span><span class="sxs-lookup"><span data-stu-id="da197-127">Create an indicator for certificates from the settings page:</span></span>

>[!IMPORTANT]
> <span data-ttu-id="da197-128">创建和删除证书 IoC 可能需要 3 小时。</span><span class="sxs-lookup"><span data-stu-id="da197-128">It can take up to 3 hours to create and remove a certificate IoC.</span></span>

1. <span data-ttu-id="da197-129">在导航窗格中，选择"**设置**  >  **""指示器"。**</span><span class="sxs-lookup"><span data-stu-id="da197-129">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="da197-130">选择" **证书"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="da197-130">Select the **Certificate** tab.</span></span>

3. <span data-ttu-id="da197-131">选择 **"添加指示器"。**</span><span class="sxs-lookup"><span data-stu-id="da197-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="da197-132">指定以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="da197-132">Specify the following details:</span></span>
   - <span data-ttu-id="da197-133">Indicator - 指定实体详细信息并定义指示器的过期时间。</span><span class="sxs-lookup"><span data-stu-id="da197-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="da197-134">操作 - 指定要采取的操作并提供说明。</span><span class="sxs-lookup"><span data-stu-id="da197-134">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="da197-135">Scope - 定义计算机组的范围。</span><span class="sxs-lookup"><span data-stu-id="da197-135">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="da197-136">查看"摘要"选项卡中的详细信息，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="da197-136">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="da197-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="da197-137">Related topics</span></span>
- [<span data-ttu-id="da197-138">创建指示器</span><span class="sxs-lookup"><span data-stu-id="da197-138">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="da197-139">创建文件指示器</span><span class="sxs-lookup"><span data-stu-id="da197-139">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="da197-140">为 IP 和 URL/域创建指示器</span><span class="sxs-lookup"><span data-stu-id="da197-140">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="da197-141">管理指示器</span><span class="sxs-lookup"><span data-stu-id="da197-141">Manage indicators</span></span>](indicator-manage.md)
