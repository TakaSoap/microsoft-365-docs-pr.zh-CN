---
title: 步骤 4：配置 Windows 信息保护
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 理解并部署 Microsoft 365 中的 Windows 信息保护。
ms.openlocfilehash: c7b76ef28d41810d6e9e45e98adb7a94cf8ae2f4
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005718"
---
# <a name="step-4-configure-windows-information-protection"></a><span data-ttu-id="00465-103">步骤 4：配置 Windows 信息保护</span><span class="sxs-lookup"><span data-stu-id="00465-103">Step 4: Configure Windows Information Protection</span></span>

<span data-ttu-id="00465-104">*此步骤可选，它适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="00465-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![第 6 阶段：信息保护](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="00465-106">随着越来越多的个人设备被用于工作，应用和设备泄露私人组织数据的风险增加。</span><span class="sxs-lookup"><span data-stu-id="00465-106">With more personal devices being used for work, there’s increased risk for apps and devices to leak private organization data.</span></span> <span data-ttu-id="00465-107">例如，员工无意中将未来产品的市场营销计划图片发送到社交媒体网站，或将包含高度机密信息的文件保存到其公有云存储。</span><span class="sxs-lookup"><span data-stu-id="00465-107">For example, an employee inadvertently sends a picture of a marketing plan for a future product to a social media site or saves a file containing highly confidential information to their public cloud storage.</span></span> 

<span data-ttu-id="00465-108">Windows 信息保护 (WIP) 有助于防止 Windows 10 设备上的这些类型的数据泄露。</span><span class="sxs-lookup"><span data-stu-id="00465-108">Windows Information Protection (WIP) helps protect against these types of data leakage on Windows 10 devices.</span></span> <span data-ttu-id="00465-109">有关详细信息，请参阅[使用 WIP 保护企业数据](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)。</span><span class="sxs-lookup"><span data-stu-id="00465-109">For more information, see [Protect your enterprise data using WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span>

<span data-ttu-id="00465-110">在 Microsoft 365 企业版中，WIP 是 Windows 10 企业版和 Microsoft Intune 的组合，包括在订阅中。</span><span class="sxs-lookup"><span data-stu-id="00465-110">In Microsoft 365 Enterprise, WIP is a combination of Windows 10 Enterprise and Microsoft Intune, which is included with your subscription.</span></span> 

<span data-ttu-id="00465-111">若要使用 Microsoft 365 企业版在组织中部署 WIP：</span><span class="sxs-lookup"><span data-stu-id="00465-111">To deploy WIP in your organization with Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="00465-112">在 Intune 中注册 Windows 设备。</span><span class="sxs-lookup"><span data-stu-id="00465-112">Enroll your Windows devices in Intune.</span></span> <span data-ttu-id="00465-113">你应该已经在[阶段 5：移动设备管理](mobility-infrastructure.md)过程中完成了此操作。</span><span class="sxs-lookup"><span data-stu-id="00465-113">You should have done this in [Phase 5: Mobile Device Management](mobility-infrastructure.md).</span></span>

2. <span data-ttu-id="00465-114">创建[WIP 的 Intune 策略](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)。</span><span class="sxs-lookup"><span data-stu-id="00465-114">Create an [Intune policy for WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span></span>

   -    <span data-ttu-id="00465-115">确保已填写“受保护应用列表”。</span><span class="sxs-lookup"><span data-stu-id="00465-115">Ensure that you have filled out your Protected apps list.</span></span>
  
   - <span data-ttu-id="00465-116">选择 WIP 保护等级。</span><span class="sxs-lookup"><span data-stu-id="00465-116">Choose your WIP protection level.</span></span>

<span data-ttu-id="00465-117">还可以将 WIP 与 [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-configmgr) 结合使用。</span><span class="sxs-lookup"><span data-stu-id="00465-117">You can also use WIP with [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-configmgr).</span></span> 

<span data-ttu-id="00465-118">请参阅 [WIP 最佳做法]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip)以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="00465-118">See [WIP best practices]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) for more information.</span></span>

<span data-ttu-id="00465-119">作为临时检查点，请查看对应于此步骤的[退出条件](infoprotect-exit-criteria.md#crit-infoprotect-step4)。</span><span class="sxs-lookup"><span data-stu-id="00465-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="00465-120">后续步骤</span><span class="sxs-lookup"><span data-stu-id="00465-120">Next step</span></span>

|||
|:-------|:-----|
|![第 5 步](../media/stepnumbers/Step5.png)|[<span data-ttu-id="00465-122">配置数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="00465-122">Configure Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|


