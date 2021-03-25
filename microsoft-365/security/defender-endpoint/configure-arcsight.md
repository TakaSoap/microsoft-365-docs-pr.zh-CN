---
title: 配置 Micro Focus ArcSight 以拉取 Microsoft Defender 进行终结点检测
description: 配置 Micro Focus ArcSight 以从 Microsoft Defender 安全中心接收和拉取检测
keywords: 配置 Micro Focus ArcSight， 安全信息和事件管理工具， arcsight
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
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166181"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a><span data-ttu-id="a2574-104">配置 Micro Focus ArcSight 以拉取 Defender 进行终结点检测</span><span class="sxs-lookup"><span data-stu-id="a2574-104">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a2574-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a2574-105">**Applies to:**</span></span>
- [<span data-ttu-id="a2574-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a2574-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a2574-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a2574-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="a2574-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="a2574-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a2574-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="a2574-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

<span data-ttu-id="a2574-110">你需要安装和配置一些文件和工具以使用 Micro Focus ArcSight，以便它可以拉取 Defender 进行终结点检测。</span><span class="sxs-lookup"><span data-stu-id="a2574-110">You'll need to install and configure some files and tools to use Micro Focus ArcSight so that it can pull Defender for Endpoint detections.</span></span>

>[!Note]
>- <span data-ttu-id="a2574-111">[Defender for Endpoint Alert](alerts.md) 由一个或多个检测组成</span><span class="sxs-lookup"><span data-stu-id="a2574-111">[Defender for Endpoint Alert](alerts.md) is composed from one or more detections</span></span>
>- <span data-ttu-id="a2574-112">[Defender for Endpoint Detection](api-portal-mapping.md) 由设备上发生的可疑事件及其相关的警报详细信息组成。</span><span class="sxs-lookup"><span data-stu-id="a2574-112">[Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a2574-113">准备工作</span><span class="sxs-lookup"><span data-stu-id="a2574-113">Before you begin</span></span>

<span data-ttu-id="a2574-114">配置 Micro Focus ArcSight 连接器工具需要多个配置文件，以从 Azure Active Directory (AAD) 检测。</span><span class="sxs-lookup"><span data-stu-id="a2574-114">Configuring the Micro Focus ArcSight Connector tool requires several configuration files for it to pull and parse detections from your Azure Active Directory (AAD) application.</span></span>

<span data-ttu-id="a2574-115">本部分将指导你获取正确设置和使用所需配置文件的必要信息。</span><span class="sxs-lookup"><span data-stu-id="a2574-115">This section guides you in getting the necessary information to set and use the required configuration files correctly.</span></span>

- <span data-ttu-id="a2574-116">确保你已启用"设置"菜单中的 SIEM **集成** 功能。</span><span class="sxs-lookup"><span data-stu-id="a2574-116">Make sure you have enabled the SIEM integration feature from the **Settings** menu.</span></span> <span data-ttu-id="a2574-117">有关详细信息，请参阅在 Defender [for Endpoint 中启用 SIEM 集成](enable-siem-integration.md)。</span><span class="sxs-lookup"><span data-stu-id="a2574-117">For more information, see [Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="a2574-118">准备好启用 SIEM 集成功能时保存的文件。</span><span class="sxs-lookup"><span data-stu-id="a2574-118">Have the file you saved from enabling the SIEM integration feature ready.</span></span> <span data-ttu-id="a2574-119">你需要获取以下值：</span><span class="sxs-lookup"><span data-stu-id="a2574-119">You'll need to get the following values:</span></span>
  - <span data-ttu-id="a2574-120">OAuth 2.0 令牌刷新 URL</span><span class="sxs-lookup"><span data-stu-id="a2574-120">OAuth 2.0 Token refresh URL</span></span>
  - <span data-ttu-id="a2574-121">OAuth 2.0 客户端 ID</span><span class="sxs-lookup"><span data-stu-id="a2574-121">OAuth 2.0 Client ID</span></span>
  - <span data-ttu-id="a2574-122">OAuth 2.0 客户端密码</span><span class="sxs-lookup"><span data-stu-id="a2574-122">OAuth 2.0 Client secret</span></span>

- <span data-ttu-id="a2574-123">准备好以下配置文件：</span><span class="sxs-lookup"><span data-stu-id="a2574-123">Have the following configuration files ready:</span></span>
  - <span data-ttu-id="a2574-124">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="a2574-124">WDATP-connector.properties</span></span>
  - <span data-ttu-id="a2574-125">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="a2574-125">WDATP-connector.jsonparser.properties</span></span>

    <span data-ttu-id="a2574-126">当你选择 Micro Focus ArcSight 作为你在组织使用的 SIEM 类型时，你将保存包含这两个文件的 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="a2574-126">You would have saved a .zip file which contains these two files when you chose Micro Focus ArcSight as the SIEM type you use in your organization.</span></span>

- <span data-ttu-id="a2574-127">请确保生成以下令牌并准备好：</span><span class="sxs-lookup"><span data-stu-id="a2574-127">Make sure you generate the following tokens and have them ready:</span></span>
  - <span data-ttu-id="a2574-128">访问令牌</span><span class="sxs-lookup"><span data-stu-id="a2574-128">Access token</span></span>
  - <span data-ttu-id="a2574-129">刷新令牌</span><span class="sxs-lookup"><span data-stu-id="a2574-129">Refresh token</span></span>

  <span data-ttu-id="a2574-130">你可以从门户的 **SIEM 集成** 设置部分生成这些令牌。</span><span class="sxs-lookup"><span data-stu-id="a2574-130">You can generate these tokens from the **SIEM integration** setup section of the portal.</span></span>

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a><span data-ttu-id="a2574-131">安装和配置 Micro Focus ArcSight FlexConnector</span><span class="sxs-lookup"><span data-stu-id="a2574-131">Install and configure Micro Focus ArcSight FlexConnector</span></span>

<span data-ttu-id="a2574-132">以下步骤假定你已完成开始之前的所有 [必需步骤](#before-you-begin)。</span><span class="sxs-lookup"><span data-stu-id="a2574-132">The following steps assume that you have completed all the required steps in [Before you begin](#before-you-begin).</span></span>

1. <span data-ttu-id="a2574-133">安装最新的 32 位 Windows FlexConnector 安装程序。</span><span class="sxs-lookup"><span data-stu-id="a2574-133">Install the latest 32-bit Windows FlexConnector installer.</span></span> <span data-ttu-id="a2574-134">可在 HPE 软件中心找到它。</span><span class="sxs-lookup"><span data-stu-id="a2574-134">You can find this in the HPE Software center.</span></span> <span data-ttu-id="a2574-135">该工具通常安装在以下默认位置 `C:\Program Files\ArcSightFlexConnectors\current\bin` ：。</span><span class="sxs-lookup"><span data-stu-id="a2574-135">The tool is typically installed in the following default location: `C:\Program Files\ArcSightFlexConnectors\current\bin`.</span></span></br></br><span data-ttu-id="a2574-136">您可以选择保存工具的位置，例如 C：folder_location \\ \current\bin，其中 folder_location表示安装位置。</span><span class="sxs-lookup"><span data-stu-id="a2574-136">You can choose where to save the tool, for example C:\\*folder_location*\current\bin where *folder_location* represents the installation location.</span></span>

2. <span data-ttu-id="a2574-137">按照安装向导完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="a2574-137">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="a2574-138">简介</span><span class="sxs-lookup"><span data-stu-id="a2574-138">Introduction</span></span>
   - <span data-ttu-id="a2574-139">选择"安装文件夹"</span><span class="sxs-lookup"><span data-stu-id="a2574-139">Choose Install Folder</span></span>
   - <span data-ttu-id="a2574-140">选择"安装集"</span><span class="sxs-lookup"><span data-stu-id="a2574-140">Choose Install Set</span></span>
   - <span data-ttu-id="a2574-141">选择快捷方式文件夹</span><span class="sxs-lookup"><span data-stu-id="a2574-141">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="a2574-142">安装前摘要</span><span class="sxs-lookup"><span data-stu-id="a2574-142">Pre-Installation Summary</span></span>
   - <span data-ttu-id="a2574-143">正在安装...</span><span class="sxs-lookup"><span data-stu-id="a2574-143">Installing...</span></span>

   <span data-ttu-id="a2574-144">您可以保留其中每个任务的默认值，或修改选择以满足您的要求。</span><span class="sxs-lookup"><span data-stu-id="a2574-144">You can keep the default values for each of these tasks or modify the selection to suit your requirements.</span></span>

3. <span data-ttu-id="a2574-145">打开文件资源管理器并找到启用 SIEM 集成功能时保存的两个配置文件。</span><span class="sxs-lookup"><span data-stu-id="a2574-145">Open File Explorer and locate the two configuration files you saved when you enabled the SIEM integration feature.</span></span> <span data-ttu-id="a2574-146">将两个文件放在 FlexConnector 安装位置，例如：</span><span class="sxs-lookup"><span data-stu-id="a2574-146">Put the two files in the FlexConnector installation location, for example:</span></span>

   - <span data-ttu-id="a2574-147">WDATP-connector.jsonparser.properties： C： \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="a2574-147">WDATP-connector.jsonparser.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   - <span data-ttu-id="a2574-148">WDATP-connector.properties：C：folder_location \\ \current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="a2574-148">WDATP-connector.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   > [!NOTE]
   > 
   > <span data-ttu-id="a2574-149">必须将配置文件放在此位置，其中 *folder_location表示安装* 该工具的位置。</span><span class="sxs-lookup"><span data-stu-id="a2574-149">You must put the configuration files in this location, where *folder_location* represents the location where you installed the tool.</span></span>

4. <span data-ttu-id="a2574-150">核心连接器的安装完成后，将打开"连接器设置"窗口。</span><span class="sxs-lookup"><span data-stu-id="a2574-150">After the installation of the core connector completes, the Connector Setup window opens.</span></span> <span data-ttu-id="a2574-151">在"连接器设置"窗口中，选择"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="a2574-151">In the Connector Setup window, select **Add a Connector**.</span></span>

5. <span data-ttu-id="a2574-152">选择类型 **：ArcSight FlexConnector REST，** 然后单击下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="a2574-152">Select Type: **ArcSight FlexConnector REST** and click **Next**.</span></span>

6. <span data-ttu-id="a2574-153">在参数详细信息表单中键入以下信息。</span><span class="sxs-lookup"><span data-stu-id="a2574-153">Type the following information in the parameter details form.</span></span> <span data-ttu-id="a2574-154">表单中的所有其他值都是可选的，可以留空。</span><span class="sxs-lookup"><span data-stu-id="a2574-154">All other values in the form are optional and can be left blank.</span></span>

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th><span data-ttu-id="a2574-155">字段</span><span class="sxs-lookup"><span data-stu-id="a2574-155">Field</span></span></th>
    <th><span data-ttu-id="a2574-156">值</span><span class="sxs-lookup"><span data-stu-id="a2574-156">Value</span></span></th>
    </tr>
    <tr>
    <td><span data-ttu-id="a2574-157">配置文件</span><span class="sxs-lookup"><span data-stu-id="a2574-157">Configuration File</span></span></td>
    <td><span data-ttu-id="a2574-158">键入客户端属性文件的名称。</span><span class="sxs-lookup"><span data-stu-id="a2574-158">Type in the name of the client property file.</span></span> <span data-ttu-id="a2574-159">该名称必须与下载的 .zip 中提供的文件匹配。</span><span class="sxs-lookup"><span data-stu-id="a2574-159">The name must match the file provided in the .zip that you downloaded.</span></span>
<span data-ttu-id="a2574-160">例如，如果 flexagent 目录中的配置文件名为 &quot; &quot;WDATP-Connector.js&quot; onparser.properties，则必须键入 &quot; &quot; WDATP-Connector 作为客户端属性 &quot; 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="a2574-160">For example, if the configuration file in &quot;flexagent&quot; directory is named &quot;WDATP-Connector.jsonparser.properties&quot;, you must type &quot;WDATP-Connector&quot; as the name of the client property file.</span></span></td>
    </tr>
    <td><span data-ttu-id="a2574-161">事件 URL</span><span class="sxs-lookup"><span data-stu-id="a2574-161">Events URL</span></span></td>
    <td><span data-ttu-id="a2574-162">根据您的数据中心位置，选择欧盟或美国 URL：</span><span class="sxs-lookup"><span data-stu-id="a2574-162">Depending on the location of your datacenter, select either the EU or the US URL:</span></span> </br></br> <span data-ttu-id="a2574-163"><b>对于欧盟</b>：https:// <i></i> wdatp-alertexporter-eu.windows.com/api/alerts/？sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="a2574-163"><b>For EU</b>:  https://<i></i>wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br>
   </br><span data-ttu-id="a2574-164"><b>对于美国：https://</b> <i></i> wdatp-alertexporter-us.windows.com/api/alerts/？sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="a2574-164"><b>For US:</b> https://<i></i>wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br> <br> <span data-ttu-id="a2574-165"><b>英国 ：https://</b> <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/？sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="a2574-165"><b>For UK</b>:  https://<i></i>wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span></td>
    <tr>
    <td><span data-ttu-id="a2574-166">身份验证类型</span><span class="sxs-lookup"><span data-stu-id="a2574-166">Authentication Type</span></span></td>
    <td><span data-ttu-id="a2574-167">OAuth 2</span><span class="sxs-lookup"><span data-stu-id="a2574-167">OAuth 2</span></span></td>
    </tr>
    <td><span data-ttu-id="a2574-168">OAuth 2 客户端属性文件</span><span class="sxs-lookup"><span data-stu-id="a2574-168">OAuth 2 Client Properties file</span></span></td>
    <td><span data-ttu-id="a2574-169">浏览到 <em>wdatp-connector.properties 文件</em> 的位置。</span><span class="sxs-lookup"><span data-stu-id="a2574-169">Browse to the location of the <em>wdatp-connector.properties</em> file.</span></span> <span data-ttu-id="a2574-170">该名称必须与下载的 .zip 中提供的文件匹配。</span><span class="sxs-lookup"><span data-stu-id="a2574-170">The name must match the file provided in the .zip that you downloaded.</span></span></td>
    <tr>
    <td><span data-ttu-id="a2574-171">刷新令牌</span><span class="sxs-lookup"><span data-stu-id="a2574-171">Refresh Token</span></span></td>
    <td><span data-ttu-id="a2574-172">可以通过两种方式获取刷新令牌：从 <b>SIEM</b> 设置页生成刷新令牌，或者使用 restutil 工具。</span><span class="sxs-lookup"><span data-stu-id="a2574-172">You can obtain a refresh token in two ways: by generating a refresh token from the <b>SIEM settings</b> page or using the restutil tool.</span></span> <br><br> <span data-ttu-id="a2574-173">有关从首选项设置生成刷新令牌详细信息 <b>，</b> 请参阅在 Defender for Endpoint 中启用 <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">SIEM 集成</a>。</span><span class="sxs-lookup"><span data-stu-id="a2574-173">For more information on generating a refresh token from the <b>Preferences setup</b> , see <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Enable SIEM integration in Defender for Endpoint</a>.</span></span> </br> </br><span data-ttu-id="a2574-174"><b>使用 restutil 工具获取刷新令牌：</b> </span><span class="sxs-lookup"><span data-stu-id="a2574-174"><b>Get your refresh token using the restutil tool:</b> </span></span></br> <span data-ttu-id="a2574-175">a.</span><span class="sxs-lookup"><span data-stu-id="a2574-175">a.</span></span> <span data-ttu-id="a2574-176">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="a2574-176">Open a command prompt.</span></span> <span data-ttu-id="a2574-177">导航到 C：\<em>folder_location</em>\current\bin，folder_location表示安装该工具的位置。 <em></em></span><span class="sxs-lookup"><span data-stu-id="a2574-177">Navigate to C:\<em>folder_location</em>\current\bin where <em>folder_location</em> represents the location where you installed the tool.</span></span> </br></br> <span data-ttu-id="a2574-178">b.</span><span class="sxs-lookup"><span data-stu-id="a2574-178">b.</span></span> <span data-ttu-id="a2574-179">类型： <code>arcsight restutil token -config</code> 从 bin 目录。例如 <b>：arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> Web 浏览器窗口将打开。</span><span class="sxs-lookup"><span data-stu-id="a2574-179">Type: <code>arcsight restutil token -config</code> from the bin directory.For example: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> A Web browser window will open.</span></span> </br> </br><span data-ttu-id="a2574-180">c.</span><span class="sxs-lookup"><span data-stu-id="a2574-180">c.</span></span> <span data-ttu-id="a2574-181">键入凭据，然后单击密码字段，让页面重定向。</span><span class="sxs-lookup"><span data-stu-id="a2574-181">Type in your credentials then click on the password field to let the page redirect.</span></span> <span data-ttu-id="a2574-182">在登录提示中，输入凭据。</span><span class="sxs-lookup"><span data-stu-id="a2574-182">In the login prompt, enter your credentials.</span></span> </br> </br><span data-ttu-id="a2574-183">d.</span><span class="sxs-lookup"><span data-stu-id="a2574-183">d.</span></span> <span data-ttu-id="a2574-184">刷新令牌显示在命令提示符中。</span><span class="sxs-lookup"><span data-stu-id="a2574-184">A refresh token is shown in the command prompt.</span></span> </br></br> <span data-ttu-id="a2574-185">e.</span><span class="sxs-lookup"><span data-stu-id="a2574-185">e.</span></span> <span data-ttu-id="a2574-186">将其复制并粘贴到 <b>"刷新令牌"</b> 字段中。</span><span class="sxs-lookup"><span data-stu-id="a2574-186">Copy and paste it into the <b>Refresh Token</b> field.</span></span>
    </td>
    </tr>
    </tr>
    </table><br/>
    
7. <span data-ttu-id="a2574-187">浏览器窗口由连接器打开。</span><span class="sxs-lookup"><span data-stu-id="a2574-187">A browser window is opened by the connector.</span></span> <span data-ttu-id="a2574-188">使用应用程序凭据登录。</span><span class="sxs-lookup"><span data-stu-id="a2574-188">Login with your application credentials.</span></span> <span data-ttu-id="a2574-189">登录后，将要求您授予 OAuth2 客户端的权限。</span><span class="sxs-lookup"><span data-stu-id="a2574-189">After you log in, you'll be asked to give permission to your OAuth2 Client.</span></span> <span data-ttu-id="a2574-190">您必须向 OAuth 2 客户端授予权限，以便连接器配置可以进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="a2574-190">You must give permission to your OAuth 2 Client so that the connector configuration can authenticate.</span></span>

   <span data-ttu-id="a2574-191">如果 <code>redirect_uri</code> 为 https URL，将重定向到本地主机上的 URL。</span><span class="sxs-lookup"><span data-stu-id="a2574-191">If the <code>redirect_uri</code> is a https URL, you'll be redirected to a URL on the local host.</span></span> <span data-ttu-id="a2574-192">你将看到一个页面，请求你信任在本地主机上运行的连接器提供的证书。</span><span class="sxs-lookup"><span data-stu-id="a2574-192">You'll see a page that requests for you to trust the certificate supplied by the connector running on the local host.</span></span> <span data-ttu-id="a2574-193">如果证书是 https，则需要redirect_uri证书。</span><span class="sxs-lookup"><span data-stu-id="a2574-193">You'll need to trust this certificate if the redirect_uri is a https.</span></span>
   
   <span data-ttu-id="a2574-194">但是，如果为证书指定 http URL redirect_uri，则无需在信任证书时提供同意。</span><span class="sxs-lookup"><span data-stu-id="a2574-194">If however you specify a http URL for the redirect_uri, you do not need to provide consent in trusting the certificate.</span></span>

8. <span data-ttu-id="a2574-195">返回到 Micro Focus ArcSight 连接器设置窗口，继续进行连接器设置。</span><span class="sxs-lookup"><span data-stu-id="a2574-195">Continue with the connector setup by returning to the Micro Focus ArcSight Connector Setup window.</span></span>

9. <span data-ttu-id="a2574-196">选择 **ArcSight 管理器 (加密)** 作为目标，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="a2574-196">Select the **ArcSight Manager (encrypted)** as the destination and click **Next**.</span></span>

10. <span data-ttu-id="a2574-197">在"管理器主机名"中键入目标IP/主机名，在参数表单中键入凭据。</span><span class="sxs-lookup"><span data-stu-id="a2574-197">Type in the destination IP/hostname in **Manager Hostname** and your credentials in the parameters form.</span></span> <span data-ttu-id="a2574-198">表单中的所有其他值都应保留为默认值。</span><span class="sxs-lookup"><span data-stu-id="a2574-198">All other values in the form should be retained with the default values.</span></span> <span data-ttu-id="a2574-199">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a2574-199">Click **Next**.</span></span>

11. <span data-ttu-id="a2574-200">在连接器详细信息表单中键入连接器的名称。</span><span class="sxs-lookup"><span data-stu-id="a2574-200">Type in a name for the connector in the connector details form.</span></span> <span data-ttu-id="a2574-201">表单中的所有其他值都是可选的，可以留空。</span><span class="sxs-lookup"><span data-stu-id="a2574-201">All other values in the form are optional and can be left blank.</span></span> <span data-ttu-id="a2574-202">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a2574-202">Click **Next**.</span></span>

12. <span data-ttu-id="a2574-203">将显示 ESM 管理器导入证书窗口。</span><span class="sxs-lookup"><span data-stu-id="a2574-203">The ESM Manager import certificate window is shown.</span></span> <span data-ttu-id="a2574-204">选择 **"将证书从目标导入连接器"，然后单击**"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="a2574-204">Select **Import the certificate to connector from destination** and click **Next**.</span></span> <span data-ttu-id="a2574-205">将显示 **"添加连接器摘要** "窗口，并导入证书。</span><span class="sxs-lookup"><span data-stu-id="a2574-205">The **Add connector Summary** window is displayed and the certificate is imported.</span></span>

13. <span data-ttu-id="a2574-206">验证"添加 **连接器摘要"** 窗口中的详细信息是否正确，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="a2574-206">Verify that the details in the **Add connector Summary** window is correct, then click **Next**.</span></span>

14. <span data-ttu-id="a2574-207">选择 **"安装为服务"，** 然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="a2574-207">Select **Install as a service** and click **Next**.</span></span>

15. <span data-ttu-id="a2574-208">在"服务内部名称" **字段中键入** 名称。</span><span class="sxs-lookup"><span data-stu-id="a2574-208">Type a name in the **Service Internal Name** field.</span></span> <span data-ttu-id="a2574-209">窗体中的所有其他值都可以使用默认值保留或留空。</span><span class="sxs-lookup"><span data-stu-id="a2574-209">All other values in the form can be retained with the default values or left blank .</span></span> <span data-ttu-id="a2574-210">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a2574-210">Click **Next**.</span></span>

16. <span data-ttu-id="a2574-211">键入服务参数，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="a2574-211">Type in the service parameters and click **Next**.</span></span> <span data-ttu-id="a2574-212">将显示一个 **包含"安装服务摘要"** 的窗口。</span><span class="sxs-lookup"><span data-stu-id="a2574-212">A window with the **Install Service Summary** is shown.</span></span> <span data-ttu-id="a2574-213">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a2574-213">Click **Next**.</span></span>

17. <span data-ttu-id="a2574-214">通过选择"退出"和"下一步 **"完成\*\*\*\*安装**。</span><span class="sxs-lookup"><span data-stu-id="a2574-214">Finish the installation by selecting **Exit** and **Next**.</span></span>

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a><span data-ttu-id="a2574-215">安装和配置 Micro Focus ArcSight 控制台</span><span class="sxs-lookup"><span data-stu-id="a2574-215">Install and configure the Micro Focus ArcSight console</span></span>

1. <span data-ttu-id="a2574-216">按照安装向导完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="a2574-216">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="a2574-217">简介</span><span class="sxs-lookup"><span data-stu-id="a2574-217">Introduction</span></span>
   - <span data-ttu-id="a2574-218">许可协议</span><span class="sxs-lookup"><span data-stu-id="a2574-218">License Agreement</span></span>
   - <span data-ttu-id="a2574-219">特别通知</span><span class="sxs-lookup"><span data-stu-id="a2574-219">Special Notice</span></span>
   - <span data-ttu-id="a2574-220">选择 ArcSight 安装目录</span><span class="sxs-lookup"><span data-stu-id="a2574-220">Choose ArcSight installation directory</span></span>
   - <span data-ttu-id="a2574-221">选择快捷方式文件夹</span><span class="sxs-lookup"><span data-stu-id="a2574-221">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="a2574-222">安装前摘要</span><span class="sxs-lookup"><span data-stu-id="a2574-222">Pre-Installation Summary</span></span>

2. <span data-ttu-id="a2574-223">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="a2574-223">Click **Install**.</span></span> <span data-ttu-id="a2574-224">安装完成后，将打开 ArcSight 控制台配置向导。</span><span class="sxs-lookup"><span data-stu-id="a2574-224">After the installation completes, the ArcSight Console Configuration Wizard opens.</span></span>

3. <span data-ttu-id="a2574-225">在"管理器主机名"**中键入 localhost，在**"管理器端口"中键入 8443，**然后单击**"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="a2574-225">Type localhost in **Manager Host Name** and 8443 in **Manager Port** then click **Next**.</span></span>

4. <span data-ttu-id="a2574-226">选择 **"使用直接连接"，** 然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="a2574-226">Select **Use direct connection**, then click **Next**.</span></span>

5. <span data-ttu-id="a2574-227">选择 **"基于密码的身份验证"，** 然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="a2574-227">Select **Password Based Authentication**, then click **Next**.</span></span>

6. <span data-ttu-id="a2574-228">选择 **"这是单个用户安装"。 (推荐**) "，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="a2574-228">Select **This is a single user installation. (Recommended)**, then click **Next**.</span></span>

7. <span data-ttu-id="a2574-229">单击 **"完成** "退出安装程序。</span><span class="sxs-lookup"><span data-stu-id="a2574-229">Click **Done** to quit the installer.</span></span>

8. <span data-ttu-id="a2574-230">登录到 Micro Focus ArcSight 控制台。</span><span class="sxs-lookup"><span data-stu-id="a2574-230">Login to the Micro Focus ArcSight console.</span></span>

9. <span data-ttu-id="a2574-231">导航到 **"活动通道设置**  >  **新建条件**  >  **设备**  >  **设备产品"。**</span><span class="sxs-lookup"><span data-stu-id="a2574-231">Navigate to **Active channel set** > **New Condition** > **Device** > **Device Product**.</span></span>

10. <span data-ttu-id="a2574-232">设置 **设备产品 = Microsoft Defender ATP**。</span><span class="sxs-lookup"><span data-stu-id="a2574-232">Set **Device Product = Microsoft Defender ATP**.</span></span> <span data-ttu-id="a2574-233">当你验证事件是否流向该工具时，请再次停止该过程，然后转到 Windows 服务并启动 ArcSight FlexConnector REST。</span><span class="sxs-lookup"><span data-stu-id="a2574-233">When you've verified that events are flowing to the tool, stop the process again and go to Windows Services and start the ArcSight FlexConnector REST.</span></span>

<span data-ttu-id="a2574-234">现在可以在 Micro Focus ArcSight 控制台中运行查询。</span><span class="sxs-lookup"><span data-stu-id="a2574-234">You can now run queries in the Micro Focus ArcSight console.</span></span>

<span data-ttu-id="a2574-235">Defender for Endpoint 检测将显示为离散事件，"Microsoft"作为供应商，"Windows Defender ATP"作为设备名称。</span><span class="sxs-lookup"><span data-stu-id="a2574-235">Defender for Endpoint detections will appear as discrete events, with "Microsoft” as the vendor and “Windows Defender ATP” as the device name.</span></span>


## <a name="troubleshooting-micro-focus-arcsight-connection"></a><span data-ttu-id="a2574-236">微焦点 ArcSight 连接疑难解答</span><span class="sxs-lookup"><span data-stu-id="a2574-236">Troubleshooting Micro Focus ArcSight connection</span></span>

<span data-ttu-id="a2574-237">**问题：** 未能刷新令牌。</span><span class="sxs-lookup"><span data-stu-id="a2574-237">**Problem:** Failed to refresh the token.</span></span> <span data-ttu-id="a2574-238">你可以找到位于 C： \\ *folder_location*\current\logs 中的日志folder_location表示安装该工具的位置。</span><span class="sxs-lookup"><span data-stu-id="a2574-238">You can find the log located in C:\\*folder_location*\current\logs where *folder_location* represents the location where you installed the tool.</span></span> <span data-ttu-id="a2574-239">打开 _agent.log_ 并查找 `ERROR/FATAL/WARN` 。</span><span class="sxs-lookup"><span data-stu-id="a2574-239">Open _agent.log_ and look for `ERROR/FATAL/WARN`.</span></span>

<span data-ttu-id="a2574-240">**症状：** 收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="a2574-240">**Symptom:** You get the following error message:</span></span>

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

<span data-ttu-id="a2574-241">**解决方案：**</span><span class="sxs-lookup"><span data-stu-id="a2574-241">**Solution:**</span></span>

1. <span data-ttu-id="a2574-242">通过单击"连接器"窗口上的 Ctrl + C 停止此过程。</span><span class="sxs-lookup"><span data-stu-id="a2574-242">Stop the process by clicking Ctrl + C on the Connector window.</span></span> <span data-ttu-id="a2574-243">当 **系统询问"** 终止批处理作业 Y/N？"时，单击"Y"。</span><span class="sxs-lookup"><span data-stu-id="a2574-243">Click **Y** when asked "Terminate batch job Y/N?".</span></span>

2. <span data-ttu-id="a2574-244">导航到存储 WDATP-connector.properties 文件的文件夹，然后对其进行编辑以添加以下值 `reauthenticate=true` ：。</span><span class="sxs-lookup"><span data-stu-id="a2574-244">Navigate to the folder where you stored the WDATP-connector.properties file and edit it to add the following value: `reauthenticate=true`.</span></span>

3. <span data-ttu-id="a2574-245">通过运行以下命令重新启动连接器 `arcsight.bat connectors` ：。</span><span class="sxs-lookup"><span data-stu-id="a2574-245">Restart the connector by running the following command: `arcsight.bat connectors`.</span></span>

   <span data-ttu-id="a2574-246">将显示浏览器窗口。</span><span class="sxs-lookup"><span data-stu-id="a2574-246">A browser window appears.</span></span> <span data-ttu-id="a2574-247">允许它运行，它应消失，连接器现在应该正在运行。</span><span class="sxs-lookup"><span data-stu-id="a2574-247">Allow it to run, it should disappear, and the connector should now be running.</span></span>

> [!NOTE]
> <span data-ttu-id="a2574-248">通过再次停止进程来验证连接器是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="a2574-248">Verify that the connector is running by stopping the process again.</span></span> <span data-ttu-id="a2574-249">然后再次启动连接器，不应显示浏览器窗口。</span><span class="sxs-lookup"><span data-stu-id="a2574-249">Then start the connector again, and no browser window should appear.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a2574-250">相关主题</span><span class="sxs-lookup"><span data-stu-id="a2574-250">Related topics</span></span>
- [<span data-ttu-id="a2574-251">在 Defender for Endpoint 中启用 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="a2574-251">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="a2574-252">将检测拉取到 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="a2574-252">Pull detections to your SIEM tools</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [<span data-ttu-id="a2574-253">使用 REST API 拉取 Defender for Endpoint 检测</span><span class="sxs-lookup"><span data-stu-id="a2574-253">Pull Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="a2574-254">SIEM 工具集成问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="a2574-254">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
