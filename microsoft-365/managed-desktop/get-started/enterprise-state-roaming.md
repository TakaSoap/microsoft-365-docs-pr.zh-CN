---
title: 启用企业状态漫游
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 709a231f1c3f401ceeee2b3aaf99ff275f107e30
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409112"
---
# <a name="enable-enterprise-state-roaming"></a><span data-ttu-id="08a43-103">启用企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="08a43-103">Enable Enterprise State Roaming</span></span>

<span data-ttu-id="08a43-104">[Enterprise状态漫游](/azure/active-directory/devices/enterprise-state-roaming-overview)允许用户将用户和应用程序设置数据安全地同步到云。</span><span class="sxs-lookup"><span data-stu-id="08a43-104">[Enterprise State Roaming](/azure/active-directory/devices/enterprise-state-roaming-overview) lets users securely synchronize user and application settings data to the cloud.</span></span> <span data-ttu-id="08a43-105">这意味着无论登录哪个设备，Windows具有相同的体验。</span><span class="sxs-lookup"><span data-stu-id="08a43-105">This means they'll have the same experience no matter which Windows device they sign into.</span></span> <span data-ttu-id="08a43-106">例如，如果你将其其中一个Microsoft 托管桌面设备替换为新设备，则其外观和行为与最后一个设备完全相同。</span><span class="sxs-lookup"><span data-stu-id="08a43-106">For example, if you replace one of their Microsoft Managed Desktop devices with a new one, it will look and behave exactly the same as the last one.</span></span> <span data-ttu-id="08a43-107">Enterprise状态漫游是一项可选的 Microsoft 托管桌面 服务功能，你可以为用户配置该功能，并且不会作为自定义服务的一Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="08a43-107">Enterprise State Roaming is an optional feature for the Microsoft Managed Desktop service that you can configure for your users and isn't included or managed as part of Microsoft Managed Desktop.</span></span>

<span data-ttu-id="08a43-108">若要启用Enterprise状态漫游，请按照启用Enterprise[状态漫游中的](/azure/active-directory/devices/enterprise-state-roaming-enable)步骤Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="08a43-108">To enable Enterprise State Roaming, follow the steps in [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

>[!NOTE]
><span data-ttu-id="08a43-109">如果你启用Enterprise漫游，你的首选语言列表将覆盖在设备设置期间选择的语言。</span><span class="sxs-lookup"><span data-stu-id="08a43-109">If you enable Enterprise State Roaming, your preferred language list will overwrite the language selected during device setup.</span></span> <span data-ttu-id="08a43-110">虽然用户可以轻松修复此问题，但最初可能会导致本地化体验不一致。</span><span class="sxs-lookup"><span data-stu-id="08a43-110">Although users can fix this easily, it could cause an inconsistent localization experience initially.</span></span> <span data-ttu-id="08a43-111">在Enterprise之前，确定状态漫游是否适合你的用户。</span><span class="sxs-lookup"><span data-stu-id="08a43-111">Determine if Enterprise State Roaming is right for your users before setting up devices.</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="08a43-112">开始使用 Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="08a43-112">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="08a43-113">在管理门户中添加和验证管理员联系人</span><span class="sxs-lookup"><span data-stu-id="08a43-113">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="08a43-114">调整条件访问</span><span class="sxs-lookup"><span data-stu-id="08a43-114">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="08a43-115">分配许可证</span><span class="sxs-lookup"><span data-stu-id="08a43-115">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="08a43-116">部署 Intune 公司门户</span><span class="sxs-lookup"><span data-stu-id="08a43-116">Deploy Intune Company Portal</span></span>](company-portal.md)
5. <span data-ttu-id="08a43-117">本主题Enterprise启用 (状态漫游) </span><span class="sxs-lookup"><span data-stu-id="08a43-117">Enable Enterprise State Roaming (this topic)</span></span>
6. [<span data-ttu-id="08a43-118">设置设备</span><span class="sxs-lookup"><span data-stu-id="08a43-118">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="08a43-119">让用户做好使用设备的准备</span><span class="sxs-lookup"><span data-stu-id="08a43-119">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="08a43-120">部署应用</span><span class="sxs-lookup"><span data-stu-id="08a43-120">Deploy apps</span></span>](deploy-apps.md)
