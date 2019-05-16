---
title: 在 Windows 10 设备上自动安装或卸载 Office
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: '从 Microsoft 365 Business 管理中心安装或卸载 Windows 10 设备上的 Office。 '
ms.openlocfilehash: 1e962f51882ddfd97da566858a0a1e6fb56ecbb8
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071952"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a><span data-ttu-id="2602e-103">在 Windows 10 设备上自动安装或卸载 Office</span><span class="sxs-lookup"><span data-stu-id="2602e-103">Automatically install or uninstall Office on Windows 10 devices</span></span>

![指向的标题https://aka.ms/aboutM365preview。](media/m365admincenterchanging.png)

<span data-ttu-id="2602e-105">可从 Microsoft 365 商业版管理中心将 Office 快速轻松地安装到 Windows 10 电脑。</span><span class="sxs-lookup"><span data-stu-id="2602e-105">You can quickly and easily install Office to Windows 10 PCs from the Microsoft 365 Business admin center.</span></span>
  
<span data-ttu-id="2602e-106">若要了解这如何适用于以前安装的 Office 应用，请在开始之前阅读[准备 Office 客户端安装](prepare-for-office-client-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="2602e-106">To understand how this works with previously installed Office apps, read [Prepare for Office client installation](prepare-for-office-client-deployment.md) before you get started.</span></span> 
  
## <a name="manage-office-deployments"></a><span data-ttu-id="2602e-107">管理 Office 部署</span><span class="sxs-lookup"><span data-stu-id="2602e-107">Manage Office deployments</span></span>

1. <span data-ttu-id="2602e-108">使用全局管理员凭据登录[管理中心](https://aka.ms/bcsportal)。</span><span class="sxs-lookup"><span data-stu-id="2602e-108">Sign in to the [admin center](https://aka.ms/bcsportal) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="2602e-109">在" **设备**"卡中，选择" **管理 Office 部署**"。</span><span class="sxs-lookup"><span data-stu-id="2602e-109">On the **Devices** card, choose **Manage Office Deployment**.</span></span>
      <span data-ttu-id="2602e-110">如果看不到 "**设备操作**" 卡, 请在管理中心**主页**上, 单击 "**添加**" (+) 以将其添加到管理员主页。</span><span class="sxs-lookup"><span data-stu-id="2602e-110">If you do not see the **Device actions** card, in the admin center **Home** page, click **Add** (+) to add it to your admin home.</span></span>
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. <span data-ttu-id="2602e-112">在打开的" **管理 Office 部署**"窗格中，选择" **添加组**"，然后选择要使用的组。</span><span class="sxs-lookup"><span data-stu-id="2602e-112">On the **Manage Office deployment** pane that opens, choose **Add a group**, then select the groups you want use.</span></span>
    
4. <span data-ttu-id="2602e-113">添加一个或多个要使用的组后，从" **部署操作**"下拉列表中，选择" **尽快安装 Office**"或" **卸载 Office**"。</span><span class="sxs-lookup"><span data-stu-id="2602e-113">After you have added the group or groups you want to use, from the **Deployment Action** drop-down, select either **Install Office as soon as possible** or **Uninstall Office**.</span></span>
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. <span data-ttu-id="2602e-115">Choose **Next** \> review the settings and then choose **Confirm**.</span><span class="sxs-lookup"><span data-stu-id="2602e-115">Choose **Next** \> review the settings and then choose **Confirm**.</span></span>
    
<span data-ttu-id="2602e-116">将在你使用的一个或多个组所指定的用户所拥有的设备上自动安装或卸载 32 位的 Office。</span><span class="sxs-lookup"><span data-stu-id="2602e-116">A 32-bit Office will be automatically installed, or uninstalled in the devices owned by users specified by the group or groups you used.</span></span>
  
<span data-ttu-id="2602e-117">可在计算机上打开为 Office 安装选择的任务管理器，然后查找 Microsoft Office 即点即用进程进行验证。</span><span class="sxs-lookup"><span data-stu-id="2602e-117">To verify you can open the Task Manager on a computer that was selected for an Office install and look for Microsoft Office Click-to-Run process.</span></span>
  


