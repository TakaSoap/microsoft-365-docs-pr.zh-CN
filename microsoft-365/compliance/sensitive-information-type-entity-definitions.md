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
localization_priority: Normal
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
description: 安全合规性中心中的数据丢失防护 (DLP) &amp; 包括80可供您在 DLP 策略中使用的敏感信息类型。 本主题列出了所有这些敏感信息类型，并显示 DLP 策略在检测到每种类型时查找的内容。
ms.openlocfilehash: 8ee871ccde30d3ab71dbcb2d5183aafdf11482bd
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235568"
---
# <a name="sensitive-information-type-entity-definitions"></a>敏感信息类型属性定义

合规性中心中的数据丢失防护 (DLP) 包括许多可供您在 DLP 策略中使用的敏感信息类型。 本主题列出了所有这些敏感信息类型，并显示 DLP 策略在检测到每种类型时查找的内容。 敏感信息类型通过正则表达式或函数可以识别的模式定义。 此外，关键字和校验和等确凿的证据可用于识别敏感信息类型。 可信度和相似度也会在评估过程中使用。

敏感信息类型需要以下订阅之一：
- Microsoft 365 E3
- Microsoft 365 E5

## <a name="aba-routing-number"></a>ABA 传送号码

### <a name="format"></a>Format

9个数字，可以是格式化或无格式的模式

### <a name="pattern"></a>模式

格式
- 以0、1、2、3、6、7或8开头的四个数字
- 连字符
- 四位数
- 连字符
- 一个数字

未格式化：以0、1、2、3、6、7或8开头的九个连续数字 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_aba_routing 找到与该模式匹配的内容。
- 找到 Keyword_ABA_Routing 中的一个关键字。

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a>关键字

#### <a name="keyword_aba_routing"></a>Keyword_aba_routing

- aba
- aba #
- aba routing #
- aba routing number
- aba#
- abarouting#
- aba number
- abaroutingnumber
- american bank association routing #
- american bank association routing number
- americanbankassociationrouting#
- americanbankassociationroutingnumber
- bank routing number
- bankrouting#
- bankroutingnumber
- routing transit number
- RTN 
   
## <a name="argentina-national-identity-dni-number"></a>阿根廷国家标识 (DNI) 号码

### <a name="format"></a>Format

八个数字，用点分隔

### <a name="pattern"></a>模式

八个数字：
- 两位数
- 一个句点
- 三个数字
- 一个句点
- 三个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina National Identity number 
- 标识 
- 标识国家/地区身份卡片 
- DNI 
- 个人的网络国家注册表 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 
   
## <a name="australia-bank-account-number"></a>澳大利亚银行帐户编号

### <a name="format"></a>Format

具有或不具有银行状态分支号码的6到 twn 位数字

### <a name="pattern"></a>模式

帐号是6到10位数字。

澳大利亚银行州级分部编号：
- 三个数字 
- 连字符 
- 三个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。
- 找到 Keyword_australia_bank_account_number 中的一个关键字。
- 正则表达式 Regex_australia_bank_account_number_bsb 找到与该模式匹配的内容。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_australia_bank_account_number 找到与该模式匹配的内容。
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

### <a name="keywords"></a>关键字

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
- iaea

## <a name="australia-business-number"></a>澳大利亚商业电话号码
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全


### <a name="format"></a>Format

11个带可选分隔符的数字

### <a name="pattern"></a>模式

11个带可选分隔符的数字：

- 两位数
- 一个可选连字符或空格
- 三个数字
- 一个可选连字符或空格
- 三个数字
- 一个可选连字符或空格
- 三个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_australian_business_number 找到与该模式匹配的内容。
- 找到 Keywords_australian_business_number 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_australian_business_number 找到与该模式匹配的内容。

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
### <a name="keywords"></a>关键字

#### <a name="keyword_australia_business_number"></a>Keyword_australia_business_number

- 澳大利亚公司编号
- 业务号码
- abn#
- businessid#
- 业务 id
- abn
- businessno#

## <a name="australia-company-number"></a>澳大利亚公司编号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

9个带分隔符的数字

### <a name="pattern"></a>模式

九位数带分隔符：

- 三个数字
- 一个空格
- 三个数字
- 一个空格
- 三个数字


### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_Australian_Company_Number 找到与该模式匹配的内容。
- 找到 Keyword_Australian_Company_Number 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
- 函数 Func_Australian_Company_Number 找到与该模式匹配的内容。

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
### <a name="keywords"></a>关键字

#### <a name="keyword_australia_company_number"></a>Keyword_australia_company_number

- 即可
- 澳大利亚公司编号
- 澳大利亚公司编号#
- 澳大利亚公司编号
- 澳大利亚公司编号
- 澳大利亚公司编号#
- 澳大利亚公司编号

## <a name="australia-drivers-license-number"></a>澳大利亚驾驶执照号码

### <a name="format"></a>Format

九个字母和数字

### <a name="pattern"></a>模式

九个字母和数字： 

- 两个数字或字母 (不区分大小写)  
- 两位数 
- 五个数字或字母 (不区分大小写) 

OR

- 一到两个可选字母 (不区分大小写)  
- 4到9个数字

OR

- 9个数字或字母 (不区分大小写) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

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
   
## <a name="australia-medical-account-number"></a>澳大利亚医疗帐户号码

### <a name="format"></a>Format

10-11 个数字

### <a name="pattern"></a>模式

10-11 个数字：
- 第一个数字在范围2-6
- 第九个数字是校验位
- 第十位数字是问题位数
- 第十位数字 (可选) 是单个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_australia_medical_account_number"></a>Keyword_Australia_Medical_Account_Number

- bank account details
- medicare payments
- mortgage account
- bank payments
- information branch
- credit card loan
- department of human services
- local service
- medicare

   
## <a name="australia-passport-number"></a>澳大利亚护照号码

### <a name="format"></a>Format

一个字母后跟七个数字

### <a name="pattern"></a>模式

一个字母（不区分大小写）后跟七个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_australia_passport_number 找到与该模式匹配的内容。
- 找到 Keyword_passport 或 Keyword_australia_passport_number 中的关键字。

```xml
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a>关键字

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport #
- 登记卡#
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport#
- PasseportNon
- Passeportn °

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- 登记卡
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- residential address
- department of immigration and citizenship
- 反之
- national identity card
- passport number
- travel document
- issuing authority
   
## <a name="australia-tax-file-number"></a>澳大利亚税务文件编号

### <a name="format"></a>Format

8到9个数字

### <a name="pattern"></a>模式

通常显示空格的八到九个数字，如下所示：
- 三个数字 
- 一个可选空格 
- 三个数字 
- 一个可选空格 
- 两到三个数字，其中最后一个数字是校验位

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

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

## <a name="austria-drivers-license-number"></a>奥地利驾驶执照号码
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

8位数，不含空格和分隔符
  
### <a name="pattern"></a>模式

八位数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式  `Regex_austria_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_austria_eu_driver's_license_number` 。 
    
```xml
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver "s_license_number

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- driver's licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- fuhrerschein
- fuhrerschein republik osterreich

## <a name="austria-identity-card"></a>奥地利身份卡片
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

字母、数字和特殊字符的24个字符的组合
  
### <a name="pattern"></a>模式

24个字符：
  
-  22个字母 (不区分大小写) 、数字、反斜杠、正斜杠或加号 
    
- 两个字母 (不区分大小写) 、数字、反斜杠、正斜杠、加号或等号
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式  `Regex_austria_eu_national_id_card` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_austria_eu_national_id_card` 。 
   
```xml
      <!-- Austria Identity Card -->
      <Entity id="5ec06c3b-007e-4820-8343-7ff73b889735" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- 标识号码
- 
national id
- personalausweis republik österreich

## <a name="austria-passport-number"></a>奥地利护照号码
此敏感信息类型实体仅适用于欧盟护照号码 sensitiveinformation 类型。

### <a name="format"></a>Format

一个字母后跟一个可选空格和七个数字
  
### <a name="pattern"></a>模式

一个字母、七个数字和一个空格的组合：
  
- 一个字母 (不区分大小写) 
- 一个空格 (可选) 
- 七位数字
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_austria_eu_passport_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_austria_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_austria_eu_passport_number"></a>Keywords_austria_eu_passport_number

- reisepassnummer
- reisepasse
- Reisepass 
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe

## <a name="austria-social-security-number-or-equivalent-identification"></a>奥地利社会保险号或等效标识
此敏感信息类型实体仅适用于欧盟社会保险号码或等效 ID 敏感信息类型。

### <a name="format"></a>Format

以指定格式表示的10个数字
  
### <a name="pattern"></a>模式

10 个数字：
  
- 与序列号对应的三个数字 
- 一个校验位
- 与出生日期 (DDMMYY) 的6个数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 "Func_austria_eu_
- _or_equivalent "找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_austria_eu_ssn_or_equivalent` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_austria_eu_ssn_or_equivalent` 找到与该模式匹配的内容。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- 社会保障号
- social security number
- social security code
- 保险号
- 奥地利 ssn
- ssn#
- ssn
- 保险费代码
- 保险费代码#
- socialsecurityno#
- sozialversicherungsnummer
- soziale sicherheit kein
- versicherungsnummer

## <a name="austria-tax-identification-number"></a>奥地利税标识号

### <a name="format"></a>Format

9个数字，带可选连字符和正斜线
  
### <a name="pattern"></a>模式

9个带可选连字符和正斜线的数字：
  
- 两位数
- 连字符 (可选) 
- 三个数字
- 可选) 的正斜杠 (
- 四位数
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_austria_eu_tax_file_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_austria_eu_tax_file_number` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
- 函数  `Func_austria_eu_tax_file_number` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

- österreich
- st.nr。
- steuernummer
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#
- 税号
 
## <a name="austria-value-added-tax"></a>奥地利增值税
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

11个字符的字母数字模式

### <a name="pattern"></a>模式

11个字符的字母数字模式：

- A 或 a
- T 或 t
- 可选空格
- U 或 u
- 可选空格
- 两个或三个数字
- 可选空格
- 四位数
- 可选空格
- 一个或两个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_Austria_Value_Added_Tax 找到与该模式匹配的内容。
- 找到 Keyword_Austria_Value_Added_Tax 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_Austria_Value_Added_Tax 找到与该模式匹配的内容。

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
### <a name="keywords"></a>关键字

#### <a name="keyword_austria_value_added_tax"></a>Keyword_austria_value_added_tax

- vat 号码
- vat#
- 奥地利 vat 号码
- vat 编号
- vatno#
- 增值税号
- 奥地利 vat
- mwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- vat 标识号
- atu 编号
- uid 号


## <a name="azure-documentdb-auth-key"></a>Azure DocumentDB 身份验证密钥

### <a name="format"></a>Format

字符串 "DocumentDb"，后跟下面模式中所示的字符和字符串。

### <a name="pattern"></a>模式

- 字符串 "DocumentDb"
- 介于3-200 个字母、数字、符号、特殊字符或空格之间的任意组合
- 大于符号 ( # A0) 、等号 (=) 、引号 ( ") 或撇号 ( ' ) 
- 86小写或大写字母、数字、正斜线 (/) 或加号 (+) 的任意组合
- 两个等号 (=) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_AzureDocumentDBAuthKey 找到与该模式匹配的内容。
- 正则表达式 **CEP_CommonExampleKeywords 不会找到与** 该模式匹配的内容。

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

### <a name="keywords"></a>关键字

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

 (请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。 ) 

- 尚未
- 送交
- 罗斯
- 沙盒
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->netmeeting

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Azure IAAS 数据库连接字符串和 Azure SQL 连接字符串

### <a name="format"></a>Format

字符串 "Server"、"server" 或 "data source"，后跟下面模式中所述的字符和字符串，包括字符串 "cloudapp"。<!--no-hyperlink-->com "或" cloudapp "。<!--no-hyperlink-->net "或" database。<!--no-hyperlink-->net "和字符串" Password "或" password "或" pwd "。

### <a name="pattern"></a>模式

- 字符串 "Server"、"server" 或 "data source"
- 零到两个空白字符
- 等号 (=) 
- 零到两个空白字符
- 介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串 "cloudapp"。<!--no-hyperlink-->com "，" cloudapp。<!--no-hyperlink-->net "或" database。<!--no-hyperlink-->netmeeting
- 介于1-300 个字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串 "Password"、"password" 或 "pwd"
- 零到两个空白字符
- 等号 (=) 
- 零到两个空白字符
- 一个或多个不是分号的字符 (; ) 、引号 ( ") 或撇号 ( ' ) 
- 分号 (; ) 、引号 ( ") 或撇号 ( ' ) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_AzureConnectionString 找到与该模式匹配的内容。
- 正则表达式 **CEP_CommonExampleKeywords 不会找到与** 该模式匹配的内容。

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

### <a name="keywords"></a>关键字

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

 (请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。 ) 

- 尚未
- 送交
- 罗斯
- 沙盒
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->netmeeting

## <a name="azure-iot-connection-string"></a>Azure IoT 连接字符串

### <a name="format"></a>Format

字符串 "HostName"，后跟下面模式中所示的字符和字符串，包括字符串 "azure 设备"。<!--no-hyperlink-->net "和" SharedAccessKey "。

### <a name="pattern"></a>模式

- 字符串 "HostName"
- 零到两个空白字符
- 等号 (=) 
- 零到两个空白字符
- 介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串 "azure 设备。<!--no-hyperlink-->netmeeting
- 介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串 "SharedAccessKey"
- 零到两个空白字符
- 等号 (=) 
- 零到两个空白字符
- 43小写或大写字母、数字、正斜线 (/) 或加号 (+) 的任意组合
- 等号 (=) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_AzureIoTConnectionString 找到与该模式匹配的内容。
- 正则表达式 **CEP_CommonExampleKeywords 不会找到与** 该模式匹配的内容。

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

### <a name="keywords"></a>关键字

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

 (请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。 ) 

- 尚未
- 送交
- 罗斯
- 沙盒
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->netmeeting

## <a name="azure-publish-setting-password"></a>Azure 发布设置密码

### <a name="format"></a>Format

字符串 "userpwd ="，后跟一个字母数字字符串。

### <a name="pattern"></a>模式

- 字符串 "userpwd ="
- 任何60小写字母或数字的组合
- 引号 ( ") 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_AzurePublishSettingPasswords 找到与该模式匹配的内容。
- 正则表达式 **CEP_CommonExampleKeywords 不会找到与** 该模式匹配的内容。


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

### <a name="keywords"></a>关键字

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

 (请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。 ) 

- 尚未
- 送交
- 罗斯
- 沙盒
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->netmeeting

## <a name="azure-redis-cache-connection-string"></a>Azure Redis 缓存连接字符串

### <a name="format"></a>Format

字符串 "redis"。<!--no-hyperlink-->net "，后跟下面的模式中所述的字符和字符串，包括字符串" password "或" pwd "。

### <a name="pattern"></a>模式

- 字符串 "redis"。<!--no-hyperlink-->netmeeting
- 介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串 "password" 或 "pwd"
- 零到两个空白字符
- 等号 (=) 
- 零到两个空白字符
- 43个字符的任意组合，这些字符为小写字母、数字、数字、正斜杠 (/) 或加号 (+) 
- 等号 (=) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_AzureRedisCacheConnectionString 找到与该模式匹配的内容。。
- 正则表达式 **CEP_CommonExampleKeywords 不会找到与** 该模式匹配的内容。

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

### <a name="keywords"></a>关键字

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

 (请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。 ) 

- 尚未
- 送交
- 罗斯
- 沙盒
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->netmeeting

## <a name="azure-sas"></a>Azure SA

### <a name="format"></a>Format

字符串 "sig"，后跟下面模式中所示的字符和字符串。

### <a name="pattern"></a>模式

- 字符串 "sig"
- 零到两个空白字符
- 等号 (=) 
- 零到两个空白字符
- 介于43-53 个字符和小写字母、数字或百分号 (% ) 之间的任意组合
- 字符串 "% 3d"
- 不是字母或数字的小写字母、数字或百分号 (% ) 的任意字符

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_AzureSAS 找到与该模式匹配的内容。

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Azure 服务总线连接字符串

### <a name="format"></a>Format

字符串 "终结点"，后跟下面模式中所示的字符和字符串，包括字符串 "<!--no-hyperlink-->net "和" SharedAccesKey "。

### <a name="pattern"></a>模式

- 字符串 "EndPoint"
- 零到两个空白字符
- 等号 (=) 
- 零到两个空白字符
- 介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串 "<!--no-hyperlink-->netmeeting
- 介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串 "SharedAccessKey"
- 零到两个空白字符
- 等号 (=) 
- 零到两个空白字符
- 43个字符的任意组合，这些字符为小写字母、数字、数字、正斜杠 (/) 或加号 (+) 
- 等号 (=) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_AzureServiceBusConnectionString 找到与该模式匹配的内容。。
- 正则表达式 **CEP_CommonExampleKeywords 不会找到与** 该模式匹配的内容。

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

### <a name="keywords"></a>关键字

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

 (请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。 ) 

- 尚未
- 送交
- 罗斯
- 沙盒
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->netmeeting

## <a name="azure-storage-account-key"></a>Azure 存储帐户密钥

### <a name="format"></a>Format

字符串 "DefaultEndpointsProtocol"，后跟下面模式中所述的字符和字符串，包括字符串 "AccountKey"。

### <a name="pattern"></a>模式

- 字符串 "DefaultEndpointsProtocol"
- 零到两个空白字符
- 等号 (=) 
- 零到两个空白字符
- 介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串 "AccountKey"
- 零到两个空白字符
- 等号 (=) 
- 零到两个空白字符
- 86个字符的任意组合，这些字符为小写字母、数字、数字、正斜杠 (/) 或加号 (+) 
- 两个等号 (=) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_AzureStorageAccountKey 找到与该模式匹配的内容。
- 正则表达式 **CEP_AzureEmulatorStorageAccountFilter 不会找到与** 该模式匹配的内容。
- 正则表达式 **CEP_CommonExampleKeywords 不会找到与** 该模式匹配的内容。

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

### <a name="keywords"></a>关键字

#### <a name="cep_azure_emulator_storage_account_filter"></a>CEP_azure_emulator_storage_account_filter

 (请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。 ) 

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

 (请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。 ) 

- 尚未
- 送交
- 罗斯
- 沙盒
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->netmeeting

## <a name="azure-storage-account-key-generic"></a> (通用) 的 Azure 存储帐户密钥

### <a name="format"></a>Format

86的任意组合（以小写或大写字母、数字、正斜杠 (/) 或加号 (+) ，在下面的模式中所列字符的前面或后面）。

### <a name="pattern"></a>模式

- 0到大于号之一 ( # A0) 、撇号 ( ' ) 、等号 (=) 、引号 ( ") 或数字标记 ( # ) 
- 86个字符的任意组合，这些字符为小写字母、数字、数字、正斜杠 (/) 或加号 (+) 
- 两个等号 (=) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_AzureStorageAccountKeyGeneric 找到与该模式匹配的内容。

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>比利时驾驶执照号码
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

10个数字，无空格和分隔符
  
### <a name="pattern"></a>模式

10位数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_belgium_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_belgium_eu_driver's_license_number` 。
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

**Keywords__belgium_eu_driver "s_license_number**

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- dlno#
- rijbewijs
- rijbewijsnummer
- führerscheinnummer
- fuhrerscheinnummer
- fuehrerscheinnummer
- führerschein-nr-nr
- fuehrerschein-Nr
- fuehrerschein-nr

## <a name="belgium-national-number"></a>比利时国家/地区号码

### <a name="format"></a>Format

11位数加上可选分隔符

### <a name="pattern"></a>模式

11 个数字加分隔符：
- 6个数字和两个可选句点（以 YY 为格式）。月.DD 出生日期 
- 点、短划线、空间中的可选分隔符 
- 奇数的三个连续数字 (奇数，即使偶数)  
- 点、短划线、空间中的可选分隔符 
- 两个校验位

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_belgium_national_number 找到与该模式匹配的内容。
- 找到 Keyword_belgium_national_number 中的一个关键字。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- belasting aantal
- bnn#
- bnn
- d'identité
- identifiant 国家
- identifiantnational#
- identificatie
- id
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- 窃取
- inscription
- 国家/地区号码
- 国家/地区寄存器
- nationalnumber#
- nationalnumber
- \n\n#
- \n\n
- numéro d'assuré
- numéro de registre 国
- numéro de sécurité

- numéro d'identification
- numéro d'immatriculation
- numéro 国家
- numéronational#
- 个人 id 号
- personalausweis
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

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#

## <a name="belgium-passport-number"></a>比利时护照号码
此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

两个字母后跟六个数字，不含空格或分隔符
  
### <a name="pattern"></a>模式

两个字母，后跟六个数字
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_belgium_eu_passport_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_belgium_eu_passport_number` 。

```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- numéro passeport
- paspoort nr
- paspoort-nr
- paspoortnummer
- paspoortnummers
- Passeport 的购买
- Passeport livre
- Pass-Nr
- Passnummer
- reisepass kein

## <a name="belgium-social-security-number-or-equivalent-identification"></a>比利时社会安全号码或等效标识
此敏感信息类型实体仅适用于欧盟社会保险号码或等效 ID 敏感信息类型。

### <a name="format"></a>Format

11位数，不含空格或分隔符
  
### <a name="pattern"></a>模式

11 个数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数  `Func_belgium_eu_ssn_or_equivalent` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_belgium_eu_ssn_or_equivalent` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_belgium_eu_ssn_or_equivalent` 找到与该模式匹配的内容。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a>Keywords_belgium_eu_ssn_or_equivalent

- 比利时国家/地区号码
- 国家/地区号码
- social security number
- nationalnumber#
- ssn#
- ssn
- nationalnumber
- bnn#
- bnn
- 个人 id 号
- personalidnumber#
- numéro 国家
- numéro de sécurité
- numéro d'assuré
- identifiant 国家
- identifiantnational#
- numéronational#


## <a name="belgium-value-added-tax-number"></a>比利时增值税号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

12个字符的字母数字模式

### <a name="pattern"></a>模式

12个字符的字母数字模式：

- 字母 B 或 b
- 字母 E 或 E
- 数字0
- 一个从1到9的数字
- 一个可选的点或连字符或空格
- 四位数
- 一个可选的点或连字符或空格
- 四位数


### <a name="checksum"></a>校验和

是


### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_belgium_value_added_tax_number 找到与该模式匹配的内容。
- 找到 Keywords_belgium_value_added_tax_number 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_belgium_value_added_tax_number 找到与该模式匹配的内容。

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
### <a name="keywords"></a>关键字

#### <a name="keyword_belgium_value_added_tax_number"></a>Keyword_belgium_value_added_tax_number

- n º tva
- vat 号码
- vat 编号
- numéro。
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- btw
- btw#
- vat#


## <a name="brazil-cpf-number"></a>巴西 CPF 号码

### <a name="format"></a>Format

11 个数字（包括校验位），可以格式化，也可以非格式化

### <a name="pattern"></a>模式

格式
- 三个数字
- 一个句点
- 三个数字
- 一个句点
- 三个数字
- 连字符
- 两个数字，是校验位

纯
- 11 个数字，其中最后两个数字是校验位

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_brazil_cpf 找到与该模式匹配的内容。
- 找到 Keyword_brazil_cpf 中的一个关键字。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_brazil_cpf"></a>Keyword_brazil_cpf

- CPF
- Id
- Registration
- 营业
- Cadastro de Pessoas Físicas 
- Imposto 
- Identificação 
- Inscrição 
- Receita 

   
## <a name="brazil-legal-entity-number-cnpj"></a>巴西法人编号 (CNPJ) 

### <a name="format"></a>Format

14 个数字（包括注册号、分行号码和校验位），再加上分隔符

### <a name="pattern"></a>模式

14 个数字，再加上分隔符：

- 两位数 
- 一个句点 
- 三个数字 
- 一个句点 
- 三个数字 (这些前八位数字是注册号码)  
- 一个正斜杠 
- 四位数的分支号码 
- 连字符 
- 两个数字，是校验位

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_brazil_cnpj 找到与该模式匹配的内容。
- 找到 Keyword_brazil_cnpj 中的一个关键字。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

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

   
## <a name="brazil-national-identification-card-rg"></a>巴西国家标识卡 (RG) 

### <a name="format"></a>Format

Registro Geral (旧格式) ：9个数字

Registro de Identidade (RIC)  (新格式) ：11个数字

### <a name="pattern"></a>模式

Registro Geral（旧格式）：
- 两位数 
- 一个句点 
- 三个数字 
- 一个句点 
- 三个数字 
- 连字符 
- 一个数字，是校验位

Registro de Identidade (RIC)  (新格式) ：
- 10位数字 
- 连字符 
- 一个数字，是校验位

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_brazil_rg 找到与该模式匹配的内容。
- 找到 Keyword_brazil_rg 中的一个关键字。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_brazil_rg 找到与该模式匹配的内容。
- 校验和通过。

```xml
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_brazil_rg"></a>Keyword_brazil_rg

- Cédula de identidade
- identity card
- national id 
- número de rregistro
- registro de Iidentidade 
- registro geral
- RG（此关键字区分大小写） 
- RIC（此关键字区分大小写） 


## <a name="bulgaria-drivers-license-number"></a>保加利亚驾驶执照号码
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

9个数字，不带空格和分隔符
  
### <a name="pattern"></a>模式

九位数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_bulgaria_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_bulgaria_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    
```

### <a name="keywords"></a>关键字

#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver "s_license_number
- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка


## <a name="bulgaria-uniform-civil-number"></a>保加利亚统一民事号码
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

10个数字，无空格和分隔符
  
### <a name="pattern"></a>模式

10个数字，无空格和分隔符
  
- 与出生日期 (YYMMDD) 的6个数字 
- 与出生顺序对应的两个数字
- 与性别对应的一位数字：男的偶数位和用于女的奇数位
- 一个校验位

### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_bulgaria_eu_national_id_card` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_bulgaria_eu_national_id_card` 。 

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_bulgaria_eu_national_id_card` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_bulgaria_eu_national_id_card"></a>Keywords_bulgaria_eu_national_id_card

- bnn#
- bnn
- bucn#
- bucn
- edinen grazhdanski nomer
- egn#
- egn
- identification number

- 
national id
- 国家/地区号码
- nationalnumber#
- nationalnumber
- 个人 id
- 个人编号
- 个人号码
- personalidnumber#
- social security number

- ssn#
- ssn
- 统一的民事 id
- 统一的民事无
- 统一的民事号码
- uniformcivilno#
- uniformcivilno
- uniformcivilnumber#
- uniformcivilnumber
- 独特公民编号
- егн#
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униформ id
- униформграждански id
- униформ граждански не
- униформ граждански номер
- униформгражданскиid#
- униформгражданскине.#


## <a name="bulgaria-passport-number"></a>保加利亚护照号码
此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

9个数字，不带空格和分隔符
  
### <a name="pattern"></a>模式

九位数字 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_bulgaria_eu_passport_number` 找到与该模式匹配的内容。 
- 找到或中的关键字  `Keywords_bulgaria_eu_passport_number` `Keywords_eu_passport_number_common` 。 

```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```
### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- номер на паспорта
- номер на паспорт
- паспорт No

## <a name="canada-bank-account-number"></a>加拿大银行帐户号码

### <a name="format"></a>Format

七个或十二个数字

### <a name="pattern"></a>模式

加拿大银行帐号是七个或十二个数字。

加拿大银行帐户的银行代号是：
- 五个数字 
- 连字符 
- 三位数字或
- 零 "0" 
- 八位数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_canada_bank_account_number 找到与该模式匹配的内容。
- 找到 Keyword_canada_bank_account_number 中的一个关键字。
- 正则表达式 Regex_canada_bank_account_transit_number 找到与该模式匹配的内容。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

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

   
## <a name="canada-drivers-license-number"></a>加拿大驾照号码

### <a name="format"></a>Format

因省而异

### <a name="pattern"></a>模式

各种模式，涵盖艾伯塔、 不列颠哥伦比亚、 马尼托巴、 新不伦瑞克、 纽芬兰/拉布拉多、 新斯科舍、 安大略、 爱德华王子岛，魁北克和萨斯喀彻温

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_ [province_name] _drivers_license_name

- 省/市/自治区的缩写，例如 AB
- 省名称，例如 Alberta

#### <a name="keyword_canada_drivers_license"></a>Keyword_canada_drivers_license

- 通讯
- DLS
- 采用
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
- id 
- 通讯#
- DLS# 
- 采用# 
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
- 号# 
- id# 
- idcard card# 
- idcard cards# 
- idcard# 
- identification card# 
- identification cards# 
- id# 

   
## <a name="canada-health-service-number"></a>加拿大运行状况服务号码

### <a name="format"></a>Format

10位数字

### <a name="pattern"></a>模式

10位数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_canada_health_service_number"></a>Keyword_canada_health_service_number

- personal health number
- patient information
- health services
- speciality services
- automobile accident
- patient hospital
- psychiatrist
- workers compensation
- 障碍

      
## <a name="canada-passport-number"></a>加拿大护照号码

### <a name="format"></a>Format

两个大写字母后跟六个数字

### <a name="pattern"></a>模式

两个大写字母后跟六个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_canada_passport_number 找到与该模式匹配的内容。
- 找到 Keyword_canada_passport_number 或 Keyword_passport 中的关键字。

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

### <a name="keywords"></a>关键字

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
- 登记卡#
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート＃
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport#
- PasseportNon
- Passeportn °

   
## <a name="canada-personal-health-identification-number-phin"></a>加拿大个人健康标识号 (PHIN) 

### <a name="format"></a>Format

九位数字

### <a name="pattern"></a>模式

九位数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_canada_phin 找到与该模式匹配的内容。
- 找到 Keyword_canada_phin 或 Keyword_canada_provinces 中至少有两个关键字。

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

### <a name="keywords"></a>关键字

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
- 省
- Northwest Territories
- 省
- British Columbia
- Alberta
- 彻
- Manitoba
- Yukon
- Newfoundland and Labrador
- New Brunswick
- Nova Scotia
- Prince Edward Island
- 加拿大

   
## <a name="canada-social-insurance-number"></a>加拿大社会保险电话号码

### <a name="format"></a>Format

9个数字，带可选连字符或空格

### <a name="pattern"></a>模式

格式
- 三个数字 
- 连字符或空格 
- 三个数字 
- 连字符或空格 
- 三个数字

未格式化：9个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_canadian_sin 找到与该模式匹配的内容。
- 至少两个以下任意组合：
    - 找到 Keyword_sin 中的一个关键字。
    - 找到 Keyword_sin_collaborative 中的一个关键字。
    - 函数 Func_eu_date 找到正确日期格式的日期。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_sin"></a>Keyword_sin

- sin 
- social insurance 
- numero d'assurance sociale 
- 罪 
- ssn 
- ssn 
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

   
## <a name="chile-identity-card-number"></a>智利标识卡号

### <a name="format"></a>Format

七到八个数字加上分隔符一个校验位或字母

### <a name="pattern"></a>模式

七到八个数字加分隔符：
- 一到两位数 
- 一个句点 
- 三个数字 
- 一个句点 
- 三个数字 
- 短划线 
- 一个数字或字母 (不区分大小写) 这是校验位

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_chile_id_card 找到与该模式匹配的内容。
- 找到 Keyword_chile_id_card 中的一个关键字。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_chile_id_card"></a>Keyword_chile_id_card

- National Identification Number 
- Identity card 
- ID 
- Id 
- Rol Único Nacional 
- 以 
- Rol Único Tributario 
- 墨守成规 
- Cédula de Identidad 
- Número De Identificación Nacional 
- Tarjeta de identificación 
- Identificación 

   
## <a name="china-resident-identity-card-prc-number"></a>中国居民身份卡片 (中国) 号码

### <a name="format"></a>Format

18 个数字

### <a name="pattern"></a>模式

18 个数字：
- 6个数字，这是一个地址代码 
- 8位数，形式为 YYYYMMDD，表示出生日期 
- 三个数字，这是一个订单代码 
- 一个数字，是校验位

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_china_resident_id 找到与该模式匹配的内容。
- 找到 Keyword_china_resident_id 中的一个关键字。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

### <a name="keyword_china_resident_id"></a>Keyword_china_resident_id

- Resident Identity Card 
- 台湾 
- National Identification Card 
- 身份证 
- 居民 身份证 
- 居民身份证 
- 鉴定 
- 身分證 
- 居民身份證
- 鑑定 

   
## <a name="credit-card-number"></a>信用卡号

### <a name="format"></a>Format

14到16个数字，可以设置格式或无格式 (dddddddddddddddd) 且必须通过 Luhn 测试。

### <a name="pattern"></a>模式

非常复杂且强大的模式，检测到来自世界各地所有重要品牌的卡，包括 Visa、万事达卡、发现卡、JCB卡、美国运通卡、礼品卡以及大莱卡。

### <a name="checksum"></a>校验和

是，Luhn 校验和

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_credit_card 找到与该模式匹配的内容。
- 下列其中一项为真：
    - 找到 Keyword_cc_verification 中的一个关键字。
    - 找到 Keyword_cc_name 中的一个关键字。
    - 函数 Func_expiration_date 找到正确日期格式的日期。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_cc_verification"></a>Keyword_cc_verification

- 
card verification

- card identification number
- cvn
- cid
- cvc2
- cvv2
- 
pin block
- security code

- security number

- security no

- issue number

- issue no
- cryptogramme
- 
numéro de sécurité
- numero de securite
- kreditkartenprüfnummer
- kreditkartenprufnummer
- prüfziffer
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- 货.sicurezza
- 
cod sicurezza
- n autorizzazione
- código
- codigo
- 货.seg
- 
cod seg
- código de segurança

- codigo de seguranca

- codigo de segurança

- código de seguranca
- cód.segurança
- 货.seguranca
- 货.segurança
- cód.seguranca
- cód segurança
- 货到付款 seguranca
- 货到付款 segurança
- cód seguranca
- número de verificação

- numero de verificacao
- ablauf
- gültig bis
- gültigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadenza
- 
data scad
- fecha de expiracion

- fecha de venc
- vencimiento
- 
válido hasta
- valido hasta
- vto
- 
data de expiração
- data de expiracao

- data em que expira
- validade
- valor
- vencimento
- transaction
- 交易记录编号
- 参考编号
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- amex
- american express
- americanexpress
- americano espresso

- 反之
- mastercard
- Master Card
- emc
- mastercards
- 
master cards
- 用餐俱乐部
- diners club
- dinersclub
- 确定
- discover card
- discovercard
- discover cards
- JCB
- BrandSmart
- japanese card bureau

- carte blanche
- carteblanche
- credit card
- 收件人#
- cc #：
- 过期日期
- exp date

- 
expiry date
- 
date d’expiration
- 
date d'exp
- 
date expiration
- bank card
- bankcard
- 
card number
- card num
- cardnumber
- cardnumbers
- card numbers
- creditcard
- credit cards
- creditcards
- ccn
- card holder
- 持卡人
- card holders
- cardholders
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
- 
en route
- card type

- Cardmember 帐户
- cardmember 帐户
- Cardno
- 公司卡片
- 公司卡片
- 卡片类型
- 卡片帐号
- 卡片成员帐户
- Cardmember 帐户。
- card no.

- 卡片编号
- card number

- carte bancaire

- carte de crédit

- carte de credit

- numéro de carte

- numero de carte

- nº de la carte

- nº de carte
- kreditkarte
- karte
- karteninhaber
- karteninhabers
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartentyp
- eigentümername
- kartennr
- kartennummer
- kreditkartennummer
- kreditkarten-nummer
- 
carta di credito
- carta credito
- \n\n\-.carta
- n carta
- führerschein-nr.carta
- 
nr carta
- numero carta

- numero della carta

- numero di carta

- tarjeta credito

- tarjeta de credito

- 
tarjeta crédito
- 
tarjeta de crédito
- tarjeta de atm

- tarjeta atm

- tarjeta debito

- tarjeta de debito

- 
tarjeta débito
- 
tarjeta de débito
- nº de tarjeta
- 不。de tarjeta
- 无 de tarjeta
- numero de tarjeta

- número de tarjeta

- tarjeta no
- tarjetahabiente
- 
cartão de crédito
- cartão de credito

- cartao de crédito

- cartao de credito

- cartão de débito

- cartao de débito

- cartão de debito

- cartao de debito

- débito automático
- debito automatico

- 
número do cartão
- numero do cartão

- número do cartao

- numero do cartao

- número de cartão

- numero de cartão

- número de cartao

- numero de cartao

- n º do cartão
- nº do cartao
- n º。do cartão
- 不执行任何操作 cartão
- 不执行任何操作 cartao
- 不。do cartão
- 不。do cartao
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
- アメリカン エクスプレス
- Visaカード
- 签证カード
- マスターカード
- マスター カード
- マスター
- ダイナースクラブ
- ダイナース クラブ
- ダイナース
- 有効期限
- 期限
- キャッシュカード
- キャッシュ カード
- カード名義人
- カードの名義人
- カードの名義
- デビット カード
- デビットカード


## <a name="croatia-drivers-license-number"></a>克罗地亚驾照号码
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

8位数，不含空格和分隔符
  
### <a name="pattern"></a>模式

八位数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式  `Regex_croatia_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_croatia_eu_driver's_license_number` 。 

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver "s_license_number

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- vozačka dozvola


## <a name="croatia-identity-card-number"></a>克罗地亚 identity 卡片号
此敏感信息类型实体包含在欧盟国家/地区标识的敏感信息类型中，可用作独立的敏感信息类型实体。

### <a name="format"></a>Format

九位数字

### <a name="pattern"></a>模式

九个连续数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- majstorski broj građana
- 主公民号码
- nacionalni identifikacijski broj
- 国家/地区标识号
- oib#
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- 个人标识号
- porezni broj
- porezni identifikacijski broj
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#


## <a name="croatia-passport-number"></a>克罗地亚护照号码
此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

9个数字，不带空格和分隔符
  
### <a name="pattern"></a>模式

九位数字 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_croatia_eu_passport_number` 找到与该模式匹配的内容。 
- 找到或中的关键字  `Keywords_eu_passport_number_common` `Keywords_croatia_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```
### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- broj putovnice
- br. Putovnice
- br putovnice
   
## <a name="croatia-personal-identification-oib-number"></a>克罗地亚个人标识 (OIB) 号码

### <a name="format"></a>Format

11 个数字

### <a name="pattern"></a>模式

11 个数字：
- 10位数字 
- 最后一个数字是校验位

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_croatia_oib_number 找到与该模式匹配的内容。
- 找到 Keywords_croatia_eu_tax_file_number 中的关键字。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- majstorski broj građana
- 主公民号码
- nacionalni identifikacijski broj
- 国家/地区标识号
- oib#
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- 个人标识号
- porezni broj
- porezni identifikacijski broj
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#

## <a name="croatia-social-security-number-or-equivalent-identification"></a>克罗地亚社会安全号码或等效标识
此敏感信息类型实体仅适用于欧盟社会保险号码或等效 ID 敏感信息类型。

### <a name="format"></a>Format

11个数字，无空格和分隔符
  
### <a name="pattern"></a>模式

11 个数字：
  
- 10位数字
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数  `Func_croatia_eu_ssn_or_equivalent` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_croatia_eu_ssn_or_equivalent` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数  `Func_croatia_eu_ssn_or_equivalent` 找到与该模式匹配的内容。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

- 个人标识号
- 主公民号码
- national identification number
- social security number
- nationalnumber#
- ssn#
- ssn
- nationalnumber
- bnn#
- bnn
- 个人 id 号
- personalidnumber#
- oib
- osobni identifikacijski broj

   
## <a name="cyprus-drivers-license-number"></a>塞浦路斯驱动程序许可证编号
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

12个数字，不含空格和分隔符
  
### <a name="pattern"></a>模式

12 个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_cyprus_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_cyprus_eu_driver's_license_number` 。

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver "s_license_number

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- άδεια οδήγησης


## <a name="cyprus-identity-card"></a>塞浦路斯标识卡片
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

10个数字，无空格和分隔符
  
### <a name="pattern"></a>模式

10位数字 
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_cyprus_eu_national_id_card` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_cyprus_eu_national_id_card` 。 
    
```xml 
      <!-- Cyprus Identity Card -->
      <Entity id="3ba8afe5-7a6c-4929-8247-0001b6878438" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

- id 卡号
- 标识卡号
- kimlik karti
- 国家/地区标识号
- 个人 id 号
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>塞浦路斯护照号码
此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

一个字母后跟6-8 个数字，不含空格或分隔符
  
### <a name="pattern"></a>模式

一个字母后跟6到8个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_cyprus_eu_passport_number` 找到与该模式匹配的内容。
- 找到或中的关键字  `Keywords_eu_passport_number_common` `Keywords_cyprus_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_cyprus_eu_passport_number"></a>Keywords_cyprus_eu_passport_number

- αριθμό διαβατηρίου
- pasaportu
- Αριθμός Διαβατηρίου
- κυπριακό διαβατήριο
- διαβατήριο#
- διαβατήριο
- αριθμός διαβατηρίου
- Pasaport Kimliği
- pasaport numarası
- Pasaport。
- Αρ. Διαβατηρίου

## <a name="cyprus-tax-identification-number"></a>塞浦路斯税号标识号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

指定模式中的八个数字和一个字母
  
### <a name="pattern"></a>模式

八个数字和一个字母：
  
- "0" 或 "9"
- 七位数字
- 一个字母 (不区分大小写) 
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_cyprus_eu_tax_file_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_cyprus_eu_tax_file_number` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_cyprus_eu_tax_file_number` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

- tax id

- 税标识代码
- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 和#
- 和
- 纳税人 id
- tin 编号
- 锡#
- vergi kimlik kodu
- vergi kimlik numarası
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>捷克语驱动程序的许可证编号
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

两个字母后跟六个数字
  
### <a name="pattern"></a>模式

八个字母和数字：
  
- 两个字母 (不区分大小写) 
- 空格 (可选) 
- 6位数字

### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_czech_republic_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_czech_republic_eu_driver's_license_number` 。 

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>关键字

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver "s_license_number

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- řidičský prúkaz


## <a name="czech-passport-number"></a>捷克语护照号码
此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

8位数，不含空格或分隔符
  
### <a name="pattern"></a>模式

8位数，不含空格或分隔符
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_czech_republic_eu_passport_number` 找到与该模式匹配的内容。 
- 找到或中的关键字  `Keywords_eu_passport_number_common` `Keywords_czech_republic_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- cestovní pas
- číslo pasu
- cestovní pasu
- passeport no
- čísla pasu


## <a name="czech-personal-identity-number"></a>捷克个人识别码

### <a name="format"></a>Format

9个数字，带可选的正斜杠 (旧格式) 10 个数字，可选的正斜杠 (新格式) 

### <a name="pattern"></a>模式

 (旧格式) 的9个数字：
- 代表出生日期的六个数字
- 可选的正斜杠
- 三个数字

10个数字 (新格式) ：
- 代表出生日期的六个数字
- 可选的正斜杠 
- 四个数字，其中最后一个数字是校验位

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：

- 函数 Func_czech_id_card 找到与该模式匹配的内容。
- 找到 Keyword_czech_id_card 中的一个关键字。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：

- 函数 Func_czech_id_card_new_format 找到与该模式匹配的内容。
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
### <a name="keywords"></a>关键字

#### <a name="keyword_czech_id_card"></a>Keyword_czech_id_card

- 出生号码
- 捷克共和国 id
- czechidno#
- daňové číslo
- identifikační číslo
- identity no
- 标识号码
- identityno#
- identityno
- 保险号
- 国家/地区标识号
- nationalnumber#
- 国家/地区号码
- osobní číslo
- personalidnumber#
- 个人 id 号
- 个人标识号
- 个人号码
- pid#
- pid
- pojištění číslo
- rč
- rodne cislo
- rodné číslo
- ssn
- ssn#
- social security number

- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#
- 唯一标识号


## <a name="czech-social-security-number-or-equivalent-identification"></a>捷克社会安全号码或等效标识

此敏感信息类型实体仅适用于欧盟社会保险号码或等效 ID 敏感信息类型。

### <a name="format"></a>Format

指定模式中的10个数字和一个反斜杠
  
### <a name="pattern"></a>模式

10个数字和一个反斜杠：
  
- 与出生日期对应的6个数字 (YYMMDD) ： 
- 反斜杠
- 与一个序列号相对应的三个数字，用于分隔出生于同一日期的人员
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_czech_republic_eu_ssn_or_equivalent` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_czech_republic_eu_ssn_or_equivalent` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_czech_republic_eu_ssn_or_equivalent` 找到与该模式匹配的内容。 

```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

- 出生号码
- national identification number
- 个人标识号
- social security number
- nationalnumber#
- ssn#
- ssn
- 国家/地区号码
- 个人 id 号
- personalidnumber#
- rč
- rodné číslo
- rodne cislo


## <a name="denmark-drivers-license-number"></a>丹麦驾照号码
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

8位数，不含空格和分隔符
  
### <a name="pattern"></a>模式

八位数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_denmark_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_denmark_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver "s_license_number

- | dl#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- kørekort
- kørekortnummer


## <a name="denmark-passport-number"></a>丹麦护照号码
此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

9个数字，不带空格和分隔符
  
### <a name="pattern"></a>模式

九位数字 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_denmark_eu_passport_number` 找到与该模式匹配的内容。 
- 找到或中的关键字  `Keywords_eu_passport_number_common` `Keywords_denmark_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- Passeport n °
- pasnumre


## <a name="denmark-personal-identification-number"></a>丹麦个人身份号码

### <a name="format"></a>Format

10个数字，包含连字符

### <a name="pattern"></a>模式

10位数字：
- 6位数，格式为 DDMMYY，表示出生日期 
- 连字符 
- 四个数字，其中最后一个数字是校验位

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式 Func_denmark_eu_tax_file_number 找到与该模式匹配的内容。
- 找到 Keyword_denmark_id 中的一个关键字。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
- 正则表达式 Func_denmark_eu_tax_file_number 找到与该模式匹配的内容。
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

### <a name="keywords"></a>关键字

#### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- centrale personregister
- civilt registreringssystem
- cpr
- cpr#
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- 运行状况卡片
- 健康保险卡号
- 健康保险号
- identification number

- identifikationsnummer
- identifikationsnummer#
- 标识号码
- krankenkassennummer
- nationalid#
- nationalnumber#
- 国家/地区号码
- personalidnumber#
- personalidentityno#
- 个人 id 号
- personnummer
- personnummer#
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- ssn
- ssn#
- skat id
- skat kode
- skat nummer
- skattenummer
- social security number

- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- 税码
- 差旅健康保险卡
- uniqueidentityno#
- 税号
- 税务登记编号
- tax id

- 税标识号
- taxid#
- taxnumber#
- 免税
- taxno#
- taxnumber
- 税号标识编号
- 锡#
- taxidno#
- taxidnumber#
- 免税#
- 纳税人 id
- tin 编号
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


## <a name="denmark-social-security-number-or-equivalent-identification"></a>丹麦社会安全号码或等效标识
此敏感信息类型实体仅适用于欧盟社会保险号或等效 ID 敏感信息类型。

### <a name="format"></a>Format

指定模式中的10个数字和一个连字符
  
### <a name="pattern"></a>模式

10个数字和一个连字符：
  
- 与出生日期 (DDMMYY) 的6个数字 
- 连字符
- 与序列号对应的四个数字

### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_denmark_eu_ssn_or_equivalent` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_denmark_eu_ssn_or_equivalent` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_denmark_eu_ssn_or_equivalent` 找到与该模式匹配的内容。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

- 个人标识号
- national identification number
- social security number
- nationalnumber#
- ssn#
- ssn
- 国家/地区号码
- 个人 id 号
- personalidnumber#
- cpr-nummer
- personnummer


## <a name="drug-enforcement-agency-dea-number"></a>药品实施代理 (DEA) 号码

### <a name="format"></a>Format

两个字母后跟七个数字

### <a name="pattern"></a>模式

模式必须包括以下各项：
- 一个字母 (不区分大小写) 这组可能的字母： abcdefghjklmnprstux，这是注册人代码 
- 一个字母 (不区分大小写) （注册人姓氏的第一个字母） 
- 七位数字，最后一个数字是校验位

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_dea_number 找到与该模式匹配的内容。
- 校验和通过。

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

无


## <a name="estonia-drivers-license-number"></a>爱沙尼亚驾照号码
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

两个字母后跟六个数字
  
### <a name="pattern"></a>模式

两个字母和六个数字：
  
- 字母 "ET" (不区分大小写)  
- 6位数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_estonia_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_estonia_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver "s_license_number

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶执照号码
- dlno#
- permis de conduire


## <a name="estonia-personal-identification-code"></a>爱沙尼亚个人标识代码
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

11个数字，无空格和分隔符
  
### <a name="pattern"></a>模式

11 个数字：
  
- 一种数字，对应于性别和出生世纪 (奇数号码男，甚至是女号码，等等。1-2：19世纪;3-4：20世纪;5-6：21世纪) 
- 6位数字，对应于出生日期 (YYMMDD) 
- 三个数字，对应于将出生在同一日期的人员组成的序列号
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_estonia_eu_national_id_card` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_estonia_eu_national_id_card` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_estonia_eu_national_id_card` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

- id-kaart
- ik
- isikukood#
- isikukood
- maksu id
- maksukohustuslase identifitseerimisnumber
- maksunumber
- 国家/地区标识号
- 国家/地区号码
- 个人代码
- 个人 id 号
- 个人标识代码
- 个人标识号
- personalidnumber#
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#


## <a name="estonia-passport-number"></a>爱沙尼亚护照号码
此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

一个字母后跟七个数字，不含空格或分隔符
  
### <a name="pattern"></a>模式

一个字母后跟七个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_estonia_eu_passport_number` 找到与该模式匹配的内容。 
- 找到或中的关键字  `Keywords_eu_passport_number_common` `Keywords_estonia_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

eesti kodaniku pass passi number passinumbrid document number document 无 dokumendi nr

## <a name="eu-debit-card-number"></a>EU 借记卡号

### <a name="format"></a>Format

16 个数字

### <a name="pattern"></a>模式

非常复杂且强大的模式

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_eu_debit_card"></a>Keyword_eu_debit_card

- account number 
- card number 
- card no. 
- security number 
- 收件人# 

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
- 持卡人 
- cardholders 
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
- chequekaart 
- cirrus 
- cirrus-edc-maestro 
- controlekaart 
- controlekaarten 
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
- dinersclub 
- 确定 
- discover card 
- discover cards 
- discovercard 
- discovercards 
- débito automático
- edc 
- eigentümername 
- european debit card 
- hoofdkaart 
- hoofdkaarten 
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
- kreditkarte 
- kreditkarten-nummer 
- kreditkarteninhaber 
- kreditkarteninstitut 
- kreditkartennummer 
- kreditkartentyp 
- maestro 
- Master Card 
- master cards 
- mastercard 
- mastercards 
- emc 
- mister cash 
- n carta 
- carta 
- no de tarjeta 
- no do cartao 
- no do cartão 
- 不。 de tarjeta 
- 不。 do cartao 
- 不。 do cartão 
- nr carta 
- führerschein-nr. carta 
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
- n º。 do cartão 
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
- solo 
- supporti di scheda 
- supporto di scheda 
- 器 
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
- v-支付 
- 反之 
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
- 货. seg 
- 货. seguranca 
- 货. segurança 
- 货. sicurezza 
- codice di sicurezza 
- codice di verifica 
- codigo 
- codigo de seguranca 
- codigo de segurança 
- crittogramma 
- cryptogram 
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
- kreditkartenprufnummer 
- kreditkartenprüfnummer 
- kwestieaantal 
- 不。 dell'edizione 
- 不。 di sicurezza 
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
- veiligheidsaantal 
- veiligheidscode 
- veiligheidsnummer 
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
- 时间 
- 何时 
- 不久 
- 过期 
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


## <a name="eu-drivers-license-number"></a>欧盟驾驶执照号码

这些是欧盟驾驶执照号码敏感信息类型中的实体。

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
- [Luxemburg](#luxemburg-drivers-license-number)
- [马耳他](#malta-drivers-license-number)
- [荷兰](#netherlands-drivers-license-number)
- [波兰](#poland-drivers-license-number) 
- [Portugal（葡萄牙）](#portugal-drivers-license-number)
- [罗马尼亚](#romania-drivers-license-number)
- [斯洛伐克](#slovakia-drivers-license-number)
- [斯洛文尼亚](#slovenia-drivers-license-number)
- [西班牙](#spain-drivers-license-number)
- [瑞典](#sweden-drivers-license-number)
- [U.K.](#uk-drivers-license-number)


## <a name="eu-national-identification-number"></a>欧盟国家身份证号

这些是欧盟国家/地区标识号敏感信息类型中的实体。

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
- [Luxemburg](#luxemburg-national-identification-number-natural-persons)
- [马耳他](#malta-identity-card-number)
- [荷兰](#netherlands-citizens-service-bsn-number)
- [波兰](#poland-national-id-pesel)
- [Portugal（葡萄牙）](#portugal-citizen-card-number)
- [罗马尼亚](#romania-personal-numeric-code-cnp)
- [斯洛伐克](#slovakia-personal-number)
- [斯洛文尼亚](#slovenia-unique-master-citizen-number)
- [西班牙](#spain-dni)
- [U.K.](#uk-national-insurance-number-nino)                                        


## <a name="eu-passport-number"></a>EU 护照号码 

以下是欧盟护照号码敏感信息 typeThese 中的实体。欧盟护照号码捆绑包中的实体。

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
- [Luxemburg](#luxemburg-passport-number)
- [马耳他](#malta-passport-number)
- [荷兰](#netherlands-passport-number)
- [波兰](#poland-passport-number)
- [Portugal（葡萄牙）](#portugal-passport-number)
- [罗马尼亚](#romania-passport-number)
- [斯洛伐克](#slovakia-passport-number)
- [斯洛文尼亚](#slovenia-passport-number)
- [西班牙](#spain-passport-number)
- [瑞典](#sweden-passport-number)
- [U.K.](#us--uk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>EU 社会保险号或等效标识

这些是欧盟社会保险号或等效的标识敏感信息类型中的实体。

- [Austria（奥地利）](#austria-social-security-number-or-equivalent-identification)
- [Belgium（比利时）](#belgium-social-security-number-or-equivalent-identification)
- [Croatia（克罗地亚）](#croatia-social-security-number-or-equivalent-identification)
- [捷克语](#czech-social-security-number-or-equivalent-identification)
- [丹麦](#denmark-social-security-number-or-equivalent-identification)
- [Finland（芬兰）](#finland-social-security-number-or-equivalent-identification)
- [France（法国）](#france-social-security-number-insee-or-equivalent-identification)
- [Germany（德国）](#germany-identity-card-number)
- [希腊](#greece-national-id-card)
- [匈牙利](#hungary-social-security-number-or-equivalent-identification)
- [Portugal（葡萄牙）](#portugal-citizen-card-number)
- [西班牙](#spain-social-security-number-ssn)
- [瑞典](#sweden-social-security-number-or-equivalent-identification)


## <a name="eu-tax-identification-number"></a>EU 税标识号

这些实体采用欧盟税识别号敏感信息类型。

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
- [Luxemburg](#luxemburg-national-identification-number-non-natural-persons)
- [马耳他](#malta-tax-identification-number)
- [荷兰](#netherlands-tax-identification-number)
- [波兰](#poland-tax-identification-number)
- [Portugal（葡萄牙）](#portugal-tax-identification-number)
- [罗马尼亚](#romania-personal-numeric-code-cnp)
- [斯洛伐克](#slovakia-personal-number)
- [斯洛文尼亚](#slovenia-tax-identification-number)
- [西班牙](#spain-tax-identification-number)
- [瑞典](#sweden-tax-identification-number)
- [U.K.](#uk-unique-taxpayer-reference-number)


## <a name="finland-drivers-license-number"></a>芬兰驾照号码
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

10个数字，包含连字符
  
### <a name="pattern"></a>模式

10位数，包含连字符：
  
- 6位数字 
- 连字符
- 四位数 
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_finland_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_finland_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver "s_license_number

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- ajokortti


## <a name="finland-european-health-insurance-number"></a>芬兰欧洲健康保险电话号码
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

20位数字

### <a name="pattern"></a>模式

20位数字：

- 10位数-8024680246
- 可选空格或连字符
- 10位数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_Finland_European_Health_Insurance_Number 找到与该模式匹配的内容。
- 找到 Keyword_Finland_European_Health_Insurance_Number 中的关键字。

```xml
      <!-- Finland European Health Insurance Number -->
      <Entity id="60f75aed-81bf-4625-89b0-0846b9248ee7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Finland_European_Health_Insurance_Number"/>
          <Match idRef="Keyword_Finland_European_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>关键字

#### <a name="keyword_finland_european_health_insurance_number"></a>Keyword_finland_european_health_insurance_number

- ehic#
- ehic
- finlandehicnumber#
- finska sjukförsäkringskort
- 运行状况卡片
- 健康保险卡
- 健康保险号
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- sjukförsäkring nummer
- sjukförsäkringskort
- suomen sairausvakuutuskortti
- terveyskortti


## <a name="finland-national-id"></a>芬兰国家/地区 ID

### <a name="format"></a>Format

6个数字加上一个字符，表示一个世纪加上三个数字加上校验位

### <a name="pattern"></a>模式

模式必须包括以下各项：
- 6位数，格式格式为 DDMMYY，表示出生日期 
- 世纪标记 (是 "-"、"+" 或 "a" )  
- 三位数的个人标识号码 
- 不区分大小写的数字或字母 () 是校验位

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_finnish_national_id 找到与该模式匹配的内容
- 找到 Keyword_finnish_national_id 中的关键字
- 校验和传递

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_finnish_national_id 找到与该模式匹配的内容
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

### <a name="keywords"></a>关键字

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero#
- henkilötunnusnumero
- hetu
- id 号
- id 号
- identification number

- identiteetti numero
- 标识号码
- idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
- 国家/地区 id 卡片
- 国家/地区 id 编号。
- 个人 id
- 个人标识代码
- personalidnumber#
- personbeteckning
- personnummer
- social security number

- sosiaaliturvatunnus
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="finland-passport-number"></a>芬兰护照号码
此敏感信息类型实体可用于欧盟护照号敏感信息类型，并可用作独立的敏感信息类型实体。

### <a name="format"></a>Format
九个字母和数字的组合

### <a name="pattern"></a>模式
九个字母和数字的组合：
- 两个字母 (不区分大小写)  
- 七位数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_finland_passport_number 找到与该模式匹配的内容。
- 找到 Keywords_eu_passport_number_common 或 Keyword_finland_passport_number 中的关键字。

```xml
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
        </Pattern>
</Entity>
```
### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- suomalainen passi
- passin numero
- passin numero.#
- passin numero#
- passin numero.
- passi#
- passi 编号


## <a name="finland-social-security-number-or-equivalent-identification"></a>芬兰社会保障号或等效标识
此敏感信息类型实体仅适用于欧盟社会保险号码或等效 ID 敏感信息类型。

### <a name="format"></a>Format

指定格式的11个字符的组合
  
### <a name="pattern"></a>模式

指定格式的11个字符的组合：
  
- 6位数字 
- 以下任一实例：
  - 加号符号
  - 负号
  - 字母 "A" (不区分大小写) 
- 三个数字
- 一个字母或一个数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_finland_eu_ssn_or_equivalent` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_finland_eu_ssn_or_equivalent` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_finland_eu_ssn_or_equivalent` 找到与该模式匹配的内容。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a>Keywords_finland_eu_ssn_or_equivalent

- identification number
- 个人 id
- 标识号码
- 芬兰国家/地区 id 号
- personalidnumber#
- national identification number
- id 号
- 国家/地区 id 编号。
- 国家/地区 id 号
- id 号
- tunnistenumero
- henkilötunnus
- yksilöllinen henkilökohtainen tunnistenumero
- ainutlaatuinen henkilökohtainen tunnus
- identiteetti numero
- suomen kansallinen henkilötunnus
- henkilötunnusnumero#
- kansallisen tunnistenumero
- tunnusnumero
- kansallinen tunnus numero
- hetu


## <a name="france-drivers-license-number"></a>法国驾驶执照号码
此敏感信息类型实体在欧盟驱动程序的 "敏感信息类型" 中可用，并可用作独立的敏感信息类型实体。

### <a name="format"></a>Format

12 个数字

### <a name="pattern"></a>模式

12 个数字，会对类似模式（如法国电话号码）进行验证

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_french_drivers_license 找到与该模式匹配的内容。
- 至少满足以下条件之一：
- 找到 Keyword_french_drivers_license 中的关键字。
- 函数 Func_eu_date 找到正确日期格式的日期。

```xml
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- drivers licence
- drivers license
- driving licence
- driving license
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers


## <a name="france-health-insurance-number"></a>法国健康保险号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

21位数字

### <a name="pattern"></a>模式

21位数字：

- 10位数字
- 一个可选空格
- 10位数字
- 一个可选空格
- 一个数字


### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_France_Health_Insurance_Number 找到与该模式匹配的内容。
- 找到 Keyword_France_Health_Insurance_Number 中的关键字。

```xml
      <!-- France Health Insurance Number -->
      <Entity id="9bc2069e-76df-4ff9-ac02-2f519469e236" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_France_Health_Insurance_Number"/>
          <Match idRef="Keyword_France_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>关键字

#### <a name="keyword_france_health_insurance_number"></a>Keyword_France_health_insurance_number

- 保险卡
- vitale
- d'assuré社交


## <a name="france-national-id-card-cni"></a>法国国家 id 卡片 (CNI) 

### <a name="format"></a>Format

12 个数字

### <a name="pattern"></a>模式

12 个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_france_cni 找到与该模式匹配的内容。
- 找到 Keywords_france_eu_national_id_card 中的关键字。

```xml
    <!-- France CNI -->
    <Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
        <Match idRef="Keywords_france_eu_national_id_card" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_france_eu_national_id_card"></a>Keywords_france_eu_national_id_card

- card number

- nationale d'identité的购买
- nationale d'idenite
- cni#
- cni
- compte bancaire
- 国家/地区标识号
- 国家标识
- nationalidno#
- numéro d'assurance maladie
- numéro 的反 vitale

   
## <a name="france-passport-number"></a>法国护照号码
此敏感信息类型实体可用于欧盟护照号敏感信息类型，并可用作独立的敏感信息类型实体。

### <a name="format"></a>Format

9个数字和字母

### <a name="pattern"></a>模式

9个数字和字母：
- 两位数 
- 两个字母 (不区分大小写)  
- 五个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_fr_passport 找到与该模式匹配的内容。
- 找到 Keyword_passport 中的一个关键字。

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport #
- 登记卡#
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport#
- PasseportNon
- Passeportn °

      
## <a name="france-social-security-number-insee-or-equivalent-identification"></a>法国社会保障号 (INSEE) 或等效标识
此敏感信息类型实体包含在欧盟社会保险号和等效 ID 敏感信息类型中，可用作独立的敏感信息类型实体。

### <a name="format"></a>Format

15 个数字

### <a name="pattern"></a>模式

必须匹配两种模式之一：
- 13位数，后跟一个空格，后跟两个数字<br/>
或
- 15 个连续的数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：
- 函数 Func_french_insee 或 Func_fr_insee 找到与该模式匹配的内容。
- 找到 Keyword_fr_insee 中的一个关键字。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_french_insee 或 Func_fr_insee 找到与该模式匹配的内容。
- 未找到 Keyword_fr_insee 中的关键字。
- 校验和通过。

```xml
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- insee
- securité sociale
- securite sociale
- national id
- national identification
- numéro d identité
- no d'identité
- 不。 d'identité
- numero d'identite
- no d'identite
- 不。 d'identite
- social security number
- social security code
- social insurance number
- le numéro d'identification nationale
- d'identité nationale
- numéro de sécurité sociale
- le code de la sécurité sociale
- numéro d'assurance sociale
- numéro de sécu
- code sécu 

## <a name="france-tax-identification-number"></a>法国纳税标识号

### <a name="format"></a>Format

13 位数字
  
### <a name="pattern"></a>模式

13 位数字
  
- 一个数字，必须为0、1、2或3
- 1位
- 一个空格（可选） 
- 2位数 
- 一个空格（可选） 
- 3位数 
- 一个空格（可选） 
- 3位数 
- 一个空格（可选） 
- 3个校验位 

  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_france_eu_tax_file_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_france_eu_tax_file_number` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_france_eu_tax_file_number` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

- numéro d'identification fiscale
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#


## <a name="france-value-added-tax-number"></a>法国增值税号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

13个字符的字母数字模式

### <a name="pattern"></a>模式

13个字符的字母数字模式：

- 两个字母-FR (不区分大小写) 
- 可选空格或连字符
- 两个字母或数字
- 可选空格、点号、连字符或逗号
- 三个数字
- 可选空格、点号、连字符或逗号
- 三个数字
- 可选空格、点号、连字符或逗号
- 三个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_france_value_added_tax_number 找到与该模式匹配的内容。
- 找到 Keywords_france_value_added_tax_number 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_france_value_added_tax_number 找到与该模式匹配的内容。

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
### <a name="keywords"></a>关键字

#### <a name="keyword_france_value_added_tax_number"></a>Keyword_France_value_added_tax_number

- vat 号码
- vat 编号
- vat#
- 增值税
- siren 标识无 numéro d'identification taxe sur valeur ajoutée
- taxe valeur ajoutée
- taxe sur la valeur ajoutée
- n ° tva
- numéro de tva
- numéro d'identification siren


## <a name="germany-drivers-license-number"></a>德国驾驶执照号码
此敏感信息类型实体包含在欧盟驱动程序的 "敏感信息类型" 中，并可用作独立的敏感信息类型实体。

### <a name="format"></a>Format

11个数字和字母的组合

### <a name="pattern"></a>模式

11 位数字和字母（不区分大小写）：
- 一个数字或字母 
- 两位数 
- 六个数字或字母 
- 一个数字 
- 一个数字或字母

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_german_drivers_license 找到与该模式匹配的内容。
- 下列至少其中一项为真：
    - 找到 Keyword_german_drivers_license_number 中的一个关键字。
    - 找到 Keyword_german_drivers_license_collaborative 中的一个关键字。
    - 找到 Keyword_german_drivers_license 中的一个关键字。
- 校验和通过。

```xml
<!-- Germany Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

- Führerschein-nr
- Fuhrerschein
- Fuehrerschein
- Führerscheinnummer
- Fuhrerscheinnummer
- Fuehrerscheinnummer
- Führerschein-nr 
- Fuhrerschein- 
- Fuehrerschein- 
- FührerscheinnummerNr
- FuhrerscheinnummerNr
- FuehrerscheinnummerNr
- FührerscheinnummerKlasse
- FuhrerscheinnummerKlasse
- FuehrerscheinnummerKlasse
- Führerschein-Nr
- Fuhrerschein- Nr
- Fuehrerschein- Nr 
- Führerschein- Klasse 
- Fuhrerschein- Klasse 
- Fuehrerschein- Klasse
- FührerscheinnummerNr 
- FuhrerscheinnummerNr 
- FuehrerscheinnummerNr 
- FührerscheinnummerKlasse 
- FuhrerscheinnummerKlasse 
- FuehrerscheinnummerKlasse 
- Führerschein-Nr 
- Fuhrerschein- Nr 
- Fuehrerschein- Nr 
- Führerschein- Klasse 
- Fuhrerschein- Klasse 
- Fuehrerschein- Klasse 
- 通讯 
- DLS
- Driv Lic 
- Driv Licen 
- Driv License
- Driv Licenses 
- Driv Licence 
- Driv Licences 
- Driv Lic 
- Driver Licen 
- Driver License 
- Driver Licenses 
- Driver Licence 
- Driver Licences 
- Drivers Lic 
- Drivers Licen 
- Drivers License 
- Drivers Licenses 
- Drivers Licence 
- Drivers Licences 
- Driver's Lic 
- Driver's Licen 
- Driver's License 
- Driver's Licenses 
- Driver's Licence 
- Driver's Licences 
- Driving Lic 
- Driving Licen 
- Driving License 
- Driving Licenses 
- Driving Licence 
- Driving Licences

#### <a name="keyword_german_drivers_license_collaborative"></a>Keyword_german_drivers_license_collaborative

- Nr-Führerschein-nr 
- Nr-Fuhrerschein 
- Nr-Fuehrerschein 
- Führerschein-nr 
- Fuhrerschein 
- Fuehrerschein 
- N-Führerschein-nr 
- N-Fuhrerschein 
- N-Fuehrerschein
- Nr-Führerschein-nr 
- Nr-Fuhrerschein 
- Nr-Fuehrerschein 
- Führerschein-nr 
- Fuhrerschein 
- Fuehrerschein 
- N-Führerschein-nr 
- N-Fuhrerschein 
- N-Fuehrerschein 

#### <a name="keyword_german_drivers_license"></a>Keyword_german_drivers_license

- ausstellungsdatum
- ausstellungsort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde


## <a name="germany-identity-card-number"></a>德国身份卡片编号

### <a name="format"></a>Format

自2010年11月1日起：九个字母和数字

从1年4月1987至31年10月2010：10位数字

### <a name="pattern"></a>模式

自2010年11月1日起：
- 一个字母 (不区分大小写)  
- 八位数字

介于1年4月1987至 31 10 月2010：
- 10位数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_germany_id_card 找到与该模式匹配的内容。
- 找到 Keyword_germany_id_card 中的一个关键字。

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- ausweis
- gpid
- id
- identifikation
- identifizierungsnummer
- identity 卡片
- 标识号码
- id-nummer
- 个人 id
- personalausweis
- persönliche id nummer
- persönliche identifikationsnummer
- persönliche-id-nummer


## <a name="germany-passport-number"></a>德国护照号码
此敏感信息类型实体包含在欧盟护照号敏感信息类型中，可用作独立的敏感信息类型实体。

### <a name="format"></a>Format

10个数字或字母

### <a name="pattern"></a>模式

模式必须包括以下各项：
- 第一个字符是数字或从该集合中的字母 (C、F、G、H、J、K)  
- 三个数字 
- 此集合中的五个数字或字母 (C、-H、J-N、P、R、T、V-Z)  
- 一个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_german_passport 找到与该模式匹配的内容。
- 找到了中的关键字 `Keyword_german_passport` 。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_german_passport_data 找到与该模式匹配的内容。
- 找到了中的关键字 `Keyword_german_passport` 。
- 校验和通过。

```xml
    <!-- German Passport Number -->
    <Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Match idRef="Keyword_german_passport" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Match idRef="Keyword_german_passport" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- reisepasse
- reisepassnummer
- Reisepass 
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe
- passeport。
- passeport no

## <a name="germany-tax-identification-number"></a>德国税号标识号

### <a name="format"></a>Format

11个数字，无空格和分隔符
  
### <a name="pattern"></a>模式

11位数字：
  
- 两位数字 
- 可选空格
- 三位数字 
- 可选空格
- 三位数字 
- 可选空格
- 两位数字
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_germany_eu_tax_file_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_germany_eu_tax_file_number` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_germany_eu_tax_file_number` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_germany_eu_tax_file_number"></a>Keywords_germany_eu_tax_file_number

- identifikationsnummer
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#
- zinn#
- zinn
- zinnnummer


## <a name="germany-value-added-tax-number"></a>德国增值税号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

11个字符的字母数字模式

### <a name="pattern"></a>模式

11个字符的字母数字模式：

- 字母 D 或 D
- 字母 E 或 E
- 一个可选空格
- 三个数字
- 可选空格或逗号
- 三个数字
- 可选空格或逗号
- 三个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_germany_value_added_tax_number 找到与该模式匹配的内容。
- 找到 Keywords_germany_value_added_tax_number 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_germany_value_added_tax_number 找到与该模式匹配的内容。

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
### <a name="keywords"></a>关键字

#### <a name="keyword_germany_value_added_tax_number"></a>Keyword_germany_value_added_tax_number

- vat 号码
- vat 编号
- vat#
- vat # mehrwertsteuer
- mwst
- mehrwertsteuer identifikationsnummer
- mehrwertsteuer nummer


## <a name="greece-drivers-license-number"></a>希腊驱动程序的许可证编号
此敏感信息类型实体包含在欧盟驱动程序的 "敏感信息类型" 中，并可用作独立的敏感信息类型实体。

### <a name="format"></a>Format

9个数字，不带空格和分隔符
  
### <a name="pattern"></a>模式

九位数字 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_greece_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_greece_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver "s_license_number

- dlL#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- δεια οδήγησης
- Adeia odigisis


## <a name="greece-national-id-card"></a>希腊国家 ID 卡

### <a name="format"></a>Format

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

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_greece_id_card 找到与该模式匹配的内容。
- 找到 Keyword_greece_id_card 中的一个关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- 希腊语 id
- 希腊国家 id
- 希腊语个人 id 卡
- 希腊警察 id
- identity 卡片
- tautotita
- ταυτότητα
- ταυτότητας


## <a name="greece-passport-number"></a>希腊护照号码

此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

两个字母后跟七个数字，不含空格或分隔符
  
### <a name="pattern"></a>模式

两个字母后跟七个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式  `Regex_greece_eu_passport_number` 找到与该模式匹配的内容。 
- 找到或中的关键字  `Keywords_eu_passport_number_common` `Keywords_greece_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο

## <a name="greece-tax-identification-number"></a>希腊税标识号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

9个数字，不带空格和分隔符
  
### <a name="pattern"></a>模式

九个数字
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式  `Regex_greece_eu_tax_file_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_greece_eu_tax_file_number` 。 
    
```xml
      <!-- Greek Tax Identification Number -->
      <Entity id="15a54a5a-53d4-4080-ad43-a2a4fe1d3bf7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

- afm#
- afm
- aφμ | aφμαριθμός
- aφμ
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- 税务注册表号
- 税务注册表号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- taxregistryno#
- 纳税人 id
- tin 编号
- 锡#
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>香港 HKID) 号码的香港身份卡片 (

### <a name="format"></a>Format

8-9 个字母和数字组合，最后一个字符两边可选择加括号

### <a name="pattern"></a>模式

8-9 个字母组合：
- 1-2 个字母（不区分大小写）  
- 六个数字  
- 最后一个字符（任意数字或字母 A）是校验位，两边可以选择加括号。

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_hong_kong_id_card 找到与该模式匹配的内容。
- 找到 Keyword_hong_kong_id_card 中的一个关键字。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_hong_kong_id_card"></a>Keyword_hong_kong_id_card

- hkid
- 中国香港恒等卡片
- HKIDC
- id card
- identity card
- hk identity 卡片
- 香港 id
- 香港身份證
- 香港永久性居民身份證
- 證
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

   
## <a name="hungary-drivers-license-number"></a>匈牙利驱动程序的许可证编号

此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

两个字母后跟六个数字
  
### <a name="pattern"></a>模式

两个字母和六个数字：
  
- 两个字母 (不区分大小写)  
- 六个数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式  `Regex_hungary_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_hungary_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver "s_license_number

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- vezetoi engedely


## <a name="hungary-personal-identification-number"></a>匈牙利个人标识号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

11 个数字
  
### <a name="pattern"></a>模式

11 个数字：
  
- 一种与性别相对应的数字 (1-男、2-女、其他号码也可能适用于在具有双公民的1900或公民之前出生的公民)  
- 与出生日期 (YYMMDD) 的6个数字
- 与序列号对应的三个数字
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数  `Func_hungary_eu_national_id_card` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_hungary_eu_national_id_card` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数  `Func_hungary_eu_national_id_card` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- id 号
- identification number

- sz ig
- sz.ig.
- ig。
- személyazonosító igazolvány
- személyi igazolvány


## <a name="hungary-passport-number"></a>匈牙利护照号码

此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

两个字母后跟6个或7个数字，不含空格或分隔符
  
### <a name="pattern"></a>模式

两个字母后跟六个或七个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式  `Regex_hungary_eu_passport_number` 找到与该模式匹配的内容。 
- 找到或中的关键字  `Keywords_eu_passport_number_common` `Keywords_hungary_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```
### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- útlevél száma
- Útlevelek száma
- útlevél szám

## <a name="hungary-social-security-number-or-equivalent-identification"></a>匈牙利社会安全号码或等效标识

此敏感信息类型实体仅适用于欧盟社会保险号码或等效 ID 敏感信息类型。

### <a name="format"></a>Format

9个数字，不带空格和分隔符
  
### <a name="pattern"></a>模式

九个数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数  `Func_hungary_eu_ssn_or_equivalent` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_hungary_eu_ssn_or_equivalent` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数  `Func_hungary_eu_ssn_or_equivalent` 找到与该模式匹配的内容。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

- 匈牙利语社会安全号码
- social security number
- socialsecuritynumber#
- hssn#
- socialsecuritynno
- hssn
- taj
- taj#
- ssn
- ssn#
- 社会保障号
- áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- magyar áfa szám


## <a name="hungary-tax-identification-number"></a>匈牙利纳税标识号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

10个数字，不含空格或分隔符
  
### <a name="pattern"></a>模式

10位数字：
  
- 一个必须为 "8" 的数字 
- 八个数字
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数  `Func_hungary_eu_tax_file_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_hungary_eu_tax_file_number` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数  `Func_hungary_eu_tax_file_number` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

- adóazonosító szám
- adóhatóság szám
- adószám
- 匈牙利纳税人标识号
- hungatiantin#
- 税务主管机构编号
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#
- vat 号码


## <a name="hungary-value-added-tax-number"></a>匈牙利增值税号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

10个字符的字母数字模式

### <a name="pattern"></a>模式

10个字符的字母数字模式：

- 2个字母-HU 或 HU
- 可选空格
- 8位数

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：

- 函数 Func_hungarian_value_added_tax_number 找到与该模式匹配的内容。
- 找到 Keywords_hungarian_value_added_tax_number 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：

- 函数 Func_hungarian_value_added_tax_number 找到与该模式匹配的内容。

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

### <a name="keywords"></a>关键字

#### <a name="keyword_hungary_value_added_tax_number"></a>Keyword_Hungary_value_added_tax_number

- vat
- 增值税号
- vat#
- vatno#
- hungarianvatno#
- 纳税编号
- 增值税áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám


## <a name="india-permanent-account-number-pan"></a> (PAN) 的印度永久帐户号

### <a name="format"></a>Format

10 个字母或数字

### <a name="pattern"></a>模式

10 个字母或数字：
- 五个字母（不区分大小写）  
- 四个数字 
- 一个字母，是字母校验位

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_india_permanent_account_number 找到与该模式匹配的内容。
- 找到 Keyword_india_permanent_account_number 中的一个关键字。
- 校验和通过。

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Permanent Account Number 
- 蛋糕 
   
## <a name="india-unique-identification-aadhaar-number"></a>印度唯一标识 (Aadhaar) 号码

### <a name="format"></a>Format

12 个数字（包含可选空格或短划线）

### <a name="pattern"></a>模式

12 个数字：
- 四个数字 
- 一个可选空格或短划线  
- 四个数字 
- 一个可选空格或短划线  
- 最后一个数字是校验位

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_india_aadhaar 找到与该模式匹配的内容。
- 找到 Keyword_india_aadhar 中的一个关键字。
- 校验和通过。
- 
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：

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
### <a name="keywords"></a>关键字
   
#### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar
- Aadhar
- Aadhaar
- UID
- आधार
   
## <a name="indonesia-identity-card-ktp-number"></a>印度尼西亚身份卡片 (KTP) 号码

### <a name="format"></a>Format

16 个数字（包含可选点）

### <a name="pattern"></a>模式

16 个数字：
- 两位省代码  
- 一个点（可选）  
- 两位摄政统治区或城市代码  
- 两位住宅小区代码  
- 一个点（可选）  
- 六个数字，采用  DDMMYY 格式，代表出生日期  
- 一个点（可选）  
- 四个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：

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

### <a name="keywords"></a>关键字
   
#### <a name="keyword_indonesia_id_card"></a>Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk 
- Nomor Induk Kependudukan 
   
## <a name="international-banking-account-number-iban"></a> (IBAN) 的国际银行帐户号

### <a name="format"></a>Format

国家/地区代码（两个字母）加校验位（两个数字）以及 bban 号码（最多 30 个字符）

### <a name="pattern"></a>模式

模式必须包括以下各项：

- 两个字母的国家/地区代码
- 两个校验位（后跟一个可选空间）  
- 1-7 个包含 4 个字母或数字的组（可以使用空格进行分隔）
- 1-3 个字母或数字

每个国家/地区的格式稍有不同。IBAN 敏感信息类型涵盖这 60 个国家/地区：

ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：

- 函数 Func_iban 找到与该模式匹配的内容。
- 校验和通过。

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

无

   
## <a name="international-classification-of-diseases-icd-10-cm"></a>国际分类的 diseases (ICD-10-CM) 

### <a name="format"></a>Format

Dictionary

### <a name="pattern"></a>模式

关键字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 找到 Dictionary_icd_10_updated 中的关键字。
- 找到 Dictionary_icd_10_codes 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 找到 Dictionary_icd_10_ 更新的关键字。

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

### <a name="keywords"></a>关键字

Dictionary_icd_10_updated 关键字词典中的任何术语，基于 [国际分类 Diseases、第10次修订、临床修改 (icd-10-CM) ](https://go.microsoft.com/fwlink/?linkid=852604)。 此类型仅查找术语，而不是保险代码。

Dictionary_icd_10_codes 关键字词典中的任何术语，基于 [国际分类 Diseases、第10次修订、临床修改 (icd-10-CM) ](https://go.microsoft.com/fwlink/?linkid=852604)。 此类型仅查找保险业代码，而不是说明。

## <a name="international-classification-of-diseases-icd-9-cm"></a>国际分类的 diseases (ICD-9-CM) 

### <a name="format"></a>Format

Dictionary

### <a name="pattern"></a>模式

关键字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 找到 Dictionary_icd_9_updated 中的关键字。
- 找到 Dictionary_icd_9_codes 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 找到 Dictionary_icd_9_updated 中的关键字。

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

### <a name="keywords"></a>关键字

Dictionary_icd_9_updated 关键字词典中的任何术语，基于 [国际分类的 Diseases、第九修订版、临床修改 (icd-9-CM) ](https://go.microsoft.com/fwlink/?linkid=852605)。 此类型仅查找术语，而不是保险代码。

Dictionary_icd_9_codes 关键字词典中的任何术语，基于 [国际分类的 Diseases、第九修订版、临床修改 (icd-9-CM) ](https://go.microsoft.com/fwlink/?linkid=852605)。 此类型仅查找保险业代码，而不是说明。

## <a name="ip-address"></a>IP 地址

### <a name="format"></a>Format

#### <a name="ipv4"></a>IPv4
解释 IPv4 地址格式化（点）版本或非格式化（没有点）版本的复杂模式

#### <a name="ipv6"></a>Ipv4
 解释格式化 IPv6 号码（包含冒号）的复杂模式

### <a name="pattern"></a>模式

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_ipv6_address 找到与该模式匹配的内容。
- 未找到 Keyword_ipaddress 中的关键字。

对于 IPv4，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_ipv4_address 找到与该模式匹配的内容。
- 找到 Keyword_ipaddress 中的一个关键字。

对于 IPv6，在 300 个字符的相似度内，如果出现以下情况，DLP 策略 95% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP（此关键字区分大小写）
- ip address 
- ip addresses
- internet protocol
- IP-כתובת ה 

## <a name="ireland-drivers-license-number"></a>爱尔兰驾照号码

此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

6位数，后跟四个字母
  
### <a name="pattern"></a>模式

6位数字和四个字母：
  
- 六位数字
- 四个字母 (不区分大小写) 
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式  `Regex_ireland_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_ireland_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver "s_license_number

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- ceadúnas tiomána


## <a name="ireland-passport-number"></a>爱尔兰护照号码

此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

两个字母或数字后跟七个数字，不含空格或分隔符
  
### <a name="pattern"></a>模式

两个字母或数字，后跟七个数字：
  
- 两位数字或字母（不区分大小写）
- 七个数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式  `Regex_ireland_eu_passport_number` 找到与该模式匹配的内容。 
- 找到或中的关键字  `Keywords_eu_passport_number_common` `Keywords_ireland_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passeport numero
- uimhreacha pasanna
- uimhir pas
- uimhir phas
- uimhreacha pas
- uimhir cárta
- uimhir chárta

## <a name="ireland-personal-public-service-pps-number"></a>爱尔兰个人公开服务 (PPS) 号码

### <a name="format"></a>Format

旧格式 (到 31 Dec 2012) ：
- 七位数字后跟1-2 个字母 

新格式 (1 Jan 2013 和) 之后）：
- 七位数字后跟两个字母

### <a name="pattern"></a>模式

旧格式 (到 31 Dec 2012) ：
- 七位数字 
- 一到两个字母 (不区分大小写)  

新格式 (1 Jan 2013 和) 之后）：
- 七位数字 
- 字母 (区分大小写) 这是字母校验位 
- 一个-I 范围内的可选字母，或 "W"

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_ireland_pps 找到与该模式匹配的内容。
- 找到 Keywords_ireland_eu_national_id_card 中的关键字。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

- 客户端标识服务
- identification number

- 个人 id 号
- 个人公开服务号码
- 个人服务编号
- phearsanta seirbhíse poiblí
- pps no
- pps 号码
- pps num
- pps 服务否
- ppsn
- ppsno#
- ppsno
- psp
- 公共服务编号
- publicserviceno#
- publicserviceno
- 收入和社会保险电话号码
- rsi no
- rsi 编号
- rsin
- seirbhís aitheantais 客户端
- uimh
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#


## <a name="israel-bank-account-number"></a>以色列银行帐号

### <a name="format"></a>Format

13 位数字

### <a name="pattern"></a>模式

格式
- 两位数 
- 短划线 
- 三个数字 
- 短划线 
- 八位数字

纯
- 	13 个连续的数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- Bank Account Number 
- Bank Account 
- Account Number 
- מספר חשבון בנק 
   
## <a name="israel-national-identification-number"></a>以色列国家身份证号

### <a name="format"></a>Format

九位数字

### <a name="pattern"></a>模式

九个连续数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_israel_national_id"></a>Keyword_Israel_National_ID

- מספר זהות 
- National ID Number
   
## <a name="italy-drivers-license-number"></a>意大利驾驶执照号码
此敏感信息类型实体包含在欧盟驱动程序的 "敏感信息类型" 中，并可用作独立的敏感信息类型实体。

### <a name="format"></a>Format

10个字母和数字的组合

### <a name="pattern"></a>模式

- 10个字母和数字的组合：
- 一个字母 (不区分大小写)  
- 字母 "A" 或 "V" (不区分大小写)  
- 七个字母 (不区分大小写) 、数字或下划线字符 
- 一个字母 (不区分大小写) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_italy_drivers_license_number 找到与该模式匹配的内容。
- 找到 Keyword_italy_drivers_license_number 中的一个关键字。

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente di guida 
- patente di guida 

## <a name="italy-fiscal-code"></a>意大利会计代码
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

在指定模式中，由16个字符组成的字母和数字的组合
  
### <a name="pattern"></a>模式

字母和数字的16个字符的组合：
- 与系列名称中的前三个辅音对应的三个字母
- 与名字中的第一个、第三个和第四个辅音对应的三个字母
- 与出生年份的最后一个数字对应的两个数字
- 一个与出生月份的字母相对应的字母–字母按字母顺序使用，但仅使用字母 A 到 E、H、L、M、P、R 和 T (因此，一月为 A，10月为 R) 
- 与出生月份的某一天对应的两个数字，为了区分 genders，40已添加到女性的出生日。
- 与特定于 municipality 的区域代码相对应的四个数字，该用户的出生国家 (国家/地区内的代码用于外国国家) 
- 一个奇偶校验数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_italy_eu_national_id_card` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_italy_eu_national_id_card` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_italy_eu_national_id_card` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

- codice 会计
- codice fiscale
- codice id personale
- codice personale
- 会计代码
- numero certificato personale
- numero di identificazione fiscale
- numero id personale
- numero personale
- 个人证书号码
- 个人代码
- 个人 id 代码
- 个人 id 号
- personalcodeno#
- 税码
- tax id

- 税号标识编号
- 税标识号
- 纳税标识编号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#


## <a name="italy-passport-number"></a>意大利护照号码
此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

两个字母或数字后跟七个数字，不含空格或分隔符
  
### <a name="pattern"></a>模式

两个字母或数字，后跟七个数字：
  
- 两个数字或字母 (不区分大小写) 
- 七位数字
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_italy_eu_passport_number` 找到与该模式匹配的内容。 
- 找到或中的关键字  `Keywords_eu_passport_number_common` `Keywords_italy_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana passaporto
- passaporto italiana
- passaporto numero
- numéro passeport
- numero di passaporto
- numeri del passaporto
- passeport italien

## <a name="italy-value-added-tax-number"></a>意大利增值税号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

带有可选分隔符的13个字符的字母数字模式

### <a name="pattern"></a>模式

带有可选分隔符的13个字符的字母数字模式：

- I 或 i
- T 或 t
- 可选空格、点号、连字符或逗号
- 11 个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_italy_value_added_tax_number 找到与该模式匹配的内容。
- 找到 Keywords_italy_value_added_tax_number 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_italy_value_added_tax_number 找到与该模式匹配的内容。

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

### <a name="keywords"></a>关键字

#### <a name="keyword_italy_value_added_tax_number"></a>Keyword_italy_value_added_tax_number

- vat 号码
- vat 编号
- vat#
- iva
- iva#


## <a name="japan-bank-account-number"></a>日本银行帐户号码

### <a name="format"></a>Format

7或8位数字

### <a name="pattern"></a>模式

银行帐户号码：
- 7或8位数字
- 银行帐户分支代码：
- 四位数 
- 可选) 的空格或短划线 ( 
- 三个数字

校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_jp_bank_account 找到与该模式匹配的内容。
- 找到 Keyword_jp_bank_account 中的一个关键字。
- 下列其中一项为真：
- 函数 Func_jp_bank_account_branch_code 找到与该模式匹配的内容。
- 找到 Keyword_jp_bank_branch_code 中的一个关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

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
- 口座番号を当座預金口座の確認 
- #アカウントの確認、勘定番号の確認 
- #勘定の確認 
- 勘定番号の確認 
- 口座番号の確認 
- 銀行口座番号 
- 銀行口座 
- 銀行口座＃ 
- 銀行の勘定番号 
- 銀行のacct＃ 
- 銀行の勘定いいえ 
- 銀行口座番号
- 普通預金口座番号 
- 預金口座 
- 貯蓄口座＃ 
- 貯蓄勘定の数 
- 貯蓄勘定＃ 
- 貯蓄勘定番号 
- 普通預金口座番号 
- 引き落とし口座番号 
- 口座番号 
- 口座番号＃ 
- デビットのacct番号 
- デビット勘定＃ 
- デビットACCTの番号 
- デビット口座番号 

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

Otemachi

## <a name="japan-drivers-license-number"></a>日本驾驶执照号码

### <a name="format"></a>Format

12 个数字

### <a name="pattern"></a>模式

12 个连续的数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_jp_drivers_license_number"></a>Keyword_jp_drivers_license_number

- 通讯# 
- 通讯 
- dls# 
- DLS 
- driver license 
- driver licenses 
- drivers license 
- driver's license 
- drivers licenses 
- driver's licenses 
- driving licence 
- .lic# 
- .LIC 
- driver'lics# 
- state id 
- state identification 
- state identification number 
- 低所得国＃ 
- 免許証 
- 状態ID
- 状態の識別 
- 状態の識別番号 
- 運転免許 
- 運転免許証 
- 運転免許証番号 


## <a name="japan-my-number---corporate"></a>日本我的号码-公司
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

13位数字

### <a name="pattern"></a>模式

13位数字：

- 一位数从1到9
- 12 个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_japanese_my_number_corporate 找到与该模式匹配的内容。
- 找到 Keywords_japanese_my_number_corporate 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_japanese_my_number_corporate 找到与该模式匹配的内容。

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

### <a name="keywords"></a>关键字

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


## <a name="japan-my-number---personal"></a>日本我的号码-个人
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

12位数字

### <a name="pattern"></a>模式

12位数字：

- 四位数
- 可选空格、点号或连字符
- 四位数
- 可选空格、点号或连字符
- 四位数

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_japanese_my_number_personal 找到与该模式匹配的内容。
- 找到 Keywords_japanese_my_number_personal 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
- 函数 Func_japanese_my_number_personal 找到与该模式匹配的内容。

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

### <a name="keywords"></a>关键字

#### <a name="keyword_japan_my_number_personal"></a>Keyword_japan_my_number_personal

- 我的号码
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

### <a name="format"></a>Format

两个字母后跟七个数字

### <a name="pattern"></a>模式

两个字母 (不区分大小写) 后跟七位数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_jp_passport"></a>Keyword_jp_passport

- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート＃ 

## <a name="japan-residence-card-number"></a>日本住宅电话卡号

### <a name="format"></a>Format

12个字母和数字

### <a name="pattern"></a>模式

12个字母和数字：
- 两个字母 (不区分大小写) 
- 八位数字 
- 两个字母 (不区分大小写) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_jp_residence_card_number 找到与该模式匹配的内容。
- 找到 Keyword_jp_residence_card_number 中的关键字。

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- 住宅电话卡号
- 住宅卡编号
- 住宅卡片#
- 在留カード番号

## <a name="japan-resident-registration-number"></a>日本居民注册号码

### <a name="format"></a>Format

11 个数字

### <a name="pattern"></a>模式

11 个连续的数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_jp_resident_registration_number"></a>Keyword_jp_resident_registration_number

- Resident Registration Number
- Resident Register Number 
- Residents Basic Registry Number 
- Resident Registration No. 
- Resident Register No. 
- Residents Basic Registry No. 
- Basic Resident Register No. 
- 住民登録番号、登録番号をレジデント 
- 住民基本登録番号、登録番号 
- 住民基本レジストリ番号を常駐 
- 登録番号を常駐住民基本台帳登録番号 

   
## <a name="japan-social-insurance-number-sin"></a>日本社会保险号 (SIN) 

### <a name="format"></a>Format

7-12 个数字 

### <a name="pattern"></a>模式

7-12 位数字：
- 四位数 
- 连字符 (可选)  
- 六位数字或
- 7-12 个连续的数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_jp_sin 找到与该模式匹配的内容。
- 找到 Keyword_jp_sin 中的一个关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_jp_sin"></a>Keyword_jp_sin

- Social Insurance No. 
- Social Insurance Num 
- Social Insurance Number 
- 社会保険のテンキー 
- 社会保険番号 

## <a name="latvia-drivers-license-number"></a>拉脱维亚驾照号码
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

三个字母后跟六个数字
  
### <a name="pattern"></a>模式

三个字母和六个数字：
  
- 三个字母 (不区分大小写)  
- 6位数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_latvia_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_latvia_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver "s_license_number

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- autovadītāja apliecība

## <a name="latvia-personal-code"></a>拉脱维亚个人代码

### <a name="format"></a>Format

11个数字和一个可选连字符
  
### <a name="pattern"></a>模式

旧格式

11个数字和一个连字符：
  
- 与出生日期 (DDMMYY) 的6个数字 
- 连字符
- 一个数字，对应于19世纪的出生世纪 ( "0"，"1" 表示20世纪，"2" 表示21世纪) 
- 四个数字，随机生成

新格式

11 个数字

- 两位数 "32"
- 九个数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_latvia_eu_national_id_card` 或正则表达式 `Regex_latvia_eu_national_id_card_new_format` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_latvia_eu_national_id_card` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_latvia_eu_national_id_card` 或正则表达式 `Regex_latvia_eu_national_id_card_new_format` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- 管理号码
- alvas nē
- 出生号码
- 公民编号
- 民事号码
- 电子人口普查编号
- 电子号码
- 会计代码
- 医疗保健用户号码
- 号#
- id-代码
- identification number

- identifikācijas numurs
- id-号码
- 单个号码
- 拉脱维亚 alva
- nacionālais id
- 
national id
- 国家识别号
- 国家/地区身份证号码
- national insurance number

- 国家/地区寄存器号
- nodokļa numurs
- nodokļu id
- nodokļu identifikācija numurs
- 个人证书号码
- 个人代码
- 个人 id 代码
- 个人 id 号
- 个人标识代码
- 个人标识符
- 个人识别码
- 个人号码
- 个人数字代码
- personalcodeno#
- 角色 kods
- 填充标识代码
- 公用服务号码
- 
registration number
- 收入编号
- 社会保险号
- social security number

- 州税码
- 税文件编号
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#
- voter 的号码

## <a name="latvia-passport-number"></a>拉脱维亚护照号码
此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

两个字母或数字后跟七个数字，不含空格或分隔符
  
### <a name="pattern"></a>模式

两个字母或数字，后跟七个数字：
  
- 两个数字或字母 (不区分大小写) 
- 七位数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_latvia_eu_passport_number` 找到与该模式匹配的内容。 
- 找到或中的关键字  `Keywords_eu_passport_number_common` `Keywords_latvia_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- pase numurs
- pase numur
- pases numuri
- pases nr
- passeport no
- n du Passeport

## <a name="lithuania-drivers-license-number"></a>立陶宛驾照号码
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

8位数，不含空格和分隔符
  
### <a name="pattern"></a>模式

八位数字 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_lithuania_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_lithuania_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver "s_license_number

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- vairuotojo pažymėjimas

## <a name="lithuania-personal-code"></a>立陶宛个人代码
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

11个数字，无空格和分隔符
  
### <a name="pattern"></a>模式

11个数字，不含空格和分隔符：
  
- 一种数字 (1-6) ，对应于个人的性别和出生世纪
- 与出生日期 (YYMMDD) 的6个数字 
- 与出生日期的序列号对应的三个数字
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_lithuania_eu_tax_file_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_lithuania_eu_tax_file_number` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_lithuania_eu_tax_file_number` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

- asmeninis skaitmeninis kodas
- asmens kodas
- 公民服务号码
- mokesčių id
- mokesčių identifikavimas numeris
- mokesčių identifikavimo numeris
- mokesčių numeris
- 国家/地区标识号
- 个人代码
- 个人数字代码
- piliečio paslaugos numeris
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#
- unikalus identifikavimo kodas
- unikalus identifikavimo numeris
- 唯一标识号
- 唯一标识号
- uniqueidentityno#

## <a name="lithuania-passport-number"></a>立陶宛护照号码
此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

八个数字或字母不带空格或分隔符
  
### <a name="pattern"></a>模式

八个数字或字母 (不区分大小写) 
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_lithuania_eu_passport_number` 找到与该模式匹配的内容。 
- 找到或中的关键字  `Keywords_eu_passport_number_common` `Keywords_lithuania_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- paso numeris
- paso numeriai
- paso nr

## <a name="luxemburg-drivers-license-number"></a>Luxemburg 驾驶执照号码
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

6位数，不含空格和分隔符
  
### <a name="pattern"></a>模式

6位数字 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_luxemburg_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_luxemburg_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver "s_license_number

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- fahrerlaubnis

## <a name="luxemburg-national-identification-number-natural-persons"></a>Luxemburg (自然个人的国家标识号码) 
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

13个不带空格或分隔符的数字
  
### <a name="pattern"></a>模式

13 个数字：
  
- 11 个数字 
- 两个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_luxemburg_eu_tax_file_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_luxemburg_eu_national_id_card` 。 

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_luxemburg_eu_tax_file_number` 找到与该模式匹配的内容。 


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

### <a name="keywords"></a>关键字

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

- eindeutige id
- eindeutige id-nummer
- eindeutigeid#
- id personnelle
- idpersonnelle#
- idpersonnelle
- 单个代码
- 个人 id
- 单个标识
- 单个标识
- numéro d'identification 人员
- 个人 id
- 个人标识
- 个人标识
- personalidno#
- personalidnumber#
- persönliche identifikationsnummer
- 唯一 id
- 唯一标识
- uniqueidkey#

## <a name="luxemburg-passport-number"></a>Luxemburg 护照号码
此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

八个数字或字母不带空格或分隔符
  
### <a name="pattern"></a>模式

八个数字或字母 (不区分大小写) 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_nation_eu_passport_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_nation_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_nation_eu_passport_number"></a>Keywords_nation_eu_passport_number

- passport number
- 拉脱维亚语护照号码
- 护照号
- passnummer

## <a name="luxemburg-national-identification-number-non-natural-persons"></a>Luxemburg 国内标识号 (非自然个人) 

### <a name="format"></a>Format

11 个数字
  
### <a name="pattern"></a>模式

11 个数字
  
- 两位数
- 一个可选空格 
- 三个数字 
- 一个可选空格
- 三个数字 
- 一个可选空格
- 两位数
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_luxemburg_eu_tax_file_number_non_natural` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_luxemburg_eu_tax_file_number` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_luxemburg_eu_tax_file_number_non_natural` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

- 反 sécurité sociale
- étain 非
- étain#
- identifiant d'impôt
- 卢森堡税 identifikatiounsnummer
- numéro d'étain
- numéro d'identification 会计 luxembourgeois
- numéro d'identification fiscale
- 社会保障
- sozialunterstützung
- sozialversécherung
- sozialversicherungsausweis
- steier id
- steier identifikatiounsnummer
- steier nummer
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#
- zinn#
- zinn
- zinnzahl


## <a name="malaysia-identification-card-number"></a>马来西亚标识卡号

### <a name="format"></a>Format

12 个数字（包含可选连字符）

### <a name="pattern"></a>模式

12 个数字：
- 6位数，格式为 YYMMDD，表示出生日期 
- 短划线 (可选)  
- 两个字母的出生位置代码 
- 短划线 (可选)  
- 三个随机数字 
- 一位数的性别代码

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字
   
#### <a name="keyword_malaysia_id_card_number"></a>Keyword_malaysia_id_card_number

- 数字应用程序卡
- i/c
- i/c 否
- ic
- 内部公司编号
- id card
- 标识卡
- identity card
- k/p
- k/p no
- kad akuan diri
- kad aplikasi 数字
- kad pengenalan 马来西亚
- kp
- kp no
- mykad
- mykas
- mykid
- mypr
- mytentera
- 马来西亚身份卡片
- 马来西亚身份卡片
- nric
- 个人标识卡

## <a name="malta-drivers-license-number"></a>马耳他驾照号码
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

两个字符与指定模式中的六个数字的组合
  
### <a name="pattern"></a>模式

两个字符和六个数字的组合：
  
- 两个字符 (数字或字母，而不区分大小写) 
- 空格 (可选) 
- 三个数字
- 空格 (可选) 
- 三个数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_malta_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_malta_eu_driver's_license_number` 。 
    
```xml
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver "s_license_number

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- liċenzja tas-sewqan

## <a name="malta-identity-card-number"></a>马耳他身份卡片号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

七位数字后跟一个字母
  
### <a name="pattern"></a>模式

七位数字后跟一个字母：
  
- 七位数字 
- 在 "M、G、A、P、L、H、B、Z" (不区分大小写中的一个字母) 
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_malta_eu_national_id_card` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_malta_eu_national_id_card` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_malta_eu_national_id_card` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

- 公民服务号码
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta "identifikazzjoni personali
- numru ta "identifikazzjoni tat-taxxa
- numru ta "identifikazzjoni uniku
- numru ta "identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- 个人数字代码
- 唯一标识号
- 唯一标识号
- uniqueidentityno#


## <a name="malta-passport-number"></a>马耳他护照号码
此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

七位数字，不含空格或分隔符
  
### <a name="pattern"></a>模式

七位数字 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_malta_eu_passport_number` 找到与该模式匹配的内容。 
- 找到或中的关键字  `Keywords_eu_passport_number_common` `Keywords_malta_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- numru tal-passaport
- numri tal-passaport
- Nru tal-passaport

## <a name="malta-tax-identification-number"></a>马耳他税标识号

### <a name="format"></a>Format

对于马耳他 nationals：
- 七个数字和指定模式中的一个字母
  
非马耳他语 nationals 和马耳他语实体：
- 九位数字
  
### <a name="pattern"></a>模式

马耳他 nationals：七位数和一个字母
  
- 七位数字 
- 一个字母 (不区分大小写) 
    
非马耳他语 nationals 和马耳他语实体：9个数字
  
- 九位数字 
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_malta_eu_tax_file_number`  或 `Regex_malta_eu_tax_file_number_non_maltese_national` 查找与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_malta_eu_tax_file_number` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_malta_eu_tax_file_number` 或 `Regex_malta_eu_tax_file_number_non_maltese_national` 查找与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- 公民服务号码
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta "identifikazzjoni personali
- numru ta "identifikazzjoni tat-taxxa
- numru ta "identifikazzjoni uniku
- numru ta "identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- 个人数字代码
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#
- 唯一标识号
- 唯一标识号
- uniqueidentityno#

## <a name="netherlands-citizens-service-bsn-number"></a>荷兰公民服务 (BSN) 号码

### <a name="format"></a>Format

8-9 个数字，包含可选空格

### <a name="pattern"></a>模式

8-9 个数字：
- 三个数字 
- 空格 (可选)  
- 三个数字 
- 空格 (可选)  
- 双三位数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card
  
- bsn#
- bsn
- burgerservicenummer
- 公民服务号码
- 人员编号
- 个人号码
- 个人数字代码
- 人员相关号码
- persoonlijk nummer
- persoonlijke numerieke 代码
- persoonsgebonden
- persoonsnummer
- sociaal-fiscaal nummer
- 社会-会计号码
- sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- 唯一标识号
- 唯一标识号
- uniqueidentityno#

## <a name="netherlands-drivers-license-number"></a>荷兰驾驶执照号码
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

10个数字，无空格和分隔符
  
### <a name="pattern"></a>模式

10位数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_netherlands_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_netherlands_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver "s_license_number

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- permis de conduire
- rijbewijs
- rijbewijsnummer


## <a name="netherlands-passport-number"></a>荷兰护照号码
此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

九个字母或数字，不带空格或分隔符
  
### <a name="pattern"></a>模式

九个字母或数字
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_netherlands_eu_passport_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_netherlands_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- 荷兰护照号码
- passport number
- 荷兰护照号码
- nederlanden paspoort nummer
- paspoort
- nederlanden paspoortnummer
- paspoortnummer

## <a name="netherlands-tax-identification-number"></a>荷兰税标识号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

9个数字，不带空格或分隔符
  
### <a name="pattern"></a>模式

九位数字 
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_netherlands_eu_tax_file_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_netherlands_eu_tax_file_number` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
- 函数  `Func_netherlands_eu_tax_file_number` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

- btw nummer
- hollânske 税标识
- hulandes impuesto id 号
- hulandes impuesto 标识
- identificatienummer belasting
- identificatienummer van belasting
- impuesto 标识号
- impuesto 编号
- 荷兰语 belasting id nummer
- 荷兰语 belasting identificatie
- 荷兰语 belasting identificatienummer
- 荷兰语 belastingnummer
- nederlandse belasting identificatie
- 荷兰税务标识
- netherland 的税标识
- 荷属安的纳税人标识号
- netherland 的纳税人标识号
- tax id

- 税号标识编号
- 税标识号
- 税标识 tal
- 免税#
- 免税
- 税号
- 税务登记编号
- 税收 tal
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#


## <a name="netherlands-value-added-tax-number"></a>荷兰增值税号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

14个字符的字母数字模式

### <a name="pattern"></a>模式

14个字符的字母数字模式：

- N 或 n
- L 或 l
- 可选空格、点号或连字符
- 九位数字
- 可选空格、点号或连字符
- B 或 b
- 两位数

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_netherlands_value_added_tax_number 找到与该模式匹配的内容。
- 找到 Keywords_netherlands_value_added_tax_number 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_netherlands_value_added_tax_number 找到与该模式匹配的内容。

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

### <a name="keywords"></a>关键字

#### <a name="keyword_netherlands_value_added_tax_number"></a>Keyword_netherlands_value_added_tax_number

- vat 号码
- vat 编号
- vat#
- wearde tafoege 税 getal
- btw nûmer
- btw-nummer


## <a name="new-zealand-bank-account-number"></a>新西兰银行帐号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

14到16个带可选分隔符的数字模式

### <a name="pattern"></a>模式

14到16个带可选分隔符的数字模式：

- 两位数
- 一个可选连字符或空格
- 三到四位数字
- 一个可选连字符或空格
- 七位数字
- 一个可选连字符或空格
- 两到三个数字
- 一个选项连字符或空格

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_new_zealand_bank_account_number 找到与该模式匹配的内容。
- 找到 Keywords_new_zealand_bank_account_number 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_new_zealand_bank_account_number 找到与该模式匹配的内容。

```xml
      <!-- New Zealand Bank Account Number -->
      <Entity id="1a97fc2b-dd2f-48f1-bc4e-2ddf25813956" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
          <Match idRef="Keywords_new_zealand_bank_account_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_new_zealand_bank_account_number"></a>Keyword_new_zealand_bank_account_number

- 帐户号
- 银行帐户
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr


## <a name="new-zealand-drivers-license-number"></a>新西兰驾照号码
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

八个字符的字母数字模式

### <a name="pattern"></a>模式

八个字符的字母数字模式

- 两个字母 
- 6位数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_newzealand_driver_license_number 找到与该模式匹配的内容。
- 找到 Keywords_newzealand_driver_license_number 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
- 函数 Func_newzealand_driver_license_number 找到与该模式匹配的内容。

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

### <a name="keywords"></a>关键字

#### <a name="keyword_new_zealand_drivers_license_number"></a>Keyword_new_zealand_drivers_license_number

- driverlicence
- driverlicences
- 驱动程序许可证
- 驱动程序许可证
- 驱动程序许可证
- driverslic
- driverslicence
- driverslicences
- 驱动程序许可证
- 驱动程序 driver'lics
- 驱动程序许可证
- 驱动程序许可
- driver'lic
- driver'lics
- driver'licence
- driver'licences
- 驱动程序 "许可证
- 驱动程序 "driver'lics
- 驱动程序 ' 许可证
- 驱动程序 ' 许可证
- driver'slic
- driver'slics
- driver'slicence
- driver'slicences
- 驱动程序的许可证
- 驱动程序的 driver'lics
- 驾驶许可证
- 驾驶许可
- driverlic#
- driverlics#
- driverlicence#
- driverlicences#
- 驱动程序许可证#
- 驱动程序 driver'lics#
- 驱动程序许可证#
- 驱动程序许可证#
- driverslic#
- driverslics#
- driverslicence#
- driverslicences#
- 驱动程序许可证#
- 驱动程序 driver'lics#
- 驱动程序许可证#
- 驱动程序许可#
- driver'lic#
- driver'lics#
- driver'licence#
- driver'licences#
- 驱动程序 "许可证#
- 驱动程序 "driver'lics#
- 驱动程序 ' 许可证#
- 驱动程序 ' 许可证#
- driver'slic#
- driver'slics#
- driver'slicence#
- driver'slicences#
- 驱动程序的许可证#
- 驱动程序的 driver'lics#
- 驾驶许可证#
- 驾驶许可#
- 
international driving permit
- international driving permits
- 新西兰汽车协会
- 新西兰汽车协会


## <a name="new-zealand-inland-revenue-number"></a>新西兰 inland 收入编号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

八个或9个带可选分隔符的数字

### <a name="pattern"></a>模式

八个或9个带可选分隔符的数字

- 两个或三个数字
- 可选空格或连字符
- 三个数字
- 可选空格或连字符
- 三个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_new_zealand_inland_revenue_number 找到与该模式匹配的内容。
- 找到 Keywords_new_zealand_inland_revenue_number 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_new_zealand_inland_revenue_number 找到与该模式匹配的内容。

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

### <a name="keywords"></a>关键字

#### <a name="keyword_new_zealand_inland_revenue_number"></a>Keyword_new_zealand_inland_revenue_number

- ird。
- ird no#
- 新西兰 ird
- 新西兰 ird
- ird 编号
- inland 收入编号


## <a name="new-zealand-ministry-of-health-number"></a>新新西兰的运行状况号码

### <a name="format"></a>Format

三个字母、一个空格 (可选) 和四位数字

### <a name="pattern"></a>模式

三个字母 (不区分大小写)  (可选的空格) 四个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_new_zealand_ministry_of_health_number 找到与该模式匹配的内容。
- 找到 Keyword_nz_terms 中的一个关键字。
- 校验和通过。

```xml
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_nz_terms"></a>Keyword_nz_terms

- NHI 
- New Zealand 
- 健康 
- 治疗 


## <a name="new-zealand-social-wlefare-number"></a>新西兰社会 wlefare 号码
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

九位数字

### <a name="pattern"></a>模式

九位数字

- 三个数字
- 可选连字符
- 三个数字
- 可选连字符
- 三个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_newzealand_social_welfare_number 找到与该模式匹配的内容。
- 找到 Keywords_newzealand_social_welfare_number 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
- 函数 Func_newzealand_social_welfare_number 找到与该模式匹配的内容。

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

### <a name="keywords"></a>关键字

#### <a name="keyword_new_zealand_social_welfare_number"></a>Keyword_new_zealand_social_welfare_number

- 社交 welfare#
- 社交 welfare#
- 社会 welfare 编号
- 社会 welfare 号码
- swn#

   
## <a name="norway-identification-number"></a>挪威身份证号码

### <a name="format"></a>Format

11 个数字

### <a name="pattern"></a>模式

11 个数字：
- 6位数，格式为 DDMMYY，表示出生日期 
- 三位数的个人号码 
- 两个校验位

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_norway_id_number 找到与该模式匹配的内容。
- 找到 Keyword_norway_id_number 中的一个关键字。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_norway_id_number"></a>Keyword_norway_id_number

- Personal identification number
- Norwegian ID Number
- ID Number
- Id
- Personnummer
- Fødselsnummer

   
## <a name="philippines-unified-multi-purpose-identification-number"></a>菲律宾统一多用途标识号码

### <a name="format"></a>Format

12 个数字，通过连字符分隔 

### <a name="pattern"></a>模式

12 个数字：
- 四位数 
- 连字符 
- 七位数字 
- 连字符 
- 一位

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字
   
#### <a name="keyword_philippines_id"></a>Keyword_philippines_id

- Unified Multi-Purpose ID 
- UMID 
- Identity Card 
- Pinag-isang Multi-Layunin ID

## <a name="poland-drivers-license-number"></a>波兰驾驶执照号码
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

14位数，包含2个正斜杠
  
### <a name="pattern"></a>模式

14位数和2正斜杠：
  
- 五个数字 
- 一个正斜杠
- 两位数
- 一个正斜杠
- 七位数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_poland_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_poland_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver "s_license_number

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- prawo jazdy

## <a name="poland-identity-card"></a>波兰恒等卡片

### <a name="format"></a>Format

三个字母和六个数字

### <a name="pattern"></a>模式

三个字母 (不区分大小写) 后跟六位数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Dowód osobisty
- 器 dowodu osobistego
- Nazwa i 器 dowodu osobistego
- Nazwa i nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- dow. os.

   
## <a name="poland-national-id-pesel"></a>波兰国 ID (PESEL) 

### <a name="format"></a>Format

11 个数字

### <a name="pattern"></a>模式

- 表示出生日期的6个数字 YYMMDD 格式。
- 4位数字
- 1校验位

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_pesel_identification_number 找到与该模式匹配的内容。
- 找到 Keyword_pesel_identification_number 中的一个关键字。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_pesel_identification_number"></a>Keyword_pesel_identification_number

- dowód osobisty
- dowódosobisty
- niepowtarzalny 器
- niepowtarzalnynumer
- nr.-pesel
- nr-pesel
- 器 identyfikacyjny
- pesel
- tożsamości narodowej

   
## <a name="poland-passport-number"></a>波兰护照号码
此敏感信息类型实体包含在欧盟护照号敏感信息类型中，可用作独立的敏感信息类型实体。

### <a name="format"></a>Format

两个字母和七个数字

### <a name="pattern"></a>模式

两个字母（不区分大小写）后跟七个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_polish_passport_number 找到与该模式匹配的内容。
- 找到 Keyword_polish_national_id_passport_number 中的一个关键字。
- 校验和通过。

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- 器 paszportu
- Führerschein-nr. Paszportu
- Paszport

## <a name="poland-regon-number"></a>波兰 REGON 号码
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

9个数字或14个数字

### <a name="pattern"></a>模式

9个数字或14位数字：

- 九位数字或 
- 九位数字
- 号
- 五个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_polish_regon_number 找到与该模式匹配的内容。
- 找到 Keywords_polish_regon_number 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
- 函数 Func_polish_regon_number 找到与该模式匹配的内容。

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
### <a name="keywords"></a>关键字

#### <a name="keywords_poland_regon_number"></a>Keywords_poland_regon_number

- regon id
- 统计数字
- 统计 id
- 统计否
- regon 编号
- regonid#
- regonno#
- 公司 id
- companyid#
- companyidno#
- 器 statystyczny
- numeru regon
- numerstatystyczny#
- numeruregon#


## <a name="poland-tax-identification-number"></a>波兰纳税标识号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

11个不带空格或分隔符的数字
  
### <a name="pattern"></a>模式

11 个数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_poland_eu_tax_file_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_poland_eu_tax_file_number` 。 
    
  
```xml
      <!-- Poland Tax Identification Number -->
      <Entity id="1ff28b4d-40f2-49e9-b677-9606a88e2bca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

- nip#
- nip
- 器 identyfikacji podatkowej
- numeridentyfikacjipodatkowej#
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#
- vat id#
- vat id
- vat 编号
- vat 号码
- vatid#
- vatid
- vatno#
   

## <a name="portugal-citizen-card-number"></a>葡萄牙公民卡片号码

### <a name="format"></a>Format

八位数字

### <a name="pattern"></a>模式

八位数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_portugal_citizen_card"></a>Keyword_portugal_citizen_card

- bilhete de identidade
- cartão de cidadão
- 公民卡片
- 文档编号
- documento de identificação
- id 号
- 标识否
- identification number

- identity 卡片编号
- 标识卡号
- 国家/地区 id 卡片
- 网络
- número bi de
- número de identificação 民事
- número de identificação 会计
- número do documento
- 葡萄牙 bi 号码


## <a name="portugal-drivers-license-number"></a>葡萄牙驾驶执照号码
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

两个字母后跟指定模式中的七个数字
  
### <a name="pattern"></a>模式

两个字母后跟七个包含特殊字符的数字：
  
- 两个字母 (不区分大小写)  
- 连字符
- 6位数字
- 一个空格
- 一位
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_portugal_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_portugal_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver "s_license_number

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- carteira de motorista

## <a name="portugal-passport-number"></a>葡萄牙护照号码
此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

一个字母后跟六个数字，不含空格或分隔符
  
### <a name="pattern"></a>模式

一个字母后跟六个数字：
  
- 一个字母 (不区分大小写) 
- 6位数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_portugal_eu_passport_number` 找到与该模式匹配的内容。 
- 找到或中的关键字  `Keywords_eu_passport_number_common` `Keywords_portugal_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número do passaporte
- 葡萄牙护照
- 葡萄牙 passeport
- 葡萄牙 passaporte
- passaporte n º
- passeport n º
- números de passaporte
- 葡萄牙 passports
- número passaporte
- números passaporte

## <a name="portugal-tax-identification-number"></a>葡萄牙税号标识号

### <a name="format"></a>Format

9个带可选空格的数字
  
### <a name="pattern"></a>模式

- 3位数
- 一个可选空格
- 3位数
- 一个可选空格
- 3位数
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_portugal_eu_tax_file_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_portugal_eu_tax_file_number` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
- 函数  `Func_portugal_eu_tax_file_number` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_portugal_eu_tax_file_number"></a>Keywords_portugal_eu_tax_file_number

- cpf#
- cpf
- \n\n#
- \n\n
- número de identificação fisca
- numero 会计
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#


## <a name="romania-drivers-license-number"></a>罗马尼亚驾照号码
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

一个字符后跟八个数字
  
### <a name="pattern"></a>模式

一个字符后跟八个数字：
  
- 一个字母 (不区分大小写) 或数字 
- 八位数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_romania_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_romania_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver "s_license_number

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- permis de conducere

## <a name="romania-personal-numeric-code-cnp"></a>罗马尼亚个人数字代码 (CNP) 
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

13位数，不含空格和分隔符
  
### <a name="pattern"></a>模式

- 1-9 的1位数字
- 代表出生日期 (YYMMDD 的6个数字) 
- 2位数，可以为01-52 或99
- 4位数字

### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_romania_eu_national_id_card` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_romania_eu_national_id_card` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_romania_eu_national_id_card` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

- cnp#
- cnp
- 货到 identificare 个人
- 付款的个人数字
- 货到付款 unic identificare
- codnumericpersonal#
- codul 会计 nr。
- identificarea fiscală nr#
- id-ul taxei
- 保险号
- insurancenumber#
- 国家/地区 id#
- 
national id
- 国家/地区标识号
- număr identificare 个人
- număr identitate
- număr 个人 unic
- număridentitate#
- număridentitate
- numărpersonalunic#
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- 个人数字代码
- 针#
- 针
- 税文件编号
- 税文件编号
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#
- 唯一标识号
- 唯一标识号
- uniqueidentityno#
- uniqueidentityno

## <a name="romania-passport-number"></a>罗马尼亚护照号码
此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

八个或9个数字，不含空格和分隔符
  
### <a name="pattern"></a>模式

8或9个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_romania_eu_passport_number` 找到与该模式匹配的内容。 
- 找到或中的关键字  `Keywords_eu_passport_number_common` `Keywords_romania_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numărul pașaportului numarul pasaportului numerele pașaportului Pașaport nr

## <a name="russia-passport-number-domestic"></a>俄罗斯护照号码（国内）
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

10位数字

### <a name="pattern"></a>模式

10位数字：

- 两位数
- 可选空格或连字符
- 两位数
- 一个可选空格
- 6位数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_Russian_Passport_Number_Domestic 找到与该模式匹配的内容。
- 找到 Keyword_Russian_Passport_Number 中的关键字。

```xml
      <!-- Russian Passport Number Domestic -->
      <Entity id="76ec2f5d-cedb-48e1-8070-1998794af445" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_Domestic" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_russia_passport_number_domestic"></a>Keyword_russia_passport_number_domestic

- 护照号码
- 护照号
- 登记卡#
- 护照 id
- passportno#
- passportnumber#
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт#
- паспортid#
- номер паспорта
- номерпаспорта#


## <a name="russia-passport-number-international"></a>俄罗斯护照号码（国际）
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

九位数字

### <a name="pattern"></a>模式

9位数字：

- 两位数
- 可选空格或连字符
- 七位数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_Russian_Passport_Number_International 找到与该模式匹配的内容。
- 找到 Keyword_Russian_Passport_Number 中的关键字。

```xml
      <!-- Russian Passport Number International -->
      <Entity id="ac5f4878-75e4-4b82-af2d-02e13ea9f411" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_International" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_russia_passport_number_international"></a>Keywords_russia_passport_number_international

- 护照号码
- 护照号
- 登记卡#
- 护照 id
- passportno#
- passportnumber#
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт#
- паспортid#
- номер паспорта
- номерпаспорта#


## <a name="saudi-arabia-national-id"></a>沙特阿拉伯国家 ID

### <a name="format"></a>Format

10位数字

### <a name="pattern"></a>模式

10个连续数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_saudi_arabia_national_id"></a>Keyword_saudi_arabia_national_id

- Identification Card 
- I card number 
- ID number 
- الوطنية الهوية بطاقة رقم 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>新加坡国家注册标识卡片 (NRIC) 号码

### <a name="format"></a>Format

九个字母和数字

### <a name="pattern"></a>模式

- 九个字母和数字：
- 字母 "F"、"G"、"S" 或 "T" (不区分大小写)  
- 七位数字 
- 字母校验位

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_singapore_nric 找到与该模式匹配的内容。
- 找到 Keyword_singapore_nric 中的一个关键字。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字
   
#### <a name="keyword_singapore_nric"></a>Keyword_singapore_nric

- National Registration Identity Card 
- Identity Card Number 
- NRIC 
- IC 
- Foreign Identification Number 
- FIN 
- 身份证 
- 證 

## <a name="slovakia-drivers-license-number"></a>斯洛伐克驾照号码
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

一个字符后跟七个数字
  
### <a name="pattern"></a>模式

一个字符后跟七个数字
  
- 一个字母 (不区分大小写) 或数字
- 七位数字 
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_slovakia_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_slovakia_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver "s_license_number

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- vodičský preukaz

## <a name="slovakia-personal-number"></a>斯洛伐克个人号码
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

九或十个数字，包含可选反斜杠
  
### <a name="pattern"></a>模式

- 代表出生日期的6个数字
- 可选的斜杠 (/) 
- 3位数
- 1可选校验位
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_slovakia_eu_national_id_card` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_slovakia_eu_national_id_card` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
- 函数  `Func_slovakia_eu_national_id_card` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- 出生号码
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- id 号
- 标识否
- identification number

- identifikačná karta č
- identifikačné číslo
- identity 卡片编号
- 标识卡号
- národná identifikačná značka č
- 国家/地区号码
- nationalnumber#
- nemzeti személyazonosító igazolvány
- personalidnumber#
- rč
- rodne cislo
- rodné číslo
- social security number

- ssn#
- ssn
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- 税文件编号
- 税文件编号
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#

## <a name="slovakia-passport-number"></a>斯洛伐克护照号码
此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

一个数字或字母后跟七个数字，不含空格或分隔符
  
### <a name="pattern"></a>模式

一个数字或字母 (不区分大小写) 后跟七位数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_slovakia_eu_passport_number` 找到与该模式匹配的内容。 
- 找到或中的关键字  `Keywords_eu_passport_number_common` `Keywords_slovakia_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- číslo pasu
- čísla pasov
- pas č。
- Passeport n °
- n ° Passeport

## <a name="slovenia-drivers-license-number"></a>斯洛文尼亚驱动程序的许可证编号
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

9个数字，不带空格和分隔符
  
### <a name="pattern"></a>模式

九位数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_slovenia_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_slovenia_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver "s_license_number

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license 
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- vozniško dovoljenje

## <a name="slovenia-unique-master-citizen-number"></a>斯洛文尼亚唯一主公民号码
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

13位数，不含空格或分隔符
  
### <a name="pattern"></a>模式

指定模式中的13个数字：
  
- 与出生日期 (DDMMLLL) 的七位数，其中 "LLL" 对应于出生年份的后三个数字 
- 两个数字，对应于出生区域 "50"
- 三个数字，对应于出生在同一天的人的性别和序列号组合， (000-499 的男和500-999 的插孔) 
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_slovenia_eu_national_id_card` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_slovenia_eu_national_id_card` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_slovenia_eu_national_id_card` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

- edinstvena številka glavnega državljana
- emšo
- enotna maticna številka obcana
- id 卡片
- identification number

- identifikacijska številka
- identity 卡片
- nacionalna id
- nacionalni potni 列表
- 
national id
- osebna izkaznica
- osebni koda
- osebni ne
- osebni številka
- 个人代码
- 个人号码
- 个人数字代码
- številka državljana
- 唯一公民编号
- 唯一 id 号
- 唯一标识号
- 唯一的主公民号码
- 唯一注册号码
- uniqueidentityno#
- uniqueidentityno#

## <a name="slovenia-passport-number"></a>斯洛文尼亚护照号码
此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

两个字母后跟七个数字，不含空格或分隔符
  
### <a name="pattern"></a>模式

两个字母后跟七个数字：
  
- 字母 "P"
- 一个大写字母
- 七位数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_slovenia_eu_passport_number` 找到与该模式匹配的内容。 
- 找到或中的关键字  `Keywords_eu_passport_number_common` `Keywords_slovenia_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- številka potnega lista
- potek veljavnosti
- potni 列表#
- 基准 rojstva
- potni 列表
- številke potnih listov

## <a name="slovenia-tax-identification-number"></a>斯洛文尼亚税标识号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

8位数，不含空格或分隔符
  
### <a name="pattern"></a>模式

- 一个从1-9 的数字
- 6位数字
- 一个校验位
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_slovenia_eu_tax_file_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_slovenia_eu_tax_file_number` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
- 函数  `Func_slovenia_eu_tax_file_number` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

- davčna številka
- identifikacijska številka davka
- številka davčne datoteke
- 税文件编号
- 税文件编号
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#


## <a name="south-africa-identification-number"></a>南非身份证号码

### <a name="format"></a>Format

13 个数字（可能包含空格）

### <a name="pattern"></a>模式

13 个数字：
- 6位数，格式为 YYMMDD，表示出生日期 
- 四位数 
- 一位公民指示器 
- 数字 "8" 或 "9" 
- 一个数字，是校验和数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字
   
#### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- Identity card
- ID
- Id 
   
## <a name="south-korea-resident-registration-number"></a>韩国居民注册号码

### <a name="format"></a>Format

13 个数字（包含连字符）

### <a name="pattern"></a>模式

13 个数字：
- 6位数，格式为 YYMMDD，表示出生日期 
- 连字符 
- 由世纪和性别确定的一位数字 
- 四位数的出生区域代码 
- 一种用于区分上述号码相同的人员的数字 
- 校验位。

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_south_korea_resident_number 找到与该模式匹配的内容。
- 找到 Keyword_south_korea_resident_number 中的一个关键字。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字
   
#### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- National ID card 
- Citizen's Registration Number 
- Jumin deungnok beonho 
- RRN 
- 주민등록번호

## <a name="spain-drivers-license-number"></a>西班牙驾驶执照号码
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

8位数，后跟一个字符
  
### <a name="pattern"></a>模式

8位数，后跟一个字符：
  
- 八位数字 
- 一个数字或字母 (不区分大小写) 
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_spain_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_spain_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver "s_license_number

- dlno#
- 通讯#
- 驱动程序许可证。
- 驱动程序许可证
- driver license
- drivers licence
- drivers license
- driver's licence
- driver's license
- driving licence
- driving license
- 驱动程序许可证编号
- 驱动程序许可证编号
- 驱动程序许可证编号
- 驱动程序许可证编号
- 驾驶许可证编号
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- 促进允许
- 驾驶允许号码
- permiso de conducción
- permiso conducción
- número licencia conducir
- número de carnet de conducir
- número carnet conducir
- licencia conducir
- número de permiso de conducir
- número de permiso conducir
- número permiso conducir
- permiso conducir
- licencia de manejo
- el carnet de conducir
- carnet conducir

## <a name="spain-dni"></a>西班牙 DNI
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

8位数，后跟一个字符
  
### <a name="pattern"></a>模式

七位数字后跟一个字符
  
- 八位数字
- 可选空格或连字符
- 一个检查信函 (不区分大小写) 
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_spain_eu_DL_and_NI_number_citizen` 或 `Func_spain_eu_DL_and_NI_number_foreigner` 查找与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_spain_eu_national_id_card"` 。 

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_spain_eu_DL_and_NI_number_citizen` 或 `Func_spain_eu_DL_and_NI_number_foreigner` 查找与该模式匹配的内容。 

    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

- carné de identidad
- dni#
- dni
- dninúmero#
- documento nacional de identidad
- identidad único
- identidadúnico#
- 保险号
- 国家/地区标识号
- 国家标识
- nationalid#
- nationalidno#
- nie#
- nie
- nienúmero#
- número de identificación
- número nacional identidad
- 个人标识号
- 个人标识编号
- 唯一标识号
- uniqueid#

## <a name="spain-passport-number"></a>西班牙护照号码
此敏感信息类型实体仅适用于欧盟护照号敏感信息类型。

### <a name="format"></a>Format

八个或九个字符的字母和数字的组合，不带空格或分隔符
  
### <a name="pattern"></a>模式

字母和数字的八个或九个字符的组合：
  
- 两位数字或字母 
- 一个数字或字母 (可选) 
- 6位数字
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_spain_eu_passport_number` 找到与该模式匹配的内容。 
- 找到或中的关键字  `Keywords_eu_passport_number_common` `Keywords_spain_eu_passport_number` 。 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number_common" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- 登记卡#
- 登记卡#
- passportid
- passports
- passportno
- 护照号
- passportnumber
- 护照号码
- passportnumbers
- 护照号码

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- libreta pasaporte
- número pasaporte
- 西班牙 pasaporte
- números de pasaporte
- número de pasaporte
- números pasaporte
- pasaporte no
- Passeport n °
- n ° Passeport
- pasaporte。
- pasaporte n °
- 西班牙护照


## <a name="spain-social-security-number-ssn"></a> (SSN) 的西班牙社会安全号码
此敏感信息类型实体包含在欧盟社会保险号或等效 ID 敏感信息类型中，可用作独立的敏感信息类型实体。

### <a name="format"></a>Format

11-12 个数字

### <a name="pattern"></a>模式

11-12 位数：
- 两位数 
- 可选) 的正斜杠 ( 
- 七到八位数字 
- 可选) 的正斜杠 ( 
- 两位数

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_spanish_social_security_number 找到与该模式匹配的内容。
- 校验和通过。

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

无

## <a name="spain-tax-identification-number"></a>西班牙纳税标识号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

七个或8个数字以及指定模式中的一个或两个字母
  
### <a name="pattern"></a>模式

具有西班牙国家标识卡片的西班牙语自然人：
  
- 八位数字 
- 一个大写字母 (区分大小写)  
    
不包含西班牙国家的非居民 Spaniards 国家标识卡片
  
- 一个大写的字母 "L" (区分大小写) 
- 七位数字
- 一个大写字母 (区分大小写)  
    
在没有西班牙国内身份证的14年年龄下的居民 Spaniards：
  
- 一个大写的字母 "K" (区分大小写) 
- 七位数字 
- 一个大写字母 (区分大小写) 
    
带有 Foreigner 标识号的 Foreigners
  
- 一个大写的字母，为 "X"、"Y" 或 "Z" (区分大小写)  
- 七位数字
- 一个大写字母 (区分大小写)  
    
没有 Foreigner 标识号的 Foreigners
  
- 一个大写字母为 "M" (区分大小写)  
- 七位数字
- 一个大写字母 (区分大小写)  
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_spain_eu_tax_file_number` 或 `Func_spain_eu_DL_and_NI_number_citizen` 查找与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_spain_eu_tax_file_number` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_spain_eu_tax_file_number` 或 `Func_spain_eu_DL_and_NI_number_citizen` 查找与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

- cif
- cifid#
- cifnúmero#
- número de contribuyente
- número de identificación 会计
- número de impuesto corporativo
- spanishcifid#
- spanishcifid
- spanishcifno#
- spanishcifno
- 税文件编号
- 税文件编号
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#


## <a name="sql-server-connection-string"></a>SQL Server 连接字符串

### <a name="format"></a>Format

字符串 "User Id"、"User ID"、"uid" 或 "UserId"，后跟下面模式中所述的字符和字符串。

### <a name="pattern"></a>模式

- 字符串 "User Id"、"User ID"、"uid" 或 "UserId"
- 介于1-200 个字母、数字、符号、特殊字符或空格之间的任意组合
- 字符串 "Password" 或 "pwd"，其中 "pwd" 不以小写字母开头
- 等号 (=) 
- 不是美元符号 ($) 的任何字符、百分比符号 (% ) 、大于符号 ( # A0) 、符号 ( @ ) 、引号 ( ") 、分号 (、) 、左大括号 ( [) 或左括号 ( {) 
- 7-128 个不是分号的字符的任意组合 (; ) 、正斜杠 (/) 或引号 ( ") 
- 分号 (; ) 或引号 ( ") 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 正则表达式 CEP_Regex_SQLServerConnectionString 找到与该模式匹配的内容。
- 找 **不** 到 CEP_GlobalFilter 中的关键字。
- 正则表达式 **CEP_PasswordPlaceHolder 不会找到与** 该模式匹配的内容。
- 正则表达式 **CEP_CommonExampleKeywords 不会找到与** 该模式匹配的内容。

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

### <a name="keywords"></a>关键字

#### <a name="cep_globalfilter"></a>CEP_GlobalFilter

- 部分密码
- somepassword
- secretPassword
- 采用

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

 (请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。 ) 

- 密码或密码后跟0-2 个空格、一个等号 (=) 、0-2 空格和一个星号 ( * ) --或--------------
- 密码或密码后跟：
    - 等号 (=) 
    - 小于符号 ( # A0) 
    - 1-200 个字符的任意组合，这些字符为大写或小写字母、数字、星号 ( * ) 、连字符 ( ) 、下划线 (_) 或空白字符
    - 大于符号 ( # A0) 

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

 (请注意，从技术上讲，此敏感信息类型通过使用正则表达式（而不是关键字列表）来标识这些关键字。 ) 

- 尚未
- 送交
- 罗斯
- 沙盒
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int。<!--no-hyperlink-->netmeeting

## <a name="sweden-drivers-license-number"></a>瑞典驾驶执照号码
此敏感信息类型实体仅适用于欧盟驾驶执照号码的敏感信息类型。

### <a name="format"></a>Format

10个数字，包含连字符
  
### <a name="pattern"></a>模式

10位数，包含连字符：
  
- 6位数字 
- 连字符
- 四位数
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式  `Regex_sweden_eu_driver's_license_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_sweden_eu_driver's_license_number` 。 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a>关键字

**Keywords_sweden_eu_driver "s_license_number**

- 通讯#
- driver license
- 驱动程序许可证编号
- 驱动程序许可证
- 驱动程序许可证。
- drivers license
- drivers licence
- driver's license
- 驾驶执照号码
- 驾驶许可证编号
- 驾驶执照号码
- dlno#
- körkort

## <a name="sweden-national-id"></a>瑞典国家 ID

### <a name="format"></a>Format

10或12个数字和一个可选分隔符

### <a name="pattern"></a>模式

10或12个数字和一个可选分隔符：
- 两个数字 (可选)  
- 采用日期格式 YYMMDD 的六位数字 
- "-" 或 "+" 的分隔符 (可选) 
- 四位数

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 `Func_swedish_national_identifier` 找到与该模式匹配的内容。
- 找到了 from 关键字 `Keywords_swedish_national_identifier`
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 `Func_swedish_national_identifier` 找到与该模式匹配的内容。
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

### <a name="keywords"></a>关键字

#### <a name="keywords_swedish_national_identifier"></a>Keywords_swedish_national_identifier

- id 号
- id 号
- 号#
- 标识否
- identification number

- identifikationsnumret#
- identifikationsnumret
- identitetshandling
- 标识文档
- identity no
- 标识号码
- id-nummer
- 个人 id
- personnummer#
- personnummer
- skatteidentifikationsnummer
   
## <a name="sweden-passport-number"></a>瑞典护照号码
此敏感信息类型实体包含在欧盟护照号敏感信息类型中，可用作独立的敏感信息类型实体。

### <a name="format"></a>Format

八位数字

### <a name="pattern"></a>模式

八个连续数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_sweden_passport_number 找到与该模式匹配的内容。
- 满足以下条件之一：
    - 找到 Keyword_passport 中的关键字。
    - 找到 Keyword_sweden_passport 中的关键字。

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字
   
#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- visa requirements 
- Alien Registration Card 
- Schengen visas 
- Schengen visa 
- Visa Processing 
- Visa Type 
- Single Entry 
- Multiple Entry 
- G3 Processing Fees 

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number 
- Passport No 
- Passport # 
- 登记卡# 
- PassportID 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート＃ 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport # 
- Passeport# 
- PasseportNon 
- Passeportn ° 

## <a name="sweden-social-security-number-or-equivalent-identification"></a>瑞典社会保险号或等效标识
此敏感信息类型实体仅适用于欧盟社会保险号码或等效 ID 敏感信息类型。

### <a name="format"></a>Format

12个数字，不含空格和分隔符
  
### <a name="pattern"></a>模式

12 个数字：
  
- 对应于出生日期 (YYYYMMDD) 的8位数字 
- 与序列号对应的三个数字，其中： 
  - 序列号中的最后一个数字指示在为 "男" 分配一个奇数号码时的性别，以及一个 "女" 的偶数号码。
  - 最多1990，将序列号 corresponded 分配给那些号码的持有者出生或 (的县。如果在 1947) 之前出生，则根据纳税记录在年1月1日的) 使用特殊代码 (通常为9的 immigrants 的1947第七位数字 
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_sweden_eu_ssn_or_equivalent` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_sweden_eu_ssn_or_equivalent` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_sweden_eu_ssn_or_equivalent` 找到与该模式匹配的内容。 
    
```xml
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

- 个人 id 号
- identification number
- 个人 id 否
- identity no
- 标识否
- 个人标识编号
- personnummer id
- personligt id-nummer
- unikt id-nummer
- personnummer
- identifikationsnumret
- personnummer#
- identifikationsnumret#

## <a name="sweden-tax-identification-number"></a>瑞典纳税标识号
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

10个数字和指定模式中的符号
  
### <a name="pattern"></a>模式

10个数字和一个符号：
  
- 与出生日期 (YYMMDD) 的6个数字 
- 正号或减号
- 在以下位置使标识号唯一的三个数字： 
  - 对于在1990之前发出的号码，第七和第八位数字标识出生的县或外部人
  - 第九个位置中的数字表示为奇数或甚至是女的性别
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数  `Func_sweden_eu_tax_file_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_sweden_eu_tax_file_number` 。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_sweden_eu_tax_file_number` 找到与该模式匹配的内容。 
    
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

### <a name="keywords"></a>关键字

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

- 个人 id 号
- personnummer
- skatt id nummer
- skatt identifikation
- skattebetalarens identifikationsnummer
- 瑞典纳税人标识号
- 税文件
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税号
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#


## <a name="swift-code"></a>SWIFT 代码

### <a name="format"></a>Format

四个字母后跟5-31 个字母或数字

### <a name="pattern"></a>模式

四个字母后跟5-31 个字母或数字：
- 四个字母的银行代码 (不区分大小写)  
- 一个可选空格 
- 4-28 个字母或数字（基本银行账号 (BBAN)） 
- 一个可选空格 
- BBAN 的余数 (1 到3个字母或数字) 

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字
   
#### <a name="keyword_swift"></a>Keyword_swift

- international organization for standardization 9362 
- iso 9362 
- iso9362 
- 反应\# 
- swiftcode 
- swiftnumber 
- swiftroutingnumber 
- swift code 
- swift number # 
- swift routing number 
- bic number 
- bic code 
- numéro \# 
- numéro\# 
- bank identifier code 
- 標準化9362 
- 迅速＃ 
- SWIFTコード 
- SWIFT番号 
- 迅速なルーティング番号 
- BIC番号 
- BICコード 
- 銀行識別コードのための国際組織 
- Organisation internationale de normalisation 9362 
- rapide \# 
- code SWIFT 
- le numéro de swift 
- swift numéro d'acheminement 
- le numéro BIC 
- \# NUMÉRO 
- code identificateur de banque 


## <a name="switzerland-ssn-ahv-number"></a>瑞士 SSN AHV 号码
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

13位数字

### <a name="pattern"></a>模式

13位数字：

- 三位数-756
- 一个可选的点
- 四位数
- 一个可选的点
- 四位数
- 一个可选的点
- 两位数

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_swiss_social_security_number_ahv 找到与该模式匹配的内容。
- 找到 Keywords_swiss_social_security_number_ahv 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_swiss_social_security_number_ahv 找到与该模式匹配的内容。

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

### <a name="keywords"></a>关键字

#### <a name="keyword_swiss_ssn_ahv_number"></a>Keyword_swiss_ssn_AHV_number

- ahv
- ssn
- pid
- 保险号
- personalidno#
- social security number

- 个人 id 号
- 个人识别码。
- insuranceno#
- uniqueidno#
- 唯一标识 "否"。
- avs 号码
- 个人标识无 versicherungsnummer
- identifikationsnummer
- einzigartige identität nicht
- sozialversicherungsnummer
- 标识 personnelle id
- 
numéro de sécurité sociale

   
## <a name="taiwan-national-identification-number"></a>台湾国家标识号码

### <a name="format"></a>Format

一个英文)  (，后跟9个数字

### <a name="pattern"></a>模式

一个英文字母 (，后跟9个数字) ：
- 一个英文字母 (，不区分大小写)  
- 数字 "1" 或 "2" 
- 八位数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_taiwanese_national_id 找到与该模式匹配的内容。
- 找到 Keyword_taiwanese_national_id 中的一个关键字。
- 校验和通过。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_taiwan_national_id"></a>Keyword_taiwan_national_id

- 身份證字號 
- 證 
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

### <a name="format"></a>Format

- 生物识别护照号码：9个数字
- 不带生物的护照号码：9个数字

### <a name="pattern"></a>模式
生物识别护照号码：
- 字符 "3" 
- 八位数字

不带生物的护照号码：
- 九位数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_taiwan_passport"></a>Keyword_taiwan_passport

- ROC passport number 
- Passport number 
- Passport no 
- Passport Num 
- Passport # 
- 护照 
- 中華民國護照 
- Zhōnghuá Mínguó hùzhào
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>台湾居民证书 (ARC/TARC) 号码

### <a name="format"></a>Format

10个字母和数字

### <a name="pattern"></a>模式

10个字母和数字：
- 两个字母 (不区分大小写)  
- 八位数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

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

## <a name="thai-population-identification-code"></a>泰语填充标识代码

### <a name="format"></a>Format

13 位数字

### <a name="pattern"></a>模式

13 个数字：
- 第一个数字不是零或九 
- 12 个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_Thai_Citizen_Id 找到与该模式匹配的内容。
- 找到 Keyword_Thai_Citizen_Id 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_Thai_Citizen_Id 找到与该模式匹配的内容。

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

### <a name="keywords"></a>关键字

#### <a name="keyword_thai_citizen_id"></a>Keyword_thai_citizen_Id

- ID Number
- 标识号码
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน
  
## <a name="turkish-national-identification-number"></a>土耳其国家标识号码

### <a name="format"></a>Format

11 个数字

### <a name="pattern"></a>模式

11 个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_Turkish_National_Id 找到与该模式匹配的内容。
- 找到 Keyword_Turkish_National_Id 中的关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_Turkish_National_Id 找到与该模式匹配的内容。

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

### <a name="keywords"></a>关键字

#### <a name="keyword_turkish_national_id"></a>Keyword_turkish_national_id

- TC Kimlik No
- TC Kimlik numarası
- Vatandaşlık numarası
- Vatandaşlık no

## <a name="uk-drivers-license-number"></a>U.K. 驾驶执照号码
此敏感信息类型实体包含在欧盟驱动程序的 "敏感信息类型" 中，并可用作独立的敏感信息类型实体。

### <a name="format"></a>Format

特定格式的 18 个字母和数字组合

### <a name="pattern"></a>模式

18 个字母和数字：
- 5个字母 (不区分大小写) 或数字 "9" 代替字母 
- 一位 
- 日期格式 MMDDY 中的五个数字。出生日期 (第七个字符将增加50如果驱动程序是女，即51到62而不是01到 12) 
- 两个字母 (不区分大小写) 或数字 "9" 代替一个字母 
- 五个数字

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_uk_drivers_license 找到与该模式匹配的内容。
- 找到 Keyword_uk_drivers_license 中的一个关键字。
- 校验和通过。

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_uk_drivers_license"></a>Keyword_uk_drivers_license

- DVLA 
- light vans 
- quadbikes 
- motor cars 
- 125cc 
- sidecar 
- tricycles 
- motorcycles 
- photocard licence 
- learner drivers 
- licence holder 
- licence holders 
- driving licences 
- driving licence 
- dual control car 
   
## <a name="uk-electoral-roll-number"></a>U.K. electoral 卷号

### <a name="format"></a>Format

两个字母后跟1-4 位数字

### <a name="pattern"></a>模式

两个字母 (不区分大小写) 后接1-4 个号码

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- council nomination 
- nomination form 
- electoral register 
- electoral roll

   
## <a name="uk-national-health-service-number"></a>U.K. 国家/地区运行状况服务号码

### <a name="format"></a>Format

10-17 个数字，通过空格分隔 

### <a name="pattern"></a>模式

10-17 位数字：
- 3个或10个数字 
- 一个空格 
- 三个数字 
- 一个空格 
- 四位数

### <a name="checksum"></a>校验和

是

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字
   
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
- D. B。 
- Date of Birth 
- Birth Date 
   
## <a name="uk-national-insurance-number-nino"></a>U.K. 国内保险号 (NINO) 
此敏感信息类型实体包含在欧盟国家/地区 Identificaiton 号敏感信息类型中，可用作独立的敏感信息类型实体。

### <a name="format"></a>Format

由空格或短划线分隔的七个字符或九个字符

### <a name="pattern"></a>模式

两种可能的模式：

-  (有效 NINOs 的两个字母仅使用此前缀中的特定字符，此格式将对此进行验证;不区分大小写) 
- 6位数字
- "A"、"B"、"C" 或 "d" (类似于前缀，后缀中只允许有某些字符;不区分大小写) 

OR

- 两个字母
- 空格或短划线
- 两位数
- 空格或短划线
- 两位数
- 空格或短划线
- 两位数
- 空格或短划线
- 要么是 "A"、"B"、"C"，要么 ' d '

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_uk_nino 找到与该模式匹配的内容。
- 找到 Keyword_uk_nino 中的一个关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_uk_nino 找到与该模式匹配的内容。
- 未找到 Keyword_uk_nino 中的关键字。

```xml
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- national insurance number

- national insurance contributions

- protection act
- 方面
- social security number

- insurance application

- medical application

- social insurance

- medical attention

- 社会保障
- great britain

- NI 号码
- NI 否。
- NI#
- NI#
- 方面#
- insurancenumber
- nationalinsurance#
- nationalinsurancenumber

    
## <a name="uk-unique-taxpayer-reference-number"></a>U.K. 唯一的纳税人参考号码
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

10个数字，不含空格和分隔符
 
  
### <a name="pattern"></a>模式

10 个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数  `Func_uk_eu_tax_file_number` 找到与该模式匹配的内容。 
- 找到了中的关键字  `Keywords_uk_eu_tax_file_number` 。 
    
```xml
      <!-- U.K. Unique Taxpayer Reference Number -->
      <Entity id="ad4a8116-0db8-439a-b545-6d967642f0ec" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

- 税号
- 税文件
- tax id

- 税号标识编号
- 税标识号
- 免税#
- 免税
- 税务登记编号
- taxid#
- taxidno#
- taxidnumber#
- taxno#
- taxnumber#
- taxnumber
- 纳税人 id
- tin 编号
- 锡#

## <a name="us-bank-account-number"></a>美国银行帐户编号

### <a name="format"></a>Format

8-17 个数字

### <a name="pattern"></a>模式

8-17 个连续的数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

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

## <a name="us-drivers-license-number"></a>美国驾驶执照号码

### <a name="format"></a>Format

取决于州

### <a name="pattern"></a>模式

取决于状态-例如，纽约：
- 与 ddd ddd ddd 相匹配的9个数字的格式将会匹配。
- 9个数字（如 ddddddddd）将不匹配。

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_new_york_drivers_license_number 找到与该模式匹配的内容。
- 找到 Keyword_[state_name]_drivers_license_name 中的一个关键字。
- 找到 Keyword_us_drivers_license 中的一个关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
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

### <a name="keywords"></a>关键字

#### <a name="keyword_us_drivers_license_abbreviations"></a>Keyword_us_drivers_license_abbreviations

- 通讯 
- DLS 
- 采用 
- CDLS 
- ID 
- Id 
- 通讯# 
- DLS# 
- 采用# 
- CDLS# 
- 号#
- Id# 
- ID number 
- ID numbers 
- .LIC 
- .LIC# 

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


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_ [state_name] _drivers_license_name

- 状态缩写 (例如，"NY" )  
- 状态名称 (例如，"纽约" ) 

## <a name="us-individual-taxpayer-identification-number-itin"></a>美国单个纳税人标识号 (ITIN) 

### <a name="format"></a>Format

九个数字，以 "9" 开头，并包含 "7" 或 "8" 作为第四个数字，可以选择使用空格或短划线进行格式设置

### <a name="pattern"></a>模式

格式
- 数字 "9" 
- 两位数 
- 空格或短划线 
- "7" 或 "8" 
- 一个数字 
- 空格或短划线 
- 四位数

纯
- 数字 "9" 
- 两位数 
- "7" 或 "8" 
- 五个数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_formatted_itin 找到与该模式匹配的内容。
- 下列至少其中一项为真：
    - 找到 Keyword_itin 中的一个关键字。
    - 函数 Func_us_address 找到正确日期格式的地址。
    - 函数 Func_us_date 找到正确日期格式的日期。
    - 找到 Keyword_itin_collaborative 中的一个关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_unformatted_itin 找到与该模式匹配的内容。
- 下列至少其中一项为真：
    - 找到 Keyword_itin_collaborative 中的一个关键字。
    - 函数 Func_us_address 找到正确日期格式的地址。
    - 函数 Func_us_date 找到正确日期格式的日期。

```xml
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_itin"></a>Keyword_itin

- 报税 
- tax id 
- tax identification 
- itin 
- ssn 
- 锡 
- social security 
- tax payer 
- itins 
- taxid 
- individual taxpayer 

#### <a name="keyword_itin_collaborative"></a>Keyword_itin_collaborative

- 许可证 
- 通讯 
- DOB 
- 出生日期 
- Birthday 
- Date of Birth 

## <a name="us-social-security-number-ssn"></a> (SSN) 的美国社会安全号码

### <a name="format"></a>Format

9个数字，可以是格式化或无格式的模式

> [!NOTE]
> 如果在 2011 年中旬前发布，则 SSN 具有强格式，即数字的某部分必须介于某个有效的范围中（但是没有校验和）。

### <a name="pattern"></a>模式

四个函数在四种不同的模式中查找 Ssn：
- Func_ssn 查找具有 2011 年以前使用短划线或空格格式化的强格式的 SSN（ddd-dd-dddd 或 ddd dd dddd）
- Func_unformatted_ssn 查找具有 2011 年以前未格式化为 9 个连续数字的强格式的 SSN (ddddddddd)
- Func_randomized_formatted_ssn 查找 2011 年后使用短划线或空格（ddd-dd-dddd 或 ddd dd dddd）格式化的 SSN
- Func_randomized_unformatted_ssn 查找 2011 年后未格式化为 9 个连续数字 (ddddddddd) 的 SSN

### <a name="checksum"></a>校验和

否


### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
- 函数 Func_ssn 找到与该模式匹配的内容。
- 找到 Keyword_ssn 中的一个关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_unformatted_ssn 查找与该模式匹配的内容。
- 找到 Keyword_ssn 中的一个关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
- 函数 Func_randomized_formatted_ssn 找到与该模式匹配的内容。
- 找到 Keyword_ssn 中的一个关键字。

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 55% 确信它检测到这种类型的敏感信息：
- 函数 Func_randomized_unformatted_ssn 找到与该模式匹配的内容。
- 找到 Keyword_ssn 中的一个关键字。


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

### <a name="keywords"></a>关键字

#### <a name="keyword_ssn"></a>Keyword_ssn

- SSA 编号
- social security number
- 社会保障#
- 社会保障#
- 社会保障号
- Social Security#
- Soc Sec
- SSN
- SSN
- SSN#
- SS#
- SSID
   
## <a name="us--uk-passport-number"></a>美国/英国 passport number
英国 护照号敏感信息类型实体在欧盟护照号敏感信息类型中可用，并可用作独立的敏感信息类型实体。

### <a name="format"></a>Format

九位数字

### <a name="pattern"></a>模式

九个连续数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 函数 Func_usa_uk_passport 找到与该模式匹配的内容。
- 找到 Keyword_passport 中的一个关键字。

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number 
- Passport No 
- Passport # 
- 登记卡# 
- PassportID 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート＃ 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport # 
- Passeport# 
- PasseportNon 
- Passeportn ° 

## <a name="ukraine-passport-domestic"></a>乌克兰护照国内
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

九位数字

### <a name="pattern"></a>模式

九位数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_Ukraine_Passport_Domestic 找到与该模式匹配的内容。
- 找到 Keyword_Ukraine_Passport_Domestic 中的关键字。

```xml
      <!-- Ukraine Passport Domestic -->
      <Entity id="1817a540-221f-4459-9202-3bd78b81d803" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_Ukraine_Passport_Domestic"/>
          <Match idRef="Keyword_Ukraine_Passport_Domestic"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_ukraine_passport_domestic"></a>Keyword_ukraine_passport_domestic

- 乌克兰护照
- 护照号码
- 护照号
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>乌克兰护照（国际）
此敏感信息类型仅可用于以下内容：
- 数据丢失防护策略
- 通信合规性策略
- 信息治理
- 记录管理
- Microsoft 云应用安全

### <a name="format"></a>Format

八个字符的字母数字模式

### <a name="pattern"></a>模式

八个字符的字母数字模式：
- 两个字母或数字
- 6位数字

### <a name="checksum"></a>校验和

否

### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
- 正则表达式 Regex_Ukraine_Passport_International 找到与该模式匹配的内容。
- 找到 Keyword_Ukraine_Passport_International 中的关键字。

```xml
      <!-- Ukraine Passport International -->
      <Entity id="cfbe032d-22e0-4f28-ab68-d66e9641f1e2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Ukraine_Passport_International"/>
          <Match idRef="Keyword_Ukraine_Passport_International"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keyword_ukraine_passport_international"></a>Keyword_ukraine_passport_international

- 乌克兰护照
- 护照号码
- 护照号
- паспорт України
- номер паспорта
