---
title: 第 3 步：配置增强的 Office 365 安全性
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并为 Office 365 配置提升的安全性，包括 Office 365 ATP。
ms.openlocfilehash: 0344778b8d8f9940dc6267a39eac2f4cfb261f9a
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865925"
---
# <a name="step-3-configure-increased-security-for-office-365"></a><span data-ttu-id="c476d-103">第 3 步：配置增强的 Office 365 安全性</span><span class="sxs-lookup"><span data-stu-id="c476d-103">Step 3: Configure increased security for Office 365</span></span>

<span data-ttu-id="c476d-104">*此步骤是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="c476d-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="c476d-105">若要确保 Office 365 订阅及其数据启用，并保持安全免遭恶意威胁的侵害，请参阅[为 Office 365 租户配置提升的安全性](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)，并配置以下额外的安全性：</span><span class="sxs-lookup"><span data-stu-id="c476d-105">To ensure that your Office 365 subscription and its data start off and remain secure from malicious threats, see [Configure your Office 365 tenant for increased security](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355) and configure the following additional security:</span></span>

- <span data-ttu-id="c476d-106">Office 365 安全与合规中心的威胁管理策略</span><span class="sxs-lookup"><span data-stu-id="c476d-106">Threat management policies in the Office 365 Security & Compliance Center</span></span>
- <span data-ttu-id="c476d-107">其他 Exchange Online 租户范围内设置</span><span class="sxs-lookup"><span data-stu-id="c476d-107">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="c476d-108">SharePoint 管理中心中的租户范围内共享策略</span><span class="sxs-lookup"><span data-stu-id="c476d-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>
- <span data-ttu-id="c476d-109">Azure Active Directory 中的设置</span><span class="sxs-lookup"><span data-stu-id="c476d-109">Settings in Azure Active Directory</span></span>

<span data-ttu-id="c476d-110">完成配置后，可从下面位置获取有关安全状态的信息：</span><span class="sxs-lookup"><span data-stu-id="c476d-110">Once configured, you can obtain information about your security status from:</span></span>

- <span data-ttu-id="c476d-111">安全与合规中心中的仪表板和报告</span><span class="sxs-lookup"><span data-stu-id="c476d-111">Dashboards and reports in the Security & Compliance Center</span></span>
- [<span data-ttu-id="c476d-112">Office 365 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="c476d-112">Office 365 Secure Score</span></span>](https://securescore.office.com/)
 
  <span data-ttu-id="c476d-113">若要访问此页面，必须以 Office 365 租户管理员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="c476d-113">To access this page, you must be signed in as an Office 365 tenant admin.</span></span>

<span data-ttu-id="c476d-114">此外，还可使用云应用安全或 Office 365 云应用安全来监控安全事件和行为。有关详细信息，请参阅 [Office 365 云应用安全概述](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475)。</span><span class="sxs-lookup"><span data-stu-id="c476d-114">You can also use Cloud App Security or Office 365 Cloud App Security to monitor for security events and act. For more information, see [Overview of Office 365 Cloud App Security](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475).</span></span>

<span data-ttu-id="c476d-115">其他安全功能包括 Office 365 高级威胁防护 (ATP)，可帮助组织通过以下方式进行更安全地协作：</span><span class="sxs-lookup"><span data-stu-id="c476d-115">An additional security feature is Office 365 Advanced Threat Protection (ATP), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="c476d-116">保护电子邮件中的链接和附件。</span><span class="sxs-lookup"><span data-stu-id="c476d-116">Protecting links and attachments in email.</span></span> 
- <span data-ttu-id="c476d-117">为 Exchange Online 中的电子邮件和 SharePoint Online、OneDrive for Business 以及 Microsoft Teams 中的文件提供欺骗智能和防钓鱼功能。</span><span class="sxs-lookup"><span data-stu-id="c476d-117">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> 

>[!Note]
><span data-ttu-id="c476d-p101">Office 365 ATP 连同 Microsoft 365 企业版 E5 一起提供。如果你有 Microsoft 365 企业版 E3，则可以购买单独的 ATP 许可证。</span><span class="sxs-lookup"><span data-stu-id="c476d-p101">Office 365 ATP is included with Microsoft 365 Enterprise E5. If you have Microsoft 365 Enterprise E3, you can purchase individual licenses for ATP.</span></span>
>

<span data-ttu-id="c476d-120">若要启用 Office 365 ATP，请参阅[开启](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton)。</span><span class="sxs-lookup"><span data-stu-id="c476d-120">To enable Office 365 ATP, see [Turn it on](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span></span>

<span data-ttu-id="c476d-121">有关详细信息，请参阅[适用于 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 ATP](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607)。</span><span class="sxs-lookup"><span data-stu-id="c476d-121">For more information, see [Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607).</span></span>


|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="c476d-123">测试实验室指南：配置更高的 Office 365 安全性</span><span class="sxs-lookup"><span data-stu-id="c476d-123">Test Lab Guide: Configure increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="c476d-124">作为临时检查点，请查看对应于此步骤的[退出条件](infoprotect-exit-criteria.md#crit-infoprotect-step4)。</span><span class="sxs-lookup"><span data-stu-id="c476d-124">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="c476d-125">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c476d-125">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="c476d-126">配置特权访问管理</span><span class="sxs-lookup"><span data-stu-id="c476d-126">Configure privileged access management</span></span>](infoprotect-configure-privileged-access-management.md)|


