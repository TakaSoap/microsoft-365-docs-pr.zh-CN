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
description: 了解 Office 365 ATP 中的安全文档。
ms.openlocfilehash: c76ae2c776c31cf798c21d7330bce488ad1e7cc6
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082362"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a><span data-ttu-id="8cc78-103">Office 365 中的安全文档高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="8cc78-103">Safe Documents in Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="8cc78-104">安全文档是 Office 365 高级威胁防护（ATP）中的一项功能，它使用[Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)来扫描在[受保护视图](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)中打开的文档和文件。</span><span class="sxs-lookup"><span data-stu-id="8cc78-104">Safe Documents is a feature in Office 365 Advanced Threat Protection (ATP) that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8cc78-105">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="8cc78-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8cc78-106">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8cc78-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8cc78-107">若要连接到 Exchange Online Protection PowerShell，请参阅[连接到 Exchange Online Protection powershell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8cc78-107">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8cc78-108">在执行本主题中的过程之前，您需要分配权限。</span><span class="sxs-lookup"><span data-stu-id="8cc78-108">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="8cc78-109">若要启用和配置安全文档，您必须是 "**组织管理**" 或 "**安全管理员**" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="8cc78-109">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="8cc78-110">有关安全 & 合规中心中的角色组的详细信息，请参阅[Office 365 安全 & 合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="8cc78-110">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-office-365-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="8cc78-111">使用 Office 365 安全 & 合规中心配置安全文档</span><span class="sxs-lookup"><span data-stu-id="8cc78-111">Use the Office 365 Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="8cc78-112">在上<https://protection.office.com>打开 "Office 365 安全性 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="8cc78-112">Open the Office 365 Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="8cc78-113">转到 "**威胁管理** \> **策略** \> **ATP 安全附件**"。</span><span class="sxs-lookup"><span data-stu-id="8cc78-113">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="8cc78-114">在 "**信任文件以在 Office 应用程序中打开外部受保护的视图**" 部分中，在 "帮助用户保持安全" 中，配置以下任一设置：</span><span class="sxs-lookup"><span data-stu-id="8cc78-114">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="8cc78-115">**打开 Office 客户端的安全文档（文件也将发送到 Microsoft 云进行深入分析）**</span><span class="sxs-lookup"><span data-stu-id="8cc78-115">**Turn on Safe Documents for Office clients (Files will also be sent to Microsoft Cloud for deep analyses)**</span></span>

   - <span data-ttu-id="8cc78-116">**允许用户在受保护的视图中单击，即使安全文档将文件标识为恶意文件**也是如此：我们建议您不要启用此选项。</span><span class="sxs-lookup"><span data-stu-id="8cc78-116">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="8cc78-117">完成后，单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8cc78-117">When you're finished, click **Save**.</span></span>

![ATP 安全附件页面](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-safe-documents"></a><span data-ttu-id="8cc78-119">使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 配置安全文档</span><span class="sxs-lookup"><span data-stu-id="8cc78-119">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="8cc78-120">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="8cc78-120">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- <span data-ttu-id="8cc78-121">_EnableSafeDocs_参数为整个组织启用或禁用安全文档。</span><span class="sxs-lookup"><span data-stu-id="8cc78-121">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="8cc78-122">_AllowSafeDocsOpen_参数允许或禁止用户在文档被标识为恶意时离开受保护的视图（即打开文档）。</span><span class="sxs-lookup"><span data-stu-id="8cc78-122">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="8cc78-123">本示例为整个组织启用安全文档，并阻止用户打开已被 "受保护的视图" 识别为恶意的文档。</span><span class="sxs-lookup"><span data-stu-id="8cc78-123">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="8cc78-124">有关语法和参数的详细信息，请参阅[AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="8cc78-124">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="8cc78-125">我如何知道这有效？</span><span class="sxs-lookup"><span data-stu-id="8cc78-125">How do I know this worked?</span></span>

<span data-ttu-id="8cc78-126">若要验证是否已启用并配置安全文档，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="8cc78-126">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="8cc78-127">在安全 & 合规性中心转到**威胁管理** \> **策略** \> **ATP 安全附件**，并验证在**信任文件以在 Office 应用程序中打开受保护视图外部时帮助**中的选择是否保持安全。</span><span class="sxs-lookup"><span data-stu-id="8cc78-127">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="8cc78-128">在 Exchange Online PowerShell 中运行以下命令，并验证属性值：</span><span class="sxs-lookup"><span data-stu-id="8cc78-128">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
