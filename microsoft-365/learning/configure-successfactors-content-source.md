---
title: 将 SAP SuccessFactors 配置为解决方案的内容Microsoft Viva Learning
ms.author: daisyfeller
author: daisyfell
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/27/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: 了解如何将 SAP SuccessFactors 配置为用于Microsoft Viva Learning。
ms.openlocfilehash: fafa0d8b610c3964617015ba3d4d1b9771c9e850
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747250"
---
# <a name="configure-sap-successfactors-as-a-content-source-for-microsoft-viva-learning"></a>将 SAP SuccessFactors 配置为解决方案的内容Microsoft Viva Learning

本文演示如何将 SAP SuccessFactors 配置为第三方内容源，以用于Microsoft Viva Learning。 首先，你需要在 SuccessFactors 门户中编辑系统配置，然后你需要完成 Microsoft 365 管理中心。

>[!NOTE]
>通过 Viva Learning的内容受 Microsoft 产品条款外的其他条款所规定。 SAP SuccessFactors 内容和任何关联的服务都受 SAP SuccessFactors 隐私和服务条款的约束。

## <a name="configure-in-your-successfactors-portal"></a>在 SuccessFactors 门户中配置

>[!NOTE]
>你需要在 SuccessFactors 中拥有管理员权限才能完成这些步骤。

1. 获取所需的工作流以编辑PARTNER_EXTRACT配置，您可以通过访问"系统管理配置""系统配置  >    >    >  "PARTNER_EXTRACT。

2. 使用 PGP 工具生成 PGP 键 (公钥、私钥、私钥密码) 首选大小。 生成 PGP 密钥时，可以选择 RSA 算法（推荐）。 对于您可以使用的 PGP 密钥生成工具之一，则使用 PGPG 工具。

3. 在配置配置中填写PARTNER_EXTRACT参数。 若要在 SuccessFactors 中编辑合作伙伴提取配置，你需要 SuccessFactors 中的 **"编辑系统配置** "工作流权限。

    - 所有作业状态的客户通知电子邮件
        - defaultJob.email=
    
    - Partner1
        - PartnerID 最大长度为 10 个字符。 这可以是你的 LMS 租户 ID。
    partners1.partnerID=
    
    - EncryptionKey 是 PGP 公共加密密钥，它是 BEGIN PGP 公钥块和 END PGP 公钥块之间的整个部分
        - partners1.encryptionKey=
    
    - KeyOwner 映射到公钥的用户 ID
        - partners1.keyOwner=
    
    - enabled 可以是"false"或"true"。 将设置为"true"以启用合作伙伴提取。
        - partners1.enabled=
    
    [![配置PARTNER_EXTRACT的图像。 ](../media/learning/sf-focus.png) ](../media/learning/sf-2.png#lightbox)

在 SuccessFactors 门户中完成这些步骤后，你需要完成 Microsoft 365 管理中心。

## <a name="configure-in-your-microsoft-365-admin-center"></a>在部署中Microsoft 365 管理中心

>[!NOTE]
>你需要拥有管理员权限才能Microsoft 365这些步骤。

1. 导航[到Microsoft 365 管理中心。](https://admin.microsoft.com)

2. 导航到 **设置**  >  **组织设置。** 搜索 *Viva Learning* 并启用选项中的 SAP SuccessFactors。

3. 填写配置详细信息：

    **显示名称**：为 SAP SuccessFactors 显示名称输入所需的名称。

    **SFTP 主机 URL：** 导航到 **LMS 管理应用程序**  >  **系统**  >  **管理配置**  >  **系统配置**  >  **连接器**。 获取属性的值 `connector.ftp.server` 。

    **用户名：** 按照 SFTP 主机 URL 的相同步骤操作。 获取属性的值 `connector.ftp.userID` 。

    **密码**：输入密码。 请与 LMS 应用程序所有者联系，获取检索密码的帮助。

    **文件夹路径**：导航到 **LMS Admin Application**  >  **System Administration**  >  **Configuration** System  >  **Configuration**  >  **PARTNER_EXTRACT**。 获取属性的值 `defaultFtp.path` 。

    **客户端的主机 URL：** 这是 BizX 域 URL。 可以从 BizX 登录 URL 获取此 URL。 例如，如果您的 BizX 登录 URL 为 `organization.successfactors.com/sf/start/#/login` ，则主机 URL 为 `organization.successfactors.com` 。

    **客户端的Learning目标 URL：** 可以从学习域模块 URL 获取此 URL。 例如，如果学习域 URL 为 `organization.scdemo.successfactors.com/learning/...` ，则Learning URL 为 `organization.scdemo.successfactors.com` 。

    **PGP 私钥**：用于解密的 PGP 私钥，它是 BEGIN PGP 私钥块和 END PGP 私钥块之间的整个部分。 你需要复制密钥，就像生成密钥一样;不要删除新行字符。

    **PGP 私钥密码**：你需要从提供 PGP 密钥的 IT 管理员或团队获取此值。

    **公司 ID：** 登录到 SuccessFactors 门户。 选择配置文件图标，然后选择"**显示版本设置"。** 你可以在此处查看你的公司 ID。

    ![已选择"显示版本"选项设置图像。](../media/learning/sf-3.png)
        
    ![版本设置窗格的图像。](../media/learning/sf-1.png)

4. 选择 **"保存**"激活"成功因素"Microsoft Viva Learning。 内容在 Viva Learning 中可用之前可能会Learning。

>[!Note]
> SuccessFactors 课程将在成功设置Learning 7 天内开始显示在 Viva 中。

>[!Note]
> 组织内的所有用户都将能够发现所有租户特定的课程，但他们只能访问和使用他们有权访问的课程。 计划在将来版本中发现特定于用户的内容。

>[!NOTE]
>租户元数据集中存储在我们的数据存储中，而不是存储在特定于地理位置的数据存储中。

>[!NOTE]
>目前，组织内的所有用户都可以发现所有租户特定的课程，但他们只能使用他们有权访问的课程。 已针对将来版本规划基于角色和权限的用户特定内容发现。
