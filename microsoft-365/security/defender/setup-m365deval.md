---
title: 设置Microsoft 365 Defender试用实验室或试点环境
description: 访问Microsoft 365 Defender门户，然后设置Microsoft 365 Defender试用实验室环境
keywords: Microsoft 365 Defender试用设置，Microsoft 365 Defender试点设置，尝试Microsoft 365 Defender，Microsoft 365 Defender评估实验室设置
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
ms.openlocfilehash: 5d516a7062d8c6f617cee2a260f27ee896689f2c
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64667331"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a>在实验室环境中设置Microsoft 365 Defender试用版 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender 

本主题指导你设置专用实验室环境。 有关在生产环境中设置试用版的信息，请参阅新的[评估和试点Microsoft 365 Defender](eval-overview.md)指南。 

## <a name="create-an-office-365-e5-trial-tenant"></a>创建Office 365 E5试用租户
>[!NOTE]
>如果已有现有Office 365或Azure Active Directory订阅，则可以跳过Office 365 E5试用租户创建步骤。

1. 转到 [Office 365 E5产品门户](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)，然后选择 **"免费试用** 版"。

   :::image type="content" source="../../media/mtp-eval-9.png" alt-text="Office 365 E5免费试用页" lightbox="../../media/mtp-eval-9.png":::
  
2. 通过在个人或公司)  (输入电子邮件地址来完成试用注册。 单击 **"设置帐户**"。

   :::image type="content" source="../../media/mtp-eval-10.png" alt-text="Office 365 E5试用注册设置页" lightbox="../../media/mtp-eval-10.png":::

3. 填写名字、姓氏、业务电话号码、公司名称、公司规模以及国家或地区。  

   :::image type="content" source="../../media/mtp-eval-11.png" alt-text="Office 365 E5试用注册设置页，询问姓名、电话和公司详细信息" lightbox="../../media/mtp-eval-11.png":::
   
   > [!NOTE]
   > 在此处设置的国家/地区决定了Office 365将托管的数据中心区域。
  
4. 选择验证首选项：通过短信或呼叫。 单击 **"发送验证码**"。 

   :::image type="content" source="../../media/mtp-eval-12.png" alt-text="请求验证首选项的Office 365 E5试用注册设置页" lightbox="../../media/mtp-eval-12.png":::

5. 设置租户的自定义域名，然后单击 **"下一步**"。

   :::image type="content" source="../../media/mtp-eval-13.png" alt-text="可在其中设置自定义域名的Office 365 E5试用注册设置页" lightbox="../../media/mtp-eval-13.png":::
 
6. 设置第一个标识，该标识将是租户的全局管理员。 填写 **名称** 和 **密码**。 单击“**注册**”。

   :::image type="content" source="../../media/mtp-eval-14.png" alt-text="可在其中设置业务标识的Office 365 E5试用注册设置页" lightbox="../../media/mtp-eval-14.png":::

7. 单击 **"转到设置**"以完成Office 365 E5试用租户预配。

   :::image type="content" source="../../media/mtp-eval-15.png" alt-text="Office 365 E5试用注册设置页提示单击&quot;转到安装&quot;按钮" lightbox="../../media/mtp-eval-15.png":::

8. 将公司域连接到Office 365租户。 [可选]选择 **连接已拥有的域**，然后键入域名。 单击“**下一步**”。

   :::image type="content" source="../../media/mtp-eval-16.png" alt-text="应在其中个性化登录和电子邮件的Office 365 E5设置页面" lightbox="../../media/mtp-eval-16.png":::
 
9. 添加 TXT 或 MX 记录以验证域所有权。 将 TXT 或 MX 记录添加到域后，选择" **验证**"。

   :::image type="content" source="../../media/mtp-eval-17.png" alt-text="应在其中添加 MX 记录的 TXT 以验证域的Office 365 E5设置页" lightbox="../../media/mtp-eval-17.png":::
 
10. [可选]为租户创建更多用户帐户。 可以通过单击" **下** 一步"跳过此步骤。

    :::image type="content" source="../../media/mtp-eval-18.png" alt-text="可在其中添加更多用户的Office 365 E5设置页" lightbox="../../media/mtp-eval-18.png":::
 
11. [可选]下载Office应用。 单击 **"下一** 步"跳过此步骤。 

    :::image type="content" source="../../media/mtp-eval-19.png" alt-text="可在其中安装Office应用的Office 365 E5页" lightbox="../../media/mtp-eval-19.png":::

12. [可选]迁移电子邮件。 同样，可以跳过此步骤。

    :::image type="content" source="../../media/mtp-eval-20.png" alt-text="可在其中设置是否迁移电子邮件的Office 365 E5" lightbox="../../media/mtp-eval-20.png":::
 
13. 选择联机服务。 选择 **Exchange**，然后单击 **"下一步**"。 

    :::image type="content" source="../../media/mtp-eval-21.png" alt-text="可在其中选择联机服务的Office 365 E5" lightbox="../../media/mtp-eval-21.png":::

14. 将 MX、CNAME 和 TXT 记录添加到域。 完成后，选择 **"验证**"。

    :::image type="content" source="../../media/mtp-eval-22.png" alt-text="可在此处添加 DNS 记录的Office 365 E5" lightbox="../../media/mtp-eval-22.png":::
 
15. 恭喜你，你已完成Office 365租户的预配。

    :::image type="content" source="../../media/mtp-eval-23.png" alt-text="Office 365 E5安装完成确认页" lightbox="../../media/mtp-eval-23.png":::
    

## <a name="enable-microsoft-365-trial-subscription"></a>启用Microsoft 365试用订阅

>[!NOTE]
>注册试用版提供 25 个用户许可证，供你使用一个月。 有关详细信息，请参阅[试用或购买Microsoft 365订阅](../../commerce/try-or-buy-microsoft-365.md)。

1. 在 [Microsoft 365 管理中心](https://admin.microsoft.com/)，单击 **"计费**"，然后导航到 **"购买"服务**。

2. 选择 **Microsoft 365 E5**，然后单击 **"开始免费试用**"。 

   :::image type="content" source="../../media/mtp-eval-24.png" alt-text="&quot;Microsoft 365 E5开始免费试用&quot;页" lightbox="../../media/mtp-eval-24.png":::

3. 选择验证首选项：通过短信或呼叫。 决定后，输入电话号码，选择 **"给我发短信** "或 **"给我打电话"** ，具体取决于你的选择。

   :::image type="content" source="../../media/mtp-eval-25.png" alt-text="&quot;Microsoft 365 E5开始免费试用版&quot;页面，要求提供联系人详细信息以发送代码以证明你不是机器人" lightbox="../../media/mtp-eval-25.png":::
 
4. 输入验证码，然后单击 **"开始免费试用**"。

   :::image type="content" source="../../media/mtp-eval-26.png" alt-text="Microsoft 365 E5开始免费试用页，可在其中填写系统发送的验证码，以证明你不是机器人" lightbox="../../media/mtp-eval-26.png":::

5. 单击"**立即试** 用"以确认Microsoft 365 E5试用版。

   :::image type="content" source="../../media/mtp-eval-27.png" alt-text="Microsoft 365 E5开始免费试用页，应在其中打卡&quot;立即试用&quot;按钮以开始" lightbox="../../media/mtp-eval-27.png":::
 
6. 转到 **Microsoft 365 管理** **CenterUsersActive** >  >  **用户**。 选择用户帐户，选择 **"管理产品许可证**"，然后将许可证从Office 365 E5交换到 **Microsoft 365 E5**。 单击 **“保存”**。

   :::image type="content" source="../../media/mtp-eval-28.png" alt-text="可在其中选择Microsoft 365 E5许可证的&quot;Microsoft 365 管理中心&quot;页" lightbox="../../media/mtp-eval-28.png":::
 
7. 再次选择全局管理员帐户，然后单击 **"管理用户名**"。

   :::image type="content" source="../../media/mtp-eval-29.png" alt-text="可在其中选择&quot;帐户&quot;和管理用户名的&quot;Microsoft 365 管理中心&quot;页" lightbox="../../media/mtp-eval-29.png":::

8. [可选]根据前面步骤中选择的内容，将域从 *onmicrosoft.com* 更改为自己的域。 单击“**保存更改**”。

   :::image type="content" source="../../media/mtp-eval-30.png" alt-text="可在其中更改域首选项的&quot;Microsoft 365 管理中心&quot;页" lightbox="../../media/mtp-eval-30.png":::

## <a name="next-step"></a>后续步骤
|[阶段 3：配置&载入](config-m365d-eval.md) | 为Microsoft 365 Defender试验实验室或试验环境配置每个Microsoft 365 Defender支柱，并载入终结点。
|:-------|:-----|
