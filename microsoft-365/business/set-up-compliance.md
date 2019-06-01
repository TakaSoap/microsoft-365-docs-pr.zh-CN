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
search.appverid:
- BCS160
- MET150
description: 设置 Office 365 高级威胁防护, 并保护敏感数据。
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668375"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="5d5f9-103">设置合规性功能</span><span class="sxs-lookup"><span data-stu-id="5d5f9-103">Set up compliance features</span></span>

<span data-ttu-id="5d5f9-104">你的 Microsoft 365 业务提供了保护数据和设备的功能, 并帮助您保护您的用户和客户的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="5d5f9-105">设置 DLP 功能</span><span class="sxs-lookup"><span data-stu-id="5d5f9-105">Set up DLP features</span></span>

<span data-ttu-id="5d5f9-106">有关如何设置策略以防止个人身份信息 (PII) 的示例, 请参阅[从模板创建 DLP 策略](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="5d5f9-107">DLP 提供了许多不同区域设置的多种可供使用的策略模板。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="5d5f9-108">例如, 澳大利亚财务数据、加拿大个人信息法案、美国财务数据等。有关完整列表, 请参阅[DLP 策略模板包含的内容](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="5d5f9-109">所有这些模板都可以像 PII 模板示例一样启用。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="5d5f9-110">使用 Exchange Online 存档设置电子邮件保留</span><span class="sxs-lookup"><span data-stu-id="5d5f9-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="5d5f9-111">**Exchange Online 存档**许可证功能通过保留电子数据展示的电子邮件内容来帮助维护合规性和法规标准。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="5d5f9-112">它还有助于在 lawsuit 事件中降低风险, 并提供了在安全破坏后或需要恢复已删除项目的情况下恢复数据的方法。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="5d5f9-113">您可以使用诉讼保留来保留用户的所有内容, 或使用保留策略来自定义要保留的内容。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="5d5f9-114">**诉讼保留:** 通过将用户的整个邮箱置于诉讼保留中, 可以保留所有邮箱内容 (包括已删除项目)。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="5d5f9-115">若要将邮箱置于诉讼保留状态, 请在管理中心:</span><span class="sxs-lookup"><span data-stu-id="5d5f9-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="5d5f9-116">在左侧导航中, 转到 "**用户** \> **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="5d5f9-117">选择要将其邮箱置于诉讼保留状态的用户, 并在用户窗格中展开 "**邮件设置**", 然后选择 "**其他设置**" 旁边的 "**编辑 Exchange 属性**"。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="5d5f9-118">在用户的 "邮箱" 页上, 在左侧导航中选择 "\* \* 邮箱功能 \* \*", 然后选择 "**诉讼保留**" 下的 "**启用**" 链接。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="5d5f9-119">在 "**诉讼保留**" 对话框中, 您可以在 "**诉讼保留持续时间**" 字段中指定诉讼保留期, 如果您想要设置无限保留, 则将字段留空。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="5d5f9-120">您还可以添加注释, 并将邮箱所有者引导到网站, 您可能需要详细了解诉讼保留\> **保存**。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="5d5f9-121">**保留:** 您可以启用自定义保留策略, 例如, 在保留期结束时保留特定时间或永久删除内容。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="5d5f9-122">若要了解详细信息, 请参阅[保留策略概述](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-azure-information-protection-features"></a><span data-ttu-id="5d5f9-123">设置 Azure 信息保护功能</span><span class="sxs-lookup"><span data-stu-id="5d5f9-123">Set up Azure Information Protection features</span></span>

<span data-ttu-id="5d5f9-124">Azure 信息保护 (AIP) 通过应用标签帮助您分类和 (可选) 保护文档和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-124">Azure Information Protection (AIP) helps you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="5d5f9-125">可以由管理员自动应用标签, 这些管理员定义规则和条件、手动按用户或通过使用用户提供建议的组合。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="5d5f9-126">在 web 上的 Outlook 中, 您可以将以下内置标签和限制应用于您的电子邮件:</span><span class="sxs-lookup"><span data-stu-id="5d5f9-126">In Outlook on the web you can apply the following built-in labels and restrictions to your emails:</span></span>
  
- <span data-ttu-id="5d5f9-127">**不转发**: 收件人可以阅读邮件, 但不能转发、打印或复制内容</span><span class="sxs-lookup"><span data-stu-id="5d5f9-127">**Do Not Forward**: Recipients can read the message, but they can't forward, print, or copy content</span></span>
    
- <span data-ttu-id="5d5f9-128">**加密**: 对整个邮件进行加密。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-128">**Encrypt**: The entire message is encrypted.</span></span> <span data-ttu-id="5d5f9-129">收件人在访问加密内容之前必须确认其标识, 并且无法删除加密。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-129">Recipients must confirm their identity before accessing encrypted content and can't remove encryption.</span></span>
    
- <span data-ttu-id="5d5f9-130">**机密**: 为组织中的员工提供对电子邮件内容和附件的完全权限, 但不授予组织外部的人员。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-130">**Confidential**: Gives the employees in your organization full permissions to the email content and attachments, but not to people outside your organization.</span></span> <span data-ttu-id="5d5f9-131">数据所有者可以随时跟踪和撤消内容。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-131">Data owners can track and revoke content at any point.</span></span>
    
- <span data-ttu-id="5d5f9-132">**高度机密**: 此限制可应用于高度机密数据, 允许员工查看、编辑和回复, 但不能转发、打印或复制数据。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-132">**Highly Confidential**: This restriction can be applied to highly confidential data, allowing employees to view, edit, and reply, but not forward, print, or copy the data.</span></span> <span data-ttu-id="5d5f9-133">数据所有者可以随时跟踪和撤消内容。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-133">Data owners can track and revoke content at any point.</span></span>

### <a name="make-sure-azure-information-protection-is-activated"></a><span data-ttu-id="5d5f9-134">请确保已激活 Azure 信息保护</span><span class="sxs-lookup"><span data-stu-id="5d5f9-134">Make sure Azure Information Protection is activated</span></span>

<span data-ttu-id="5d5f9-135">若要验证是否已激活 AIP, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="5d5f9-135">To verify that AIP is activated :</span></span>

1. <span data-ttu-id="5d5f9-136">登录到[Azure 门户](https://portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-136">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="5d5f9-137">选择 "**所有服务**", 并在 "**搜索" 框**中键入*Azure 信息保护*。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-137">Select **All services** and type in *Azure Information Protection* in the **Search Box**.</span></span>

3. <span data-ttu-id="5d5f9-138">显示结果后, 单击 " **Azure 信息保护**" 旁边的 "开始", 使其成为收藏且易于查找。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-138">Once the results display, click the start next to **Azure Information Protection** to make it a favorite and easy to find later.</span></span>

4. <span data-ttu-id="5d5f9-139">选择 " **Azure 信息保护** \> **激活**", 并确保将 "状态" 设置为 "已激活"。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-139">Select **Azure Information Protection** \> **Protection activation** and make sure the status is set to activated.</span></span> 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a><span data-ttu-id="5d5f9-140">查看 Azure 信息保护策略和默认标签</span><span class="sxs-lookup"><span data-stu-id="5d5f9-140">View the Azure Information Protection policy and default labels</span></span> 

<span data-ttu-id="5d5f9-141">若要查看和修改现有标签, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="5d5f9-141">To view, and modify, the existing labels:</span></span>

1. <span data-ttu-id="5d5f9-142">在 "Azure 信息保护" 仪表板中, 选择 "**分类** \> **标签**"。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-142">On the Azure Information Protection dashboard, select **Classifications** \> **Labels**.</span></span> <br/><span data-ttu-id="5d5f9-143">![用于 Azure 信息保护的标准标签。](media/AIPLabels.png)</span><span class="sxs-lookup"><span data-stu-id="5d5f9-143">![Standard labels for Azure Information Protection.](media/AIPLabels.png)</span></span>

2. <span data-ttu-id="5d5f9-144">您可以选择任何标签以查看选项, 您可以更改显示名称、颜色等。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-144">You can choose any label to view options, you can change the display name, colors, etc.</span></span>
 
3. <span data-ttu-id="5d5f9-145">若要创建自己的[标签, 请参阅修改和创建新标签](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2)。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-145">See  [Modify and create new labels](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) if you want to create your own.</span></span> 

### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="5d5f9-146">手动安装 Azure 信息保护客户端</span><span class="sxs-lookup"><span data-stu-id="5d5f9-146">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="5d5f9-147">若要手动安装 AIP 客户端:</span><span class="sxs-lookup"><span data-stu-id="5d5f9-147">To manually install the AIP client:</span></span>

1. <span data-ttu-id="5d5f9-148">从[Microsoft 下载中心](https://www.microsoft.com/download/details.aspx?id=53018)下载**azinfoprotection.exe** 。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-148">Download **AzInfoProtection.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="5d5f9-149">您可以通过查看 Word 文档并确保 "**主页**" 选项卡上的 "**保护**" 选项可用来验证安装是否正常。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-149">You can verify that the installation worked by viewing a Word document and making sure that the **Protect** option is available on the **Home** tab.</span></span> <br/><span data-ttu-id="5d5f9-150">![Word 文档中的 "保护" 选项卡下拉箭头。](media/Word_Protect.png)</span><span class="sxs-lookup"><span data-stu-id="5d5f9-150">![Protection tab drop-down in a Word document.](media/Word_Protect.png)</span></span>

<span data-ttu-id="5d5f9-151">有关详细信息, 请参阅[安装客户端](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)。</span><span class="sxs-lookup"><span data-stu-id="5d5f9-151">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
