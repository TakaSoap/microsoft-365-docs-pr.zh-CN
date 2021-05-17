---
title: 为 Microsoft 托管桌面准备打印资源
description: 确保打印工作平稳的重要步骤
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 971644aafabda733bf745fae278bdfeeed3282e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574543"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a><span data-ttu-id="15e45-104">为 Microsoft 托管桌面准备打印资源</span><span class="sxs-lookup"><span data-stu-id="15e45-104">Prepare printing resources for Microsoft Managed Desktop</span></span>

<span data-ttu-id="15e45-105">当你准备好注册Microsoft 托管桌面，你应该评估打印要求并确定适合你的环境的方法。</span><span class="sxs-lookup"><span data-stu-id="15e45-105">As you get ready to enroll in Microsoft Managed Desktop, you should evaluate your printing requirements and determine the right approach for your environment.</span></span> <span data-ttu-id="15e45-106">有三个选项：</span><span class="sxs-lookup"><span data-stu-id="15e45-106">You have three options:</span></span>
 
- <span data-ttu-id="15e45-107">部署 Microsoft 通用打印解决方案，使设备Microsoft 托管桌面发现打印机。</span><span class="sxs-lookup"><span data-stu-id="15e45-107">Deploy the Microsoft Universal Print solution to make it easy for Microsoft Managed Desktop devices to discover printers.</span></span> <span data-ttu-id="15e45-108">有关详细信息，请参阅 [什么是通用打印](/universal-print/fundamentals/universal-print-whatis)。</span><span class="sxs-lookup"><span data-stu-id="15e45-108">For more information, see [What is Universal Print](/universal-print/fundamentals/universal-print-whatis).</span></span>
- <span data-ttu-id="15e45-109">使用自定义 PowerShell 脚本直接部署打印机。</span><span class="sxs-lookup"><span data-stu-id="15e45-109">Deploy printers directly by using a custom PowerShell script.</span></span> <span data-ttu-id="15e45-110">按照设置本地打印机 [部分中的步骤](#set-up-local-printers) 操作。</span><span class="sxs-lookup"><span data-stu-id="15e45-110">Follow the steps in the [Set up local printers](#set-up-local-printers) section.</span></span>
- <span data-ttu-id="15e45-111">使用与加入域的 Windows 10 兼容的非 Microsoft 云打印Azure Active Directory解决方案。</span><span class="sxs-lookup"><span data-stu-id="15e45-111">Use a non-Microsoft cloud printing solution that is compatible with Windows 10 devices that are joined to an Azure Active Directory domain.</span></span> <span data-ttu-id="15e45-112">解决方案必须满足软件要求，Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="15e45-112">The solution must meet the software requirements for Microsoft Managed Desktop.</span></span> <span data-ttu-id="15e45-113">有关详细信息，请参阅应用[Microsoft 托管桌面要求](../service-description/mmd-app-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="15e45-113">For more information, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
 
<span data-ttu-id="15e45-114">在所有情况下，如果打印机驱动程序在 Microsoft 更新或 Microsoft Store 中不可用，你必须自己获取它们，然后将它们打包，以使用 Microsoft Intune 将其部署到 Microsoft 托管桌面 设备。</span><span class="sxs-lookup"><span data-stu-id="15e45-114">In all cases, if the printer drivers are not available from Microsoft Update or the Microsoft Store, you'll have to obtain them yourself and have them packaged for deployment to your Microsoft Managed Desktop devices with Microsoft Intune.</span></span> <span data-ttu-id="15e45-115">有关详细信息，请参阅 [Intune 独立 - Win32 应用管理](/mem/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="15e45-115">For more, see [Intune Standalone - Win32 app management](/mem/intune/apps/apps-win32-app-management)</span></span>

## <a name="set-up-local-printers"></a><span data-ttu-id="15e45-116">设置本地打印机</span><span class="sxs-lookup"><span data-stu-id="15e45-116">Set up local printers</span></span>

<span data-ttu-id="15e45-117">如果决定使用自定义 PowerShell 脚本部署打印机并准备打印资源，请按照以下步骤部署共享打印机：</span><span class="sxs-lookup"><span data-stu-id="15e45-117">If you've decided to deploy printers by using a custom PowerShell script and have prepared the printing resources, follow these steps to have shared printers deployed:</span></span>

1.  <span data-ttu-id="15e45-118">导航到Microsoft 托管桌面门户。</span><span class="sxs-lookup"><span data-stu-id="15e45-118">Navigate to the Microsoft Managed Desktop portal.</span></span>
2.  <span data-ttu-id="15e45-119">在管理 *门户的"* 支持> **支持** 请求"部分提交标记为"打印机部署"的请求，并提供以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="15e45-119">Submit a request labeled *Printer deployment* in the **Support > Support requests** section of the Admin Portal, providing these details:</span></span>
    - <span data-ttu-id="15e45-120">需要为设备部署的所有共享打印机位置的 UNC Microsoft 托管桌面路径</span><span class="sxs-lookup"><span data-stu-id="15e45-120">All UNC paths to shared printer locations that will need to be deployed for Microsoft Managed Desktop devices</span></span>
    - <span data-ttu-id="15e45-121">需要访问这些共享打印机的用户组</span><span class="sxs-lookup"><span data-stu-id="15e45-121">User groups that require access to these shared printers</span></span>
3.  <span data-ttu-id="15e45-122">使用管理门户，我们将告知你请求完成时间。</span><span class="sxs-lookup"><span data-stu-id="15e45-122">Using the Admin Portal, we'll let you know when the request has been completed.</span></span> <span data-ttu-id="15e45-123">最初，我们将仅将配置部署到测试部署组的设备。</span><span class="sxs-lookup"><span data-stu-id="15e45-123">Initially we'll only deploy the configuration to devices in the Test deployment group.</span></span>
4.  <span data-ttu-id="15e45-124">必须测试并确认配置是否如预期工作。</span><span class="sxs-lookup"><span data-stu-id="15e45-124">You must test and confirm whether the configuration works as you expect.</span></span> <span data-ttu-id="15e45-125">使用支持 **请求中的** "讨论"选项卡进行回复，以在测试完成时告诉我们。</span><span class="sxs-lookup"><span data-stu-id="15e45-125">Reply by using the **Discussion** tab in the Support request to let us know when you've completed your testing.</span></span>
5.  <span data-ttu-id="15e45-126">然后，我们将配置部署到其他部署组。</span><span class="sxs-lookup"><span data-stu-id="15e45-126">We'll then deploy the configuration to the other deployment groups.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="15e45-127">准备步骤</span><span class="sxs-lookup"><span data-stu-id="15e45-127">Steps to get ready</span></span>

1. <span data-ttu-id="15e45-128">Review [Prerequisites for Microsoft 托管桌面](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="15e45-128">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="15e45-129">使用 [准备情况评估工具](readiness-assessment-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="15e45-129">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="15e45-130">来宾帐户的先决条件</span><span class="sxs-lookup"><span data-stu-id="15e45-130">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="15e45-131">Microsoft 托管桌面的网络配置</span><span class="sxs-lookup"><span data-stu-id="15e45-131">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="15e45-132">为 Microsoft 托管桌面准备证书和网络配置文件</span><span class="sxs-lookup"><span data-stu-id="15e45-132">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="15e45-133">为 Microsoft 托管桌面准备本地资源访问权限</span><span class="sxs-lookup"><span data-stu-id="15e45-133">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="15e45-134">Microsoft 托管桌面中的应用</span><span class="sxs-lookup"><span data-stu-id="15e45-134">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="15e45-135">为 Microsoft 托管桌面准备映射的驱动器</span><span class="sxs-lookup"><span data-stu-id="15e45-135">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. <span data-ttu-id="15e45-136">[准备打印资源Microsoft 托管桌面 (](printing.md)本文) </span><span class="sxs-lookup"><span data-stu-id="15e45-136">[Prepare printing resources for Microsoft Managed Desktop](printing.md) (This article)</span></span>
