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
ms.openlocfilehash: 715baeb0355ab203e890f2c87cf0751eff69e7f8
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2020
ms.locfileid: "43503991"
---
# <a name="plan-for-multi-factor-authentication-for-office-365-deployments"></a><span data-ttu-id="6545e-103">Office 365 部署的多重身份验证计划</span><span class="sxs-lookup"><span data-stu-id="6545e-103">Plan for multi-factor authentication for Office 365 Deployments</span></span>

<span data-ttu-id="6545e-104">多重身份验证 (MFA) 是一种身份验证方法，要求使用多个验证方法，并向用户登录和交易添加第二层安全。</span><span class="sxs-lookup"><span data-stu-id="6545e-104">Multi-factor authentication (MFA) is a method of authentication that requires the use of more than one verification method and adds a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="6545e-105">它的工作方式是要求包含用户帐户密码之外的信息的附加验证步骤，如：</span><span class="sxs-lookup"><span data-stu-id="6545e-105">It works by requiring an addition verification step with information beyond the user account password, such as:</span></span>
  
- <span data-ttu-id="6545e-106">随机生成的密码</span><span class="sxs-lookup"><span data-stu-id="6545e-106">A randomly generated pass code</span></span>
    
- <span data-ttu-id="6545e-107">电话联络</span><span class="sxs-lookup"><span data-stu-id="6545e-107">A phone call</span></span>
    
- <span data-ttu-id="6545e-108">智能卡（虚拟或物理）</span><span class="sxs-lookup"><span data-stu-id="6545e-108">A smart card (virtual or physical)</span></span> 
    
- <span data-ttu-id="6545e-109">生物识别设备</span><span class="sxs-lookup"><span data-stu-id="6545e-109">A biometric device</span></span> 
    
## <a name="mfa-in-office-365"></a><span data-ttu-id="6545e-110">Office 365 中的 MFA</span><span class="sxs-lookup"><span data-stu-id="6545e-110">MFA in Office 365</span></span>

<span data-ttu-id="6545e-111">Office 365 使用 MFA 实现额外的登录安全性，并可为 Microsoft 365 管理中心内的每个用户帐户进行管理。</span><span class="sxs-lookup"><span data-stu-id="6545e-111">Office 365 uses MFA for extra sign-in security and can be managed for each individual user account from the Microsoft 365 admin center.</span></span> <span data-ttu-id="6545e-112">Office 365 提供了以下 Azure 多重身份验证功能子集作为订阅的一部分：</span><span class="sxs-lookup"><span data-stu-id="6545e-112">Office 365 offers the following subset of Azure Multi-Factor Authentication capabilities as a part of your subscription:</span></span> 
  
- <span data-ttu-id="6545e-113">为最终用户启用和强制进行 MFA 的能力</span><span class="sxs-lookup"><span data-stu-id="6545e-113">The ability to enable and enforce MFA for end users</span></span>
    
- <span data-ttu-id="6545e-114">使用移动应用（联机和一次性密码 [OTP]）作为第二身份验证因素</span><span class="sxs-lookup"><span data-stu-id="6545e-114">The use of a mobile app (online and one-time password [OTP]) as a second authentication factor</span></span>
    
- <span data-ttu-id="6545e-115">使用电话联络作为第二身份验证因素</span><span class="sxs-lookup"><span data-stu-id="6545e-115">The use of a phone call as a second authentication factor</span></span>
    
- <span data-ttu-id="6545e-116">使用短消息服务 (SMS) 消息作为第二身份验证因素</span><span class="sxs-lookup"><span data-stu-id="6545e-116">The use of a Short Message Service (SMS) message as a second authentication factor</span></span>
    
- <span data-ttu-id="6545e-117">非浏览器客户端的应用程序密码（例如，Microsoft Lync 2013 通信软件）</span><span class="sxs-lookup"><span data-stu-id="6545e-117">Application passwords for non-browser clients (for example, the Microsoft Lync 2013 communications software)</span></span>
    
- <span data-ttu-id="6545e-118">身份验证电话联络期间的默认 Microsoft 问候语</span><span class="sxs-lookup"><span data-stu-id="6545e-118">Default Microsoft greetings during authentication phone calls</span></span>
    
<span data-ttu-id="6545e-p103">有关新增功能的完整列表，请参阅 [Azure 多重身份验证版本比较](https://go.microsoft.com/fwlink/?LinkId=506927)。通过购买 Azure 多重身份验证服务，可始终获得完整功能。</span><span class="sxs-lookup"><span data-stu-id="6545e-p103">For the full list of added features, see [the comparison of Azure Multi-Factor Authentication version](https://go.microsoft.com/fwlink/?LinkId=506927). You can always get the full functionality by purchasing the Azure Multi-Factor Authentication service.</span></span> 
  
<span data-ttu-id="6545e-121">您将获得不同的功能子集，具体取决于您是否具有适用于 Office 365 的云或混合身份或与 Active Directory 联合身份验证服务（AD FS）的联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="6545e-121">You get a different subset of capabilities depending on whether you have a cloud-only or hybrid identity for Office 365 or federated authentication with Active Directory Federation Services (AD FS).</span></span> 
  
<span data-ttu-id="6545e-122">|**您在哪里管理 Office 365 租户？**| **MFA 第二因素选项**|</span><span class="sxs-lookup"><span data-stu-id="6545e-122">|**Where do you manage your Office 365 tenant?**|**MFA second factor options**|</span></span>

<span data-ttu-id="6545e-123">|:-----|:-----| |仅限云</span><span class="sxs-lookup"><span data-stu-id="6545e-123">|:-----|:-----| |Cloud only</span></span>  <br/> <span data-ttu-id="6545e-124">|Azure 多因素身份验证（文本或电话呼叫）</span><span class="sxs-lookup"><span data-stu-id="6545e-124">|Azure Multi-Factor Authentication (text or phone call)</span></span>  <br/> <span data-ttu-id="6545e-125">| |混合安装，托管本地</span><span class="sxs-lookup"><span data-stu-id="6545e-125">| |Hybrid setup, managed on-premises</span></span>  <br/> <span data-ttu-id="6545e-126">|如果您在本地管理用户标识，则有以下几种选择：</span><span class="sxs-lookup"><span data-stu-id="6545e-126">| If you manage user identity on-premises, you have the following choices:</span></span>  <br/>  <span data-ttu-id="6545e-127">物理或虚拟智能卡（使用 AD FS 时）</span><span class="sxs-lookup"><span data-stu-id="6545e-127">Physical or virtual smart card (when using AD FS)</span></span>  <br/> <span data-ttu-id="6545e-128">[Azure 多因素身份验证](https://go.microsoft.com/fwlink/p/?LinkId=526677)（AD FS 模块）</span><span class="sxs-lookup"><span data-stu-id="6545e-128">[Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=526677) (module for AD FS)</span></span>  <br/>  <span data-ttu-id="6545e-129">Azure Active Directory （Azure AD）多重身份验证</span><span class="sxs-lookup"><span data-stu-id="6545e-129">Azure Active Directory (Azure AD) Multi-Factor Authentication</span></span>  <br/> |
   
  
<span data-ttu-id="6545e-130">下图演示更新的 Office 2013 设备应用（用于 Windows）如何使用户能够使用 MFA 登录。</span><span class="sxs-lookup"><span data-stu-id="6545e-130">The following figure shows how the updated Office 2013 device apps (on Windows) enable users to sign in with MFA.</span></span> 

![Office 2013 设备应用的现代身份验证。](../../media/dc37645c-b899-4715-b162-d7653bd0aebd.png)

<span data-ttu-id="6545e-132">Office 2013 设备应用程序通过使用[Active Directory 身份验证库（ADAL）](https://go.microsoft.com/fwlink/p/?LinkId=526684)支持多因素身份验证。</span><span class="sxs-lookup"><span data-stu-id="6545e-132">The Office 2013 device apps support multi-factor authentication through the use of the [Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684).</span></span> <span data-ttu-id="6545e-133">Azure AD 托管用户可登录的网页。</span><span class="sxs-lookup"><span data-stu-id="6545e-133">Azure AD hosts a webpage where users can sign in.</span></span> <span data-ttu-id="6545e-134">标识提供程序可以是 Azure AD 或联合身份提供程序，如 AD FS。</span><span class="sxs-lookup"><span data-stu-id="6545e-134">The identity provider can be Azure AD or a federated identity provider like AD FS.</span></span> <span data-ttu-id="6545e-135">联合用户的身份验证执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6545e-135">The authentication for federated users follows these steps:</span></span>
  
1. <span data-ttu-id="6545e-p105">Azure AD 将用户重定向到由 Office 365 租户的记录的标识提供程序托管的登录网页。标识提供程序由用户登录名中指定的域来确定。</span><span class="sxs-lookup"><span data-stu-id="6545e-p105">Azure AD redirects the user to the sign-in web page hosted by the identity provider of record for the Office 365 tenant. The identity provider is determined by the domain specified in the user's sign in name.</span></span>
    
2. <span data-ttu-id="6545e-138">用户在其设备的登录网页上进行登录。</span><span class="sxs-lookup"><span data-stu-id="6545e-138">The user signs in on the sign in web page on his or her device.</span></span> 
    
3. <span data-ttu-id="6545e-139">如果用户成功登录，标识提供程序会将一个令牌返回到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6545e-139">The identity provider returns a token to Azure AD when the user is successfully signed in.</span></span>
    
4. <span data-ttu-id="6545e-140">Azure AD 将 JSON Web 令牌 (JWT) 返回到 Office 设备应用，并通过结合使用 JWT 和 Office 365 对设备应用进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="6545e-140">Azure AD returns a JSON Web Token (JWT) to the Office device app, and the device app is authenticated by using a JWT with Office 365.</span></span> 
    
  
## <a name="requirements-for-office-2013-client-apps"></a><span data-ttu-id="6545e-141">Office 2013 客户端应用程序的要求</span><span class="sxs-lookup"><span data-stu-id="6545e-141">Requirements for Office 2013 client apps</span></span>

<span data-ttu-id="6545e-142">要启用适用于 Office 2013 客户端的 MFA，必须根据是具有[基于即点即用的安装](#click-to-run-based-installations)内容还是[基于 MSI 的安装](#msi-based-installations)内容，来安装以下软件（下面列出的版本或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="6545e-142">To enable MFA for Office 2013 client apps, you must have the following software installed (the version listed below, or a later version) based on whether you have a [Click-to-run based installations](#click-to-run-based-installations) or an [MSI-based installations](#msi-based-installations).</span></span>
  
<span data-ttu-id="6545e-143">确定拥有的 Office 安装内容是基于即点即用的还是基于 MSI 的：</span><span class="sxs-lookup"><span data-stu-id="6545e-143">To determine whether your Office installation is Click-to-run or MSI-base:</span></span>
  
1. <span data-ttu-id="6545e-144">启动 Outlook 2013。</span><span class="sxs-lookup"><span data-stu-id="6545e-144">Start Outlook 2013.</span></span>
    
2. <span data-ttu-id="6545e-145">在 "**文件**" 菜单上，选择 " **Office 帐户**"。</span><span class="sxs-lookup"><span data-stu-id="6545e-145">On the **File** menu, choose **Office Account**.</span></span>
    
3. <span data-ttu-id="6545e-146">对于 Outlook 2013 即点即用安装，将显示" **更新选项**"项。</span><span class="sxs-lookup"><span data-stu-id="6545e-146">For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed.</span></span> <span data-ttu-id="6545e-147">对于基于 MSI 的安装，将不会显示" **更新选项**"项。</span><span class="sxs-lookup"><span data-stu-id="6545e-147">For MSI-based installations, the **Update Options** item is not displayed.</span></span> 
    
    ![如何判断你的 Office 2013 安装是即点即用还是基于 MSI 的](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)

<span data-ttu-id="6545e-149">Sor 详细信息，请参阅[有关新式验证 wiki 文章的常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=530064)。</span><span class="sxs-lookup"><span data-stu-id="6545e-149">Sor more information, see the [FAQ about Modern Authentication wiki article](https://go.microsoft.com/fwlink/p/?LinkId=530064).</span></span>
  
### <a name="click-to-run-based-installations"></a><span data-ttu-id="6545e-150">基于即点即用的安装</span><span class="sxs-lookup"><span data-stu-id="6545e-150">Click-to-run based installations</span></span>

<span data-ttu-id="6545e-151">对于基于即点即用的安装，必须安装以下软件，且下面列出的文件版本或更高版本的文件版本。</span><span class="sxs-lookup"><span data-stu-id="6545e-151">For Click-to-run based installations, you must have the following software installed, with the file version listed below or a later file version.</span></span> <span data-ttu-id="6545e-152">如果文件版本不是或低于列出的文件版本，请按照下面的步骤进行更新。</span><span class="sxs-lookup"><span data-stu-id="6545e-152">If your file version is not equal to or greater than the file version listed, update it using the steps below.</span></span>
  
|<span data-ttu-id="6545e-153">**文件名**</span><span class="sxs-lookup"><span data-stu-id="6545e-153">**File name**</span></span>|<span data-ttu-id="6545e-154">**计算机上的安装路径**</span><span class="sxs-lookup"><span data-stu-id="6545e-154">**Install path on your computer**</span></span>|<span data-ttu-id="6545e-155">**文件版本**</span><span class="sxs-lookup"><span data-stu-id="6545e-155">**File version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6545e-156">MSO.DLL.DLL</span><span class="sxs-lookup"><span data-stu-id="6545e-156">MSO.DLL</span></span>  <br/> |<span data-ttu-id="6545e-157">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="6545e-157">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |<span data-ttu-id="6545e-158">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="6545e-158">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="6545e-159">CSI.DLL</span><span class="sxs-lookup"><span data-stu-id="6545e-159">CSI.DLL</span></span>  <br/> |<span data-ttu-id="6545e-160">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span><span class="sxs-lookup"><span data-stu-id="6545e-160">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span></span>  <br/> |<span data-ttu-id="6545e-161">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="6545e-161">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="6545e-162">Groove</span><span class="sxs-lookup"><span data-stu-id="6545e-162">Groove.EXE</span></span>  <br/> |<span data-ttu-id="6545e-163">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span><span class="sxs-lookup"><span data-stu-id="6545e-163">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span></span>  <br/> |<span data-ttu-id="6545e-164">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="6545e-164">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="6545e-165">Outlook .exe</span><span class="sxs-lookup"><span data-stu-id="6545e-165">Outlook.exe</span></span>  <br/> |<span data-ttu-id="6545e-166">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span><span class="sxs-lookup"><span data-stu-id="6545e-166">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span></span>  <br/> |<span data-ttu-id="6545e-167">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="6545e-167">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="6545e-168">ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="6545e-168">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="6545e-169">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="6545e-169">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |<span data-ttu-id="6545e-170">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="6545e-170">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="6545e-171">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="6545e-171">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="6545e-172">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="6545e-172">C:\Program Files\Internet Explorer</span></span>  <br/> |<span data-ttu-id="6545e-173">变量</span><span class="sxs-lookup"><span data-stu-id="6545e-173">varies</span></span>  <br/> |
   
### <a name="msi-based-installations"></a><span data-ttu-id="6545e-174">基于 MSI 的安装</span><span class="sxs-lookup"><span data-stu-id="6545e-174">MSI-based installations</span></span>

<span data-ttu-id="6545e-p108">对于基于 MSI 的安装，必须根据下面列出的文件版本或更高文件版本安装以下软件。如果文件版本不是或低于列出的文件版本，请使用"更新 KB 文章"列中的链接进行更新。</span><span class="sxs-lookup"><span data-stu-id="6545e-p108">For MSI-based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the link in the Update KB Article column.</span></span>
  
|<span data-ttu-id="6545e-177">**文件名**</span><span class="sxs-lookup"><span data-stu-id="6545e-177">**File name**</span></span>|<span data-ttu-id="6545e-178">**计算机上的安装路径**</span><span class="sxs-lookup"><span data-stu-id="6545e-178">**Install path on your computer**</span></span>|<span data-ttu-id="6545e-179">**获取更新的位置**</span><span class="sxs-lookup"><span data-stu-id="6545e-179">**Where to get the update**</span></span>|<span data-ttu-id="6545e-180">**版本**</span><span class="sxs-lookup"><span data-stu-id="6545e-180">**Version**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6545e-181">MSO.DLL.DLL</span><span class="sxs-lookup"><span data-stu-id="6545e-181">MSO.DLL</span></span>  <br/> |<span data-ttu-id="6545e-182">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="6545e-182">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |[<span data-ttu-id="6545e-183">KB3085480</span><span class="sxs-lookup"><span data-stu-id="6545e-183">KB3085480</span></span>](https://support.microsoft.com/kb/3085480) <br/> |<span data-ttu-id="6545e-184">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="6545e-184">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="6545e-185">CSI.DLL</span><span class="sxs-lookup"><span data-stu-id="6545e-185">CSI.DLL</span></span>  <br/> |<span data-ttu-id="6545e-186">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span><span class="sxs-lookup"><span data-stu-id="6545e-186">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span></span>  <br/> |[<span data-ttu-id="6545e-187">KB3085504</span><span class="sxs-lookup"><span data-stu-id="6545e-187">KB3085504</span></span>](https://support.microsoft.com/kb/3085504) <br/> |<span data-ttu-id="6545e-188">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="6545e-188">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="6545e-189">Groove</span><span class="sxs-lookup"><span data-stu-id="6545e-189">Groove.exe</span></span>  <br/> |<span data-ttu-id="6545e-190">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span><span class="sxs-lookup"><span data-stu-id="6545e-190">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span></span>  <br/> |[<span data-ttu-id="6545e-191">KB3085509</span><span class="sxs-lookup"><span data-stu-id="6545e-191">KB3085509</span></span>](https://support.microsoft.com/kb/3085509) <br/> |<span data-ttu-id="6545e-192">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="6545e-192">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="6545e-193">Outlook .exe</span><span class="sxs-lookup"><span data-stu-id="6545e-193">Outlook.exe</span></span>  <br/> |<span data-ttu-id="6545e-194">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span><span class="sxs-lookup"><span data-stu-id="6545e-194">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span></span>  <br/> |[<span data-ttu-id="6545e-195">KB3085495</span><span class="sxs-lookup"><span data-stu-id="6545e-195">KB3085495</span></span>](https://support.microsoft.com/kb/3085495) <br/> |<span data-ttu-id="6545e-196">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="6545e-196">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="6545e-197">ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="6545e-197">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="6545e-198">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="6545e-198">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |[<span data-ttu-id="6545e-199">KB3055000</span><span class="sxs-lookup"><span data-stu-id="6545e-199">KB3055000</span></span>](https://support.microsoft.com/kb/3055000) <br/> |<span data-ttu-id="6545e-200">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="6545e-200">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="6545e-201">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="6545e-201">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="6545e-202">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="6545e-202">C:\Program Files\Internet Explorer</span></span>  <br/> |[<span data-ttu-id="6545e-203">MS14-052</span><span class="sxs-lookup"><span data-stu-id="6545e-203">MS14-052</span></span>](https://support.microsoft.com/kb/2977629) <br/> |<span data-ttu-id="6545e-204">不适用</span><span class="sxs-lookup"><span data-stu-id="6545e-204">Not applicable</span></span>  <br/> |
   
## <a name="enable-mfa"></a><span data-ttu-id="6545e-205">启用 MFA</span><span class="sxs-lookup"><span data-stu-id="6545e-205">Enable MFA</span></span>

<span data-ttu-id="6545e-206">若要为 Office 365 订阅启用 MFA，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="6545e-206">To enable MFA for your Office 365 subscription, follow these steps:</span></span>
  
1. <span data-ttu-id="6545e-207">如果需要，[为 Windows 设备上的 Office 2013 启用新式验证](enable-modern-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="6545e-207">If needed, [enable Modern Authentication for Office 2013 on Windows devices](enable-modern-authentication.md).</span></span>
    
2. <span data-ttu-id="6545e-208">对于联合身份验证，请使用第三方目录服务设置 Azure 多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="6545e-208">For federated authentication, set up Azure Multi-Factor Authentication with your third-party directory service.</span></span>
    
    <span data-ttu-id="6545e-209">有关可接受此程序的特定标识提供程序的信息，请参阅[使用 Azure 多重身份验证和第三方 VPN 解决方案的高级方案](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)。</span><span class="sxs-lookup"><span data-stu-id="6545e-209">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for information on specific identity providers accepted to this program.</span></span> 
    
3. <span data-ttu-id="6545e-210">[为 Office 365 设置多重身份验证](set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="6545e-210">[Set up multi-factor authentication for Office 365](set-up-multi-factor-authentication.md).</span></span>
    
4. <span data-ttu-id="6545e-211">告诉用户如何为[其 Office 365 用户帐户设置 MFA](https://support.office.com/article/set-up-2-step-verification-for-office-365-ace1d096-61e5-449b-a875-58eb3d74de14)。</span><span class="sxs-lookup"><span data-stu-id="6545e-211">Tell your users how to [set up MFA for their Office 365 user account](https://support.office.com/article/set-up-2-step-verification-for-office-365-ace1d096-61e5-449b-a875-58eb3d74de14).</span></span> <span data-ttu-id="6545e-212">在设置了其辅助身份验证方法后，他们的未来登录将需要进行 MFA。</span><span class="sxs-lookup"><span data-stu-id="6545e-212">After they set up their secondary authentication method, their future sign-ins will require MFA.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="6545e-213">如果已为您的用户启用了 Azure 多重身份验证，并且这些设备具有运行 Office 2013 的任何设备，而这些设备未启用新式验证，则需要使用应用密码。</span><span class="sxs-lookup"><span data-stu-id="6545e-213">If you have enabled your users for Azure Multi-Factor Authentication and they have any devices running Office 2013 that are not enabled for Modern Authentication, they will need to use App Passwords.</span></span> <span data-ttu-id="6545e-214">若要详细了解应用密码以及何时/何地使用它们，可以在此处找到：[使用 Azure Multi_Factor 身份验证的应用密码](https://go.microsoft.com/fwlink/p/?LinkId=528178)。</span><span class="sxs-lookup"><span data-stu-id="6545e-214">More information on App Passwords and when/where/how they should be used can be found here: [App Passwords with Azure Multi_Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=528178).</span></span> 
  
## <a name="known-issues"></a><span data-ttu-id="6545e-215">已知问题</span><span class="sxs-lookup"><span data-stu-id="6545e-215">Known issues</span></span>
  
[<span data-ttu-id="6545e-216">Office 2013 和 Office 365 专业增强版新式验证：在载入前要了解的事项</span><span class="sxs-lookup"><span data-stu-id="6545e-216">Office 2013 and Office 365 ProPlus modern authentication: Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="6545e-217">**Azure 多重身份验证疑难解答：**</span><span class="sxs-lookup"><span data-stu-id="6545e-217">**Troubleshooting Azure Multi-Factor Authentication:**</span></span>
  
<span data-ttu-id="6545e-218">请参阅[对 Azure 多重身份验证进行故障排除](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)。</span><span class="sxs-lookup"><span data-stu-id="6545e-218">See [Troubleshoot Azure Multi-Factor Authentication](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).</span></span>
  
[<span data-ttu-id="6545e-219">使用 AD FS 时，如何解决 Office 2013 新式验证的登录问题</span><span class="sxs-lookup"><span data-stu-id="6545e-219">How to troubleshoot sign-in issues with Office 2013 modern authentication when you use AD FS</span></span>](https://support.microsoft.com/kb/3052203/)
  
 <span data-ttu-id="6545e-220">**如果备选 ID 不起作用：**</span><span class="sxs-lookup"><span data-stu-id="6545e-220">**When alternate IDs don't work:**</span></span>
  
[<span data-ttu-id="6545e-221">如何使用 PowerShell 修复 UPN 重复</span><span class="sxs-lookup"><span data-stu-id="6545e-221">How to use PowerShell to fix duplicate UPN</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[<span data-ttu-id="6545e-222">用于修复用户主体名称重复的脚本</span><span class="sxs-lookup"><span data-stu-id="6545e-222">Script to fix duplicate user principal names</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 <span data-ttu-id="6545e-223">**客户端访问筛选：**</span><span class="sxs-lookup"><span data-stu-id="6545e-223">**Client access filtering:**</span></span>
  
[<span data-ttu-id="6545e-224">Office 2013 和 Office 365 专业增强版新式验证和客户端访问筛选策略：载入前注意事项</span><span class="sxs-lookup"><span data-stu-id="6545e-224">Office 2013 and Office 365 ProPlus modern authentication and client access filtering policies : Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="6545e-225">**哪些应用支持 MFA？**</span><span class="sxs-lookup"><span data-stu-id="6545e-225">**Which apps support MFA?**</span></span>
  
|<span data-ttu-id="6545e-226">**Windows**</span><span class="sxs-lookup"><span data-stu-id="6545e-226">**Windows**</span></span>|<span data-ttu-id="6545e-227">**Mac**</span><span class="sxs-lookup"><span data-stu-id="6545e-227">**Mac**</span></span>|<span data-ttu-id="6545e-228">**iOS**</span><span class="sxs-lookup"><span data-stu-id="6545e-228">**iOS**</span></span>|<span data-ttu-id="6545e-229">**Android 手机**</span><span class="sxs-lookup"><span data-stu-id="6545e-229">**Android phone**</span></span>|<span data-ttu-id="6545e-230">**Android 平板电脑**</span><span class="sxs-lookup"><span data-stu-id="6545e-230">**Android tablet**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6545e-231">此版本支持用于 Word 2013、Word 2016、Excel 2013、Excel 2016、PowerPoint 2013、PowerPoint 2016、OneNote 2013、OneNote 2016、Project 2013、Project 2016、Visio 2013、Visio 2016、Lync 2013 和 Skype for Business 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="6545e-231">Modern authentication for Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013, and Skype for Business is supported with this release.</span></span>  <br/> |<span data-ttu-id="6545e-232">此版本支持用于 Word 2016 for Mac、Excel 2016 for Mac 和 PowerPoint 2016 for Mac 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="6545e-232">Modern authentication for Word 2016 for Mac, Excel 2016 for Mac, and PowerPoint 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="6545e-233">此版本支持用于 Word for iPad、Excel for iPad 和 PowerPoint for iPad 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="6545e-233">Modern authentication for Word for iPad, Excel for iPad, and PowerPoint for iPad is supported with this release.</span></span>  <br/> |<span data-ttu-id="6545e-234">此版本支持用于 Word for Android、Excel for Android 和 PowerPoint for Android 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="6545e-234">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |<span data-ttu-id="6545e-235">此版本支持用于 Word for Android、Excel for Android 和 PowerPoint for Android 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="6545e-235">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |
|<span data-ttu-id="6545e-236">此版本支持用于 Outlook 2013 和 Outlook 2016 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="6545e-236">Modern authentication for Outlook 2013 and Outlook 2016 is supported with this release.</span></span>  <br/> |<span data-ttu-id="6545e-237">此版本支持用于 Outlook 2016 for Mac 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="6545e-237">Modern authentication for Outlook 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="6545e-238">此版本支持用于 Outlook for iPad 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="6545e-238">Modern authentication for Outlook for iPad is supported with this release.</span></span>  <br/> |||
   

