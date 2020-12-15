---
title: Microsoft Defender for Office 365 中的安全文档
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
ms.openlocfilehash: 1bf802422dc05babaf5e2616468f8326b7007dc8
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682933"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="5c209-103">Microsoft 365 E5 中的安全文档</span><span class="sxs-lookup"><span data-stu-id="5c209-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="5c209-104">安全文档是 Microsoft 365 E5 或 Microsoft 365 E5 安全版中的一项功能，它使用 [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 扫描受保护的视图中打开的文档和 [文件](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)。</span><span class="sxs-lookup"><span data-stu-id="5c209-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5c209-105">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="5c209-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5c209-106">安全文档仅适用于拥有 *Microsoft 365 E5* 或 *Microsoft 365 E5 安全许可证* 的用户。</span><span class="sxs-lookup"><span data-stu-id="5c209-106">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="5c209-107">这些许可证不包含在 Microsoft Defender for Office 365 计划中。</span><span class="sxs-lookup"><span data-stu-id="5c209-107">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="5c209-108">安全文档在 Microsoft 365 企业应用版 (以前称为 Office 365 专业增强版) 版本 2004 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5c209-108">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="5c209-109">安全与合规中心的打开网址为 <https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="5c209-109">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="5c209-110">若要直接转到 **ATP 安全附件页，** 请打开 <https://protection.office.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="5c209-110">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="5c209-111">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5c209-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="5c209-112">必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="5c209-112">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="5c209-113">若要配置安全文档设置，您必须是组织管理或安全 **管理员角色\*\*\*\*组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="5c209-113">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="5c209-114">若要对安全文档设置进行只读访问，你需要是全局读者或安全 **读者角色组** 的成员。 </span><span class="sxs-lookup"><span data-stu-id="5c209-114">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="5c209-115">有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="5c209-115">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="5c209-116">**注意**：</span><span class="sxs-lookup"><span data-stu-id="5c209-116">**Notes**:</span></span>

  - <span data-ttu-id="5c209-117">向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。</span><span class="sxs-lookup"><span data-stu-id="5c209-117">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="5c209-118">有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="5c209-118">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="5c209-119">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="5c209-119">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="5c209-120">Microsoft 如何处理你的数据？</span><span class="sxs-lookup"><span data-stu-id="5c209-120">How does Microsoft handle your data?</span></span>

<span data-ttu-id="5c209-121">为了保护你，安全文档将文件发送到 [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 云进行分析。</span><span class="sxs-lookup"><span data-stu-id="5c209-121">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="5c209-122">有关 Microsoft Defender for Endpoint 如何处理你的数据的详细信息，请参阅：适用于终结点数据存储和隐私的[Microsoft Defender。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="5c209-122">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="5c209-123">安全文档发送的文件不会在 Defender 中保留超过分析 (，通常少于 24 小时) 。</span><span class="sxs-lookup"><span data-stu-id="5c209-123">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="5c209-124">使用安全&合规中心配置安全文档</span><span class="sxs-lookup"><span data-stu-id="5c209-124">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="5c209-125">在安全&，转到 **"威胁管理** 策略 \>  \> **ATP 安全附件**"，然后单击"**全局设置"。**</span><span class="sxs-lookup"><span data-stu-id="5c209-125">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="5c209-126">在 **出现的全局设置** 飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="5c209-126">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="5c209-127">**打开 Office 客户端的安全** 文档：将开关向右移动以打开功能： ![ 打开 ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="5c209-127">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="5c209-128">即使安全文档将文件标识为恶意文件，也允许用户单击"受保护的视图"：建议将此选项保持关闭状态， (将开关向左切换 ![ ：) 。 ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="5c209-128">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="5c209-129">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="5c209-129">When you're finished, click **Save**.</span></span>

   ![选择"安全附件"页上的"全局"设置后的安全文档设置。](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="5c209-131">使用 Exchange Online PowerShell 配置安全文档</span><span class="sxs-lookup"><span data-stu-id="5c209-131">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="5c209-132">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="5c209-132">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="5c209-133">_EnableSafeDocs_ 参数为整个组织启用或禁用安全文档。</span><span class="sxs-lookup"><span data-stu-id="5c209-133">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="5c209-134">_AllowSafeDocsOpen_ 参数允许或阻止用户离开受保护的视图 (也就是说，如果文档被标识为恶意) 则打开文档。</span><span class="sxs-lookup"><span data-stu-id="5c209-134">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="5c209-135">本示例为整个组织启用安全文档，并阻止用户从受保护的视图中打开已标识为恶意的文档。</span><span class="sxs-lookup"><span data-stu-id="5c209-135">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="5c209-136">有关语法和参数的详细信息，请参阅[Set-AtpPolicyForO365。](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="5c209-136">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="5c209-137">我如何知道这有效？</span><span class="sxs-lookup"><span data-stu-id="5c209-137">How do I know this worked?</span></span>

<span data-ttu-id="5c209-138">若要验证是否已启用和配置了安全文档，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="5c209-138">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="5c209-139">在安全&合规中心，转到"威胁管理策略 \>  \> **ATP** 安全附件"，单击"全局设置"，并验证"为 **Office** 客户端启用安全文档"并允许用户单击"受保护的视图"，即使安全文档将文件标识为恶意设置。</span><span class="sxs-lookup"><span data-stu-id="5c209-139">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="5c209-140">在 Exchange Online PowerShell 中运行以下命令并验证属性值：</span><span class="sxs-lookup"><span data-stu-id="5c209-140">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="5c209-141">以下文件可用于测试安全文档保护。</span><span class="sxs-lookup"><span data-stu-id="5c209-141">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="5c209-142">这些文档类似于EICAR.TXT反恶意软件和防病毒解决方案的文件。</span><span class="sxs-lookup"><span data-stu-id="5c209-142">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="5c209-143">这些文件没有危害，但它们将触发安全文档保护。</span><span class="sxs-lookup"><span data-stu-id="5c209-143">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="5c209-144">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="5c209-144">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="5c209-145">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="5c209-145">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="5c209-146">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="5c209-146">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
