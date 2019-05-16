---
title: 步骤 5：配置 Office 365 数据丢失防护
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并部署 Microsoft 365 中的 Office 365 数据丢失防护。
ms.openlocfilehash: f6b9291a2965552837f989c98b32674f6093b383
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073553"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a><span data-ttu-id="7f1b3-103">步骤 5：配置 Office 365 数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="7f1b3-103">Step 5: Configure Office 365 Data Loss Prevention</span></span>

<span data-ttu-id="7f1b3-104">*此步骤可选，它适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="7f1b3-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="7f1b3-105">通过 Office 365 安全与合规中心的数据丢失防护 (DLP) 策略，可在 Microsoft 365 内识别、监视和自动保护敏感数据。</span><span class="sxs-lookup"><span data-stu-id="7f1b3-105">With data loss prevention (DLP) policies in the Office 365 Security & Compliance center, you can identify, monitor, and automatically protect sensitive information across Microsoft 365.</span></span> <span data-ttu-id="7f1b3-106">DLP 策略可助你实现以下操作：</span><span class="sxs-lookup"><span data-stu-id="7f1b3-106">With DLP policies, you can:</span></span>

- <span data-ttu-id="7f1b3-107">跨 Exchange Online、SharePoint Online、OneDrive for Business 和 Microsoft Teams 等多个位置标识敏感信息。</span><span class="sxs-lookup"><span data-stu-id="7f1b3-107">Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>
- <span data-ttu-id="7f1b3-108">阻止访问某文档或阻止包含该文档的电子邮件，从而防止额外共享敏感信息。</span><span class="sxs-lookup"><span data-stu-id="7f1b3-108">Prevent the accidental sharing of sensitive information by blocking access to a document or blocking the email that contains it.</span></span>
- <span data-ttu-id="7f1b3-109">监视和保护 Excel、PowerPoint 和 Word 桌面版中的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="7f1b3-109">Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.</span></span>
- <span data-ttu-id="7f1b3-110">帮助用户了解如何通过电子邮件通知和策略提示在不中断工作流的同时保证合规。</span><span class="sxs-lookup"><span data-stu-id="7f1b3-110">Help users learn how to stay compliant without interrupting their workflow with email notifications and policy tips.</span></span> 
- <span data-ttu-id="7f1b3-111">查看 DLP 报告，了解符合组织的 DLP 策略的内容。</span><span class="sxs-lookup"><span data-stu-id="7f1b3-111">View DLP reports showing content that matches your organization's DLP policies.</span></span>

<span data-ttu-id="7f1b3-112">DLP 策略指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="7f1b3-112">A DLP policy specifies:</span></span>

- <span data-ttu-id="7f1b3-113">**何处：** Exchange Online、SharePoint Online 和 OneDrive for Business 网站等位置，还包括 Microsoft Teams 聊天和频道。</span><span class="sxs-lookup"><span data-stu-id="7f1b3-113">**Where:** Locations such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chats and channels.</span></span>
- <span data-ttu-id="7f1b3-114">**何时：** 内容必须在特定策略规则中匹配的条件。</span><span class="sxs-lookup"><span data-stu-id="7f1b3-114">**When:** Conditions the content must match within a specific policy rule.</span></span>
- <span data-ttu-id="7f1b3-115">**如何：** 该匹配策略规则中针对匹配条件自动执行的操作。</span><span class="sxs-lookup"><span data-stu-id="7f1b3-115">**How:** Actions within that matching policy rule to take automatically for the matching conditions.</span></span>

<span data-ttu-id="7f1b3-116">换言之：</span><span class="sxs-lookup"><span data-stu-id="7f1b3-116">In other words:</span></span>

- <span data-ttu-id="7f1b3-117">对于此位置（何处）中的文档，如果内容与规则的条件相匹配（何时），则自动执行规则中指定的操作（如何）。</span><span class="sxs-lookup"><span data-stu-id="7f1b3-117">For a document in this location (where), if the content matches the conditions of a rule (when), then automatically take the actions specified in the rule (how).</span></span>

<span data-ttu-id="7f1b3-118">为确定你需要的 DLP 策略集，必须分析需要防止数据丢失的文档及其包含的数据类型。</span><span class="sxs-lookup"><span data-stu-id="7f1b3-118">To determine the set of DLP policies you need, you must analyze your documents and the types of data within them that need protection from data loss.</span></span> <span data-ttu-id="7f1b3-119">例如，如果你是美国的一家财务组织，则会创建一个 DLP 策略来阻止在组织外部共享包含社会安全号码的文档或阻止通过电子邮件将此类文档发送到组织外部。</span><span class="sxs-lookup"><span data-stu-id="7f1b3-119">For example, if you are a financial organization in the United States of America, you would create a DLP policy that prevents documents with social security numbers from being shared outside the organization or sent in email to locations outside the organization.</span></span>

<span data-ttu-id="7f1b3-120">接下来，你使用测试位置来配置和测试策略，以确保 DLP 行为正确无误并最大程度减少误报。</span><span class="sxs-lookup"><span data-stu-id="7f1b3-120">Next, you configure and test the policies with test locations to ensure the correct DLP behavior and to minimize false positives.</span></span>

<span data-ttu-id="7f1b3-121">最后，你让员工知晓新策略及其预期行为，同时扩大位置范围，将它推广到整个组织。</span><span class="sxs-lookup"><span data-stu-id="7f1b3-121">Finally, you roll it out to your organization by informing the employees of the new policies and their desired behavior and widening the scope of the locations.</span></span>

<span data-ttu-id="7f1b3-122">有关详细信息，请参阅[开始使用 DLP 策略建议](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations)。</span><span class="sxs-lookup"><span data-stu-id="7f1b3-122">For more information, see [Get started with DLP policy recommendations](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span></span>

<span data-ttu-id="7f1b3-123">作为临时检查点，请查看对应于此步骤的[退出条件](infoprotect-exit-criteria.md#crit-infoprotect-step5)。</span><span class="sxs-lookup"><span data-stu-id="7f1b3-123">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step5) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="7f1b3-124">下一步骤</span><span class="sxs-lookup"><span data-stu-id="7f1b3-124">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)|[<span data-ttu-id="7f1b3-125">配置 Office 365 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="7f1b3-125">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|


