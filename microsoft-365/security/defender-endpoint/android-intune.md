---
title: 使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint
description: 介绍如何在 Android 上部署 Microsoft Defender for Endpoint Microsoft Intune
keywords: microsoft， defender， Microsoft Defender for Endpoint， mde， android， 安装， 部署， 卸载，
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aab50764a13a671cdeb10902744456dcbc1cb48f
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64471398"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-android-with-microsoft-intune"></a>使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

了解如何在已注册的设备上在 Android Intune 公司门户 Defender for Endpoint。 有关 Intune 设备注册详细信息，请参阅 [注册设备](/mem/intune/user-help/enroll-device-android-company-portal)。

> [!NOTE]
> **Android 上的 Defender for Endpoint 现已在 [Google Play 上可用](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**
>
> 你可以从 Intune 连接到 Google Play，以跨设备管理员和 Android Enterprise部署 Defender for Endpoint 应用。
>
> 通过 Google Play 自动更新应用。

## <a name="deploy-on-device-administrator-enrolled-devices"></a>在设备管理员注册的设备上部署

**在 Android 设备上部署 Defender for Endpoint Intune 公司门户 - 设备管理员注册的设备**

了解如何在 Android 设备上部署 Defender for Endpoint Intune 公司门户 - 设备管理员注册的设备。

### <a name="add-as-android-store-app"></a>添加为 Android 应用商店应用

1. In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431)， go to **Apps** \> **Android Apps** \> **Add \> Android store app** and choose **Select**.

   :::image type="content" source="images/mda-addandroidstoreapp.png" alt-text="Microsoft Endpoint Manager管理中心门户中的&quot;添加 Android 应用商店应用程序&quot;窗格"  lightbox="images/mda-addandroidstoreapp.png":::

2. 在" **添加应用程序"页** 的"应用程序信息"部分 *，输入* ：

   - **名称**
   - **说明**
   - **Publisher** Microsoft。
   - **作为 Defender** for Endpoint (https://play.google.com/store/apps/details?id=com.microsoft.scmx 的应用商店 URL Google Play 应用商店 URL) 

   其他字段是可选的。 选择 **下一步**。

   :::image type="content" source="images/mda-addappinfo.png" alt-text="在管理中心门户中显示应用程序发布者和 URL 信息的&quot;添加Microsoft Endpoint Manager页面" lightbox="images/mda-addappinfo.png":::

3. 在" *分配"* 部分，转到" **必需"** 部分并选择" **添加组"。** 然后，你可以选择你要 (Android) Defender for Endpoint 的用户组策略。 选择 **"选择** "，然后选择"下一 **步"**。

    > [!NOTE]
    > 所选用户组应由 Intune 注册的用户组成。
    >
    > :::image type="content" source="images/363bf30f7d69a94db578e8af0ddd044b.png" alt-text="Microsoft Endpoint Manager管理中心门户的&quot;添加应用&quot;页中的&quot;添加组&quot;窗格" lightbox="images/363bf30f7d69a94db578e8af0ddd044b.png":::

4. 在" **查看+创建** "部分，验证输入的所有信息是否正确，然后选择"创建 **"**。

    片刻后，将成功创建 Defender for Endpoint 应用，页面右上角将显示一条通知。

    :::image type="content" source="images/86cbe56f88bb6e93e9c63303397fc24f.png" alt-text="管理中心门户Microsoft Endpoint Manager应用程序状态窗格" lightbox="images/86cbe56f88bb6e93e9c63303397fc24f.png":::

5. 在显示的"应用信息"页的"监视器"部分，选择"设备安装状态"以验证设备安装是否成功完成。

    :::image type="content" source="images/513cf5d59eaaef5d2b5bc122715b5844.png" alt-text="Microsoft Defender 365 门户中的设备安装状态页" lightbox="images/513cf5d59eaaef5d2b5bc122715b5844.png":::

### <a name="complete-onboarding-and-check-status"></a>完成载入和检查状态

1. 在设备上安装 Android 上的 Defender for Endpoint 后，你将看到应用图标。

   :::image type="content" source="images/7cf9311ad676ec5142002a4d0c2323ca.jpg" alt-text="搜索窗格中列出的 Microsoft Defender ATP 图标" lightbox="images/7cf9311ad676ec5142002a4d0c2323ca.jpg":::

2. 点击 Microsoft Defender for Endpoint 应用图标并按照屏幕上的说明完成应用载入。 详细信息包括最终用户接受 Android 上的 Defender for Endpoint 所需的 Android 权限。

3. 成功载入后，设备将开始显示在设备门户中的设备Microsoft 365 Defender上。

    :::image type="content" source="images/9fe378a1dce0f143005c3aa53d8c4f51.png" alt-text="Microsoft Defender 终结点门户中的设备"  lightbox="images/9fe378a1dce0f143005c3aa53d8c4f51.png":::

## <a name="deploy-on-android-enterprise-enrolled-devices"></a>在 Android Enterprise注册的设备上部署

Android 上的 Defender for Endpoint 支持 Android Enterprise注册的设备。

有关 Intune 支持的注册选项的详细信息，请参阅 [注册选项](/mem/intune/enrollment/android-enroll)。

**目前，支持部署具有工作配置文件和公司所有完全托管用户设备注册的个人拥有设备。**

## <a name="add-microsoft-defender-for-endpoint-on-android-as-a-managed-google-play-app"></a>将 Android 上的 Microsoft Defender for Endpoint 添加为托管 Google Play 应用

按照以下步骤将 Microsoft Defender for Endpoint 应用添加到托管 Google Play。

1. In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431)， go to **Apps** \> **Android Apps** \> **Add** and select **Managed Google Play app**.

    :::image type="content" source="images/579ff59f31f599414cedf63051628b2e.png" alt-text="管理中心门户Microsoft Endpoint Manager应用程序添加窗格" lightbox="images/579ff59f31f599414cedf63051628b2e.png":::

2. 在随后加载的托管 Google Play 页面上，转到搜索框并输入 `Microsoft Defender`。 你的搜索应在托管 Google Play 中显示 Microsoft Defender for Endpoint 应用。 从应用搜索结果中单击 Microsoft Defender for Endpoint 应用。

    :::image type="content" source="images/0f79cb37900b57c3e2bb0effad1c19cb.png" alt-text="管理中心门户中的Microsoft Endpoint Manager Google Play 页面" lightbox="images/0f79cb37900b57c3e2bb0effad1c19cb.png":::

3. 在接下来启动的应用描述页面中，你应该能够看到 Defender for Endpoint 上的应用详细信息。 查看页面上的信息，然后选择"批准 **"**。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/07e6d4119f265037e3b80a20a73b856f.png" alt-text="管理中心门户中托管的 Google Play Microsoft Endpoint Manager页面" lightbox="images/07e6d4119f265037e3b80a20a73b856f.png":::
      

4. 你将看到 Defender for Endpoint 为它工作获取的权限。 查看它们，然后选择"批准 **"**。

    :::image type="content" source="images/206b3d954f06cc58b3466fb7a0bd9f74.png" alt-text="Microsoft Defender 365 门户中的权限审批页面" lightbox="images/206b3d954f06cc58b3466fb7a0bd9f74.png":::

5. You'll be presented with the Approval settings page. 此页面确认你优先处理 Android 上的 Defender for Endpoint 可能请求的新应用权限。 查看选项并选择首选选项。 选择“**完成**”。

    默认情况下，托管 Google Play 在应用请求新权限时 **选择"保持已批准"**。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ffecfdda1c4df14148f1526c22cc0236.png" alt-text=" Microsoft Defender 365 门户中的审批设置配置完成页面" lightbox="images/ffecfdda1c4df14148f1526c22cc0236.png":::

6. 完成权限处理选择后，选择" **同步** "以将 Microsoft Defender for Endpoint 同步到应用列表。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/34e6b9a0dae125d085c84593140180ed.png" alt-text="Microsoft Defender 365 门户中的&quot;同步&quot;窗格" lightbox="images/34e6b9a0dae125d085c84593140180ed.png":::

7. 同步将在几分钟后完成。

    :::image type="content" source="images/9fc07ffc150171f169dc6e57fe6f1c74.png" alt-text="Microsoft Defender 365 门户的 Android 应用页面中的应用程序同步状态窗格"  lightbox="images/9fc07ffc150171f169dc6e57fe6f1c74.png":::

8. 选择 **Android 应用** 屏幕中的"刷新"按钮，Microsoft Defender for Endpoint 应在应用列表中可见。

    :::image type="content" source="images/fa4ac18a6333335db3775630b8e6b353.png" alt-text="显示已同步应用程序的页面" lightbox="images/fa4ac18a6333335db3775630b8e6b353.png":::

9. Defender for Endpoint 通过 Intune 支持托管设备的应用配置策略。 此功能可用于自动授予适用的 Android () ，因此最终用户无需接受这些 (权限) 。

    1. 在应用 **页面中** ，转到策略 **>应用配置策略>添加>托管设备**。

       :::image type="content" source="images/android-mem.png" alt-text="管理中心门户中的&quot;Microsoft Endpoint Manager策略&quot;窗格" lightbox="images/android-mem.png":::

    1. 在" **创建应用配置策略"** 页中，输入以下详细信息：

        - 名称：Microsoft Defender for Endpoint。
        - 选择 **Android Enterprise** 作为平台。
        - 选择 **"仅作为配置文件类型** 的工作配置文件"。
        - 单击 **"选择应用"**，选择 **"Microsoft Defender ATP**"，选择" **确定"** ，然后选择"下一 **步"**。

        :::image type="content" source="images/android-create-app.png" alt-text=" &quot;关联的应用程序详细信息&quot;窗格" lightbox="images/android-create-app.png":::

    1. In the **设置** page， go to the Permissions section click on Add to view the list of supported permissions. 在"添加权限"部分，选择以下权限：

       - 外部存储 (读取) 
       - 外部存储 (写入) 

       然后，选择“**确定**”。

       :::image type="content" source="images/android-create-app-config.png" alt-text="&quot;添加权限&quot;窗格" lightbox="images/android-create-app-config.png":::

    1. 现在应该可以看到列出的权限，现在可以通过在"权限状态"下拉列表中选择"自动授予"，然后选择"下一步"来自动授予 **这两种权限**。

       :::image type="content" source="images/android-auto-grant.png" alt-text="&quot;权限&quot;状态窗格" lightbox="images/android-auto-grant.png":::

    1. 在 **"分配** "页中，选择此应用配置策略将分配到的用户组。 单击 **"选择要包含的组"** 并选择适用的组，然后选择"下一步 **"**。 在此处选择的组通常是你将 Microsoft Defender for Endpoint Android 应用分配到的同一个组。

       :::image type="content" source="images/android-select-group.png" alt-text="&quot;选定的组&quot;窗格" lightbox="images/android-select-group.png":::

    1. In the **Review + Create** page that comes up next， review all the information and then select **Create**.

        Defender for Endpoint 的应用配置策略（自动授予存储权限）现在已分配给所选用户组。

        > [!div class="mx-imgBorder"]
        > :::image type="content" source="images/android-review-create.png" alt-text="&quot;创建应用配置策略&quot;页中的&quot;查看 + 创建&quot;选项卡" lightbox="images/android-review-create.png":::

10. 在 **"属性分配编辑**"列表中选择\>  \> \>"Microsoft Defender ATP **应用"**。

   :::image type="content" source="images/mda-properties.png" alt-text="&quot;属性&quot;页上的&quot;编辑&quot;选项" lightbox="images/mda-properties.png":::

11. 将应用分配为 *用户组所需的* 应用。 下次通过应用 *同步* 设备时，它会自动安装在公司门户配置文件中。 此分配可通过导航到"必需"部分\>"添加组"**，选择用户组** 并单击"选择 **"** 完成。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ea06643280075f16265a596fb9a96042.png" alt-text="&quot;编辑应用程序&quot;页" lightbox="images/ea06643280075f16265a596fb9a96042.png":::

12. 在" **编辑应用程序"** 页中，查看上面输入的所有信息。 然后选择" **查看 + 保存** "，然后 **再次"保存** "以开始工作分配。

### <a name="auto-setup-of-always-on-vpn"></a>自动设置始终打开 VPN

Defender for Endpoint 通过 Intune 支持托管设备的设备配置策略。 此功能可用于在 Android Enterprise 设备上自动设置始终打开 **VPN**，因此最终用户无需在载入时设置 VPN 服务。

1. 在 **设备上，** 选择 **配置文件 创建** \> **配置文件** \> **平台** \> **Android Enterprise**

   根据 **你的设备** 注册类型，在下列选项之一下选择设备限制：
   - **完全托管、专用Corporate-Owned工作配置文件**
   - **个人拥有的工作配置文件**

   选择“**创建**”。

   :::image type="content" source="images/1autosetupofvpn.png" alt-text="&quot;策略&quot;窗格中的&quot;配置文件&quot;菜单项" lightbox="images/1autosetupofvpn.png":::

2. **配置设置** 提供 **用于** 唯一标识配置文件的名称和说明。

   :::image type="content" source="images/2autosetupofvpn.png" alt-text="&quot;基本&quot;窗格中的设备配置文件名称和说明字段" lightbox="images/2autosetupofvpn.png":::

3. 选择 **连接** 并配置 VPN：

   - 启用 **始终启用 VPN**

     在工作配置文件中设置 VPN 客户端，尽可能自动连接和重新连接到 VPN。 在给定设备上只能为始终打开的 VPN 配置一个 VPN 客户端，因此请确保将始终打开的 VPN 策略部署到单个设备不超过一个。

   - **选择"** VPN 客户端中的自定义"下拉列表

     在这种情况下，自定义 VPN 是 Defender for Endpoint VPN，用于提供 Web 保护功能。

     > [!NOTE]
     > 必须在用户设备上安装 Microsoft Defender for Endpoint 应用，才能自动设置此 VPN。

   - 在 **Google** Play 应用商店中输入 Microsoft Defender for Endpoint 应用的程序包 ID。 对于 Defender 应用 URL， <https://play.google.com/store/apps/details?id=com.microsoft.scmx>程序包 ID 为 **com.microsoft.scmx**

   - **锁定模式** 未配置 (默认) 

     :::image type="content" source="images/3autosetupofvpn.png" alt-text="&quot;配置设置&quot;选项卡下的&quot;连接&quot;窗格" lightbox="images/3autosetupofvpn.png":::

4. **Assignment**

   在 **"分配** "页中，选择此应用配置策略将分配到的用户组。 选择 **"选择要包含** 的组"并选择适用的组，然后选择"下一步 **"**。 在此处选择的组通常是你将 Microsoft Defender for Endpoint Android 应用分配到的同一个组。

   :::image type="content" source="images/4autosetupofvpn.png" alt-text="&quot;设备限制&quot;中的&quot;设备配置文件分配&quot;窗格" lightbox="images/4autosetupofvpn.png":::

5. In the **Review + Create** page that comes up next， review all the information and then select **Create**.
现在，设备配置文件已分配给选定的用户组。

   :::image type="content" source="images/5autosetupofvpn.png" alt-text="设备配置文件的审阅 + 创建预配" lightbox="images/5autosetupofvpn.png":::

## <a name="check-status-and-complete-onboarding"></a>检查状态和完成载入

1. 通过单击"设备安装状态"确认 Android 上的 Microsoft Defender for Endpoint **的安装状态**。 验证设备是否在此处显示。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/900c0197aa59f9b7abd762ab2b32e80c.png" alt-text="设备安装状态窗格" lightbox="images/900c0197aa59f9b7abd762ab2b32e80c.png":::

2. 在设备上，可以通过访问工作配置文件来验证载入 **状态**。 确认 Defender for Endpoint 可用，并且你已使用工作配置文件注册到个人 **拥有的设备**。 如果你注册到企业拥有、完全 **托管** 的用户设备，你将在设备上拥有一个配置文件，你可以确认 Defender for Endpoint 可用。

    :::image type="content" source="images/c2e647fc8fa31c4f2349c76f2497bc0e.png" alt-text="应用程序显示窗格" lightbox="images/c2e647fc8fa31c4f2349c76f2497bc0e.png":::

3. 安装应用后，打开应用并接受权限，然后载入应该会成功。

    :::image type="content" source="images/MDE_new.png" alt-text="Th display of a Microsoft Defender for Endpoint application on a mobile device" lightbox="images/MDE_new.png":::

4. 在此阶段，设备已成功载入 Android 上的 Defender for Endpoint。 可以通过导航到"设备 [清单"Microsoft 365 Defender](https://security.microsoft.com)门户 **对此进行验证**。

    :::image type="content" source="images/9fe378a1dce0f143005c3aa53d8c4f51.png" alt-text="Microsoft Defender for Endpoint 门户" lightbox="images/9fe378a1dce0f143005c3aa53d8c4f51.png":::

## <a name="related-topics"></a>相关主题

- [Android 上的 Microsoft Defender for Endpoint 概述](microsoft-defender-endpoint-android.md)
- [在 Android 功能上配置 Microsoft Defender for Endpoint](android-configure.md)
