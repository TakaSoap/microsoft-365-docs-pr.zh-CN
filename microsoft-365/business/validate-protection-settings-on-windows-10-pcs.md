---
title: 验证 Windows 10 电脑上的应用保护设置
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 在 Windows 10 设备上验证 Microsoft 365 商业应用保护设置，并验证用户不能将公司数据复制到个人文件或非托管应用。
ms.openlocfilehash: 4d3d7e950311ac32606e700ebb35bf026ae091cc
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2020
ms.locfileid: "42549989"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="ca6c2-103">验证 Windows 10 电脑上的应用保护设置</span><span class="sxs-lookup"><span data-stu-id="ca6c2-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="ca6c2-104">确定用户不能将公司数据复制到企业设备上的个人文件中</span><span class="sxs-lookup"><span data-stu-id="ca6c2-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="ca6c2-105">[设置应用保护策略](protection-settings-for-windows-10-devices.md) 后，可能需要几个小时策略才会在用户的设备上生效。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-105">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="ca6c2-106">如果启用了 "**阻止用户将公司数据复制到个人文件，并强制他们将公司拥有的工作文件保存到 OneDrive for** business**设置"，** 则可以在用户的设备连接到 Azure AD 并登录后对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-106">If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they've connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="ca6c2-107">**验证连接设置**</span><span class="sxs-lookup"><span data-stu-id="ca6c2-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="ca6c2-p102">按[为 Microsoft 365 商业版用户设置 Windows 设备](set-up-windows-devices.md)所述，使用 Microsoft 365 商业版凭据登录并连接到 Azure AD 后，请转到" **Windows 设置**"\>" **帐户**"\>" **访问工作或学校帐户**"。选择" **连接到 \<租户名称\> Azure AD**"，然后选择" **信息**"。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="ca6c2-111">在 "**管理者** \<租户名称\> " 页上，您可以看到包含**管理服务器地址**的**连接信息**，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-111">On the **Managed by** \<tenant name\> page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="ca6c2-113">**确认无法将公司数据粘贴到非托管应用中**</span><span class="sxs-lookup"><span data-stu-id="ca6c2-113">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="ca6c2-114">打开由 Microsoft 365 商业版安装的 Outlook 2016。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-114">Open Outlook 2016 that was installed by Microsoft 365 Business.</span></span>
    
2. <span data-ttu-id="ca6c2-115">打开一封电子邮件，并复制其中的某些内容。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="ca6c2-116">打开记事本，并尝试将该内容粘贴到其中。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="ca6c2-117">你将收到一条错误，指出应用无法访问内容。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-117">You'll receive an error that states the app can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="ca6c2-119">但是，可以将相同的内容粘贴到 Word 2016。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="ca6c2-120">验证用户不能将公司数据复制到个人设备上的个人文件中</span><span class="sxs-lookup"><span data-stu-id="ca6c2-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="ca6c2-121">**验证连接设置**</span><span class="sxs-lookup"><span data-stu-id="ca6c2-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="ca6c2-122">在以本地用户身份登录的 windows 10 个人设备上，转到 " **Windows 设置**"，然后单击或点击 "**帐户** \> **访问工作或学校**"。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-122">On your Windows 10 personal device where you're logged in as a local user, go to **Windows Settings**, and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="ca6c2-123">在" **访问工作或学校帐户**"下选择" **连接**"。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="ca6c2-124">在" **设置工作或学校帐户**"对话框\>" **登录**"中，输入 Microsoft 365 商业版凭据。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="ca6c2-125">在" **访问工作或学校帐户**"页面，选择" **工作或学校帐户**"，然后选择" **信息**"。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![单击或点击 "工作或学校帐户" 对话框上的 "信息"。](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="ca6c2-127">在 "**访问工作或学校**" 页面上，您可以看到包含**管理服务器地址**的**连接信息**，如下图中所示，并在中包括 " *wip* " 和 " *mam* " 一词。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-127">On the **Access work or school** page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="ca6c2-129">**确认无法将公司数据粘贴到非托管应用中**</span><span class="sxs-lookup"><span data-stu-id="ca6c2-129">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="ca6c2-130">打开 Outlook 2016，并添加 Microsoft 365 商业版 帐户（如有必要），然后使用 Microsoft 365 商业版凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-130">Open Outlook 2016 and add your Microsoft 365 Business account if necessary and sign in with your Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="ca6c2-131">打开一封电子邮件，并复制其中的某些内容。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="ca6c2-132">打开记事本，并尝试将该内容粘贴到其中。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="ca6c2-133">您将收到一条错误，说明应用程序无法访问内容。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-133">You'll receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="ca6c2-135">但是，可以将相同的内容粘贴到 Word 2016。</span><span class="sxs-lookup"><span data-stu-id="ca6c2-135">You can, however, paste the same content into Word 2016.</span></span>
    

