---
title: '步骤 3：为 Microsoft 365 配置提升的安全性:'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 为 Microsoft 365 了解和配置提升的安全性。
ms.openlocfilehash: a1976a9305c40d721bd56a4b21b8a52552c1a9dc
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285072"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="35b16-103">步骤 3：为 Microsoft 365 配置提升的安全性:</span><span class="sxs-lookup"><span data-stu-id="35b16-103">Step 3: Configure increased security for Office 365</span></span>

<span data-ttu-id="35b16-104">*此步骤是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="35b16-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="35b16-105">若要确保 Microsoft 365 订阅及其数据启用，并保持安全免遭恶意威胁的侵害，请配置以下各项：</span><span class="sxs-lookup"><span data-stu-id="35b16-105">To ensure that your Office 365 subscription and its data start off and remain secure from malicious threats, see Configure your Office 365 tenant for increased security and configure the following additional security:</span></span>

- [<span data-ttu-id="35b16-106">优化威胁管理策略</span><span class="sxs-lookup"><span data-stu-id="35b16-106">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-office-365-security--compliance-center)
- [<span data-ttu-id="35b16-107">其他 Exchange Online 租户范围内设置</span><span class="sxs-lookup"><span data-stu-id="35b16-107">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="35b16-108">SharePoint 管理中心中的租户范围内共享策略</span><span class="sxs-lookup"><span data-stu-id="35b16-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="35b16-109">Azure Active Directory 中的设置 (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="35b16-109">CORS support in Microsoft Azure Active Directory (Azure AD)</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="35b16-110">完成配置后，可从下面位置获取有关安全状态的信息：</span><span class="sxs-lookup"><span data-stu-id="35b16-110">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="35b16-111">Microsoft 安全中心中的仪表板和报告</span><span class="sxs-lookup"><span data-stu-id="35b16-111">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security--compliance-center)
- [<span data-ttu-id="35b16-112">Microsoft 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="35b16-112">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="35b16-113">其他安全功能包括 [Office 365 高级威胁防护 (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp)，可帮助组织通过以下方式进行更安全地协作：</span><span class="sxs-lookup"><span data-stu-id="35b16-113">An additional security feature is Office 365 Advanced Threat Protection (ATP), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="35b16-114">保护电子邮件中的[链接](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links)和[附件](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments)。</span><span class="sxs-lookup"><span data-stu-id="35b16-114">Protecting links and attachments in email.</span></span> 
- <span data-ttu-id="35b16-115">为 Exchange Online 中的电子邮件和 [SharePoint Online、OneDrive for Business 以及 Microsoft Teams 中的文件](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams)提供欺骗智能和防钓鱼功能。</span><span class="sxs-lookup"><span data-stu-id="35b16-115">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> 

<span data-ttu-id="35b16-116">Office 365 ATP 仅在 Microsoft 365 企业版 E5 中提供。</span><span class="sxs-lookup"><span data-stu-id="35b16-116">Office 365 ATP is only available with Microsoft 365 Enterprise E5.</span></span>

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="35b16-118">测试实验室指南：配置更高的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="35b16-118">Test Lab Guide: Configure increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="35b16-119">作为临时检查点，请查看对应于此步骤的[退出条件](infoprotect-exit-criteria.md#crit-infoprotect-step4)。</span><span class="sxs-lookup"><span data-stu-id="35b16-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="35b16-120">后续步骤</span><span class="sxs-lookup"><span data-stu-id="35b16-120">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="35b16-121">配置特权访问管理</span><span class="sxs-lookup"><span data-stu-id="35b16-121">Configure privileged access management</span></span>](infoprotect-configure-privileged-access-management.md)|


