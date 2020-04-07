---
title: Office 365 部署的多重身份验证计划
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: 了解 Office 365 中的多重身份验证，以及对其进行设置时需要遵循的步骤。
ms.openlocfilehash: e3886387740fe904b9c9458f7b1abf736c3ef83f
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153564"
---
# <a name="plan-for-multi-factor-authentication-for-office-365-deployments"></a><span data-ttu-id="aa066-103">Office 365 部署的多重身份验证计划</span><span class="sxs-lookup"><span data-stu-id="aa066-103">Plan for multi-factor authentication for Office 365 Deployments</span></span>

<span data-ttu-id="aa066-p101">多重身份验证 (MFA) 是一种身份验证方法，要求使用多个验证方法，并向用户登录和交易添加第二层安全。该验证需要任意两个或多个以下验证方法来实现：</span><span class="sxs-lookup"><span data-stu-id="aa066-p101">Multi-factor authentication (MFA) is a method of authentication that requires the use of more than one verification method and adds a second layer of security to user sign-ins and transactions. It works by requiring any two or more of the following verification methods:</span></span>
  
- <span data-ttu-id="aa066-106">随机生成的密码</span><span class="sxs-lookup"><span data-stu-id="aa066-106">A randomly generated pass code</span></span>
    
- <span data-ttu-id="aa066-107">电话联络</span><span class="sxs-lookup"><span data-stu-id="aa066-107">A phone call</span></span>
    
- <span data-ttu-id="aa066-108">智能卡（虚拟或物理）</span><span class="sxs-lookup"><span data-stu-id="aa066-108">A smart card (virtual or physical)</span></span> 
    
- <span data-ttu-id="aa066-109">生物识别设备</span><span class="sxs-lookup"><span data-stu-id="aa066-109">A biometric device</span></span> 
    
## <a name="multi-factor-authentication-in-office-365"></a><span data-ttu-id="aa066-110">Office 365 中的多重身份验证</span><span class="sxs-lookup"><span data-stu-id="aa066-110">Multi-factor authentication in Office 365</span></span>

<span data-ttu-id="aa066-111">Office 365 使用多重身份验证来帮助提供额外的安全性，并通过 Microsoft 365 管理中心进行管理。</span><span class="sxs-lookup"><span data-stu-id="aa066-111">Office 365 uses multi-factor authentication to help provide the extra security and is managed from the Microsoft 365 admin center.</span></span> <span data-ttu-id="aa066-112">Office 365 提供了以下 Azure 多重身份验证功能子集作为订阅的一部分：</span><span class="sxs-lookup"><span data-stu-id="aa066-112">Office 365 offers the following subset of Azure Multi-Factor Authentication capabilities as a part of the subscription:</span></span> 
  
- <span data-ttu-id="aa066-113">能够启用和强制实施针对最终用户的多重身份验证</span><span class="sxs-lookup"><span data-stu-id="aa066-113">The ability to enable and enforce multi-factor authentication for end users</span></span>
    
- <span data-ttu-id="aa066-114">使用移动应用（联机和一次性密码 [OTP]）作为第二身份验证因素</span><span class="sxs-lookup"><span data-stu-id="aa066-114">The use of a mobile app (online and one-time password [OTP]) as a second authentication factor</span></span>
    
- <span data-ttu-id="aa066-115">使用电话联络作为第二身份验证因素</span><span class="sxs-lookup"><span data-stu-id="aa066-115">The use of a phone call as a second authentication factor</span></span>
    
- <span data-ttu-id="aa066-116">使用短消息服务 (SMS) 消息作为第二身份验证因素</span><span class="sxs-lookup"><span data-stu-id="aa066-116">The use of a Short Message Service (SMS) message as a second authentication factor</span></span>
    
- <span data-ttu-id="aa066-117">用于非浏览器客户端的应用程序密码（例如，Microsoft Lync 2013 通信软件）</span><span class="sxs-lookup"><span data-stu-id="aa066-117">Application passwords for non browser clients (for example, the Microsoft Lync 2013 communications software)</span></span>
    
- <span data-ttu-id="aa066-118">身份验证电话联络期间的默认 Microsoft 问候语</span><span class="sxs-lookup"><span data-stu-id="aa066-118">Default Microsoft greetings during authentication phone calls</span></span>
    
<span data-ttu-id="aa066-p103">有关新增功能的完整列表，请参阅 [Azure 多重身份验证版本比较](https://go.microsoft.com/fwlink/?LinkId=506927)。通过购买 Azure 多重身份验证服务，可始终获得完整功能。</span><span class="sxs-lookup"><span data-stu-id="aa066-p103">For the full list of added features, see [the comparison of Azure Multi-Factor Authentication version](https://go.microsoft.com/fwlink/?LinkId=506927). You can always get the full functionality by purchasing the Azure Multi-Factor Authentication service.</span></span> 
  
<span data-ttu-id="aa066-121">获取的功能子集会有所不同，具体取决于是只进行 Office 365 的云部署，还是使用单一登录和 Active Directory 联合身份验证服务 (AD FS) 的混合设置。</span><span class="sxs-lookup"><span data-stu-id="aa066-121">You get a different subset of capabilities depending on whether you have a cloud-only deployment for Office 365 or a hybrid set up with single sign-on and Active Directory Federation Services (AD FS).</span></span> 
  
|<span data-ttu-id="aa066-122">**在哪里管理 Office 365 租户？**</span><span class="sxs-lookup"><span data-stu-id="aa066-122">**Where do you manage your Office 365 tenant?**</span></span>|<span data-ttu-id="aa066-123">**MFA 第二因素选项**</span><span class="sxs-lookup"><span data-stu-id="aa066-123">**MFA second factor options**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aa066-124">仅云</span><span class="sxs-lookup"><span data-stu-id="aa066-124">Cloud only</span></span>  <br/> |<span data-ttu-id="aa066-125">Azure 多因素身份验证（文本或电话呼叫）</span><span class="sxs-lookup"><span data-stu-id="aa066-125">Azure Multi-Factor Authentication (text or phone call)</span></span>  <br/> |
|<span data-ttu-id="aa066-126">本地托管的混合设置</span><span class="sxs-lookup"><span data-stu-id="aa066-126">Hybrid setup, managed on-premises</span></span>  <br/> | <span data-ttu-id="aa066-127">如果在本地管理用户身份，有以下几种选择：</span><span class="sxs-lookup"><span data-stu-id="aa066-127">If you manage user identity on-premises, you have the following choices:</span></span>  <br/>  <span data-ttu-id="aa066-128">物理或虚拟智能卡（使用 AD FS 时）</span><span class="sxs-lookup"><span data-stu-id="aa066-128">Physical or virtual smart card (when using AD FS)</span></span>  <br/> <span data-ttu-id="aa066-129">[Azure 多因素身份验证](https://go.microsoft.com/fwlink/p/?LinkId=526677)（AD FS 模块）</span><span class="sxs-lookup"><span data-stu-id="aa066-129">[Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=526677) (module for AD FS)</span></span>  <br/>  <span data-ttu-id="aa066-130">Azure Active Directory （Azure AD）多重身份验证</span><span class="sxs-lookup"><span data-stu-id="aa066-130">Azure Active Directory (Azure AD) Multi-Factor Authentication</span></span>  <br/> |
   
  
<span data-ttu-id="aa066-p104">下图演示更新的 Office 2013 设备应用（用于 Windows）如何使用户能够使用 MFA 登录。Office2013 设备应用通过使用 [Active Directory 身份验证库 (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684) 支持多重身份验证。Azure AD 托管用户可登录的网页。标识提供程序可以是 Azure AD 或联合身份提供程序，如 AD FS。联合用户的身份验证执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="aa066-p104">The following figure shows how the updated Office 2013 device apps (on Windows) enable users to sign in with MFA. TheOffice 2013 device apps support multi-factor authentication through the use of the [Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684). Azure AD hosts a webpage where users can sign in. The identity provider can be Azure AD or a federated identity provider like AD FS. The authentication for federated users follows these steps:</span></span>
  
1. <span data-ttu-id="aa066-p105">Azure AD 将用户重定向到由 Office 365 租户的记录的标识提供程序托管的登录网页。标识提供程序由用户登录名中指定的域来确定。</span><span class="sxs-lookup"><span data-stu-id="aa066-p105">Azure AD redirects the user to the sign-in web page hosted by the identity provider of record for the Office 365 tenant. The identity provider is determined by the domain specified in the user's sign in name.</span></span>
    
2. <span data-ttu-id="aa066-138">用户在其设备的登录网页上进行登录。</span><span class="sxs-lookup"><span data-stu-id="aa066-138">The user signs in on the sign in web page on his or her device.</span></span> 
    
3. <span data-ttu-id="aa066-139">如果用户成功登录，标识提供程序会将一个令牌返回到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="aa066-139">The identity provider returns a token to Azure AD when the user is successfully signed in.</span></span>
    
4. <span data-ttu-id="aa066-140">Azure AD 将 JSON Web 令牌 (JWT) 返回到 Office 设备应用，并通过结合使用 JWT 和 Office 365 对设备应用进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="aa066-140">Azure AD returns a JSON Web Token (JWT) to the Office device app, and the device app is authenticated by using a JWT with Office 365.</span></span> 
    
<span data-ttu-id="aa066-141">下图对此进行了详细说明：</span><span class="sxs-lookup"><span data-stu-id="aa066-141">This is detailed in the following figure:</span></span>
  
![Office 2013 设备应用的现代身份验证。](../../media/dc37645c-b899-4715-b162-d7653bd0aebd.png)
  
## <a name="software-requirements"></a><span data-ttu-id="aa066-143">软件要求</span><span class="sxs-lookup"><span data-stu-id="aa066-143">Software requirements</span></span>

<span data-ttu-id="aa066-144">要启用适用于 Office 2013 客户端的 MFA，必须根据是具有[基于即点即用的安装](#click-to-run-based-installations)内容还是[基于 MSI 的安装](#msi-based-installations)内容，来安装以下软件（下面列出的版本或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="aa066-144">To enable MFA for Office 2013 client apps, you must have the following software installed (the version listed below, or a later version) based on whether you have a [Click-to-run based installations](#click-to-run-based-installations) or an [MSI-based installations](#msi-based-installations).</span></span>
  
<span data-ttu-id="aa066-145">确定拥有的 Office 安装内容是基于即点即用的还是基于 MSI 的：</span><span class="sxs-lookup"><span data-stu-id="aa066-145">To determine whether your Office installation is Click-to-run or MSI-base:</span></span>
  
1. <span data-ttu-id="aa066-146">启动 Outlook 2013。</span><span class="sxs-lookup"><span data-stu-id="aa066-146">Start Outlook 2013.</span></span>
    
2. <span data-ttu-id="aa066-147">在 "**文件**" 菜单上，选择 " **Office 帐户**"。</span><span class="sxs-lookup"><span data-stu-id="aa066-147">On the **File** menu, choose **Office Account**.</span></span>
    
3. <span data-ttu-id="aa066-p106">对于 Outlook 2013 即点即用安装，将显示" **更新选项**"项。对于基于 MSI 的安装，将不会显示" **更新选项**"项。</span><span class="sxs-lookup"><span data-stu-id="aa066-p106">For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed. For MSI-based installations, the **Update Options** item is not displayed.</span></span> 
    
    ![Graphic that shows how to tell if Office 2013 install is click-to-run or MSI-based](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)
  
### <a name="click-to-run-based-installations"></a><span data-ttu-id="aa066-151">基于即点即用的安装</span><span class="sxs-lookup"><span data-stu-id="aa066-151">Click-to-run based installations</span></span>

<span data-ttu-id="aa066-p107">对于基于即点即用的安装，必须根据下面列出的文件版本或更高文件版本安装以下软件。如果文件版本不是或低于列出的文件版本，请按照下面的步骤进行更新。</span><span class="sxs-lookup"><span data-stu-id="aa066-p107">For Click-to-run based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the steps below.</span></span>
  
|<span data-ttu-id="aa066-154">**文件名**</span><span class="sxs-lookup"><span data-stu-id="aa066-154">**File name**</span></span>|<span data-ttu-id="aa066-155">**计算机上的安装路径**</span><span class="sxs-lookup"><span data-stu-id="aa066-155">**Install path on your computer**</span></span>|<span data-ttu-id="aa066-156">**文件版本**</span><span class="sxs-lookup"><span data-stu-id="aa066-156">**File version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aa066-157">MSO.DLL.DLL</span><span class="sxs-lookup"><span data-stu-id="aa066-157">MSO.DLL</span></span>  <br/> |<span data-ttu-id="aa066-158">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="aa066-158">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |<span data-ttu-id="aa066-159">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="aa066-159">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="aa066-160">CSI.DLL</span><span class="sxs-lookup"><span data-stu-id="aa066-160">CSI.DLL</span></span>  <br/> |<span data-ttu-id="aa066-161">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span><span class="sxs-lookup"><span data-stu-id="aa066-161">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span></span>  <br/> |<span data-ttu-id="aa066-162">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="aa066-162">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="aa066-163">Groove</span><span class="sxs-lookup"><span data-stu-id="aa066-163">Groove.EXE</span></span>  <br/> |<span data-ttu-id="aa066-164">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span><span class="sxs-lookup"><span data-stu-id="aa066-164">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span></span>  <br/> |<span data-ttu-id="aa066-165">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="aa066-165">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="aa066-166">Outlook .exe</span><span class="sxs-lookup"><span data-stu-id="aa066-166">Outlook.exe</span></span>  <br/> |<span data-ttu-id="aa066-167">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span><span class="sxs-lookup"><span data-stu-id="aa066-167">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span></span>  <br/> |<span data-ttu-id="aa066-168">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="aa066-168">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="aa066-169">ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="aa066-169">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="aa066-170">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="aa066-170">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |<span data-ttu-id="aa066-171">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="aa066-171">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="aa066-172">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="aa066-172">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="aa066-173">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="aa066-173">C:\Program Files\Internet Explorer</span></span>  <br/> |<span data-ttu-id="aa066-174">变量</span><span class="sxs-lookup"><span data-stu-id="aa066-174">varies</span></span>  <br/> |
   
### <a name="msi-based-installations"></a><span data-ttu-id="aa066-175">基于 MSI 的安装</span><span class="sxs-lookup"><span data-stu-id="aa066-175">MSI-based installations</span></span>

<span data-ttu-id="aa066-p108">对于基于 MSI 的安装，必须根据下面列出的文件版本或更高文件版本安装以下软件。如果文件版本不是或低于列出的文件版本，请使用"更新 KB 文章"列中的链接进行更新。</span><span class="sxs-lookup"><span data-stu-id="aa066-p108">For MSI-based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the link in the Update KB Article column.</span></span>
  
|<span data-ttu-id="aa066-178">**文件名**</span><span class="sxs-lookup"><span data-stu-id="aa066-178">**File name**</span></span>|<span data-ttu-id="aa066-179">**计算机上的安装路径**</span><span class="sxs-lookup"><span data-stu-id="aa066-179">**Install path on your computer**</span></span>|<span data-ttu-id="aa066-180">**获取更新的位置**</span><span class="sxs-lookup"><span data-stu-id="aa066-180">**Where to get the update**</span></span>|<span data-ttu-id="aa066-181">**版本**</span><span class="sxs-lookup"><span data-stu-id="aa066-181">**Version**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aa066-182">MSO.DLL.DLL</span><span class="sxs-lookup"><span data-stu-id="aa066-182">MSO.DLL</span></span>  <br/> |<span data-ttu-id="aa066-183">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="aa066-183">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |[<span data-ttu-id="aa066-184">KB3085480</span><span class="sxs-lookup"><span data-stu-id="aa066-184">KB3085480</span></span>](https://support.microsoft.com/kb/3085480) <br/> |<span data-ttu-id="aa066-185">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="aa066-185">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="aa066-186">CSI.DLL</span><span class="sxs-lookup"><span data-stu-id="aa066-186">CSI.DLL</span></span>  <br/> |<span data-ttu-id="aa066-187">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span><span class="sxs-lookup"><span data-stu-id="aa066-187">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span></span>  <br/> |[<span data-ttu-id="aa066-188">KB3085504</span><span class="sxs-lookup"><span data-stu-id="aa066-188">KB3085504</span></span>](https://support.microsoft.com/kb/3085504) <br/> |<span data-ttu-id="aa066-189">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="aa066-189">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="aa066-190">Groove</span><span class="sxs-lookup"><span data-stu-id="aa066-190">Groove.exe</span></span>  <br/> |<span data-ttu-id="aa066-191">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span><span class="sxs-lookup"><span data-stu-id="aa066-191">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span></span>  <br/> |[<span data-ttu-id="aa066-192">KB3085509</span><span class="sxs-lookup"><span data-stu-id="aa066-192">KB3085509</span></span>](https://support.microsoft.com/kb/3085509) <br/> |<span data-ttu-id="aa066-193">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="aa066-193">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="aa066-194">Outlook .exe</span><span class="sxs-lookup"><span data-stu-id="aa066-194">Outlook.exe</span></span>  <br/> |<span data-ttu-id="aa066-195">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span><span class="sxs-lookup"><span data-stu-id="aa066-195">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span></span>  <br/> |[<span data-ttu-id="aa066-196">KB3085495</span><span class="sxs-lookup"><span data-stu-id="aa066-196">KB3085495</span></span>](https://support.microsoft.com/kb/3085495) <br/> |<span data-ttu-id="aa066-197">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="aa066-197">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="aa066-198">ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="aa066-198">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="aa066-199">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="aa066-199">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |[<span data-ttu-id="aa066-200">KB3055000</span><span class="sxs-lookup"><span data-stu-id="aa066-200">KB3055000</span></span>](https://support.microsoft.com/kb/3055000) <br/> |<span data-ttu-id="aa066-201">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="aa066-201">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="aa066-202">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="aa066-202">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="aa066-203">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="aa066-203">C:\Program Files\Internet Explorer</span></span>  <br/> |[<span data-ttu-id="aa066-204">MS14-052</span><span class="sxs-lookup"><span data-stu-id="aa066-204">MS14-052</span></span>](https://support.microsoft.com/kb/2977629) <br/> |<span data-ttu-id="aa066-205">不适用</span><span class="sxs-lookup"><span data-stu-id="aa066-205">Not applicable</span></span>  <br/> |
   
## <a name="enable-mfa"></a><span data-ttu-id="aa066-206">启用 MFA</span><span class="sxs-lookup"><span data-stu-id="aa066-206">Enable MFA</span></span>

<span data-ttu-id="aa066-207">要启用 MFA，必须完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="aa066-207">To enable MFA, you have to complete the following:</span></span>
  
1. <span data-ttu-id="aa066-208">启用用于新式验证的客户端：</span><span class="sxs-lookup"><span data-stu-id="aa066-208">Enable clients for modern authentication:</span></span>
    
  - <span data-ttu-id="aa066-209">[在 Windows 设备上启用适用于 Office 2013 的新式验证](enable-modern-authentication.md) 。</span><span class="sxs-lookup"><span data-stu-id="aa066-209">[Enable Modern Authentication for Office 2013 on Windows devices](enable-modern-authentication.md) .</span></span> 
    
  - <span data-ttu-id="aa066-210">使用第三方目录服务设置 Azure 多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="aa066-210">Set up Azure Multi-Factor Authentication with third-party directory services.</span></span>
    
    <span data-ttu-id="aa066-211">有关可接受此程序的特定标识提供程序的信息，请参阅[使用 Azure 多重身份验证和第三方 VPN 解决方案的高级方案](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)。</span><span class="sxs-lookup"><span data-stu-id="aa066-211">See the [Advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for information on specific identity providers accepted to this program.</span></span> 
    
2. [<span data-ttu-id="aa066-212">为 Office 365 设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="aa066-212">Set up multi-factor authentication for Office 365</span></span>](set-up-multi-factor-authentication.md)
    
3. <span data-ttu-id="aa066-213">告知单个用户如何通过 MFA 进行登录：[通过 2 步验证登录 Office 365](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx)。</span><span class="sxs-lookup"><span data-stu-id="aa066-213">Tell individual users how to sign in by MFA: [Sign in to Office 365 with 2-step verification](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="aa066-214">如果已为您的用户启用了 Azure 多重身份验证，并且这些设备具有运行 Office 2013 的任何设备，而这些设备未启用新式验证，则需要在这些设备上使用 AppPasswords。</span><span class="sxs-lookup"><span data-stu-id="aa066-214">If you have enabled your users for Azure Multi-Factor Authentication and they have any devices running Office 2013 that are not enabled for Modern Authentication, they will need to use AppPasswords on those devices.</span></span> <span data-ttu-id="aa066-215">有关应用密码以及应在何时、何处和如何使用的详细信息，可访问此处进行了解：[用于 Azure 多重身份验证的应用密码](https://go.microsoft.com/fwlink/p/?LinkId=528178)</span><span class="sxs-lookup"><span data-stu-id="aa066-215">More information on AppPasswords and when/where/how they should be used can be found here: [App Passwords with Azure Multi_Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=528178).</span></span> 
  
## <a name="faq"></a><span data-ttu-id="aa066-216">常见问题</span><span class="sxs-lookup"><span data-stu-id="aa066-216">FAQ</span></span>

[<span data-ttu-id="aa066-217">新式验证常见问题解答 wiki 文章</span><span class="sxs-lookup"><span data-stu-id="aa066-217">FAQ about Modern Authentication wiki article</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
 <span data-ttu-id="aa066-218">**已知问题：**</span><span class="sxs-lookup"><span data-stu-id="aa066-218">**Known issues:**</span></span>
  
[<span data-ttu-id="aa066-219">Office 2013 和 Office 365 专业增强版新式验证：载入前注意事项</span><span class="sxs-lookup"><span data-stu-id="aa066-219">Office 2013 and Office 365 ProPlus modern authentication : Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="aa066-220">**Azure 多重身份验证疑难解答：**</span><span class="sxs-lookup"><span data-stu-id="aa066-220">**Troubleshooting Azure Multi-Factor Authentication:**</span></span>
  
<span data-ttu-id="aa066-221">请参阅[对 Azure 多重身份验证进行故障排除](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)。</span><span class="sxs-lookup"><span data-stu-id="aa066-221">See [Troubleshoot Azure Multi-Factor Authentication](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).</span></span>
  
[<span data-ttu-id="aa066-222">使用 AD FS 时，如何解决 Office 2013 新式验证的登录问题</span><span class="sxs-lookup"><span data-stu-id="aa066-222">How to troubleshoot sign-in issues with Office 2013 modern authentication when you use AD FS</span></span>](https://support.microsoft.com/kb/3052203/)
  
 <span data-ttu-id="aa066-223">**如果备选 ID 不起作用：**</span><span class="sxs-lookup"><span data-stu-id="aa066-223">**When alternate IDs don't work:**</span></span>
  
[<span data-ttu-id="aa066-224">如何使用 PowerShell 修复 UPN 重复</span><span class="sxs-lookup"><span data-stu-id="aa066-224">How to use PowerShell to fix duplicate UPN</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[<span data-ttu-id="aa066-225">用于修复用户主体名称重复的脚本</span><span class="sxs-lookup"><span data-stu-id="aa066-225">Script to fix duplicate user principal names</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 <span data-ttu-id="aa066-226">**客户端访问筛选：**</span><span class="sxs-lookup"><span data-stu-id="aa066-226">**Client access filtering:**</span></span>
  
[<span data-ttu-id="aa066-227">Office 2013 和 Office 365 专业增强版新式验证和客户端访问筛选策略：载入前注意事项</span><span class="sxs-lookup"><span data-stu-id="aa066-227">Office 2013 and Office 365 ProPlus modern authentication and client access filtering policies : Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="aa066-228">**哪些应用支持 MFA？**</span><span class="sxs-lookup"><span data-stu-id="aa066-228">**Which apps support MFA?**</span></span>
  
|<span data-ttu-id="aa066-229">**Windows**</span><span class="sxs-lookup"><span data-stu-id="aa066-229">**Windows**</span></span>|<span data-ttu-id="aa066-230">**Mac**</span><span class="sxs-lookup"><span data-stu-id="aa066-230">**Mac**</span></span>|<span data-ttu-id="aa066-231">**iOS**</span><span class="sxs-lookup"><span data-stu-id="aa066-231">**iOS**</span></span>|<span data-ttu-id="aa066-232">**Android 手机**</span><span class="sxs-lookup"><span data-stu-id="aa066-232">**Android phone**</span></span>|<span data-ttu-id="aa066-233">**Android 平板电脑**</span><span class="sxs-lookup"><span data-stu-id="aa066-233">**Android tablet**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aa066-234">此版本支持用于 Word 2013、Word 2016、Excel 2013、Excel 2016、PowerPoint 2013、PowerPoint 2016、OneNote 2013、OneNote 2016、Project 2013、Project 2016、Visio 2013、Visio 2016、Lync 2013 和 Skype for Business 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="aa066-234">Modern authentication for Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013, and Skype for Business is supported with this release.</span></span>  <br/> |<span data-ttu-id="aa066-235">此版本支持用于 Word 2016 for Mac、Excel 2016 for Mac 和 PowerPoint 2016 for Mac 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="aa066-235">Modern authentication for Word 2016 for Mac, Excel 2016 for Mac, and PowerPoint 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="aa066-236">此版本支持用于 Word for iPad、Excel for iPad 和 PowerPoint for iPad 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="aa066-236">Modern authentication for Word for iPad, Excel for iPad, and PowerPoint for iPad is supported with this release.</span></span>  <br/> |<span data-ttu-id="aa066-237">此版本支持用于 Word for Android、Excel for Android 和 PowerPoint for Android 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="aa066-237">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |<span data-ttu-id="aa066-238">此版本支持用于 Word for Android、Excel for Android 和 PowerPoint for Android 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="aa066-238">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |
|<span data-ttu-id="aa066-239">此版本支持用于 Outlook 2013 和 Outlook 2016 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="aa066-239">Modern authentication for Outlook 2013 and Outlook 2016 is supported with this release.</span></span>  <br/> |<span data-ttu-id="aa066-240">此版本支持用于 Outlook 2016 for Mac 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="aa066-240">Modern authentication for Outlook 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="aa066-241">此版本支持用于 Outlook for iPad 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="aa066-241">Modern authentication for Outlook for iPad is supported with this release.</span></span>  <br/> |||
   

