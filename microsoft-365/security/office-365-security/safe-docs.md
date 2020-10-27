---
title: Office 365 ATP 中的安全文档
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 了解 Microsoft 365 E5 或 Microsoft 365 E5 Security 中的安全文档。
ms.openlocfilehash: baa04f74388b702b42a0bdb83a7f0797ace09883
ms.sourcegitcommit: 45c0afcf958069c5c1b31f9b6c762d8dd806e1e9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48773945"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="2824a-103">Microsoft 365 E5 中的安全文档</span><span class="sxs-lookup"><span data-stu-id="2824a-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2824a-104">安全文档是 Microsoft 365 E5 或 Microsoft 365 E5 Security 中的一项功能，使用 [Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 来扫描在 [受保护视图](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)中打开的文档和文件。</span><span class="sxs-lookup"><span data-stu-id="2824a-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2824a-105">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="2824a-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2824a-106">安全文档仅适用于使用 *Microsoft 365 e5* 或 *Microsoft 365 e5 安全* 许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="2824a-106">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="2824a-107">这些许可证不包含在 Office 365 高级威胁防护 (ATP) 计划中。</span><span class="sxs-lookup"><span data-stu-id="2824a-107">These licenses are not included in Office 365 Advanced Threat Protection (ATP) plans.</span></span>

- <span data-ttu-id="2824a-108">Microsoft 365 应用程序中的安全文档在以前称为 Office 365 专业增强版) 版本2004或更高版本的企业版 (中受支持。</span><span class="sxs-lookup"><span data-stu-id="2824a-108">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="2824a-109">安全与合规中心的打开网址为 <https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="2824a-109">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="2824a-110">若要直接转到 " **ATP 安全附件** " 页面，请打开 <https://protection.office.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="2824a-110">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="2824a-111">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2824a-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="2824a-112">在执行本主题中的过程之前，您需要分配权限。</span><span class="sxs-lookup"><span data-stu-id="2824a-112">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="2824a-113">若要启用和配置安全文档，您必须是 " **组织管理** " 或 " **安全管理员** " 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="2824a-113">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="2824a-114">若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2824a-114">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="2824a-115">Microsoft 如何处理您的数据？</span><span class="sxs-lookup"><span data-stu-id="2824a-115">How does Microsoft handle your data?</span></span>

<span data-ttu-id="2824a-116">为了使你受到保护，安全文档会将文件发送到 [Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 云进行分析。</span><span class="sxs-lookup"><span data-stu-id="2824a-116">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="2824a-117">有关 Microsoft Defender ATP 如何处理你的数据的详细信息，请参阅此处： [Microsoft DEFENDER atp 数据存储和隐私](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。</span><span class="sxs-lookup"><span data-stu-id="2824a-117">Details on how Microsoft Defender ATP handles your data can be found here: [Microsoft Defender ATP data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="2824a-118">安全文档发送的文件不会在进行分析所需的时间段内保留，而不会在 (中保留（) 通常不到24小时）。</span><span class="sxs-lookup"><span data-stu-id="2824a-118">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="2824a-119">使用安全 & 合规中心配置安全文档</span><span class="sxs-lookup"><span data-stu-id="2824a-119">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="2824a-120">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全附件** "，然后单击 " **全局设置** "。</span><span class="sxs-lookup"><span data-stu-id="2824a-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments** , and then click **Global settings** .</span></span>

2. <span data-ttu-id="2824a-121">在显示的 **全局设置** 飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="2824a-121">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="2824a-122">**打开 Office 客户端的安全文档** ：将切换移到右侧以打开功能： ![ 开启 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 。</span><span class="sxs-lookup"><span data-stu-id="2824a-122">**Turn on Safe Documents for Office clients** : Move the toggle to the right to turn on the feature: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="2824a-123">**允许用户在受保护的视图中单击，即使安全文档将该文件标识为恶意文件** 也是如此：建议您将此选项保留为关闭状态 (保持左侧的开关： ![ ](../../media/scc-toggle-off.png)) 切换。</span><span class="sxs-lookup"><span data-stu-id="2824a-123">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious** : We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="2824a-124">完成时，请单击“保存”  。</span><span class="sxs-lookup"><span data-stu-id="2824a-124">When you're finished, click **Save** .</span></span>

   ![选择 "ATP 安全附件" 页面上的 "全局设置" 后的安全文档设置。](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="2824a-126">使用 Exchange Online PowerShell 配置安全文档</span><span class="sxs-lookup"><span data-stu-id="2824a-126">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="2824a-127">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2824a-127">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="2824a-128">_EnableSafeDocs_ 参数为整个组织启用或禁用安全文档。</span><span class="sxs-lookup"><span data-stu-id="2824a-128">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="2824a-129">_AllowSafeDocsOpen_ 参数允许或禁止用户将受保护的视图 (即，如果文档已被标识为恶意文档，则打开文档) 。</span><span class="sxs-lookup"><span data-stu-id="2824a-129">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="2824a-130">本示例为整个组织启用安全文档，并阻止用户打开已被 "受保护的视图" 识别为恶意的文档。</span><span class="sxs-lookup"><span data-stu-id="2824a-130">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="2824a-131">有关语法和参数的详细信息，请参阅 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="2824a-131">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="2824a-132">我如何知道这有效？</span><span class="sxs-lookup"><span data-stu-id="2824a-132">How do I know this worked?</span></span>

<span data-ttu-id="2824a-133">若要验证是否已启用并配置安全文档，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="2824a-133">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="2824a-134">在 "安全性 & 合规性中心" 中，转到 " **威胁管理** \> **策略** \> **ATP 安全附件** "，单击 " **全局设置** "，然后验证是否 **打开 Office 客户端的安全文档** 并 **允许用户在受保护的视图中单击，即使安全文档将该文件标识为恶意** 设置也是如此。</span><span class="sxs-lookup"><span data-stu-id="2824a-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments** , click **Global settings** , and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="2824a-135">在 Exchange Online PowerShell 中运行以下命令，并验证属性值：</span><span class="sxs-lookup"><span data-stu-id="2824a-135">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="2824a-136">以下文件可用于测试安全文档保护。</span><span class="sxs-lookup"><span data-stu-id="2824a-136">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="2824a-137">这些文档类似于测试反恶意软件和反病毒解决方案的 EICAR.TXT 文件。</span><span class="sxs-lookup"><span data-stu-id="2824a-137">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="2824a-138">这些文件不会造成危害，但会触发安全文档保护。</span><span class="sxs-lookup"><span data-stu-id="2824a-138">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="2824a-139">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="2824a-139">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="2824a-140">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="2824a-140">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="2824a-141">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="2824a-141">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
