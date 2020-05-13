---
title: 为 Microsoft 365 部署规划多重身份验证
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
description: 了解 Microsoft 365 中的多重身份验证，以及对其进行设置时需要遵循的步骤。
ms.openlocfilehash: 6d28e9e7db825aa9030196396ad420028dc1c881
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213124"
---
# <a name="plan-for-multi-factor-authentication-for-microsoft-365-deployments"></a><span data-ttu-id="4301a-103">为 Microsoft 365 部署规划多重身份验证</span><span class="sxs-lookup"><span data-stu-id="4301a-103">Plan for multi-factor authentication for Microsoft 365 deployments</span></span>

<span data-ttu-id="4301a-104">多重身份验证 (MFA) 是一种身份验证方法，要求使用多个验证方法，并向用户登录和交易添加第二层安全。</span><span class="sxs-lookup"><span data-stu-id="4301a-104">Multi-factor authentication (MFA) is a method of authentication that requires the use of more than one verification method and adds a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="4301a-105">它的工作方式是要求包含用户帐户密码之外的信息的附加验证步骤，如：</span><span class="sxs-lookup"><span data-stu-id="4301a-105">It works by requiring an addition verification step with information beyond the user account password, such as:</span></span>
  
- <span data-ttu-id="4301a-106">发送到智能手机的随机生成的验证代码</span><span class="sxs-lookup"><span data-stu-id="4301a-106">A randomly generated verification code sent to your smart phone</span></span>
    
- <span data-ttu-id="4301a-107">电话联络</span><span class="sxs-lookup"><span data-stu-id="4301a-107">A phone call</span></span>
    
- <span data-ttu-id="4301a-108">智能卡（虚拟或物理）</span><span class="sxs-lookup"><span data-stu-id="4301a-108">A smart card (virtual or physical)</span></span> 
    
- <span data-ttu-id="4301a-109">生物识别设备</span><span class="sxs-lookup"><span data-stu-id="4301a-109">A biometric device</span></span> 
    
## <a name="mfa-in-microsoft-365"></a><span data-ttu-id="4301a-110">Microsoft 365 中的 MFA</span><span class="sxs-lookup"><span data-stu-id="4301a-110">MFA in Microsoft 365</span></span>

<span data-ttu-id="4301a-111">Microsoft 365 使用 MFA 帮助提供额外的安全性，并通过 Microsoft 365 管理中心进行管理。</span><span class="sxs-lookup"><span data-stu-id="4301a-111">Microsoft 365 uses MFA to help provide the extra security and is managed from the Microsoft 365 admin center.</span></span> <span data-ttu-id="4301a-112">Microsoft 365 提供了以下[Azure 多重身份验证](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)功能子集作为订阅的一部分：</span><span class="sxs-lookup"><span data-stu-id="4301a-112">Microsoft 365 offers the following subset of [Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) capabilities as a part of the subscription:</span></span> 
  
- <span data-ttu-id="4301a-113">为最终用户启用和强制进行 MFA 的能力</span><span class="sxs-lookup"><span data-stu-id="4301a-113">The ability to enable and enforce MFA for end users</span></span>
    
- <span data-ttu-id="4301a-114">使用移动应用（联机和一次性密码 [OTP]）作为第二身份验证因素</span><span class="sxs-lookup"><span data-stu-id="4301a-114">The use of a mobile app (online and one-time password [OTP]) as a second authentication factor</span></span>
    
- <span data-ttu-id="4301a-115">使用电话联络作为第二身份验证因素</span><span class="sxs-lookup"><span data-stu-id="4301a-115">The use of a phone call as a second authentication factor</span></span>
    
- <span data-ttu-id="4301a-116">将短信服务（SMS）短信用作第二身份验证因素</span><span class="sxs-lookup"><span data-stu-id="4301a-116">The use of a Short Message Service (SMS) text message as a second authentication factor</span></span>
    
- <span data-ttu-id="4301a-117">非浏览器客户端的应用程序密码（例如，Microsoft Lync 2013 通信软件）</span><span class="sxs-lookup"><span data-stu-id="4301a-117">Application passwords for non-browser clients (for example, the Microsoft Lync 2013 communications software)</span></span>
    
- <span data-ttu-id="4301a-118">身份验证电话联络期间的默认 Microsoft 问候语</span><span class="sxs-lookup"><span data-stu-id="4301a-118">Default Microsoft greetings during authentication phone calls</span></span>
    
<span data-ttu-id="4301a-119">有关添加的功能的完整列表，请参阅[Azure 多因素身份验证](https://go.microsoft.com/fwlink/?LinkId=506927)。</span><span class="sxs-lookup"><span data-stu-id="4301a-119">For the full list of added features, see [Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/?LinkId=506927).</span></span> <span data-ttu-id="4301a-120">你始终可以通过购买[Azure 多重身份验证许可证](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-licensing)获取完整功能。</span><span class="sxs-lookup"><span data-stu-id="4301a-120">You can always get the full functionality by purchasing [Azure Multi-Factor Authentication licenses](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-licensing).</span></span> 
  
<span data-ttu-id="4301a-121">您将获得不同的功能子集，具体取决于您是使用仅限云的标识（其中的用户帐户在 Microsoft 365 中存在），还是使用单一登录和 Active Directory 联合身份验证服务（AD FS）的混合设置。</span><span class="sxs-lookup"><span data-stu-id="4301a-121">You get a different subset of capabilities depending on whether you use cloud-only identity where the user accounts on exist in Microsoft 365, or hybrid set up with single sign-on and Active Directory Federation Services (AD FS).</span></span> 
  
|<span data-ttu-id="4301a-122">**您在哪里管理 Microsoft 365？**</span><span class="sxs-lookup"><span data-stu-id="4301a-122">**Where do you manage Microsoft 365?**</span></span>|<span data-ttu-id="4301a-123">**MFA 第二因素选项**</span><span class="sxs-lookup"><span data-stu-id="4301a-123">**MFA second factor options**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4301a-124">仅云</span><span class="sxs-lookup"><span data-stu-id="4301a-124">Cloud only</span></span>  <br/> | <span data-ttu-id="4301a-125">Azure 多因素身份验证（文本或电话呼叫）</span><span class="sxs-lookup"><span data-stu-id="4301a-125">Azure Multi-Factor Authentication (text or phone call)</span></span>  <br/> |
|<span data-ttu-id="4301a-126">本地托管的混合设置</span><span class="sxs-lookup"><span data-stu-id="4301a-126">Hybrid setup, managed on-premises</span></span>  <br/> | <span data-ttu-id="4301a-127">如果在本地管理用户身份，有以下几种选择：</span><span class="sxs-lookup"><span data-stu-id="4301a-127">If you manage user identity on-premises, you have the following choices:</span></span>  <br/> <span data-ttu-id="4301a-128">-物理或虚拟智能卡（AD FS）</span><span class="sxs-lookup"><span data-stu-id="4301a-128">-  Physical or virtual smart card (AD FS)</span></span>  <br/> <span data-ttu-id="4301a-129">-Azure 多重身份验证（用于 AD FS 的模块）</span><span class="sxs-lookup"><span data-stu-id="4301a-129">- Azure Multi-Factor Authentication (module for AD FS)</span></span>  <br/>  <span data-ttu-id="4301a-130">-Azure 多重身份验证</span><span class="sxs-lookup"><span data-stu-id="4301a-130">- Azure Multi-Factor Authentication</span></span>  <br/> |
   
<span data-ttu-id="4301a-131">Office 2013 设备应用通过使用[Active Directory 身份验证库（ADAL）](https://go.microsoft.com/fwlink/p/?LinkId=526684)支持 MFA。</span><span class="sxs-lookup"><span data-stu-id="4301a-131">The Office 2013 device apps support MFA through the use of the [Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684).</span></span> <span data-ttu-id="4301a-132">Azure Active Directory （Azure AD）托管用户可在其中登录的网页。</span><span class="sxs-lookup"><span data-stu-id="4301a-132">Azure Active Directory (Azure AD) hosts a web page where users can sign in.</span></span> <span data-ttu-id="4301a-133">标识提供程序可以是 Azure AD 或联合身份提供程序，如 AD FS。</span><span class="sxs-lookup"><span data-stu-id="4301a-133">The identity provider can be Azure AD or a federated identity provider like AD FS.</span></span> <span data-ttu-id="4301a-134">联合用户的身份验证执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4301a-134">The authentication for federated users follows these steps:</span></span>
  
1. <span data-ttu-id="4301a-135">Azure AD 将用户重定向到由组织的标识提供程序托管的登录网页。</span><span class="sxs-lookup"><span data-stu-id="4301a-135">Azure AD redirects the user to the sign-in web page hosted by the identity provider of record for the organization.</span></span> <span data-ttu-id="4301a-136">标识提供程序由用户登录名中指定的域来确定。</span><span class="sxs-lookup"><span data-stu-id="4301a-136">The identity provider is determined by the domain specified in the user's sign in name.</span></span>
    
2. <span data-ttu-id="4301a-137">用户在其设备的登录网页上进行登录。</span><span class="sxs-lookup"><span data-stu-id="4301a-137">The user signs in on the sign in web page on his or her device.</span></span> 
    
3. <span data-ttu-id="4301a-138">如果用户成功登录，标识提供程序会将一个令牌返回到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="4301a-138">The identity provider returns a token to Azure AD when the user is successfully signed in.</span></span>
    
4. <span data-ttu-id="4301a-139">Azure AD 将 JSON Web 令牌（JWT）返回到 Office 设备应用，并通过将 JWT 与 Microsoft 365 结合使用来对设备应用进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="4301a-139">Azure AD returns a JSON Web Token (JWT) to the Office device app, and the device app is authenticated by using a JWT with Microsoft 365.</span></span> 
    
  
## <a name="requirements-for-office-2013-client-apps"></a><span data-ttu-id="4301a-140">Office 2013 客户端应用程序的要求</span><span class="sxs-lookup"><span data-stu-id="4301a-140">Requirements for Office 2013 client apps</span></span>

<span data-ttu-id="4301a-141">要启用适用于 Office 2013 客户端的 MFA，必须根据是具有[基于即点即用的安装](#click-to-run-based-installations)内容还是[基于 MSI 的安装](#msi-based-installations)内容，来安装以下软件（下面列出的版本或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="4301a-141">To enable MFA for Office 2013 client apps, you must have the following software installed (the version listed below, or a later version) based on whether you have a [Click-to-run based installations](#click-to-run-based-installations) or an [MSI-based installations](#msi-based-installations).</span></span>
  
<span data-ttu-id="4301a-142">确定拥有的 Office 安装内容是基于即点即用的还是基于 MSI 的：</span><span class="sxs-lookup"><span data-stu-id="4301a-142">To determine whether your Office installation is Click-to-run or MSI-base:</span></span>
  
1. <span data-ttu-id="4301a-143">启动 Outlook 2013。</span><span class="sxs-lookup"><span data-stu-id="4301a-143">Start Outlook 2013.</span></span>
    
2. <span data-ttu-id="4301a-144">在 "**文件**" 菜单上，选择 " **Office 帐户**"。</span><span class="sxs-lookup"><span data-stu-id="4301a-144">On the **File** menu, choose **Office Account**.</span></span>
    
3. <span data-ttu-id="4301a-145">对于 Outlook 2013 即点即用安装，将显示" **更新选项**"项。</span><span class="sxs-lookup"><span data-stu-id="4301a-145">For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed.</span></span> <span data-ttu-id="4301a-146">对于基于 MSI 的安装，将不会显示" **更新选项**"项。</span><span class="sxs-lookup"><span data-stu-id="4301a-146">For MSI-based installations, the **Update Options** item is not displayed.</span></span> 
    
    ![如何判断你的 Office 2013 安装是即点即用还是基于 MSI 的](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)

<span data-ttu-id="4301a-148">Sor 详细信息，请参阅[有关新式验证 wiki 文章的常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=530064)。</span><span class="sxs-lookup"><span data-stu-id="4301a-148">Sor more information, see the [FAQ about Modern Authentication wiki article](https://go.microsoft.com/fwlink/p/?LinkId=530064).</span></span>
  
### <a name="click-to-run-based-installations"></a><span data-ttu-id="4301a-149">基于即点即用的安装</span><span class="sxs-lookup"><span data-stu-id="4301a-149">Click-to-run based installations</span></span>

<span data-ttu-id="4301a-150">对于基于即点即用的安装，必须安装以下软件，且下面列出的文件版本或更高版本的文件版本。</span><span class="sxs-lookup"><span data-stu-id="4301a-150">For Click-to-run based installations, you must have the following software installed, with the file version listed below or a later file version.</span></span> <span data-ttu-id="4301a-151">如果文件版本不是或低于列出的文件版本，请按照下面的步骤进行更新。</span><span class="sxs-lookup"><span data-stu-id="4301a-151">If your file version is not equal to or greater than the file version listed, update it using the steps below.</span></span>
  
|<span data-ttu-id="4301a-152">**文件名**</span><span class="sxs-lookup"><span data-stu-id="4301a-152">**File name**</span></span>|<span data-ttu-id="4301a-153">**计算机上的安装路径**</span><span class="sxs-lookup"><span data-stu-id="4301a-153">**Install path on your computer**</span></span>|<span data-ttu-id="4301a-154">**文件版本**</span><span class="sxs-lookup"><span data-stu-id="4301a-154">**File version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4301a-155">MSO.DLL.DLL</span><span class="sxs-lookup"><span data-stu-id="4301a-155">MSO.DLL</span></span>  <br/> |<span data-ttu-id="4301a-156">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="4301a-156">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |<span data-ttu-id="4301a-157">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="4301a-157">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="4301a-158">CSI.DLL</span><span class="sxs-lookup"><span data-stu-id="4301a-158">CSI.DLL</span></span>  <br/> |<span data-ttu-id="4301a-159">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span><span class="sxs-lookup"><span data-stu-id="4301a-159">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span></span>  <br/> |<span data-ttu-id="4301a-160">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="4301a-160">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="4301a-161">Groove</span><span class="sxs-lookup"><span data-stu-id="4301a-161">Groove.EXE</span></span>  <br/> |<span data-ttu-id="4301a-162">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span><span class="sxs-lookup"><span data-stu-id="4301a-162">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span></span>  <br/> |<span data-ttu-id="4301a-163">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="4301a-163">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="4301a-164">Outlook .exe</span><span class="sxs-lookup"><span data-stu-id="4301a-164">Outlook.exe</span></span>  <br/> |<span data-ttu-id="4301a-165">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span><span class="sxs-lookup"><span data-stu-id="4301a-165">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span></span>  <br/> |<span data-ttu-id="4301a-166">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="4301a-166">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="4301a-167">ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="4301a-167">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="4301a-168">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="4301a-168">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |<span data-ttu-id="4301a-169">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="4301a-169">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="4301a-170">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="4301a-170">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="4301a-171">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="4301a-171">C:\Program Files\Internet Explorer</span></span>  <br/> |<span data-ttu-id="4301a-172">变量</span><span class="sxs-lookup"><span data-stu-id="4301a-172">varies</span></span>  <br/> |
   
### <a name="msi-based-installations"></a><span data-ttu-id="4301a-173">基于 MSI 的安装</span><span class="sxs-lookup"><span data-stu-id="4301a-173">MSI-based installations</span></span>

<span data-ttu-id="4301a-p108">对于基于 MSI 的安装，必须根据下面列出的文件版本或更高文件版本安装以下软件。如果文件版本不是或低于列出的文件版本，请使用"更新 KB 文章"列中的链接进行更新。</span><span class="sxs-lookup"><span data-stu-id="4301a-p108">For MSI-based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the link in the Update KB Article column.</span></span>
  
|<span data-ttu-id="4301a-176">**文件名**</span><span class="sxs-lookup"><span data-stu-id="4301a-176">**File name**</span></span>|<span data-ttu-id="4301a-177">**计算机上的安装路径**</span><span class="sxs-lookup"><span data-stu-id="4301a-177">**Install path on your computer**</span></span>|<span data-ttu-id="4301a-178">**获取更新的位置**</span><span class="sxs-lookup"><span data-stu-id="4301a-178">**Where to get the update**</span></span>|<span data-ttu-id="4301a-179">**版本**</span><span class="sxs-lookup"><span data-stu-id="4301a-179">**Version**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4301a-180">MSO.DLL.DLL</span><span class="sxs-lookup"><span data-stu-id="4301a-180">MSO.DLL</span></span>  <br/> |<span data-ttu-id="4301a-181">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="4301a-181">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |[<span data-ttu-id="4301a-182">KB3085480</span><span class="sxs-lookup"><span data-stu-id="4301a-182">KB3085480</span></span>](https://support.microsoft.com/kb/3085480) <br/> |<span data-ttu-id="4301a-183">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="4301a-183">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="4301a-184">CSI.DLL</span><span class="sxs-lookup"><span data-stu-id="4301a-184">CSI.DLL</span></span>  <br/> |<span data-ttu-id="4301a-185">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span><span class="sxs-lookup"><span data-stu-id="4301a-185">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span></span>  <br/> |[<span data-ttu-id="4301a-186">KB3085504</span><span class="sxs-lookup"><span data-stu-id="4301a-186">KB3085504</span></span>](https://support.microsoft.com/kb/3085504) <br/> |<span data-ttu-id="4301a-187">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="4301a-187">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="4301a-188">Groove</span><span class="sxs-lookup"><span data-stu-id="4301a-188">Groove.exe</span></span>  <br/> |<span data-ttu-id="4301a-189">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span><span class="sxs-lookup"><span data-stu-id="4301a-189">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span></span>  <br/> |[<span data-ttu-id="4301a-190">KB3085509</span><span class="sxs-lookup"><span data-stu-id="4301a-190">KB3085509</span></span>](https://support.microsoft.com/kb/3085509) <br/> |<span data-ttu-id="4301a-191">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="4301a-191">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="4301a-192">Outlook .exe</span><span class="sxs-lookup"><span data-stu-id="4301a-192">Outlook.exe</span></span>  <br/> |<span data-ttu-id="4301a-193">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span><span class="sxs-lookup"><span data-stu-id="4301a-193">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span></span>  <br/> |[<span data-ttu-id="4301a-194">KB3085495</span><span class="sxs-lookup"><span data-stu-id="4301a-194">KB3085495</span></span>](https://support.microsoft.com/kb/3085495) <br/> |<span data-ttu-id="4301a-195">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="4301a-195">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="4301a-196">ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="4301a-196">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="4301a-197">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="4301a-197">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |[<span data-ttu-id="4301a-198">KB3055000</span><span class="sxs-lookup"><span data-stu-id="4301a-198">KB3055000</span></span>](https://support.microsoft.com/kb/3055000) <br/> |<span data-ttu-id="4301a-199">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="4301a-199">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="4301a-200">Iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="4301a-200">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="4301a-201">C:\Program Files\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="4301a-201">C:\Program Files\Internet Explorer</span></span>  <br/> |[<span data-ttu-id="4301a-202">MS14-052</span><span class="sxs-lookup"><span data-stu-id="4301a-202">MS14-052</span></span>](https://support.microsoft.com/kb/2977629) <br/> |<span data-ttu-id="4301a-203">不适用</span><span class="sxs-lookup"><span data-stu-id="4301a-203">Not applicable</span></span>  <br/> |
   
## <a name="enable-mfa"></a><span data-ttu-id="4301a-204">启用 MFA</span><span class="sxs-lookup"><span data-stu-id="4301a-204">Enable MFA</span></span>

<span data-ttu-id="4301a-205">若要为你的订阅启用 MFA，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="4301a-205">To enable MFA for your subscription, follow these steps:</span></span>
  
1. <span data-ttu-id="4301a-206">如果需要：</span><span class="sxs-lookup"><span data-stu-id="4301a-206">If needed:</span></span> 

  - <span data-ttu-id="4301a-207">[为 Windows 设备上的 Office 2013 启用新式验证](enable-modern-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="4301a-207">[Enable Modern Authentication for Office 2013 on Windows devices](enable-modern-authentication.md).</span></span>
    
  - <span data-ttu-id="4301a-208">使用第三方目录服务设置 Azure 多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="4301a-208">Set up Azure Multi-Factor Authentication with third-party directory services.</span></span>
    
    <span data-ttu-id="4301a-209">有关可接受此程序的特定标识提供程序的信息，请参阅[使用 Azure 多重身份验证和第三方 VPN 解决方案的高级方案](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)。</span><span class="sxs-lookup"><span data-stu-id="4301a-209">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for information on specific identity providers accepted to this program.</span></span> 
    
2. <span data-ttu-id="4301a-210">[为 Microsoft 365 设置 MFA](set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="4301a-210">[Set up MFA for Microsoft 365](set-up-multi-factor-authentication.md).</span></span>
    
3. <span data-ttu-id="4301a-211">通知各个用户如何通过 MFA 进行登录。</span><span class="sxs-lookup"><span data-stu-id="4301a-211">Tell individual users how to sign in by MFA.</span></span> <span data-ttu-id="4301a-212">请参阅[使用 MFA 登录 Microsoft 365](https://support.office.com/article/sign-in-to-microsoft-365-with-2-step-verification-2b856342-170a-438e-9a4f-3c092394d3cb)。</span><span class="sxs-lookup"><span data-stu-id="4301a-212">See [Sign in to Microsoft 365 with MFA](https://support.office.com/article/sign-in-to-microsoft-365-with-2-step-verification-2b856342-170a-438e-9a4f-3c092394d3cb).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4301a-213">如果已为您的用户启用了 Azure 多重身份验证，并且它们具有任何运行 Office 2013 且未启用新式验证的设备，则它们将需要在这些设备上使用应用密码。</span><span class="sxs-lookup"><span data-stu-id="4301a-213">If you have enabled your users for Azure Multi-Factor Authentication and they have any devices running Office 2013 that are not enabled for Modern Authentication, they will need to use app passwords on those devices.</span></span> <span data-ttu-id="4301a-214">有关详细信息，请参阅[本文](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords)。</span><span class="sxs-lookup"><span data-stu-id="4301a-214">See [this article](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) for more information.</span></span>
  
## <a name="faq"></a><span data-ttu-id="4301a-215">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="4301a-215">FAQ</span></span>

[<span data-ttu-id="4301a-216">新式验证常见问题解答 wiki 文章</span><span class="sxs-lookup"><span data-stu-id="4301a-216">FAQ about Modern Authentication wiki article</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
## <a name="known-issues"></a><span data-ttu-id="4301a-217">已知问题</span><span class="sxs-lookup"><span data-stu-id="4301a-217">Known issues</span></span>

[<span data-ttu-id="4301a-218">适用于企业的 Office 2013 和 Microsoft 365 应用新式身份验证：在载入前要了解的事项</span><span class="sxs-lookup"><span data-stu-id="4301a-218">Office 2013 and Microsoft 365 Apps for enterprise modern authentication: Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="4301a-219">**Azure 多重身份验证疑难解答：**</span><span class="sxs-lookup"><span data-stu-id="4301a-219">**Troubleshooting Azure Multi-Factor Authentication:**</span></span>
  
<span data-ttu-id="4301a-220">请参阅[对 Azure 多重身份验证进行故障排除](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues)。</span><span class="sxs-lookup"><span data-stu-id="4301a-220">See [Troubleshoot Azure Multi-Factor Authentication](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).</span></span>
  
[<span data-ttu-id="4301a-221">使用 AD FS 时，如何解决 Office 2013 新式验证的登录问题</span><span class="sxs-lookup"><span data-stu-id="4301a-221">How to troubleshoot sign-in issues with Office 2013 modern authentication when you use AD FS</span></span>](https://support.microsoft.com/kb/3052203/)
  
 <span data-ttu-id="4301a-222">**如果备选 ID 不起作用：**</span><span class="sxs-lookup"><span data-stu-id="4301a-222">**When alternate IDs don't work:**</span></span>
  
[<span data-ttu-id="4301a-223">如何使用 PowerShell 修复 UPN 重复</span><span class="sxs-lookup"><span data-stu-id="4301a-223">How to use PowerShell to fix duplicate UPN</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[<span data-ttu-id="4301a-224">用于修复用户主体名称重复的脚本</span><span class="sxs-lookup"><span data-stu-id="4301a-224">Script to fix duplicate user principal names</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 <span data-ttu-id="4301a-225">**客户端访问筛选：**</span><span class="sxs-lookup"><span data-stu-id="4301a-225">**Client access filtering:**</span></span>
  
[<span data-ttu-id="4301a-226">适用于企业新式验证和客户端访问筛选策略的 Office 2013 和 Microsoft 365 应用程序：在加入之前需要了解的事项</span><span class="sxs-lookup"><span data-stu-id="4301a-226">Office 2013 and Microsoft 365 Apps for enterprise modern authentication and client access filtering policies: Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="4301a-227">**哪些应用支持 MFA？**</span><span class="sxs-lookup"><span data-stu-id="4301a-227">**Which apps support MFA?**</span></span>
  
|<span data-ttu-id="4301a-228">**Windows**</span><span class="sxs-lookup"><span data-stu-id="4301a-228">**Windows**</span></span>|<span data-ttu-id="4301a-229">**Mac**</span><span class="sxs-lookup"><span data-stu-id="4301a-229">**Mac**</span></span>|<span data-ttu-id="4301a-230">**iOS**</span><span class="sxs-lookup"><span data-stu-id="4301a-230">**iOS**</span></span>|<span data-ttu-id="4301a-231">**Android 手机**</span><span class="sxs-lookup"><span data-stu-id="4301a-231">**Android phone**</span></span>|<span data-ttu-id="4301a-232">**Android 平板电脑**</span><span class="sxs-lookup"><span data-stu-id="4301a-232">**Android tablet**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4301a-233">此版本支持用于 Word 2013、Word 2016、Excel 2013、Excel 2016、PowerPoint 2013、PowerPoint 2016、OneNote 2013、OneNote 2016、Project 2013、Project 2016、Visio 2013、Visio 2016、Lync 2013 和 Skype for Business 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="4301a-233">Modern authentication for Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013, and Skype for Business is supported with this release.</span></span>  <br/> |<span data-ttu-id="4301a-234">此版本支持用于 Word 2016 for Mac、Excel 2016 for Mac 和 PowerPoint 2016 for Mac 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="4301a-234">Modern authentication for Word 2016 for Mac, Excel 2016 for Mac, and PowerPoint 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="4301a-235">此版本支持用于 Word for iPad、Excel for iPad 和 PowerPoint for iPad 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="4301a-235">Modern authentication for Word for iPad, Excel for iPad, and PowerPoint for iPad is supported with this release.</span></span>  <br/> |<span data-ttu-id="4301a-236">此版本支持用于 Word for Android、Excel for Android 和 PowerPoint for Android 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="4301a-236">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |<span data-ttu-id="4301a-237">此版本支持用于 Word for Android、Excel for Android 和 PowerPoint for Android 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="4301a-237">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |
|<span data-ttu-id="4301a-238">此版本支持用于 Outlook 2013 和 Outlook 2016 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="4301a-238">Modern authentication for Outlook 2013 and Outlook 2016 is supported with this release.</span></span>  <br/> |<span data-ttu-id="4301a-239">此版本支持用于 Outlook 2016 for Mac 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="4301a-239">Modern authentication for Outlook 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="4301a-240">此版本支持用于 Outlook for iPad 的新式验证。</span><span class="sxs-lookup"><span data-stu-id="4301a-240">Modern authentication for Outlook for iPad is supported with this release.</span></span>  <br/> |||
   

