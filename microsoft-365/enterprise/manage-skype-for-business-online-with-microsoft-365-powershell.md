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
ms.openlocfilehash: d50f35d7d5e81622eb8dfc3bbf8328a8c43e9676
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430030"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="432e8-103">使用 PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="432e8-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="432e8-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="432e8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="432e8-105">Skype for Business Online 管理员负责管理策略。</span><span class="sxs-lookup"><span data-stu-id="432e8-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="432e8-106">虽然你可以在 Microsoft 365 管理中心中执行其中一些任务，但在 PowerShell 中执行其他任务更容易。</span><span class="sxs-lookup"><span data-stu-id="432e8-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="432e8-107">准备工作</span><span class="sxs-lookup"><span data-stu-id="432e8-107">Before you start</span></span>

<span data-ttu-id="432e8-108">下载并安装 [Skype for Business Online Windows PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366)，然后重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="432e8-108">Download and install the [Skype for Business Online Windows PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer.</span></span>


## <a name="connect-using-skype-for-business-online-admin-credentials"></a><span data-ttu-id="432e8-109">使用 Skype for Business Online 管理员凭据进行连接</span><span class="sxs-lookup"><span data-stu-id="432e8-109">Connect using Skype for Business Online admin credentials</span></span>

1. <span data-ttu-id="432e8-110">打开 Windows PowerShell 命令提示符窗口并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="432e8-110">Open a Windows PowerShell command prompt window and run the following commands:</span></span>
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="432e8-111">在“**Windows PowerShell 凭据请求**”对话框中，键入你的 Skype for Business Online 管理员帐户名和密码，然后选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="432e8-111">In the **Windows PowerShell Credential Request** dialog box, type your Skype for Business Online administrator account name and password, and then select **OK**.</span></span>


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="432e8-112">使用具有多重身份验证的管理员帐户进行连接</span><span class="sxs-lookup"><span data-stu-id="432e8-112">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="432e8-113">打开 Windows PowerShell 命令提示符窗口并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="432e8-113">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="432e8-114">当出现 **New-CsOnlineSession** 命令提示时，请输入 Skype for Business Online 管理员帐户名称。</span><span class="sxs-lookup"><span data-stu-id="432e8-114">When prompted by the **New-CsOnlineSession** command, enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="432e8-115">在“**登录到你的帐户**”对话框中，键入你的 Skype for Business Online 管理员密码，然后选择“**登录**”。</span><span class="sxs-lookup"><span data-stu-id="432e8-115">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="432e8-116">在“**登录到你的帐户**”对话框中，按照说明添加身份验证信息（如验证码），然后选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="432e8-116">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="432e8-117">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="432e8-117">For more information, see:</span></span>
  
- [<span data-ttu-id="432e8-118">使用 PowerShell 管理 Skype for Business Online 策略</span><span class="sxs-lookup"><span data-stu-id="432e8-118">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="432e8-119">使用 PowerShell 指定每个用户 Skype for Business Online 策略</span><span class="sxs-lookup"><span data-stu-id="432e8-119">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="432e8-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="432e8-120">See also</span></span>

[<span data-ttu-id="432e8-121">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="432e8-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="432e8-122">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="432e8-122">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="432e8-123">Skype for Business PowerShell cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="432e8-123">Skype for Business PowerShell cmdlet references</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
