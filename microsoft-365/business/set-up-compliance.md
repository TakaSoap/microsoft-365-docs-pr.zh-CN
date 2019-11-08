---
title: 为 Microsoft 365 商业版增加威胁防护
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
description: 设置合规性功能，以防止数据丢失并为敏感数据添加标签。
ms.openlocfilehash: 5213c55f4a8ce0e223896f1b960847714d6d06cb
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031407"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="a46d1-103">设置合规性功能</span><span class="sxs-lookup"><span data-stu-id="a46d1-103">Set up compliance features</span></span>

<span data-ttu-id="a46d1-104">你的 Microsoft 365 业务提供了保护数据和设备的功能，并帮助您保护您的用户和客户的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="a46d1-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="a46d1-105">设置 DLP 功能</span><span class="sxs-lookup"><span data-stu-id="a46d1-105">Set up DLP features</span></span>

<span data-ttu-id="a46d1-106">有关如何设置策略以防止个人身份信息（PII）的示例，请参阅[从模板创建 DLP 策略](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)。</span><span class="sxs-lookup"><span data-stu-id="a46d1-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="a46d1-107">DLP 提供了许多不同区域设置的多种可供使用的策略模板。</span><span class="sxs-lookup"><span data-stu-id="a46d1-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="a46d1-108">例如，澳大利亚财务数据、加拿大个人信息法案、美国财务数据等。有关完整列表，请参阅[DLP 策略模板包含的内容](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)。</span><span class="sxs-lookup"><span data-stu-id="a46d1-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="a46d1-109">所有这些模板都可以像 PII 模板示例一样启用。</span><span class="sxs-lookup"><span data-stu-id="a46d1-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="a46d1-110">使用 Exchange Online 存档设置电子邮件保留</span><span class="sxs-lookup"><span data-stu-id="a46d1-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="a46d1-111">**Exchange Online 存档**许可证功能通过保留电子数据展示的电子邮件内容来帮助维护合规性和法规标准。</span><span class="sxs-lookup"><span data-stu-id="a46d1-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="a46d1-112">它还有助于在 lawsuit 事件中降低风险，并提供了在安全破坏后或需要恢复已删除项目的情况下恢复数据的方法。</span><span class="sxs-lookup"><span data-stu-id="a46d1-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="a46d1-113">您可以使用诉讼保留来保留用户的所有内容，或使用保留策略来自定义要保留的内容。</span><span class="sxs-lookup"><span data-stu-id="a46d1-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="a46d1-114">**诉讼保留：** 通过将用户的整个邮箱置于诉讼保留中，可以保留所有邮箱内容（包括已删除项目）。</span><span class="sxs-lookup"><span data-stu-id="a46d1-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="a46d1-115">若要将邮箱置于诉讼保留状态，请在管理中心：</span><span class="sxs-lookup"><span data-stu-id="a46d1-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="a46d1-116">在左侧导航中，转到 "**用户** \> **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="a46d1-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="a46d1-117">选择要将其邮箱置于诉讼保留状态的用户，并在用户窗格中展开 "**邮件设置**"，然后选择 "**其他设置**" 旁边的 "**编辑 Exchange 属性**"。</span><span class="sxs-lookup"><span data-stu-id="a46d1-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="a46d1-118">在用户的 "邮箱" 页上，在左侧导航中选择 "\* \* 邮箱功能 \* \*"，然后选择 "**诉讼保留**" 下的 "**启用**" 链接。</span><span class="sxs-lookup"><span data-stu-id="a46d1-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="a46d1-119">在 "**诉讼保留**" 对话框中，您可以在 "**诉讼保留持续时间**" 字段中指定诉讼保留期，如果您想要设置无限保留，则将字段留空。</span><span class="sxs-lookup"><span data-stu-id="a46d1-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="a46d1-120">您还可以添加注释，并将邮箱所有者引导到网站，您可能需要详细了解诉讼保留\> **保存**。</span><span class="sxs-lookup"><span data-stu-id="a46d1-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="a46d1-121">**保留：** 您可以启用自定义保留策略，例如，在保留期结束时保留特定时间或永久删除内容。</span><span class="sxs-lookup"><span data-stu-id="a46d1-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="a46d1-122">若要了解详细信息，请参阅[保留策略概述](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)。</span><span class="sxs-lookup"><span data-stu-id="a46d1-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="a46d1-123">设置敏感度标签</span><span class="sxs-lookup"><span data-stu-id="a46d1-123">Set up Sensitivity labels</span></span>

<span data-ttu-id="a46d1-124">敏感度标签随附有 Azure 信息保护（AIP）计划1，并通过应用标签帮助您分类和（可选）保护文档和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a46d1-124">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="a46d1-125">可以由管理员自动应用标签，这些管理员定义规则和条件、手动按用户或通过使用用户提供建议的组合。</span><span class="sxs-lookup"><span data-stu-id="a46d1-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="a46d1-126">若要设置敏感度标签，请查看[创建和管理敏感度标签](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)视频。</span><span class="sxs-lookup"><span data-stu-id="a46d1-126">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="a46d1-127">手动安装 Azure 信息保护客户端</span><span class="sxs-lookup"><span data-stu-id="a46d1-127">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="a46d1-128">若要手动安装 AIP 客户端：</span><span class="sxs-lookup"><span data-stu-id="a46d1-128">To manually install the AIP client:</span></span>

1. <span data-ttu-id="a46d1-129">从[Microsoft 下载中心](https://www.microsoft.com/download/details.aspx?id=53018)下载**AzinfoProtection_UL** 。</span><span class="sxs-lookup"><span data-stu-id="a46d1-129">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="a46d1-130">您可以通过查看 Word 文档，并确保 "**开始**" 选项卡上的 "**敏感度**" 选项可用来验证安装是否正常进行。</span><span class="sxs-lookup"><span data-stu-id="a46d1-130">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="a46d1-131">![Word 文档中的 "保护" 选项卡下拉箭头。](media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="a46d1-131">![Protection tab drop-down in a Word document.](media/word-sensitivity.png)</span></span>

<span data-ttu-id="a46d1-132">有关详细信息，请参阅[安装客户端](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)。</span><span class="sxs-lookup"><span data-stu-id="a46d1-132">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
