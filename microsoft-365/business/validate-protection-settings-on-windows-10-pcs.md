---
title: 验证 Windows 10 电脑上的应用保护设置
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
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 了解如何在 Windows 10 设备中验证 Microsoft 365 商业应用保护设置。
ms.openlocfilehash: 7710accf9a3cd1db788dd5215ab6d7bbb97e48a6
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074372"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="3d05f-103">验证 Windows 10 电脑上的应用保护设置</span><span class="sxs-lookup"><span data-stu-id="3d05f-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="3d05f-104">确定用户不能将公司数据复制到企业设备上的个人文件中</span><span class="sxs-lookup"><span data-stu-id="3d05f-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="3d05f-p101">[设置应用保护策略](protection-settings-for-windows-10-devices.md) 后，可能需要几个小时策略才会在用户的设备上生效。如果将公司拥有的设备上的" **防止用户将公司数据复制到个人文件，并强制要求将工作文件保存到 OneDrive for Business**"设置调整为" **打开**"状态，则可以在用户连接到 Azure AD 并登录之后在其设备上选中此选项。</span><span class="sxs-lookup"><span data-stu-id="3d05f-p101">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices. If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they have connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="3d05f-107">**验证连接设置**</span><span class="sxs-lookup"><span data-stu-id="3d05f-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="3d05f-p102">按[为 Microsoft 365 商业版用户设置 Windows 设备](set-up-windows-devices.md)所述，使用 Microsoft 365 商业版凭据登录并连接到 Azure AD 后，请转到" **Windows 设置**"\>" **帐户**"\>" **访问工作或学校帐户**"。选择" **连接到 \<租户名称\> Azure AD**"，然后选择" **信息**"。</span><span class="sxs-lookup"><span data-stu-id="3d05f-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="3d05f-111">在 "**管理者** \<租户名称\> " 页上, 您可以看到包含**管理服务器地址**的**连接信息**, 如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="3d05f-111">On the **Managed by** \<tenant name\> page you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="3d05f-113">**验证不能将公司数据粘贴到非托管的应用**</span><span class="sxs-lookup"><span data-stu-id="3d05f-113">**Verify that you cannot paste company data to a non-managed app**</span></span>
  
1. <span data-ttu-id="3d05f-114">打开由 Microsoft 365 商业版安装的 Outlook 2016。</span><span class="sxs-lookup"><span data-stu-id="3d05f-114">Open Outlook 2016 that was installed by Microsoft 365 Business.</span></span>
    
2. <span data-ttu-id="3d05f-115">打开一封电子邮件，并复制其中的某些内容。</span><span class="sxs-lookup"><span data-stu-id="3d05f-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="3d05f-116">打开记事本，并尝试将该内容粘贴到其中。</span><span class="sxs-lookup"><span data-stu-id="3d05f-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="3d05f-117">会收到错误，表示应用不能访问该内容。</span><span class="sxs-lookup"><span data-stu-id="3d05f-117">You will receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="3d05f-119">但是，可以将相同的内容粘贴到 Word 2016。</span><span class="sxs-lookup"><span data-stu-id="3d05f-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="3d05f-120">验证用户不能将公司数据复制到个人设备上的个人文件中</span><span class="sxs-lookup"><span data-stu-id="3d05f-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="3d05f-121">**验证连接设置**</span><span class="sxs-lookup"><span data-stu-id="3d05f-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="3d05f-122">在作为本地用户登录到其中的 Windows 10 个人设备上，转到" **Windows 设置**"并单击或点击" **帐户**"\>" **访问工作或学校帐户**"。</span><span class="sxs-lookup"><span data-stu-id="3d05f-122">On your Windows 10 personal device where you are logged in as a local user, go to **Windows Settings** and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="3d05f-123">在" **访问工作或学校帐户**"下选择" **连接**"。</span><span class="sxs-lookup"><span data-stu-id="3d05f-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="3d05f-124">在" **设置工作或学校帐户**"对话框\>" **登录**"中，输入 Microsoft 365 商业版凭据。</span><span class="sxs-lookup"><span data-stu-id="3d05f-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="3d05f-125">在" **访问工作或学校帐户**"页面，选择" **工作或学校帐户**"，然后选择" **信息**"。</span><span class="sxs-lookup"><span data-stu-id="3d05f-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Work or school account dalog.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="3d05f-127">在" **访问工作或学校帐户**"页面，可以看到" **连接信息**"，其中包含如下图所示的" **管理服务器地址**"，还包括单词  *wip*  和  *mam*  。</span><span class="sxs-lookup"><span data-stu-id="3d05f-127">On the **Access work or school** page you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="3d05f-129">**验证不能将公司数据粘贴到非托管的应用**</span><span class="sxs-lookup"><span data-stu-id="3d05f-129">**Verify that you cannot paste company data to a non-managed app**</span></span>
  
1. <span data-ttu-id="3d05f-130">打开 Outlook 2016，并添加 Microsoft 365 商业版 帐户（如有必要），然后使用 Microsoft 365 商业版凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="3d05f-130">Open Outlook 2016 and add your Microsoft 365 Business account if necessary and sign in with your Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="3d05f-131">打开一封电子邮件，并复制其中的某些内容。</span><span class="sxs-lookup"><span data-stu-id="3d05f-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="3d05f-132">打开记事本，并尝试将该内容粘贴到其中。</span><span class="sxs-lookup"><span data-stu-id="3d05f-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="3d05f-133">会收到错误，表示应用不能访问该内容。</span><span class="sxs-lookup"><span data-stu-id="3d05f-133">You will receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="3d05f-135">但是，可以将相同的内容粘贴到 Word 2016。</span><span class="sxs-lookup"><span data-stu-id="3d05f-135">You can, however, paste the same content into Word 2016.</span></span>
    

