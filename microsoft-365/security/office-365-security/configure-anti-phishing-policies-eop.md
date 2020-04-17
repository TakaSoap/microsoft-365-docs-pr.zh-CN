---
title: 配置 EOP 中的默认防钓鱼策略
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何使用 Exchange Online 邮箱修改 Office 365 组织中的默认反网络钓鱼策略中提供的反欺骗设置。
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537529"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a><span data-ttu-id="52f7e-103">配置 EOP 中的默认防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="52f7e-103">Configure the default anti-phishing policy in EOP</span></span>

<span data-ttu-id="52f7e-104">拥有 Exchange Online 邮箱和独立 Exchange Online Protection （EOP）组织（没有 Exchange Online 邮箱）的 Office 365 组织具有默认的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="52f7e-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes have a default anti-phishing policy.</span></span> <span data-ttu-id="52f7e-105">此策略包含默认情况下启用的有限数量的反欺骗功能。</span><span class="sxs-lookup"><span data-stu-id="52f7e-105">This policy contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="52f7e-106">有关详细信息，请参阅[反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="52f7e-106">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="52f7e-107">使用 Exchange Online 邮箱的 office 365 组织可以修改 Office 365 安全性 & 合规性中心或 Exchange Online PowerShell 中的默认反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="52f7e-107">Office 365 organizations with Exchange Online mailboxes can modify the default anti-phishing policy in the Office 365 Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="52f7e-108">没有 Exchange Online 邮箱的独立 EOP 组织无法修改其默认的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="52f7e-108">Standalone EOP organizations without Exchange Online mailboxes can't modify their default anti-phishing policy.</span></span>

<span data-ttu-id="52f7e-109">有关创建和修改 Office 365 高级威胁防护中提供的更高级 ATP 反钓鱼策略的信息，请参阅[在 office 365 中配置 ATP 反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="52f7e-109">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="52f7e-110">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="52f7e-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="52f7e-111">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="52f7e-111">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="52f7e-112">若要直接转到 "**反钓鱼**" 页面， <https://protection.office.com/antiphishing>请使用。</span><span class="sxs-lookup"><span data-stu-id="52f7e-112">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="52f7e-113">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="52f7e-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="52f7e-114">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="52f7e-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="52f7e-115">若要添加、修改和删除反网络钓鱼策略，您必须是 "**组织管理**" 或 "**安全管理员**" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="52f7e-115">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="52f7e-116">若要对反网络钓鱼策略进行只读访问，您需要是**安全读者**角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="52f7e-116">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="52f7e-117">若要详细了解安全与合规中心内的角色组，请参阅 [Office 365 安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="52f7e-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="52f7e-118">有关默认反网络钓鱼策略的推荐设置，请参阅[EOP 默认反网络钓鱼策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="52f7e-118">For our recommended settings for the default anti-phishing policy, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="52f7e-119">允许应用更新后的策略最长为30分钟。</span><span class="sxs-lookup"><span data-stu-id="52f7e-119">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="52f7e-120">有关在筛选管道中应用反网络钓鱼策略的位置的信息，请参阅[Office 365 中的电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="52f7e-120">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection in Office 365](how-policies-and-protections-are-combined.md).</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="52f7e-121">使用安全 & 合规性中心修改默认的反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="52f7e-121">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="52f7e-122">默认的反网络钓鱼策略名为 Office365 AntiPhish Default，且不会出现在策略列表中。</span><span class="sxs-lookup"><span data-stu-id="52f7e-122">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="52f7e-123">若要修改默认的反网络钓鱼策略，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="52f7e-123">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="52f7e-124">在安全 & 合规性中心中，转到 "**威胁管理** \> **策略** \> " "**反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="52f7e-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="52f7e-125">在 "**反钓鱼网站**" 页上，单击 "**默认策略**"。</span><span class="sxs-lookup"><span data-stu-id="52f7e-125">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="52f7e-126">将显示 "**编辑您的策略 Office365 AntiPhish 默认**页"。</span><span class="sxs-lookup"><span data-stu-id="52f7e-126">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="52f7e-127">在 "**欺骗**" 部分，单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="52f7e-127">In the **Spoof** section, click **Edit**.</span></span>

   <span data-ttu-id="52f7e-128">请注意，这些设置与 ATP 反网络钓鱼策略中提供的欺骗设置相同。</span><span class="sxs-lookup"><span data-stu-id="52f7e-128">Note that these settings are identical to the spoof settings that are available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="52f7e-129">**哄骗筛选器设置**：默认值为 **"开**"，我们建议您将其保留在中。</span><span class="sxs-lookup"><span data-stu-id="52f7e-129">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="52f7e-130">若要将其关闭，请将开关滑动到 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="52f7e-130">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="52f7e-131">有关详细信息，请参阅[在 Office 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="52f7e-131">For more information, see [Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="52f7e-132">如果您的 MX 记录不指向 Office 365，则无需禁用反欺骗保护;可以改为对连接器启用增强的筛选。</span><span class="sxs-lookup"><span data-stu-id="52f7e-132">You don't need to disable anti-spoofing protection if your MX record doesn't point to Office 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="52f7e-133">有关说明，请参阅[增强的对 Exchange Online 中的连接器的筛选](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="52f7e-133">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="52f7e-134">**启用未经身份验证的发件人功能**：如果邮件失败电子邮件身份验证检查，则向发件人的照片添加问号。</span><span class="sxs-lookup"><span data-stu-id="52f7e-134">**Enable Unauthenticated Sender feature**: Adds a question mark to the sender's photo if the message fails email authentication checks.</span></span> <span data-ttu-id="52f7e-135">有关详细信息，请参阅[反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="52f7e-135">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span> <span data-ttu-id="52f7e-136">默认值为“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="52f7e-136">The default value is **On**.</span></span> <span data-ttu-id="52f7e-137">若要将其关闭，请将开关滑动到 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="52f7e-137">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="52f7e-138">**操作**：指定对欺骗性智能邮件失败的邮件执行的操作：</span><span class="sxs-lookup"><span data-stu-id="52f7e-138">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="52f7e-139">**如果电子邮件由不允许欺骗您的域的人发送**：</span><span class="sxs-lookup"><span data-stu-id="52f7e-139">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="52f7e-140">**将邮件移到收件人的 "垃圾邮件" 文件夹**（这是默认值。）</span><span class="sxs-lookup"><span data-stu-id="52f7e-140">**Move message to the recipients' Junk Email folders** (This is the default value.)</span></span>
     - <span data-ttu-id="52f7e-141">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="52f7e-141">**Quarantine the message**</span></span>

   - <span data-ttu-id="52f7e-142">**查看设置**：不是单击每个单独的步骤，而是在摘要中显示设置。</span><span class="sxs-lookup"><span data-stu-id="52f7e-142">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="52f7e-143">您可以单击每个部分中的 "**编辑**" 以跳回到相关页面。</span><span class="sxs-lookup"><span data-stu-id="52f7e-143">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="52f7e-144">您可以在此页面**上\*\*\*\*直接切换**以下设置：</span><span class="sxs-lookup"><span data-stu-id="52f7e-144">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="52f7e-145">**启用 antispoofing 保护**</span><span class="sxs-lookup"><span data-stu-id="52f7e-145">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="52f7e-146">**启用未经身份验证的发件人功能**</span><span class="sxs-lookup"><span data-stu-id="52f7e-146">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="52f7e-147">完成后，请单击任意页面上的 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="52f7e-147">When you're finished, click **Save** on any page.</span></span>

4. <span data-ttu-id="52f7e-148">返回到 "**编辑您的策略 Office365 AntiPhish 默认**页面"，查看您的设置，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="52f7e-148">Back on the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a><span data-ttu-id="52f7e-149">使用安全 & 合规性中心查看默认的反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="52f7e-149">Use the Security & Compliance Center to view the default anti-phishing policy</span></span>

1. <span data-ttu-id="52f7e-150">在安全 & 合规性中心，并转到**威胁管理** \> **策略** \> **ATP 反网络钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="52f7e-150">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="52f7e-151">单击 "**默认策略**" 以查看默认的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="52f7e-151">Click **Default policy** to view the default anti-phishing policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a><span data-ttu-id="52f7e-152">使用 Exchange Online PowerShell 配置默认的反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="52f7e-152">Use Exchange Online PowerShell to configure the default anti-phishing policy</span></span>

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a><span data-ttu-id="52f7e-153">使用 PowerShell 查看默认反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="52f7e-153">Use PowerShell to view the default anti-phish policy</span></span>

<span data-ttu-id="52f7e-154">若要查看默认的反网络钓鱼策略，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="52f7e-154">To view the default anti-phish policy, run the following command:</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

<span data-ttu-id="52f7e-155">有关语法和参数的详细信息，请参阅[AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="52f7e-155">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a><span data-ttu-id="52f7e-156">使用 PowerShell 修改默认反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="52f7e-156">Use PowerShell to modify the default anti-phish policy</span></span>

<span data-ttu-id="52f7e-157">若要修改默认的反网络钓鱼策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="52f7e-157">To modify the default anti-phish policy, use the following syntax:</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="52f7e-158">本示例将对未通过身份验证检查的欺骗性邮件的操作更改为 "隔离"。</span><span class="sxs-lookup"><span data-stu-id="52f7e-158">This example changes the action for spoofed messages that fail authentication checks to quarantine.</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="52f7e-159">有关语法和参数的详细信息，请参阅[AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="52f7e-159">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="52f7e-160">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="52f7e-160">How do you know these procedures worked?</span></span>

<span data-ttu-id="52f7e-161">若要验证是否已成功配置默认的反网络钓鱼策略，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="52f7e-161">To verify that you've successfully configured the default anti-phishing policy, do any of the following steps:</span></span>

- <span data-ttu-id="52f7e-162">在安全 & 合规性中心中，转到 "**威胁管理** \> **策略** \> **反网络钓鱼** \> " 单击 "**默认策略**"，然后在浮出控件中查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="52f7e-162">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="52f7e-163">在 Exchange Online PowerShell 中，运行以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="52f7e-163">In Exchange Online PowerShell, run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
