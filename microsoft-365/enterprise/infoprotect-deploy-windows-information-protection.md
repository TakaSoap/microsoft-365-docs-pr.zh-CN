---
title: 步骤 4：配置 Windows 信息保护
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 理解并部署 Microsoft 365 中的 Windows 信息保护。
ms.openlocfilehash: ca706d49053bbc100a633afb74c7c978de2e4c5c
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353095"
---
# <a name="step-4-configure-windows-information-protection"></a><span data-ttu-id="f863c-103">步骤 4：配置 Windows 信息保护</span><span class="sxs-lookup"><span data-stu-id="f863c-103">Step 4: Configure Windows Information Protection</span></span>

<span data-ttu-id="f863c-104">\*\* 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本</span><span class="sxs-lookup"><span data-stu-id="f863c-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="f863c-105">随着越来越多的个人设备被用于工作，应用和设备泄露私人组织数据的风险增加。</span><span class="sxs-lookup"><span data-stu-id="f863c-105">With more personal devices being used for work, there’s increased risk for apps and devices to leak private organization data.</span></span> <span data-ttu-id="f863c-106">例如，员工无意中将未来产品的市场营销计划图片发送到社交媒体网站，或将包含高度机密信息的文件保存到其公有云存储。</span><span class="sxs-lookup"><span data-stu-id="f863c-106">For example, an employee inadvertently sends a picture of a marketing plan for a future product to a social media site or saves a file containing highly confidential information to their public cloud storage.</span></span> 

<span data-ttu-id="f863c-107">Windows 信息保护 (WIP) 有助于防止 Windows 10 设备上的这些类型的数据泄露。</span><span class="sxs-lookup"><span data-stu-id="f863c-107">Windows Information Protection (WIP) helps protect against these types of data leakage on Windows 10 devices.</span></span> <span data-ttu-id="f863c-108">有关详细信息，请参阅[使用 WIP 保护企业数据](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)。</span><span class="sxs-lookup"><span data-stu-id="f863c-108">For more information, see [Protect your enterprise data using WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span>

<span data-ttu-id="f863c-109">在 Microsoft 365 企业版中，WIP 是 Windows 10 企业版和 Microsoft Intune 的组合，包括在套餐内的企业移动性 + 安全性 (EMS) 中。</span><span class="sxs-lookup"><span data-stu-id="f863c-109">In Microsoft 365 Enterprise, WIP is a combination of Windows 10 Enterprise and Microsoft Intune, which is included with Enterprise Mobility + Security (EMS) in your subscription.</span></span> 

<span data-ttu-id="f863c-110">若要使用 Microsoft 365 企业版在组织中部署 WIP：</span><span class="sxs-lookup"><span data-stu-id="f863c-110">To deploy WIP in your organization with Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="f863c-111">在 Intune 中注册 Windows 设备。</span><span class="sxs-lookup"><span data-stu-id="f863c-111">Enroll your Windows devices in Intune.</span></span> <span data-ttu-id="f863c-112">你应该已经在[阶段 5：移动设备管理](mobility-infrastructure.md)过程中完成了此操作。</span><span class="sxs-lookup"><span data-stu-id="f863c-112">You should have done this in [Phase 5: Mobile Device Management](mobility-infrastructure.md).</span></span>
2. <span data-ttu-id="f863c-113">创建[WIP 的 Intune 策略](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)。</span><span class="sxs-lookup"><span data-stu-id="f863c-113">Create an [Intune policy for WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span></span>
  - <span data-ttu-id="f863c-114">确保已填写“受保护应用列表”。</span><span class="sxs-lookup"><span data-stu-id="f863c-114">Ensure that you have filled out your Protected apps list.</span></span>
  - <span data-ttu-id="f863c-115">选择 WIP 保护等级。</span><span class="sxs-lookup"><span data-stu-id="f863c-115">Choose your WIP protection level.</span></span>

<span data-ttu-id="f863c-116">也可通过 [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm) 使用 WIP。</span><span class="sxs-lookup"><span data-stu-id="f863c-116">You can also use WIP with [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span></span> 

<span data-ttu-id="f863c-117">请参阅 [WIP 最佳做法]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip)以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="f863c-117">See [WIP best practices]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) for more information.</span></span>

<span data-ttu-id="f863c-118">作为临时检查点，请查看对应于此步骤的[退出条件](infoprotect-exit-criteria.md#crit-infoprotect-step4)。</span><span class="sxs-lookup"><span data-stu-id="f863c-118">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="f863c-119">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f863c-119">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="f863c-120">配置 Office 365 数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="f863c-120">Office 365 Data Loss Prevention (DLP)</span></span>](infoprotect-data-loss-prevention.md)|


