---
title: 使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint
description: 介绍如何使用 Microsoft Intune 在 Android 上部署Microsoft Defender for Endpoint
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
ms.openlocfilehash: 461664cc72486a49e5b7bd9be44235559409adff
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64825231"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-android-with-microsoft-intune"></a>使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

了解如何在已注册设备Intune 公司门户 Android 上部署 Defender for Endpoint。 有关Intune设备注册的详细信息，请[参阅注册设备](/mem/intune/user-help/enroll-device-android-company-portal)。

> [!NOTE]
> **Android 上的 Defender for Endpoint 现已在 [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) 上推出**
>
> 可以从 Intune 连接到 Google Play，跨设备管理员和 Android Enterprise注册模式部署 Defender for Endpoint 应用。
>
> 通过 Google Play 自动更新应用。

## <a name="deploy-on-device-administrator-enrolled-devices"></a>在设备管理员注册的设备上部署

**在 Android 上部署 Defender for Endpoint on Intune 公司门户 - 设备管理员注册的设备**

了解如何在 Android 上部署 Defender for Endpoint on Intune 公司门户 - 设备管理员已注册设备。

### <a name="add-as-android-store-app"></a>添加为 Android 应用商店应用

1. 在 [Microsoft Endpoint Manager管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，转到 **“应用** \> **Android 应用** \> **添加 \> Android 应用商店”应用** 并选择 **“选择**”。

   :::image type="content" source="images/mda-addandroidstoreapp.png" alt-text="Microsoft Endpoint Manager管理中心门户中的“添加 Android 应用商店应用程序”窗格"  lightbox="images/mda-addandroidstoreapp.png":::

2. 在 **“添加应用** ”页和“ *应用信息* ”部分中，输入：

   - **名称**
   - **说明**
   - **Publisher** 为 Microsoft。
   - **应用商店 URL** 作为 https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint 应用 Google Play 应用商店 URL) 

   其他字段是可选的。 选择 **下一步**。

   :::image type="content" source="images/mda-addappinfo.png" alt-text="在 Microsoft Endpoint Manager 管理中心门户中显示应用程序发布者和 URL 信息的“添加应用”页" lightbox="images/mda-addappinfo.png":::

3. 在 *“分配”* 部分，转到 **“必需** ”部分，然后选择 **“添加组”。** 然后，可以选择用户组 (要在 Android 应用上面向 Defender for Endpoint 的) 。 选择 **“选择** ”，然后选择 **“下一步**”。

    > [!NOTE]
    > 所选用户组应由Intune注册的用户组成。
    >
    > :::image type="content" source="images/363bf30f7d69a94db578e8af0ddd044b.png" alt-text="Microsoft Endpoint Manager管理中心门户中“添加应用”页中的“添加组”窗格" lightbox="images/363bf30f7d69a94db578e8af0ddd044b.png":::

4. 在 **“审阅+创建”** 部分中，验证输入的所有信息是否正确，然后选择 **“创建**”。

    几分钟后，将成功创建 Defender for Endpoint 应用，并在页面右上角显示通知。

    :::image type="content" source="images/86cbe56f88bb6e93e9c63303397fc24f.png" alt-text="Microsoft Endpoint Manager管理中心门户中的应用程序状态窗格" lightbox="images/86cbe56f88bb6e93e9c63303397fc24f.png":::

5. 在显示的应用信息页的 **“监视器”** 部分中，选择 **“设备安装状态** ”以验证设备安装是否已成功完成。

    :::image type="content" source="images/513cf5d59eaaef5d2b5bc122715b5844.png" alt-text="Microsoft Defender 365 门户中的“设备安装状态”页" lightbox="images/513cf5d59eaaef5d2b5bc122715b5844.png":::

### <a name="complete-onboarding-and-check-status"></a>完成载入和检查状态

1. 在设备上安装 Android 上的 Defender for Endpoint 后，你将看到应用图标。

   :::image type="content" source="images/7cf9311ad676ec5142002a4d0c2323ca.jpg" alt-text="“搜索”窗格中列出的 Microsoft Defender ATP 图标" lightbox="images/7cf9311ad676ec5142002a4d0c2323ca.jpg":::

2. 点击Microsoft Defender for Endpoint应用图标，并按照屏幕上的说明完成应用的载入。 详细信息包括最终用户接受 Android 上 Defender for Endpoint 所需的 Android 权限。

3. 成功载入后，设备将开始显示在Microsoft 365 Defender门户中的“设备”列表中。

    :::image type="content" source="images/9fe378a1dce0f143005c3aa53d8c4f51.png" alt-text="Microsoft Defender for Endpoint门户中的设备"  lightbox="images/9fe378a1dce0f143005c3aa53d8c4f51.png":::

## <a name="deploy-on-android-enterprise-enrolled-devices"></a>在已注册的 Android Enterprise设备上部署

Android 上的 Defender for Endpoint 支持 Android Enterprise注册的设备。

有关Intune支持的注册选项的详细信息，请参阅[注册选项](/mem/intune/enrollment/android-enroll)。

**目前，支持使用工作配置文件和公司拥有的完全托管用户设备注册的个人拥有设备进行部署。**

## <a name="add-microsoft-defender-for-endpoint-on-android-as-a-managed-google-play-app"></a>在 Android 上将Microsoft Defender for Endpoint添加为托管 Google Play 应用

按照以下步骤将Microsoft Defender for Endpoint应用添加到托管 Google Play 中。

1. 在 [Microsoft Endpoint Manager管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，转到 **“应用** \> **Android 应用** \> **添加”**，然后选择 **托管 Google Play 应用**。

    :::image type="content" source="images/579ff59f31f599414cedf63051628b2e.png" alt-text="Microsoft Endpoint Manager管理中心门户中的“应用程序添加”窗格" lightbox="images/579ff59f31f599414cedf63051628b2e.png":::

2. 在随后加载的托管 Google Play 页面上，转到搜索框并输入 `Microsoft Defender`。 搜索应在托管 Google Play 中显示Microsoft Defender for Endpoint应用。 单击应用搜索结果中的Microsoft Defender for Endpoint应用。

    :::image type="content" source="images/0f79cb37900b57c3e2bb0effad1c19cb.png" alt-text="Microsoft Endpoint Manager管理中心门户中的托管 Google Play 页面" lightbox="images/0f79cb37900b57c3e2bb0effad1c19cb.png":::

3. 在下一页的“应用说明”页中，应该能够看到有关 Defender for Endpoint 的应用详细信息。 查看页面上的信息，然后选择 **“批准**”。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/07e6d4119f265037e3b80a20a73b856f.png" alt-text="Microsoft Endpoint Manager管理中心门户中托管 Google Play 的页面" lightbox="images/07e6d4119f265037e3b80a20a73b856f.png":::
      

4. 你将获得 Defender for Endpoint 获取的权限，使其正常工作。 查看它们，然后选择 **“批准**”。

    :::image type="content" source="images/206b3d954f06cc58b3466fb7a0bd9f74.png" alt-text="Microsoft Defender 365 门户中的权限审批页" lightbox="images/206b3d954f06cc58b3466fb7a0bd9f74.png":::

5. 你将看到“审批设置”页。 该页面确认你首选处理 Android 上的 Defender for Endpoint 可能要求的新应用权限。 查看选项并选择首选选项。 选择“**完成**”。

    默认情况下，当 **应用请求新权限时**，托管 Google Play 选择“保持批准”。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ffecfdda1c4df14148f1526c22cc0236.png" alt-text=" Microsoft Defender 365 门户中的审批设置配置完成页" lightbox="images/ffecfdda1c4df14148f1526c22cc0236.png":::

6. 进行权限处理选择后，选择 **“同步**”以将Microsoft Defender for Endpoint同步到应用列表。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/34e6b9a0dae125d085c84593140180ed.png" alt-text="Microsoft Defender 365 门户中的“同步”窗格" lightbox="images/34e6b9a0dae125d085c84593140180ed.png":::

7. 同步将在几分钟内完成。

    :::image type="content" source="images/9fc07ffc150171f169dc6e57fe6f1c74.png" alt-text="Microsoft Defender 365 门户中 Android 应用页中的应用程序同步状态窗格"  lightbox="images/9fc07ffc150171f169dc6e57fe6f1c74.png":::

8. 在 Android 应用屏幕中选择 **“刷新**”按钮，Microsoft Defender for Endpoint应在应用列表中可见。

    :::image type="content" source="images/fa4ac18a6333335db3775630b8e6b353.png" alt-text="显示同步应用程序的页面" lightbox="images/fa4ac18a6333335db3775630b8e6b353.png":::

9. Defender for Endpoint 通过Intune支持托管设备的应用配置策略。 可以利用此功能为 Defender 选择不同的配置。

    1. 在 **“应用** ”页中，转到 **“策略>应用配置策略>添加>托管设备**。

       :::image type="content" source="images/android-mem.png" alt-text="Microsoft Endpoint Manager管理中心门户中的“应用配置策略”窗格" lightbox="images/android-mem.png":::

    1. 在 **“创建应用配置策略** ”页中，输入以下详细信息：

        - 名称：Microsoft Defender for Endpoint。
        - 选择 **Android Enterprise** 作为平台。
        - **仅选择工作配置文件** 作为配置文件类型。
        - 单击 **“选择应用**”，选择 **“Microsoft Defender ATP**”，选择 **“确定** ”，然后 **选择“下一步**”。

        :::image type="content" source="images/android-create-app.png" alt-text=" “关联的应用详细信息”窗格" lightbox="images/android-create-app.png":::

    1. 在 **设置** 页中，转到 **“配置设置”** 部分，并选择 **“使用配置设计器”的“配置设置”** 格式。 

       :::image type="content" alt-text="android 创建应用配置策略的图像。" source="images/configurationformat.png" lightbox="images/configurationformat.png":::

    1. 单击 **“添加** ”可查看支持的配置列表。 选择所需的配置，然后单击 **“确定**”。

       :::image type="content" alt-text="为 android 选择配置策略的图像。" source="images/selectconfigurations.png" lightbox="images/selectconfigurations.png":::


    1. 应会看到列出的所有所选配置。 可以根据需要更改配置值，然后选择 **“下一步**”。
        
        :::image type="content" alt-text="所选配置策略的图像。" source="images/listedconfigurations.png" lightbox="images/listedconfigurations.png":::
       

    1. 在 **“分配”** 页中，选择此应用配置策略将分配到的用户组。 单击 **“选择组”以包括** 并选择适用的组，然后选择 **“下一步**”。 此处选择的组通常是你将Microsoft Defender for Endpoint Android 应用分配到的同一组。

       :::image type="content" source="images/android-select-group.png" alt-text="“所选组”窗格" lightbox="images/android-select-group.png":::

    1. 在下一页的 **“审阅 + 创建”** 页中，查看所有信息，然后选择 **“创建**”。

        为 Defender for Endpoint 自动授予存储权限的应用配置策略现在分配给所选用户组。

        > [!div class="mx-imgBorder"]
        > :::image type="content" source="images/android-review-create.png" alt-text="“创建应用配置策略”页中的“审阅 + 创建”选项卡" lightbox="images/android-review-create.png":::

10. 在 **“属性****分配** \> **编辑**”列表\>\>中选择 **Microsoft Defender ATP** 应用。

   :::image type="content" source="images/mda-properties.png" alt-text="“属性”页上的“编辑”选项" lightbox="images/mda-properties.png":::

11. 将应用作为 *必需* 应用分配给用户组。 在下一次通过公司门户应用同步设备期间，它会自动安装在 *工作配置文件* 中。 可以通过导航到 *“必需*”部分\>**“添加组、** 选择用户组并单击 **”选择**“来完成此分配。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ea06643280075f16265a596fb9a96042.png" alt-text="“编辑应用程序”页" lightbox="images/ea06643280075f16265a596fb9a96042.png":::

12. 在 **“编辑应用程序** ”页中，查看上面输入的所有信息。 然后选择 **“审阅 + 保存** ”，然后再次 **保存** 以开始分配。

### <a name="auto-setup-of-always-on-vpn"></a>Always-on VPN 的自动设置

Defender for Endpoint 通过Intune支持托管设备的设备配置策略。 此功能可用于在 Android Enterprise已注册设备上 **自动设置 Always-on VPN**，因此最终用户无需在加入时设置 VPN 服务。

1. 在 **设备** 上，选择 **“配置文件****创建配置文件** \> \> **平台** \> **Android Enterprise**

   根据 **设备** 注册类型，选择下列其中一项下的设备限制：
   - **完全托管、专用和Corporate-Owned工作配置文件**
   - **个人拥有的工作配置文件**

   选择“**创建**”。

   :::image type="content" source="images/1autosetupofvpn.png" alt-text="“策略”窗格中的“配置文件”菜单项" lightbox="images/1autosetupofvpn.png":::

2. **配置设置** 提供用于唯一标识配置文件的 **名称** 和 **说明**。

   :::image type="content" source="images/2autosetupofvpn.png" alt-text="“基本信息”窗格中的设备配置文件名称和说明字段" lightbox="images/2autosetupofvpn.png":::

3. 选择 **连接并** 配置 VPN：

   - 启用 **Always-on VPN**

     在工作配置文件中设置 VPN 客户端，以便尽可能自动连接并重新连接到 VPN。 只有一个 VPN 客户端可以在给定设备上为始终打开的 VPN 配置，因此请确保在单个设备上部署的 VPN 策略不超过一个。

   - 在 VPN 客户端下拉列表中选择 **“自定义** ”

     本例中的自定义 VPN 是用于提供 Web 保护功能的 Defender for Endpoint VPN。

     > [!NOTE]
     > Microsoft Defender for Endpoint应用必须安装在用户的设备上，才能运行此 VPN 的自动设置。

   - 在 Google Play 商店中输入Microsoft Defender for Endpoint应用的 **包 ID**。 对于 Defender 应用 URL <https://play.google.com/store/apps/details?id=com.microsoft.scmx>，包 ID 为 **com.microsoft.scmx**

   - **锁定模式** 未配置 (默认) 

     :::image type="content" source="images/3autosetupofvpn.png" alt-text="“配置设置”选项卡下的“连接”窗格" lightbox="images/3autosetupofvpn.png":::

4. **Assignment**

   在 **“分配”** 页中，选择此应用配置策略将分配到的用户组。 选择要包括和选择适用组的 **组** ，然后选择 **“下一步**”。 此处选择的组通常是你将Microsoft Defender for Endpoint Android 应用分配到的同一组。

   :::image type="content" source="images/4autosetupofvpn.png" alt-text="设备限制中的“设备配置文件分配”窗格" lightbox="images/4autosetupofvpn.png":::

5. 在下一页的 **“审阅 + 创建”** 页中，查看所有信息，然后选择 **“创建**”。
设备配置文件现在分配给所选用户组。

   :::image type="content" source="images/5autosetupofvpn.png" alt-text="适用于 Review + create 的设备配置文件预配" lightbox="images/5autosetupofvpn.png":::

## <a name="check-status-and-complete-onboarding"></a>检查状态并完成载入

1. 单击“设备安装状态”，确认 Android 上Microsoft Defender for Endpoint的 **安装状态**。 验证设备是否显示在此处。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/900c0197aa59f9b7abd762ab2b32e80c.png" alt-text="设备安装状态窗格" lightbox="images/900c0197aa59f9b7abd762ab2b32e80c.png":::

2. 在设备上，可以通过转到 **工作配置文件** 来验证载入状态。 确认 Defender for Endpoint 可用，并且你已注册到 **具有工作配置文件的个人拥有的设备**。 如果已注册到 **公司拥有的完全托管用户设备，** 则设备上将有一个配置文件，可在其中确认 Defender for Endpoint 可用。

    :::image type="content" source="images/c2e647fc8fa31c4f2349c76f2497bc0e.png" alt-text="应用程序显示窗格" lightbox="images/c2e647fc8fa31c4f2349c76f2497bc0e.png":::

3. 安装应用后，打开应用并接受权限，然后载入应成功。

    :::image type="content" source="images/MDE_new.png" alt-text="在移动设备上显示Microsoft Defender for Endpoint应用程序" lightbox="images/MDE_new.png":::

4. 在此阶段，设备已成功载入 Android 上的 Defender for Endpoint。 可以通过导航到“**设备清单**”页，在 [Microsoft 365 Defender门户](https://security.microsoft.com)上验证这一点。

    :::image type="content" source="images/9fe378a1dce0f143005c3aa53d8c4f51.png" alt-text="Microsoft Defender for Endpoint门户" lightbox="images/9fe378a1dce0f143005c3aa53d8c4f51.png":::

## <a name="related-topics"></a>相关主题

- [Android 上的 Microsoft Defender for Endpoint 概述](microsoft-defender-endpoint-android.md)
- [在 Android 功能上配置 Microsoft Defender for Endpoint](android-configure.md)
