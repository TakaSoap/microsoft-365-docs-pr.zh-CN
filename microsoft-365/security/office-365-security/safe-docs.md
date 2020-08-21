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
description: 了解 Microsoft 365 E5 或 Microsoft 365 E5 安全中心中的安全文档。
ms.openlocfilehash: cd689099fc6a6caa1e0e649c3f152f1de123bf12
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827465"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="ebe98-103">Microsoft 365 E5 安全文档</span><span class="sxs-lookup"><span data-stu-id="ebe98-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="ebe98-104">安全文档是 Microsoft 365 E5 或 Microsoft 365 E5 安全中的一项功能，它 [使用 Microsoft Defender 高级威胁](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 防护扫描在受保护视图中 [打开的文档和文件](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)。</span><span class="sxs-lookup"><span data-stu-id="ebe98-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ebe98-105">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="ebe98-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ebe98-106">现在，拥有 Office 2004 版 Office 2004 或更高 (版本的用户现在已经有) 安全文档！</span><span class="sxs-lookup"><span data-stu-id="ebe98-106">Safe Documents is now generally available to users with Office Version 2004 (12730.x) or greater!</span></span> <span data-ttu-id="ebe98-107">此功能默认处于关闭状态，需要由安全管理员启用。</span><span class="sxs-lookup"><span data-stu-id="ebe98-107">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="ebe98-108">此功能仅适用于 Office *365* ATP 计划计划中未附带 *的 (365 E5* 或 Microsoft 365 E5 安全) 。</span><span class="sxs-lookup"><span data-stu-id="ebe98-108">This feature is only available to users with the *Microsoft 365 E5* or *Microsoft 365 E5 Security* license (not included in Office 365 ATP plans).</span></span>

- <span data-ttu-id="ebe98-109">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ebe98-109">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ebe98-110">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ebe98-110">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ebe98-111">您必须先拥有权限，然后才能执行本主题中的过程。</span><span class="sxs-lookup"><span data-stu-id="ebe98-111">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="ebe98-112">若要启用和配置安全文档，您需要是组织**管理或安全\*\*\*\*管理员**角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="ebe98-112">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="ebe98-113">若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="ebe98-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="ebe98-114">Microsoft 如何处理你的数据？</span><span class="sxs-lookup"><span data-stu-id="ebe98-114">How does Microsoft handle your data?</span></span>

<span data-ttu-id="ebe98-115">为确保你受保护，安全文档将文件发送至 [Microsoft Defender 高级威胁防护云进行](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 分析。</span><span class="sxs-lookup"><span data-stu-id="ebe98-115">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span>

- <span data-ttu-id="ebe98-116">有关 Microsoft Defender 高级威胁防护如何处理你的数据的详细信息，可以从 [此处查看](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="ebe98-116">Details on how Microsoft Defender Advanced Threat Protection handles your data can be found [here](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span></span>
- <span data-ttu-id="ebe98-117">除了上述指南以外，安全文档发送的文件不会在 Defender 中保留超过分析所需的时间，通常会少于 24 小时</span><span class="sxs-lookup"><span data-stu-id="ebe98-117">In addition to the guidelines above, files sent by Safe Documents are not retained in Defender beyond the time needed for analysis, which is typically less than 24 hours</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="ebe98-118">使用安全与&合规中心配置安全文档</span><span class="sxs-lookup"><span data-stu-id="ebe98-118">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="ebe98-119">打开"&安全与合规中心 <https://protection.office.com> "。</span><span class="sxs-lookup"><span data-stu-id="ebe98-119">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="ebe98-120">转到威 **胁管理** \> **策略** \> **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="ebe98-120">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="ebe98-121">在帮助 **用户信任文件在 Office 应用程序部分的"受保护视图"之外打开时，帮助** 人员可安全运行，配置以下设置之一：</span><span class="sxs-lookup"><span data-stu-id="ebe98-121">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="ebe98-122">**为 Office 客户端启用安全文档**</span><span class="sxs-lookup"><span data-stu-id="ebe98-122">**Turn on Safe Documents for Office clients**</span></span>

   - <span data-ttu-id="ebe98-123">**是否允许用户单击受保护视图，即使安全**文档将文件标识为恶意文件也是如此：我们建议您不要启用此选项。</span><span class="sxs-lookup"><span data-stu-id="ebe98-123">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="ebe98-124">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ebe98-124">When you're finished, click **Save**.</span></span>

![ATP 安全附件页面](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a><span data-ttu-id="ebe98-126">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置安全文档</span><span class="sxs-lookup"><span data-stu-id="ebe98-126">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="ebe98-127">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="ebe98-127">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="ebe98-128">_EnableSafeDocs_参数启用或禁用整个组织的安全文档。</span><span class="sxs-lookup"><span data-stu-id="ebe98-128">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="ebe98-129">_AllowSafeDocsOpen_参数允许或阻止用户离开受保护的视图 (即如果文档被识别为恶意文档) 打开该文档。</span><span class="sxs-lookup"><span data-stu-id="ebe98-129">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="ebe98-130">本示例为整个组织启用安全文档，并阻止用户打开已被恶意的受保护的视图的文档。</span><span class="sxs-lookup"><span data-stu-id="ebe98-130">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="ebe98-131">有关语法和参数的详细信息，请参阅[Set-AtpPolicyForO365。](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="ebe98-131">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="ebe98-132">我如何知道这有效？</span><span class="sxs-lookup"><span data-stu-id="ebe98-132">How do I know this worked?</span></span>

<span data-ttu-id="ebe98-133">若要验证是否已启用和配置安全文档，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="ebe98-133">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="ebe98-134">在安全 & 合规中心转至 **威胁管理** \> **策略** \> **ATP 安全附件**，并验证信任 **在 Office** 应用程序部分的"受保护视图外部打开"的文件时帮助用户中的选择都保持安全。</span><span class="sxs-lookup"><span data-stu-id="ebe98-134">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="ebe98-135">在 Exchange Online PowerShell 中运行以下命令并验证属性值：</span><span class="sxs-lookup"><span data-stu-id="ebe98-135">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
