---
title: Microsoft 云服务的合规性管理器符合数据保护和法规要求
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 429e686f-d8a6-455e-a2b6-3791d763f000
description: 了解如何使用 Microsoft 服务信任门户中的合规性管理器来满足数据保护和管理法规要求。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 071da43244f2afae3df29ec84ae98713ed0dc2d7
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815593"
---
# <a name="microsoft-compliance-manager-classic"></a>Microsoft 合规性管理器（经典）

> [!NOTE]
> 此文档介绍此产品的先前版本。 强烈建议用户不要使用此版本的合规性管理器，而应鼓励用户使用新的 [Microsoft 合规性分数](compliance-score.md)。

 *由世纪互联运营的 Office 365、Office 365 Germany、Office 365 U.S. Government Community High (GCC High) 或 Office 365 Department of Defense 不提供合规性管理器。*
  
合规性管理器是 Microsoft [服务信任门户](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-service-trust-portal)中基于工作流的风险评估工具，可跟踪、分配和验证组织的合规性活动，这些活动与 Microsoft 专业服务和 Microsoft 云服务（如 Microsoft Office 365、Microsoft Dynamics 365 和 Microsoft Azure）相关。 

合规性管理器：
  
- 结合使用在根据各种标准（例如，ISO 27001、ISO 27018 和 NIST）对 Microsoft 云服务执行的各种第三方审计过程中 Microsoft 提供给审计和监管人员的详细信息，，以及 Microsoft 为遵守法规（如 HIPAA 和欧盟一般数据保护条例 (GDPR)）在内部汇编的信息，与你自己对组织遵守这些标准和法规情况的自我评估。
    
- 可便于分配、跟踪和记录合规性活动以及与评估相关的活动，这有助于组织跨越团队障碍，从而实现组织的合规性目标。
    
- 提供合规性分数，这有助于跟踪进度并确定审核控制措施的优先顺序，从而降低组织的风险暴露程度。
    
- 提供安全存储库，用于上传和管理与合规性活动相关的证据及其他项目。
    
- 生成丰富详细的 Microsoft Excel 报告，记录 Microsoft 和组织执行的合规性活动，以提供给审计、监管人员和其他合规性利益干系人。

有关合规性管理器的简短演示，请参阅此[合规性管理器](https://www.youtube.com/watch?v=r1vs8NdSXKQ)视频。

    
> [!IMPORTANT]
> Compliance Manager is a dashboard that provides a summary of your data protection and compliance stature and recommendations to improve data protection and compliance. The Customer Actions provided in Compliance Manager are recommendations; it is up to each organization to evaluate the effectiveness of these recommendations in their respective regulatory environment prior to implementation. Recommendations found in Compliance Manager should not be interpreted as a guarantee of compliance.

    
## <a name="what-is-compliance-manager"></a>什么是合规性管理器？

Compliance Manager is a workflow-based risk assessment tool designed to help you manage regulatory compliance within the shared responsibility model of the cloud. Compliance Manager provides you with a dashboard view of standards and regulations and assessments that contain Microsoft's control implementation details and test results and customer control implementation guidance and tracking for your organization to enter. Compliance Manager provides certification assessment control definitions, guidance on implementation and testing of controls, risk-weighted scoring of controls, role-based access management, and an in-place control action assignment workflow to track control implementation, testing status and evidence management. Compliance Manager optimizes compliance workload by enabling customers to logically group assessments together and apply assessment control testing to identical or related controls, reducing the duplication of effort that might otherwise be required to satisfy identical control requirements across different certifications.

## <a name="assessments-in-compliance-manager"></a>合规性管理器中的评估

The core component of Compliance Manager is called an *Assessment*. An Assessment is an assessment of a Microsoft service against a certification standard or data protection regulation (such as ISO 27001:2013, and the GDPR). Assessments help you to discern your organization's data protection and compliance posture against the selected industry standard for the selected Microsoft cloud service. Assessments are completed by the implementation of the controls that map to the certification standard being assessed. 
  
评估的结构依据为 Microsoft 和组织共同承担的责任，双方负责评估云中的安全性和合规性风险，并实现合规性标准、数据保护标准、法规或法律规定的数据保护安全措施。
  
评估由多个组件组成，它们分别是：
  
- **范围内服务** - 每项评估都适用于一组特定的 Microsoft 服务，这些服务在“范围内云服务”部分中列出。 
    
- **Microsoft-Managed Controls** - For each cloud service, Microsoft implements and manages a set of  *controls*  as part of Microsoft's compliance with various standards and regulations. These controls are organized into  *control families*  that align with the structure from the corresponding certification or regulation that the Assessment is aligned to. For each Microsoft-managed control, Compliance Manager provides details about how Microsoft implemented the control, along with how and when that implementation was tested and validated by an independent third-party auditor. 
    
    下面的示例展示了三项 Microsoft 管理的控制措施，均来自“Office 365 + GDPR”评估中的“**安全**”控制措施系列。 

    ![合规性管理器中 Microsoft 管理的控制措施的详细信息](../media/d1351212-1ebf-424e-91b8-930c2b2edef1.png)
  
  a. Specifies the following information from the certification or regulation that maps to the Microsoft-managed control.

  - **控制措施 ID** - 控制措施映射到的认证或法规中的节或条款编号。
    
  - **标题** - 相应认证或法规的标题。
    
  - **条款 ID** - 仅当为“GDPR”评估时，才会添加此字段，因为它指定了相应 GDPR 条款编号。
    
  - **说明** - 映射到选定 Microsoft 管理的控制措施的标准或法规文本。

  b. The Compliance Score for the control, which indicates the level of risk (due to non-compliance or control failure) associated with each Microsoft-managed control. See [Understanding the Compliance Score](#understanding-the-compliance-score) for more information. Note that Compliance Scores are rated from 1 to 10 and are color-coded. Yellow indicates low risk controls, orange indicates medium-risk controls, and red indicated high-risk controls. 
    
  c. Information about the implementation status of a control, the date the control was tested, who performed the test, and the test result.
    
  d. For each control, you can click **More** to see additional information, including details about Microsoft's implementation of the control and details about how the control was tested and validated by an independent third-party auditor. 
    
- **Customer-Managed Controls** - This is the collection of controls that are managed by your organization. Your organization is responsible for implementing these controls as part of your compliance process for a given standard or regulation. Customer-managed controls are also organized into control families for the corresponding certification or regulation. Use the customer-managed controls to implement the recommended actions suggested by Microsoft as part of your compliance activities. Your organization can use the prescriptive guidance and recommended Customer Actions in each customer-managed control to manage the implementation and assessment process for that control.
    
    Customer-managed controls in Assessments also have built-in workflow management functionality that you can use to manage and track your organization's progress towards completing the Assessment. For example, a Compliance Officer in your organization can assign an Action Item to an IT admin who has the responsibility and necessary permissions to perform the actions that are recommended for the control. When that work is complete, the IT admin can upload evidence of their implementation tasks (for example, screenshots of configuration or policy settings) and then assign the Action Item back to the Compliance Officer to evaluate the collected evidence, test the implementation of the control, and record the implementation date and test results in Compliance Manager. For more information, see the [Managing the assessment process](#managing-the-assessment-process) section in the article. 
  
## <a name="permissions-and-role-based-access-control"></a>权限和基于角色的访问控制

合规性管理器使用基于角色的访问控制权限模型。 只有分配了用户角色的用户可访问合规性管理器，并且每位用户允许的操作受到角色类型的限制。
  
请注意，“**来宾访问**”这一默认角色已不复存在。 必须为每位用户分配一个角色，使其可访问合规性管理器并在其中工作。
  
The following table describes each Compliance Manager permission and what it allows the user do. The table also indicates the role that each permission is assigned to.
  
||**合规性管理器读者**|**合规性管理器参与者**|**合规性管理器评估员**|**合规性管理器管理员**|**门户管理员**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**读取数据** - 用户可读取但不能编辑数据。  <br/> |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>|
|**编辑数据** - 用户可编辑除“测试结果”和“测试日期”字段以外的其他所有字段。  <br/> ||![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>|![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|**编辑测试结果** - 用户可编辑“测试结果”和“测试日期”字段。  <br/> ||<br/> |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|**管理评估** - 用户可创建、存档和删除评估。  <br/> |||<br/> |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|**Manage users** - Users can add other users in their organization to the Reader, Contributor, Assessor, and Administrator roles. Only those users with the Global Administrator role in your organization can add or remove users from the Portal Admin role.  <br/> ||||<br/> |![复选标记](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
   
## <a name="understanding-the-compliance-score"></a>了解合规性分数

在仪表板上，合规性管理器会在磁贴右上角显示 Office 365 评估的总分数。 这是评估的整体合规性分数，也是评估中标记为“已实施且已测试”的每项控件评估所得到的累计分数。 添加评估时，你将看到合规性分数正在完成中，因为已应用已由 Microsoft 实施且已经过独立第三方测试的 Microsoft 托管控件的得分。
  
![合规性管理器仪表板 - 总合规性分数](../media/756091aa-1afd-4aff-93ab-c6f6824f2add.png)
  
剩余分数来自于成功的客户控制措施评估，也来自于实现和测试客户管理的控制措施，其中每项控制措施都有特定的分值累积到总合规性分数中。 
  
每项评估都会显示基于风险的合规性分数，帮助评估与“评估”中每个控件（包括 Microsoft 托管控件和客户托管控件）相关联的风险（因不合规或控件故障所致）级别。 每个客户托管控件都分配了介于 1 和 10 之间的点数（称为*严重度排名）；控件发生故障的风险因子越高，控件点数越高；风险越低，点数越低。 
  
例如，下面所示的“用户访问管理”评估控制措施的严重性风险级别非常高，分配到的值为 10。
  
![合规性管理器 - 高严重程度的评估控制措施 - 10 分](../media/174ecb2c-aaed-436e-9950-74da7dadf5db.png)
  
 相比之下，下面的“信息备份”评估控制措施的严重性风险级别较低，分配到的值为 3。 
  
![合规性管理器 - 低严重程度的评估控制措施 - 3 分](../media/11749f20-5f22-40c2-bbc1-eaccbf29e2ae.png)
  
The Compliance Manager assigns a default severity ranking to each control. Risk rankings are calculated based on the following criteria:
  
- 控件是防止事件发生（排名最高）、检测已发生的事件，还是更正事件造成的影响（排名最低）。 在严重度排名方面，向防止威胁的强制性控件分配最高分数；向检测性或纠正性控件（无论是强制性的还是自主性的）分配最低分数。
    
- 控制措施（在实现后）是用户无法规避的必需措施（例如，用户必须重置密码，并符合密码长度和字符数要求），还是用户可规避的随意措施（例如，要求用户在计算机无人使用时锁定屏幕的业务规则）。
    
- Controls related to risks to data confidentiality, integrity, and availability, whether these risks come from internal or external threats, and whether the threat is malicious or accidental. For example, controls that would help prevent an external attacker from breaching that network and gaining access to personally identifiable information would be assigned more points than a control related to preventing an employee from accidentally mis-configuring a network router setting that results in a network outage).
    
- 与法律和外部驱动因素相关的风险，如每项控制措施对应的合同、法规和公开承诺。
    
The displayed Compliance Score values for the control are applied  *in their entirety*  to the Total Compliance Score on a pass/fail basis--either the control is implemented and passes the subsequent assessment test or it does not; there is no partial credit for a partial implementation. Only when the control has its **Implementation Status** set to **Implemented** or **Alternative Implementation** and the **Test Result** is set to **Passed** are the assigned points added to the Total Compliance Score. 
  
最重要的是，合规性分数可通过在出现与控件相关的故障时指出存在较高潜在风险的控件，帮助用户确定要优先实施的控件。 除了基于风险的优先级排序外，如果评估控件与其他控件相关（在同一评估中或在同一评估组中的其他评估中），那么基于控件测试结果的同步，成功完成单一控件可显著降低相关工作量。
  
例如，在下图中，“Office 365 - GDPR”评估目前已评估 46%，111 项控制措施评估中已完成 51 项，总合规性分数为 289 分（满分可能为 600 分）。
  
![合规性管理器 - 评估摘要](../media/595eedae-e3e0-4d1f-8cf5-7c1c9f4fd1e8.png)
  
在评估中，GDPR 控件 7.5.5 与其他 5 个控件（7.4.1、7.4.3、7.4.4、7.4.8 和 7.4.9）相关，每个控件的风险等级均达到中度或重度，分数为 6 或 8。 使用评估筛选器，选择所有这些控件，使它们显示在评估视图中，可在下方看到它们当前都没有被评估。 
  
![合规性管理器 - 评估视图 - 筛选控制措施，未评估任何控制措施](../media/b2ae7120-2d7a-4247-b0a9-f5f65433395f.jpg) As those 6 controls are related, the completion of any one them will result in a synchronization of those test results across the related controls within this assessment (just as it will for any related controls in an assessment that is in the same assessment grouping). Upon completion of the implementation and testing of GDPR control 7.5.5, the control detail area refreshes to show that all 6 controls have been assessed, with a corresponding increase in the number of assessed controls to 57 and 51% assessed, and a change in total Compliance Score of +40. 
  
![合规性管理器 - 评估视图 - 已同步控制措施结果](../media/e9da2b30-053a-4d40-ace9-ae1b39cdaf66.jpg)
  
若要更改相关控制措施的“实现状态”，并且这会影响其他相关控制措施，就会看到下面的确认更新对话框。
  
![合规性管理器 - 评估视图 - 相关控制措施的更新确认对话框](../media/8be25bd2-1aee-455f-8aa4-10b1184ca4c3.png)
  
> [!NOTE]
> Currently, only Assessments for Office 365 cloud services include a Compliance Score. Assessments for Azure and Dynamics show an assessment status. 

## <a name="compliance-score-methodology"></a>合规性分数计算方法

合规性分数（如 Microsoft 安全功能分数）类似于其他基于行为的评分系统；组织可通过执行与数据保护、隐私和安全性相关的活动，增加合规性分数。
  
> [!NOTE]
> The Compliance Score does not express an absolute measure of organizational compliance with any particular standard or regulation. It expresses the extent to which you have adopted controls which can reduce the risks to personal data and individual privacy. No service can guarantee that you are compliant with a standard or regulation, and the Compliance Score should not be interpreted as a guarantee in any way. 
  
Assessments in Compliance Manager are based on the shared responsibility model for cloud computing. In the shared responsibility model, Microsoft and each customer share responsibility for the protection of the customer's data when that data is stored in our cloud.
  
如下方的 Office 365 GDPR 评估所示，Microsoft 和客户各自负责执行一些操作，以便满足所评估标准或法规要求。 为了解释并理解 各种标准和法规所需的操作，合规性管理器将所有标准和法规都视为控制框架。 如此，Microsoft 和客户为每项评估所执行的操作将涉及各种控件的实施和验证。
  
![合规性管理器 -“GDPR”评估](../media/123f8126-85b8-4baa-9c4e-c6295cf4a5ca.png)
  
下面是典型行动的基本工作流：
  
1. The Compliance, Risk, Privacy, and/or Data Protection Officer of an organization assigns the task to someone in the organization to implement a control. That person could be:

    - 业务策略所有者
    
    - IT 实现者
    
    - 组织中另一个负责执行任务的人员
    
2. That individual performs the tasks necessary to implement the control, uploads evidence of implementation into Compliance Manager, and marks the control(s) tied to the Action as implemented. Once these tasks are completed, they assign the Action to an Assessor for validation. Assessors can be:
    
    - 在组织内部验证控制措施的内部评估员
    
    - 检查、验证和认证合规性的外部评估员，如审核 Microsoft 云服务的第三方独立组织
    
3. 评估员验证控制措施并检查证据，然后将一项或多项控制措施标记为“已评估”，并记录评估结果（例如，“通过”）。
    
当与评估相关联的所有控制措施都已获评估后，便认为评估已完成。
  
Every Assessment in Compliance Manager comes pre-loaded with information that provides details about the Actions taken by Microsoft to satisfy the requirements of the controls for which Microsoft is responsible. This information includes details about how Microsoft has implemented each control and how and when Microsoft's implementation was assessed and verified by a third-party auditor. For this reason, the Microsoft Managed Controls for each Assessment are marked as Assessed, and the Compliance Score for the Assessment reflects this.
  
Each Assessment includes a total Compliance Score based on the shared responsibility model. Microsoft's implementation and testing of controls for Office 365 contributes a portion of the total possible points associated with a GDPR assessment. As the customer implements and tests each of the customer Actions, the Compliance Score for the Assessment will increase by the value assigned to the control. 
  
 ### <a name="risk-based-scoring-methodology"></a>基于风险的评分方法
  
Compliance Manager uses a risk-based scoring methodology with a scale from 1-10 that assigns a higher value to controls that represent a higher risk in the event the control fails or is non-compliant. The scoring system used by Compliance Score is based on several key factors, such as:
  
- 控制措施的本质
    
- 以威胁种类为依据的控制措施风险级别
    
- 控制措施的外部驱动因素
    
![合规性管理器 - 合规性分数计算方法](../media/e48764c4-828e-44b0-8636-fb3c352f2bac.png)
  
 ### <a name="essence-of-the-control"></a>控制措施的本质
  
控制措施的本质依据的是，控制措施是必需还是随意控制措施，以及控制措施是预防型、检测型还是纠正型。
  
 ### <a name="mandatory-or-discretionary"></a>必需或随意
  
 *Mandatory controls*  are controls that cannot be bypassed either intentionally or accidentally. An example of a common mandatory control is a centrally-managed password policy that sets requirements for password length, complexity, and expiration. Users must comply with these requirements in order to access the system. 
  
 *Discretionary controls*  rely upon users to understand policy and act accordingly. For example, a policy requiring users to lock their computer when they leave it is a discretionary control because it relies on the user. 
  
 ### <a name="preventative-detective-or-corrective"></a>预防型、检测型或纠正型
  
 *Preventative controls*  are those that prevent specific risks. For example, protecting information at rest using encryption is a preventative control against attacks, breaches, etc. Separation of duties is a preventative control to manage conflict of interest and to guard against fraud. 
  
 *Detective controls*  are those that actively monitor systems to identify irregular conditions or behaviors that represent risk or that can be used to detect intrusions or determine if a breach has occurred. System access auditing and privileged administrative actions auditing are types of detective monitoring controls; regulatory compliance audits are a type of detective control used to find process issues. 
  
 *Corrective controls*  are those that try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage, if possible. Privacy incident response is a corrective control to limit damage and restore systems to an operational state after a breach. 
  
我们根据这些因素评估每项控制措施，从而确定控制措施的本质，并向它分配与之所代表的风险相关的分数值。
  
 **威胁**
  
||||
|:-----|:-----|:-----|
||**必需** <br/> |**随意** <br/> |
|**预防型** <br/> |高风险  <br/> |中等风险  <br/> |
|**检测型** <br/> |中等风险  <br/> |低风险  <br/> |
|**纠正型** <br/> |中等风险  <br/> |低风险  <br/> |
   
威胁是指任何对公认的基本安全标准构成风险的要素。这一标准就是所谓数据 CIA 三概念，分别为机密性、完整性和可用性：
  
- 机密性是指信息只能被受信任的授权方读取和理解。
    
- 完整性是指信息尚未被未授权方修改或销毁。
    
- 可用性是指信息可供轻松访问，并能获取优质服务。
    
A failure of any of these characteristics is considered a compromise of the system as a whole. Threats can come from both internal and external sources, and an actor's intent can be accidental or malicious. These factors are estimated in a threat matrix that assigns threat levels of either High, Moderate, or Low to each combination of scenarios.

||**内部**<br/>||**外部**<br/>||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||*恶意*<br/>|*偶发*<br/>|*恶意*<br/>|*偶发*<br/>|||
|**机密性**<br/>|（高、中等或低）  <br/> |（高、中等或低）  <br/> |（高、中等或低）  <br/> |（高、中等或低）|
|**完整性**<br/>|（高、中等或低）  <br/> |（高、中等或低）  <br/> |（高、中等或低）  <br/> |（高、中等或低）|
|**可用性**<br/>|（高、中等或低）  <br/> |（高、中等或低）  <br/> |（高、中等或低）  <br/> |（高、中等或低）|
   
 **外部驱动因素**
  
|**合同**|**法规**|**公开承诺**|
|:-----|:-----|:-----|
|（高、中等或低）  <br/> |（高、中等或低）  <br/> |（高、中等或低）  <br/> |
   
适用法规、合同和公开承诺等外部因素可能会影响旨在保护数据和防止数据泄露的控制措施，其中每个因素都分配有风险值，或分配有高、中等、低风险级别。
  
计算风险权重时也考虑到，在这些高、中等、低风险级别对应的风险值，在“CIA/威胁和法律/外部驱动因素”中介绍的 15 种可能风险方案内估计会出现多少次风险，即在给定值出现风险的可能性和次数，计算控制措施的严重程度时也会将这一点考虑在内。
  
根据控制措施的严重程度，控制措施分配有合规性分数值（即介于 1（低）和 10（高）之间的数字），分为以下几种风险类别：
  
|**风险级别**|**控制措施分数值**|
|:-----|:-----|
|低  <br/> |1-3  <br/> |
|中等  <br/> |6  <br/> |
|高  <br/> |8  <br/> |
|严重  <br/> |10  <br/> |
   
通过按合规性分数值从高到低的顺序确定评估控制措施的优先级，组织可以最高风险项为重点，并相应地获得更高正反馈，即完成的每项控制措施评估累积到评估总合规性分数中的分数更多。
  
### <a name="summary-of-scoring-methodology"></a>评分方法总结
  
The Compliance Score is a core component of the way that Compliance Manager helps organizations understand and manage their compliance. The Compliance Score for an assessment is an expression of the company's compliance with a given standard or regulation as a number, where the higher the score (up to the maximum number of points allocated for the Assessment), the better the company's compliance posture. Understanding the compliance scoring methodology in which assessment controls are assigned risk severity values between 1- 10 (low to high), and how completed control assessments add to the total compliance score is crucial to organizations for prioritizing their actions.

## <a name="grouping-assessments"></a>对评估进行分组

创建新的评估时，系统会提示创建用于将评估分配到其中的组，或将评估分配到现有组。 借助组，可以在具有相同或相关客户托管控件的评估之间逻辑地整理评估，并共享常见信息和工作流任务。
  
For example, you could group Assessments by year or teams, departments, or agencies within your organization or group them by year. Here are some examples of groups and the Assessments they might contain.
  
- GDPR 评估 - 2018 年
    
  - Office 365 + GDPR
    
  - Azure + GDPR
    
  - Dynamics + GDPR
    
- Azure 评估 - 2018 年
    
  - Azure + GDPR
    
  - Azure + ISO 27001:2013
    
  - Azure + ISO 27018:2014
    
- “数据安全和隐私”评估
    
  - Office 365 + ISO 27001:2013
    
  - Office 365 + ISO 27018:2014
    
  - Azure + ISO 27001:2013
    
  - Azure + ISO 27018:2014
    
> [!TIP]
> 建议在添加新评估前，先确定组织的分组策略。 
  
下面介绍了评估分组要求：
  
- 组名（亦称为“*组 ID”）在组织中必须是唯一的。 
    
- Groups can contain Assessments for the same certification/regulation, but each group can only contain one Assessment for a specific cloud service/certification pair. For example, a group can't contain two Assessments for Office 365 and GDPR. Similarly, a group can contain multiple Assessments for the same cloud service as long as the corresponding certification/regulation for each one is different.
    
将评估添加到评估分组中后，就无法更改分组。 可重命名评估组，这会更改与该组相关的所有评估的评估分组名称。 可以创建评估和新评估组，并从现有评估中复制信息，这会在另一个评估组中创建该评估的有效副本。 对评估进行存档会破坏评估与评估组之间的关系。 对其他相关评估的后续更新将不再反映在已存档的评估中。
  
如前所述，使用组的关键优势之一是，如果同一组中的两个不同评估共用相同的客户管理的控制措施（因此每项控制措施的客户行动都是一样的），那么一项评估中控制措施的完成实现详情、测试信息和状态就会同步到这一组中其他任何评估内的相同控制措施。 换言之，如果同一组中的评估共用相同的控制措施，那么只需管理一项评估中控制措施的评估流程。 这项控制措施的结果会自动同步到其他评估。 例如，ISO 27001 和 ISO 27018 都有与密码策略相关的控制措施。 如果一项评估中控制措施的“测试状态”设置为“通过”，那么另一项评估中的控制措施也会进行更新（并标记为“通过”），只要两项评估都位于同一个评估组中即可。
  
例如，假设有两项相关的评估控制措施，分别是“Office 365 — GDPR”评估中的控制措施 6.10.1.2 和“Office 365 — NIST 800-53”评估中的控制措施 SC-13，均与公用网络上的数据加密有关。 这两项相关的评估控制措施位于默认组中的两个不同评估内。 最初，这两项评估都没有完成任何客户控制措施评估，如显示这两项评估的合规性管理器仪表板所示。
  
![合规性管理器仪表板 — 已分组评估 — 前](../media/dc0126a3-415c-4fbe-a020-1806dd1caebd.png)
  
单击“**Office 365 — GDPR**”评估，并使用筛选器控件筛选出 GDPR 控制措施 6.10.1.2 后，就会发现 NIST 800-53 控制措施 SC-13 被列为相关控制措施。
  
![合规性管理器评估 —共用控制措施](../media/aafb106e-0abc-4918-8038-de11cf326dfe.png)
  
 下图说明 GDPR 控制措施 6.10.1.2 的实现和测试已完成。 
  
![合规性管理器评估控制措施 GDPR 6.10.1.2 — 已通过](../media/ee9e83b6-9d51-4b3b-85eb-96bec0fef2e1.png)
  
通过转到已分组评估中的相关控制措施，我们发现 NIST 800-53 SC-13 也已在相同的日期和时间标记为完成，无需执行其他任何实现或测试工作。
  
![合规性管理器评估 — NIST 800-53 SC(13) 已完成](../media/b5933592-db5a-4fdd-9be2-bba777646a88.png)
  
返回到仪表板，可以看到每项评估都完成了一项控制措施评估，并且每项评估的总合规性分数增加了 8 分（即共用控制措施分配到的合规性分数值）。
  
![合规性管理器仪表板 — 已分组评估的进度同步](../media/727f1203-b98d-4a03-a7af-e9236f4c5534.png)

## <a name="administrative-functions"></a>管理功能

有一些特定的管理功能只对租户管理员帐户可用，并且只有在以全局管理员身份登录时才可见。
  
> [!NOTE]
> The Access to Restricted Documents permission in the drop-down list will allow administrators to give users access to restricted documents that Microsoft shares on the Service Trust Portal. The Restricted Documents feature isn't available, but is coming soon. 
  
### <a name="assigning-compliance-manager-roles-to-users"></a>向用户分配合规性管理器角色

Each Compliance Manager role has slightly different permissions. You can view the permissions assigned to each role, see which users are in which roles, and add or remove users from that role through the Service Trust Portal by selecting the **Admin** menu item, and then choosing **Settings**. 
  
![STP“管理员”菜单 — 已选择“设置”](../media/65a82b1b-d462-452f-988b-7e4263bd638e.png)
  
若要在合规性管理器角色中添加或删除用户，请执行以下操作。
  
1. 转到 [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com)。
    
2. 使用 Azure Active Directory 全局管理员帐户登录。
    
3. 单击服务信任门户顶部菜单栏中的“管理员”****，再选择“设置”****。 
    
4. 在“选择角色”**** 下拉列表中，单击要管理的角色。 
    
5. “**选择角色**”页上会列出已添加到每个角色的用户。 
    
6. To add users to this role, click **Add**. In the **Add Users** dialog, click the user field. You can scroll through the list of available users or begin typing the user name to filter the list based on your search term. Click the user to add that account to the **Add Users** list to be provisioned with that role. If you would like to add multiple users concurrently, begin typing a user name to filter the list, and then click the user to add to the list. Click **Save** to provision the selected role to these users. 
    
    ![合规性管理器 — 预配角色 — 添加用户](../media/2f386f82-2bf8-4e95-ab41-1724b752b508.png)
  
7. 若要从此角色中删除用户，请选择一个或多个用户，然后单击“**删除**”。 
    
    ![合规性管理器 — 预配角色 — 删除用户](../media/17004def-604f-471d-a54d-f678fcc01c1e.png)
 
## <a name="user-privacy-settings"></a>用户隐私设置

Certain regulations require that an organization must be able to delete user history data. To enable this, Compliance Manager provides the **User Privacy Settings** functions, that allow administrators to: 
  
- [搜索用户](#search-for-a-user)

- [导出帐户数据历史记录报告](#export-a-report-of-account-data-history)

- [重新分配行动项](#reassign-action-items)

- [删除用户数据历史记录](#delete-user-data-history)
    
![合规性管理器管理员 —“用户隐私设置”功能](../media/067d6c6a-712a-4dc2-9b99-de2fa4417dc3.png)
  
### <a name="search-for-a-user"></a>搜索用户

若要搜索用户帐户，请执行以下操作：
  
1. 键入别名（@ 符号左侧的信息）并通过单击右侧的域后缀列表选择域名，从而输入用户电子邮件地址。 如果此租户注册了多个域，可以双击电子邮件地址域名后缀以确保它的正确性。
    
2. 正确输入用户名后，单击“搜索”****。 
    
3. If the user account is not found, the error message 'User not found' will be displayed on the page. Check the user's email address information, make corrections as necessary and click **Search** to try again. 
    
4. 如果找到了用户帐户，按钮文本会从“**搜索**”更改为“**清除**”，这表明返回的用户帐户是下方显示的附加功能的操作上下文，运行这些功能会应用于此用户帐户。 
    
5. 若要清除搜索结果并搜索其他用户，请单击“清除”****。 
    
### <a name="export-a-report-of-account-data-history"></a>导出帐户数据历史记录报告

识别用户帐户后，可能要生成与此帐户链接的依赖项报告。 通过此信息，可以重新分配未完成的操作项目，或确保可访问之前上传的证据。 
  
 若要生成并导出报告，请执行以下操作：
  
1. 单击“**导出**”，生成并下载报告，报告包含当前分配给所返回用户帐户的合规性管理器控制操作项目和该用户上传的文档列表。 如果没有分配的操作或没有上传的文档，则会出现一条错误消息：“没有此用户的数据”。 
    
2. 报告是在活动浏览器窗口的后台进行下载（如果没有看到下载弹出窗口，建议查看浏览器下载历史记录）。
    
3. 打开文档即可查看报告数据。
    
> [!NOTE]
> This is not a historical report that retains and displays state changes to action item assignment history. The generated report is a snapshot of the control action items assigned at the time that the report is run (date and time stamp written into the report). For instance, any subsequent reassignment of action items will result in different snapshot report data if this report is generated again for the same user. 
  
### <a name="reassign-action-items"></a>重新分配行动项

This function enables an organization to remove any active or outstanding dependencies on the user account by reassigning all action item ownership (which includes both active and completed action items) from the returned user account to a new user selected below. This action does not change document upload history for the returned user account. 
  
 若要向其他用户重新分配行动项，请执行以下操作：
  
1. 单击输入框，浏览并选择组织内的另一名用户，向其分配已返回用户的行动项。
    
2. 选择“替换”****，将所有控制措施行动项从已返回用户重新分配给新选择的用户。 
    
3. 此时会出现一个确认对话框：“这会将所有控制操作项目从当前用户重新分配至所选用户。 此操作无法撤消。 你确定要继续吗?”
    
4. 若要继续，请单击“确定”****；否则，请单击“取消”****。 
    
> [!NOTE]
> All action items (both active and completed) will be assigned to the newly selected user. However, this action does not affect the document upload history; any documents uploaded by the previously assigned user will still show the date/time and name of the previously assigned user. 
  
Changing the document upload history to remove the previously assigned user will have to be done as a manual process. In that case, the administrator will need to:
  
1. 打开以前下载的“导出”报告。
  
2. 标识并转到相应控制措施行动项。
  
3. 单击“管理文档”****，以转到此控制措施的证据存储库。 
  
4. 下载文档。
  
5. 从证据存储库中删除此文档。
  
6. Re-upload the document. The document will now have a new upload date, time and Uploaded By username. 
  
### <a name="delete-user-data-history"></a>删除用户数据历史记录

This sets control action items to 'unassigned' for all action items assigned to the returned user. This also sets uploaded by value to 'user removed' for any documents uploaded by the returned user
  
 若要删除用户帐户行动项和文档上传历史记录，请执行以下操作：
  
1. 单击“删除”****。 

    A confirmation dialog will be displayed, stating "This will remove all control action item assignments and the document upload history for the selected user. This action cannot be undone. Are you sure you want to continue?"
    
3. 若要继续，请单击“确定”****；否则，请单击“取消”****。 
  
## <a name="using-compliance-manager"></a>使用合规性管理器

合规性管理器提供了各种工具，可便于分配、跟踪和记录合规性活动以及与评估相关的活动，这有助于组织跨越团队障碍，从而实现组织的合规性目标。
  
![合规性管理器仪表板 — 顶部菜单 — 更新后的“管理员”菜单](../media/134d7577-cd70-4124-bcfd-d3feb248952b.png)

## <a name="accessing-compliance-manager"></a>访问合规性管理器

You access Compliance Manager from the Service Trust Portal. Anyone with a Microsoft account or Azure Active Directory organizational account can access Compliance Manager.
  
![合规性管理器 — 从 STP 菜单访问合规性管理器](../media/14be4cac-2380-49bc-9b36-210da8cafdfa.png)
  
1. 转到 [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/)。
    
2. 使用 Azure Active Directory (Azure AD) 用户帐户登录。
    
3. 在服务信任门户中，单击“合规性管理器”****。 
    
4. When the Non-Disclosure Agreement is displayed, read it, and then click **Agree** to continue. You'll only have to do this once, and then the Compliance Manager dashboard is displayed. 

    为了帮助你开始使用，我们已默认添加以下评估：
    
    ![合规性管理器中的默认评估](../media/8c59b45a-706a-4362-a7ba-2cb782931bf7.png)
    
5. 单击 ![合规性管理器中的“帮助”图标](../media/c1b3092f-6ac7-43ab-b1c4-63a54598450c.png)“帮助”****，以观看合规性管理器的快速导览。 
  
## <a name="viewing-action-items"></a>查看行动项

合规性管理器为所有已分配的控件评估操作项目提供方便的视图，让用户能够快速轻松地操作这些项目。 可查看所有操作项目，或单击与该评估相关的选项卡来选择与特定认证相对应的操作项目。 例如，在下方图片中，已选中“GDPR”选项卡，显示了与 GDPR 评估相关的控件。
  
![合规性管理器 — “行动项”列表中有多个选项卡，已选择“GDPR”选项卡](../media/ba960f5c-becb-4d95-a000-d08ec77b7b46.png)
  
若要查看行动项，请执行以下操作：
  
1. 转到合规性管理器仪表板
    
2. 单击“行动项”**** 链接，此时页面刷新为显示已分配给你的行动项。 
    
    By default, all action items are shown. If you have action items across multiple certifications, the names of the certifications will be listed in tabs across the top of the assessment control. To see the action items for a specific certification, click that tab.

## <a name="adding-an-assessment"></a>添加评估

若要将评估添加到合规性管理器，请执行以下操作：
  
1. 在合规性管理器仪表板中，单击 ![“添加”图标](../media/ITPro-EAC-AddIcon.gif)“添加评估”****。 
    
2. In the **Add an Assessment** window, you can create a new group to add the Assessment to or you can add it to an existing group (the built-in group is named "Initial Group".) Depending on the option you choose, either type the name of a new group or select an existing group from the drop-down list. For more information, see [Grouping Assessments](#grouping-assessments).
    
    如果创建了组，还可以选择将现有组的信息复制到新的评估中。 这意味着，添加到正在从中进行复制的组中的评估的客户托管控件的“实施详细信息”和“测试计划”和“管理响应”字段中的任何信息都会复制到新评估中的同一（或相关）客户托管控件。 要为现有组添加新的评估，该组中评估的常见信息会复制到新的评估中。 有关详细信息，请参阅[从现有评估复制信息](#copying-information-from-existing-assessments)。
    
3. 单击“下一步”****，再按照以下步骤操作：
    
    a. 从“**选择产品**”下拉列表选择要评估合规性的 Microsoft 云服务。 
    
    b. 从“**选择认证**”下拉列表选择据以评估所选云服务的认证。 
    
4. 单击“添加到仪表板”**** 以创建评估；此时，新评估会添加到合规性管理器仪表板中，作为现有磁贴列表末尾的新磁贴。 
    
    合规性管理器仪表板中的**评估磁贴**显示评估分组、评估名称（自动创建为服务名称和选定认证的组合）、创建日期、上次修改时间和总合规性分数（即所有已实现、测试并通过的已分配控制措施的风险分数总和），并在底部显示指明已评估控制措施数的进度指示器。 
    
5. 单击评估名称即可打开它，并查看评估的详细信息。
    
6. 单击“**行动**”菜单，可查看已分配的行动项、重命名评估组、导出评估报告或存档评估。 
    
    ![合规性管理器 — 评估磁贴](../media/abf35c11-9757-45c1-aa14-91178f67a18c.png)

## <a name="copying-information-from-existing-assessments"></a>从现有评估复制信息

如前所述，创建评估组时，可以选择将现有组中评估的信息复制到新组中的新评估。 这使你可以将已完成的评估和测试工作应用到新评估中相同的客户托管控件中。 例如，如果组织中具有所有与 GDPR 相关的评估的组，则向组添加新的评估时，可以从现有评估工作中复制常见信息。
  
可以将下面的信息从客户复制到新评估：
  
- Assessment Users. An Assessment user is a user who the control is assigned to.
    
- 状态、测试日期和测试结果。
    
- 实现详情和测试计划信息。
    
同样地，同一评估组中共享客户托管控件的信息会同步。 并且同一评估中相关客户托管控件的信息也会同步。

## <a name="viewing-assessments"></a>查看评估

1. 查找与要查看的评估对应的评估磁贴，再单击评估名称以打开它，并查看与评估相关联的 Microsoft 管理和客户管理的控制措施，以及评估的范围内云服务列表。 下面的示例展示了“Office 365 + GDPR”评估。
    
    ![合规性管理器评估视图 — 含标注的全屏视图](../media/169a02eb-e805-412d-b9e7-89561aa7ad1d.png)
  
1. 此部分显示了评估摘要信息，包括评估分组名称、产品、评估名称和评估控制措施数
    
2. This section shows the Assessment Filter controls. For a more detailed explanation of how to use the Assessment Filter controls see the [Managing the assessment process](#managing-the-assessment-process) section. 
    
3. 此部分显示了评估的各个范围内云服务。
    
4. 本部分包含 Microsoft 托管控件。 按控件系列整理相关控件。 单击控件系列，即可将其展开并显示单个控件。
    
5. 本部分包含同样按照控件系列进行整理的客户托管控件。 单击控件系列，即可将其展开并显示单个控件。
    
6. 显示控件系列中的控件总数，及已评估的控件数。 合规性管理器的关键功能是跟踪组织评估客户托管控件的进度。 有关详细信息，请参阅[了解合规性分数](#understanding-the-compliance-score)一节。 

## <a name="managing-the-assessment-process"></a>管理评估流程

评估的创建者最初是唯一的评估用户。 对于每个客户托管控件，可以将操作项目分配给组织中的某个人，这样该人员成为可执行推荐客户操作并收集和上传证据的评估用户。 分配操作项目时，可以选择向包含推荐客户操作和操作项目优先级等详细信息的人员发送电子邮件。 电子邮件通知包括指向**操作项目**仪表板的链接，其中列出了分配给该人员的所有操作项目。 
  
下面列出了使用合规性管理器的工作流功能可以执行的任务。
  
![含标注的合规性管理器评估工作流](../media/9e5ae34d-b55e-4452-a021-e0e5b10218f5.png)
  
1. **使用筛选器选项查找特定评估控制措施** - 合规性管理器提供了**筛选器选项**，可便于选择高度细化的评估控制措施筛选条件，有助于精确定位合规性工作的特定领域。 
    
    单击页面右侧的漏斗图标可显示或隐藏“**筛选器选项**”控件。 这些控件允许指定筛选条件，只有符合这些条件的评估控件才会显示在下方。 ![合规性管理器评估筛选控制措施](../media/d44e1b4b-d928-4778-8a3a-6231edde9ca0.png)
  
    - **条款** - 筛选条款名称，返回与该条款相关的评估控件。 例如，键入“条款(5)”可返回名称中包含此字符串的条款的选择列表，即条款 (5)(1)(a)、条款 (5)(1)(b)、条款 (5)(1)(c) 等。选择“条款(5)(1)(c)”会返回与条款 (5)(1)(c) 关联的控制措施。 这是使用 OR 运算符的多值多选字段。例如，如果你先选择“条款(5)(1)(a)”，再添加“条款(5)(1)(c)”，筛选器会返回与条款 (5)(1)(a) 或条款 (5)(1)(c) 关联的控制措施。 
    
      ![合规性管理器评估视图 — 筛选条款名称](../media/8b0507a0-589d-484a-bc60-80a3debe3ddb.png)
  
    - **控制措施** - 返回名称符合筛选条件的控制措施列表，即键入“7.3”返回项的选择列表，如 7.3.1、7.3.4、7.3.5 等。这是使用 OR 运算符的多值多选字段。例如，如果你先选择“7.3.1”，再添加“7.3.4”，筛选器会返回与 7.3.1 或 7.3.4 关联的控制措施。 
    
      ![合规性管理器评估视图 - 筛选控制措施（多选）](../media/c4fc25e8-2376-4f2d-b605-f9c3d90413bf.png)
  
    - **已分配用户** - 返回包含已分配选定用户的控制措施列表。 
    
    - **状态** - 返回包含选定状态的控制措施列表。 
    
    - **测试结果** - 返回包含选定测试结果的控制措施列表。 
    
    As you apply filter conditions, the view of applicable controls will change to correspond to your filter conditions. Expand the control family sections to show the control details below. 
    
    ![合规性管理器 - 评估视图 - 筛选条款结果](../media/e6485d45-d47f-4b25-8b1c-b3c2ee4a8328.png)
  
2. If after selecting the desired filters no results are shown, that means there are no controls that correspond to the specified filter conditions. For instance, if you select a particular **Assigned User** and then choose a **Control** name that does correspond to the control assigned to that user, no assessments will be shown in the page below. 
    
3. **Assign an Action Item to a user** - You can assign an Action Item to a person to implement the requirements of a certification/regulation, or to test, verify, and document your organization's implementation requirements. When you assign an Action Item, you can choose to send an email to the person that contains details including the recommended Customer Actions and the Action Item priority. You can also unassign or reassign an Action Item to a different person. 
    
4. **管理文档** - 客户托管控件还提供管理与实施任务的执行、测试和验证任务的执行相关的文档的功能。 有权在合规性管理器中编辑数据的任何人都可以通过单击“**管理文档**”上传文档。 上传文档后，可以单击“**管理文档**”，查看和下载文件。 
    
5. **提供实现和测试详情** - 每项客户管理的控制措施都有一个可编辑字段，便于用户添加实现详情，以记录组织为符合认证/法规要求，以及为验证和记录组织如何符合这些要求所采取的步骤。
    
6. **Set Status** - Set the Status for each item as part of the assessment process. Available status values are **Implemented**, **Alternative Implementation**, **Planned**, and **Not in Scope**. 
    
7. **输入测试日期和测试结果** - 具有合规性管理器评估方角色的人员可以验证是否执行了合适的测试，查看实施详细信息、测试计划、测试结果和上传的任何证据，然后设置“测试日期”和“测试结果”。 可能的测试结果值有“**通过**”、“**失败 - 低风险**”、“**失败 - 中等风险**”和“**失败 - 高风险**”。 

## <a name="managing-action-items"></a>管理行动项

组织中参与评估过程的人员可以使用合规性管理器检查其作为用户的所有评估中的客户托管控件。 用户登录合规性管理器并打开“**操作项目**”仪表板时，会显示分配给他们的操作项目列表。 根据分配给用户的合规性管理器角色，他们可以提供实施或测试详细信息，更新状态或分配操作项目。 
  
As certification controls are generally implemented by one person and tested by another, the control action item can be initially assigned to one person for implementation, and once that is complete, that person can reassign the control action item to the next person for control testing and uploading of evidence. This assignment/reassignment of control actions can be performed by any users who have a Compliance Manager role with sufficient permissions, allowing for central management of control assignments, or decentralized routing of control action items, from implementer to tester as appropriate.
  
若要分配行动项，请执行以下操作：
  
1. 在合规性管理器仪表板中，找到要处理的评估的评估磁贴，再单击评估名称，以转到评估详情页。
    
2. 可单击“筛选器”****，并使用筛选器控件查找要分配的特定评估控制措施；或 
    
3. 向下滚动到“客户管理的控制措施”部分，展开控制措施系列，并滚动浏览控制措施列表，直到找到要分配的评估控制措施。
    
4. 在“已分配用户”**** 列下，单击“分配”****。 
    
5. In the Assign Action Item dialog box, click the **Assign To** field to populate the list of users to whom the action can be assigned. You can scroll through the list to find the target user or start typing in the field to search for the username. 
    
6. 单击用户，以向其分配此行动项。
    
7. 若要向用户发送电子邮件通知，请务必选中“发送电子邮件通知”**** 复选框。 
    
8. 键入要向此用户显示的任何备注，再单击“分配”****。 
 
    用户收到的通知中既包含行动项分配，也包含你提供的任何备注。
    
The notes that are associated with the action item are persisted in the notes section, available for the next time the action item is assigned. These notes are not read-only, can be edited, replaced or removed by the person assigning the action item.

## <a name="exporting-information-from-an-assessment"></a>导出评估中的信息

可以将评估导出到 Excel 文件，由组织中的合规性利益干系人审查，并提供给审核人员和监管人员。 本评估报告是报告创建时点的评估快照，其中包含该评估的 Microsoft 托管控件和客户托管控件的详细信息，包括控件实施状态、控件测试日期和测试结果，并提供已上传的证据文档的链接。 建议在对评估进行存档之前先导出评估报告，因为已存档的评估不会保留已上传的文档的链接。
  
若要导出评估报告，请执行以下操作：
  
- 在合规性管理器仪表板中要导出的评估的评估磁贴上，单击“行动”****，再选择“导出为 Excel”****

  或
    
- 若要查看评估详情页，请单击“**导出为 Excel**”按钮，此按钮位于页面右上角的评估合规性分数上方。
    
The assessment report will be downloaded in your browser session. If you don't see a popup informing you of this, you may wish to check your browser's downloads folder.

## <a name="archiving-an-assessment"></a>存档评估

When you have completed an Assessment and no longer need it for compliance purposes, you can archive it. When an Assessment is archived, it is removed from Assessments dashboard.
  
> [!NOTE]
> When an Assessment is Archived, it cannot be 'unarchived' or restored to a read-write in progress state. Please note that Archived Assessments do not retain their links to uploaded evidence documents, so it is highly recommended that you perform an Export of the Assessment before archiving it, as the exported assessment report will contain links to the evidence documents, enabling you to continue to access them. 
  
若要存档评估，请执行以下操作：
  
1. 在相应评估的仪表板磁贴上，单击“行动”****。 
    
2. 选择“存档评估”****。 
 
    此时，“存档评估”**** 对话框显示，询问是否确认要存档评估。
    
4. 若要继续存档，请单击“存档”****；否则，请单击“取消”****。 
    
若要查看已存档评估，请执行以下操作：
  
1. 在合规性管理器仪表板中，选中“显示已存档评估”**** 复选框。 
    
    此时，已存档评估会显示在其余活动评估下方新显示的部分中，位于标题为“已存档评估”**** 的栏下。
    
3. 单击要查看的评估的名称。
    
当你查看已存档评估时，所有通常可编辑的控件（即“实现”和“测试结果”）都处于禁用状态，且看不到“管理文档”**** 按钮。

## <a name="using-search"></a>使用搜索

![服务信任门户 -“搜索”输入字段](../media/7c5cd817-3d62-420b-adb4-76e33fef941f.png)
  
Click the magnifying glass in the upper right-hand corner of the page by to expand the Search input field, enter your search terms and press Enter. The Search control will appear, with the search term in the search pane input field, and search results will appear beneath.
  
By default, Search returns Document results, and you can use the Filter By dropdown lists to refine the list of documents displayed, to add or remove search results from view. You can use multiple filter attributes at the same time to narrow the returned documents to specific cloud services, categories of compliance or security practices, regions of the world, or industries. Click the document name link to download the document.
  
![服务信任门户 - 搜索文档（应用了筛选器）](../media/86b754e1-c63c-4514-89ac-d014bf334140.png)
  
单击“合规性管理器”链接，以显示合规性管理器评估控件的搜索结果。 列出的搜索结果会显示创建评估的日期、评估分组的名称、适用的云服务，以及该控件由 Microsoft 还是客户管理。
  
![服务信任门户 - 搜索合规性管理器控制措施](../media/bafb811a-68ce-40b5-ad16-058498fe5439.png)
  
> [!NOTE]
> 服务信任门户报告和文档在发布后的至少 12 个月内或在新版文档发布前都可供下载。 
 
## <a name="localization-support"></a>本地化支持

Service Trust Portal enables you to view the page content in different languages. To change the page language, simply click on the globe icon in the lower left corner of the page and select the language of your choice. 
  
![服务信任门户 - 本地化内容选项](../media/b50c677e-a886-4267-9eca-915d880ead7a.png)


## <a name="change-log-for-customer-managed-controls"></a>客户管理的控制措施的更改日志

合规性管理器旨在定期更新，以与法规要求的更改以及我们云服务中的更改保持同步。 这些更新包括对客户托管控件的更改。 并提供更改日志，帮助用户了解这些更改的影响，包括已添加或更改的内容的详细信息以及有关更改对现有评估的影响的指南。 通常有两种类型的更改：
  
- A **Major** change is a significant change to a Customer Action, such as the addition or removal of a control or specific numbered steps, or a change in the guidance around responsibilities, recommendations, or evidence. For Major changes, we recommend that you re-evaluate your implementation and/or assessment of the affected control.
    
- A **Minor** change is an insignificant change to a Customer Actions, such as fixing a typo or formatting issues, or updating or correcting hyperlinks. Minor changes generally do not require the control to be re-evaluated; however, we do recommend that you review the updated Customer Action.
  
### <a name="customer-managed-controls---change-log-for-july-2018"></a>客户管理的控制措施 - 2018 年 7 月更改日志

|**控制措施 ID**|**评估**|**更改类型**|**更改说明**|**建议客户采取的行动**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|45 C.F.R. § 164.308(a)(7)(ii)(A)<br/> |Office 365：HIPAA|主要|向“Office 365 - HIPAA”评估添加了 HITECH 控制措施 |查看添加的控制措施和建议的客户行动<br/> |
|45 C.F.R.  164.312(a)(6)(ii)|Office 365：HIPAA|主要|向“Office 365 - HIPAA”评估添加了 HITECH 控制措施|查看添加的控制措施和建议的客户行动<br/>|
45 C.F.R. § 164.312(c)(1)| Office 365：HIPAA|主要| 向“Office 365 - HIPAA”评估添加了 HITECH 控制措施 |查看添加的控制措施和建议的客户行动<br/> |
45 C.F.R.  § 164.316(b)(2)(iii)| Office 365：HIPAA|主要|向“Office 365 - HIPAA”评估添加了 HITECH 控制措施|查看添加的控制措施和建议的客户行动<br/>|
|

### <a name="customer-managed-controls---change-log-for-april-2018"></a>客户管理的控制措施 - 2018 年 4 月更改日志

|**GDPR**|**HIPAA**|**ISO 27001**|**ISO 27018**|**NIST 800-53**|**NIST 800-171**|**更改类型**|**更改说明**|**建议客户采取的行动**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|6.13.2  <br/> |||C.16.1.1  <br/> |||主要  <br/> |旧编号为 6.12.1.1。  <br/> 添加了有关建议的详细信息。  <br/> |重新评估控制措施：查看客户行动中的更新后指导，并按照建议步骤来实现和评估控制措施。  <br/> |
||||||3.1.6  <br/> |主要  <br/> |向包括启用审核和搜索审核日志的指导中添加了步骤。  <br/> |查看客户行动中的更新后建议。  <br/> |
|6.8.2  <br/> |||A.10.2  <br/> |||主要  <br/> |旧编号为 6.7.2.9。  <br/> 更新了指导，在其中添加了其他建议和行动项。  <br/> |重新评估控制措施：查看客户行动中的更新后指导，并按照建议步骤来实现和评估控制措施。  <br/> |
|6.6.4  <br/> |45 C.F.R. § 164.312(a)(2)(i)  <br/>           45 C.F.R. § 164.312(d)  <br/> |A.9.4.2  <br/> ||IA-2  <br/> |3.5.1  <br/> |主要  <br/> |旧编号为 6.5.2.3。  <br/> 更新了指导，在其中添加了其他建议和行动项。  <br/> |重新评估控制措施：查看客户行动中的更新后指导，并按照建议步骤来实现和评估控制措施。  <br/> |
|6.13.1  <br/> |45 C.F.R. § 164.308(a)(1)(i)  <br/> |A.16.1  <br/> |C.16.1  <br/> |IR-4(a)  <br/> |3.6.1  <br/> |主要  <br/> |旧编号为 6.12.1。  <br/> 更新了指导，在其中添加了其他建议和行动项。  <br/> |重新评估控制措施：查看客户行动中的更新后指导，并按照建议步骤来实现和评估控制措施。  <br/> |
|6.7  <br/> ||||||主要  <br/> |旧编号为 6.6.1.1。  <br/> 更新了指导，在其中添加了其他建议和行动项。  <br/> |重新评估控制措施：查看客户行动中的更新后指导，并按照建议步骤来实现和评估控制措施。  <br/> |
|6.6.5  <br/> |||A.10.8  <br/> |IA-3  <br/> |3.5.2  <br/> |主要  <br/> |旧编号为 6.5.4.2。  <br/> 更新了指导，在其中添加了其他建议和行动项。  <br/> |重新评估控制措施：查看客户行动中的更新后指导，并按照建议步骤来实现和评估控制措施。  <br/> |
|6.15.1  <br/> ||||||主要  <br/> |旧编号为 6.14.1.3。  <br/> 更新了指导，在其中添加了其他建议和行动项。  <br/> |重新评估控制措施：查看客户行动中的更新后指导，并按照建议步骤来实现和评估控制措施。  <br/> |
|||||AC-2(h)(2)  <br/> ||次要  <br/> |添加了指向“启用审核”边栏选项卡的链接。  <br/> |无需采取任何行动。  <br/> |
|||||AC-2(7)(b)  <br/> ||次要  <br/> |添加了指向“启用审核”边栏选项卡的链接。  <br/> |无需采取任何行动。  <br/> |
|||||AC-2(h)(1)  <br/> ||次要  <br/> |添加了指向“启用审核”边栏选项卡的链接。  <br/> |无需采取任何行动。  <br/> |
||45 C.F.R. § 164.308(a)(5)(ii)(C)  <br/> |||AC-2(g)  <br/> ||次要  <br/> |添加了指向“启用审核”边栏选项卡的链接。  <br/> |无需采取任何行动。  <br/> |
|||||AC-2(12)  <br/> ||次要  <br/> |添加了指向“启用审核”边栏选项卡的链接。  <br/> |无需采取任何行动。  <br/> |
||45 C.F.R. § 164.312(b)  <br/> |A.12.4.3  <br/> ||AU-2(d)  <br/> ||次要  <br/> |添加了指向“启用审核”边栏选项卡的链接。  <br/> |无需采取任何行动。  <br/> |
|||||AC-2(4)  <br/> ||次要  <br/> |添加了指向“启用审核”边栏选项卡的链接。  <br/> |无需采取任何行动。  <br/> |
||||||3.1.7  <br/> |次要  <br/> |添加了指向“启用审核”边栏选项卡的链接。  <br/> |无需采取任何行动。  <br/> |
|||A.16.1.7  <br/> |C.12.4.2，第 2 部分  <br/> |||次要  <br/> |添加了指向“启用审核”边栏选项卡的链接。  <br/> |无需采取任何行动。  <br/> |
|||||AC-2(h)(3)  <br/> ||次要  <br/> |添加了指向“启用审核”边栏选项卡的链接。  <br/> |无需采取任何行动。  <br/> |
|||A.12.4.2  <br/> ||||次要  <br/> |添加了指向“启用审核”边栏选项卡的链接。  <br/> |无需采取任何行动。  <br/> |
|||A.7.2.8  <br/> ||||次要  <br/> |添加了指向“内容搜索”边栏选项卡和 DSR 门户的链接。  <br/> |无需采取任何行动。  <br/> |
||45 C.F.R. § 164.308(a)(3)(ii)(C)  <br/> |||||次要  <br/> |添加了指向“启用审核”边栏选项卡和 Office 365 管理员角色支持主题的链接。  <br/> |无需采取任何行动。  <br/> |
|5.2.1  <br/> ||||||次要  <br/> |旧编号为 5.2.2。  <br/> 在指导中阐明了客户职责。  <br/> |查看客户行动中的更新后建议。  <br/> |
|6.11.1  <br/> |45 C.F.R. § 164.312(e)(2)(ii)  <br/> |A.10.1.1          A.10.1.2          A.18.1.5  <br/> |C.10.1.1  <br/> |SC-13  <br/> |3.13.11  <br/> |次要  <br/> |旧编号为 6.10.1.2。  <br/> 更正了拼写错误。  <br/> |无需采取任何行动。  <br/> |
|7.5.1  <br/> ||||||次要  <br/> |旧编号为 A.7.4.1。  <br/> 更正了拼写错误。  <br/> |无需采取任何行动。  <br/> |
|||A.8.2.3  <br/> |||3.1.3  <br/> |次要  <br/> |删除了多余的不必要句子。  <br/> |无需采取任何行动。  <br/> |
||45 C.F.R. § 164.308(a)(4)(i)  <br/> |A.6.1.2  <br/> ||AC-5(a)  <br/> |3.1.2          3.1.4  <br/> |次要  <br/> |更新了指导，在其中添加了其他建议和行动项。  <br/> |查看客户行动中的更新后建议。  <br/> |
||45 C.F.R. § 164.308(a)(7)(ii)(E)  <br/> |||RA-2(a)  <br/> ||次要  <br/> |已将导入服务帮助主题链接更新为使用 FWLink。  <br/> |无需采取任何行动。  <br/> |
|

### <a name="gdpr-assessment-control-id-change-reference---change-log-for-february-2018"></a>GDPR 评估控制措施 ID 更改参考 - 2018 年 2 月更改日志 

|**旧控制措施 ID（2017 年 11 月预览版）**|**新控制措施 ID（2018 年 2 月正式版）**|
|:-----|:-----|
|5.2.2  <br/> |5.2.1  <br/> |
|5.2.3  <br/> |5.2.2  <br/> |
|5.2.4  <br/> |5.2.3  <br/> |
|6.1.1.1  <br/> |6.2  <br/> |
|6.10.1.2  <br/> |6.11.1  <br/> |
|6.10.2.5  <br/> |6.11.2  <br/> |
|6.11.1.2  <br/> |6.12  <br/> |
|6.12.1  <br/> |6.13.1  <br/> |
|6.12.1.1  <br/> |6.13.2  <br/> |
|6.12.1.5  <br/> |6.13.3  <br/> |
|6.14.1.3  <br/> |6.15.1  <br/> |
|6.14.2.1  <br/> |6.15.2  <br/> |
|6.14.2.3  <br/> |6.15.3  <br/> |
|6.2.1.1  <br/> |6.3  <br/> |
|6.3.2.2  <br/> |6.4  <br/> |
|6.4.3.1  <br/> |6.5.2  <br/> |
|6.4.3.2  <br/> |6.8.1  <br/> |
|6.4.3.3  <br/> |6.5.3  <br/> |
|6.5.2  <br/> |6.6.1  <br/> |
|6.5.2.1  <br/> |6.6.2  <br/> |
|6.5.2.2  <br/> |6.6.3  <br/> |
|6.5.2.3  <br/> |6.6.4  <br/> |
|6.5.4.2  <br/> |6.6.5  <br/> |
|6.6.1.1  <br/> |6.7  <br/>   |
|6.7.2.7  <br/> |6.8.1  <br/> |
|6.7.2.9  <br/> |6.8.2  <br/> |
|6.8.1.4  <br/> |6.9.1  <br/> |
|6.8.4.1  <br/> |6.9.3  <br/> |
|6.8.4.2  <br/> |6.9.4  <br/> |
|6.9.2.1  <br/> |6.10.1  <br/>|
|6.9.2.3  <br/> |6.10.2  <br/>|
|A.7.1.1  <br/> |7.2.1  <br/> |
|A.7.1.2  <br/> |7.2.2  <br/> |
|A.7.1.3  <br/> |7.2.3  <br/> |
|A.7.1.4  <br/> |7.2.4  <br/> |
|A.7.1.5  <br/> |7.2.5  <br/> |
|A.7.1.6  <br/> |7.2.6  <br/> |
|A.7.1.7  <br/> |7.2.7  <br/> |
|A.7.2.1  <br/> |7.3.1  <br/> |
|A.7.2.10 <br/> |7.3.9  <br/> |
|A.7.2.11 <br/> |7.3.10  <br/>|
|A.7.2.2  <br/> |7.3.2  <br/> |
|A.7.2.3  <br/> |7.3.3  <br/> |
|A.7.2.4  <br/> |7.3.4  <br/> |
|A.7.2.5  <br/> |7.3.5  <br/> |
|A.7.2.6  <br/> |7.3.6  <br/> |
|A.7.2.7  <br/> |7.3.7  <br/> |
|A.7.2.8  <br/> |7.3.8  <br/> |
|A.7.3.1  <br/> |7.4.1  <br/> |
|A.7.3.10 <br/> |7.4.10  <br/>|
|A.7.3.2  <br/> |7.4.2  <br/> |
|A.7.3.3  <br/> |7.4.3  <br/> |
|A.7.3.4  <br/> |7.4.4  <br/> |
|A.7.3.5  <br/> |7.4.5  <br/> |
|A.7.3.6  <br/> |7.4.6  <br/> |
|A.7.3.7  <br/> |7.4.7  <br/> |
|A.7.3.8  <br/> |7.4.8  <br/> |
|A.7.3.9  <br/> |7.4.9  <br/> |
|A.7.4.1  <br/> |7.5.1  <br/> |
|A.7.4.2  <br/> |7.5.2  <br/> |
|A.7.4.3  <br/> |7.5.3  <br/> |
|A.7.4.4  <br/> |7.5.4  <br/> |
|A.7.4.5  <br/> |7.5.5  <br/> |
|B.8.1.1  <br/> |8.2.1  <br/> |
|B.8.1.2  <br/> |8.2.2  <br/> |
|B.8.1.3  <br/> |8.2.3  <br/> |
|B.8.1.4  <br/> |8.2.4  <br/> |
|B.8.1.5  <br/> |8.2.5  <br/> |
|B.8.1.6  <br/> |8.2.6  <br/> |
|B.8.2.1  <br/> |8.3.1  <br/> |
|B.8.3.1  <br/> |8.4.1  <br/> |
|B.8.3.2  <br/> |8.4.2  <br/> |
|B.8.3.3  <br/> |8.4.3  <br/> |
|B.8.4.1  <br/> |8.5.1  <br/> |
|B.8.4.2  <br/> |8.5.2  <br/> |
|B.8.4.3  <br/> |8.5.4  <br/> |
|B.8.4.4  <br/> |8.5.5  <br/> |
|B.8.4.5  <br/> |8.5.3  <br/> |
|B.8.4.6  <br/> |8.5.6  <br/> |
|B.8.4.7  <br/> |8.5.7  <br/> |
|B.8.4.8  <br/> |8.5.8  <br/> |
|
   
## <a name="see-also"></a>另请参阅

- [合规性管理器交互指南](https://content.cloudguides.com/guides/Compliance%20Manager)

- [宣布合规性管理器正式推出](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Announcing-Compliance-Manager-general-availability/ba-p/161922)

- [Microsoft 365 提供有助于遵守 GDPR 的信息保护策略](https://blogs.office.com/2018/02/22/microsoft-365-provides-an-information-protection-strategy-to-help-with-the-gdpr)
