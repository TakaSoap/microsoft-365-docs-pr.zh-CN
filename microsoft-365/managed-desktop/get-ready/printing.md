---
title: 为 Microsoft 托管桌面准备打印资源
description: 确保打印顺利进行的重要步骤
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1588a2c91bcbe0bd381acb6be4f9bd5562810860
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530243"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a><span data-ttu-id="6338f-104">为 Microsoft 托管桌面准备打印资源</span><span class="sxs-lookup"><span data-stu-id="6338f-104">Prepare printing resources for Microsoft Managed Desktop</span></span>

<span data-ttu-id="6338f-105">在准备好在 Microsoft 托管桌面中注册时，应评估打印要求并为您的环境确定正确的方法。</span><span class="sxs-lookup"><span data-stu-id="6338f-105">As you get ready to enroll in Microsoft Managed Desktop, you should evaluate your printing requirements and determine the right approach for your environment.</span></span> <span data-ttu-id="6338f-106">有三个选项：</span><span class="sxs-lookup"><span data-stu-id="6338f-106">You have three options:</span></span>
 
- <span data-ttu-id="6338f-107">部署 Microsoft 混合云打印解决方案，使 Microsoft 托管桌面设备能够更轻松地发现打印机。</span><span class="sxs-lookup"><span data-stu-id="6338f-107">Deploy the Microsoft hybrid cloud print solution to make it easy for Microsoft Managed Desktop devices to discover printers.</span></span> <span data-ttu-id="6338f-108">有关详细信息，请参阅[Deploy Windows Server 混合云打印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。</span><span class="sxs-lookup"><span data-stu-id="6338f-108">For more information, see [Deploy Windows Server Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
- <span data-ttu-id="6338f-109">使用自定义 PowerShell 脚本直接部署打印机。</span><span class="sxs-lookup"><span data-stu-id="6338f-109">Deploy printers directly by using a custom PowerShell script.</span></span> <span data-ttu-id="6338f-110">按照 "[设置本地打印机](#set-up-local-printers)" 部分中的步骤执行此操作。</span><span class="sxs-lookup"><span data-stu-id="6338f-110">Follow the steps in the [Set up local printers](#set-up-local-printers) section to do this.</span></span>
- <span data-ttu-id="6338f-111">使用与加入 Azure Active Directory 域的 Windows 10 设备兼容的非 Microsoft 云打印解决方案。</span><span class="sxs-lookup"><span data-stu-id="6338f-111">Use a non-Microsoft cloud printing solution that is compatible with Windows 10 devices that are joined to an Azure Active Directory domain.</span></span> <span data-ttu-id="6338f-112">解决方案必须满足 Microsoft 托管桌面的软件要求。</span><span class="sxs-lookup"><span data-stu-id="6338f-112">The solution must meet the software requirements for Microsoft Managed Desktop.</span></span> <span data-ttu-id="6338f-113">有关详细信息，请参阅[Microsoft 托管桌面应用程序要求](../service-description/mmd-app-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6338f-113">For more information, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
 
<span data-ttu-id="6338f-114">在所有情况下，如果无法从 Microsoft Update 或 Microsoft Store 中获取打印机驱动程序，则必须自己获取这些驱动程序，并使用 Microsoft Intune 将其打包以部署到 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="6338f-114">In all cases, if the printer drivers are not available from Microsoft Update or the Microsoft Store, you'll have to obtain them yourself and have them packaged for deployment to your Microsoft Managed Desktop devices with Microsoft Intune.</span></span> <span data-ttu-id="6338f-115">有关详细信息，请参阅[Intune 独立-Win32 应用管理](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="6338f-115">For more, see [Intune Standalone - Win32 app management](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)</span></span>

## <a name="set-up-local-printers"></a><span data-ttu-id="6338f-116">设置本地打印机</span><span class="sxs-lookup"><span data-stu-id="6338f-116">Set up local printers</span></span>

<span data-ttu-id="6338f-117">如果您已决定使用自定义 PowerShell 脚本部署打印机并准备好打印资源，请按照以下步骤部署共享打印机：</span><span class="sxs-lookup"><span data-stu-id="6338f-117">If you've decided to deploy printers by using a custom PowerShell script and have prepared the printing resources, follow these steps to have shared printers deployed:</span></span>

1.  <span data-ttu-id="6338f-118">导航到 Microsoft 托管桌面门户。</span><span class="sxs-lookup"><span data-stu-id="6338f-118">Navigate to the Microsoft Managed Desktop portal.</span></span>
2.  <span data-ttu-id="6338f-119">在管理门户的 "**支持 > 支持请求**" 部分中的 "提交标记为*打印机部署*的请求" 中，提供以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="6338f-119">Submit a request labeled *Printer deployment* in the **Support > Support requests** section of the Admin Portal, providing these details:</span></span>
    - <span data-ttu-id="6338f-120">将需要为 Microsoft 托管桌面设备部署的共享打印机位置的所有 UNC 路径</span><span class="sxs-lookup"><span data-stu-id="6338f-120">All UNC paths to shared printer locations that will need to be deployed for Microsoft Managed Desktop devices</span></span>
    - <span data-ttu-id="6338f-121">需要访问这些共享打印机的用户组</span><span class="sxs-lookup"><span data-stu-id="6338f-121">User groups that require access to these shared printers</span></span>
3.  <span data-ttu-id="6338f-122">使用管理门户，我们会在请求完成时通知你。</span><span class="sxs-lookup"><span data-stu-id="6338f-122">Using the Admin Portal, we'll let you know when the request has been completed.</span></span> <span data-ttu-id="6338f-123">最初，我们仅将配置部署到测试部署组中的设备。</span><span class="sxs-lookup"><span data-stu-id="6338f-123">Initially we'll only deploy the configuration to devices in the Test deployment group.</span></span>
4.  <span data-ttu-id="6338f-124">您必须测试和确认配置是否按预期运行。</span><span class="sxs-lookup"><span data-stu-id="6338f-124">You must test and confirm whether the configuration works as you expect.</span></span> <span data-ttu-id="6338f-125">使用支持请求中的 "**讨论**" 选项卡进行答复，让我们知道您何时完成测试。</span><span class="sxs-lookup"><span data-stu-id="6338f-125">Reply by using the **Discussion** tab in the Support request to let us know when you've completed your testing.</span></span>
5.  <span data-ttu-id="6338f-126">然后，我们将配置部署到其他部署组。</span><span class="sxs-lookup"><span data-stu-id="6338f-126">We'll then deploy the configuration to the other deployment groups.</span></span>
