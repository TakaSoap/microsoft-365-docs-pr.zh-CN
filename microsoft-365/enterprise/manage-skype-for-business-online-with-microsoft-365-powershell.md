---
title: 使用 PowerShell 管理 Skype for Business Online
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: 使用 PowerShell for Microsoft 365 管理 Skype for Business Online 策略、每用户策略和会议设置。
ms.openlocfilehash: 1992edfb6d1c141c7ed4db22064960873b768865
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "50514952"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="a2ba6-103">使用 PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a2ba6-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="a2ba6-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="a2ba6-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a2ba6-105">Skype for Business Online 管理员负责管理策略。</span><span class="sxs-lookup"><span data-stu-id="a2ba6-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="a2ba6-106">虽然你可以在 Microsoft 365 管理中心中执行其中一些任务，但在 PowerShell 中执行其他任务更容易。</span><span class="sxs-lookup"><span data-stu-id="a2ba6-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="a2ba6-107">准备工作</span><span class="sxs-lookup"><span data-stu-id="a2ba6-107">Before you start</span></span>

  > [!Note]
   > <span data-ttu-id="a2ba6-108">Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="a2ba6-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="a2ba6-109">如果你使用的是最新 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="a2ba6-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
<span data-ttu-id="a2ba6-110">安装 [Teams PowerShell 模块](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="a2ba6-110">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>


## <a name="connect-using-admin-credentials"></a><span data-ttu-id="a2ba6-111">使用管理员凭据连接</span><span class="sxs-lookup"><span data-stu-id="a2ba6-111">Connect using admin credentials</span></span>

1. <span data-ttu-id="a2ba6-112">打开 Windows PowerShell 命令提示符窗口并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a2ba6-112">Open a Windows PowerShell command prompt window and run the following commands:</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

2. <span data-ttu-id="a2ba6-113">在 “**Windows PowerShell 凭据请求**”对话框中，键入你的 管理员帐户名和密码，然后选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="a2ba6-113">In the **Windows PowerShell Credential Request** dialog box, type your administrator account name and password, and then select **OK**.</span></span>


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="a2ba6-114">使用具有多重身份验证的管理员帐户进行连接</span><span class="sxs-lookup"><span data-stu-id="a2ba6-114">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="a2ba6-115">打开 Windows PowerShell 命令提示符窗口并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a2ba6-115">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

2. <span data-ttu-id="a2ba6-116">系统提示时，输入 Skype for Business Online 管理员帐户名称。</span><span class="sxs-lookup"><span data-stu-id="a2ba6-116">When prompted enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="a2ba6-117">在“**登录到你的帐户**”对话框中，键入你的 Skype for Business Online 管理员密码，然后选择“**登录**”。</span><span class="sxs-lookup"><span data-stu-id="a2ba6-117">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="a2ba6-118">在“**登录到你的帐户**”对话框中，按照说明添加身份验证信息（如验证码），然后选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="a2ba6-118">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="a2ba6-119">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="a2ba6-119">For more information, see:</span></span>
  
- [<span data-ttu-id="a2ba6-120">使用 PowerShell 管理 Skype for Business Online 策略</span><span class="sxs-lookup"><span data-stu-id="a2ba6-120">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="a2ba6-121">使用 PowerShell 指定每个用户 Skype for Business Online 策略</span><span class="sxs-lookup"><span data-stu-id="a2ba6-121">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="a2ba6-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2ba6-122">See also</span></span>

[<span data-ttu-id="a2ba6-123">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a2ba6-123">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a2ba6-124">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="a2ba6-124">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="a2ba6-125">Skype for Business PowerShell cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="a2ba6-125">Skype for Business PowerShell cmdlet references</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
