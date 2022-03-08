---
title: 成为 Microsoft Defender for Endpoint 合作伙伴
ms.reviewer: ''
description: 了解将解决方案与 Microsoft Defender for Endpoint 集成并成为合作伙伴的步骤和要求
keywords: 合作伙伴， 集成， 解决方案验证， 认证， 要求， 成员， 杂项， 应用程序门户
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: b063d8435817d7dd64c3febf6e3399f3876ef894
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319821"
---
# <a name="become-a-microsoft-defender-for-endpoint-partner"></a>成为 Microsoft Defender for Endpoint 合作伙伴

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


若要成为 Defender for Endpoint 解决方案合作伙伴，你需要遵循并完成以下步骤。

## <a name="step-1-subscribe-to-a-microsoft-defender-for-endpoint-license"></a>步骤 1：订阅 Microsoft Defender for Endpoint 许可证

想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。 订阅允许你将 Microsoft Defender for Endpoint 租户与最多三台设备一同使用，以开发与 Microsoft Defender for Endpoint 集成的解决方案。

## <a name="step-2-fulfill-the-solution-validation-and-certification-requirements"></a>步骤 2：满足解决方案验证和认证要求

技术合作伙伴认证其集成工作的最佳方法就是让联合客户批准建议的集成设计  (\(客户可以使用 Microsoft 365 Defender 合作伙伴应用程序页面中的推荐合作伙伴选项合作伙伴和 API > [](https://security.microsoft.com/interoperability/partnersapps)\) 合作伙伴应用程序，并针对 Microsoft Defender for Endpoint 团队进行测试和降级。

Microsoft Defender for Endpoint 团队审阅并批准集成后，我们将指导你成为 Microsoft 智能安全协会的合作伙伴。

## <a name="step-3-get-listed-in-the-microsoft-defender-for-endpoint-partner-application-portal"></a>步骤 3：在 Microsoft Defender for Endpoint 合作伙伴应用程序门户中列出

Microsoft Defender for Endpoint 支持使用嵌入在 Microsoft Defender for Endpoint 管理门户中的产品内[](partner-applications.md)合作伙伴页面发现和集成第三方应用程序。

若要将贵公司列为产品内合作伙伴页面中的合作伙伴，你需要提供以下信息：

1. SVG (方形) 。
2. 要显示的产品的名称。
3. 提供 15 字的产品说明。
4. 链接到客户完成集成或博客文章的登陆页面，该集成或博客文章将为客户提供足够的信息。 营销和工程团队应审阅任何新闻稿，包括 Microsoft Defender for Endpoint 产品名称。 等待至少 10 天，待审阅过程完成。
5. 如果使用多租户租户Azure AD，我们将需要Azure AD应用程序名称来跟踪应用程序的使用情况。
6. 在每个User-Agent Microsoft Defender for Endpoint 公共 API 集或安全中心 API 进行的每个 API 调用Graph字段。 这将用于统计目的、疑难解答和合作伙伴识别。 此外，此步骤是 Microsoft Intelligent Security Association (MISA) 的要求。

   请按以下步骤操作：

   - 将User-Agent HTTP 请求标头中的"请求字段"字段设置为以下格式。

     ```http
     MdePartner-{CompanyName}-{ProductName}/{Version}
     ```

     例如，User-Agent：

     ```http
     MdePartner-Contoso-ContosoCognito/1.0.0
     ```

   - 有关详细信息，请参阅 [RFC 2616 部分-14.43](https://tools.ietf.org/html/rfc2616#section-14.43)。

与 Microsoft Defender for Endpoint 的合作关系可帮助我们的相互客户进一步简化、集成和安排防御。 我们很高兴你选择成为 Microsoft Defender for Endpoint 合作伙伴，并同时防止和响应新式威胁，从而达到有效保护客户及其资产的共同目标。

## <a name="misa-nomination"></a>MISA 推荐 
MSSP (托管安全) 独立软件供应商 (ISV) 可指定给 Microsoft Intelligent Security Association (MISA) 。 有关详细信息，请参阅 [MISA 信息页面](https://www.microsoft.com/security/business/intelligent-security-association)。


## <a name="related-topics"></a>相关主题

- [技术合作伙伴商机](partner-integration.md)
