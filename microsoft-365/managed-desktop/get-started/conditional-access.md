---
title: 调整条件访问
description: 如何排除某些 Microsoft 帐户
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1b91186837ad558965d675f82d013a7081c7c7ec
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012445"
---
# <a name="adjust-conditional-access"></a><span data-ttu-id="bd9bf-104">调整条件访问</span><span class="sxs-lookup"><span data-stu-id="bd9bf-104">Adjust conditional access</span></span>

<span data-ttu-id="bd9bf-105">如果您在组织中使用[条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)策略，则必须将其设置为排除某些帐户，以便 Microsoft 托管桌面能够正常工作。</span><span class="sxs-lookup"><span data-stu-id="bd9bf-105">If you use [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies in your organization, you'll have to set them to exclude certain accounts so that Microsoft Managed Desktop can work properly.</span></span>

<span data-ttu-id="bd9bf-106">要实现这一点，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="bd9bf-106">To do this, follow these steps:</span></span>

1. <span data-ttu-id="bd9bf-107">请参阅 how [to： Plan a 条件 Access deployment in The Azure Active Directory 中](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps)的 "回滚步骤" 一节。</span><span class="sxs-lookup"><span data-stu-id="bd9bf-107">Refer to the "Rollback steps" section of [How To: Plan your Conditional Access deployment in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span></span>
2. <span data-ttu-id="bd9bf-108">按照中的步骤操作，以排除所有策略的*新式 Workplace Service 帐户*组。</span><span class="sxs-lookup"><span data-stu-id="bd9bf-108">Follow the steps there to exclude the *Modern Workplace Service Accounts* group for all policies.</span></span>


<span data-ttu-id="bd9bf-109">如果您在条件访问方面遇到困难，请与管理员[支持](../working-with-managed-desktop/admin-support.md)联系。</span><span class="sxs-lookup"><span data-stu-id="bd9bf-109">If you have any difficulty with conditional access, contact admin [support](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="bd9bf-110">Microsoft 托管桌面入门步骤</span><span class="sxs-lookup"><span data-stu-id="bd9bf-110">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="bd9bf-111">在管理门户中添加和验证管理员联系人</span><span class="sxs-lookup"><span data-stu-id="bd9bf-111">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="bd9bf-112">调整条件访问（本主题）</span><span class="sxs-lookup"><span data-stu-id="bd9bf-112">Adjust conditional access (this topic)</span></span>
3. [<span data-ttu-id="bd9bf-113">分配许可证</span><span class="sxs-lookup"><span data-stu-id="bd9bf-113">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="bd9bf-114">部署 Intune 公司门户</span><span class="sxs-lookup"><span data-stu-id="bd9bf-114">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="bd9bf-115">启用企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="bd9bf-115">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="bd9bf-116">设置设备</span><span class="sxs-lookup"><span data-stu-id="bd9bf-116">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="bd9bf-117">让用户做好使用设备的准备</span><span class="sxs-lookup"><span data-stu-id="bd9bf-117">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="bd9bf-118">部署应用</span><span class="sxs-lookup"><span data-stu-id="bd9bf-118">Deploy apps</span></span>](deploy-apps.md)