---
title: 在 Microsoft Defender for Endpoint 中启用 SIEM 集成
description: 启用 SIEM 集成以在 SIEM 解决方案的安全信息和事件 (接收) 检测。
keywords: 启用 siem 连接器， siem， 连接器， 安全信息和事件
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 337eb28b7e4b4a7c57b63ff45fb1cea81db43604
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056444"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="b49de-104">在 Microsoft Defender for Endpoint 中启用 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="b49de-104">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b49de-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b49de-105">**Applies to:**</span></span>
- [<span data-ttu-id="b49de-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b49de-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


><span data-ttu-id="b49de-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b49de-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b49de-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="b49de-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

<span data-ttu-id="b49de-109">在 SIEM (启用安全信息和事件) 集成，以便你可以从 Microsoft Defender 安全中心拉取检测。</span><span class="sxs-lookup"><span data-stu-id="b49de-109">Enable security information and event management (SIEM) integration so you can pull detections from Microsoft Defender Security Center.</span></span> <span data-ttu-id="b49de-110">使用 SIEM 解决方案或直接连接到检测 REST API 拉取检测。</span><span class="sxs-lookup"><span data-stu-id="b49de-110">Pull detections using your SIEM solution or by connecting directly to the detections REST API.</span></span>

>[!NOTE]
>- <span data-ttu-id="b49de-111">[Microsoft Defender for Endpoint Alert](alerts.md) 由一个或多个检测组成。</span><span class="sxs-lookup"><span data-stu-id="b49de-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="b49de-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) 由设备上发生的可疑事件及其相关的警报详细信息组成。</span><span class="sxs-lookup"><span data-stu-id="b49de-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
>- <span data-ttu-id="b49de-113">Microsoft Defender for Endpoint 警报 API 是警报使用的最新 API，包含每个警报的相关证据的详细列表。</span><span class="sxs-lookup"><span data-stu-id="b49de-113">The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="b49de-114">有关详细信息，请参阅[警报方法和属性和](alerts.md)[列表警报](get-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="b49de-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b49de-115">先决条件</span><span class="sxs-lookup"><span data-stu-id="b49de-115">Prerequisites</span></span>

- <span data-ttu-id="b49de-116">激活该设置的用户必须有权在 Azure Active Directory (AAD) 。</span><span class="sxs-lookup"><span data-stu-id="b49de-116">The user who activates the setting must have permissions to create an app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="b49de-117">这是具有以下角色的人：</span><span class="sxs-lookup"><span data-stu-id="b49de-117">This is someone with the following roles:</span></span> 

  - <span data-ttu-id="b49de-118">安全管理员和全局管理员之一</span><span class="sxs-lookup"><span data-stu-id="b49de-118">Security Administrator and either Global Administrator</span></span>
  - <span data-ttu-id="b49de-119">云 应用程序管理员</span><span class="sxs-lookup"><span data-stu-id="b49de-119">Cloud Application Administrator</span></span>
  - <span data-ttu-id="b49de-120"> 应用程序管理员</span><span class="sxs-lookup"><span data-stu-id="b49de-120">Application Administrator</span></span>
  - <span data-ttu-id="b49de-121">服务主体的所有者</span><span class="sxs-lookup"><span data-stu-id="b49de-121">Owner of the service principal</span></span>

- <span data-ttu-id="b49de-122">在初始激活期间，将显示一个弹出屏幕以输入凭据。</span><span class="sxs-lookup"><span data-stu-id="b49de-122">During the initial activation, a pop-up screen is displayed for credentials to be entered.</span></span> <span data-ttu-id="b49de-123">请确保允许此网站的弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="b49de-123">Make sure that you allow pop-ups for this site.</span></span>

## <a name="enabling-siem-integration"></a><span data-ttu-id="b49de-124">启用 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="b49de-124">Enabling SIEM integration</span></span> 
1. <span data-ttu-id="b49de-125">在导航窗格中，**选择设置**  >  **SIEM**。</span><span class="sxs-lookup"><span data-stu-id="b49de-125">In the navigation pane, select **Settings** > **SIEM**.</span></span>

    !["设置"菜单中 SIEM 集成的图像1](images/enable_siem.png)

    >[!TIP]
    ><span data-ttu-id="b49de-127">如果在尝试启用 SIEM 连接器应用程序时遇到错误，请检查浏览器的弹出窗口阻止程序设置。</span><span class="sxs-lookup"><span data-stu-id="b49de-127">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="b49de-128">启用该功能时，它可能会阻止打开的新窗口。</span><span class="sxs-lookup"><span data-stu-id="b49de-128">It might be blocking the new window being opened when you enable the capability.</span></span> 

2. <span data-ttu-id="b49de-129">选择 **启用 SIEM 集成**。</span><span class="sxs-lookup"><span data-stu-id="b49de-129">Select **Enable SIEM integration**.</span></span> <span data-ttu-id="b49de-130">这会使用预填充的值激活 **SIEM** 连接器访问详细信息部分，并且应用程序是在 Azure AD 租户的 Azure Active Directory (创建的) 部分。</span><span class="sxs-lookup"><span data-stu-id="b49de-130">This activates the **SIEM connector access details** section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span>

    > [!WARNING]
    ><span data-ttu-id="b49de-131">客户端密码只显示一次。</span><span class="sxs-lookup"><span data-stu-id="b49de-131">The client secret is only displayed once.</span></span> <span data-ttu-id="b49de-132">请确保将其副本放在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="b49de-132">Make sure you keep a copy of it in a safe place.</span></span><br>
     

    !["设置"菜单中 SIEM 集成的图像2](images/siem_details.png)

3. <span data-ttu-id="b49de-134">选择你在组织使用的 SIEM 类型。</span><span class="sxs-lookup"><span data-stu-id="b49de-134">Choose the SIEM type you use in your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b49de-135">如果选择 HP ArcSight，将需要保存以下两个配置文件：</span><span class="sxs-lookup"><span data-stu-id="b49de-135">If you select HP ArcSight, you'll need to save these two configuration files:</span></span><br>
   > - <span data-ttu-id="b49de-136">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="b49de-136">WDATP-connector.jsonparser.properties</span></span>
   > - <span data-ttu-id="b49de-137">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="b49de-137">WDATP-connector.properties</span></span> <br>

   <span data-ttu-id="b49de-138">如果你想要通过编程访问直接连接到检测 REST API，请选择通用 **API**。</span><span class="sxs-lookup"><span data-stu-id="b49de-138">If you want to connect directly to the detections REST API through programmatic access, choose **Generic API**.</span></span>

4. <span data-ttu-id="b49de-139">复制各个值或选择 **"将详细信息保存到文件** "以下载包含所有值的文件。</span><span class="sxs-lookup"><span data-stu-id="b49de-139">Copy the individual values or select **Save details to file** to download a file that contains all the values.</span></span>

5. <span data-ttu-id="b49de-140">选择 **"生成令牌** "，获取访问令牌和刷新令牌。</span><span class="sxs-lookup"><span data-stu-id="b49de-140">Select **Generate tokens** to get an access and refresh token.</span></span>
  
   > [!NOTE]
   > <span data-ttu-id="b49de-141">你将需要每 90 天生成一个新的刷新令牌。</span><span class="sxs-lookup"><span data-stu-id="b49de-141">You'll need to generate a new Refresh token every 90 days.</span></span> 

6. <span data-ttu-id="b49de-142">按照为 Microsoft Defender for Endpoint 创建 [Azure AD](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) 应用注册的说明操作，并为其分配正确的权限以读取警报。</span><span class="sxs-lookup"><span data-stu-id="b49de-142">Follow the instructions for [creating an Azure AD app registration for Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) and assign the correct permissions to it to read alerts.</span></span>

<span data-ttu-id="b49de-143">你现在可以继续配置 SIEM 解决方案，或者通过编程访问连接到检测 REST API。</span><span class="sxs-lookup"><span data-stu-id="b49de-143">You can now proceed with configuring your SIEM solution or connecting to the detections REST API through programmatic access.</span></span> <span data-ttu-id="b49de-144">配置 SIEM 解决方案时，你需要使用令牌，以允许它接收来自 Microsoft Defender 安全中心的检测。</span><span class="sxs-lookup"><span data-stu-id="b49de-144">You'll need to use the tokens when configuring your SIEM solution to allow it to receive detections from Microsoft Defender Security Center.</span></span>

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a><span data-ttu-id="b49de-145">将 Microsoft Defender for Endpoint 与 IBM QRadar 集成</span><span class="sxs-lookup"><span data-stu-id="b49de-145">Integrate Microsoft Defender for Endpoint with IBM QRadar</span></span> 
<span data-ttu-id="b49de-146">你可以将 IBM QRadar 配置为从 Microsoft Defender for Endpoint 收集检测。</span><span class="sxs-lookup"><span data-stu-id="b49de-146">You can configure IBM QRadar to collect detections from Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b49de-147">有关详细信息，请参阅 [IBM 知识库](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)。</span><span class="sxs-lookup"><span data-stu-id="b49de-147">For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

## <a name="see-also"></a><span data-ttu-id="b49de-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b49de-148">See also</span></span>
- [<span data-ttu-id="b49de-149">配置 HP ArcSight 以拉取 Microsoft Defender 进行终结点检测</span><span class="sxs-lookup"><span data-stu-id="b49de-149">Configure HP ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="b49de-150">适用于终结点检测字段的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b49de-150">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="b49de-151">使用 REST API 拉取 Microsoft Defender 的终结点检测</span><span class="sxs-lookup"><span data-stu-id="b49de-151">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="b49de-152">SIEM 工具集成问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="b49de-152">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
