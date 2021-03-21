---
title: 设置 Microsoft 365 Defender 试用实验室或试验环境
description: 访问 Microsoft 365 安全中心，然后设置 Microsoft 365 Defender 试用实验室环境
keywords: Microsoft 威胁防护试用设置， Microsoft 威胁防护试点设置， 尝试 Microsoft 威胁防护， Microsoft 威胁防护评估实验室设置
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 76f46f5205380580cbe5b68d7ede91dddb848036
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918890"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>设置 Microsoft 365 Defender 试用实验室环境 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender 


创建 Microsoft 365 Defender 试用实验室或试验环境并部署它的过程分三个阶段：

|[![阶段 1：准备](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[阶段 1：准备](prepare-mtpeval.md) |![阶段 2：设置](../../media/phase-diagrams/setup.png)<br/>阶段 2：设置 |[![阶段 3：载入](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[阶段 3：载入](config-mtpeval.md) | [![返回到试点](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[返回到试点手册](mtp-pilot.md) |
|--|--|--|--|
||*你在这里！*  | | |


你当前处于设置阶段。 执行初始步骤以访问 Microsoft 365 安全中心，然后设置试用实验室或试验环境。

注册 Office 365 或 Azure Active Directory 订阅以生成可用于注册 Microsoft 365 E5 许可证的 *.onmicrosoft.com* 租户。 

>[!NOTE]
>如果已有 Office 365 或 Azure Active Directory 订阅，可以跳过 Office 365 E5 试用版或试点租户创建步骤。

在此阶段，将指导你：
- 创建 Office 365 E5 试用租户
- 启用 Microsoft 365 试用订阅


## <a name="create-an-office-365-e5-trial-tenant"></a>创建 Office 365 E5 试用租户
>[!NOTE]
>如果已有 Office 365 或 Azure Active Directory 订阅，可以跳过 Office 365 E5 试用租户创建步骤。

1. 转到 [Office 365 E5 产品门户，](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 然后选择 **免费试用**。

   ![图像of_Office 365 E5 免费试用版页面](../../media/mtp-eval-9.png)
  
2. 通过向个人或公司用户 (电子邮件地址完成) 。 单击 **"设置帐户"。**

   ![图像of_Office 365 E5 试用注册设置页面](../../media/mtp-eval-10.png)

3. 填写你的名字、姓氏、公司电话号码、公司名称、公司规模以及国家/地区。  

   ![要求of_Office、电话和公司详细信息的 365 E5 试用注册设置页面的图像](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > 你在此处设置的一个或多个国家/地区决定了 Office 365 将托管的数据中心区域。
  
4. 选择验证首选项：通过短信或呼叫。 单击 **"发送验证码"。** 

   ![要求of_Office首选项的 365 E5 试用注册设置页面的图像](../../media/mtp-eval-12.png)

5. 为租户设置自定义域名，然后单击"下一步 **"。**

   ![Image of_Office 365 E5 trial registration setup page where you can set up your custom domain name](../../media/mtp-eval-13.png)
 
6. 设置第一个标识，即租户的全局管理员。 填写名称和 **密码**。 单击 **"注册"。**

   ![Image of_Office 365 E5 trial registration setup page where you can set your business identity](../../media/mtp-eval-14.png)

7. 单击 **"转到设置"** 以完成 Office 365 E5 试用租户预配。

   ![Office 365 E5 试用注册设置页面提示单击"开始设置"按钮的图像](../../media/mtp-eval-15.png)

8. 将公司域连接到 Office 365 租户。 [可选]选择 **"连接你已拥有的域"，** 然后键入你的域名。 单击“**下一步**”。

   ![图像of_Office 365 E5 设置页面，应在其中个性化设置登录和电子邮件](../../media/mtp-eval-16.png)
 
9. 添加 TXT 或 MX 记录以验证域所有权。 将 TXT 或 MX 记录添加到域后，选择"验证 **"。**

   ![图像of_Office 365 E5 设置页面，应在其中添加 MX 记录的 TXT 以验证域](../../media/mtp-eval-17.png)
 
10. [可选]为租户创建多个用户帐户。 可以通过单击"下一步"跳过 **此步骤**。

    ![图像of_Office 365 E5 设置页面，可在其中添加更多用户](../../media/mtp-eval-18.png)
 
11. [可选]下载 Office 应用。 单击 **"下一** 步"跳过此步骤。 

    ![Image of_Office 365 E5 page where you can install your Office apps](../../media/mtp-eval-19.png)

12. [可选]迁移电子邮件。 同样，可以跳过此步骤。

    ![图像of_Office 365 E5 中可以设置是否迁移电子邮件](../../media/mtp-eval-20.png)
 
13. 选择"联机服务"。 选择 **"Exchange"，** 然后单击"下一 **步"。** 

    ![图像of_Office 365 E5，可在其中选择联机服务](../../media/mtp-eval-21.png)

14. 将 MX、CNAME 和 TXT 记录添加到你的域。 完成后，选择"验证 **"。**

    ![图像of_Office 365 E5，可以在此处添加 DNS 记录](../../media/mtp-eval-22.png)
 
15. 恭喜！你已完成 Office 365 租户的预配。

    ![图像of_Office 365 E5 设置完成确认页](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>启用 Microsoft 365 试用订阅

>[!NOTE]
>注册试用版可为你提供 25 个用户许可证，供一个月使用。 有关详细信息 [，请参阅试用或购买 M365](../../commerce/try-or-buy-microsoft-365.md#try-or-buy-a-microsoft-365-subscription-1) 订阅。

1. 在 [Microsoft 365 管理中心中](https://admin.microsoft.com/)，单击 **"计费**"，然后导航到"**购买服务"。**

2. 选择 **"Microsoft 365 E5"，** 然后单击"**开始免费试用"。** 

   ![图像of_Microsoft 365 E5 开始免费试用页面](../../media/mtp-eval-24.png)

3. 选择验证首选项：通过短信或呼叫。 决定后，输入电话号码，选择"为我发 **短信** "或" **呼叫** 我"，具体取决于你的选择。

   ![图像of_Microsoft 365 E5 开始免费试用页面，请求联系人详细信息发送代码以证明你并非机器人](../../media/mtp-eval-25.png)
 
4. 输入验证码，然后单击 **开始免费试用**。

   ![图像of_Microsoft 365 E5 开始免费试用页面，你可以填写系统发送的验证码以证明你并非机器人](../../media/mtp-eval-26.png)

5. 单击 **立即试用** 以确认 Microsoft 365 E5 试用版。

   ![Image of_Microsoft 365 E5 Start free trial page where you should clock the Try now button to start](../../media/mtp-eval-27.png)
 
6. 转到 **Microsoft 365 管理中心**  >  **用户**  >  **活动用户**。 选择用户帐户，选择管理 **产品许可证**，然后将许可证从 Office 365 E5 交换为 **Microsoft 365 E5。** 单击“**保存**”。

   ![图像of_Microsoft 365 管理中心页面，可在其中选择 Microsoft 365 E5 许可证](../../media/mtp-eval-28.png)
 
7. 再次选择全局管理员帐户，然后单击"**管理用户名"。**

   ![图像of_Microsoft 365 管理中心页面，可在其中选择"帐户"，然后选择"管理用户名"](../../media/mtp-eval-29.png)

8. [可选]根据你在之前 *onmicrosoft.com* 选择的不同，将域从一个域更改为你自己的域。 单击“**保存更改**”。

   ![图像of_Microsoft 365 管理中心页面，可在其中更改域首选项](../../media/mtp-eval-30.png)



## <a name="next-step"></a>后续步骤
|[阶段 3：配置&载入](config-mtpeval.md) | 为 Microsoft 365 Defender 试用实验室或试点环境配置每个 Microsoft 365 Defender 支柱，并载入终结点。
|:-------|:-----|