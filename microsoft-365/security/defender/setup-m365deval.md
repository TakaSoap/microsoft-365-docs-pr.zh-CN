---
title: 设置你的Microsoft 365 Defender试验实验室或试验环境
description: 然后Microsoft 365 Defender访问实验室门户，Microsoft 365 Defender测试实验室环境
keywords: Microsoft 365 Defender试验设置，Microsoft 365 Defender试验设置，请尝试Microsoft 365 Defender，Microsoft 365 Defender测试设置
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 681d9798c6f16f5829bdb4e5272abc3eac719a59
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2022
ms.locfileid: "64500972"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a>在实验室Microsoft 365 Defender设置试用版 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender 

本主题指导您设置专用实验室环境。 有关在生产中设置试用版的信息，请参阅新的评估和试用[Microsoft 365 Defender指南。](eval-overview.md) 

## <a name="create-an-office-365-e5-trial-tenant"></a>创建Office 365 E5租户
>[!NOTE]
>如果你已拥有现有 Office 365 或 Azure Active Directory 订阅，可以跳过Office 365 E5租户创建步骤。

1. 转到产品Office 365 E5 [并选择](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)免费 **试用版**。

   :::image type="content" source="../../media/mtp-eval-9.png" alt-text="免费Office 365 E5页面" lightbox="../../media/mtp-eval-9.png":::
  
2. 通过输入你个人或公司用户的电子邮件地址 (完成) 。 单击 **"设置帐户"**。

   :::image type="content" source="../../media/mtp-eval-10.png" alt-text="&quot;Office 365 E5注册设置&quot;页" lightbox="../../media/mtp-eval-10.png":::

3. 填写你的名字、姓氏、公司电话号码、公司名称、公司规模以及国家/地区。  

   :::image type="content" source="../../media/mtp-eval-11.png" alt-text="The Office 365 E5 trial registration setup page asking for name， phone， and company details" lightbox="../../media/mtp-eval-11.png":::
   
   > [!NOTE]
   > 你在此处设置的一个或多个国家/地区决定了你的Office 365的数据中心区域。
  
4. 选择验证首选项：通过短信或呼叫。 单击 **"发送验证码"**。 

   :::image type="content" source="../../media/mtp-eval-12.png" alt-text="要求Office 365 E5首选项的&quot;试用注册设置&quot;页" lightbox="../../media/mtp-eval-12.png":::

5. 为租户设置自定义域名，然后单击"下一步 **"**。

   :::image type="content" source="../../media/mtp-eval-13.png" alt-text="The Office 365 E5 trial registration setup page where you can set up your custom domain name" lightbox="../../media/mtp-eval-13.png":::
 
6. 设置第一个标识，即租户的全局管理员。 填写 **名称和****密码**。 单击“**注册**”。

   :::image type="content" source="../../media/mtp-eval-14.png" alt-text="The Office 365 E5 trial registration setup page where you can set your business identity" lightbox="../../media/mtp-eval-14.png":::

7. 单击 **"转到设置**"以完成Office 365 E5租户预配。

   :::image type="content" source="../../media/mtp-eval-15.png" alt-text="The Office 365 E5 trial registration setup page prompting to click Go to Setup button" lightbox="../../media/mtp-eval-15.png":::

8. 连接公司域注册到 Office 365 租户。 [可选]选择 **连接你已拥有的域，** 然后键入你的域名。 单击“**下一步**”。

   :::image type="content" source="../../media/mtp-eval-16.png" alt-text="the Office 365 E5 Setup page where you should personalize your sign-in and email" lightbox="../../media/mtp-eval-16.png":::
 
9. 添加 TXT 或 MX 记录以验证域所有权。 将 TXT 或 MX 记录添加到域后，选择"验证 **"**。

   :::image type="content" source="../../media/mtp-eval-17.png" alt-text="&quot;Office 365 E5设置&quot;页，应在其中添加 MX 记录的 TXT 以验证域" lightbox="../../media/mtp-eval-17.png":::
 
10. [可选]为租户创建多个用户帐户。 可以通过单击"下一步"跳过 **此步骤**。

    :::image type="content" source="../../media/mtp-eval-18.png" alt-text="&quot;Office 365 E5设置&quot;页，可在其中添加更多用户" lightbox="../../media/mtp-eval-18.png":::
 
11. [可选]下载Office应用。 单击 **"下一** 步"跳过此步骤。 

    :::image type="content" source="../../media/mtp-eval-19.png" alt-text="&quot;Office 365 E5&quot;页面，可在其中安装 Office 应用" lightbox="../../media/mtp-eval-19.png":::

12. [可选]迁移电子邮件。 同样，可以跳过此步骤。

    :::image type="content" source="../../media/mtp-eval-20.png" alt-text="设置Office 365 E5是否迁移电子邮件的邮箱" lightbox="../../media/mtp-eval-20.png":::
 
13. 选择"联机服务"。 选择"**Exchange**"，然后单击"下一 **步"**。 

    :::image type="content" source="../../media/mtp-eval-21.png" alt-text="可以选择Office 365 E5服务的信息" lightbox="../../media/mtp-eval-21.png":::

14. 将 MX、CNAME 和 TXT 记录添加到你的域。 完成后，选择"验证 **"**。

    :::image type="content" source="../../media/mtp-eval-22.png" alt-text="此处Office 365 E5可以添加 DNS 记录" lightbox="../../media/mtp-eval-22.png":::
 
15. 恭喜！你已完成预配你的 Office 365 租户。

    :::image type="content" source="../../media/mtp-eval-23.png" alt-text="设置Office 365 E5确认页面" lightbox="../../media/mtp-eval-23.png":::
    

## <a name="enable-microsoft-365-trial-subscription"></a>启用Microsoft 365试用版订阅

>[!NOTE]
>注册试用版可为你提供 25 个用户许可证，供一个月使用。 有关详细信息[，请参阅试用或Microsoft 365订阅](../../commerce/try-or-buy-microsoft-365.md)。

1. 从 [Microsoft 365 管理中心，](https://admin.microsoft.com/)单击 **"计费"**，然后导航到"**购买服务"**。

2. 选择 **"Microsoft 365 E5**"，然后单击 **"开始免费试用"**。 

   :::image type="content" source="../../media/mtp-eval-24.png" alt-text="&quot;Microsoft 365 E5免费试用版&quot;页面" lightbox="../../media/mtp-eval-24.png":::

3. 选择验证首选项：通过短信或呼叫。 决定后，输入电话号码，选择" **短信** "或" **呼叫** 我"，具体取决于你的选择。

   :::image type="content" source="../../media/mtp-eval-25.png" alt-text="The Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot" lightbox="../../media/mtp-eval-25.png":::
 
4. 输入验证码，然后单击 **开始免费试用**。

   :::image type="content" source="../../media/mtp-eval-26.png" alt-text="The Microsoft 365 E5 Start free trial page where you can fill out verification code the system sent to prove you are not a robot" lightbox="../../media/mtp-eval-26.png":::

5. 单击 **"立即试用**"确认Microsoft 365 E5试用版。

   :::image type="content" source="../../media/mtp-eval-27.png" alt-text="The Microsoft 365 E5 Start free trial page where you should clock the Try now button to start" lightbox="../../media/mtp-eval-27.png":::
 
6. 转到"Microsoft 365 管理 **CenterUsersActive** >  >  **用户"**。 选择用户帐户，选择"**管理产品许可证**"，然后将许可证从 **Office 365 E5 交换Microsoft 365 E5**。 单击 **“保存”**。

   :::image type="content" source="../../media/mtp-eval-28.png" alt-text="The Microsoft 365 管理 Center page where you can select the Microsoft 365 E5 license" lightbox="../../media/mtp-eval-28.png":::
 
7. 再次选择全局管理员帐户，然后单击" **管理用户名"**。

   :::image type="content" source="../../media/mtp-eval-29.png" alt-text="&quot;Microsoft 365 管理中心&quot;页，可在其中选择&quot;帐户&quot;和&quot;管理用户名&quot;" lightbox="../../media/mtp-eval-29.png":::

8. [可选]将域从 *onmicrosoft.com* 更改为您自己的域，具体取决于你之前步骤中的选择。 单击“**保存更改**”。

   :::image type="content" source="../../media/mtp-eval-30.png" alt-text="&quot;Microsoft 365 管理中心&quot;页，可在其中更改域首选项" lightbox="../../media/mtp-eval-30.png":::

## <a name="next-step"></a>后续步骤
|[阶段 3：配置&载入](config-m365d-eval.md) | 为测试Microsoft 365 Defender环境配置Microsoft 365 Defender功能支柱，并载入终结点。
|:-------|:-----|
