---
title: Microsoft Defender for Office 365 中的安全文档
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 了解保险箱文档Microsoft 365 E5或Microsoft 365 E5 安全性。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e1bd2150a04e51e0d06c6cd1c17a71a032df1a5
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108603"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="185cb-103">Microsoft 365 E5 中的安全文档</span><span class="sxs-lookup"><span data-stu-id="185cb-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="185cb-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="185cb-104">**Applies to**</span></span>
- [<span data-ttu-id="185cb-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="185cb-105">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="185cb-106">保险箱文档是 Microsoft 365 E5 或 Microsoft 365 E5 安全性 中的一项功能，该功能使用[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)扫描在受保护的[](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)视图或应用程序防护中打开的文档[和文件Office。](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)</span><span class="sxs-lookup"><span data-stu-id="185cb-106">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) or [Application Guard for Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="185cb-107">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="185cb-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="185cb-108">保险箱文档仅对拥有 Microsoft 365 E5 *或\*\*Microsoft 365 E5 安全性* 许可证的用户可用。</span><span class="sxs-lookup"><span data-stu-id="185cb-108">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="185cb-109">这些许可证不包含在 Microsoft Defender for Office 365计划中。</span><span class="sxs-lookup"><span data-stu-id="185cb-109">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="185cb-110">保险箱文档在以前称为Microsoft 365 企业应用版 (2004 或Office 365 专业增强版) 版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="185cb-110">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="185cb-111">访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。</span><span class="sxs-lookup"><span data-stu-id="185cb-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="185cb-112">若要直接转到"附件 **保险箱，** 请使用 <https://security.microsoft.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="185cb-112">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="185cb-113">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="185cb-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="185cb-114">您需要在Exchange Online中的权限，然后才能执行本文中的过程：</span><span class="sxs-lookup"><span data-stu-id="185cb-114">You need permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="185cb-115">若要保险箱文档设置，您必须是组织管理或 **安全管理员角色组** 的成员。 </span><span class="sxs-lookup"><span data-stu-id="185cb-115">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="185cb-116">若要对文档保险箱只读访问权限，您需要是全局读者或安全读者 **角色组的成员**。 </span><span class="sxs-lookup"><span data-stu-id="185cb-116">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="185cb-117">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="185cb-117">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="185cb-118">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="185cb-118">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="185cb-119">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="185cb-119">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="185cb-120">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="185cb-120">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="185cb-121">Microsoft 如何处理你的数据？</span><span class="sxs-lookup"><span data-stu-id="185cb-121">How does Microsoft handle your data?</span></span>

<span data-ttu-id="185cb-122">若要保护你，保险箱文档将文件发送到[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)云进行分析。</span><span class="sxs-lookup"><span data-stu-id="185cb-122">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="185cb-123">有关 Microsoft Defender for Endpoint 如何处理你的数据的详细信息，请参阅 [：Microsoft Defender for Endpoint 数据存储和隐私](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。</span><span class="sxs-lookup"><span data-stu-id="185cb-123">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="185cb-124">通常，保险箱文档发送的文件不会在 Defender 中保留超过分析 (，通常不超过 24 小时) 。</span><span class="sxs-lookup"><span data-stu-id="185cb-124">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-microsoft-365-defender-to-configure-safe-documents"></a><span data-ttu-id="185cb-125">使用Microsoft 365 Defender配置文档保险箱文档</span><span class="sxs-lookup"><span data-stu-id="185cb-125">Use the Microsoft 365 Defender to configure Safe Documents</span></span>

1. <span data-ttu-id="185cb-126">打开Microsoft 365 Defender门户，然后转到电子邮件&协作策略 \> **&规则** 威胁策略"页面"策略"部分保险箱 \>  \>  \> **附件"。**</span><span class="sxs-lookup"><span data-stu-id="185cb-126">Open the Microsoft 365 Defender portal and go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="185cb-127">在 **"保险箱"页上**，单击"**全局设置"。**</span><span class="sxs-lookup"><span data-stu-id="185cb-127">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="185cb-128">在出现的 **"全局** 设置"飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="185cb-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>
   - <span data-ttu-id="185cb-129">**打开保险箱客户端Office** 文档：将切换开关向右移动，以打开功能： ![ 打开 ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="185cb-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="185cb-130">即使 **保险箱** 文档将文件标识为恶意文件，也允许用户单击"受保护的视图"：建议将此选项保持关闭状态 (将开关保留为左侧："关闭 ![) "。 ](../../media/scc-toggle-off.png)</span><span class="sxs-lookup"><span data-stu-id="185cb-130">**Allow people to click through Protected View even if Safe Documents identified the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="185cb-131">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="185cb-131">When you're finished, click **Save**.</span></span>

   ![保险箱在"附件"页上选择"全局"保险箱文档设置。](../../media/safe-docs-global-settings.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="185cb-133">使用 Exchange Online PowerShell 配置保险箱文档</span><span class="sxs-lookup"><span data-stu-id="185cb-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="185cb-134">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="185cb-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="185cb-135">_EnableSafeDocs_ 参数为保险箱启用或禁用文档。</span><span class="sxs-lookup"><span data-stu-id="185cb-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="185cb-136">_AllowSafeDocsOpen_ 参数允许或阻止用户离开受保护的视图 (也就是说，如果文档被标识为恶意) 则打开文档。</span><span class="sxs-lookup"><span data-stu-id="185cb-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="185cb-137">本示例为保险箱启用文档，并阻止用户打开受保护视图中标识为恶意的文档。</span><span class="sxs-lookup"><span data-stu-id="185cb-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="185cb-138">有关语法和参数的详细信息，请参阅 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="185cb-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a><span data-ttu-id="185cb-139">载入 Microsoft Defender for Endpoint Service 以启用审核功能</span><span class="sxs-lookup"><span data-stu-id="185cb-139">Onboard to the Microsoft Defender for Endpoint Service to enable auditing capabilities</span></span>

<span data-ttu-id="185cb-140">若要部署 Microsoft Defender for Endpoint，你需要完成部署的各个阶段。</span><span class="sxs-lookup"><span data-stu-id="185cb-140">To deploy Microsoft Defender for Endpoint, you need to go through the various phases of deployment.</span></span> <span data-ttu-id="185cb-141">载入后，可以在企业门户中配置Microsoft 365 Defender功能。</span><span class="sxs-lookup"><span data-stu-id="185cb-141">After onboarding, you can configure auditing capabilities in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="185cb-142">若要了解更多信息，请参阅 [载入到 Microsoft Defender for Endpoint 服务](/microsoft-365/security/defender-endpoint/onboarding)。</span><span class="sxs-lookup"><span data-stu-id="185cb-142">To learn more, see [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding).</span></span> <span data-ttu-id="185cb-143">如果你需要其他帮助，请参阅解决 [Microsoft Defender 终结点载入问题](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)。</span><span class="sxs-lookup"><span data-stu-id="185cb-143">If you need additional help, refer to [Troubleshoot Microsoft Defender for Endpoint onboarding issues](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="185cb-144">我如何知道这有效？</span><span class="sxs-lookup"><span data-stu-id="185cb-144">How do I know this worked?</span></span>

<span data-ttu-id="185cb-145">若要验证是否已启用和配置保险箱文档，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="185cb-145">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="185cb-146">在 Microsoft 365 Defender 门户中，转到电子邮件 **& 协作** 策略 & 规则威胁策略页面策略部分 保险箱 附件全局设置，并验证启用 Office 客户端的 保险箱 文档和允许用户通过受保护的视图单击，即使 \>  \>  \>  \>  \> **保险箱 文档** 将该文件标识为恶意设置。</span><span class="sxs-lookup"><span data-stu-id="185cb-146">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments** \> **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="185cb-147">在 PowerShell 中Exchange Online以下命令并验证属性值：</span><span class="sxs-lookup"><span data-stu-id="185cb-147">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="185cb-148">以下文件可用于测试文档保险箱保护。</span><span class="sxs-lookup"><span data-stu-id="185cb-148">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="185cb-149">这些文档类似于EICAR.TXT反恶意软件和防病毒解决方案的文档文件。</span><span class="sxs-lookup"><span data-stu-id="185cb-149">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="185cb-150">这些文件不有害的，但它们将触发保险箱文档保护。</span><span class="sxs-lookup"><span data-stu-id="185cb-150">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="185cb-151">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="185cb-151">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="185cb-152">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="185cb-152">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="185cb-153">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="185cb-153">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
