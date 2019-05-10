---
title: 为 Microsoft 365 商业版用户设置高级安全策略
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
ms.openlocfilehash: 4728e11a16fdf8a461f5687632df75699923f846
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "33663626"
---
# <a name="set-up-advanced-security-policies"></a><span data-ttu-id="93c15-103">设置高级安全策略</span><span class="sxs-lookup"><span data-stu-id="93c15-103">Set up advanced security policies</span></span>

<span data-ttu-id="93c15-104">除了可在[管理中心](security-features.md#microsoft-365-business-admin-center-security-features)中设置的策略之外, 还可以通过设置[Office 365 高级威胁防护](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)(ATP) 来添加针对网络威胁的额外保护。</span><span class="sxs-lookup"><span data-stu-id="93c15-104">In addition to the policies you can set up in the [admin center](security-features.md#microsoft-365-business-admin-center-security-features), you can add additional protection against cyber threats by setting up [Office 365 Advanced Threat Protection](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653) (ATP).</span></span> <span data-ttu-id="93c15-105">您还可以通过设置[数据丢失防护](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)(DLP)、Azure 信息保护 (AIP)、 [Exchange Online 存档](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)以及在[Intune 门户](#go-to-intune-admin-center)中管理设备来保护敏感信息。</span><span class="sxs-lookup"><span data-stu-id="93c15-105">You can also guard sensitive information by setting up [Data Loss Prevention](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) (DLP), Azure Information Protection (AIP), [Exchange Online Archiving](https://products.office.com/exchange/microsoft-exchange-online-archiving-email), and also manage your devices in the [Intune portal](#go-to-intune-admin-center).</span></span>

<span data-ttu-id="93c15-106">请参阅[前10种保护 Microsoft 365 业务计划的方法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data), 概述了保护业务的最重要方式, 包括使用 MFA 创建第二种登录窗体。</span><span class="sxs-lookup"><span data-stu-id="93c15-106">See [top 10 ways to secure Microsoft 365 Business plan](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for an overview of the most important ways in which you can protect your business, including using MFA to create a second form of sign-in.</span></span>

<span data-ttu-id="93c15-107">请参阅[保护您的业务培训视频](https://support.office.com/article/e12187b8-216a-4490-9e3b-df34a06fb787), 获取易于遵循说明的说明。</span><span class="sxs-lookup"><span data-stu-id="93c15-107">See [Secure your business training videos](https://support.office.com/article/e12187b8-216a-4490-9e3b-df34a06fb787) for instructions for easy to follow instructions.</span></span>

## <a name="increase-email-malware-protection"></a><span data-ttu-id="93c15-108">增加电子邮件恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="93c15-108">Increase email malware protection</span></span>

<span data-ttu-id="93c15-109">恶意软件是一种软件, 它可能会损坏计算机或网络, 并且可能会窃取您的数据, 包括个人或客户信息。</span><span class="sxs-lookup"><span data-stu-id="93c15-109">Malware is software that can damage your computers or network, and possibly to steal data from you, including personal or customer information.</span></span> <span data-ttu-id="93c15-110">Microsoft 365 业务包括针对恶意软件保护的基准级别, 但你可以通过设置其他设置来提高此保护。</span><span class="sxs-lookup"><span data-stu-id="93c15-110">Microsoft 365 Business includes a baseline level of protection against malware, but you can increase this protection by setting up additional settings.</span></span> <span data-ttu-id="93c15-111">有关说明, 请参阅[启用恶意软件检测](https://support.office.com/article/02b5783a-eea0-42e8-8856-62440718c3f0)培训视频。</span><span class="sxs-lookup"><span data-stu-id="93c15-111">See [turn on malware detection](https://support.office.com/article/02b5783a-eea0-42e8-8856-62440718c3f0) training video for instructions.</span></span>

## <a name="set-up-advanced-threat-protection-features"></a><span data-ttu-id="93c15-112">设置高级威胁防护功能</span><span class="sxs-lookup"><span data-stu-id="93c15-112">Set up Advanced Threat Protection features</span></span>

- <span data-ttu-id="93c15-113">防御**不安全附件:** ATP 通过在虚拟环境中打开电子邮件附件并对生成的行为进行分析来识别恶意内容。</span><span class="sxs-lookup"><span data-stu-id="93c15-113">**Protect against unsafe attachments:** ATP identifies malicious content by opening email attachments in a virtual environment and performing analysis of the resulting behavior.</span></span> <span data-ttu-id="93c15-114">对内容进行评估, 以确定其目的 (无论是正常还是恶意), ATP 会阻止传输不安全的附件, 从而帮助您抵御网络钓鱼骗术和勒索软件感染。</span><span class="sxs-lookup"><span data-stu-id="93c15-114">The content is evaluated to determine its intent (whether normal or malicious), and ATP blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections.</span></span> <span data-ttu-id="93c15-115">若要激活附件保护, 请参阅[设置 Office 365 ATP 安全附件](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775)帮助文档, 并[防止恶意文件](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)较短的培训视频。</span><span class="sxs-lookup"><span data-stu-id="93c15-115">To activate attachment protection, see [set up Office 365 ATP Safe Attachments](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775) help documentation, and [protect against malicious files](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5) short training video.</span></span>
    
- <span data-ttu-id="93c15-116">**当用户单击恶意链接时保护您的环境:** ATP 还会在用户单击时检查电子邮件中的链接。</span><span class="sxs-lookup"><span data-stu-id="93c15-116">**Protect your environment when users click malicious links:** ATP also examines links in email at the time a user clicks them.</span></span> <span data-ttu-id="93c15-117">如果链接不安全, 则会警告用户不会访问网站, 或通知用户网站已被阻止。</span><span class="sxs-lookup"><span data-stu-id="93c15-117">If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked.</span></span> <span data-ttu-id="93c15-118">这有助于防止仿冒骗术。</span><span class="sxs-lookup"><span data-stu-id="93c15-118">This helps protect against phishing schemes.</span></span> <span data-ttu-id="93c15-119">若要激活此设置, 请参阅[设置 Office 365 ATP 安全链接](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies)帮助文档, 并[防止恶意网站](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)进行简短的培训视频。</span><span class="sxs-lookup"><span data-stu-id="93c15-119">To activate this, see [set up Office 365 ATP Safe Links](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies) help documentation and [protect against malicious sites](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa) short training video.</span></span>

- <span data-ttu-id="93c15-120">**保护你的环境免受仿冒网站的攻击:** ATP 反网络钓鱼对传入的邮件应用一组计算机学习模式和模拟检测算法, 以防止有人尝试从你的网络中提取信息, 因为它通过假装成为已知信息.</span><span class="sxs-lookup"><span data-stu-id="93c15-120">**Protect your enviroment from phishing attempt:**  ATP anti-phishing applies a set of machine learning models together with impersonation detection algorithms to incoming messages to provide protection from phishing attacks where someone is trying to extract information from you by pretending to be a known contact.</span></span> <span data-ttu-id="93c15-121">若要激活此设置, 请参阅[设置 ATP 反网络钓鱼](https://docs.microsoft.com/office365/securitycompliance/set-up-anti-phishing-policies)帮助文档, 并[防止网络钓鱼尝试](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)进行简短的培训视频。</span><span class="sxs-lookup"><span data-stu-id="93c15-121">To Activate this, see [set up ATP anti-phishing](https://docs.microsoft.com/office365/securitycompliance/set-up-anti-phishing-policies) help documentation and [protect against phishing attempts](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c) short training video.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="93c15-122">设置 DLP 功能</span><span class="sxs-lookup"><span data-stu-id="93c15-122">Set up DLP features</span></span>

<span data-ttu-id="93c15-123">有关如何设置策略以防止个人身份信息 (PII) 的示例, 请参阅[从模板创建 DLP 策略](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)。</span><span class="sxs-lookup"><span data-stu-id="93c15-123">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="93c15-124">DLP 提供了许多不同区域设置的多种可供使用的策略模板。</span><span class="sxs-lookup"><span data-stu-id="93c15-124">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="93c15-125">例如, 澳大利亚财务数据、加拿大个人信息法案、美国财务数据等。有关完整列表, 请参阅[DLP 策略模板包含的内容](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)。</span><span class="sxs-lookup"><span data-stu-id="93c15-125">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="93c15-126">所有这些模板都可以像 PII 模板示例一样启用。</span><span class="sxs-lookup"><span data-stu-id="93c15-126">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="93c15-127">使用 Exchange Online 存档设置电子邮件保留</span><span class="sxs-lookup"><span data-stu-id="93c15-127">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="93c15-128">**Exchange Online 存档**许可证功能使您能够通过保留电子邮件内容以用于电子数据展示来帮助维护合规性和法规标准。</span><span class="sxs-lookup"><span data-stu-id="93c15-128">**Exchange Online Archiving** license features give you the ability to help maintain compliance and regulatory standards by preserving email content for the purposes of eDiscovery.</span></span> <span data-ttu-id="93c15-129">它还有助于在发生诉讼时降低风险, 并提供在安全破坏或需要恢复已删除项目时恢复数据的方法。</span><span class="sxs-lookup"><span data-stu-id="93c15-129">It also helps reduce your risk in the event of litigation and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="93c15-130">若要激活这些功能, 您可以使用诉讼保留来保留用户的所有内容, 或使用保留策略以进行更好的自定义。</span><span class="sxs-lookup"><span data-stu-id="93c15-130">To activate these capabilities, you can use litigation hold to preserve all of a user's content, or use retention policies for greater customization.</span></span> 
  
<span data-ttu-id="93c15-131">**诉讼保留:** 通过将用户的整个邮箱置于诉讼保留中, 可以保留所有邮箱内容 (包括已删除项目)。</span><span class="sxs-lookup"><span data-stu-id="93c15-131">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="93c15-132">若要将邮箱置于诉讼保留状态, 请在管理中心:</span><span class="sxs-lookup"><span data-stu-id="93c15-132">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="93c15-133">在左侧导航中, 转到 "**用户** \> **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="93c15-133">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="93c15-134">选择要将其邮箱置于诉讼保留状态的用户, 并在用户窗格中展开 "**邮件设置**", 然后选择 "**其他设置**" 旁边的 "**编辑 Exchange 属性**"。</span><span class="sxs-lookup"><span data-stu-id="93c15-134">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="93c15-135">在用户的 "邮箱" 页上, 在左侧导航中选择 "\* \* 邮箱功能 \* \*", 然后选择 "**诉讼保留**" 下的 "**启用**" 链接。</span><span class="sxs-lookup"><span data-stu-id="93c15-135">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="93c15-136">在 "**诉讼保留**" 对话框中, 您可以在 "**诉讼保留持续时间**" 字段中指定诉讼保留期, 如果您想要设置无限保留, 则将字段留空。</span><span class="sxs-lookup"><span data-stu-id="93c15-136">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="93c15-137">您还可以添加注释, 并将邮箱所有者引导到网站, 您可能需要详细了解诉讼保留\> **保存**。</span><span class="sxs-lookup"><span data-stu-id="93c15-137">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="93c15-138">**保留:** 您可以启用自定义保留策略, 例如, 在保留期结束时保留特定时间或永久删除内容。</span><span class="sxs-lookup"><span data-stu-id="93c15-138">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="93c15-139">若要了解详细信息, 请参阅[保留策略概述](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)。</span><span class="sxs-lookup"><span data-stu-id="93c15-139">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
## <a name="set-up-azure-information-protection-features"></a><span data-ttu-id="93c15-140">设置 Azure 信息保护功能</span><span class="sxs-lookup"><span data-stu-id="93c15-140">Set up Azure Information Protection features</span></span>

<span data-ttu-id="93c15-141">Azure 信息保护 (AIP) 是一种基于云的解决方案, 可帮助组织通过应用标签来分类和 (可选) 保护其文档和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="93c15-141">Azure Information Protection (AIP) is a cloud-based solution that helps an organization to classify and optionally, protect its documents and emails by applying labels.</span></span> <span data-ttu-id="93c15-142">可以由管理员自动应用标签, 这些管理员定义规则和条件、手动由用户手动应用或为用户提供建议的组合。</span><span class="sxs-lookup"><span data-stu-id="93c15-142">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="93c15-143">为所有用户自动启用了在 web 上的 Outlook 中发送电子邮件时应用以下限制的能力:</span><span class="sxs-lookup"><span data-stu-id="93c15-143">The ability to apply the following restrictions when sending emails in Outlook on the web is automatically enabled for all users:</span></span>
  
- <span data-ttu-id="93c15-144">**不转发**: 收件人可以阅读邮件, 但不能转发、打印或复制内容</span><span class="sxs-lookup"><span data-stu-id="93c15-144">**Do Not Forward**: Recipients can read the message, but they can't forward, print, or copy content</span></span>
    
- <span data-ttu-id="93c15-145">**加密**: 对整个邮件进行加密。</span><span class="sxs-lookup"><span data-stu-id="93c15-145">**Encrypt**: The entire message is encrypted.</span></span> <span data-ttu-id="93c15-146">收件人在访问加密内容之前, 必须执行额外的步骤来确认其标识, 并且无法删除加密。</span><span class="sxs-lookup"><span data-stu-id="93c15-146">Recipients must take extra steps to confirm their identity before accessing encrypted content and can't remove encryption.</span></span>
    
- <span data-ttu-id="93c15-147">**机密**: 为组织中的员工提供对电子邮件内容和附件的完全权限, 但不授予组织外部的人员。</span><span class="sxs-lookup"><span data-stu-id="93c15-147">**Confidential**: Gives the employees in your organization full permissions to the email content and attachments, but not to people outside your organization.</span></span> <span data-ttu-id="93c15-148">数据所有者可以随时跟踪和撤消内容。</span><span class="sxs-lookup"><span data-stu-id="93c15-148">Data owners can track and revoke content at any point.</span></span>
    
- <span data-ttu-id="93c15-149">**高度机密**: 此限制可应用于高度机密数据, 允许员工查看、编辑和回复, 但不能转发、打印或复制数据。</span><span class="sxs-lookup"><span data-stu-id="93c15-149">**Highly Confidential**: This restriction can be applied to highly confidential data, allowing employees to view, edit, and reply, but not forward, print, or copy the data.</span></span> <span data-ttu-id="93c15-150">数据所有者可以随时跟踪和撤消内容。</span><span class="sxs-lookup"><span data-stu-id="93c15-150">Data owners can track and revoke content at any point.</span></span>

### <a name="make-sure-azure-information-protection-is-activated"></a><span data-ttu-id="93c15-151">请确保已激活 Azure 信息保护</span><span class="sxs-lookup"><span data-stu-id="93c15-151">Make sure Azure Information Protection is activated</span></span>

<span data-ttu-id="93c15-152">若要验证是否已激活 AIP, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="93c15-152">To verify that AIP is activated :</span></span>

1. <span data-ttu-id="93c15-153">登录到[Azure 门户](https://portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="93c15-153">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="93c15-154">选择 "**所有服务**", 并在 "**搜索" 框**中键入*Azure 信息保护*。</span><span class="sxs-lookup"><span data-stu-id="93c15-154">Select **All services** and type in *Azure Information Protection* in the **Search Box**.</span></span>

3. <span data-ttu-id="93c15-155">显示结果后, 单击 " **Azure 信息保护**" 旁边的 "开始", 使其成为收藏且易于查找。</span><span class="sxs-lookup"><span data-stu-id="93c15-155">Once the results display, click the start next to **Azure Information Protection** to make it a favorite and easy to find later.</span></span>

4. <span data-ttu-id="93c15-156">选择 " **Azure 信息保护** \> **激活**", 并确保将 "状态" 设置为 "已激活"。</span><span class="sxs-lookup"><span data-stu-id="93c15-156">Select **Azure Information Protection** \> **Protection activation** and make sure the status is set to activated.</span></span> 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a><span data-ttu-id="93c15-157">查看 Azure 信息保护策略和默认标签</span><span class="sxs-lookup"><span data-stu-id="93c15-157">View the Azure Information Protection policy and default labels</span></span> 

<span data-ttu-id="93c15-158">若要查看和修改现有标签, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="93c15-158">To view, and modify, the existing labels:</span></span>

1. <span data-ttu-id="93c15-159">在 "Azure 信息保护" 仪表板中, 选择 "**分类** \> **标签**"。</span><span class="sxs-lookup"><span data-stu-id="93c15-159">On the Azure Information Protection dashboard, select **Classifications** \> **Labels**.</span></span> <br/><span data-ttu-id="93c15-160">![用于 Azure 信息保护的标准标签。](media/AIPLabels.png)</span><span class="sxs-lookup"><span data-stu-id="93c15-160">![Standard labels for Azure Information Protection.](media/AIPLabels.png)</span></span>

2. <span data-ttu-id="93c15-161">您可以选择任何标签以查看选项, 您可以更改显示名称、颜色等。</span><span class="sxs-lookup"><span data-stu-id="93c15-161">You can choose any label to view options, you can change the display name, colors, etc.</span></span>
 
3. <span data-ttu-id="93c15-162">若要创建自己的[标签, 请参阅修改和创建新标签](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2)。</span><span class="sxs-lookup"><span data-stu-id="93c15-162">See  [Modify and create new labels](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) if you want to create your own.</span></span> 

### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="93c15-163">手动安装 Azure 信息保护客户端</span><span class="sxs-lookup"><span data-stu-id="93c15-163">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="93c15-164">若要手动安装 AIP 客户端:</span><span class="sxs-lookup"><span data-stu-id="93c15-164">To manually install the AIP client:</span></span>

1. <span data-ttu-id="93c15-165">从[Microsoft 下载中心](https://www.microsoft.com/download/details.aspx?id=53018)下载**azinfoprotection.exe** 。</span><span class="sxs-lookup"><span data-stu-id="93c15-165">Download **AzInfoProtection.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="93c15-166">您可以通过查看 Word 文档并确保 "**主页**" 选项卡上的 "**保护**" 选项可用来验证安装是否正常。</span><span class="sxs-lookup"><span data-stu-id="93c15-166">You can verify that the installation worked by viewing a Word document and making sure that the **Protect** option is available on the **Home** tab.</span></span> <br/><span data-ttu-id="93c15-167">![Word 文档中的 "保护" 选项卡下拉箭头。](media/Word_Protect.png)</span><span class="sxs-lookup"><span data-stu-id="93c15-167">![Protection tab drop-down in a Word document.](media/Word_Protect.png)</span></span>

<span data-ttu-id="93c15-168">有关详细信息, 请参阅[安装客户端](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)。</span><span class="sxs-lookup"><span data-stu-id="93c15-168">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>

## <a name="go-to-intune-admin-center"></a><span data-ttu-id="93c15-169">转到 Intune 管理中心</span><span class="sxs-lookup"><span data-stu-id="93c15-169">Go to Intune admin center</span></span>

1. <span data-ttu-id="93c15-170">登录到[Azure 门户](https://portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="93c15-170">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="93c15-171">在 "**搜索" 框**中选择 "**所有服务**", 然后键入*Intune* 。</span><span class="sxs-lookup"><span data-stu-id="93c15-171">Select **All services** and type in *Intune* in the **Search Box**.</span></span>

3. <span data-ttu-id="93c15-172">显示结果后, 单击 " **Microsoft Intune** " 旁边的 "开始", 使其成为收藏, 以便稍后查找。</span><span class="sxs-lookup"><span data-stu-id="93c15-172">Once the results display, click the start next to **Microsoft Intune** to make it a favorite and easy to find later.</span></span>

<span data-ttu-id="93c15-173">除了管理中心之外, 你还可以使用 Intune 注册和管理你的组织的设备。</span><span class="sxs-lookup"><span data-stu-id="93c15-173">In addition to the admin center, you can use Intune to enroll and manage your organization's devices.</span></span> <span data-ttu-id="93c15-174">有关详细信息, 请参阅[Windows 设备注册方法](https://docs.microsoft.com/intune/enrollment-method-capabs)和由[Intune 管理的设备的注册选项](https://docs.microsoft.com/intune/enrollment-options)的功能。</span><span class="sxs-lookup"><span data-stu-id="93c15-174">For more information, see [Capabilities by enrollment method for Windows devices](https://docs.microsoft.com/intune/enrollment-method-capabs) and [Enrollment options for devices managed by Intune](https://docs.microsoft.com/intune/enrollment-options).</span></span>

## <a name="microsoft-secure-score"></a><span data-ttu-id="93c15-175">Microsoft 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="93c15-175">Microsoft Secure Score</span></span>

