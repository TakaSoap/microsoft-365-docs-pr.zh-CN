---
title: Office 365 ATP 中的安全文档
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 了解 Microsoft 365 E5 或 Microsoft 365 E5 Security 中的安全文档。
ms.openlocfilehash: c574e28a01dc961d898638184afe9ece90e31133
ms.sourcegitcommit: aa7f7350d1342ff9713bb840b2cc96d1a4234ef4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2020
ms.locfileid: "44835343"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="b0eda-103">Microsoft 365 E5 中的安全文档</span><span class="sxs-lookup"><span data-stu-id="b0eda-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="b0eda-104">安全文档是 Microsoft 365 E5 或 Microsoft 365 E5 Security 中的一项功能，使用[Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)来扫描在[受保护视图](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)中打开的文档和文件。</span><span class="sxs-lookup"><span data-stu-id="b0eda-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b0eda-105">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="b0eda-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b0eda-106">安全文档现在通常对使用 Office 版本2004（12730）或更高版本的用户可用！</span><span class="sxs-lookup"><span data-stu-id="b0eda-106">Safe Documents is now generally available to users with Office Version 2004 (12730.x) or greater!</span></span> <span data-ttu-id="b0eda-107">此功能在默认情况下处于禁用状态，将需要由安全管理员启用。</span><span class="sxs-lookup"><span data-stu-id="b0eda-107">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="b0eda-108">此功能仅适用于使用*microsoft 365 e5*或*Microsoft 365 e5 安全*许可证（不包括在 Office 365 ATP 计划中）的用户。</span><span class="sxs-lookup"><span data-stu-id="b0eda-108">This feature is only available to users with the *Microsoft 365 E5* or *Microsoft 365 E5 Security* license (not included in Office 365 ATP plans).</span></span>

- <span data-ttu-id="b0eda-109">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b0eda-109">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b0eda-110">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b0eda-110">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b0eda-111">在执行本主题中的过程之前，您需要分配权限。</span><span class="sxs-lookup"><span data-stu-id="b0eda-111">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="b0eda-112">若要启用和配置安全文档，您必须是 "**组织管理**" 或 "**安全管理员**" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="b0eda-112">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="b0eda-113">若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b0eda-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="b0eda-114">Microsoft 如何处理您的数据？</span><span class="sxs-lookup"><span data-stu-id="b0eda-114">How does Microsoft handle your data?</span></span>

<span data-ttu-id="b0eda-115">为了使你受到保护，安全文档会将文件发送到[Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)云进行分析。</span><span class="sxs-lookup"><span data-stu-id="b0eda-115">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span>

- <span data-ttu-id="b0eda-116">有关 Microsoft Defender 高级威胁防护如何处理你的数据的详细信息，请参阅[此处](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。</span><span class="sxs-lookup"><span data-stu-id="b0eda-116">Details on how Microsoft Defender Advanced Threat Protection handles your data can be found [here](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span></span>
- <span data-ttu-id="b0eda-117">除了上述准则之外，通过安全文档发送的文件不会在进行分析所需的时间（通常少于24小时）的情况下保留在 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="b0eda-117">In addition to the guidelines above, files sent by Safe Documents are not retained in Defender beyond the time needed for analysis, which is typically less than 24 hours</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="b0eda-118">使用安全 & 合规中心配置安全文档</span><span class="sxs-lookup"><span data-stu-id="b0eda-118">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="b0eda-119">在上打开安全 & 合规性中心 <https://protection.office.com> 。</span><span class="sxs-lookup"><span data-stu-id="b0eda-119">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="b0eda-120">转到 "**威胁管理** \> **策略** \> **ATP 安全附件**"。</span><span class="sxs-lookup"><span data-stu-id="b0eda-120">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="b0eda-121">在 "**信任文件以在 Office 应用程序中打开外部受保护的视图**" 部分中，在 "帮助用户保持安全" 中，配置以下任一设置：</span><span class="sxs-lookup"><span data-stu-id="b0eda-121">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="b0eda-122">**打开 Office 客户端的安全文档**</span><span class="sxs-lookup"><span data-stu-id="b0eda-122">**Turn on Safe Documents for Office clients**</span></span>

   - <span data-ttu-id="b0eda-123">**允许用户在受保护的视图中单击，即使安全文档将文件标识为恶意文件**也是如此：我们建议您不要启用此选项。</span><span class="sxs-lookup"><span data-stu-id="b0eda-123">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="b0eda-124">完成后，单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="b0eda-124">When you're finished, click **Save**.</span></span>

![ATP 安全附件页面](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a><span data-ttu-id="b0eda-126">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置安全文档</span><span class="sxs-lookup"><span data-stu-id="b0eda-126">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="b0eda-127">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="b0eda-127">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="b0eda-128">_EnableSafeDocs_参数为整个组织启用或禁用安全文档。</span><span class="sxs-lookup"><span data-stu-id="b0eda-128">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="b0eda-129">_AllowSafeDocsOpen_参数允许或禁止用户在文档被标识为恶意时离开受保护的视图（即打开文档）。</span><span class="sxs-lookup"><span data-stu-id="b0eda-129">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="b0eda-130">本示例为整个组织启用安全文档，并阻止用户打开已被 "受保护的视图" 识别为恶意的文档。</span><span class="sxs-lookup"><span data-stu-id="b0eda-130">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="b0eda-131">有关语法和参数的详细信息，请参阅[AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="b0eda-131">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="b0eda-132">我如何知道这有效？</span><span class="sxs-lookup"><span data-stu-id="b0eda-132">How do I know this worked?</span></span>

<span data-ttu-id="b0eda-133">若要验证是否已启用并配置安全文档，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="b0eda-133">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="b0eda-134">在安全 & 合规性中心转到**威胁管理** \> **策略** \> **ATP 安全附件**，并验证在**信任文件以在 Office 应用程序中打开受保护视图外部时帮助**中的选择是否保持安全。</span><span class="sxs-lookup"><span data-stu-id="b0eda-134">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="b0eda-135">在 Exchange Online PowerShell 中运行以下命令，并验证属性值：</span><span class="sxs-lookup"><span data-stu-id="b0eda-135">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
