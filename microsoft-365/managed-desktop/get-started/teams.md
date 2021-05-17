---
title: Microsoft Teams
description: 如何在设备上安装 Teams 并随后进行更新
keywords: Microsoft 托管桌面， Microsoft 365， 服务， 文档， 应用， 业务线应用， LOB 应用
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 01a3adc7829bbb94f36649f69ba6ef15dbe6b3c2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920652"
---
# <a name="microsoft-teams"></a><span data-ttu-id="0565c-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0565c-104">Microsoft Teams</span></span>

<span data-ttu-id="0565c-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) 是 [组织的消息传递](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) 应用，它还提供用于实时协作和通信、会议以及文件和应用共享的工作区。</span><span class="sxs-lookup"><span data-stu-id="0565c-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="0565c-106">初始部署</span><span class="sxs-lookup"><span data-stu-id="0565c-106">Initial deployment</span></span>

<span data-ttu-id="0565c-107">大多数硬件供应商尚未将 Teams 作为映像的一部分，因此 Microsoft 托管桌面使用 Microsoft Intune 将 Teams 部署到你的设备。</span><span class="sxs-lookup"><span data-stu-id="0565c-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="0565c-108">所有托管设备都安装了 [Teams .msi](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) 程序包，从而确保登录到设备的所有用户都准备好使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="0565c-108">All managed devices have the [Teams .msi package](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="0565c-109">程序包首次安装完成后，Teams 将自动启动，并将快捷方式添加到桌面。</span><span class="sxs-lookup"><span data-stu-id="0565c-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="0565c-110">Microsoft Intune 更改</span><span class="sxs-lookup"><span data-stu-id="0565c-110">Microsoft Intune changes</span></span>

<span data-ttu-id="0565c-111">Microsoft 托管桌面将两个应用程序添加到 Microsoft Teams 的 Azure AD 组织。</span><span class="sxs-lookup"><span data-stu-id="0565c-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="0565c-112">它们部署到适用于设备的 64 位或 32 位客户端：</span><span class="sxs-lookup"><span data-stu-id="0565c-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="0565c-113">现代工作场所 – Teams 计算机范围安装程序 x64</span><span class="sxs-lookup"><span data-stu-id="0565c-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="0565c-114">现代工作场所 – Teams 计算机范围安装程序 x32</span><span class="sxs-lookup"><span data-stu-id="0565c-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="0565c-115">更新</span><span class="sxs-lookup"><span data-stu-id="0565c-115">Updates</span></span>

<span data-ttu-id="0565c-116">Teams 遵循 Microsoft 365 企业应用版中的单独更新路径，桌面客户端将自动更新自身。</span><span class="sxs-lookup"><span data-stu-id="0565c-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="0565c-117">Teams 每隔几小时检查一次更新，下载更新，然后等待计算机处于空闲状态，然后以无提示方式安装更新。</span><span class="sxs-lookup"><span data-stu-id="0565c-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="0565c-118">Teams 产品组不允许管理员控制更新，因此 Microsoft 托管桌面使用 [标准自动更新频道](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)。</span><span class="sxs-lookup"><span data-stu-id="0565c-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="0565c-119">手动更新 Teams</span><span class="sxs-lookup"><span data-stu-id="0565c-119">Manually updating Teams</span></span>

<span data-ttu-id="0565c-120">单个用户还可以下载更新，具体操作是选择应用右上方的"配置文件"下拉菜单上的"检查    \*\*\*\*   更新"。</span><span class="sxs-lookup"><span data-stu-id="0565c-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="0565c-121">如果更新可用，它将在计算机空闲时下载并静默安装。</span><span class="sxs-lookup"><span data-stu-id="0565c-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="0565c-122">更新的传递优化</span><span class="sxs-lookup"><span data-stu-id="0565c-122">Delivery optimization of updates</span></span>

<span data-ttu-id="0565c-123">Teams 更新的传递优化默认启用，不需要管理员或用户的操作。</span><span class="sxs-lookup"><span data-stu-id="0565c-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span>