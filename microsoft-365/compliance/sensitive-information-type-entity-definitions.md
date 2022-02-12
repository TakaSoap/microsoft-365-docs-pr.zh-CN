---
title: 敏感信息类型属性定义
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: 有很多敏感信息类型可供您用于 DLP 策略。 本文列出了所有这些敏感信息类型，并演示 DLP 策略在检测到每种类型时查找的信息。
ms.openlocfilehash: 208c36aec9baf1aeee2856869b3a789312305a9b
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2022
ms.locfileid: "62766892"
---
# <a name="sensitive-information-type-entity-definitions"></a>敏感信息类型属性定义

本文列出了所有敏感信息类型实体定义。 每个定义都显示 DLP 策略查找以检测每种类型。 若要了解有关敏感信息类型的信息，请参阅 [敏感信息类型](sensitive-information-type-learn-about.md)

> [!NOTE]
> 置信度 (高/中/低) 的映射 (1 到 100) 
> - 低可信度：65 或以下
> - 中等可信度：75
> - 高可信度：85


## <a name="aba-routing-number"></a>ABA 路由号码

### <a name="format"></a>格式

9 个数字，可能采用格式化或无格式模式

### <a name="pattern"></a>模式

- 00-12、21-32、61-72 或 80 之间的两个数字
- 两个数字
- 可选连字符
- 四个数字
- 可选连字符
- 一个数字


### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

如果策略在 300 个字符的邻近度内检测到这种类型的敏感信息，则策略具有中等可信度：
- 函数 Func_aba_routing 找到与该模式匹配的内容。
- 找到 Keyword_ABA_Routing 中的一个关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数 Func_aba_routing 找到与该模式匹配的内容。

```xml
    <!-- ABA Routing Number -->
    <Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_aba_routing" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_aba_routing"></a>Keyword_aba_routing

- aba number
- aba#
- aba
- abarouting#
- abaroutingnumber
- americanbankassociationrouting#
- americanbankassociationroutingnumber
- bankrouting#
- bankroutingnumber
- routing#
- routing no
- 路由号码
- routing transit number
- routing#
- RTN


## <a name="all-full-names"></a>所有全名

这是一个捆绑命名实体，可检测来自所有受支持国家/地区的人员的完整姓名，包括澳大利亚、中国、日本、美国和欧盟国家/地区。 使用此 SIT 检测所有可能的全名匹配项。

### <a name="format"></a>格式

各种。

### <a name="pattern"></a>模式

各种。

### <a name="checksum"></a>校验和

不正确。

### <a name="description"></a>说明

此已命名实体 SIT 与用户以高可信度标识为名称的个人名称匹配。 它使用三个主要资源：

-   给定名称的字典。
-   系列名称字典。
-   名称构成方式的模式。

这三个资源对于每个国家/地区是不同的。 例如，对于美国字典中的名称，如果找到由给定名称组成的字符串，后跟一个系列名称，则使用高可信度进行匹配。 字符串 *Olivia Wilson* 将触发匹配。通常给定/系列名称的置信度比罕见名称高。 但是，模式还允许部分匹配。 例如，字典中的给定名称后跟不在字典中的系列名称，例如 *Tomas Richard* 将触发部分匹配。 部分匹配项的置信度较低。

此外，人们看到的作为名称指示的模式也以相应的可信度进行匹配。 与 *O. Wilson、**O.P. Wilson*、*O. P. Wilson*、*Wilson、O.P.* 或 *T. Richard， Jr.* 将是匹配项。

### <a name="supported-languages"></a>支持的语言

- 英语
- 保加利亚语
- 中文
- 克罗地亚语
- 捷克语
- 丹麦语
- 爱沙尼亚语
- 芬兰语
- 法语
- 德语
- 匈牙利语
- 冰岛语
- 爱尔兰语
- 意大利语
- 日语
- 拉脱维亚语
- 立陶宛语
- 马耳他语
- 荷兰语
- 挪威语
- 波兰语
- 葡萄牙语
- 罗马尼亚语
- 斯洛伐克语
- 斯洛文尼亚语
- 西班牙语
- 瑞典语
- 土耳其语


## <a name="all-medical-terms-and-conditions"></a>所有医疗条款和条件

这是一个捆绑的命名实体，可检测医疗术语和医疗状况。 它仅检测英语术语。 使用此 SIT 检测所有可能的医疗条款和条件匹配项。

### <a name="format"></a>格式

Dictionary

### <a name="pattern"></a>模式

Dictionary

### <a name="checksum"></a>校验和

否

### <a name="description"></a>说明

此捆绑命名实体与涉及特选词典中的医疗状况的文本匹配。 每个受支持的语言有一个已选择词典。 这些词典来自大量国际医疗资源。 所策展的词典包含尽可能多的医疗条件，而不会面临大量误报的风险。 .每个条目都包含通常写入单个条件以确保覆盖范围的不同形式，例如：

- *TB*
- *功能区*
- *phthisis 为alis*

### <a name="contains"></a>Contains

此捆绑命名实体 SIT 包含这些单独的 SIT。

- 检测词 
- 企业类型
- 动物
- 通用名
- 美国社会保险下残障评估中列出的残障人士
- 实验室测试术语
- 与医疗状况相关的生活方式
- 医疗特长
- 过程：一些程序
- 品牌品牌名称


## <a name="all-physical-addresses"></a>所有物理地址

这是一个捆绑实体 SIT，可检测与来自所有受支持的国家/地区的物理地址相关的模式。

### <a name="format"></a>格式

各种

### <a name="pattern"></a>模式

各种

### <a name="checksum"></a>校验和

否

### <a name="description"></a>说明

街道地址的匹配旨在匹配用户标识为街道地址的字符串。 为此，它使用若干主要资源：

-   一个包含城市、国家/地区和地区的字典。
-   街道后缀字典，如"路"、街道或"街道"。
-   邮政编码的模式。
-   地址格式的模式。

资源对于每个国家/地区是不同的。 主要资源是给定国家/地区中使用的地址格式的模式。 选择不同的格式以确保匹配尽可能多的地址，而不会面临大量误报的风险。 这些格式允许灵活性，例如，地址可以省略邮政编码，也可以省略街道名称，或者具有没有街道后缀的街道。 在所有情况下，此类匹配都用于提高匹配可信度。

请注意，这些模式旨在匹配单个地址，而不是通用位置。 因此， *Redmond、WA 98052* 或 *Main Street、Albuquerque* 等字符串将不匹配。

### <a name="contains"></a>Contains

此捆绑的命名实体 SIT 包含以下单个 SIT：

- 澳大利亚物理地址
- 奥地利物理地址
- 比利时物理地址
- 巴西物理地址
- 保加利亚物理地址
- 加拿大物理地址
- 克罗地亚物理地址
- 塞浦路斯物理地址
- 捷克共和国物理地址
- 丹麦物理地址
- 爱沙尼亚物理地址
- 芬兰物理地址
- 法国物理地址
- 德国物理地址
- 希腊物理地址
- 匈牙利物理地址
- 冰岛物理地址
- 爱尔兰物理地址
- 意大利物理地址
- 拉脱维亚物理地址
- 列支敦士登物理地址
- 立陶宛物理地址
- 卢森堡物理地址
- 马耳他物理地址
- 荷兰物理地址
- 新西兰物理地址
- 挪威物理地址
- 波兰物理地址
- 葡萄牙物理地址
- 罗马尼亚物理地址
- 斯洛伐克物理地址
- 斯洛文尼亚物理地址
- 西班牙物理地址
- 瑞典物理地址
- 瑞士物理地址
- 土耳其物理地址
- 英国物理地址
- 美国物理地址

### <a name="supported-languages"></a>支持的语言

- 英语
- 保加利亚语
- 中文
- 克罗地亚语
- 捷克语
- 丹麦语
- 爱沙尼亚语
- 芬兰语
- 法语
- 德语
- 匈牙利语
- 冰岛语
- 爱尔兰语
- 意大利语
- 日语
- 拉脱维亚语
- 立陶宛语
- 马耳他语
- 荷兰语
- 挪威语
- 波兰语
- 葡萄牙语
- 罗马尼亚语
- 斯洛伐克语
- 斯洛文尼亚语
- 西班牙语
- 瑞典语
- 土耳其语


## <a name="argentina-national-identity-dni-number"></a>阿根廷国家/ (DNI) 号码

### <a name="format"></a>格式

带或不带句号的八个数字

### <a name="pattern"></a>模式

八个数字：
- 两个数字
- 可选时间段
- 三个数字
- 可选时间段
- 三个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式 Regex_argentina_national_id 找到与该模式匹配的内容。
- 找到 Keyword_argentina_national_id 中的一个关键字。

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina National Identity number
- cedula
- cédula
- dni
- documento nacional de identidad
- documento número
- documento numero
- registro nacional de las personas
- rnp


## <a name="argentina-unique-tax-identification-key-cuitcuil"></a>阿根廷唯一税务识别密钥 (CUIT/CUIL) 

### <a name="format"></a>格式

11 个数字（带短划线）

### <a name="pattern"></a>模式

带破折号的 11 个数字：
- 20、23、24、27、30、33 或 34 中的两个数字
- 连字符 (-) 
- 八个数字
- 连字符 (-) 
- 一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 `Func_Argentina_Unique_Tax_Key` 查找与模式匹配的内容。
- 找到 的 `Keyword_Argentina_Unique_Tax_Key` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 `Func_Argentina_Unique_Tax_Key` 查找与模式匹配的内容。

```xml
    <!-- Argentina Unique Tax Identification Key (CUIT/CUIL) -->
      <Entity id="98da3da1-9199-4571-b7c4-b6522980b507" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
          <Match idRef="Keyword_Argentina_Unique_Tax_Key" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_argentina_unique_tax_key"></a>Keyword_Argentina_Unique_Tax_Key

- Clave Unica de Identificacion Tribut一
- CUIT
- 唯一的标识代码 
- Clave Única de Identificación Tribut一
- 唯一的树标识代码
- CUIL
- 唯一税务标识密钥
- 唯一的位元标识密钥
- 唯一的标识密钥
- 唯一工作标识代码
- 工作标识的唯一代码
- 唯一工作标识密钥
- 工作标识的唯一密钥
- 唯一的税务识别代码
- 税务识别的唯一密钥
- 唯一人工标识代码
- 唯一的人工标识代码
- 唯一人工标识密钥
- 唯一的人工标识密钥
- tax ID
- taxID#
- taxId
- 一些
- tax number
- tax no
- tax#
- tax#
- 用户 ID
- 用户编号
- "不""不"。
- 将#
- 将#
- tax identity
- tax identification
- Número de Identificación Fiscal
- número de contribuyente


## <a name="australia-bank-account-number"></a>澳大利亚银行帐号

### <a name="format"></a>格式

具有或不带银行省/市/县分支机构号码的 6 到 10 个数字

### <a name="pattern"></a>模式

帐户号码是 6 到 10 个数字。

澳大利亚银行州级分部编号：
- 三个数字
- 连字符
- 三个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式Regex_australia_bank_account_number查找与模式匹配的内容。
- 找到 Keyword_australia_bank_account_number 中的一个关键字。
- 正则表达式 Regex_australia_bank_account_number_bsb 找到与该模式匹配的内容。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式Regex_australia_bank_account_number查找与模式匹配的内容。

- 找到 Keyword_australia_bank_account_number 中的一个关键字。

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_australia_bank_account_number"></a>Keyword_australia_bank_account_number

- swift bank code
- correspondent bank
- base currency
- usa account
- holder address
- bank address
- information account
- fund transfers
- bank charges
- bank details
- banking information
- full names
- 系统


## <a name="australia-business-number"></a>澳大利亚商务号码

此敏感信息类型仅在：

- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

带可选分隔符的 11 个数字

### <a name="pattern"></a>模式

带可选分隔符的 11 个数字：

- 两个数字
- 可选连字符或空格
- 三个数字
- 可选连字符或空格
- 三个数字
- 可选连字符或空格
- 三个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_australian_business_number查找与模式匹配的内容。
- 找到来自Keywords_australian_business_number关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数Func_australian_business_number查找与模式匹配的内容。

```xml
      <!-- Australia Business Number -->
      <Entity id="76e83b3b-01ee-4530-aced-e667a6609f49" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_australian_business_number" />
          <Match idRef="Keywords_australian_business_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_australian_business_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_australia_business_number"></a>Keyword_australia_business_number

- australia business no
- 商务号码
- abn#
- businessid#
- 业务 ID
- abn
- businessno#


## <a name="australia-company-number"></a>澳大利亚公司编号

此敏感信息类型仅在：

- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

九个数字（带分隔符）

### <a name="pattern"></a>模式

带分隔符的九个数字：

- 三个数字
- 一个空格
- 三个数字
- 一个空格
- 三个数字


### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_Australian_Company_Number查找与模式匹配的内容。
- 找到来自Keyword_Australian_Company_Number关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数Func_Australian_Company_Number查找与模式匹配的内容。

```xml
      <!-- Australia Company Number -->
      <Entity id="b1fba4f7-7b3e-4bb9-8f9a-9366df604dbb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Australian_Company_Number" />
          <Match idRef="Keyword_Australian_Company_Number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_Australian_Company_Number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_australia_company_number"></a>Keyword_australia_company_number

- can
- australia company no
- australia company no#
- 澳大利亚公司编号
- 澳大利亚公司否
- 澳大利亚公司否#
- 澳大利亚公司编号


## <a name="australia-drivers-license-number"></a>澳大利亚驾驶证号码

### <a name="format"></a>格式

九个字母和数字

### <a name="pattern"></a>模式

九个字母和数字：

- 两个数字或字母 (不区分大小写) 
- 两个数字
- 五个数字或字母 (不区分大小写) 

或

- 一到两个可选字母 (不区分大小写) 
- 四到九个数字

或

- 九个数字或字母 (不区分大小写) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式 Regex_australia_drivers_license_number 找到与该模式匹配的内容。
- 找到 Keyword_australia_drivers_license_number 中的一个关键字。
- 未找到 Keyword_australia_drivers_license_number_exclusions 中的关键字。

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_australia_drivers_license_number"></a>Keyword_australia_drivers_license_number

- international driving permits
- australian automobile association
- international driving permit
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Licence
- Driver Licences
- DriversLic
- DriversLicence
- DriversLicences
- Drivers Lic
- Drivers Lics
- Drivers Licence
- Drivers Licences
- Driver'Lic
- Driver'Lics
- Driver'Licence
- Driver'Licences
- Driver' Lic
- Driver' Lics
- Driver' Licence
- Driver' Licences
- Driver'sLic
- Driver'sLics
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's Licence
- Driver's Licences
- DriverLic#
- DriverLics#
- DriverLicence#
- DriverLicences#
- Driver Lic#
- Driver Lics#
- Driver Licence#
- Driver Licences#
- DriversLic#
- DriversLics#
- DriversLicence#
- DriversLicences#
- Drivers Lic#
- Drivers Lics#
- Drivers Licence#
- Drivers Licences#
- Driver'Lic#
- Driver'Lics#
- Driver'Licence#
- Driver'Licences#
- Driver' Lic#
- Driver' Lics#
- Driver' Licence#
- Driver' Licences#
- Driver'sLic#
- Driver'sLics#
- Driver'sLicence#
- Driver'sLicences#
- Driver's Lic#
- Driver's Lics#
- Driver's Licence#
- Driver's Licences#

#### <a name="keyword_australia_drivers_license_number_exclusions"></a>Keyword_australia_drivers_license_number_exclusions

- aaa
- DriverLicense
- DriverLicenses
- Driver License
- Driver Licenses
- DriversLicense
- DriversLicenses
- Drivers License
- Drivers Licenses
- Driver'License
- Driver'Licenses
- Driver' License
- Driver' Licenses
- Driver'sLicense
- Driver'sLicenses
- Driver's License
- Driver's Licenses
- DriverLicense#
- DriverLicenses#
- Driver License#
- Driver Licenses#
- DriversLicense#
- DriversLicenses#
- Drivers License#
- Drivers Licenses#
- Driver'License#
- Driver'Licenses#
- Driver' License#
- Driver' Licenses#
- Driver'sLicense#
- Driver'sLicenses#
- Driver's License#
- Driver's Licenses#


## <a name="australia-medical-account-number"></a>澳大利亚医疗帐号

### <a name="format"></a>格式

10-11 个数字

### <a name="pattern"></a>模式

10-11 个数字：
- 第一个数字范围为 2-6
- 第九个数字是校验位
- 第十个数字是问题数字
- 第十一个数字（可选）是个人号码

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_australian_medical_account_number 找到与该模式匹配的内容。
- 找到 Keyword_Australia_Medical_Account_Number 中的一个关键字。
- 校验和通过。


```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_australia_medical_account_number"></a>Keyword_Australia_Medical_Account_Number

- bank account details
- medicare payments
- mortgage account
- bank payments
- information branch
- credit card loan
- department of human services
- local service
- 一


## <a name="australia-passport-number"></a>澳大利亚护照号码

### <a name="format"></a>格式

八个或九个字母数字字符

### <a name="pattern"></a>模式

- 一个字母 (N、E、D、F、A、C、U、X) 后跟七个数字或
- 两个字母 (PA、PB、PC、PD、PE、PF、PU、PW、PX、PZ) 后跟七个数字。

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找 `Regex_australia_passport_number` 与模式匹配的内容。
- 找到 的 `Keyword_australia_passport_number` 关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 正则表达式查找 `Regex_australia_passport_number` 与模式匹配的内容。

```xml
    <!-- Australia Passport Number -->
    <Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Match idRef="Keyword_australia_passport_number" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_australia_passport_number" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- national identity card
- travel document
- issuing authority


## <a name="australia-physical-addresses"></a>澳大利亚物理地址 

未包的命名实体，检测与来自澳大利亚的物理地址相关的模式。

### <a name="confidence-level"></a>置信度
中等


## <a name="australia-tax-file-number"></a>澳大利亚税务文件编号

### <a name="format"></a>格式

八到九个数字

### <a name="pattern"></a>模式

通常用空格显示八到九个数字，如下所示：
- 三个数字
- 可选空格
- 三个数字
- 可选空格
- 两到三个数字，其中最后一个数字是一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_australian_tax_file_number 找到与该模式匹配的内容。
- 未找到 Keyword_Australia_Tax_File_Number 或 Keyword_number_exclusions 中的关键字。
- 校验和通过。

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_australia_tax_file_number"></a>Keyword_australia_tax_file_number

- australian business number
- marginal tax rate
- medicare levy
- portfolio number
- service veterans
- withholding tax
- individual tax return
- tax file number
- tfn


## <a name="austria-drivers-license-number"></a>奥地利驾驶证号码

### <a name="format"></a>格式

八个数字（不含空格和分隔符）

### <a name="pattern"></a>模式

八个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：

- 正则表达式查找  `Regex_austria_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_austria_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Austria Driver's License Number -->
      <Entity id="682f18ce-44eb-482b-8198-2bcb96a0761e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_austria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver s_license_number

- fuhrerschein
- führerschein
- Führerscheine
- Fhrerscheinnummer
- Fhrerscheinnummern


## <a name="austria-identity-card"></a>奥地利身份证

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

字母、数字和特殊字符的 24 个字符组合

### <a name="pattern"></a>模式

24 个字符：

-  22 个字母 (不区分大小写) 数字、反斜杠、正斜杠或加号

- 两个字母 (不区分大小写) 、数字、反斜杠、正斜杠、加号或等号

### <a name="checksum"></a>校验和

不适用

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：

- 正则表达式查找  `Regex_austria_eu_national_id_card` 与模式匹配的内容。
- 找到 的  `Keywords_austria_eu_national_id_card` 关键字。

```xml
      <!-- Austria Identity Card -->
      <Entity id="5ec06c3b-007e-4820-8343-7ff73b889735" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- 标识号
- national id
- personalaus一sich österreich


## <a name="austria-passport-number"></a>奥地利护照号码

### <a name="format"></a>格式

一个字母后跟一个可选空格和七个数字

### <a name="pattern"></a>模式

一个字母、七个数字和一个空格的组合：

- 一个字母 (不区分大小写) 
- 一个 (可选) 
- 七个数字

### <a name="checksum"></a>校验和

不适用

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_austria_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_austria_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_eu_passport_date1` DD.MM.YYYY 格式的日期或找到 `Keywords_eu_passport_date` 的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_austria_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_austria_eu_passport_number` 中的关键字。

```xml
      <!-- Austria Passport Number -->
      <Entity id="1c96ae4e-303b-447d-86c7-77113ac266bf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_austria_eu_passport_number"></a>Keywords_austria_eu_passport_number

- reisepassnummer
- reisepasse
- No-Reisepass
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisep的sse

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="austria-physical-addresses"></a>奥地利物理地址

此未解包的命名实体检测与来自奥地利的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="austria-social-security-number"></a>奥地利社会保险号

### <a name="format"></a>格式

10 个数字，采用指定格式

### <a name="pattern"></a>模式

10 个数字：

- 对应于序列号的三个数字
- 一个检查数字
- 六个数字，对应于 DDMMYY (出生日期) 

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_austria_eu_ssn_or_equivalent` 查找与模式匹配的内容。
- 找到 的  `Keywords_austria_eu_ssn_or_equivalent` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_austria_eu_ssn_or_equivalent` 查找与模式匹配的内容。

```xml
      <!-- Austria Social Security Number -->
      <Entity id="6896a906-86c9-4d19-a2da-6e43ccd19b7b" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_austria_eu_telephone_number" />
            <Match idRef="Keywords_austria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- 将 ssn
- ehic number
- ehic no
- insurance code
- insurancecode#
- insurance number
- insurance no
- kr一nkassennummer
- 一名或多名
- socialsecurityno
- socialsecurityno#
- social security no
- social security number
- social security code
- sozialversicherungsnummer
- sozialversicherungsnummer#
- soziale sicherheit kein
- sozialesicherheitkein#
- ssn#
- ssn
- versicherungscode
- versicherungsnummer
- zdravstveno zavarovanje


## <a name="austria-tax-identification-number"></a>奥地利税务标识号

### <a name="format"></a>格式

九个数字，带可选连字符和正斜杠

### <a name="pattern"></a>模式

九个数字，带可选连字符和正斜杠：

- 两个数字
- 连字符 (可选) 
- 三个数字
- 可选参数， (正斜) 
- 四个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_austria_eu_tax_file_number` 查找与模式匹配的内容。
- 找到 的  `Keywords_austria_eu_tax_file_number` 关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数  `Func_austria_eu_tax_file_number` 查找与模式匹配的内容。

```xml
      <!-- Austria Tax Identification Number -->
      <Entity id="4fd58d22-af28-4451-b18a-6f722430a56d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

- österreich
- st.nr。
- steuernummer
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- tax number


## <a name="austria-value-added-tax"></a>奥地利增值税

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

11 字符字母数字模式

### <a name="pattern"></a>模式

11 字符字母数字模式：

- A 或 a
- T 或 t
- 可选空格
- U 或 u
- 可选空格
- 两个或三个数字
- 可选空格
- 四个数字
- 可选空格
- 一个或两个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_Austria_Value_Added_Tax查找与模式匹配的内容。
- 找到来自Keyword_Austria_Value_Added_Tax关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数Func_Austria_Value_Added_Tax查找与模式匹配的内容。

```xml
      <!-- Austria Value Added Tax -->
      <Entity id="b6a3eda2-c56c-4b69-a5f7-dca34db00f48" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
          <Match idRef="Keyword_Austria_Value_Added_Tax" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_austria_value_added_tax"></a>Keyword_austria_value_added_tax

- vat number
- vat#
- vat number
- vat no.
- vatno#
- 增值税编号
- vat
- mwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- vat 标识号
- atu number
- uid number


## <a name="azure-documentdb-auth-key"></a>Azure DocumentDB 身份验证密钥

### <a name="format"></a>格式

字符串"DocumentDb"后跟以下模式中列出的字符和字符串。

### <a name="pattern"></a>模式

- 字符串"DocumentDb"
- 3-200 位小写或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 大于 symbol (>) 、等号 (=) 、引号 (") 或撇号 (') 
- 86 个小写或大写字母、数字、正斜杠 (/) 或加号 (+) 
- 两个等号 (=) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式CEP_Regex_AzureDocumentDBAuthKey查找与模式匹配的内容。
- 正则表达式CEP_CommonExampleKeywords找不到与模式匹配的内容。

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

 (，从技术上说，此敏感信息类型使用正则表达式（而不是关键字列表）标识这些关键字) 

- contoso
- fabrikam
- northwind
- 沙盒
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->net


## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Azure IAAS 数据库连接字符串和 Azure SQL连接字符串

### <a name="format"></a>格式

字符串"Server"、"server"或"data source"，后跟以下模式中列出的字符和字符串，包括字符串"cloudapp.azure"。<!--no-hyperlink-->com"或"cloudapp.azure"。<!--no-hyperlink-->net"或"database.windows"。<!--no-hyperlink-->net"，字符串"Password"或"password"或"pwd"。

### <a name="pattern"></a>模式

- 字符串"Server"、"server"或"data source"
- 零到两个空格字符
- 等号 (=) 
- 零到两个空格字符
- 1-200 位小写字母或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串"cloudapp.azure"。<!--no-hyperlink-->com"、"cloudapp.azure"。<!--no-hyperlink-->net"或"database.windows"。<!--no-hyperlink-->net"
- 1-300 位小写或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串"Password"、"password"或"pwd"
- 零到两个空格字符
- 等号 (=) 
- 零到两个空格字符
- 一个或多个不是分号字符 (;) 、引号 (") 或撇 (字符) 
- 分号 (;) 、引号 (") 或撇号 () 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式CEP_Regex_AzureConnectionString查找与模式匹配的内容。
- 正则表达式CEP_CommonExampleKeywords找不到与模式匹配的内容。

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

 (，此敏感信息类型使用正则表达式（而不是关键字列表）标识这些关键字。) 

- contoso
- fabrikam
- northwind
- 沙盒
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->net


## <a name="azure-iot-connection-string"></a>Azure IoT连接字符串

### <a name="format"></a>格式

字符串"HostName"后跟模式中列出的字符和字符串，包括字符串"azure-devices"。<!--no-hyperlink-->net"和"SharedAccessKey"。

### <a name="pattern"></a>模式

- 字符串"HostName"
- 零到两个空格字符
- 等号 (=) 
- 零到两个空格字符
- 1-200 位小写字母或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串"azure-devices"。<!--no-hyperlink-->net"
- 1-200 位小写字母或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串"SharedAccessKey"
- 零到两个空格字符
- 等号 (=) 
- 零到两个空格字符
- 43 个小写或大写字母、数字、正斜杠 (/) 或加号 + (+) 
- 等号 (=) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式CEP_Regex_AzureIoTConnectionString查找与模式匹配的内容。
- 正则表达式CEP_CommonExampleKeywords找不到与模式匹配的内容。

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

此敏感信息类型使用正则表达式（而不是关键字列表）标识这些关键字。

- contoso
- fabrikam
- northwind
- 沙盒
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->net


## <a name="azure-publish-setting-password"></a>Azure 发布设置密码

### <a name="format"></a>格式

字符串"userpwd="后跟字母数字字符串。

### <a name="pattern"></a>模式

- 字符串"userpwd="
- 60 个小写字母或数字的任意组合
- 引号 (") 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式CEP_Regex_AzurePublishSettingPasswords查找与模式匹配的内容。
- 正则表达式CEP_CommonExampleKeywords找不到与模式匹配的内容。


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

此敏感信息类型使用正则表达式（而不是关键字列表）标识这些关键字。

- contoso
- fabrikam
- northwind
- 沙盒
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->net


## <a name="azure-redis-cache-connection-string"></a>Azure Redis 缓存连接字符串

### <a name="format"></a>格式

字符串"redis.cache.windows"。<!--no-hyperlink-->net"，后跟以下模式中列出的字符和字符串，包括字符串"password"或"pwd"。

### <a name="pattern"></a>模式

- 字符串"redis.cache.windows"。<!--no-hyperlink-->net"
- 1-200 位小写字母或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串"password"或"pwd"
- 零到两个空格字符
- 等号 (=) 
- 零到两个空格字符
- 43 个字符的任意组合，包括小写或大写字母、数字、正斜杠 (/) 或加号 (+) 
- 等号 (=) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式CEP_Regex_AzureRedisCacheConnectionString查找与模式匹配的内容。
- 正则表达式CEP_CommonExampleKeywords找不到与模式匹配的内容。

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

 (，从技术上说，此敏感信息类型使用正则表达式（而不是关键字列表）标识这些关键字) 

- contoso
- fabrikam
- northwind
- 沙盒
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->net


## <a name="azure-sas"></a>Azure SAS

### <a name="format"></a>格式

字符串"sig"后跟以下模式中列出的字符和字符串。

### <a name="pattern"></a>模式

- 字符串"sig"
- 零到两个空格字符
- 等号 (=) 
- 零到两个空格字符
- 小写字母、数字或百分号（小写字母、数字或百分号）之间 43-53 个字符的任意组合 (%) 
- 字符串"%3d"
- 不是小写或大写字母、数字或百分号的任何字符 (%) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式CEP_Regex_AzureSAS查找与模式匹配的内容。

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Azure 服务总线连接字符串

### <a name="format"></a>格式

字符串"EndPoint"后跟以下模式中列出的字符和字符串，包括字符串"servicebus.windows"。<!--no-hyperlink-->net"和"SharedAccesKey"。

### <a name="pattern"></a>模式

- 字符串"EndPoint"
- 零到两个空格字符
- 等号 (=) 
- 零到两个空格字符
- 1-200 位小写字母或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串"servicebus.windows"。<!--no-hyperlink-->net"
- 1-200 位小写字母或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串"SharedAccessKey"
- 零到两个空格字符
- 等号 (=) 
- 零到两个空格字符
- 43 个字符的任意组合，包括小写或大写字母、数字、正斜杠 (/) 或加号 (+) 
- 等号 (=) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式CEP_Regex_AzureServiceBusConnectionString查找与模式匹配的内容。
- 正则表达式CEP_CommonExampleKeywords找不到与模式匹配的内容。

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

 (，从技术上说，此敏感信息类型使用正则表达式（而不是关键字列表）标识这些关键字) 

- contoso
- fabrikam
- northwind
- 沙盒
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->net


## <a name="azure-storage-account-key"></a>Azure 存储帐户密钥

### <a name="format"></a>格式

字符串"DefaultEndpointsProtocol"后跟以下模式中列出的字符和字符串，包括字符串"AccountKey"。

### <a name="pattern"></a>模式

- 字符串"DefaultEndpointsProtocol"
- 零到两个空格字符
- 等号 (=) 
- 零到两个空格字符
- 1-200 位小写字母或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串"AccountKey"
- 零到两个空格字符
- 等号 (=) 
- 零到两个空格字符
- 小写或大写字母、数字、正斜杠 (/) 或加号 (+) 
- 两个等号 (=) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式CEP_Regex_AzureStorageAccountKey查找与模式匹配的内容。
- 正则表达式CEP_AzureEmulatorStorageAccountFilter找不到与模式匹配的内容。
- 正则表达式CEP_CommonExampleKeywords找不到与模式匹配的内容。

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_azure_emulator_storage_account_filter"></a>CEP_azure_emulator_storage_account_filter

 (，此敏感信息类型使用正则表达式（而不是关键字列表）标识这些关键字。) 

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

 (，此敏感信息类型使用正则表达式（而不是关键字列表）标识这些关键字。) 

- contoso
- fabrikam
- northwind
- 沙盒
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->net


## <a name="azure-storage-account-key-generic"></a>Azure 存储常规 (帐户) 

### <a name="format"></a>格式

86 个小写或大写字母、数字、正斜杠 (/) 或加号 (+) 的任意组合，前面或后跟以下模式中列出的字符。

### <a name="pattern"></a>模式

- 从零到大于 symbol (>) 、撇号 (') 、等号 (=) 、引号 (") 或数字符号 (#) 
- 小写或大写字母、数字、正斜杠 (/) 或加号 (+) 
- 两个等号 (=) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式CEP_Regex_AzureStorageAccountKeyGeneric查找与模式匹配的内容。

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```


## <a name="belgium-drivers-license-number"></a>比利时驾驶证号码

### <a name="format"></a>格式

不带空格和分隔符的 10 个数字

### <a name="pattern"></a>模式

10 个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_belgium_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或 `Keywords_eu_driver's_license_number` `Keywords_belgium_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Belgium Driver's License Number -->
      <Entity id="d89fd329-9324-433c-b687-2c37bd5166f3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_belgium_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_belgium_eu_drivers_license_number"></a>Keywords_belgium_eu_driver s_license_number

- rijbewijs
- rijbewijsnummer
- führerschein
- führerscheinnummer
- füehrerscheinnummer
- fuhrerschein
- fuehrerschein
- fuhrerscheinnummer
- fuehrerscheinnummer
- permis de conduire
- numéro permis conduire


## <a name="belgium-national-number"></a>比利时国家号码

### <a name="format"></a>格式

11 个数字加上可选的分隔符

### <a name="pattern"></a>模式

11 个数字加分隔符：
- YY 格式的六个数字和两个可选句点。出生日期的 MM.DD
- 点、短划线、空格中的可选分隔符
- 三个连续的数字 (男性为奇数，即使对于男性) 
- 点、短划线、空格中的可选分隔符
- 两个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_belgium_national_number 找到与该模式匹配的内容。
- 找到 Keyword_belgium_national_number 中的一个关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数 Func_belgium_national_number 找到与该模式匹配的内容。
- 校验和通过。

```xml
<!-- Belgium National Number -->
       <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_national_number" />
          <Match idRef="Keyword_belgium_national_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_belgium_national_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- belasting aantal
- bnn#
- bnn
- carte d'identité
- identifiant national
- identifiantnational#
- identificatie
- identification
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identit一
- identit一skaart
- identity
- inscription
- national number
- national register
- nationalnumber#
- nationalnumber
- nif#
- nif
- numéro d'assuré
- numéro de registre national
- numéro de sécurité
- numéro d'identification
- numéro d'immatriculation
- numéro national
- numéronational#
- 个人 ID 号
- personalaus一s
- personalidnumber#
- registratie
- 注册
- registrationsnumme
- registrierung
- social security number
- ssn#
- ssn
- steuernummer
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="belgium-passport-number"></a>比利时护照号码

### <a name="format"></a>格式

两个字母后跟 6 个数字，没有空格或分隔符

### <a name="pattern"></a>模式

两个字母，后跟六个数字

### <a name="checksum"></a>校验和

不适用

### <a name="definition"></a>定义

 DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_belgium_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_belgium_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_eu_passport_date2` 格式为 DD MM YY 的日期或 `Keywords_eu_passport_date` 找到的 `Keywords_belgium_eu_passport_number` 关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_belgium_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_belgium_eu_passport_number` 中的关键字。

```xml
      <!-- Belgium Passport Number -->
      <Entity id="d7b1315b-21ca-4774-a32a-596010ff78fd" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
            <Match idRef="Keywords_belgium_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- numéro passeport
- paspoort nr
- paspoort-nr
- paspoortnummer
- paspoortnummers
- Passeport carte
- Passeport livre
- Pass-Nr
- Passnummer
- reisepass kein

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="belgium-physical-addresses"></a>比利时物理地址

此未发包的命名实体检测与比利时的物理地址相关的模式。

### <a name="confidence-level"></a>置信度

中


## <a name="belgium-value-added-tax-number"></a>比利时增值税编号

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

12 字符字母数字模式

### <a name="pattern"></a>模式

12 字符字母数字模式：

- 字母 B 或 b
- 字母 E 或 e
- 数字 0
- 从 1 到 9 的数字
- 可选点或连字符或空格
- 四个数字
- 可选点或连字符或空格
- 四个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_belgium_value_added_tax_number查找与模式匹配的内容。
- 找到来自Keywords_belgium_value_added_tax_number关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数Func_belgium_value_added_tax_number查找与模式匹配的内容。

```xml
      <!-- Belgium Value Added Tax Number -->
      <Entity id="85b5b3c3-f2de-4ae8-ac46-fd3cb38bf9ed" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
          <Match idRef="Keywords_belgium_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
        </Pattern>
      </Entity>
    </Version>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_belgium_value_added_tax_number"></a>Keyword_belgium_value_added_tax_number

- n？ tva
- vat number
- vat no
- numéro t.v.a
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- btw
- btw#
- vat#


## <a name="blood-test-terms"></a>检测词

此未解包的命名实体检测与检测相关的术语，例如 *hCG*。 它仅支持英语术语。

### <a name="confidence-level"></a>置信度

高

## <a name="brand-medication-names"></a>品牌品牌名称

此未解包的命名实体可检测品牌品牌的名称，如 *Tylenol*。 它仅支持英语术语。

### <a name="confidence-level"></a>置信度

高


## <a name="brazil-cpf-number"></a>巴西 CPF 号码

### <a name="format"></a>格式

11 个数字（包括校验位），可以格式化，也可以非格式化

### <a name="pattern"></a>模式

格式化：
- 三个数字
- a period
- 三个数字
- a period
- 三个数字
- 连字符
- 两个数字是检查数字

无格式：
- 11 个数字，其中最后两个数字是校验位

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_brazil_cpf 找到与该模式匹配的内容。
- 找到 Keyword_brazil_cpf 中的一个关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_brazil_cpf 找到与该模式匹配的内容。
- 校验和通过。

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_brazil_cpf"></a>Keyword_brazil_cpf

- CPF
- 标识
- 注册
- 收入
- Cadastro de Pessoas Físicas
- 中年
- Identificação
- Inscrição
- Receita


## <a name="brazil-legal-entity-number-cnpj"></a>CNPJ (巴西法律) 

### <a name="format"></a>格式

14 个数字（包括注册号、分行号码和校验位），再加上分隔符

### <a name="pattern"></a>模式

14 个数字，再加上分隔符：

- 两个数字
- a period
- 三个数字
- a period
- 三个数字 (前八个数字是注册号码) 
- 正斜杠
- 四位数分支号码
- 连字符
- 两个数字是检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_brazil_cnpj 找到与该模式匹配的内容。
- 找到 Keyword_brazil_cnpj 中的一个关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_brazil_cnpj 找到与该模式匹配的内容。
- 校验和通过。

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_brazil_cnpj"></a>Keyword_brazil_cnpj

- CNPJ
- CNPJ/MF
- CNPJ-MF
- National Registry of Legal Entities
- Taxpayers Registry
- Legal entity
- Legal entities
- Registration Status
- 商业版
- Company
- CNPJ
- Cadastro Nacional da Pessoa Jurídica
- Cadastro Geral de Contribuintes
- CGC
- Pessoa jurídica
- Pessoas jurídicas
- Situação cadastral
- Inscrição
- Empresa


## <a name="brazil-national-identification-card-rg"></a>巴西国家身份证 (RG) 

### <a name="format"></a>格式

Registro Geral (旧格式) ：九个数字

Registro de Identidade (RIC)  (新格式) ：11 个数字

### <a name="pattern"></a>模式

Registro Geral（旧格式）：
- 两个数字
- a period
- 三个数字
- a period
- 三个数字
- 连字符
- 一个数字，是一个检查数字

Registro de Identidade (RIC)  (新) ：
- 10 个数字
- 连字符
- 一个数字，是一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_brazil_rg 找到与该模式匹配的内容。
- 找到 Keyword_brazil_rg 中的一个关键字。
- 校验和通过。


```xml
      <!-- Brazil National ID Card (RG) -->
      <Entity id="486de900-db70-41b3-a886-abdf25af119c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_brazil_rg" />
          <Match idRef="Keyword_brazil_rg" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_brazil_rg"></a>Keyword_brazil_rg

- Cédula de identidade
- identity card
- national id
- número de rregistro
- registro de Iidentidade
- registro geral
- RG (关键字区分大小写) 
- RIC (关键字区分大小写) 


## <a name="brazil-physical-addresses"></a>巴西物理地址

此未解包的命名实体检测与来自巴西的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中

## <a name="bulgaria-drivers-license-number"></a>保加利亚驾驶证号码

### <a name="format"></a>格式

九个数字，不带空格和分隔符

### <a name="pattern"></a>模式

九个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_bulgaria_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_bulgaria_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Bulgaria Driver's License Number -->
      <Entity id="66d39258-94c2-43b2-804b-aa312258e54b" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver s_license_number

- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка
- шофьорски книжки


## <a name="bulgaria-passport-number"></a>保加利亚护照号码

### <a name="format"></a>格式

九个数字，不带空格和分隔符

### <a name="pattern"></a>模式

九个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_bulgaria_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_bulgaria_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_eu_passport_date1` DD.MM.YYYY 格式的日期或找到 `Keywords_eu_passport_date` 的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_bulgaria_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_bulgaria_eu_passport_number` 中的关键字。

```xml
      <!-- Bulgaria Passport Number -->
      <Entity id="f7172b82-c588-4216-845e-4e54e397f29a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- номер на паспорта
- номер на паспорт
- 均？

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="bulgaria-physical-addresses"></a>保加利亚物理地址

此未解包的命名实体检测与保加利亚的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中

## <a name="bulgaria-uniform-civil-number"></a>保加利亚统一编号
此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

不带空格和分隔符的 10 个数字

### <a name="pattern"></a>模式

不带空格和分隔符的 10 个数字

- 六个数字，对应于 YYMMDD (出生日期) 
- 两个数字，对应于出生日期
- 对应于性别的一个数字：男性的偶数位数和男性的奇数
- 一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_bulgaria_eu_national_id_card` 查找与模式匹配的内容。
- 找到 的  `Keywords_bulgaria_eu_national_id_card` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_bulgaria_eu_national_id_card` 查找与模式匹配的内容。

```xml
      <!-- Bulgaria Uniform Civil Number -->
      <Entity id="100d58b1-0a35-4fb1-aa89-e4a86fb53fcc" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_bulgaria_eu_telephone_number" />
            <Match idRef="Keywords_bulgaria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_bulgaria_eu_national_id_card"></a>Keywords_bulgaria_eu_national_id_card

- bnn#
- bnn
- bucn#
- bucn
- edinen grazhski nomer
- egn#
- egn
- identification number
- national id
- national number
- nationalnumber#
- nationalnumber
- 个人 ID
- personal no
- 个人编号
- personalidnumber#
- social security number
- ssn#
- ssn
- uniform uniform uniform id
- uniform uniform uniform no
- uniform uniform number
- uniformcivilno#
- uniformcivilno
- uniformcivilnumber#
- uniformcivilnumber
- 唯一公民编号
- егн#
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- 2013 年 1 月 2 日
- 2016 年 4 月граждански граждански id
- униформ граждански не
- униформ граждански номер
- униформгражданскиid#
- униформгражданскине.#


## <a name="canada-bank-account-number"></a>加拿大银行帐号

### <a name="format"></a>格式

7 个或 12 个数字

### <a name="pattern"></a>模式

加拿大银行帐号是 7 个或 12 个数字。

加拿大银行帐户的银行代号是：
- 五个数字
- 连字符
- 三个数字 OR
- 零"0"
- 八个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。
- 找到 Keyword_canada_bank_account_number 中的一个关键字。
- 正则表达式 Regex_canada_bank_account_transit_number 找到与该模式匹配的内容。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。
- 找到 Keyword_canada_bank_account_number 中的一个关键字。

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_canada_bank_account_number"></a>Keyword_canada_bank_account_number

- canada savings bonds
- canada revenue agency
- canadian financial institution
- direct deposit form
- canadian citizen
- legal representative
- notary public
- commissioner for oaths
- child care benefit
- universal child care
- canada child tax benefit
- income tax benefit
- harmonized sales tax
- social insurance number
- income tax refund
- child tax benefit
- territorial payments
- institution number
- deposit request
- banking information
- direct deposit


## <a name="canada-drivers-license-number"></a>加拿大驾驶证号码

### <a name="format"></a>格式

因省而异

### <a name="pattern"></a>模式

各种模式涵盖：
- 省/市/市
- British Columbia
- 马尼托巴
- New Brunswick
- Newfoundland/Labrador
- Nova Scotia
- On一
- Prince Edward Island
- 百里达
- Saskatchewan

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_[province_name]_drivers_license_number 找到与该模式匹配的内容。
- 找到 Keyword_[province_name]_drivers_license_name 中的一个关键字。
- 找到 Keyword_canada_drivers_license 中的一个关键字。

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_[province_name]_drivers_license_name

- 省/市/自治区的缩写，例如 AB
- 省名称，例如 Alberta

#### <a name="keyword_canada_drivers_license"></a>Keyword_canada_drivers_license

- DL
- DLS
- CDL
- CDLS
- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Lics
- Driver License
- Driver Licenses
- Driver Licence
- Driver Licences
- DriversLic
- DriversLics
- DriversLicence
- DriversLicences
- DriversLicense
- DriversLicenses
- Drivers Lic
- Drivers Lics
- Drivers License
- Drivers Licenses
- Drivers Licence
- Drivers Licences
- Driver'Lic
- Driver'Lics
- Driver'License
- Driver'Licenses
- Driver'Licence
- Driver'Licences
- Driver' Lic
- Driver' Lics
- Driver' License
- Driver' Licenses
- Driver' Licence
- Driver' Licences
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Driver'sLicenses
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's License
- Driver's Licenses
- Driver's Licence
- Driver's Licences
- Permis de Conduire
- id
- ids
- idcard number
- idcard numbers
- idcard #
- idcard #s
- idcard card
- idcard cards
- idcard
- identification number
- identification numbers
- identification #
- identification #s
- identification card
- identification cards
- identification
- DL#
- DLS#
- CDL#
- CDLS#
- DriverLic#
- DriverLics#
- DriverLicense#
- DriverLicenses#
- DriverLicence#
- DriverLicences#
- Driver Lic#
- Driver Lics#
- Driver License#
- Driver Licenses#
- Driver License#
- Driver Licences#
- DriversLic#
- DriversLics#
- DriversLicense#
- DriversLicenses#
- DriversLicence#
- DriversLicences#
- Drivers Lic#
- Drivers Lics#
- Drivers License#
- Drivers Licenses#
- Drivers Licence#
- Drivers Licences#
- Driver'Lic#
- Driver'Lics#
- Driver'License#
- Driver'Licenses#
- Driver'Licence#
- Driver'Licences#
- Driver' Lic#
- Driver' Lics#
- Driver' License#
- Driver' Licenses#
- Driver' Licence#
- Driver' Licences#
- Driver'sLic#
- Driver'sLics#
- Driver'sLicense#
- Driver'sLicenses#
- Driver'sLicence#
- Driver'sLicences#
- Driver's Lic#
- Driver's Lics#
- Driver's License#
- Driver's Licenses#
- Driver's Licence#
- Driver's Licences#
- Permis de Conduire#
- id#
- ids#
- idcard card#
- idcard cards#
- idcard#
- identification card#
- identification cards#
- identification#


## <a name="canada-health-service-number"></a>加拿大卫生服务号码

### <a name="format"></a>格式

 10 个数字

### <a name="pattern"></a>模式

10 个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式 Regex_canada_health_service_number 找到与该模式匹配的内容。
- 找到 Keyword_canada_health_service_number 中的一个关键字。

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_canada_health_service_number"></a>Keyword_canada_health_service_number

- personal health number
- patient information
- health services
- speciality services
- automobile accident
- patient hospital
- 一些
- workers compensation
- 残障


## <a name="canada-passport-number"></a>加拿大护照号码

### <a name="format"></a>格式

两个小写字母后跟六个数字

### <a name="pattern"></a>模式

两个小写字母后跟六个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式 Regex_canada_passport_number 找到与该模式匹配的内容。
- 找到来自Keyword_canada_passport_number或Keyword_passport关键字。

```xml
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_canada_passport_number"></a>Keyword_canada_passport_number

- canadian citizenship
- canadian passport
- passport application
- passport photos
- certified translator
- canadian citizens
- processing times
- renewal application

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport #
- Passport#
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポのnum
- パスポート＃
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport#
- PasseportNon
- Passeportn °


## <a name="canada-personal-health-identification-number-phin"></a>加拿大个人健康标识号 (PHIN) 

### <a name="format"></a>格式

九个数字

### <a name="pattern"></a>模式

九个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式 Regex_canada_phin 找到与该模式匹配的内容。
- 至少找到了两个来自Keyword_canada_phin或Keyword_canada_provinces关键字。

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_canada_phin"></a>Keyword_canada_phin

- social insurance number
- health information act
- income tax information
- manitoba health
- health registration
- prescription purchases
- benefit eligibility
- personal health
- power of attorney
- registration number
- personal health number
- practitioner referral
- wellness professional
- patient referral
- health and wellness

#### <a name="keyword_canada_provinces"></a>Keyword_canada_provinces

- Nunavut
- 百里达
- Northwest Territories
- On一
- British Columbia
- 省/市/市
- Saskatchewan
- 马尼托巴
- Yukon
- Newfoundland and Labrador
- New Brunswick
- Nova Scotia
- Prince Edward Island
- 加拿大


## <a name="canada-physical-addresses"></a>加拿大物理地址

此未解包的命名实体检测与来自加拿大的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="canada-social-insurance-number"></a>加拿大社会保险号码

### <a name="format"></a>格式

九个数字（可选连字符或空格）

### <a name="pattern"></a>模式

格式化：
- 三个数字
- 连字符或空格
- 三个数字
- 连字符或空格
- 三个数字

无格式：九个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_canadian_sin 找到与该模式匹配的内容。
- 至少以下两种模式：
    - 找到 Keyword_sin 中的一个关键字。
    - 找到 Keyword_sin_collaborative 中的一个关键字。
    - 函数 Func_eu_date 找到正确日期格式的日期。
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_unformatted_canadian_sin 找到与该模式匹配的内容。
- 找到 Keyword_sin 中的一个关键字。
- 校验和通过。

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_sin"></a>Keyword_sin

- sin
- social insurance
- numero d'assurance sociale
- sins
- ssn
- ssns
- social security
- numero d'assurance social
- national identification number
- national id
- sin#
- soc ins
- social ins

#### <a name="keyword_sin_collaborative"></a>Keyword_sin_collaborative

- driver's license
- drivers license
- driver's licence
- drivers licence
- DOB
- 出生日期
- Birthday
- Date of Birth


## <a name="chile-identity-card-number"></a>智利身份证号码

### <a name="format"></a>格式

七到八个数字加上分隔符一个检查数字或字母

### <a name="pattern"></a>模式

七到八个数字加分隔符：
- 一到两个数字
- 可选时间段
- 三个数字
- 可选时间段
- 三个数字
- 短划线
- 一个数字或 (不区分大小写) 一个数字或字母，这是一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_chile_id_card 找到与该模式匹配的内容。
- 找到 Keyword_chile_id_card 中的一个关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_chile_id_card 找到与该模式匹配的内容。
- 校验和通过。

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_chile_id_card"></a>Keyword_chile_id_card

- cédula de identidad
- identificación
- national identification
- national identification number
- national id
- número de identificación nacional
- rol único nacional
- rol único tribu一
- RUN
- RUT
- tarjeta de identificación
- Rol Unico Nacional
- Rol Unico Tribu一
- RUN#
- RUT#
- nationaluniqueroleID#
- nacional identidad
- número identificación
- identidad número
- numero identificacion
- identidad numero
- 百分卡标识否。
- 高能标识号
- 百分卡标识#
- 唯一税务注册表
- 唯一的三元角色
- 唯一税务角色
- 唯一的三元数
- 唯一国家/区号
- 唯一的国家角色
- 国家/地区唯一角色
- 智利标识否。
- 智利标识号
- 智利标识#
- R.U.T
- R.U.N


## <a name="china-resident-identity-card-prc-number"></a>中国居民身份证 (中国) 号码

### <a name="format"></a>格式

18 个数字

### <a name="pattern"></a>模式

18 个数字：
- 六个数字，表示地址代码
- 八个数字，格式为 YYYYMMDD，表示出生日期
- 三个数字，表示订单代码
- 一个数字，是一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_china_resident_id 找到与该模式匹配的内容。
- 找到 Keyword_china_resident_id 中的一个关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_china_resident_id 找到与该模式匹配的内容。
- 校验和通过。

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

### <a name="keyword_china_resident_id"></a>Keyword_china_resident_id

- Resident Identity Card
- 中国
- National Identification Card
- 身份证
- 居民 身份证
- 居民身份证
- 鉴定
- 身分證
- 居民身份證
- 鑑定


## <a name="credit-card-number"></a>信用卡号

### <a name="format"></a>格式

14 到 19 个数字，可以格式化或无格式 (ddddddd) 且必须通过 Luhn 测试。

### <a name="pattern"></a>模式

检测来自全球所有主要品牌的卡，包括 Visa、MasterCard、Discover Card、JCB、American Express、名片、第二者卡、Rupay 和 China UnionPay。

### <a name="checksum"></a>校验和

是，Luhn 检查

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_credit_card 找到与该模式匹配的内容。
- 下列其中一项为真：
    - 找到 Keyword_cc_verification 中的一个关键字。
    - 找到 Keyword_cc_name 中的一个关键字。
    - 函数 Func_expiration_date 找到正确日期格式的日期。
- 校验和通过。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数 Func_credit_card 找到与该模式匹配的内容。
- 校验和通过。

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_cc_verification"></a>Keyword_cc_verification

- card verification
- card identification number
- cvn
- cid
- cvc2
- cvv2
- pin block
- security code
- security number
- security no
- issue number
- issue no
- cryptogramme
- numéro de sécurité
- numero de securite
- kreditittenprüfnummer
- kreditittenprufnummer
- prüfziffer
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- cod。 sicurezza
- cod sicurezza
- n autorizzazione
- código
- codigo
- cod。 seg
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- 
cód. segurança
- cod. seguranca

- cod. segurança

- cód。 seguranca
- cód segurança
- cod seguranca
- cod segurança
- cód seguranca
- número de verificação
- numero de verificacao
- ablauf
- gültig bis
- gültigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadenza
- data scad
- fecha de expiracion
- fecha de venc
- vencimiento
- válido hasta
- valido hasta
- vto
- data de expiração
- data de expiracao
- data em que expira
- validade
- valor
- vencimento
- transaction
- 事务编号
- 参考编号
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- amex
- american express
- americanexpress
- americano espresso
- Visa
- mastercard
- Master Card
- mc
- mastercards
- master cards
- diner's Club
- diners club
- dinersc一
- discover
- discover card
- discovercard
- discover cards
- JCB
- BrandSmart
- japanese card bureau
- carte blanche
- carteblanche
- credit card
- cc#
- cc#：
- expiration date
- exp date
- expiry date
- date d’expiration
- date d'exp
- date expiration
- bank card
- bankcard
- card number
- card num
- cardnumber
- cardnumbers
- card numbers
- creditcard
- credit cards
- creditcards
- ccn
- card holder
- 将
- card holders
- 将
- check card
- checkcard
- check cards
- checkcards
- debit card
- debitcard
- debit cards
- debitcards
- atm card
- atmcard
- atm cards
- atmcards
- enroute
- en route
- card type
- Cardmember Acct
- cardmember 帐户
- Cardno
- 公司卡
- 公司卡
- 卡片类型
- card account number
- card 成员帐户
- Cardmember Acct。
- card no.
- card no
- card number
- carte bancaire
- carte de crédit
- carte de credit
- numéro de carte
- numero de carte
- nº de la carte
- nº de carte
- kreditkrte
- karte
- karteninhaber
- karteninhabers
- kredititteninhaber
- kredit功能teninstitut
- kredittentyp
- eigentümername
- kartennr
- kartennummer
- kreditittennummer
- kreditkrten-nummer
- carta di credito
- carta credito
- n. carta
- n carta
- nr. carta
- nr carta
- numero carta
- numero della carta
- numero di carta
- tarjeta credito
- tarjeta de credito
- tarjeta crédito
- tarjeta de crédito
- tarjeta de atm
- tarjeta atm
- tarjeta debito
- tarjeta de debito
- tarjeta débito
- tarjeta de débito
- nº de tarjeta
- 不。 de tarjeta
- no de tarjeta
- numero de tarjeta
- número de tarjeta
- tarjeta no
- tarjetahabiente
- cartão de crédito
- cartão de credito
- cartao de crédito
- cartao de credito
- cartão de débito
- cartao de débito
- cartão de debito
- cartao de debito
- débito automático
- debito automatico
- número do cartão
- numero do cartão
- número do cartao
- numero do cartao
- número de cartão
- numero de cartão
- número de cartao
- numero de cartao
- nº do cartão
- nº do cartao
- n？ do cartão
- no do cartão
- no do cartao
- 不。 do cartão
- no. do cartao

- rupay
- union pay
- unionpay
- 第二者
- 第二方
- クレジットカード番号
- クレジットカードナンバー
- クレジットカード＃
- クレジットカード
- クレジット
- クレカ
- カード番号
- カードナンバー
- カード＃
- アメックス
- アメリカンエクスプレス
- アメリカン エクスプレス
- Visaカド
- Visa カド
- マスターカード
- マスター カード
- マスター
- ダイナースクラブ
- ダイナース クラブ
- ダイナース
- 有効期限
- 期限
- キャッシュカード
- キャッシュ カード
- カード名義人
- カードの名義人
- カードの名義
- デビット カード
- デビットカード
- 中国银联
- 银联


## <a name="croatia-drivers-license-number"></a>克罗地亚驾驶证号码

### <a name="format"></a>格式

八个数字（不含空格和分隔符）

### <a name="pattern"></a>模式

八个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：

- 正则表达式查找  `Regex_croatia_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或 `Keywords_eu_driver's_license_number` `Keywords_croatia_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Croatia Driver's License Number -->
      <Entity id="005b3ef1-47dd-4e68-bb02-c6db484d00f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_croatia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver s_license_number

- voza-ka dozvola
- vozazake dozvole


## <a name="croatia-identity-card-number"></a>克罗地亚身份证号
此实体包含在欧盟国家标识号敏感信息类型中。 它作为独立的敏感信息类型实体提供。

### <a name="format"></a>格式

九个数字

### <a name="pattern"></a>模式

九个连续的数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_croatia_id_card 找到与该模式匹配的内容。
- 找到 Keyword_croatia_id_card 中的一个关键字。

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- majstorski broj gragragraana
- master citizen number
- nacionalni identifikacijski broj
- national identification number
- oib#
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- 个人标识号
- 一些项目
- identzni identifikacijski broj
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="croatia-passport-number"></a>克罗地亚护照号码

### <a name="format"></a>格式

九个数字，不带空格和分隔符

### <a name="pattern"></a>模式

九个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_croatia_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_croatia_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_eu_passport_date1` DD.MM.YYYY 格式的日期或找到 `Keywords_eu_passport_date` 的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_croatia_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_croatia_eu_passport_number` 中的关键字。

```xml
      <!-- Croatia Passport Number -->
      <Entity id="7d7a729d-32d8-4204-8d01-d5e6a6c25581" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- broj putov一
- br. Putov一
- br putov一

## <a name="croatia-personal-identification-oib-number"></a>克罗地亚个人标识 (OIB) 号

### <a name="format"></a>格式

11 个数字

### <a name="pattern"></a>模式

11 个数字：
- 10 个数字
- 最终数字是一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_croatia_oib_number 找到与该模式匹配的内容。
- 找到来自Keywords_croatia_eu_tax_file_number关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_croatia_oib_number 找到与该模式匹配的内容。
- 校验和通过。

```xml
      <!-- Croatia Personal Identification (OIB) Number -->
      <Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_oib_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_oib_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- majstorski broj gragragraana
- master citizen number
- nacionalni identifikacijski broj
- national identification number
- oib#
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- 个人标识号
- 一些项目
- identzni identifikacijski broj
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="croatia-physical-addresses"></a>克罗地亚物理地址

此未解包的命名实体检测与克罗地亚的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="cyprus-drivers-license-number"></a>塞浦路斯驾驶证号码

### <a name="format"></a>格式

不带空格和分隔符的 12 个数字

### <a name="pattern"></a>模式

12 个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_cyprus_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_cyprus_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Cyprus Driver's License Number -->
      <Entity id="356fa104-f9ac-4aff-a0e4-2e6e65ea06c4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver s_license_number

- άδεια οδήγησης
- αριθμό άδειας οδήγησης
- άδειες οδήγησης


## <a name="cyprus-identity-card"></a>塞浦路斯身份证

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

不带空格和分隔符的 10 个数字

### <a name="pattern"></a>模式

10 个数字

### <a name="checksum"></a>校验和

不适用

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_cyprus_eu_national_id_card` 与模式匹配的内容。
- 找到 的  `Keywords_cyprus_eu_national_id_card` 关键字。

```xml
      <!-- Cyprus Identity Card -->
      <Entity id="3ba8afe5-7a6c-4929-8247-0001b6878438" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

- id card number
- 标识卡号
- kim且 karti
- national identification number
- 个人 ID 号
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>塞浦路斯护照号码

### <a name="format"></a>格式

一个字母后跟 6-8 个数字，无空格或分隔符

### <a name="pattern"></a>模式

一个字母后跟六到八个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_cyprus_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_cyprus_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_cyprus_eu_passport_date` DD/MM/YYYY 格式的日期或找到 `Keywords_cyprus_eu_passport_date` 的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_cyprus_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_cyprus_eu_passport_number` 中的关键字。

```xml
      <!-- Cyprus Passport Number -->
      <Entity id="9193e2e8-7f8c-43c1-a274-ac40d651936f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_cyprus_eu_passport_date" />
            <Match idRef="Keywords_cyprus_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_cyprus_eu_passport_number"></a>Keywords_cyprus_eu_passport_number

- αριθμό διαβατηρίου
- pasaportu
- Αριθμός Διαβατηρίου
- κυπριακό διαβατήριο
- διαβατήριο#
- διαβατήριο
- αριθμός διαβατηρίου
- Pasaport Kimli以i
- pasaport nu一起
- Pasaport 否。
- Αρ. Διαβατηρίου

#### <a name="keywords_cyprus_eu_passport_date"></a>Keywords_cyprus_eu_passport_date

- 到期时间
- 颁发于


## <a name="cyprus-physical-addresses"></a>塞浦路斯物理地址

此未解包的命名实体检测与来自塞浦路斯的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中

## <a name="cyprus-tax-identification-number"></a>塞浦路斯税务标识号
此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

指定模式中的八个数字和一个字母

### <a name="pattern"></a>模式

八个数字和一个字母：

- "0"或"9"
- 七个数字
- 一个字母 (不区分大小写) 

### <a name="checksum"></a>校验和

不适用

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_cyprus_eu_tax_file_number` 查找与模式匹配的内容。
- 找到 的  `Keywords_cyprus_eu_tax_file_number` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_cyprus_eu_tax_file_number` 查找与模式匹配的内容。

```xml
      <!-- Cyprus Tax Identification Number -->
      <Entity id="40e64bd9-55f3-4a09-9bd6-1db18dced9dd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

- tax id
- 税务识别代码
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tic#
- tic
- tin id
- tin no
- tin#
- vergi kim且 kodu
- vergi kim且 nu一ss
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>捷克驾驶证号码

### <a name="format"></a>格式

两个字母后跟六个数字

### <a name="pattern"></a>模式

八个字母和数字：

- 字母"E" (不区分大小写) 
- 一个字母
- 一个 (可选) 
- 六个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_czech_republic_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_czech_republic_eu_driver's_license_number` 中的关键字。

```xml
      <Entity id="86b40d3b-d8ea-4c36-aab0-ef9416a6769c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver s_license_number

- úidiúskú prúkaz
- üidiidiské prükazy
- ííslo íidiíského przukazu
- íísla íidiískích príkaz≥


## <a name="czech-passport-number"></a>捷克护照号码

### <a name="format"></a>格式

八个数字，不带空格或分隔符

### <a name="pattern"></a>模式

八个数字，不带空格或分隔符

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_czech_republic_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_czech_republic_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_eu_passport_date1` DD.MM.YYYY 格式的日期或找到 `Keywords_eu_passport_date` 的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_czech_republic_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_czech_republic_eu_passport_number` 中的关键字。

```xml
      <!-- Czech Republic Passport Number -->
      <Entity id="7bcd8ce8-5e92-4bbe-bc92-fa669f0369fa" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- cestovní pas
- ííslo pasu
- cestovní pasu
- passeport no
- íísla pasu

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="czech-personal-identity-number"></a>捷克个人标识号

### <a name="format"></a>格式

九个数字，带可选正斜杠 (旧格式) 10 个数字，带可选正斜杠 (新格式) 

### <a name="pattern"></a>模式

九个数字 (旧格式) ：
- 六个数字，表示出生日期
- 可选正斜杠
- 三个数字

10 个数字 (新格式) ：
- 六个数字，表示出生日期
- 可选正斜杠
- 四个数字，其中最后一个数字是一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：

- 函数 Func_czech_id_card 找到与该模式匹配的内容。
- 找到 Keyword_czech_id_card 中的一个关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：

- 函数Func_czech_id_card_new_format查找与模式匹配的内容。
- 校验和通过。

```xml
<!-- Czech Personal Identity Number -->
      <!-- Czech Personal Identity Number -->
      <Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_id_card" />
          <Match idRef="Keyword_czech_id_card" />
        </Pattern>
        <Version minEngineVersion="15.20.3000.000">
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Func_czech_id_card_new_format" />
          </Pattern>
        </Version>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_czech_id_card"></a>Keyword_czech_id_card

- birth number
- 捷克共和国 ID
- czechidno#
- daíové ííslo
- identifíní ííslo
- identity no
- 标识号
- identityno#
- identityno
- insurance number
- national identification number
- nationalnumber#
- national number
- osobní ííslo
- personalidnumber#
- 个人 ID 号
- 个人标识号
- 个人编号
- pid#
- pid
- pojiítíní ííslo
- r以
- rodne cislo
- rodné ííslo
- ssn
- ssn#
- social security number
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- 唯一标识号


## <a name="czech-republic-physical-addresses"></a>捷克共和国物理地址

此未解包的命名实体检测与来自捷克共和国的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中

## <a name="denmark-drivers-license-number"></a>丹麦驾驶证号码

### <a name="format"></a>格式

八个数字（不含空格和分隔符）

### <a name="pattern"></a>模式

八个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_denmark_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_denmark_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Denmark Driver's License Number -->
      <Entity id="98a95812-6203-451a-a220-d39870ebef0e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_denmark_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver s_license_number

- kørekort
- kørekortnummer


## <a name="denmark-passport-number"></a>丹麦护照号码

### <a name="format"></a>格式

九个数字，不带空格和分隔符

### <a name="pattern"></a>模式

九个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_denmark_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_denmark_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_eu_passport_date2` 格式为 DD MM YY 的日期或找到 `Keywords_eu_passport_date` 的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_denmark_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_denmark_eu_passport_number` 中的关键字。

```xml
      <!-- Denmark Passport Number -->
      <Entity id="25e8c47e-e6fe-4884-a211-74898f8c0196" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- Passeport n°
- pasnumre

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="denmark-personal-identification-number"></a>丹麦个人标识号

### <a name="format"></a>格式

10 个数字，包含连字符

### <a name="pattern"></a>模式

10 个数字：
- 六个数字，格式为 DDMMYY，表示出生日期
- 可选空格或连字符
- 四个数字，其中最后一个数字是一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式Func_denmark_eu_tax_file_number查找与模式匹配的内容。
- 找到 Keyword_denmark_id 中的一个关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 正则表达式Func_denmark_eu_tax_file_number查找与模式匹配的内容。
- 校验和通过。

```xml
<!-- Denmark Personal Identification Number -->
    <!-- Denmark Personal Identification Number -->
      <Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keyword_denmark_id" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- centrale personregister
- civilt registreringssystem
- cpr
- cpr#
- gesundheitshete nummer
- gesundheitsversicherungungte nummer
- health card
- 健康保险卡号
- 健康保险号码
- identification number
- identifikationsnummer
- identifikationsnummer#
- 标识号
- kr一nkassennummer
- nationalid#
- nationalnumber#
- national number
- personalidnumber#
- personalidentityno#
- 个人 ID 号
- personnummer
- personnummer#
- reisekrankenversicherungsichtenummer
- rejsesygesikringskort
- ssn
- ssn#
- 用户 ID
- 将 kode
- 将 nummer
- 将tenummer
- social security number
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- tax code
- 旅行健康保险卡
- uniqueidentityno#
- tax number
- tax registration number
- tax id
- tax identification number
- 已#
- taxnumber#
- tax no
- taxno#
- taxnumber
- tax identification no
- tin#
- 一些#
- 一些#
- tax no#
- tin id
- tin no
- cpr.nr
- cprnr
- cprnummer
- personnr
- personregister
- sygesikringsbevis
- sygesikringsbevisnr
- sygesikringsbevisnummer
- sygesikringskort
- sygesikringskortnr
- sygesikringskortnummer
- sygesikringsnr
- sygesikringsnummer


## <a name="denmark-physical-addresses"></a>丹麦物理地址

此未解包的命名实体检测与来自丹麦的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="diseases"></a>动物

此未解包的命名实体检测匹配花名称的文本，如 *花体*。 它仅支持英语术语。

### <a name="confidence-level"></a>置信度

高


## <a name="drug-enforcement-agency-dea-number"></a>管制局 (DEA) 号码

### <a name="format"></a>格式

两个字母后跟七个数字

### <a name="pattern"></a>模式

模式必须包括以下各项：
- 一个字母 (可能) 字母不区分大小写：abcdefghjklmnprstux，这是一个注册表代码
- 一个字母 (不区分大小写) ，即注册人姓氏或数字"9"的第一个字母
- 七个数字，最后一个数字是检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_dea_number 找到与该模式匹配的内容。
- 找到的关键字来自`Keyword_dea_number`
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_dea_number 找到与该模式匹配的内容。
- 校验和通过。

```xml
    <!-- DEA Number -->
    <Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_dea_number" />
      </Pattern>
      <Version minEngineVersion="15.20.1207.000" maxEngineVersion="15.20.3134.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
        </Pattern>
      </Version>
      <Version minEngineVersion="15.20.3135.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
          <Match idRef="Keyword_dea_number" />
        </Pattern>
      </Version>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_dea_number"></a>Keyword_dea_number

- dea
- dea#
- 一些强制执行管理
- 犯罪管制机构


## <a name="estonia-drivers-license-number"></a>爱沙尼亚驾驶证号码

### <a name="format"></a>格式

两个字母后跟六个数字

### <a name="pattern"></a>模式

两个字母和六个数字：

- 字母"ET" (不区分大小写) 
- 六个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_estonia_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_estonia_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Estonia Driver's License Number -->
      <Entity id="51da8171-da70-4cc1-9d65-055a59ca4f83" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_estonia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver s_license_number

- permis de conduire
- juhiadeade numbrid
- juhiloa number
- juhi一a


## <a name="estonia-passport-number"></a>爱沙尼亚护照号码

### <a name="format"></a>格式

一个字母后跟七个数字，无空格或分隔符

### <a name="pattern"></a>模式

一个字母后跟七个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_estonia_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_estonia_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_eu_passport_date1` DD.MM.YYYY 格式的日期或找到 `Keywords_eu_passport_date` 的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_estonia_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_estonia_eu_passport_number` 中的关键字。

```xml
      <!-- Estonia Passport Number -->
      <Entity id="61f7073a-509e-425b-a754-bc01bb5d5b8c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

eesti kodaniku passi number passinumbrid document number document no dokumendi nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="estonia-personal-identification-code"></a>爱沙尼亚个人标识代码

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

11 个数字，不带空格和分隔符

### <a name="pattern"></a>模式

11 个数字：

- 一个数字，对应于性生活和出生日期的世纪 (奇数男性，偶数男性;1-2：19 世纪;3-4：20 世纪;5-6：21 世纪) 
- 六个数字，对应于 YYMMDD (出生日期) 
- 三个数字，对应于同一日期出生日期的分隔人的序列号
- 一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_estonia_eu_national_id_card` 查找与模式匹配的内容。
- 找到 的  `Keywords_estonia_eu_national_id_card` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_estonia_eu_national_id_card` 查找与模式匹配的内容。

```xml
      <!-- Estonia Personal Identification Code -->
      <Entity id="bfb26de6-dad5-4d48-ab72-4789cdd0654c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_estonia_eu_telephone_number" />
            <Match idRef="Keywords_estonia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

- id-kaart
- ik
- isikukood#
- isikukood
- maksu id
- maksukohustuslase identifitseerimisnumber
- maksunumber
- national identification number
- national number
- 个人代码
- 个人 ID 号
- 个人标识代码
- 个人标识号
- personalidnumber#
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="estonia-physical-addresses"></a>爱沙尼亚物理地址

此未解包的命名实体检测与爱沙尼亚的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="eu-debit-card-number"></a>欧盟借记卡号码

### <a name="format"></a>格式

16 个数字

### <a name="pattern"></a>模式

复杂而可靠的模式

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_eu_debit_card 找到与该模式匹配的内容。
- 下列至少其中一项为真：
    - 找到 Keyword_eu_debit_card 中的一个关键字。
    - 找到 Keyword_card_terms_dict 中的一个关键字。
    - 找到 Keyword_card_security_terms_dict 中的一个关键字。
    - 找到 Keyword_card_expiration_terms_dict 中的一个关键字。
    - 函数 Func_expiration_date 找到正确日期格式的日期。
- 校验和通过。

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_eu_debit_card"></a>Keyword_eu_debit_card

- account number
- card number
- card no.
- security number
- cc#

#### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

- acct nbr
- acct num
- acct no
- american express
- americanexpress
- americano espresso
- amex
- atm card
- atm cards
- atm kaart
- atmcard
- atmcards
- atmkaart
- atmkaarten
- bancontact
- bank card
- bankkaart
- card holder
- card holders
- card num
- card number
- card numbers
- card type
- cardano numerico
- 将
- 将
- cardnumber
- cardnumbers
- carta bianca
- carta credito
- carta di credito
- cartao de credito
- cartao de crédito
- cartao de debito
- cartao de débito
- carte bancaire
- carte blanche
- carte bleue
- carte de credit
- carte de crédit
- carte di credito
- carteblanche
- cartão de credito
- cartão de crédito
- cartão de debito
- cartão de débito
- cb
- ccn
- check card
- check cards
- checkcard
- checkcards
- 一些
- cirrus
- cirrus-edc-ciostro
- controlekaart
- controlekekten
- credit card
- credit cards
- creditcard
- creditcards
- debetkaart
- debetkaarten
- debit card
- debit cards
- debitcard
- debitcards
- debito automatico
- diners club
- dinersc一
- discover
- discover card
- discover cards
- discovercard
- discovercards
- débito automático
- edc
- eigentümername
- european debit card
- hoofdkaart
- hoofdkdkdkten
- in viaggio
- japanese card bureau
- japanse kaartdienst
- jcb
- kaart
- kaart num
- kaartaantal
- kaartaantallen
- kaarthouder
- kaarthouders
- karte
- karteninhaber
- karteninhabers
- kartennr
- kartennummer
- kreditkrte
- kreditkrten-nummer
- kredititteninhaber
- kredit功能teninstitut
- kreditittennummer
- kredittentyp
- 将
- Master Card
- master cards
- mastercard
- mastercards
- mc
- mister cash
- n carta
- carta
- no de tarjeta
- no do cartao
- no do cartão
- no. de tarjeta

- no. do cartao

- no. do cartão

- nr carta
- nr. carta

- numeri di scheda
- numero carta
- numero de cartao
- numero de carte
- numero de cartão
- numero de tarjeta
- numero della carta
- numero di carta
- numero di scheda
- numero do cartao
- numero do cartão
- numéro de carte
- nº carta
- nº de carte
- nº de la carte
- nº de tarjeta
- nº do cartao
- nº do cartão
- nº. do cartão

- número de cartao
- número de cartão
- número de tarjeta
- número do cartao
- scheda dell'assegno
- scheda dell'atmosfera
- scheda dell'atmosfera
- scheda della banca
- scheda di controllo
- scheda di debito
- scheda matrice
- schede dell'atmosfera
- schede di controllo
- schede di debito
- schede matrici
- scoprono la scheda
- scoprono le schede
- 一个
- supporti di scheda
- supporto di scheda
- switch
- tarjeta atm
- tarjeta credito
- tarjeta de atm
- tarjeta de credito
- tarjeta de debito
- tarjeta debito
- tarjeta no
- tarjetahabiente
- tipo della scheda
- ufficio giapponese della
- scheda
- v pay
- v-pay
- visa
- visa plus
- visa electron
- visto
- visum
- vpay

#### <a name="keyword_card_security_terms_dict"></a>Keyword_card_security_terms_dict

- card identification number
- card verification
- cardi la verifica
- cid
- cod seg
- cod seguranca
- cod segurança
- cod sicurezza
- cod. seg

- cod. seguranca

- cod. segurança

- cod. sicurezza

- codice di sicurezza
- codice di verifica
- codigo
- codigo de seguranca
- codigo de segurança
- crittogramma
- 加密报
- cryptogramme
- cv2
- cvc
- cvc2
- cvn
- cvv
- cvv2
- cód seguranca
- cód segurança
- cód. seguranca

- cód. segurança

- código
- código de seguranca
- código de segurança
- de kaart controle
- geeft nr uit
- issue no
- issue number
- kaartidentificatienummer
- kreditittenprufnummer
- kreditittenprüfnummer
- kwestieaantal
- no. dell'edizione

- no. di sicurezza

- numero de securite
- numero de verificacao
- numero dell'edizione
- numero di identificazione della
- scheda
- numero di sicurezza
- numero van veiligheid
- numéro de sécurité
- nº autorizzazione
- número de verificação
- perno il blocco
- pin block
- prufziffer
- prüfziffer
- security code
- security no
- security number
- sicherheits kode
- sicherheitscode
- sicherheitsnummer
- speldblok
- veiligheid nr
- 将igheidsaantal
- 一个
- 将igheidsnummer
- verfalldatum

#### <a name="keyword_card_expiration_terms_dict"></a>Keyword_card_expiration_terms_dict

- ablauf
- data de expiracao
- data de expiração
- data del exp
- data di exp
- data di scadenza
- data em que expira
- data scad
- data scadenza
- date de validité
- datum afloop
- datum van exp
- de afloop
- espira
- espira
- exp date
- exp datum
- expiration
- expire
- expires
- expiry
- fecha de expiracion
- fecha de venc
- gultig bis
- gultigkeitsdatum
- gültig bis
- gültigkeitsdatum
- la scadenza
- scadenza
- valable
- validade
- valido hasta
- valor
- venc
- vencimento
- vencimiento
- verloopt
- vervaldag
- vervaldatum
- vto
- válido hasta


## <a name="eu-drivers-license-number"></a>欧盟驾驶证号码

这些实体在欧盟驾驶证号码中，是敏感信息类型。

- [Austria（奥地利）](#austria-drivers-license-number)
- [Belgium（比利时）](#belgium-drivers-license-number)
- [保加利亚](#bulgaria-drivers-license-number)
- [Croatia（克罗地亚）](#croatia-drivers-license-number)
- [塞浦路斯](#cyprus-drivers-license-number)
- [捷克语](#czech-drivers-license-number)
- [丹麦](#denmark-drivers-license-number)
- [爱沙尼亚](#estonia-drivers-license-number)
- [Finland（芬兰）](#finland-drivers-license-number)
- [France（法国）](#france-drivers-license-number)
- [Germany（德国）](#germany-drivers-license-number)
- [希腊](#greece-drivers-license-number)
- [匈牙利](#hungary-drivers-license-number)
- [爱尔兰](#ireland-drivers-license-number)
- [意大利](#italy-drivers-license-number)
- [拉脱维亚](#latvia-drivers-license-number)
- [Lithuania（立陶宛）](#lithuania-drivers-license-number)
- [亚明卡](#luxemburg-drivers-license-number)
- [马耳他](#malta-drivers-license-number)
- [荷兰](#netherlands-drivers-license-number)
- [波兰](#poland-drivers-license-number)
- [Portugal（葡萄牙）](#portugal-drivers-license-number)
- [罗马尼亚](#romania-drivers-license-number)
- [斯洛伐克](#slovakia-drivers-license-number)
- [斯洛文尼亚](#slovenia-drivers-license-number)
- [西班牙](#spain-drivers-license-number)
- [瑞典](#sweden-drivers-license-number)
- [英国](#uk-drivers-license-number)


## <a name="eu-national-identification-number"></a>欧盟国家标识号

这些实体在欧盟国家标识号中，是敏感信息类型。

- [Austria（奥地利）](#austria-identity-card)
- [Belgium（比利时）](#belgium-national-number)
- [保加利亚](#bulgaria-uniform-civil-number)
- [Croatia（克罗地亚）](#croatia-identity-card-number)
- [塞浦路斯](#cyprus-identity-card)
- [捷克语](#czech-personal-identity-number)
- [丹麦](#denmark-personal-identification-number)
- [爱沙尼亚](#estonia-personal-identification-code)
- [Finland（芬兰）](#finland-national-id)
- [France（法国）](#france-national-id-card-cni)
- [Germany（德国）](#germany-identity-card-number)
- [希腊](#greece-national-id-card)
- [匈牙利](#hungary-personal-identification-number)
- [爱尔兰](#ireland-personal-public-service-pps-number)
- [意大利](#italy-fiscal-code)
- [拉脱维亚](#latvia-personal-code)
- [Lithuania（立陶宛）](#lithuania-personal-code)
- [亚明卡](#luxemburg-national-identification-number-natural-persons)
- [马耳他](#malta-identity-card-number)
- [荷兰](#netherlands-citizens-service-bsn-number)
- [波兰](#poland-national-id-pesel)
- [Portugal（葡萄牙）](#portugal-citizen-card-number)
- [罗马尼亚](#romania-personal-numeric-code-cnp)
- [斯洛伐克](#slovakia-personal-number)
- [斯洛文尼亚](#slovenia-unique-master-citizen-number)
- [西班牙](#spain-dni)
- [英国](#uk-national-insurance-number-nino)


## <a name="eu-passport-number"></a>欧盟护照号码

这些实体在欧盟护照号码中，是敏感信息类型。 这些实体在欧盟护照号码捆绑包中。

- [Austria（奥地利）](#austria-passport-number)
- [Belgium（比利时）](#belgium-passport-number)
- [保加利亚](#bulgaria-passport-number)
- [Croatia（克罗地亚）](#croatia-passport-number)
- [塞浦路斯](#cyprus-passport-number)
- [捷克语](#czech-passport-number)
- [丹麦](#denmark-passport-number)
- [爱沙尼亚](#estonia-passport-number)
- [Finland（芬兰）](#finland-passport-number)
- [France（法国）](#france-passport-number)
- [Germany（德国）](#germany-passport-number)
- [希腊](#greece-passport-number)
- [匈牙利](#hungary-passport-number)
- [爱尔兰](#ireland-passport-number)
- [意大利](#italy-passport-number)
- [拉脱维亚](#latvia-passport-number)
- [Lithuania（立陶宛）](#lithuania-passport-number)
- [亚明卡](#luxemburg-passport-number)
- [马耳他](#malta-passport-number)
- [荷兰](#netherlands-passport-number)
- [波兰](#poland-passport-number)
- [Portugal（葡萄牙）](#portugal-passport-number)
- [罗马尼亚](#romania-passport-number)
- [斯洛伐克](#slovakia-passport-number)
- [斯洛文尼亚](#slovenia-passport-number)
- [西班牙](#spain-passport-number)
- [瑞典](#sweden-passport-number)
- [美国/英国护照号码](#usuk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>欧盟社会保险号或等效标识

这些实体是欧盟社会保险号或等效标识中的实体，是敏感信息类型。

- [Austria（奥地利）](#austria-social-security-number)
- [Belgium（比利时）](#belgium-national-number)
- [Croatia（克罗地亚）](#croatia-personal-identification-oib-number)
- [捷克语](#czech-personal-identity-number)
- [丹麦](#denmark-personal-identification-number)
- [Finland（芬兰）](#finland-national-id)
- [France（法国）](#france-social-security-number-insee)
- [Germany（德国）](#germany-identity-card-number)
- [希腊](#greece-national-id-card)
- [匈牙利](#hungary-social-security-number-taj)
- [Portugal（葡萄牙）](#portugal-citizen-card-number)
- [西班牙](#spain-social-security-number-ssn)
- [瑞典](#sweden-national-id)


## <a name="eu-tax-identification-number"></a>欧盟税务标识号

这些实体在欧盟税务标识号敏感信息类型中。

- [Austria（奥地利）](#austria-tax-identification-number)
- [Belgium（比利时）](#belgium-national-number)
- [保加利亚](#bulgaria-uniform-civil-number)
- [Croatia（克罗地亚）](#croatia-identity-card-number)
- [塞浦路斯](#cyprus-tax-identification-number)
- [捷克语](#czech-personal-identity-number)
- [丹麦](#denmark-personal-identification-number)
- [爱沙尼亚](#estonia-personal-identification-code)
- [Finland（芬兰）](#finland-national-id)
- [France（法国）](#france-tax-identification-number)
- [Germany（德国）](#germany-tax-identification-number)
- [希腊](#greece-tax-identification-number)
- [匈牙利](#hungary-tax-identification-number)
- [爱尔兰](#ireland-personal-public-service-pps-number)
- [意大利](#italy-fiscal-code)
- [拉脱维亚](#latvia-personal-code)
- [Lithuania（立陶宛）](#lithuania-personal-code)
- [亚明卡](#luxemburg-national-identification-number-non-natural-persons)
- [马耳他](#malta-tax-identification-number)
- [荷兰](#netherlands-tax-identification-number)
- [波兰](#poland-tax-identification-number)
- [Portugal（葡萄牙）](#portugal-tax-identification-number)
- [罗马尼亚](#romania-personal-numeric-code-cnp)
- [斯洛伐克](#slovakia-personal-number)
- [斯洛文尼亚](#slovenia-tax-identification-number)
- [西班牙](#spain-tax-identification-number)
- [瑞典](#sweden-tax-identification-number)
- [英国](#uk-unique-taxpayer-reference-number)


## <a name="finland-drivers-license-number"></a>芬兰驾驶证号码

### <a name="format"></a>格式

10 个数字，包含连字符

### <a name="pattern"></a>模式

10 个数字，包含连字符：

- 六个数字
- 连字符
- 三个数字
- 数字或字母

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_finland_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_finland_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Finland Driver's License Number -->
      <Entity id="bb3b27a3-79bd-4ac4-81a7-f9fca3c7d1a7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_finland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver s_license_number

- ajokortti
- permis de conduire
- ajokortin numero
- kuljettaja lic。
- körkort
- krkortnummer
- frare lic。
- ajokortit
- ajokortin numerot


## <a name="finland-european-health-insurance-number"></a>芬兰欧洲健康保险号码

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

20 位数字

### <a name="pattern"></a>模式

20 位数字：

- 10 个数字 - 8024680246
- 可选空格或连字符
- 10 个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式Regex_Finland_European_Health_Insurance_Number查找与模式匹配的内容。
- 找到来自Keyword_Finland_European_Health_Insurance_Number关键字。

```xml
      <!-- Finland European Health Insurance Number -->
      <Entity id="60f75aed-81bf-4625-89b0-0846b9248ee7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Finland_European_Health_Insurance_Number"/>
          <Match idRef="Keyword_Finland_European_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_finland_european_health_insurance_number"></a>Keyword_finland_european_health_insurance_number

- ehic#
- ehic
- finlandehicnumber#
- finska sjukförsökringskort
- health card
- 健康保险卡
- 健康保险号码
- hhlsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- sjukförskring nummer
- sjukförsökringskort
- s一men sairausvakuutuskortti
- terveyskortti


## <a name="finland-national-id"></a>芬兰国家/区 ID

### <a name="format"></a>格式

六个数字加一个字符，表示一世纪加三个数字加一个检查数字

### <a name="pattern"></a>模式

模式必须包括以下各项：
- 六个数字，格式为 DDMMYY，表示出生日期
- century marker (either '-'， '+' or 'a') 
- 三位数的个人标识号
- 一个数字或 (不区分大小写) 是一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_finnish_national_id查找与模式匹配的内容
- 找到来自Keyword_finnish_national_id的关键字
- 校验和传递

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数Func_finnish_national_id查找与模式匹配的内容
- 校验和传递

```xml
      <!-- Finnish National ID-->
      <Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finnish_national_id" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero#
- henkilötunnusnumero
- hetu
- id no
- id number
- identification number
- identiteetti numero
- 标识号
- idnumber
- 将linen henkilötunnus
- 一节
- national id card
- national id no.
- 个人 ID
- 个人标识代码
- personalidnumber#
- personbeteckning
- personnummer
- social security number
- so一aliturvatunnus
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- tunnistenumero
- tunnus numero
- tunnusl一
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="finland-passport-number"></a>芬兰护照号码

此实体在欧盟护照号码敏感信息类型中可用，并作为独立的敏感信息类型实体提供。

### <a name="format"></a>格式
九个字母和数字的组合

### <a name="pattern"></a>模式
九个字母和数字的组合：
- 两个字母 (不区分大小写) 
- 七个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找 `Regex_finland_passport_number` 与模式匹配的内容。
- 找到 或 `Keywords_eu_passport_number` `Keyword_finland_passport_number` 中的关键字。
- 正则表达式查找 `Regex_eu_passport_date1` DD.MM.YYYY 格式的日期或找到 `Keywords_eu_passport_date` 的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找 `Regex_finland_passport_number` 与模式匹配的内容。
- 找到 或 `Keywords_eu_passport_number` `Keyword_finland_passport_number` 中的关键字。

```xml
      <!-- Finland Passport Number -->
      <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- suomalainen passi
- passin numero
- passin numero。#
- passin numero#
- passin numero。
- passi#
- passi number

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="finland-physical-addresses"></a>芬兰物理地址

此未解包的命名实体检测与来自芬兰的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="france-drivers-license-number"></a>法国驾驶证号码

此实体在欧盟驾驶证号码敏感信息类型中可用，并作为独立的敏感信息类型实体提供。

### <a name="format"></a>格式

12 个数字

### <a name="pattern"></a>模式

12 个数字，会对类似模式（如法国电话号码）进行验证

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数Func_french_drivers_license查找与模式匹配的内容。
- 找到来自Keyword_french_drivers_license关键字。

```xml
    <!-- France Driver's License Number -->
    <Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Match idRef="Keyword_french_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers
- numéros de licence


## <a name="france-health-insurance-number"></a>法国健康保险号码

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

21 位数字

### <a name="pattern"></a>模式

21 位数字：

- 10 个数字
- 可选空格
- 10 个数字
- 可选空格
- 一个数字


### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式Regex_France_Health_Insurance_Number查找与模式匹配的内容。
- 找到来自Keyword_France_Health_Insurance_Number的关键字。

```xml
      <!-- France Health Insurance Number -->
      <Entity id="9bc2069e-76df-4ff9-ac02-2f519469e236" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_France_Health_Insurance_Number"/>
          <Match idRef="Keyword_France_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_france_health_insurance_number"></a>Keyword_France_health_insurance_number

- insurance card
- carte vitale
- carte d'assuré social


## <a name="france-national-id-card-cni"></a>法国国家/ (CNI) 

### <a name="format"></a>格式

12 个数字

### <a name="pattern"></a>模式

12 个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 正则表达式 Regex_france_cni 找到与该模式匹配的内容。
- 找到来自Keywords_france_eu_national_id_card关键字。

```xml
    <!-- France CNI -->
    <Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
        <Match idRef="Keywords_france_eu_national_id_card" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_france_eu_national_id_card"></a>Keywords_france_eu_national_id_card

- card number
- carte nationale d'identité
- carte nationale d'idenite no
- cni#
- cni
- compte bancaire
- national identification number
- national identity
- nationalidno#
- numéro d'assurance mal一e
- numéro de carte vitale


## <a name="france-passport-number"></a>法国护照号码

此实体在欧盟护照号码敏感信息类型中可用。 它还作为独立的敏感信息类型实体提供。

### <a name="format"></a>格式

九个数字和字母

### <a name="pattern"></a>模式

九个数字和字母：
- 两个数字
- 两个字母 (不区分大小写) 
- 五个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 `Func_fr_passport` 查找与模式匹配的内容。
- 找到 或 `Keywords_eu_passport_number` `Keywords_france_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_eu_passport_date3` 格式为 DD MM YYYY 的日期或找到 `Keywords_eu_passport_date` 的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 `Func_fr_passport` 查找与模式匹配的内容。
- 找到 或 `Keywords_eu_passport_number` `Keywords_france_eu_passport_number` 中的关键字。


```xml
    <!-- France Passport Number -->
    <Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_france_eu_passport_number"></a>Keywords_france_eu_passport_number

- numéro de passeport
- passeport n °
- passeport non
- passeport#
- passeport#
- passeportnon
- passeportn °
- passeport français
- passeport livre
- passeport carte
- numéro passeport
- passeport n°
- n° du passeport
- n° passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="france-physical-addresses"></a>法国物理地址

此未解包的命名实体检测与来自法国的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="france-social-security-number-insee"></a>法国社会保险号码 (INSEE) 

### <a name="format"></a>格式

15 个数字

### <a name="pattern"></a>模式

必须匹配两种模式之一：
- 13 个数字，后跟一个空格，后跟两个数字<br/>
或
- 15 个连续的数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 `Func_french_insee` 查找与模式匹配的内容。
- 找到 Keyword_fr_insee 中的一个关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数Func_french_insee或Func_fr_insee找到与模式匹配的内容。
- 校验和通过。

```xml
    <!-- France INSEE -->
    <Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Keyword_fr_insee" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- code sécu
- d'identité nationale
- insee
- fssn#
- le numéro d'identification nationale
- le code de la sécurité sociale
- national id
- national identification
- no d'identité
- 
no. d'identité
- numéro d'assurance
- numéro d identité
- numero d'identite
- numéro de sécu
- numéro de sécurité sociale
- no d'identite
- 
no. d'identite
- ssn
- ssn#
- sécurité sociale
- securité sociale
- securite sociale
- socialsecuritynumber
- social security number
- social security code
- social insurance number


## <a name="france-tax-identification-number"></a>法国税务标识号

### <a name="format"></a>格式

13 位数字

### <a name="pattern"></a>模式

13 位数字

- 一个数字，必须为 0、1、2 或 3
- 一位数字
- 一个空格（可选） 
- 两位数字
- 一个空格（可选） 
- 三个数字 
- 一个空格（可选） 
- 三个数字 
- 一个空格（可选） 
- 三个检查数字


### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_france_eu_tax_file_number` 查找与模式匹配的内容。
- 找到 的  `Keywords_france_eu_tax_file_number` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_france_eu_tax_file_number` 查找与模式匹配的内容。

```xml
      <!-- France Tax Identification Number (numéro SPI.) -->
      <Entity id="ed59e77e-171d-442c-9ec1-88e2ebcb5b0a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_france_eu_telephone_number" />
            <Match idRef="Keywords_france_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Keywords

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

- numéro d'identification fiscale
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="france-value-added-tax-number"></a>法国增值税编号

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

13 个字符字母数字模式

### <a name="pattern"></a>模式

13 个字符字母数字模式：

- 两个字母 - FR (不区分大小写) 
- 可选空格或连字符
- 两个字母或数字
- 可选空格、点、连字符或逗号
- 三个数字
- 可选空格、点、连字符或逗号
- 三个数字
- 可选空格、点、连字符或逗号
- 三个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_france_value_added_tax_number查找与模式匹配的内容。
- 找到来自Keywords_france_value_added_tax_number关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数Func_france_value_added_tax_number查找与模式匹配的内容。

```xml
      <!-- France Value Added Tax Number -->
      <Entity id="949121e6-ad9f-4379-8731-710342baea78" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_value_added_tax_number" />
          <Match idRef="Keywords_france_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_france_value_added_tax_number"></a>Keyword_France_value_added_tax_number

- vat number
- vat no
- vat#
- 增值税
- siren identification no numéro d'identification taxe surur ajoutée
- taxe 为 ajoutée
- taxe sur laurur ajoutée
- n° tva
- numéro de tva
- numéro d'identification siren


## <a name="generic-medication-names"></a>通用名

此未解包的命名实体可检测泛型类的名称，例如 *，用户* 名称。 它仅支持英语术语。

### <a name="confidence-level"></a>置信度

高


## <a name="germany-drivers-license-number"></a>德国驾驶证号码

此敏感信息类型实体包含在欧盟驾驶证号码敏感信息类型中。 它还作为独立的敏感信息类型实体提供。

### <a name="format"></a>格式

11 个数字和字母的组合

### <a name="pattern"></a>模式

11 个数字和字母 (不区分大小写) ：
- 数字或字母
- 两个数字
- 六个数字或字母
- 一个数字
- 数字或字母

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_german_drivers_license 找到与该模式匹配的内容。
- 找到 Keyword_german_drivers_license_number 中的一个关键字。
- 校验和通过。

```xml
    <!-- German Driver's License Number -->
    <Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Match idRef="Keyword_german_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

- ausstel一sdatum
- ausstel一sort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde
- führerschein
- fuhrerschein
- fuehrerschein
- führerscheinnummer
- fuhrerscheinnummer
- fuehrerscheinnummer
- führerschein- 
- fuhrerschein- 
- fuehrerschein- 
- führerscheinnummernr
- fuhrerscheinnummernr
- fuehrerscheinnummernr
- führerscheinnummerklasse
- fuhrerscheinnummerklasse
- fuehrerscheinnummerklasse
- nr-fhrerschein
- nr-fuhrerschein
- nr-fuehrerschein
- no-fhrerschein
- no-fuhrerschein
- no-fuehrerschein
- n-fhrerschein
- n-fuhrerschein
- n-fuehrerschein
- permis de conduire
- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dlno


## <a name="germany-identity-card-number"></a>德国身份证号码

### <a name="format"></a>格式

自 2010 年 11 月 1 日：九到十一个字母和数字

从 1987 年 4 月 1 日到 2010 年 10 月 31 日：10 个数字

### <a name="pattern"></a>模式

自 2010 年 11 月 1 日起：9 到 11 个字符的字母数字模式
- 一个 L、M、N、P、R、T、V、W、X、Y (不区分大小写) 
- 八个数字或字母，以 C、F、G、H、J、K、L、M、N、P、R、T、V、W、X、Y 和 Z (区分大小写) 
- 可选检查数字
- 可选 d/D

从 1987 年 4 月 1 日到 2010 年 10 月 31 日：
- 10 个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 `Func_german_id_card_with_check` 查找与模式匹配的内容。
- 找到 的 `Keyword_germany_id_card` 关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- `Regex_germany_id_card`正则表达式查找与 2010 年前颁发的 9 个字符模式（不含检查数字 2010 或 2010 年颁发的 10 个数字模式）) 。 (
- 找到 Keyword_germany_id_card 中的一个关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数 `Func_german_id_card_with_check` 查找与模式匹配的内容。
- 校验和通过。


```xml
      <!-- Germany Identity Card Number -->
      <Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" patternsProximity="300" recommendedConfidence="75"> 
        <Pattern confidenceLevel="75">
         <IdMatch idRef="Regex_germany_id_card" /> 
         <Match idRef="Keyword_germany_id_card" /> 
        </Pattern>
        <Version minEngineVersion="15.20.4545.000"> 
          <Pattern confidenceLevel="85">
           <IdMatch idRef="Func_german_id_card_with_check" />
            <Match idRef="Keyword_germany_id_card" /> 
          </Pattern> 
          <Pattern confidenceLevel="65">
           <IdMatch idRef="Func_german_id_card_with_check" /> 
          </Pattern> 
        </Version>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- aus一s
- gpid
- identification
- identifikation
- identifizierungsnummer
- identity card
- 标识号
- id-nummer
- 个人 ID
- personalaus一s
- persönliche id nummer
- persönliche identifikationsnummer
- persönliche-id-nummer


## <a name="germany-passport-number"></a>德国护照号码

### <a name="format"></a>格式

9 到 11 个字符

### <a name="pattern"></a>模式

- 一个字母，C、F、G、H、J、K (不区分大小写) 
- 八个数字或字母，以 C、F、G、H、J、K、L、M、N、P、R、T、V、W、X、Y 和 Z (区分大小写) 
- 可选检查数字
- 可选 d/D

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 `Func_german_passport_checksum` 查找与模式匹配的内容。
- 找到 或 `Keyword_german_passport` `Keywords_eu_passport_number_common` 中的关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 该函数 `Func_german_passport` 查找与九个字符模式匹配的内容 (无检查数字和可选 d/D) 。
- 找到 或 `Keyword_german_passport` `Keywords_eu_passport_number_common` 中的关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数 `Func_german_passport_checksum` 查找与模式匹配的内容。
- 校验和通过。

```xml
    <!-- German Passport Number -->
    <Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
      <Version minEngineVersion="15.20.4570.0">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_german_passport_checksum" />
          <Any minMatches="1">
            <Match idRef="Keyword_german_passport" />
            <Match idRef="Keywords_eu_passport_number_common" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_german_passport_checksum" />
        </Pattern>
      </Version>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- reisepasse
- reisepassnummer
- No-Reisepass
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisep的sse
- passeport no.
- passeport no

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers


## <a name="germany-physical-addresses"></a>德国物理地址

此未解包的命名实体检测与来自德国的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="germany-tax-identification-number"></a>德国税务标识号

### <a name="format"></a>格式

11 个数字，不带空格和分隔符

### <a name="pattern"></a>模式

11 个数字

- 两位数字
- 可选空格
- 三位数字
- 可选空格
- 三位数字
- 可选空格
- 两位数字
- 一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_germany_eu_tax_file_number` 查找与模式匹配的内容。
- 找到 的  `Keywords_germany_eu_tax_file_number` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_germany_eu_tax_file_number` 查找与模式匹配的内容。

```xml
      <!-- Germany Tax Identification Number -->
      <Entity id="43316a89-9880-40cf-b980-04bc7eefcec5" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_germany_eu_tax_file_number"></a>Keywords_germany_eu_tax_file_number

- identifikationsnummer
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- zinn#
- zinn
- zinnnummer


## <a name="germany-value-added-tax-number"></a>德国增值税编号

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

11 个字符字母数字模式

### <a name="pattern"></a>模式

11 字符字母数字模式：

- 字母 D 或 d
- 字母 E 或 e
- 可选空格
- 三个数字
- 可选空格或逗号
- 三个数字
- 可选空格或逗号
- 三个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_germany_value_added_tax_number查找与模式匹配的内容。
- 找到来自Keywords_germany_value_added_tax_number关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数Func_germany_value_added_tax_number查找与模式匹配的内容。

```xml
      <!-- Germany Value Added Tax Number -->
      <Entity id="db177eb2-8811-4842-bffc-128c14aa219f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
          <Match idRef="Keywords_germany_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_germany_value_added_tax_number"></a>Keyword_germany_value_added_tax_number

- vat number
- vat no
- vat#
- vat# mehrwertsteuer
- mwst
- mehrwertsteuer identifikationsnummer
- mehrwertsteuer nummer


## <a name="greece-drivers-license-number"></a>希腊驾驶证号码

此实体包含在欧盟驾驶证号码敏感信息类型中。 它还作为独立的敏感信息类型实体提供。

### <a name="format"></a>格式

九个数字，不带空格和分隔符

### <a name="pattern"></a>模式

九个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_greece_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_greece_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Greece Driver's License Number -->
      <Entity id="7a2200b5-aacf-4e3c-ab36-136d3e68b7da" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_greece_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver s_license_number

- δεια οδήγησης
- Adeia odigisis
- Άδεια οδήγησης
- Δίπλωμα οδήγησης


## <a name="greece-national-id-card"></a>希腊国民身份证

### <a name="format"></a>格式

7-8 个字母和数字组合加一个短划线

### <a name="pattern"></a>模式

七个字母和数字（旧格式）：
- 一个字母（希腊字母表中的任一字母） 
- 一个短划线 
- 六个数字

八个字母和数字（新格式）：
- 大写字符同时出现在希腊和拉丁字母表中的两个字母 (ABEZHIKMNOPTYX) 
- 一个短划线 
- 六个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式 Regex_greece_id_card 找到与该模式匹配的内容。
- 找到 Keyword_greece_id_card 中的一个关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 正则表达式 Regex_greece_id_card 找到与该模式匹配的内容。

```xml
      <!-- Greece National ID Card -->
      <Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_id_card" />
          <Match idRef="Keyword_greece_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- greek id
- 希腊语国家/区 ID
- 希腊语个人 ID 卡
- 希腊语政府 ID
- identity card
- tautotita
- ταυτότητα
- ταυτότητας


## <a name="greece-passport-number"></a>希腊护照号码

### <a name="format"></a>格式

两个字母后跟七个数字，无空格或分隔符

### <a name="pattern"></a>模式

两个字母后跟七个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_greece_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_greece_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_greece_eu_passport_date` DD MMM YY 格式的日期 (示例 - 8 月 19 `Keywords_greece_eu_passport_date` 日) 找到关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_greece_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_greece_eu_passport_number` 中的关键字。

```xml
      <!-- Greece Passport Number -->
      <Entity id="7e65eb47-cdf9-4f52-8f90-2a27d5ee67e3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_greece_eu_passport_date" />
            <Match idRef="Keywords_greece_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο


## <a name="greece-physical-addresses"></a>希腊物理地址

此未解包的命名实体检测与来自希腊的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中

## <a name="greece-social-security-number-amka"></a>希腊社会保险号码 (AMKA) 

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

11 个数字，不带空格和分隔符

### <a name="pattern"></a>模式

- 六个数字作为出生日期 YYMMDD
- 四位数字
- 一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_greece_eu_ssn` 查找与模式匹配的内容。
- 找到 的  `Keywords_greece_eu_ssn_or_equivalent` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_greece_eu_ssn` 查找与模式匹配的内容。

```xml
      <!-- Greece Social Security Number (AMKA) -->
      <Entity id="e39b03f4-50ea-41ae-af7a-a4b9539596ad" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_greece_eu_ssn" />
          <Match idRef="Keywords_greece_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_greece_eu_ssn" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_greece_eu_ssn_or_equivalent"></a>Keywords_greece_eu_ssn_or_equivalent

- ssn
- ssn#
- social security no
- socialsecurityno#
- social security number
- amka
- a.m.k.a.
- Αριθμού Μητρώου Κοινωνικής Ασφάλισης


## <a name="greece-tax-identification-number"></a>希腊税务标识号

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

九个数字，不带空格和分隔符

### <a name="pattern"></a>模式

九个数字

### <a name="checksum"></a>校验和

不适用

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：

- 正则表达式查找  `Regex_greece_eu_tax_file_number` 与模式匹配的内容。
- 找到 的  `Keywords_greece_eu_tax_file_number` 关键字。

```xml
      <!-- Greek Tax Identification Number -->
      <Entity id="15a54a5a-53d4-4080-ad43-a2a4fe1d3bf7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

- afm#
- afm
- a→ |a αριθμός
- a
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- tax registry no
- tax registry number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- taxregistryno#
- tin id
- tin no
- tin#
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>Hk Kong identity card (HKID) number

### <a name="format"></a>格式

8-9 个字母和数字组合，最后一个字符两边可选择加括号

### <a name="pattern"></a>模式

8-9 个字母组合：
- 1-2 个字母 (不区分大小写) 
- 六个数字 
- 最后一个字符（任意数字或字母 A）是校验位，两边可以选择加括号。

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_hong_kong_id_card 找到与该模式匹配的内容。
- 找到 Keyword_hong_kong_id_card 中的一个关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数 Func_hong_kong_id_card 找到与该模式匹配的内容。
- 校验和通过。

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_hong_kong_id_card"></a>Keyword_hong_kong_id_card

- hkid
- hong kong identity card
- HKIDC
- id card
- identity card
- hk identity card
- hong kong id
- 香港身份證
- 香港永久性居民身份證
- 身份證
- 身份証
- 身分證
- 身分証
- 香港身份証
- 香港身分證
- 香港身分証
- 香港身份證
- 香港居民身份證
- 香港居民身份証
- 香港居民身分證
- 香港居民身分証
- 香港永久性居民身份証
- 香港永久性居民身分證
- 香港永久性居民身分証
- 香港永久性居民身份證
- 香港非永久性居民身份證
- 香港非永久性居民身份証
- 香港非永久性居民身分證
- 香港非永久性居民身分証
- 香港特別行政區永久性居民身份證
- 香港特別行政區永久性居民身份証
- 香港特別行政區永久性居民身分證
- 香港特別行政區永久性居民身分証
- 香港特別行政區非永久性居民身份證
- 香港特別行政區非永久性居民身份証
- 香港特別行政區非永久性居民身分證
- 香港特別行政區非永久性居民身分証


## <a name="hungary-drivers-license-number"></a>匈牙利驾驶证号码

### <a name="format"></a>格式

两个字母后跟六个数字

### <a name="pattern"></a>模式

两个字母和六个数字：

- 两个字母 (不区分大小写) 
- 六个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：

- 正则表达式查找  `Regex_hungary_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_hungary_eu_driver's_license_number` 中的关键字。

```xml
      <Entity id="9d31c46b-6e6b-444c-aeb1-6dd7e604bb24" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_hungary_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver s_license_number

- vezetoi engedely
- vezetői engedély
- vezetői engedélyek


## <a name="hungary-passport-number"></a>匈牙利护照号码

### <a name="format"></a>格式

两个字母后跟 6 个或 7 个数字，没有空格或分隔符

### <a name="pattern"></a>模式

两个字母后跟六个或七个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_hungary_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_hungary_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_hungary_eu_passport_date` 格式为 DD MMM/MMM YY (示例 - 01 MÁR/MAR 12 `Keywords_eu_passport_date` 的日期) 找到的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_hungary_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_hungary_eu_passport_number` 中的关键字。

```xml
      <!-- Hungary Passport Number -->
      <Entity id="5b483910-9aa7-4c99-9917-f4001464bda7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_hungary_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- útlevél száma
- Útlevelek száma
- útlevél szám

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="hungary-personal-identification-number"></a>匈牙利个人标识号

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

11 个数字

### <a name="pattern"></a>模式

11 个数字：

- 一个数字，对应性别，1 表示男性，2 表示男性。 对于在 1900 以前生活的人或具有双重公民权的人，也可以申请其他号码。
- 六个数字，对应于出生日期 (YYMMDD) 
- 对应于序列号的三个数字
- 一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：

- 函数  `Func_hungary_eu_national_id_card` 查找与模式匹配的内容。
- 找到 的  `Keywords_hungary_eu_national_id_card` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：

- 函数  `Func_hungary_eu_national_id_card` 查找与模式匹配的内容。

```xml
      <!-- Hungary Personal Identification Number -->
      <Entity id="7b5cc218-7046-47d9-80c9-f325b50896ca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- id number
- identification number
- sz ig
- sz. ig.
- sz.ig.
- személyazonosító igazolv一y
- személyi igazolvméy


## <a name="hungary-physical-addresses"></a>匈牙利物理地址

此未解包的命名实体检测与匈牙利的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="hungary-social-security-number-taj"></a>匈牙利社会保险号码 (TAJ) 

### <a name="format"></a>格式

九个数字，不带空格和分隔符

### <a name="pattern"></a>模式

九个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：

- 函数  `Func_hungary_eu_ssn_or_equivalent` 查找与模式匹配的内容。
- 找到 的  `Keywords_hungary_eu_ssn_or_equivalent` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：

- 函数  `Func_hungary_eu_ssn_or_equivalent` 查找与模式匹配的内容。

```xml
      <!-- Hungarian Social Security Number (TAJ) -->
      <Entity id="0de78315-9537-47f5-95ab-b3e77eba3993" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

- 匈牙利社会安全号码
- social security number
- socialsecuritynumber#
- hssn#
- socialsecuritynno
- hssn
- taj
- taj#
- ssn
- ssn#
- social security no
- áfa
- kázósségi adószám
- által一os forgalmi adó szám
- hozzáadott一ték adó
- áfa szám
- magyar áfa szám


## <a name="hungary-tax-identification-number"></a>匈牙利税收标识号

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

10 个数字，无空格或分隔符

### <a name="pattern"></a>模式

10 个数字：

- 一个数字必须为"8"
- 八位数字
- 一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：

- 函数  `Func_hungary_eu_tax_file_number` 查找与模式匹配的内容。
- 找到 的  `Keywords_hungary_eu_tax_file_number` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：

- 函数  `Func_hungary_eu_tax_file_number` 查找与模式匹配的内容。

```xml
      <!-- Hungary Tax Identification Number -->
      <Entity id="ede42eb4-59d9-49eb-9603-d7853fbda91d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

- adóazonosító szám
- adóhatóság szám
- adószám
- 匈牙利语（该文）
- hungatiantin#
- 税务机构否
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- vat number


## <a name="hungary-value-added-tax-number"></a>匈牙利增值税编号

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

10 个字符字母数字模式

### <a name="pattern"></a>模式

10 个字符字母数字模式：

- 两个字母 - HU 或 hu
- 可选空格
- 八个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：

- 函数Func_hungarian_value_added_tax_number查找与模式匹配的内容。
- 找到来自Keywords_hungarian_value_added_tax_number关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：

- 函数Func_hungarian_value_added_tax_number查找与模式匹配的内容。

```xml
      <!-- Hungarian Value Added Tax Number -->
      <Entity id="976349a0-683b-477a-90f8-ff0a220d5592" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
          <Match idRef="Keywords_hungarian_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_hungary_value_added_tax_number"></a>Keyword_Hungary_value_added_tax_number

- vat
- 增值税编号
- vat#
- vatno#
- hungarianvatno#
- tax no.
- value added tax áfa
- kázósségi adószám
- által一os forgalmi adó szám
- hozzáadott一ték adó
- áfa szám


## <a name="iceland-physical-addresses"></a>冰岛物理地址

此未解包的命名实体检测与来自冰岛的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中

## <a name="impairments-listed-in-the-us-disability-evaluation-under-social-security"></a>美国社会保险下残障评估中列出的障碍

此未解包的命名实体检测美国社会保险下残障评估中列出的障碍名称，如听力 *障碍*。 它仅支持英语术语。

### <a name="confidence-level"></a>置信度

高


## <a name="india-drivers-license-number"></a>印度驾驶证号码

### <a name="format"></a>格式

15 个字符字母数字模式

### <a name="pattern"></a>模式

15 个字母或数字：
- 指示状态代码的两个字母
- 可选空格或短划线
- 指示城市代码的两个数字
- 可选空格或短划线
- 四个数字，表示问题年份
- 可选空格或短划线
- 七个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找 `Regex_india_driving_license` 与模式匹配的内容。
- 找到 的 `Keywords_eu_driver's_license_number_common` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找 `Regex_india_driving_license` 与模式匹配的内容。


```xml
      <!-- India Driver's License Number -->
        <Entity id="680788a3-53b6-455a-b891-c38cd76dc917" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
          <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_india_driving_license" />
            <Match idRef="Keywords_eu_driver's_license_number_common" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_india_driving_license" />
            </Pattern>
        </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number_common"></a>Keywords_eu_driver s_license_number_common

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number



## <a name="india-gst-number"></a>印度 GST 号码

### <a name="format"></a>格式

15 个字符字母数字模式

### <a name="pattern"></a>模式

15 个字母或数字：
- 表示有效状态代码的两个数字
- 可选空格或短划线
- 10 个字符，代表 PAN (")  
- 一个字母或数字
- 可选空格或短划线
- 一个字母"z"或"Z"
- 可选空格或短划线
- 一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 `Func_india_gst_number` 查找与模式匹配的内容。
- 找到 的 `Keyword_india_gst_number` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 `Func_india_gst_number` 查找与模式匹配的内容。


```xml
    <!-- India GST number  -->
      <Entity id="9f5a721c-2fd2-446a-a27e-0c02fbe4630c" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_india_gst_number" />
          <Match idRef="Keyword_india_gst_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_india_gst_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_india_gst_number"></a>Keyword_india_gst_number

- gst
- gstin
- 商品和服务税
- 商品和服务税


## <a name="india-permanent-account-number-pan"></a>PAN (印度永久) 

### <a name="format"></a>格式

10 个字母或数字

### <a name="pattern"></a>模式

10 个字母或数字：
- 三个字母 (不区分大小写) 
- C、P、H、F、A、T、B、L、J、G (不区分大小写) 
- 一个字母
- 四位数字
- 字母是字母检查数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式 Regex_india_permanent_account_number 找到与该模式匹配的内容。
- 找到 Keyword_india_permanent_account_number 中的一个关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 正则表达式 Regex_india_permanent_account_number 找到与该模式匹配的内容。


```xml
      <!-- India Permanent Account Number -->
      <Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_india_permanent_account_number" />
          <Match idRef="Keyword_india_permanent_account_number" />
        </Pattern>
        <Version minEngineVersion="15.20.3520.000">
          <Pattern confidenceLevel="65">
            <IdMatch idRef="Regex_india_permanent_account_number" />
          </Pattern>
        </Version>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Permanent Account Number
- PAN

## <a name="india-unique-identification-aadhaar-number"></a>印度唯一 (Aadhaar) 号

### <a name="format"></a>格式

12 个数字（包含可选空格或短划线）

### <a name="pattern"></a>模式

12 个数字：
- 不为 0 或 1 的数字
- 三位数字
- 一个可选空格或短划线 
- 四个数字
- 一个可选空格或短划线 
- 最后一个数字，即检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_india_aadhaar 找到与该模式匹配的内容。
- 找到 Keyword_india_aadhar 中的一个关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：

- 函数 Func_india_aadhaar 找到与该模式匹配的内容。
- 校验和通过。

```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar
- aadhaar
- aadhar
- aadhar#
- uid
- आधार
- uidai


## <a name="india-voter-id-card"></a>印度身份证

### <a name="format"></a>格式

10 个字符字母数字模式

### <a name="pattern"></a>模式

10 个字母或数字：
- 三个字母
- 七个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找 `Regex_india_voter_id_card` 与模式匹配的内容。
- 找到 的 `Keyword_india_voter_id_card` 关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 正则表达式查找 `Regex_india_voter_id_card` 与模式匹配的内容。


```xml
      <!-- India Voter Id Card  -->
        <Entity id="646d643f-5228-4408-acc8-f2e81a6df897" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
           <Pattern confidenceLevel="75">
             <IdMatch idRef="Regex_india_voter_id_card" />
             <Match idRef="Keyword_india_voter_id_card" />
            </Pattern>
           <Pattern confidenceLevel="65">
              <IdMatch idRef="Regex_india_voter_id_card" />
            </Pattern>
        </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_india_voter_id_card"></a>Keyword_india_voter_id_card

- 一个
- voterid
- 将card
- voteridcard
- 组照片标识卡
- 一百万
- ECI
- commmision


## <a name="indonesia-identity-card-ktp-number"></a>印度尼西亚身份证号码 (KTP) 号码

### <a name="format"></a>格式

16 个数字（包含可选点）

### <a name="pattern"></a>模式

16 个数字：
- 两位省代码 
- 一个点（可选） 
- 两位摄政统治区或城市代码 
- 两位住宅小区代码 
- 一个点（可选） 
- 六个数字，格式为 DDMMYY，表示出生日期
- 一个点（可选） 
- 四个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：

- 正则表达式 Regex_indonesia_id_card 找到与该模式匹配的内容。
- 找到 Keyword_indonesia_id_card 中的一个关键字。

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_indonesia_id_card"></a>Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk
- Nomor Induk Kependudukan

## <a name="international-banking-account-number-iban"></a>IBAN (国际银行) 

### <a name="format"></a>格式

国家/地区代码（两个字母）加校验位（两个数字）以及 bban 号码（最多 30 个字符）

### <a name="pattern"></a>模式

模式必须包括以下各项：

- 两个字母的国家/地区代码
- 两个校验位（后跟一个可选空间） 
- 1-7 个包含 4 个字母或数字的组（可以使用空格进行分隔）
- 1-3 个字母或数字

每个国家/地区的格式稍有不同。IBAN 敏感信息类型涵盖这 60 个国家/地区：

- ad
- ae
- al
- at
- az
- ba
- be
- bg
- bh
- ch
- cr
- cy
- cz
- de
- dk
- do
- ee
- es
- fi
- fo
- fr
- gb
- ge
- gi
- gl
- gr
- hr
- hu
- ie
- il
- is
- it
- kw
- kz
- lb
- li
- lt
- lu
- lv
- mc
- md
- me
- mk
- mr
- mt
- mu
- nl
- 否
- pl
- pt
- ro
- rs
- sa
- se
- si
- sk
- sm
- tn
- tr
- vg

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：

- 函数 Func_iban 找到与该模式匹配的内容。
- 校验和通过。

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

无


## <a name="international-classification-of-diseases-icd-10-cm"></a>ICD-10-CM (国际) 

### <a name="format"></a>格式

Dictionary

### <a name="pattern"></a>模式

Keyword

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 找到来自Dictionary_icd_10_updated关键字。
- 找到来自Dictionary_icd_10_codes关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 找到更新Dictionary_icd_10_关键字。

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

### <a name="keywords"></a>Keywords

基于国际Dictionary_icd_10_updated分类、第十次修订、修订修改和 [ICD-10-CM ](https://go.microsoft.com/fwlink/?linkid=852604) (的关键字词典) 。 此类型仅查找术语，而不是保险代码。

基于国际Dictionary_icd_10_codes分类、第十次修订、修订修改和 [ICD-10-CM ](https://go.microsoft.com/fwlink/?linkid=852604) (关键字词典的任何) 。 此类型仅查找保险代码，而不是说明。


## <a name="international-classification-of-diseases-icd-9-cm"></a>ICD-9-CM (国际) 

### <a name="format"></a>格式

Dictionary

### <a name="pattern"></a>模式

Keyword

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 找到来自Dictionary_icd_9_updated关键字。
- 找到来自Dictionary_icd_9_codes关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 找到来自Dictionary_icd_9_updated关键字。

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

基于国际Dictionary_icd_9_updated分类、第九次修订、修订和 [ICD-9-CM ](https://go.microsoft.com/fwlink/?linkid=852605) (的关键字词典) 。 此类型仅查找术语，而不是保险代码。

基于国际Dictionary_icd_9_codes分类、第九次修订、修订修改和 [ICD-9-CM ](https://go.microsoft.com/fwlink/?linkid=852605) (关键字词典的任何) 。 此类型仅查找保险代码，而不是说明。

## <a name="ip-address"></a>IP 地址

### <a name="format"></a>格式

#### <a name="ipv4"></a>IPv4：
复杂模式，用于设置格式 (句) ， (无格式) IPv4 地址版本

#### <a name="ipv6"></a>IPv6：
包含带格式的 IPv6 号码的复杂 (包括冒号) 

### <a name="pattern"></a>模式

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

对于 IPv6，如果在 300 个字符的邻近度内，DLP 策略会高可信度地检测到这种类型的敏感信息：
- 正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。
- 未找到 Keyword_ipaddress 中的关键字。

对于 IPv4，如果在 300 个字符的邻近度内，DLP 策略会高可信度地检测到这种类型的敏感信息：
- 正则表达式 Regex_ipv4_address 找到与该模式匹配的内容。
- 找到 Keyword_ipaddress 中的一个关键字。

对于 IPv6，如果在 300 个字符的邻近度内，DLP 策略会高可信度地检测到这种类型的敏感信息：
- 正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。
- 未找到 Keyword_ipaddress 中的关键字。

```xml
    <!-- IP Address --> 
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- 此 (的 IP 关键字区分大小写) 
- ip address
- ip addresses
- internet protocol
- IP-כתובת ה


## <a name="ip-address-v4"></a>IP 地址 v4

### <a name="format"></a>格式

复杂模式，用于设置格式 (句) ， (无格式) IPv4 地址版本

### <a name="pattern"></a>模式


### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找 `Regex_ipv4_address` 与模式匹配的内容。
- 找到 的 `Keyword_ipaddress` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找 `Regex_ipv4_address` 与模式匹配的内容。


```xml
      <!-- IP Address v4--> 
      <Entity id="a7dd5e5f-e7f9-4626-a2c6-86a8cb6830d2" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ipv4_address" />
          <Match idRef="Keyword_ipaddress" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ipv4_address" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (区分大小写) 
- ip address
- ip addresses
- internet protocol
- IP-כתובת ה


## <a name="ip-address-v6"></a>IP 地址 v6

### <a name="format"></a>格式

包含带格式的 IPv6 号码的复杂 (包括冒号) 

### <a name="pattern"></a>模式


### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找 `Regex_ipv6_address` 与模式匹配的内容。
- 找到 的 `Keyword_ipaddress` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找 `Regex_ipv6_address` 与模式匹配的内容。


```xml
      <!-- IP Address v6-->
      <Entity id="3f691089-7413-4926-ab3b-3c5ea8a1c17e" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ipv6_address" />
          <Match idRef="Keyword_ipaddress" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ipv6_address" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (区分大小写) 
- ip address
- ip addresses
- internet protocol
- IP-כתובת ה


## <a name="ireland-drivers-license-number"></a>爱尔兰驾驶证号码

### <a name="format"></a>格式

六个数字后跟四个字母

### <a name="pattern"></a>模式

六个数字和四个字母：

- 六位数字
- 四个字母 (不区分大小写) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：

- 正则表达式查找  `Regex_ireland_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_ireland_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Ireland Driver's License Number -->
      <Entity id="e01bccd9-eb4d-414f-ace1-e9b6a4c4a2ca" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_ireland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver s_license_number

- ceadúnas tiom在a
- ceadúnais tiom一a

## <a name="ireland-passport-number"></a>爱尔兰护照号码

### <a name="format"></a>格式

两个字母或数字后跟七个数字，无空格或分隔符

### <a name="pattern"></a>模式

两个字母或数字后跟七个数字：

- 两个数字或字母 (不区分大小写) 
- 七个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_ireland_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_ireland_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_ireland_eu_passport_date` 格式为 DD MMM/MMM YYYYY (示例 - 01 BEA/MAY 1988 `Keywords_eu_passport_date`) 或找到的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_ireland_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_ireland_eu_passport_number` 中的关键字。

```xml
      <!-- Ireland Passport Number -->
      <Entity id="a2130f27-9ee2-4103-84f9-a6b1ee7d0cbf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_ireland_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passeport numero
- uimhreacha pasanna
- uimhir pas
- uimhir 阶段
- uimhreacha pas
- uimhir cárta
- uimhir chárta

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="ireland-personal-public-service-pps-number"></a>爱尔兰个人公共服务 (PPS) 号码

### <a name="format"></a>格式

旧格式 (2012 年 12 月 31 日) ：
- 七个数字后跟 1-2 个字母

新格式 (2013 年 1 月 1 日及之后) ：
- 七个数字后跟两个字母

### <a name="pattern"></a>模式

旧格式 (2012 年 12 月 31 日) ：
- 七个数字
- 一到两个字母 (不区分大小写) 

新格式 (2013 年 1 月 1 日及之后) ：
- 七个数字
- 字母 (不区分大小写) 字母检查数字
- A-I 或"W"范围中的可选字母

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_ireland_pps 找到与该模式匹配的内容。
- 找到来自Keywords_ireland_eu_national_id_card关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数 Func_ireland_pps 找到与该模式匹配的内容。
- 校验和通过。

```xml
      <!-- Ireland Personal Public Service (PPS) Number -->
      <Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_pps" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_ireland_pps" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

- 客户端标识服务
- identification number
- 个人 ID 号
- 个人公共服务号码
- 个人服务否
- phearsanta seirbhíse poiblí
- pps 否
- pps number
- pps num
- pps 服务否
- ppsn
- ppsno#
- ppsno
- psp
- 公共服务否
- publicserviceno#
- publicserviceno
- 收入和社会保险号码
- rsi no
- rsi number
- rsin
- seirbhís aitheantais 客户端
- uimh
- uimhir aitheantais ch操作
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="ireland-physical-addresses"></a>爱尔兰物理地址

此未解包的命名实体检测与爱尔兰的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="israel-bank-account-number"></a>以色列银行帐号

### <a name="format"></a>格式

13 位数字

### <a name="pattern"></a>模式

格式化：
- 两个数字
- 短划线
- 三个数字
- 短划线
- 八个数字

无格式：
- 	13 个连续的数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式 Regex_israel_bank_account_number 找到与该模式匹配的内容。
- 找到 Keyword_israel_bank_account_number 中的一个关键字。

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- Bank Account Number
- Bank Account
- Account Number
- מספר חשבון בנק


## <a name="israel-national-identification-number"></a>以色列国家标识号

### <a name="format"></a>格式

九个数字

### <a name="pattern"></a>模式

九个连续的数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_israeli_national_id_number 找到与该模式匹配的内容。
- 找到 Keyword_Israel_National_ID 中的一个关键字。
- 校验和通过。

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_israel_national_id"></a>Keyword_Israel_National_ID

-   מספר זהות
-   מספר זיה וי
-   מספר זיהוי ישר אלי      
-   זהותישר אלית
-   هو ية اسرائيل ية عدد
-   هوية إسرائ يلية
-   رقم الهوية
-   عدد هوية فريدة من نوعها
-   idnumber#
-   id number
-   identity no        
-   identitynumber#
-   标识号
-   identitynumber       
-   个人 ID
-   unique id  


## <a name="italy-drivers-license-number"></a>意大利驾驶证号码

此类型实体包含在欧盟驾驶证号码敏感信息类型中。 它还作为独立的敏感信息类型实体提供。

### <a name="format"></a>格式

10 个字母和数字的组合

### <a name="pattern"></a>模式

10 个字母和数字的组合：
- 一个字母 (不区分大小写) 
- 字母"A"或"V" (不区分大小写) 
- 七个数字
- 一个字母 (不区分大小写) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找 `Regex_italy_drivers_license_number` 与模式匹配的内容。
- 找到 或 `Keywords_eu_driver's_license_number` `Keyword_italy_drivers_license_number` 中的关键字。

```xml
    <!-- Italy Driver's license Number -->
    <Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keyword_italy_drivers_license_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente
- patente di guida
- patente guida
- patenti di guida
- patenti guida


## <a name="italy-fiscal-code"></a>意大利财政代码
此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

指定模式中字母和数字的 16 个字符组合

### <a name="pattern"></a>模式

字母和数字的 16 个字符组合：
- 三个字母，对应于系列名称中的前三个辅音
- 三个字母，分别对应名字中的第一个、第三个和第四个辅音
- 两个数字，对应于出生日期的最后一个数字
- 一个对应于出生日期月份字母的字母 - 字母按字母顺序使用，但只有字母 A 到 E、H、L、M、P、R 到 T (因此，January 为 A，10 月为 R) 
- 为区分性别，与当月中的一天对应的两个数字，40 个数字将添加到女士的出生日期
- 四个数字，对应于特定的地区代码，该号码是此人 (的国家/地区代码用于国家/地区) 
- 一个奇偶校验数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_italy_eu_national_id_card` 查找与模式匹配的内容。
- 找到 的  `Keywords_italy_eu_national_id_card` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_italy_eu_national_id_card` 查找与模式匹配的内容。

```xml
      <!-- Italy Fiscal Code -->
      <Entity id="4cd79172-8da9-4ff5-9188-98b1e7e2eca6" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

- codice 会计
- codice fiscale
- codice id personale
- codice personale
- 财务代码
- numero certificato personale
- numero di identific一one fiscale
- numero id personale
- numero personale
- 个人证书编号
- 个人代码
- 个人 ID 代码
- 个人 ID 号
- personalcodeno#
- tax code
- tax id
- tax identification no
- tax identification number
- tax identity number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="italy-passport-number"></a>意大利护照号码

### <a name="format"></a>格式

两个字母或数字后跟七个数字，无空格或分隔符

### <a name="pattern"></a>模式

两个字母或数字后跟七个数字：

- 两个数字或字母 (不区分大小写) 
- 七个数字

### <a name="checksum"></a>校验和

不适用

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_italy_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_italy_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_italy_eu_passport_date` DD MMM/MMM YYYYY 格式的日期 (示例 - 01 GEN/JAN 1988 `Keywords_eu_passport_date`) 或找到的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_italy_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_italy_eu_passport_number` 中的关键字。

```xml
      <!-- Italy Passport Number -->
      <Entity id="39811019-4750-445f-b26d-4c0e6c431544" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_italy_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana passaporto
- passaporto italiana
- passaporto numero
- numéro passeport
- numero di passaporto
- numeri del passaporto
- passeport italien

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="italy-physical-addresses"></a>意大利物理地址

此未解包的命名实体检测与来自意大利的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="italy-value-added-tax-number"></a>意大利增值税编号

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

带可选分隔符的 13 个字符字母数字模式

### <a name="pattern"></a>模式

带可选分隔符的 13 个字符字母数字模式：

- I 或 i
- T 或 t
- 可选空格、点、连字符或逗号
- 11 个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_italy_value_added_tax_number查找与模式匹配的内容。
- 找到来自Keywords_italy_value_added_tax_number关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数Func_italy_value_added_tax_number查找与模式匹配的内容。

```xml
      <!-- Italy Value Added Tax -->
      <Entity id="26a8cc07-2283-4a2a-ab1d-4ab643c4c67f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
          <Match idRef="Keywords_italy_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_italy_value_added_tax_number"></a>Keyword_italy_value_added_tax_number

- vat number
- vat no
- vat#
- 一
- 一#


## <a name="japan-bank-account-number"></a>日本银行帐号

### <a name="format"></a>格式

七个或八个数字

### <a name="pattern"></a>模式

bank account number：
- 七个或八个数字
- bank account branch code：
- 四个数字
- 一个空格或 (划线) 
- 三个数字

校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_jp_bank_account 找到与该模式匹配的内容。
- 找到 Keyword_jp_bank_account 中的一个关键字。
- 下列其中一项为真：
- 函数 Func_jp_bank_account_branch_code 找到与该模式匹配的内容。
- 找到 Keyword_jp_bank_branch_code 中的一个关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_jp_bank_account 找到与该模式匹配的内容。
- 找到 Keyword_jp_bank_account 中的一个关键字。

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_jp_bank_account"></a>Keyword_jp_bank_account

- Checking Account Number
- Checking Account
- Checking Account #
- Checking Acct Number
- Checking Acct #
- Checking Acct No.
- Checking Account No.
- Bank Account Number
- Bank Account
- Bank Account #
- Bank Acct Number
- Bank Acct #
- Bank Acct No.
- Bank Account No.
- Savings Account Number
- Savings Account
- Savings Account #
- Savings Acct Number
- Savings Acct #
- Savings Acct No.
- Savings Account No.
- Debit Account Number
- Debit Account
- Debit Account #
- Debit Acct Number
- Debit Acct #
- Debit Acct No.
- Debit Account No.
- 口座番号
- 銀行口座
- 銀行口座番号
- 総合口座
- 普通預金口座
- 普通口座
- 当座預金口座
- 当座口座
- 預金口座
- 振替口座
- 銀行
- バンク

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

- 支店番号
- 支店コード
- 店番号

## <a name="japan-drivers-license-number"></a>日本驾驶证号码

### <a name="format"></a>格式

12 个数字

### <a name="pattern"></a>模式

12 个连续的数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_jp_drivers_license_number 找到与该模式匹配的内容。
- 找到 Keyword_jp_drivers_license_number 中的一个关键字。

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_jp_drivers_license_number"></a>Keyword_jp_drivers_license_number

- driverlicense
- driverslicense
- driver'slicense
- driverslicenses
- driver'slicenses
- driverlicenses
- dl#
- dls#
- lic#
- lics#
- 運転免許証
- 運転免許
- 免許証
- 免許
- 運転免許証番号
- 運転免許番号
- 免許証番号
- 免許番号
- 運転免許証ナンバー
- 運転免許ナンバー
- 免許証ナンバー
- 転証no
- 転転no
- 証no
- 免
- 運転経歴証明書番号
- 運転経歴証明書
- 転証No。
- 転転no。
- 証No。
- 免。。
- 運転免許証#
- 運転免許#
- 免許証#
- 免許#


## <a name="japan-my-number---corporate"></a>日本我的号码 - 公司

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

13 位数字

### <a name="pattern"></a>模式

13 位数字：

- 一个数字，从 1 到 9
- 12 个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_japanese_my_number_corporate查找与模式匹配的内容。
- 找到来自Keywords_japanese_my_number_corporate关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数Func_japanese_my_number_corporate查找与模式匹配的内容。

```xml
      <!-- Japanese My Number – Corporate -->
      <Entity id="9e0eaf79-ff20-4ffb-b3e4-e7368d5db6ff" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
          <Match idRef="Keywords_japanese_my_number_corporate" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_japan_my_number_corporate"></a>Keyword_japan_my_number_corporate

- 公司编号
- マイナンバー
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 法人番号
- 指定通知書


## <a name="japan-my-number---personal"></a>日本我的号码 - 个人

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

12 位数字

### <a name="pattern"></a>模式

12 位数字：

- 四个数字
- 可选空格、点或连字符
- 四个数字
- 可选空格、点或连字符
- 四个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_japanese_my_number_personal查找与模式匹配的内容。
- 找到来自Keywords_japanese_my_number_personal关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数Func_japanese_my_number_personal查找与模式匹配的内容。

```xml
      <!-- Japanese My Number – Personal -->
      <Entity id="98da8e66-7299-4ebd-9f82-c871ab37d3ef" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_personal" />
          <Match idRef="Keywords_japanese_my_number_personal" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_japanese_my_number_personal" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_japan_my_number_personal"></a>Keyword_japan_my_number_personal

- my number
- マイナンバー
- 個人番号
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 通知カード


## <a name="japan-passport-number"></a>日本护照号码

### <a name="format"></a>格式

两个字母后跟七个数字

### <a name="pattern"></a>模式

两个字母 (不区分大小写) 后跟七个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_jp_passport 找到与该模式匹配的内容。
- 找到 Keyword_jp_passport 中的一个关键字。

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_jp_passport"></a>Keyword_jp_passport

- Passport
- Passport Number
- Passport No.
- Passport #
- パスポート
- パスポート番号
- パスポートナンバー
- パスポート＃
- パスポート#
- パスポパスポパスポ。
- 旅券番号
- 旅券番号＃
- 旅券番号♯
- 旅券ナンバー


## <a name="japan-residence-card-number"></a>日本居民身份证号

### <a name="format"></a>格式

12 个字母和数字

### <a name="pattern"></a>模式

12 个字母和数字：
- 两个字母 (不区分大小写) 
- 八个数字
- 两个字母 (不区分大小写) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式Regex_jp_residence_card_number查找与模式匹配的内容。
- 找到来自Keyword_jp_residence_card_number关键字。

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- 居住地卡号
- 居住卡否
- 居住卡#
- 在留カード番号
- 在留カード
- 在留番号

## <a name="japan-resident-registration-number"></a>日本居民注册号码

### <a name="format"></a>格式

11 个数字

### <a name="pattern"></a>模式

11 个连续的数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_jp_resident_registration_number 找到与该模式匹配的内容。
- 找到 Keyword_jp_resident_registration_number 中的一个关键字。

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_jp_resident_registration_number"></a>Keyword_jp_resident_registration_number

- Resident Registration Number
- Residents Basic Registry Number
- Resident Registration No.
- Resident Register No.
- Residents Basic Registry No.
- Basic Resident Register No.
- 外国人登録証明書番号
- 証明書番号
- 登録番号
- 外国人登録証


## <a name="japan-social-insurance-number-sin"></a>日本社会保险号码 (SIN) 

### <a name="format"></a>格式

7-12 个数字 

### <a name="pattern"></a>模式

7-12 位数字：
- 四个数字
- 连字符 (可选) 
- 六个数字 OR
- 7-12 个连续的数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_jp_sin 找到与该模式匹配的内容。
- 找到 Keyword_jp_sin 中的一个关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_jp_sin_pre_1997 找到与该模式匹配的内容。
- 找到 Keyword_jp_sin 中的一个关键字。

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_jp_sin"></a>Keyword_jp_sin

- Social Insurance No.
- Social Insurance Num
- Social Insurance Number
- 健康保険被保険者番号
- 健保番号
- 基礎年金番号
- 雇用保険被保険者番号
- 雇用保険番号
- 保険証番号
- 社会保険番号
- 可険No。
- 社会保険
- 介護保険
- 介護保険被保険者番号
- 健康保険被保険者整理番号
- 雇用保険被保険者整理番号
- 厚生年金
- 厚生年金被保険者整理番号


## <a name="lab-test-terms"></a>实验室测试术语

此未解包的命名实体可检测与实验室测试相关的术语，例如 *，为进行实验室测试的项*。 它仅支持英语术语。

### <a name="confidence-level"></a>置信度

高


## <a name="latvia-drivers-license-number"></a>拉脱维亚驾驶证号码

### <a name="format"></a>格式

三个字母后跟六个数字

### <a name="pattern"></a>模式

三个字母和六个数字：

- 三个字母 (不区分大小写) 
- 六个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_latvia_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_latvia_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Latvia Driver's License Number -->
      <Entity id="ec996de0-30f2-46b1-b192-4d2ff8805fa7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_latvia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver s_license_number

- autovad的t个ja apliec以ba
- autovad的t个ja apliec以bas
- vad的tja apliec以ba


## <a name="latvia-passport-number"></a>拉脱维亚护照号码

### <a name="format"></a>格式

两个字母或数字后跟七个数字，无空格或分隔符

### <a name="pattern"></a>模式

两个字母或数字后跟七个数字：

- 两个数字或字母 (不区分大小写) 
- 七个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_latvia_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_latvia_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_eu_passport_date1` DD.MM.YYYY 格式的日期或找到 `Keywords_eu_passport_date` 的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_latvia_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_latvia_eu_passport_number` 中的关键字。

```xml
      <!-- Latvia Passport Number -->
      <Entity id="23ae25ec-cc28-421b-b77a-3054eadf1ede" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- pase numurs
- pase numur
- pases numuri
- pases nr
- passeport no
- n° du Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="latvia-personal-code"></a>拉脱维亚个人代码

### <a name="format"></a>格式

11 个数字和一个可选连字符

### <a name="pattern"></a>模式

旧格式

11 个数字和连字符：

- 六个数字，对应于 DDMMYY (出生日期) 
- 连字符
- 一个数字，对应于 19 世纪 ("0"，"1"对应于 20 世纪，"2"对应于 21 世纪) 
- 四个数字，随机生成

新格式

11 个数字

- 两个数字"32"
- 九个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_latvia_eu_national_id_card` 或正则表达式 `Regex_latvia_eu_national_id_card_new_format` 找到与模式匹配的内容。
- 找到 的  `Keywords_latvia_eu_national_id_card` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_latvia_eu_national_id_card` 或正则表达式 `Regex_latvia_eu_national_id_card_new_format` 找到与模式匹配的内容。

```xml
      <!-- Latvia Personal Code -->
      <Entity id="03fcf763-27c2-49ed-9422-2641c6c895c9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Keywords

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- 管理编号
- alvas nē
- birth number
- citizen number
- 用户编号
- 电子统计数字
- 电子数字
- 财务代码
- 医疗保健用户数
- id#
- id-code
- identification number
- identifik以cijas numurs
- id-number
- individual number
- latvija alva
- nacionlais id
- national id
- national identifying number
- national identity number
- national insurance number
- national register number
- nodokļa numurs
- nodokļu ID
- nodokļu identifik以cija numurs
- 个人证书编号
- 个人代码
- 个人 ID 代码
- 个人 ID 号
- 个人标识代码
- 个人标识符
- 个人标识号
- 个人编号
- 个人数字代码
- personalcodeno#
- personas kods
- 总体标识代码
- 公共服务号码
- registration number
- 收入编号
- social insurance number
- social security number
- 省税代码
- tax file number
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- 用户编号


## <a name="latvia-physical-addresses"></a>拉脱维亚物理地址

此未解包的命名实体检测与拉脱维亚的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="liechtenstein-physical-addresses"></a>列支敦士登物理地址

此未解包的命名实体检测与列支敦士登的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="lifestyles-that-relate-to-medical-conditions"></a>与医疗状况相关的生活方式

此未解包的命名实体会检测与可能导致医学状况（如医生）的生活方式相关的 *术语*。 它仅支持英语术语。

### <a name="confidence-level"></a>置信度

高


## <a name="lithuania-drivers-license-number"></a>立陶宛驾驶证号码

### <a name="format"></a>格式

八个数字（不含空格和分隔符）

### <a name="pattern"></a>模式

八个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_lithuania_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_lithuania_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Lithuania Driver's License Number -->
      <Entity id="86f7628b-e0f4-4dc3-9fbc-e4300e4c7d78" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver s_license_number

- vair一pažymėjimas
- vair一pažymėjimo jo numeris
- vair一pažymėjimo jo pažymėjimo num进行


## <a name="lithuania-personal-code"></a>立陶宛个人代码

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

11 个数字，不带空格和分隔符

### <a name="pattern"></a>模式

11 个数字，不带空格和分隔符：

- 一个数字 (1-6) 对应于性别和出生日期的世纪
- 六个数字，对应于出生日期 (YYMMDD) 
- 三个数字，对应于出生日期的序列号
- 一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_lithuania_eu_tax_file_number` 查找与模式匹配的内容。
- 找到 的  `Keywords_lithuania_eu_tax_file_number` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_lithuania_eu_tax_file_number` 查找与模式匹配的内容。

```xml
      <!-- Lithuania Personal Code -->
      <Entity id="cd6d3786-8ec3-4524-a2cf-1e0095379171" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_lithuania_eu_telephone_number" />
            <Match idRef="Keywords_lithuania_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

- asmeninis skaitmeninis kodas
- asmens kodas
- citizen service number
- mokesčių ID
- mokesčių identif一vimas numeris
- mokesčių identif一vimo numeris
- mokesčių numeris
- national identification number
- 个人代码
- 个人数字代码
- pilieio paslaugos numeris
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- un则lus identif一vimo kodas
- un则lus identif一vimo numeris
- 唯一标识号
- 唯一标识号
- uniqueidentityno#


## <a name="lithuania-physical-addresses"></a>立陶宛物理地址

此未解包的命名实体检测与立陶宛的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="lithuania-passport-number"></a>立陶宛护照号码

### <a name="format"></a>格式

八个数字或字母，无空格或分隔符

### <a name="pattern"></a>模式

八个数字或字母 (不区分大小写) 

### <a name="checksum"></a>校验和

不适用

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_lithuania_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_lithuania_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_eu_passport_date3` 格式为 DD MM YYYY 的日期或找到 `Keywords_eu_passport_date` 的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_lithuania_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_lithuania_eu_passport_number` 中的关键字。

```xml
      <!-- Lithuania Passport Number -->
      <Entity id="1b79900f-047b-4c3f-846f-7d73b5534bce" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- paso numeris
- paso num一i
- paso nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="luxemburg-drivers-license-number"></a>百度达驾驶证号码

### <a name="format"></a>格式

6 个数字，不带空格和分隔符

### <a name="pattern"></a>模式

六个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_luxemburg_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_luxemburg_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Luxemburg Driver's License Number -->
      <Entity id="89daf717-1544-4860-9a2e-fc9166dd8852" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver s_license_number

- fahrerlaubnis
- Führerschhrin

## <a name="luxemburg-national-identification-number-natural-persons"></a>阿比塞明卡国民身份证号 (自然人) 

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

13 个数字，无空格或分隔符

### <a name="pattern"></a>模式

13 个数字：

- 11 个数字
- 两个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_luxemburg_eu_tax_file_number` 查找与模式匹配的内容。
- 找到 的  `Keywords_luxemburg_eu_national_id_card` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_luxemburg_eu_tax_file_number` 查找与模式匹配的内容。


```xml
      <!-- Luxemburg National Identification Number (Natural persons) -->
      <Entity id="aaf661ed-29ec-426d-8bf9-880cad298ebb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

- eindeutige id
- eindeutige id-nummer
- eindeutigeid#
- id personnelle
- idpersonnelle#
- idpersonnelle
- 单个代码
- individual id
- 个人标识
- 个人标识
- numéro d'identification personnel
- 个人 ID
- 个人标识
- 个人标识
- personalidno#
- personalidnumber#
- persönliche identifikationsnummer
- unique id
- 唯一标识
- uniqueidkey#


## <a name="luxemburg-national-identification-number-non-natural-persons"></a>阿比塞卡 (非自然人的身份证号) 

### <a name="format"></a>格式

11 个数字

### <a name="pattern"></a>模式

11 个数字

- 两个数字
- 可选空格
- 三个数字
- 可选空格
- 三个数字
- 可选空格
- 两个数字
- 一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_luxemburg_eu_tax_file_number_non_natural` 查找与模式匹配的内容。
- 找到 的  `Keywords_luxemburg_eu_tax_file_number` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_luxemburg_eu_tax_file_number_non_natural` 查找与模式匹配的内容。

```xml
      <!-- Luxemburg National Identification Number (Non-natural persons) -->
      <Entity id="84bffa3a-d805-4788-a613-b1e4df3804cf" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

- carte de sécurité sociale
- étain non
- étain#
- identifiant d'imp与t
- luxembourg tax identif一tiounsnummer
- numéro d'étain
- numéro d'identification fiscal luxembourgeois
- numéro d'identification fiscale
- social security
- sozialunterstützung
- sozialversécherung
- sozialversicherungsaus以
- steier id
- steier identifikatiounsnummer
- steier nummer
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- zinn#
- zinn
- zinnzahl


## <a name="luxemburg-passport-number"></a>百里达护照号码

### <a name="format"></a>格式

八个数字或字母，无空格或分隔符

### <a name="pattern"></a>模式

八个数字或字母 (不区分大小写) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_luxemburg_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_luxemburg_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_eu_passport_date3` 格式为 DD MM YYYY 的日期或找到 `Keywords_eu_passport_date` 的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_luxemburg_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_luxemburg_eu_passport_number` 中的关键字。

```xml
      <!-- Luxemburg Passport Number -->
      <Entity id="81d5c027-bed9-4421-91a0-3b2e55b3eb85" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_luxemburg_eu_passport_number"></a>Keywords_luxemburg_eu_passport_number
- aus一snummer
- 卢森堡传递
- 卢森堡通道
- 卢森堡护照
- 无通道
- no-reisepass
- nr-reisepass
- numéro de passeport
- pass net
- pass nr
- passnummer
- passeport nombre
- reisep的sse
- reisepass-nr
- reisepassnummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="luxemburg-physical-addresses"></a>百里达物理地址

此未解包的命名实体可检测与来自 Windowsemtu 的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="malaysia-identification-card-number"></a>马来西亚身份证号

### <a name="format"></a>格式

12 个数字（包含可选连字符）

### <a name="pattern"></a>模式

12 个数字：
- 六个数字，格式为 YYMMDD，表示出生日期
- 划线 (可选) 
- 双字母的出生日期位置代码
- 划线 (可选) 
- 三个随机数字
- 一位数性别代码

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式 Regex_malaysia_id_card_number 找到与该模式匹配的内容。
- 找到 Keyword_malaysia_id_card_number 中的一个关键字。

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_malaysia_id_card_number"></a>Keyword_malaysia_id_card_number

- 数字应用程序卡
- i/c
- i/c 否
- ic
- ic no
- id card
- identification Card
- identity card
- k/p
- k/p no
- kad akuan diri
- kad aplikasi digital
- kadenalan（马来西亚）
- kp
- kp no
- mykad
- mykas
- mykid
- mypr
- mytentera
- malaysia identity card
- 用户标识卡
- nric
- 个人标识卡


## <a name="malta-drivers-license-number"></a>马耳他驾驶证号码

### <a name="format"></a>格式

指定模式中两个字符和六个数字的组合

### <a name="pattern"></a>模式

两个字符和六个数字的组合：

- 两个字符 (数字或字母，不区分大小写) 
- 可选 (空格) 
- 三个数字
- 可选 (空格) 
- 三个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_malta_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_malta_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Malta Driver's License Number -->
      <Entity id="a3bdaa4a-8371-4735-8fa5-56ee0fb4afc4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_malta_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver s_license_number

- liċenzja tas-sewqan
- liċenzji tas-sewwieq


## <a name="malta-identity-card-number"></a>马耳他身份证号码

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

七个数字后跟一个字母

### <a name="pattern"></a>模式

七个数字后跟一个字母：

- 七个数字
- "M、G、A、P、L、H、B、Z"中的一个字母 (不区分大小写) 

### <a name="checksum"></a>校验和

不适用

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_malta_eu_national_id_card` 与模式匹配的内容。
- 找到 的  `Keywords_malta_eu_national_id_card` 关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 正则表达式查找  `Regex_malta_eu_national_id_card` 与模式匹配的内容。

```xml
      <!-- Malta Identity Card Number -->
      <Entity id="854b36b3-a388-4ac8-a4ec-677c2b5e4356" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

- citizen service number
- id tat-taxxa
- identifjet numru tal-jett
- kodiċi数字 personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- 个人数字代码
- 唯一标识号
- 唯一标识号
- uniqueidentityno#


## <a name="malta-passport-number"></a>马耳他护照号码

### <a name="format"></a>格式

七个数字，不带空格或分隔符

### <a name="pattern"></a>模式

七个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_malta_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_malta_eu_passport_number` 中的关键字。
- 找到的关键字来自`Keywords_eu_passport_date`

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_malta_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_malta_eu_passport_number` 中的关键字。

```xml
      <!-- Malta Passport Number -->
      <Entity id="b2b21198-48f9-4d13-b2a5-03969bff0fb8" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
          <Match idRef="Keywords_eu_passport_date" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- numru tal-passaport
- numri tal-passaport
- Nru tal-passaport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="malta-physical-addresses"></a>马耳他物理地址

此未解包的命名实体检测与来自马耳他的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="malta-tax-identification-number"></a>马耳他税务标识号

### <a name="format"></a>格式

对于马耳他语：
- 指定模式中的七个数字和一个字母

非马耳他语公民和马耳他语实体：
- 九个数字

### <a name="pattern"></a>模式

马耳他语：七个数字和一个字母

- 七个数字
- 一个字母 (不区分大小写) 

非马耳他公民和马耳他实体：9 个数字

- 九个数字

### <a name="checksum"></a>校验和

不适用

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式或`Regex_malta_eu_tax_file_number``Regex_malta_eu_tax_file_number_non_maltese_national`查找与模式匹配的内容。
- 找到 的  `Keywords_malta_eu_tax_file_number` 关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 正则表达式或`Regex_malta_eu_tax_file_number``Regex_malta_eu_tax_file_number_non_maltese_national`查找与模式匹配的内容。

```xml
      <!-- Malta Tax ID Number -->
      <Entity id="ec830c63-65f4-45d0-9d8c-910dc8334b20" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- citizen service number
- id tat-taxxa
- identifjet numru tal-jett
- kodiċi数字 personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- 个人数字代码
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- 唯一标识号
- 唯一标识号
- uniqueidentityno#

## <a name="medical-specialities"></a>医疗特殊性

此未解包的命名实体可检测与医疗特殊性相关的术语，例如 *"真眼"*。  它仅支持英语术语。

### <a name="confidence-level"></a>置信度

高

## <a name="medicare-beneficiary-identifier-mbi-card"></a>MBI 卡中的 (性) 标识符

### <a name="format"></a>格式

11 个字符字母数字模式

### <a name="pattern"></a>模式

- 1 到 9 之间的一个数字
- 一个字母，不包括 S、L、O、I、B、Z
- 一个数字或字母，不包括 S、L、O、I、B、Z
- 一个数字
- 可选连字符
- 一个字母，不包括 S、L、O、I、B、Z
- 一个数字或字母，不包括 S、L、O、I、B、Z
- 一个数字
- 可选连字符
- 两个字母，不包括 S、L、O、I、B、Z
- 两个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_mbi_card` 与模式匹配的内容。
- 找到 的  `Keyword_mbi_card` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_mbi_card` 与模式匹配的内容。

```xml
    <!-- Medicare Beneficiary Identifier (MBI) card -->
      <Entity id="f753a286-f5cc-47e6-a592-4be25fd02591" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_mbi_card" />
          <Match idRef="Keyword_mbi_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_mbi_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_mbi_card"></a>Keyword_mbi_card

- mbi
- mbi#
- 一名收入#
- 一个优势标识符
- 一名受益者否
- 一名收入者编号
- 一名收入#


## <a name="mexico-unique-population-registry-code-curp"></a>墨西哥唯一总体注册表代码 (CURP) 

### <a name="format"></a>格式

18 个字符字母数字模式

### <a name="pattern"></a>模式

- 四个字母 (不区分大小写) 
- 六个数字，表示有效日期
- 字母 - H/h 或 M/m
- 指示有效"墨西哥"状态代码的两个字母
- 三个字母
- 一个字母或数字
- 一个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_mexico_population_registry_code` 查找与模式匹配的内容。
- 找到 的  `Keyword_mexico_population_registry_code` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_mexico_population_registry_code` 查找与模式匹配的内容。

```xml
    <!-- Mexico Unique Population Registry Code (CURP) -->
      <Entity id="e905ad4d-5a74-406d-bf36-b1efca798af4" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_mexico_population_registry_code" />
          <Match idRef="Keyword_mexico_population_registry_code" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_mexico_population_registry_code" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_mexico_population_registry_code"></a>Keyword_mexico_population_registry_code

- Clave Única de Registro de Población
- Clave Unica de Registro de Poblacion
- 唯一填充注册表代码 
- 唯一总体代码
- CURP
- 个人 ID
- 唯一 ID
- personalid
- personalidnumber
- uniqueidkey
- uniqueidnumber
- clave única
- clave unica
- clave 个人 Identidad
- personal Identidad Clave
- ClaveÚnica
- claveunica
- clavepersonalIdentidad


## <a name="netherlands-citizens-service-bsn-number"></a>荷兰公民服务号码 (BSN) 号码

### <a name="format"></a>格式

包含可选空格的八个或九个数字

### <a name="pattern"></a>模式

八个九个数字：
- 三个数字
- 一个 (可选) 
- 三个数字
- 一个 (可选) 
- 2-3 个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_netherlands_bsn 找到与该模式匹配的内容。
- 找到 Keyword_netherlands_bsn 中的一个关键字。
- 校验和通过。

```xml
      <!-- Netherlands Citizen's Service (BSN) Number -->
      <Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_bsn" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card

- bsn#
- bsn
- servicenummer
- citizen service number
- person number
- 个人编号
- 个人数字代码
- 与人员相关的号码
- persoonlijk nummer
- persoonlijke numerieke 代码
- persoonsgeoonden
- persoonsnummer
- sociaal-fiscaal nummer
- social-fiscal number
- sofi
- sofinummer
- uniek identificatienummer
- uniek identit一snummer
- 唯一标识号
- 唯一标识号
- uniqueidentityno#


## <a name="netherlands-drivers-license-number"></a>荷兰驾驶证号码

### <a name="format"></a>格式

不带空格和分隔符的 10 个数字

### <a name="pattern"></a>模式

10 个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_netherlands_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_netherlands_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Netherlands Driver's License Number -->
      <Entity id="6247fbea-ab80-4be5-8233-308b7c031401" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
            </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver s_license_number

- permis de conduire
- rijbewijs
- rijbewijsnummer
- rijbewijzen
- rijbewijs nummer
- rijbewijsnummers


## <a name="netherlands-passport-number"></a>荷兰护照号码

### <a name="format"></a>格式

九个字母或数字，无空格或分隔符

### <a name="pattern"></a>模式

九个字母或数字

### <a name="checksum"></a>校验和

不适用

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_netherlands_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_netherlands_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_netherlands_eu_passport_date` DD MMM/MMM YYYYY 格式的日期 (示例 - 26 MAA/MAR 2012) 

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_netherlands_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_netherlands_eu_passport_number` 中的关键字。

```xml
      <!-- Netherlands Passport Number -->
      <Entity id="61786727-bafd-45f6-94d9-888d815e228e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Regex_netherlands_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- paspoort nummer
- paspoortnummers
- paspoortnummer
- paspoort nr


## <a name="netherlands-physical-addresses"></a>荷兰物理地址

此未解包的命名实体检测与荷兰物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="netherlands-tax-identification-number"></a>荷兰税务标识号

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

九个数字，不带空格或分隔符

### <a name="pattern"></a>模式

九个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_netherlands_eu_tax_file_number` 查找与模式匹配的内容。
- 找到 的  `Keywords_netherlands_eu_tax_file_number` 关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数  `Func_netherlands_eu_tax_file_number` 查找与模式匹配的内容。

```xml
      <!-- Netherlands Tax Identification Number -->
      <Entity id="01f42a64-eba7-4892-a67b-398237e4ade2" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

- btw nummer
- hollânske 税务识别
- hulandes impuesto id number
- hulandes impuesto identification
- identificatienummer belasting
- identificatienummer van belasting
- impuesto 标识号
- impuesto number
- nederlands belasting id nummer
- nederlands belasting identificatie
- nederlands belasting identificatienummer
- nederlands belastingnummer
- nederlandse belasting identificatie
- netherlands tax identifications
- 荷兰的税务标识
- netherlands tin
- 荷兰的 tin
- tax id
- tax identification no
- tax identification number
- tax identification tal
- tax no#
- tax no
- tax number
- tax registration number
- tax tal
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="netherlands-value-added-tax-number"></a>荷兰增值税编号

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

14 个字符字母数字模式

### <a name="pattern"></a>模式

14 字符字母数字模式：

- N 或 n
- L 或 l
- 可选空格、点或连字符
- 九个数字
- 可选空格、点或连字符
- B 或 b
- 两个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_netherlands_value_added_tax_number查找与模式匹配的内容。
- 找到来自Keywords_netherlands_value_added_tax_number关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数Func_netherlands_value_added_tax_number查找与模式匹配的内容。

```xml
      <!-- Netherlands Value Added Tax Number -->
      <Entity id="4f320d9b-4972-41ae-b337-88d499bb1ade" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
          <Match idRef="Keywords_netherlands_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_netherlands_value_added_tax_number"></a>Keyword_netherlands_value_added_tax_number

- vat number
- vat no
- vat#
- wearde tafoege tax getal
- btw n与mer
- btw-nummer


## <a name="new-zealand-bank-account-number"></a>新西兰银行帐号

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

带可选分隔符的 14 位到 16 位模式

### <a name="pattern"></a>模式

带可选分隔符的 14 位到 16 位模式：

- 两个数字
- 可选连字符或空格
- 三到四个数字
- 可选连字符或空格
- 七个数字
- 可选连字符或空格
- 两到三个数字
- 选项连字符或空格

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_new_zealand_bank_account_number查找与模式匹配的内容。
- 找到来自Keywords_new_zealand_bank_account_number关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数Func_new_zealand_bank_account_number查找与模式匹配的内容。

```xml
      <!-- New Zealand Bank Account Number -->
      <Entity id="1a97fc2b-dd2f-48f1-bc4e-2ddf25813956" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
          <Match idRef="Keywords_new_zFealand_bank_account_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_new_zealand_bank_account_number"></a>Keyword_new_zealand_bank_account_number

- account number
- bank account
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr


## <a name="new-zealand-drivers-license-number"></a>新西兰驾驶证号码

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

八个字符字母数字模式

### <a name="pattern"></a>模式

八个字符字母数字模式

- 两个字母
- 六个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_newzealand_driver_license_number查找与模式匹配的内容。
- 找到来自Keywords_newzealand_driver_license_number关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数Func_newzealand_driver_license_number查找与模式匹配的内容。

```xml
      <!-- New Zealand Driver License Number -->
      <Entity id="1924b377-d287-49c9-a737-cfe7a8a2615a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
          <Match idRef="Keywords_newzealand_driver_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_new_zealand_drivers_license_number"></a>Keyword_new_zealand_drivers_license_number

- driverlicence
- driverlicences
- driver lic
- driver licence
- driver licences
- driverslic
- driverslicence
- driverslicences
- drivers lic
- drivers lics
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's licence
- driver's licences
- driverlic#
- driverlics#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver licence#
- driver licences#
- driverslic#
- driverslics#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's licence#
- driver's licences#
- international driving permit
- international driving permits
- nz 汽车关联
- 新西兰汽车关联


## <a name="new-zealand-inland-revenue-number"></a>新西兰的收入数字

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

八个或九个数字（带可选分隔符）

### <a name="pattern"></a>模式

八个或九个数字（带可选分隔符）

- 两个或三个数字
- 可选空格或连字符
- 三个数字
- 可选空格或连字符
- 三个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_new_zealand_inland_revenue_number查找与模式匹配的内容。
- 找到来自Keywords_new_zealand_inland_revenue_number关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数Func_new_zealand_inland_revenue_number查找与模式匹配的内容。

```xml
      <!-- New Zealand Inland Revenue Number -->
      <Entity id="dd0fe2bc-7bcf-455f-bac1-83b1e3eb25fd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
          <Match idRef="Keywords_new_zealand_inland_revenue_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_new_zealand_inland_revenue_number"></a>Keyword_new_zealand_inland_revenue_number

- 否。
- ird 否#
- nz ird
- 新西兰 ird
- ird number
- 一元收入数


## <a name="new-zealand-ministry-of-health-number"></a>新西兰卫生服务局号码

### <a name="format"></a>格式

三个字母和四个数字

### <a name="pattern"></a>模式

- 三个字母 (区分大小写) "I"和"O"除外
- 四个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_new_zealand_ministry_of_health_number 找到与该模式匹配的内容。
- 找到 Keyword_nz_terms 中的一个关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_new_zealand_ministry_of_health_number 找到与该模式匹配的内容。
- 校验和通过。

```xml
    <!-- New Zealand Health Number -->
    <Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
          <Match idRef="Keyword_nz_terms" />
      </Pattern>
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
       </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_nz_terms"></a>Keyword_nz_terms

- NHI
- New Zealand
- National Health Index
- NHI#
- National Health Index#


## <a name="new-zealand-physical-addresses"></a>新西兰物理地址

此未解包的命名实体检测与新西兰物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="new-zealand-social-welfare-number"></a>新西兰社会电话号码

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

九个数字

### <a name="pattern"></a>模式

九个数字

- 三个数字
- 可选连字符
- 三个数字
- 可选连字符
- 三个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_newzealand_social_welfare_number查找与模式匹配的内容。
- 找到来自Keywords_newzealand_social_welfare_number关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数Func_newzealand_social_welfare_number查找与模式匹配的内容。

```xml
      <!-- Newzealand Social Welfare Number -->
      <Entity id="20f3c48d-4ac1-4cd2-86bd-34ecc1826e9d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
          <Match idRef="Keywords_newzealand_social_welfare_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_new_zealand_social_welfare_number"></a>Keyword_new_zealand_social_welfare_number

- 社交#
- 社交#
- social一号。
- social 时号
- swn#


## <a name="norway-identification-number"></a>挪威标识号

### <a name="format"></a>格式

11 个数字

### <a name="pattern"></a>模式

11 个数字：
- 六个数字，格式为 DDMMYY，表示出生日期
- 三位数个人号码
- 两个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_norway_id_number 找到与该模式匹配的内容。
- 找到 Keyword_norway_id_number 中的一个关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_norway_id_numbe 找到与该模式匹配的内容。
- 校验和通过。

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_norway_id_number"></a>Keyword_norway_id_number

- Personal identification number
- Norwegian ID Number
- ID Number
- 标识
- Personnummer
- Fødselsnummer


## <a name="norway-physical-addresses"></a>挪威物理地址

此未解包的命名实体检测与挪威的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="philippines-unified-multi-purpose-identification-number"></a>菲律宾统一的多用途标识号

### <a name="format"></a>格式

12 个数字，通过连字符分隔 

### <a name="pattern"></a>模式

12 个数字：
- 四个数字
- 连字符
- 七个数字
- 连字符
- 一个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式 Regex_philippines_unified_id 找到与该模式匹配的内容。
- 找到 Keyword_philippines_id 中的一个关键字。

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_philippines_id"></a>Keyword_philippines_id

- Unified Multi-Purpose ID
- UMID
- Identity Card
- Pinag-isang Multi-Layunin ID


## <a name="poland-drivers-license-number"></a>波兰驾驶证号码

### <a name="format"></a>格式

14 个数字，包含两个正斜杠

### <a name="pattern"></a>模式

14 个数字和两个正斜杠：

- 五个数字
- 正斜杠
- 两个数字
- 正斜杠
- 七个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_poland_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_poland_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Poland Driver's License Number -->
      <Entity id="24d51f99-ee9e-4060-a077-cae58cab1ee4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_poland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver s_license_number

- prawo jazdy
- prawa jazdy


## <a name="poland-identity-card"></a>波兰身份证

### <a name="format"></a>格式

三个字母和六个数字

### <a name="pattern"></a>模式

三个字母 (不区分大小写) 后跟六个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_polish_national_id 找到与该模式匹配的内容。
- 找到 Keyword_polish_national_id_passport_number 中的一个关键字。
- 校验和通过。

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- ）Osobisty
- Numer dowodu osobistego
- Nazwa i numer dowodu osobistego
- Nazwa i nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- dow. os.



## <a name="poland-national-id-pesel"></a>波兰国家/ (PESEL) 

### <a name="format"></a>格式

11 个数字

### <a name="pattern"></a>模式

- 六个数字，表示 YYMMDD 格式的出生日期
- 四个数字
- 一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_pesel_identification_number 找到与该模式匹配的内容。
- 找到 Keyword_pesel_identification_number 中的一个关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_pesel_identification_number 找到与该模式匹配的内容。
- 校验和通过。

```xml
      <!-- Poland National ID (PESEL) -->
      <Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_pesel_identification_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_pesel_identification_number"></a>Keyword_pesel_identification_number

- dowód osobisty
- dowódosobisty
- niepowtarzalny numer
- niepowtarzalnynumer
- nr.-pesel
- nr-pesel
- numer identyfikacyjny
- pesel
- tożsamości narodowej


## <a name="poland-passport-number"></a>波兰护照号码

此敏感信息类型实体包含在欧盟护照号码敏感信息类型中。 它还作为独立的敏感信息类型实体提供。

### <a name="format"></a>格式

两个字母和七个数字

### <a name="pattern"></a>模式

两个字母 (不区分大小写) 后跟七个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 `Func_polish_passport_number_v2` 查找与模式匹配的内容。
- 校验和通过。
- 找到 或 `Keywords_eu_passport_number` `Keyword_polish_national_passport_number` 中的关键字。
- 找到 的 `Keywords_eu_passport_date` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 `Func_polish_passport_number_v2` 查找与模式匹配的内容。
- 校验和通过。
- 找到 或 `Keywords_eu_passport_number` `Keyword_polish_national_passport_number` 中的关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数 `Func_polish_passport_number_v2` 查找与模式匹配的内容。
- 校验和通过。

```xml
      <!-- Poland Passport Number -->
      <Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_passport_number_v2" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keyword_polish_national_passport_number"></a>Keyword_polish_national_passport_number

- numer paszportu
- numery paszportów
- numery paszportowe
- nr paszportu
- nr. paszportu
- nr paszportów
- n° passeport
- passeport n°

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="poland-physical-addresses"></a>波兰物理地址

此未解包的命名实体检测与来自波兰的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="poland-regon-number"></a>波兰 REGON 号码

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

9 位数字或 14 位数字

### <a name="pattern"></a>模式

九位数字或 14 位数字：

- 九个数字或
- 九个数字
- hyphen
- 五个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_polish_regon_number查找与模式匹配的内容。
- 找到来自Keywords_polish_regon_number关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数Func_polish_regon_number查找与模式匹配的内容。

```xml
      <!-- Polish REGON Number  -->
      <Entity id="fc87b421-f437-4f8b-b739-29a735ead0d9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_regon_number" />
          <Match idRef="Keywords_polish_regon_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_regon_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Keywords

#### <a name="keywords_poland_regon_number"></a>Keywords_poland_regon_number

- regon id
- 统计数字
- 统计 ID
- 统计否
- regon number
- reg一维#
- regonno#
- 公司 ID
- companyid#
- companyidno#
- numer statystyczny
- numeru regon
- numerstatystyczny#
- numeruregon#


## <a name="poland-tax-identification-number"></a>波兰税务标识号

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

11 个数字，无空格或分隔符

### <a name="pattern"></a>模式

11 个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_poland_eu_tax_file_number` 查找与模式匹配的内容。
- 找到 的  `Keywords_poland_eu_tax_file_number` 关键字。


```xml
      <!-- Poland Tax Identification Number -->
      <Entity id="1ff28b4d-40f2-49e9-b677-9606a88e2bca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

- nip#
- nip
- numer identyfikacji podatkowej
- numeridentyfikacjipodatkowej#
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- vat id#
- vat id
- vat no
- vat number
- vatid#
- vatid
- vatno#


## <a name="portugal-citizen-card-number"></a>葡萄牙公民卡号

### <a name="format"></a>格式

八个数字

### <a name="pattern"></a>模式

八个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式 Regex_portugal_citizen_card 找到与该模式匹配的内容。
- 找到 Keyword_portugal_citizen_card 中的一个关键字。

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_portugal_citizen_card"></a>Keyword_portugal_citizen_card

- 将 de identidade
- cartão de cidadão
- citizen card
- 文档编号
- documento de identificação
- id number
- identification no
- identification number
- identity card no
- 标识卡号
- national id card
- nic
- número bi de portugal
- número de identificação
- número de identificação fiscal
- número do documento
- portugal bi number


## <a name="portugal-drivers-license-number"></a>葡萄牙驾驶证号码

### <a name="format"></a>格式

两个模式 - 两个字母后跟 5-8 个数字（带特殊字符）

### <a name="pattern"></a>模式

模式 1：两个字母后跟 5/6 特殊字符：
- 两个字母 (不区分大小写) 
- 一个连字符 
- 五个或六个数字
- 一个空格
- 一位数字

模式 2：一个字母后跟 6/8 个数字（带特殊字符）：
- 一个字母 (不区分大小写) 
- 一个连字符 
- 六个或八个数字
- 一个空格
- 一个数字


### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_portugal_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_portugal_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Portugal Driver's License Number -->
      <Entity id="977f1e5a-2c33-4bcc-b516-95bb275cff23" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_portugal_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver s_license_number

- cart cart cart de motorista
- cart cart motorista
- cart cart cart de habilitação
- cart cart cart habilitação
- número de licença
- número licença
- permissão de condução
- permissão condução
- 葡萄牙利cença condução
- carta de condução


## <a name="portugal-passport-number"></a>葡萄牙护照号码

### <a name="format"></a>格式

一个字母后跟 6 个数字，无空格或分隔符

### <a name="pattern"></a>模式

一个字母后跟六个数字：

- 一个字母 (不区分大小写) 
- 六个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_portugal_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_portugal_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_eu_passport_date1` DD.MM.YYYY 格式的日期或找到 `Keywords_eu_passport_date` 的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_portugal_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_portugal_eu_passport_number` 中的关键字。

```xml
      <!-- Portugal Passport Number -->
      <Entity id="080a52fd-a7bc-431e-b54d-51f08f59db11" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número do passaporte
- 葡萄牙语 passport
- 葡萄牙语通道
- 葡萄牙语 passaporte
- passaporte n？
- passeport n°
- números de passaporte
- 葡萄牙语护照
- número passaporte
- números passaporte

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="portugal-physical-addresses"></a>葡萄牙物理地址

此未解包的命名实体检测与来自葡萄牙的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="portugal-tax-identification-number"></a>葡萄牙税务标识号

### <a name="format"></a>格式

九个数字（带可选空格）

### <a name="pattern"></a>模式

- 三个数字
- 可选空格
- 三个数字
- 可选空格
- 三个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_portugal_eu_tax_file_number` 查找与模式匹配的内容。
- 找到 的  `Keywords_portugal_eu_tax_file_number` 关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数  `Func_portugal_eu_tax_file_number` 查找与模式匹配的内容。

```xml
      <!-- Portugal Tax Identification Number -->
      <Entity id="65372402-3131-4f1e-9983-4439841d1f15" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_portugal_eu_tax_file_number"></a>Keywords_portugal_eu_tax_file_number

- cpf#
- cpf
- nif#
- nif
- número de identificação fisca
- numero fiscal
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="romania-drivers-license-number"></a>罗马尼亚驾驶证号码

### <a name="format"></a>格式

一个字符后跟八个数字

### <a name="pattern"></a>模式

一个字符后跟八个数字：
- 一个字母 (不区分大小写) 或数字
- 八个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_romania_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_romania_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Romania Driver's License Number -->
      <Entity id="b5511ace-2fd8-4ae4-b6fc-c7c6e4689e3c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_romania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver s_license_number

- permis de conducere
- permisului de conducere
- permisului conducere
- permisele de conducere
- permisele conducere
- permis conducere


## <a name="romania-passport-number"></a>罗马尼亚护照号码

### <a name="format"></a>格式

八个或九个数字，不带空格和分隔符

### <a name="pattern"></a>模式

八个或九个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_romania_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_romania_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_romania_eu_passport_date` DD MMM/MMM YY 格式的日期 (示例- 01 2 月/2 月 10) 或 `Keywords_eu_passport_date` 找到的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_romania_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_romania_eu_passport_number` 中的关键字。

```xml
      <!-- Romania Passport Number -->
      <Entity id="5d31b90c-7fe2-4a76-a14b-767b8fd19d6c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_romania_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numrul pașaportului numarul pasaportului numerele pașaportului Pașaport nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="romania-personal-numeric-code-cnp"></a>CNP (罗马尼亚个人) 

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

不带空格和分隔符的 13 个数字

### <a name="pattern"></a>模式

- 一个数字，从 1 到 9
- 六个数字，表示 YYMMDD (出生日期) 
- 两个数字，可以是 01-52 或 99
- 四个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_romania_eu_national_id_card` 查找与模式匹配的内容。
- 找到 的  `Keywords_romania_eu_national_id_card` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_romania_eu_national_id_card` 查找与模式匹配的内容。

```xml
      <!-- Romania Personal Numerical Code (CNP) -->
      <Entity id="eb5fa399-fe28-4c67-8188-d63a616ed89c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

- cnp#
- cnp
- cod identificare personal
- cod numeric personal
- cod unic identificare
- codnumericpersonal#
- codul fiscal nr.
- identificarea fiscalnr#
- id-ul taxei
- insurance number
- insurancenumber#
- national id#
- national id
- national identification number
- numr identificare personal
- numr identitate
- num个个人 unic
- numridentitate#
- numridentitate
- num个rpersonalunic#
- num个rpersonalunic
- num以ru de identificare fiscal的
- num个rul de identificare fiscal器
- 个人数字代码
- pin#
- pin
- tax file no
- tax file number
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#
- 唯一标识号
- 唯一标识号
- uniqueidentityno#
- uniqueidentityno


## <a name="romania-physical-addresses"></a>罗马尼亚物理地址

此未解包的命名实体检测与罗马尼亚的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="russia-passport-number-domestic"></a>俄罗斯护照号码国内

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

10 位数字

### <a name="pattern"></a>模式

10 位数字：

- 两个数字
- 可选空格或连字符
- 两个数字
- 可选空格
- 六个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式Regex_Russian_Passport_Number_Domestic查找与模式匹配的内容。
- 找到来自Keyword_Russian_Passport_Number关键字。

```xml
      <!-- Russian Passport Number Domestic -->
      <Entity id="76ec2f5d-cedb-48e1-8070-1998794af445" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_Domestic" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_russia_passport_number_domestic"></a>Keyword_russia_passport_number_domestic

- passport number
- passport no
- passport#
- passport id
- passportno#
- passportnumber#
- паспорт нет
- 均？
- pоссийской паспорт
- pусский номер паспорта
- паспорт#
- 均？#
- номер паспорта
- номерпаспорта#


## <a name="russia-passport-number-international"></a>俄罗斯护照号码国际

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

九位数

### <a name="pattern"></a>模式

九位数：

- 两个数字
- 可选空格或连字符
- 七个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式Regex_Russian_Passport_Number_International查找与模式匹配的内容。
- 找到来自Keyword_Russian_Passport_Number关键字。

```xml
      <!-- Russian Passport Number International -->
      <Entity id="ac5f4878-75e4-4b82-af2d-02e13ea9f411" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_International" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_russia_passport_number_international"></a>Keywords_russia_passport_number_international

- passport number
- passport no
- passport#
- passport id
- passportno#
- passportnumber#
- паспорт нет
- 均？
- pоссийской паспорт
- pусский номер паспорта
- паспорт#
- 均？#
- номер паспорта
- номерпаспорта#


## <a name="saudi-arabia-national-id"></a>沙特阿拉伯国家 ID

### <a name="format"></a>格式

10 个数字

### <a name="pattern"></a>模式

10 个连续的数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式 Regex_saudi_arabia_national_id 找到与该模式匹配的内容。
- 找到 Keyword_saudi_arabia_national_id 中的一个关键字。

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_saudi_arabia_national_id"></a>Keyword_saudi_arabia_national_id

- Identification Card
- I card number
- ID number
- الوطنية الهوية بطاقة رقم


## <a name="singapore-national-registration-identity-card-nric-number"></a>新加坡国家注册身份证号码 (NRIC) 号码

### <a name="format"></a>格式

九个字母和数字

### <a name="pattern"></a>模式

- 九个字母和数字：
- 字母"F"、"G"、"S"或"T" (不区分大小写) 
- 七个数字
- 字母检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。
- 找到 Keyword_singapore_nric 中的一个关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。
- 校验和通过。

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_singapore_nric"></a>Keyword_singapore_nric

- National Registration Identity Card
- Identity Card Number
- NRIC
- IC
- Foreign Identification Number
- FIN
- 身份证
- 身份證


## <a name="slovakia-drivers-license-number"></a>斯洛伐克驾驶证号码

### <a name="format"></a>格式

一个字符后跟七个数字

### <a name="pattern"></a>模式

一个字符后跟七个数字

- 一个字母 (不区分大小写) 或数字
- 七个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_slovakia_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_slovakia_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Slovakia Driver's License Number -->
      <Entity id="14240c22-b6de-4ce5-a90b-137f74252513" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver s_license_number

- vodi的skk pre一z
- vodi-ské pre一zy
- vodizuského pre一zu
- vodi个sk与 pre一zov


## <a name="slovakia-passport-number"></a>斯洛伐克护照号码

### <a name="format"></a>格式

一个数字或字母后跟七个数字，无空格或分隔符

### <a name="pattern"></a>模式

一个数字或字母 (不区分大小写) 后跟七个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_slovakia_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_slovakia_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_eu_passport_date1` DD.MM.YYYY 格式的日期或找到 `Keywords_eu_passport_date` 的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_slovakia_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_slovakia_eu_passport_number` 中的关键字。

```xml
      <!-- Slovakia Passport Number -->
      <Entity id="238e1f08-d80e-4793-af33-9b57918335b7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- ííslo pasu
- íísla pasov
- pas 。
- Passeport n°
- n° Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="slovakia-personal-number"></a>斯洛伐克个人号码

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

九个或 10 个数字，包含可选反杠

### <a name="pattern"></a>模式

- 六个数字，表示出生日期
- 可选斜 (/) 
- 三个数字
- 一个可选检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_slovakia_eu_national_id_card` 查找与模式匹配的内容。
- 找到 的  `Keywords_slovakia_eu_national_id_card` 关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数  `Func_slovakia_eu_national_id_card` 查找与模式匹配的内容。

```xml
      <!-- Slovakia Personal Number -->
      <Entity id="951c26b7-3b35-4f73-924b-15dd599cb9ab" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- birth number
- ííslo národnej identifíánej karty
- ííslo obianského pre一zu
- daíové ííslo
- id number
- identification no
- identification number
- identifikaáná gam
- identifíné ííslo
- identity card no
- 标识卡号
- národná identif一ná znaáka á
- national number
- nationalnumber#
- nemzeti személyazonosító igazolv一y
- personalidnumber#
- r以
- rodne cislo
- rodné ííslo
- social security number
- ssn#
- ssn
- személyi igazolvlvy szám
- személyi igazolvlvy száma
- személy一zolvlvy szám
- tax file no
- tax file number
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="slovakia-physical-addresses"></a>斯洛伐克物理地址

此未解包的命名实体检测与斯洛伐克的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="slovenia-drivers-license-number"></a>斯洛文尼亚驾驶证号码

### <a name="format"></a>格式

九个数字，不带空格和分隔符

### <a name="pattern"></a>模式

九个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_slovenia_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_slovenia_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Slovenia Driver's License Number -->
      <Entity id="d5bc089a-f2ee-433d-a6b1-5c253051d6f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number

#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver s_license_number

- vozni-ko dovoljenje
- vozninika         2013 许可证
- vozninikih dovoljenj
- 个tevilka voznininikega dovoljenja
- 个tevilke voznininikih dovoljenj


## <a name="slovenia-passport-number"></a>斯洛文尼亚护照号码

### <a name="format"></a>格式

两个字母后跟七个数字，无空格或分隔符

### <a name="pattern"></a>模式

两个字母后跟七个数字：

- 字母"P"
- 一个小写字母
- 七个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_slovenia_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_slovenia_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_eu_passport_date1` DD.MM.YYYY 格式的日期或找到 `Keywords_eu_passport_date` 的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_slovenia_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_slovenia_eu_passport_number` 中的关键字。

```xml
      <!-- Slovenia Passport Number -->
      <Entity id="235b7976-7bbe-4df5-bb40-08678e749d1a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- 个tevilka potnega lista
- potek veljavnosti
- potni 列表#
- datum rojstva
- potni 列表
- 个tevilke potnih listov

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="slovenia-physical-addresses"></a>斯洛文尼亚物理地址

此未解包的命名实体检测与斯洛文尼亚的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="slovenia-tax-identification-number"></a>斯洛文尼亚税务标识号

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

八个数字，无空格或分隔符

### <a name="pattern"></a>模式

- 一个数字，从 1 到 9
- 六个数字
- 一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_slovenia_eu_tax_file_number` 查找与模式匹配的内容。
- 找到 的  `Keywords_slovenia_eu_tax_file_number` 关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数  `Func_slovenia_eu_tax_file_number` 查找与模式匹配的内容。

```xml
      <!-- Slovenia Tax Identification Number -->
      <Entity id="e47b071e-c352-4d70-8241-8c215ad65505" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
          <Match idRef="Keywords_slovenia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

- dav-na    gamtevilka
- identifikacijska       tevilka davka
- gamtevilka dav的ne datoatoatoe
- tax file no
- tax file number
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="slovenia-unique-master-citizen-number"></a>斯洛文尼亚唯一主公民编号

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

不带空格或分隔符的 13 个数字

### <a name="pattern"></a>模式

指定模式中的 13 个数字：

- 对应于出生日期的七个数字 (DDMMLLL) 其中"LLL"对应于出生日期的最后三个数字
- 两个数字，对应于出生日期"50"
- 三个数字，对应于同一天的人的性别和序列号的组合。 000-499（男性）和 500-999（针对男性）。
- 一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_slovenia_eu_national_id_card` 查找与模式匹配的内容。
- 找到 的  `Keywords_slovenia_eu_national_id_card` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_slovenia_eu_national_id_card` 查找与模式匹配的内容。

```xml
      <!-- Slovenia Unique Master Citizen Number -->
      <Entity id="68948b27-803d-41e4-adf1-13e05eb541bb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

- edinstvena 2tevilka g一nega dr-avljana
- em以o
- enotna maticna 且tevilka obcana
- id card
- identification number
- identifikacijska      vilka
- identity card
- nacionalna id
- nacionalni potni list
- national id
- osebna izkaznica
- osebni koda
- osebni ne
- osebni ebtevilka
- 个人代码
- 个人编号
- 个人数字代码
- *tevilka dr-avljana
- 唯一公民编号
- 唯一 ID 号
- 唯一标识号
- unique master citizen number
- 唯一注册号
- uniqueidentityno#
- uniqueidentityno#


## <a name="south-africa-identification-number"></a>南非标识号

### <a name="format"></a>格式

13 个数字（可能包含空格）

### <a name="pattern"></a>模式

13 个数字：
- 六个数字，格式为 YYMMDD，表示出生日期
- 四个数字
- 单数字公民指示符
- 数字"8"或"9"
- 一个数字，即校验和数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_south_africa_identification_number 找到与该模式匹配的内容。
- 找到 Keyword_south_africa_identification_number 中的一个关键字。
- 校验和通过。

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- Identity card
- ID
- 标识


## <a name="south-korea-resident-registration-number"></a>韩国居民注册号码

### <a name="format"></a>格式

13 个数字（包含连字符）

### <a name="pattern"></a>模式

13 个数字：
- 六个数字，格式为 YYMMDD，表示出生日期
- 连字符
- 一个数字，由世纪和性别决定
- 四位数的出生日期区域代码
- 一个数字，用于区分前面数字完全相同的人
- 一个检查数字。

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_south_korea_resident_number 找到与该模式匹配的内容。
- 找到 Keyword_south_korea_resident_number 中的一个关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_south_korea_resident_number 找到与该模式匹配的内容。
- 校验和通过。

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- National ID card
- Citizen's Registration Number
- Jumin deungnok beonho
- RRN
- 주민등록번호


## <a name="spain-dni"></a>西班牙 DNI

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

八个数字后跟一个字符

### <a name="pattern"></a>模式

七个数字后跟一个字符

- 八个数字
- 可选空格或连字符
- 一个检查 (不区分大小写) 

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_spain_eu_DL_and_NI_number_citizen` 或 `Func_spain_eu_DL_and_NI_number_foreigner` 查找与模式匹配的内容。
- 找到 的  `Keywords_spain_eu_national_id_card"` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_spain_eu_DL_and_NI_number_citizen` 或 `Func_spain_eu_DL_and_NI_number_foreigner` 查找与模式匹配的内容。


```xml
      <!-- Spain DNI -->
      <Entity id="8e6251b9-47b4-40e8-a42b-0f80876be192" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

- carné de identidad
- dni#
- dni
- dninúmero#
- documento nacional de identidad
- identidad único
- identidadúnico#
- insurance number
- national identification number
- national identity
- nationalid#
- nationalidno#
- 一#
- 一
- nienúmero#
- número de identificación
- número nacional identidad
- 个人标识号
- 个人标识否
- 唯一标识号
- uniqueid#


## <a name="spain-drivers-license-number"></a>西班牙驾驶证号码

### <a name="format"></a>格式

八个数字后跟一个字符

### <a name="pattern"></a>模式

八个数字后跟一个字符：

- 八个数字
- 一个数字或字母 (不区分大小写) 

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_spain_eu_DL_and_NI_number_citizen` 或 `Func_spain_eu_DL_and_NI_number_foreigner` 查找与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_spain_eu_driver's_license_number` 中的关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_spain_eu_DL_and_NI_number_citizen` 或 `Func_spain_eu_DL_and_NI_number_foreigner` 查找与模式匹配的内容。

```xml
      <!-- Spain Driver's License Number -->
      <Entity id="d5a82922-b501-4f40-8868-341321146aa2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver s_license_number

- permiso de conducción
- permiso conducción
- licencia de cond一r
- licencia cond一r
- permiso cond一r
- permiso de cond一r
- permisos de cond一r
- permisos cond一r
- carnet cond一r
- carnet de cond一r
- licencia de manejo
- licencia manejo


## <a name="spain-passport-number"></a>西班牙护照号码

### <a name="format"></a>格式

字母和数字的八字符或九字符组合，无空格或分隔符

### <a name="pattern"></a>模式

字母和数字的八字符或九字符组合：

- 两个数字或字母
- 一个数字或字母 (可选) 
- 六个数字

### <a name="checksum"></a>校验和

不适用

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式查找  `Regex_spain_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_spain_eu_passport_number` 中的关键字。
- 正则表达式查找 `Regex_spain_eu_passport_date` DD-MM-YYYY 格式的日期或找到 `Keywords_eu_passport_date` 的关键字

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_spain_eu_passport_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_passport_number` `Keywords_spain_eu_passport_number` 中的关键字。

```xml
      <!-- Spain Passport Number -->
      <Entity id="d17a57de-9fa5-4e9f-85d3-85c26d89686e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_spain_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- libreta pasaporte
- número pasaporte
- espa与 pasaporte
- números de pasaporte
- número de pasaporte
- números pasaporte
- pasaporte no
- Passeport n°
- n° Passeport
- pasaporte 否。
- pasaporte n°
- 西班牙护照

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="spain-physical-addresses"></a>西班牙物理地址

此未解包的命名实体检测与来自西班牙的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="spain-social-security-number-ssn"></a>西班牙社会保险号码 (SSN) 


### <a name="format"></a>格式

11-12 个数字

### <a name="pattern"></a>模式

11-12 个数字：
- 两个数字
- 可选参数， (正斜) 
- 七到八个数字
- 可选参数， (正斜) 
- 两个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_spanish_social_security_number 找到与该模式匹配的内容。
- 校验和通过。
- - 找到 的  `Keywords_spain_eu_ssn_or_equivalent` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_spanish_social_security_number 找到与该模式匹配的内容。
- 校验和通过。

```xml
    <!-- Spain SSN -->
    <Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85" relaxProximity="true" >
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spanish_social_security_number" />
          <Match idRef="Keywords_spain_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spanish_social_security_number" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- ssn
- ssn#
- socialsecurityno
- social security no
- social security number
- número de la seguridad social


## <a name="spain-tax-identification-number"></a>西班牙税务标识号

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

七个或八个数字以及指定模式中一个或两个字母

### <a name="pattern"></a>模式

具有西班牙国家身份证的西班牙自然人：

- 八个数字
- 一个小写 (区分大小写) 

没有西班牙国家身份证的非常驻 Spaniards

- 一个小写字母"L" (区分大小写) 
- 七个数字
- 一个小写 (区分大小写) 

没有西班牙国家身份证的 14 岁以下的儿童的常驻 Spaniards：

- 一个小写字母"K" (区分大小写) 
- 七个数字
- 一个小写 (区分大小写) 

具有一位用户标识号的百位用户

- 一个区分大小写的大写字母"X"、"Y"或"Z" (区分大小写) 
- 七个数字
- 一个小写 (区分大小写) 

没有标识号的百分卡

- 一个区分大小写的大写字母 ("M") 
- 七个数字
- 一个小写 (区分大小写) 

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_spain_eu_tax_file_number` 或 `Func_spain_eu_DL_and_NI_number_citizen` 查找与模式匹配的内容。
- 找到 的  `Keywords_spain_eu_tax_file_number` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_spain_eu_tax_file_number` 或 `Func_spain_eu_DL_and_NI_number_citizen` 查找与模式匹配的内容。

```xml
      <!-- Spain Tax Identification Number -->
      <Entity id="10f0d113-b0e1-47dc-872a-a4f45b9376a3" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

- cif
- cifid#
- cifnúmero#
- número de contribuyente
- número de identificación fiscal
- número de impuesto corporativo
- spanishcifid#
- spanishcifid
- spanishcifno#
- spanishcifno
- tax file no
- tax file number
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="sql-server-connection-string"></a>SQL Server连接字符串

### <a name="format"></a>格式

字符串"用户 ID"、"用户 ID"、"uid"或"UserId"后跟以下模式中列出的字符和字符串。

### <a name="pattern"></a>模式

- 字符串"用户 ID"、"用户 ID"、"uid"或"UserId"
- 1-200 位小写字母或大写字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串"Password"或"pwd"，其中"pwd"的前面没有小写字母
- 等号 (=) 
- 不是美元符号的任何字符 ($) ，百分比符号 (%) ，大于符号 (>) ，符号为 (@) ，引号 (") ，分号 (;) ，左大括号 ([) ，或左括号 ({) 
- 7-128 个字符的任意组合，这些字符不是分号 (;) 、正斜杠 (/) 或引号 (") 
- 分号 (;) 或引号 (") 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式CEP_Regex_SQLServerConnectionString查找与模式匹配的内容。
- 未找到CEP_GlobalFilter关键字。
- 正则表达式CEP_PasswordPlaceHolder找不到与模式匹配的内容。
- 正则表达式CEP_CommonExampleKeywords找不到与模式匹配的内容。

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="cep_globalfilter"></a>CEP_GlobalFilter

- some-password
- somepassword
- secretPassword
- 示例

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

此敏感信息类型使用正则表达式（而不是关键字列表）标识这些关键字。

- 密码或 pwd 后跟 0-2 个空格、一个等号 (=) 、0-2 个空格和一个星号 (*) -OR-
- 密码或 pwd 后跟：
    - 等号 (=) 
    - 小于符号 (<) 
    - 大写或小写字母、数字、星号 (*) 、连字符 (-) 、下划线 (_) 或空格字符的 1-200 个字符的任意组合
    - 大于符号 (>) 

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

此敏感信息类型使用正则表达式（而不是关键字列表）标识这些关键字。

- contoso
- fabrikam
- northwind
- 沙盒
- onebox
- localhost
- 127.0.0.1
- testacs。<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->net


## <a name="surgical-procedures"></a>过程：一些程序

此未解包的命名实体检测与过程相关的术语，如 *appendectomy*。  它仅支持英语术语。

### <a name="confidence-level"></a>置信度

高


## <a name="sweden-drivers-license-number"></a>瑞典驾驶证号码

### <a name="format"></a>格式

10 个数字，包含连字符

### <a name="pattern"></a>模式

10 个数字，包含连字符：

- 六个数字
- 连字符
- 四个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式查找  `Regex_sweden_eu_driver's_license_number` 与模式匹配的内容。
- 找到 或  `Keywords_eu_driver's_license_number` `Keywords_sweden_eu_driver's_license_number` 中的关键字。

```xml
      <!-- Sweden Driver's License Number -->
      <Entity id="70088720-90dd-47f5-805e-5525f3567391" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_sweden_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


#### <a name="keywords_sweden_eu_drivers_license_number"></a>Keywords_sweden_eu_driver s_license_number

- ajokortti
- permis de conducere
- ajokortin numero
- kuljettajat lic。
- drivere lic.
- körkort
- numrul permisului de conducere
-  שאָפער דערלויבעניש נומער
- frare lic。
-  דריווערס דערלויבעניש
- krkortsnummer


## <a name="sweden-national-id"></a>瑞典国家/身份证号码

### <a name="format"></a>格式

10 个或 12 个数字和一个可选分隔符

### <a name="pattern"></a>模式

10 或 12 位数字和可选的分隔符：
- 两个数字 (可选) 
- 采用日期格式 YYMMDD 的六位数字
- 可选参数"-"或"+" (分隔符) 
- 四个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 `Func_swedish_national_identifier` 查找与模式匹配的内容。
- 找到的关键字来自`Keywords_swedish_national_identifier`
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 `Func_swedish_national_identifier` 查找与模式匹配的内容。
- 校验和通过。


```xml
    <!-- Sweden National ID -->
    <Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
        <Match idRef="Keywords_swedish_national_identifier" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_swedish_national_identifier" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_swedish_national_identifier"></a>Keywords_swedish_national_identifier

- id no
- id number
- id#
- identification no
- identification number
- identifikationsnumret#
- identifikationsnumret
- identitetshandling
- 标识文档
- identity no
- 标识号
- id-nummer
- 个人 ID
- personnummer#
- personnummer
- 将identifikationsnummer


## <a name="sweden-passport-number"></a>瑞典护照号码

### <a name="format"></a>格式

八个数字

### <a name="pattern"></a>模式

八个连续的数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 正则表达式Regex_sweden_passport_number找到与模式匹配的内容。
- 找到或 `Keywords_eu_passport_number` 找到 `Keyword_sweden_passport` 的关键字。
- 正则表达式查找 `Regex_sweden_eu_passport_date` DD MMM/MMM YY (01 JAN/JAN 12 `Keywords_eu_passport_date`) 或找到的关键字的日期。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式Regex_sweden_passport_number找到与模式匹配的内容。
- 找到或 `Keywords_eu_passport_number` 找到 `Keyword_sweden_passport` 的关键字。


```xml
    <!-- Sweden Passport Number -->
    <Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_sweden_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- 注册卡
- g3 处理费用
- 多个条目
- Numéro de passeport
- passeport n °
- passeport non
- passeport#
- passeport#
- passeportnon
- passeportn °
- passnummer
- pass nr
- visa visa
- visa visas
- 单个条目
- sverige pass
- visa requirements
- visa processing
- visa type

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- 发行日期
- 到期日期


## <a name="sweden-physical-addresses"></a>瑞典物理地址

此未解包的命名实体检测与瑞典的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="sweden-tax-identification-number"></a>瑞典税务标识号

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

10 个数字和指定模式中的符号

### <a name="pattern"></a>模式

10 个数字和一个符号：

- 六个数字，对应于 YYMMDD (出生日期) 
- 加号或减号
- 使标识号唯一的三个数字，其中：
  - 对于 1990 以前颁发的数字，第七位和第八位标识出生日期或出生日期的县
  - 第九个位置的数字表示性别（男性为奇数或偶数）
- 一个检查数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数  `Func_sweden_eu_tax_file_number` 查找与模式匹配的内容。
- 找到 的  `Keywords_sweden_eu_tax_file_number` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_sweden_eu_tax_file_number` 查找与模式匹配的内容。

```xml
      <!-- Sweden Tax Identification Number -->
      <Entity id="139acba0-a5bc-4fbb-876d-f7a493ae8a40" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_sweden_eu_telephone_number" />
            <Match idRef="Keywords_sweden_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

- 个人 ID 号
- personnummer
- 将 id nummer
- 将 identifikation
- alatebetalarens identifikationsnummer
- sverige tin
- tax file
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax number
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="swift-code"></a>SWIFT 代码

### <a name="format"></a>格式

四个字母后跟 5-31 个字母或数字

### <a name="pattern"></a>模式

四个字母后跟 5-31 个字母或数字：
- 四个字母银行 (不区分大小写) 
- 可选空格
- 4-28 个字母或数字（基本银行账号 (BBAN)）
- 可选空格
- BBAN 项目的剩余 (一到三个字母或) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式 Regex_swift 找到与该模式匹配的内容。
- 找到 Keyword_swift 中的一个关键字。

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_swift"></a>Keyword_swift

- international organization for standardization 9362
- iso 9362
- iso9362
- swift#
- swiftcode
- swiftnumber
- swiftroutingnumber
- swift code
- swift number #
- swift routing number
- bic number
- bic code
- bic #
- bic#
- bank identifier code
- Organisation internationale de normalisation 9362
- rapide #
- code SWIFT
- le numéro de swift
- swift numéro d'acheminement
- le numéro BIC
- # <a name="bic"></a>BIC
- code identificateur de banque
- SWIFTコド
- SWIFT 号
- BIC 级
- BICコド
- SWIFT コド
- SWIFT 号
- BIC 活动号
- BIC コド
- 金融機関識別コード
- 金融機関コード
- 銀行コード


## <a name="switzerland-physical-addresses"></a>瑞士物理地址

此未解包的命名实体检测与来自瑞士的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="switzerland-ssn-ahv-number"></a>瑞士 SSN AHV 号码

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

13 位数字

### <a name="pattern"></a>模式

13 位数字：

- 三个数字 - 756
- 可选点
- 四个数字
- 可选点
- 四个数字
- 可选点
- 两个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_swiss_social_security_number_ahv查找与模式匹配的内容。
- 找到来自Keywords_swiss_social_security_number_ahv关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数Func_swiss_social_security_number_ahv查找与模式匹配的内容。

```xml
      <!-- Swiss SSN AHV Number -->
      <Entity id="277cfa4b-6eaa-4a1b-9492-099dec849971" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
          <Match idRef="Keywords_swiss_social_security_number_ahv" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_swiss_ssn_ahv_number"></a>Keyword_swiss_ssn_AHV_number

- ahv
- ssn
- pid
- insurance number
- personalidno#
- social security number
- 个人 ID 号
- 个人标识号。
- insuranceno#
- uniqueidno#
- 唯一标识号。
- avs number
- personal identity no versicherungsnummer
- identifikationsnummer
- einzi一ige identitchtt nicht
- sozialversicherungsnummer
- identification personnelle id
- numéro de sécurité sociale


## <a name="taiwan-national-identification-number"></a>台湾国家/地区身份证号码

### <a name="format"></a>格式

一个字母 (英文) 后跟九个数字

### <a name="pattern"></a>模式

一个字母 (英文) 后跟九个数字：
- 一个字母 (英语，不区分大小写) 
- 数字"1"或"2"
- 八个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_taiwanese_national_id 找到与该模式匹配的内容。
- 找到 Keyword_taiwanese_national_id 中的一个关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_taiwanese_national_id 找到与该模式匹配的内容。
- 校验和通过。

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
       <Pattern confidenceLevel="75">
         <IdMatch idRef="Func_taiwanese_national_id" />
       </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_taiwan_national_id"></a>Keyword_taiwan_national_id

- 身份證字號
- 身份證
- 身份證號碼
- 身份證號
- 身分證字號
- 身分證
- 身分證號碼
- 身份證號
- 身分證統一編號
- 國民身分證統一編號
- 簽名
- 蓋章
- 簽名或蓋章
- 簽章


## <a name="taiwan-passport-number"></a>台湾护照号码

### <a name="format"></a>格式

- 生物识别护照号码：九个数字
- 非生物识别护照号码：九个数字

### <a name="pattern"></a>模式
生物识别护照号码：
- 字符"3"
- 八个数字

非生物识别护照号码：
- 九个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式 Regex_taiwan_passport 找到与该模式匹配的内容。
- 找到 Keyword_taiwan_passport 中的一个关键字。

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_taiwan_passport"></a>Keyword_taiwan_passport

- ROC passport number
- Passport number
- Passport no
- Passport Num
- Passport #
- 护照
- 中華民國護照
- Zhōnghuá Mínguó hùzhào


## <a name="taiwan-resident-certificate-arctarc-number"></a>中国台湾居民证书 (ARC/TARC) 号码

### <a name="format"></a>格式

10 letters and digits

### <a name="pattern"></a>模式

10 个字母和数字
- 两个字母 (不区分大小写) 
- 八个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式 Regex_taiwan_resident_certificate 找到与该模式匹配的内容。
- 找到 Keyword_taiwan_resident_certificate 中的一个关键字。

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_taiwan_resident_certificate"></a>Keyword_taiwan_resident_certificate

- Resident Certificate
- Resident Cert
- Resident Cert.
- Identification card
- Alien Resident Certificate
- ARC
- Taiwan Area Resident Certificate
- TARC
- 居留證
- 外僑居留證
- 台灣地區居留證


## <a name="thai-population-identification-code"></a>泰语总体标识代码

### <a name="format"></a>格式

13 位数字

### <a name="pattern"></a>模式

13 个数字：
- 第一个数字不为零或九
- 12 个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_Thai_Citizen_Id查找与模式匹配的内容。
- 找到来自Keyword_Thai_Citizen_Id关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数Func_Thai_Citizen_Id查找与模式匹配的内容。

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_thai_citizen_id"></a>Keyword_thai_citizen_Id

- ID 编号
- 标识号
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน

## <a name="turkey-national-identification-number"></a>土耳其国家/地区标识号

### <a name="format"></a>格式

11 个数字

### <a name="pattern"></a>模式

11 个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数Func_Turkish_National_Id查找与模式匹配的内容。
- 找到来自Keyword_Turkish_National_Id关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数Func_Turkish_National_Id查找与模式匹配的内容。

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_turkish_national_id"></a>Keyword_turkish_national_id

- TC Kim且否
- TC Kim且 nu一
- Vat一2k nu一s
- Vat一体车否


## <a name="turkey-physical-addresses"></a>土耳其物理地址

此未解包的命名实体检测与土耳其的物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="types-of-medication"></a>企业类型

此未解包的命名实体将检测检测名称，例如 *"花"*。  它仅支持英语术语。

### <a name="confidence-level"></a>置信度

高


## <a name="uk-drivers-license-number"></a>英国 driver's license number

### <a name="format"></a>格式

特定格式的 18 个字母和数字组合

### <a name="pattern"></a>模式

18 个字母和数字：
- 五个字母 (不区分大小写) 或数字"9"来表示字母。
- 一个数字。
- 日期格式 MMDDY 表示出生日期的五个数字。 如果驱动程序是男性，则第七个字符将递增 50;对于考试，51 到 62，而不是 01 到 12。
- 两个字母 (不区分大小写) 或数字"9"来表示字母。
- 五个数字。

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 `Func_uk_drivers_license` 查找与模式匹配的内容。
- 找到 的 `Keywords_eu_driver's_license_number` 关键字。
- 校验和通过。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数 `Func_uk_drivers_license` 查找与模式匹配的内容。
- 校验和通过。

```xml
    <!-- U.K. Driver's License Number -->
    <Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75" relaxProximity="true" >
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_drivers_license" />
          <Match idRef="Keywords_eu_driver's_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_uk_drivers_license" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver' lic
- driver' lics
- driver' license
- driver' licenses
- driver' licence
- driver' licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- driver's lic
- driver's lics
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl#
- dls#
- driverlic#
- driverlics#
- driverlicense#
- driverlicenses#
- driverlicence#
- driverlicences#
- driver lic#
- driver lics#
- driver license#
- driver licenses#
- driver licences#
- driverslic#
- driverslics#
- driverslicense#
- driverslicenses#
- driverslicence#
- driverslicences#
- drivers lic#
- drivers lics#
- drivers license#
- drivers licenses#
- drivers licence#
- drivers licences#
- driver'lic#
- driver'lics#
- driver'license#
- driver'licenses#
- driver'licence#
- driver'licences#
- driver' lic#
- driver' lics#
- driver' license#
- driver' licenses#
- driver' licence#
- driver' licences#
- driver'slic#
- driver'slics#
- driver'slicense#
- driver'slicenses#
- driver'slicence#
- driver'slicences#
- driver's lic#
- driver's lics#
- driver's license#
- driver's licenses#
- driver's licence#
- driver's licences#
- driving licence 
- driving license
- dlno#
- driv lic
- driv licen
- driv 许可证
- driv 许可证
- driv licence
- driv licences
- driver licen
- drivers licen
- 驱动程序的 licen
- driving lic
- driving licen
- driving licenses
- driving licence
- driving licences
- driving permit
- dl no
- dlno
- dl number


## <a name="uk-electoral-roll-number"></a>英国 roll roll number

### <a name="format"></a>格式

两个字母后跟 1-4 个数字

### <a name="pattern"></a>模式

两个字母 (不区分大小写) 后跟 1-4 个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式 Regex_uk_electoral 找到与该模式匹配的内容。
- 找到 Keyword_uk_electoral 中的一个关键字。

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- council nomination
- nomination form
- electoral register
- electoral roll


## <a name="uk-national-health-service-number"></a>英国 national health service number

### <a name="format"></a>格式

10-17 个数字，通过空格分隔 

### <a name="pattern"></a>模式

10-17 位数字：
- 3 个或 10 个数字
- 一个空格
- 三个数字
- 一个空格
- 四个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_uk_nhs_number 找到与该模式匹配的内容。
- 下列其中一项为真：
    - 找到 Keyword_uk_nhs_number 中的一个关键字。
    - 找到 Keyword_uk_nhs_number1 中的一个关键字。
    - 找到 Keyword_uk_nhs_number_dob 中的一个关键字。
- 校验和通过。

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_uk_nhs_number"></a>Keyword_uk_nhs_number

- national health service
- nhs
- health services authority
- health authority

#### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- patient id
- patient identification
- patient no
- patient number

#### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- GP
- DOB
- D.O.B
- Date of Birth
- Birth Date


## <a name="uk-national-insurance-number-nino"></a>英国 NINO 保险号码 (NINO) 

此敏感信息类型实体包含在欧盟国家标识号敏感信息类型中。 它还作为独立的敏感信息类型实体提供。

### <a name="format"></a>格式

七个字符或九个字符，用空格或短划线分隔

### <a name="pattern"></a>模式

两种可能的模式：

- 两个字母 (有效 NINOs 仅使用此前缀中的某些字符，此模式对此进行验证;不区分大小写) 
- 六个数字
- "A"、B、C 或"D" (如前缀一样，后缀中只允许某些字符;不区分大小写) 

或

- 两个字母
- 空格或短划线
- 两个数字
- 空格或短划线
- 两个数字
- 空格或短划线
- 两个数字
- 空格或短划线
- "A"、"B"、"C"或"D"

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_uk_nino 找到与该模式匹配的内容。
- 找到 Keyword_uk_nino 中的一个关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_uk_nino 找到与该模式匹配的内容。

```xml
    <!-- U.K. NINO -->
    <Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Match idRef="Keyword_uk_nino" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- national insurance number
- national insurance contributions
- protection act
- insurance
- social security number
- insurance application
- medical application
- social insurance
- medical attention
- social security
- great britain
- NI 数字
- NI 否。
- NI#
- NI#
- insurance#
- insurancenumber
- nationalinsurance#
- nationalinsurancenumber


## <a name="uk-physical-addresses"></a>英国 物理地址

此未解包的命名实体检测与英国物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中



## <a name="uk-unique-taxpayer-reference-number"></a>英国 唯一的纳税参考编号

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

不带空格和分隔符的 10 个数字


### <a name="pattern"></a>模式

10 个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数  `Func_uk_eu_tax_file_number` 查找与模式匹配的内容。
- 找到 的  `Keywords_uk_eu_tax_file_number` 关键字。

```xml
      <!-- U.K. Unique Taxpayer Reference Number -->
      <Entity id="ad4a8116-0db8-439a-b545-6d967642f0ec" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

- tax number
- tax file
- tax id
- tax identification no
- tax identification number
- tax no#
- tax no
- tax registration number
- 已#
- 一些#
- 一些#
- taxno#
- taxnumber#
- taxnumber
- tin id
- tin no
- tin#


## <a name="us-bank-account-number"></a>美国银行帐号

### <a name="format"></a>格式

6-17 个数字

### <a name="pattern"></a>模式

6-17 个连续的数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式 Regex_usa_bank_account_number 找到与该模式匹配的内容。
- 找到 Keyword_usa_Bank_Account 中的一个关键字。

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_usa_bank_account"></a>Keyword_usa_Bank_Account

- Checking Account Number
- Checking Account
- Checking Account #
- Checking Acct Number
- Checking Acct #
- Checking Acct No.
- Checking Account No.
- Bank Account Number
- Bank Account #
- Bank Acct Number
- Bank Acct #
- Bank Acct No.
- Bank Account No.
- Savings Account Number
- Savings Account.
- Savings Account #
- Savings Acct Number
- Savings Acct #
- Savings Acct No.
- Savings Account No.
- Debit Account Number
- Debit Account
- Debit Account #
- Debit Acct Number
- Debit Acct #
- Debit Acct No.
- Debit Account No.


## <a name="us-drivers-license-number"></a>美国驾驶证号码

### <a name="format"></a>格式

取决于州

### <a name="pattern"></a>模式

取决于州 -例如，纽约：
- 9 个数字，格式为 ddd ddd ddd 将匹配。
- 9 个数字（如 ddddddddd）不匹配。

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。
- 找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。
- 找到 Keyword_us_drivers_license 中的一个关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。
- 找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。
- 找到 Keyword_us_drivers_license_abbreviations 中的一个关键字。
- 未找到 Keyword_us_drivers_license 中的关键字。

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_us_drivers_license_abbreviations"></a>Keyword_us_drivers_license_abbreviations

- DL
- DLS
- CDL
- CDLS
- ID
- ID
- DL#
- DLS#
- CDL#
- CDLS#
- ID#
- ID#
- ID number
- ID numbers
- LIC
- LIC#

#### <a name="keyword_us_drivers_license"></a>Keyword_us_drivers_license

- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- Driver Lic
- Driver Lics
- Driver License
- Driver Licenses
- DriversLic
- DriversLics
- DriversLicense
- DriversLicenses
- Drivers Lic
- Drivers Lics
- Drivers License
- Drivers Licenses
- Driver'Lic
- Driver'Lics
- Driver'License
- Driver'Licenses
- Driver' Lic
- Driver' Lics
- Driver' License
- Driver' Licenses
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Driver'sLicenses
- Driver's Lic
- Driver's Lics
- Driver's License
- Driver's Licenses
- identification number
- identification numbers
- identification #
- id card
- id cards
- identification card
- identification cards
- DriverLic#
- DriverLics#
- DriverLicense#
- DriverLicenses#
- Driver Lic#
- Driver Lics#
- Driver License#
- Driver Licenses#
- DriversLic#
- DriversLics#
- DriversLicense#
- DriversLicenses#
- Drivers Lic#
- Drivers Lics#
- Drivers License#
- Drivers Licenses#
- Driver'Lic#
- Driver'Lics#
- Driver'License#
- Driver'Licenses#
- Driver' Lic#
- Driver' Lics#
- Driver' License#
- Driver' Licenses#
- Driver'sLic#
- Driver'sLics#
- Driver'sLicense#
- Driver'sLicenses#
- Driver's Lic#
- Driver's Lics#
- Driver's License#
- Driver's Licenses#
- id card#
- id cards#
- identification card#
- identification cards#


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_[state_name]_drivers_license_name

- state 缩写 (例如，"NY") 
- 州名称 (例如，"New York") 


## <a name="us-individual-taxpayer-identification-number-itin"></a>ITIN 中美国个人纳税 (标识号) 

### <a name="format"></a>格式

九个数字，以"9"开头，包含"7"或"8"作为第四个数字，可选格式为空格或短划线

### <a name="pattern"></a>模式

格式化：
- 数字"9"
- 两个数字
- 空格或短划线
- "7"或"8"
- 一个数字
- 空格或短划线
- 四个数字

unformatted：
- 数字"9"
- 两个数字
- "7"或"8"
- 五个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_formatted_itin 找到与该模式匹配的内容。
- 找到 Keyword_itin 中的一个关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_unformatted_itin 找到与该模式匹配的内容。
- 找到 Keyword_itin 中的一个关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数Func_formatted_itin或Func_unformatted_itin找到与模式匹配的内容。

```xml
    <!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
    <Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_formatted_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_unformatted_itin" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_itin"></a>Keyword_itin

- 将
- tax id
- tax identification
- itin
- i.t.i.n.
- ssn
- tin
- social security
- tax payer
- itins
- 已
- individual taxpayer


## <a name="us-physical-addresses"></a>美国物理地址

此未解包的命名实体检测美国物理地址相关的模式。 

### <a name="confidence-level"></a>置信度

中


## <a name="us-social-security-number-ssn"></a>SSN (美国社会保险) 

### <a name="format"></a>格式

九个数字，可能采用格式化或无格式模式

> [!NOTE]
> 如果在 2011 年中旬前发布，则 SSN 具有强格式，即数字的某部分必须介于某个有效的范围中（但是没有校验和）。

### <a name="pattern"></a>模式

四个函数以四种不同的模式查找 SSN：
- Func_ssn 查找具有 2011 年以前使用短划线或空格格式化的强格式的 SSN（ddd-dd-dddd 或 ddd dd dddd）
- Func_unformatted_ssn 查找具有 2011 年以前未格式化为 9 个连续数字的强格式的 SSN (ddddddddd)
- Func_randomized_formatted_ssn 查找 2011 年后使用短划线或空格（ddd-dd-dddd 或 ddd dd dddd）格式化的 SSN
- Func_randomized_unformatted_ssn 查找 2011 年后未格式化为 9 个连续数字 (ddddddddd) 的 SSN

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 `Func_ssn` 查找与模式匹配的内容。
- 找到 的 `Keyword_ssn` 关键字。

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_unformatted_ssn 找到与模式匹配的内容。
- 找到 的 `Keyword_ssn` 关键字。

DLP 策略在 300 个字符的邻近范围内检测到这种类型的敏感信息时，其置信度较低：
- 函数 `Func_randomized_formatted_ssn` 或 `Func_randomized_unformatted_ssn` 查找与模式匹配的内容。
- 找到 的 `Keyword_ssn` 关键字。


```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_ssn"></a>Keyword_ssn

- SSA 号码
- social security number
- social security#
- social security#
- social security no
- Social Security#
- Soc Sec
- SSN
- SSNS
- SSN#
- SS#
- SSID


## <a name="usuk-passport-number"></a>美国/英国 passport number

### <a name="format"></a>格式

九个数字

### <a name="pattern"></a>模式

- 一个字母或数字
- 八个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息时，其可信度很高：
- 函数 Func_usa_uk_passport 找到与该模式匹配的内容。
- 找到 或 `Keywords_eu_passport_number` `Keywords_uk_eu_passport_number` 中的关键字。
- 找到的关键字来自`Keywords_eu_passport_date`

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 函数 Func_usa_uk_passport 找到与该模式匹配的内容。
- 找到 或 `Keywords_eu_passport_number` `Keywords_uk_eu_passport_number` 中的关键字。

```xml
    <!-- U.S. / U.K. Passport Number -->
    <Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
       <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport#
- passport#
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- passport numbers

#### <a name="keywords_uk_eu_passport_number"></a>Keywords_uk_eu_passport_number

- british passport
- uk passport


## <a name="ukraine-passport-domestic"></a>乌克兰护照国内

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

九个数字

### <a name="pattern"></a>模式

九个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式Regex_Ukraine_Passport_Domestic查找与模式匹配的内容。
- 找到来自Keyword_Ukraine_Passport_Domestic关键字。

```xml
      <!-- Ukraine Passport Domestic -->
      <Entity id="1817a540-221f-4459-9202-3bd78b81d803" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_Ukraine_Passport_Domestic"/>
          <Match idRef="Keyword_Ukraine_Passport_Domestic"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_ukraine_passport_domestic"></a>Keyword_ukraine_passport_domestic

- 乌克兰护照
- passport number
- passport no
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>乌克兰护照国际

此敏感信息类型仅在：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft Defender for Cloud Apps

### <a name="format"></a>格式

八字符字母数字模式

### <a name="pattern"></a>模式

八字符字母数字模式：
- 两个字母或数字
- 六个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

DLP 策略在 300 个字符的邻近度内检测到这种类型的敏感信息，可信度中等：
- 正则表达式Regex_Ukraine_Passport_International查找与模式匹配的内容。
- 找到来自Keyword_Ukraine_Passport_International关键字。

```xml
      <!-- Ukraine Passport International -->
      <Entity id="cfbe032d-22e0-4f28-ab68-d66e9641f1e2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Ukraine_Passport_International"/>
          <Match idRef="Keyword_Ukraine_Passport_International"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keyword_ukraine_passport_international"></a>Keyword_ukraine_passport_international

- 乌克兰护照
- passport number
- passport no
- паспорт України
- номер паспорта


