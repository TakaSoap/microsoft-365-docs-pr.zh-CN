---
title: Microsoft 365 企业版工作负载
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 将组织用户载入到 Microsoft 365 企业版的工作效率工作负载。
ms.openlocfilehash: 0e1658655c4b97a7e571d1ac09c4b2edcc6c82ce
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268268"
---
# <a name="microsoft-365-for-enterprise-workloads"></a><span data-ttu-id="a5070-103">Microsoft 365 企业版工作负载</span><span class="sxs-lookup"><span data-stu-id="a5070-103">Microsoft 365 for enterprise workloads</span></span>

<span data-ttu-id="a5070-104">为了实现 Microsoft 365 企业版在创造力和团队合作方面的优势，请在基础结构上部署这些工作负载：</span><span class="sxs-lookup"><span data-stu-id="a5070-104">To get the creativity and teamwork benefits of Microsoft 365 for enterprise, deploy these workloads over your foundation infrastructure:</span></span>

- [<span data-ttu-id="a5070-105">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a5070-105">Microsoft Teams</span></span>](teams-workload.md)
- [<span data-ttu-id="a5070-106">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a5070-106">Exchange Online</span></span>](exchangeonline-workload.md)
- [<span data-ttu-id="a5070-107">SharePoint 和 OneDrive</span><span class="sxs-lookup"><span data-stu-id="a5070-107">SharePoint and OneDrive</span></span>](sharepoint-online-onedrive-workload.md)

<span data-ttu-id="a5070-108">有关将整个组织迁移到 Microsoft 365 企业版的常规路线图（其中包括 Microsoft Office 客户端产品、本地 Office Server 产品和基于 Microsoft Windows 的设备），请参阅[迁移](migration-microsoft-365-enterprise-workload.md)文章。</span><span class="sxs-lookup"><span data-stu-id="a5070-108">See the [migration](migration-microsoft-365-enterprise-workload.md) article for a general roadmap to migrate your entire organization to Microsoft 365 for enterprise, which includes Microsoft Office client products, on-premises Office Server products, and Microsoft Windows-based devices.</span></span>

<span data-ttu-id="a5070-109">以下是 Microsoft 365 企业版部署指南中的工作负载：</span><span class="sxs-lookup"><span data-stu-id="a5070-109">Here are the workloads in the overall Microsoft 365 for enterprise deployment guide:</span></span>

![Microsoft 365 企业版部署指南中的工作负载](../media/deploy-workloads/m365-deploy-content-arch-workloads.png)

## <a name="foundation-infrastructure-prerequisites"></a><span data-ttu-id="a5070-111">基础结构先决条件</span><span class="sxs-lookup"><span data-stu-id="a5070-111">Foundation infrastructure prerequisites</span></span>

<span data-ttu-id="a5070-112">*理想情况下*，你应该在配置[基础结构](deploy-foundation-infrastructure.md)的所有阶段后部署工作负载。</span><span class="sxs-lookup"><span data-stu-id="a5070-112">*Ideally*, you should deploy workloads after you have configured all of the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span> <span data-ttu-id="a5070-113">这可确保所有基础层设施都准备就绪，以便为用户及其设备提供集成、安全性和最佳体验。</span><span class="sxs-lookup"><span data-stu-id="a5070-113">This ensures that all of the underlying foundation layers are in place to provide integration, security, and the best experience for your users and their devices.</span></span>

| <span data-ttu-id="a5070-114">阶段</span><span class="sxs-lookup"><span data-stu-id="a5070-114">Phase</span></span> | <span data-ttu-id="a5070-115">结果</span><span class="sxs-lookup"><span data-stu-id="a5070-115">Result</span></span> |
|:-------|:-----|
| <span data-ttu-id="a5070-116">网络</span><span class="sxs-lookup"><span data-stu-id="a5070-116">Network</span></span> | <span data-ttu-id="a5070-117">你的网络已更新，可以为 Microsoft 365 云服务提供最佳性能。</span><span class="sxs-lookup"><span data-stu-id="a5070-117">Your network is updated for optimum performance to Microsoft 365 cloud services.</span></span> |
| <span data-ttu-id="a5070-118">标识</span><span class="sxs-lookup"><span data-stu-id="a5070-118">Identity</span></span> | <span data-ttu-id="a5070-119">通过对用户帐户进行强身份验证和保护管理员帐户来同步和保护身份。</span><span class="sxs-lookup"><span data-stu-id="a5070-119">Identity is synchronized and secured with strong authentication for user accounts and protection for admin accounts.</span></span> |
| <span data-ttu-id="a5070-120">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="a5070-120">Windows 10 Enterprise</span></span> | <span data-ttu-id="a5070-121">运行 Windows 7 或 Windows 8.1 的计算机可以升级至 Windows 10 企业版，并且新设备已安装了 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="a5070-121">Your computers running Windows 7 or Windows 8.1 can upgrade to Windows 10 Enterprise and new devices are installed with Windows 10 Enterprise.</span></span> |
| <span data-ttu-id="a5070-122">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="a5070-122">Microsoft 365 Apps for enterprise</span></span> | <span data-ttu-id="a5070-123">现有 Microsoft Office 用户可以升级到 Microsoft 365 企业应用版。</span><span class="sxs-lookup"><span data-stu-id="a5070-123">Your existing users of Microsoft Office can upgrade to Microsoft 365 Apps for enterprise.</span></span> |
| <span data-ttu-id="a5070-124">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="a5070-124">Mobile device management</span></span> | <span data-ttu-id="a5070-125">可以注册和管理你的设备。</span><span class="sxs-lookup"><span data-stu-id="a5070-125">Your devices can be enrolled and managed.</span></span> |
| <span data-ttu-id="a5070-126">信息保护</span><span class="sxs-lookup"><span data-stu-id="a5070-126">Information protection</span></span> | <span data-ttu-id="a5070-127">已配置 Office 365 信息保护功能，并且你的敏感度标签或 Azure 信息保护标签已准备好保护文档和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a5070-127">Microsoft 365 information protection features are configured and your sensitivity or Azure Information Protection labels are ready to protect documents and email.</span></span> |

<span data-ttu-id="a5070-128">请记住，这是理想方案，可能需要一些时间来规划、配置、测试和试用，尤其是在具有现有基础架构和多个位置的大型组织中。</span><span class="sxs-lookup"><span data-stu-id="a5070-128">Remember that this is ideal and can take some time to plan for, configure, test, and pilot, especially in large organizations with existing infrastructure and multiple locations.</span></span> <span data-ttu-id="a5070-129">不必在所有位置完成所有这些阶段，也可快速从 Microsoft 365 企业版中获得业务价值。</span><span class="sxs-lookup"><span data-stu-id="a5070-129">Completing all of these phases in all locations is not necessary for you to more quickly get business value from Microsoft 365 for enterprise.</span></span> 

<span data-ttu-id="a5070-130">以下是一些可立即部署的常见工作负载：</span><span class="sxs-lookup"><span data-stu-id="a5070-130">Here are some common workloads to deploy right away:</span></span> 

- <span data-ttu-id="a5070-131">向用户推出基础架构的**标识**阶段后，许多组织都会部署：</span><span class="sxs-lookup"><span data-stu-id="a5070-131">After the **Identity** phase of the foundation infrastructure is rolled out to users, many organizations deploy:</span></span>
  - <span data-ttu-id="a5070-132">[Microsoft 365 企业应用版](office365proplus-infrastructure.md)加上 [OneDrive](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="a5070-132">[Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md) combined with [OneDrive](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).</span></span> <span data-ttu-id="a5070-133">Microsoft 365 企业应用版提供了新式身份验证的安全性，以及最新 Microsoft Office 客户端的用户体验。</span><span class="sxs-lookup"><span data-stu-id="a5070-133">Microsoft 365 Apps for enterprise provides the security of modern authentication and the user experience of the latest Microsoft Office client.</span></span> <span data-ttu-id="a5070-134">将用户的个人文件迁移到 OneDrive 可以减少对基础架构以及为主文件夹和驱动器提供支持的需要。</span><span class="sxs-lookup"><span data-stu-id="a5070-134">The migration of user's personal files to OneDrive reduces infrastructure and the need to support home folders and drives.</span></span>
  - <span data-ttu-id="a5070-135">[Exchange Online](exchangeonline-workload.md)，以便用户可以开始使用基于云的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a5070-135">[Exchange Online](exchangeonline-workload.md) so that users can begin using cloud-based email.</span></span>
- <span data-ttu-id="a5070-136">如果你不需要在云中存储高度管控的数字资产，请在进行**信息保护**阶段之前为用户部署 [Microsoft Teams](teams-workload.md) 和 [SharePoint](sharepoint-online-onedrive-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="a5070-136">If you don't have an immediate need for storing highly regulated digital assets in the cloud, deploy [Microsoft Teams](teams-workload.md) and [SharePoint](sharepoint-online-onedrive-workload.md) for your users prior to the **Information protection** phase.</span></span>

<span data-ttu-id="a5070-137">必须确定采用何种最佳方式来排序和部署基础结构先决条件阶段的配置，以满足业务需求。</span><span class="sxs-lookup"><span data-stu-id="a5070-137">You must decide on how to best order and deploy the configuration of prerequisite phases of foundation infrastructure to meet your business needs.</span></span>

### <a name="best-practice"></a><span data-ttu-id="a5070-138">最佳做法</span><span class="sxs-lookup"><span data-stu-id="a5070-138">Best practice</span></span>

<span data-ttu-id="a5070-139">我们强烈建议你在将用户载入任何工作负载或方案之前部署并推出基础架构的**标识**阶段。</span><span class="sxs-lookup"><span data-stu-id="a5070-139">We highly recommend that you deploy and roll out the **Identity** phase of the foundation infrastructure prior to onboarding your users to any workloads or scenarios.</span></span>

<span data-ttu-id="a5070-140">**标识**阶段可确保基于云的标识（无论是仅限云还是与本地 Active Directory 域服务 (AD DS) 同步）包含用于管理身份验证和访问的用户和计算机帐户及组。</span><span class="sxs-lookup"><span data-stu-id="a5070-140">The **Identity** phase ensures that your cloud-based identity, whether cloud-only or synchronized with your on-premises Active Directory Domain Services (AD DS), contains the user and computer accounts and groups to manage authentication and access.</span></span> <span data-ttu-id="a5070-141">将组织的数字资产置于 Microsoft 365 云中之前，需要对所有用户进行强身份验证并为管理员帐户提供强大的保护。</span><span class="sxs-lookup"><span data-stu-id="a5070-141">Strong authentication for all your users along with strong protection of admin accounts is required before placing your organization's digital assets in the Microsoft 365 cloud.</span></span>

<span data-ttu-id="a5070-142">虽然是基础性的并且对整体性能非常重要，在将用户载入工作负载的过程中，可以推出**网络**阶段，而你知道 Microsoft 365 工作负载和服务性能将随着时间的推移而提高。</span><span class="sxs-lookup"><span data-stu-id="a5070-142">Although foundational and very important to overall performance, the rollout of the **Networking** phase can be in progress while onboarding your users to workloads, with the understanding that Microsoft 365 workload and service performance will improve over time.</span></span> <span data-ttu-id="a5070-143">对于具有多个位置、混合边缘设备和 Internet 连接的企业组织尤其如此。</span><span class="sxs-lookup"><span data-stu-id="a5070-143">This is especially true for enterprise organizations with multiple locations and a mixture of edge devices and Internet connections.</span></span>
