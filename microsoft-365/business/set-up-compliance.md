---
title: 增强 Microsoft 365 商业高级版的威胁防护
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 设置合规性功能以防止数据丢失，并帮助保护你和客户敏感信息的安全。
ms.openlocfilehash: 945f8a283b90b89da2fbe67a073e0807b80d198f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245076"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="5ef9f-103">设置合规性功能</span><span class="sxs-lookup"><span data-stu-id="5ef9f-103">Set up compliance features</span></span>

<span data-ttu-id="5ef9f-104">Microsoft 365 商业高级版附带保护你的数据和设备的功能，并且可帮助你保护你和客户敏感信息的安全。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-104">Your Microsoft 365 Business Premium comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="5ef9f-105">设置 DLP 功能</span><span class="sxs-lookup"><span data-stu-id="5ef9f-105">Set up DLP features</span></span>

<span data-ttu-id="5ef9f-106">请参阅 [从模板创建 DLP](../compliance/create-a-dlp-policy-from-a-template.md) 策略，了解如何设置策略防止个人数据丢失的示例。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-106">See [Create a DLP policy from a template](../compliance/create-a-dlp-policy-from-a-template.md) for an example on how to set up a policy to protect against protect loss of personal data.</span></span> 
  
<span data-ttu-id="5ef9f-107">DLP 附带许多适用于许多不同区域设置的现成策略模板。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="5ef9f-108">例如，澳大利亚财务数据、加拿大个人信息法案、美国财务数据等。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="5ef9f-109">有关 [完整列表，请参阅 DLP](../compliance/what-the-dlp-policy-templates-include.md) 策略模板包含的内容。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-109">See [What the DLP policy templates include](../compliance/what-the-dlp-policy-templates-include.md) for a full list.</span></span> <span data-ttu-id="5ef9f-110">所有这些模板都可以启用，类似于 PII 模板示例。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="5ef9f-111">设置电子邮件保留时间Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="5ef9f-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="5ef9f-112">**Exchange Online Archiving** 许可证功能通过保留电子数据展示的电子邮件内容来帮助维护合规性和法规标准。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="5ef9f-113">它还有助于在有诉讼时降低风险，并提供一种在安全漏洞或需要恢复已删除项目时恢复数据的方法。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="5ef9f-114">您可以使用诉讼保留保留用户的所有内容，或使用保留策略自定义要保留的内容。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="5ef9f-115">**诉讼保留：** 通过将用户的整个邮箱置于诉讼保留状态，可以保留所有邮箱内容，包括已删除的项目。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="5ef9f-116">若要将邮箱置于诉讼保留状态，在管理中心：</span><span class="sxs-lookup"><span data-stu-id="5ef9f-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="5ef9f-117">在左侧导航中，转到"用户 \> **""活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="5ef9f-117">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="5ef9f-118">选择要将其邮箱置于诉讼保留状态的用户。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="5ef9f-119">在用户窗格中，展开"**邮件设置"，** 在"更多设置"**旁边**，选择"**编辑 Exchange 属性"。**</span><span class="sxs-lookup"><span data-stu-id="5ef9f-119">In the user pane, expand **Mail settings**, and next to **More settings**, choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="5ef9f-120">On the mailbox page for the user， choose \*\* mailbox features \*\* on the left nav， and then choose the **Enable** link under **Litigation hold**.</span><span class="sxs-lookup"><span data-stu-id="5ef9f-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="5ef9f-121">在 **"诉讼保留** "对话框中，您可以在"诉讼保留持续时间"字段中指定 **诉讼保留** 持续时间。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="5ef9f-122">如果希望将字段留空，请保留无限期保留。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="5ef9f-123">您还可以添加注释，将邮箱所有者引导到网站，您可能必须解释有关诉讼保留的更多内容。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="5ef9f-124">\>**保存**。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-124">\> **Save**.</span></span>
    
<span data-ttu-id="5ef9f-125">**保留：** 例如，您可以启用自定义保留策略以保留特定时间，或在保留期结束时永久删除内容。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-125">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="5ef9f-126">若要了解更多信息，请参阅 [保留策略概述](../compliance/retention.md)。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-126">To learn more, see [Overview of retention policies](../compliance/retention.md).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="5ef9f-127">设置敏感度标签</span><span class="sxs-lookup"><span data-stu-id="5ef9f-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="5ef9f-128">敏感度标签随 Azure 信息保护 (AIP) 计划 1 提供，可帮助你通过应用标签对文档和电子邮件进行分类和选择性保护。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="5ef9f-129">标签可自动由定义规则和条件的管理员应用，由用户手动应用，也可结合使用为用户提供建议。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="5ef9f-130">若要设置敏感度标签，请 [观看创建和管理敏感度标签](../business-video/create-sensitivity-labels.md) 视频。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-130">To set up Sensitivity labels, view [create and manage sensitivity labels](../business-video/create-sensitivity-labels.md) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="5ef9f-131">手动安装 Azure 信息保护客户端</span><span class="sxs-lookup"><span data-stu-id="5ef9f-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="5ef9f-132">若要手动安装 AIP 客户端，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5ef9f-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="5ef9f-133">从 **microsoftAzinfoProtection_UL.exe**[下载中心 下载文件](https://www.microsoft.com/download/details.aspx?id=53018)。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="5ef9f-134">您可以通过查看 Word 文档并确保"开始"选项卡上提供"敏感度"选项来验证安装 **是否** 有效。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="5ef9f-135">![Word 文档中的"保护"选项卡下拉列表。](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="5ef9f-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="5ef9f-136">有关详细信息，请参阅安装 [客户端](/azure/information-protection/infoprotect-tutorial-step3)。</span><span class="sxs-lookup"><span data-stu-id="5ef9f-136">For more information, see [Install the client](/azure/information-protection/infoprotect-tutorial-step3).</span></span>