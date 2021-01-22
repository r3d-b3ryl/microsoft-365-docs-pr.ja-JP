---
title: 機密情報の種類の詳細
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: ''
ms.openlocfilehash: 896a529d67faddb45b2672ca077f5a8e3b19827e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933083"
---
# <a name="learn-about-sensitive-information-types"></a>機密情報の種類の詳細

組織の管理下にある機密性の高いアイテムの特定と分類は、情報保護の分野の最初 [のステップです](protect-information.md)。  Microsoft 365 には、分類可能なアイテムを識別する 3 つの方法があります。

- ユーザーが手動で行う
- 機密情報の種類などの自動パターン認識
- [機械学習](classifier-learn-about.md)

機密情報の種類はパターン ベースの分類子です。 機密情報を識別するために、社会保障、クレジット カード、銀行口座番号などの機密情報を検出する場合は、「機密情報の種類」エンティティ定義 [を参照してください。](sensitive-information-type-entity-definitions.md)

## <a name="sensitive-information-types-are-used-in"></a>機密情報の種類は次の中で使用されます。

- [データ損失防止ポリシー](data-loss-prevention-policies.md) 
- [機密ラベル](sensitivity-labels.md)
- [保持ラベル](retention.md)
- [通信コンプライアンス](communication-compliance.md)
- [自動ラベル付けポリシー](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a>機密情報の種類の基本的な部分

機密情報の種類のエンティティは、次のフィールドで定義されます。

- name: 機密情報の種類の参照方法
- description: 機密情報の種類が何を探しているのかを説明します
- パターン: パターンは、機密情報の種類が検出する情報を定義します。 次のコンポーネントで構成されます。
    - プライマリ要素 – 機密情報の種類が検索している主な要素。 正規表現 **には、チェックサム** 検証、キーワード リスト、キーワード ディクショナリ、または関数を使用 **できます**。
    - サポート要素 – マッチの信頼度を高めるのに役立つサポート 証拠として機能する要素。 たとえば、SSN 番号の近くにあるキーワード "SSN" です。 これは、チェックサム検証、キーワード リスト、キーワード ディクショナリを使用する場合と使用しない場合の正規表現です。
    - 信頼度 - 信頼度 (高、中、低) は、プライマリ要素と共に検出されたサポート証拠の量を反映します。 アイテムに含まれる証拠が多いほど、一致するアイテムに探している機密情報が含まれているという信頼度が高くなります。
    - 近接性 – プライマリ要素とサポート要素の間の文字数

![補強証拠と近接ウィンドウの図](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

信頼度の詳細については、このビデオを参照してください。


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a>機密情報の種類の例


## <a name="argentina-national-identity-dni-number"></a>アルゼンチンの国民識別番号 (DNI)

### <a name="format"></a>フォーマット

ピリオドで区切られた 8 桁の数字

### <a name="pattern"></a>パターン

8 桁の数字:
- 2 桁の数字
- ピリオド
- 3 桁の数字
- ピリオド
- 3 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、約 300 文字以下の場合にこの種の機密情報が検出されたという中程度の信頼度を持っています。
- パターンに一Regex_argentina_national_idコンテンツを検索する正規表現。
- 検索されたKeyword_argentina_national_id検索されます。

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>キーワード

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina National Identity number 
- ID 
- Id の国民識別カード 
- DNI 
- NIC National Registry of Persons 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 

### <a name="more-on-confidence-levels"></a>信頼度の詳細

機密情報の種類のエンティティ定義では、信頼度は、プライマリ要素に加えて検出されるサポート証拠の量を反映します。 アイテムに含まれる証拠が多いほど、一致するアイテムに探している機密情報が含まれているという信頼度が高くなります。 たとえば、信頼度の高い一致では、主要素の近くに多くのサポート証拠が含まれるのに対し、信頼度の低い一致には近接する証拠はほとんど含めず、何も含めずに最も近い証拠が含まれる場合があります。 

信頼度が高い場合は、最も少ない誤検知が返されますが、誤検知の数が多い場合があります。 低または中程度の信頼度は、より多くの誤検知を返しますが、検出検出は少なからゼロです。

- **低信頼** 度 : 値 65、一致したアイテムに含まれる検出検出は最も少なく、誤検知は最も少ない。  
- **中程度の** 信頼度 : 値 75、一致したアイテムには、平均的な誤検知と検出検出の量が含まれます。  
- **高信頼** 度 : 値 85、一致したアイテムには、最も少ない誤検知が含まれますが、最も検出検出が多い。  

高信頼度パターンは、低カウント (5 ~ 10) と高いカウント (20 以上) の低信頼度パターンを使用する必要があります。

## <a name="creating-custom-sensitive-information-types"></a>カスタムの機密情報の種類を作成する

次のオプションを使用して、セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成できます。

- **UI を使用する** セキュリティ/コンプライアンス センターの UI を使用して、カスタムの機密情報の種類を設定します。 この方法では、正規表現、キーワード、キーワード辞書を使用することができます。 詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」を参照してください。

- **EDM を使用する** データ一致 (EDM) に基づく分類によって、カスタム機密情報の種類を設定します。 この方法では、定期的に更新できる安全なデータベースを使用して、動的な機密情報の種類を作成することができます。 詳細については、「[Exact Data Match に基づく分類で、カスタムの機密情報の種類を作成する](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)」を参照してください。

- **PowerShell を使用する** PowerShell を使用して、カスタムの機密情報の種類を設定します。 この方法は、UI を使用する場合よりも複雑ですが、より多くの構成オプションがあります。 詳細については、「[セキュリティ/コンプライアンス センターの PowerShell でカスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)」を参照してください。



> [!NOTE]
> Microsoft 365 の情報保護は、次のような場合に2バイト文字セットの言語をpreviewでサポートしています。
> - 中国語 (簡体字)
> - 中国語 (繁体字)
> - 韓国語
> - 日本語

>このサポートは、機密情報の種類で使用できます。 詳細については、「[2バイト文字セットのリリースノート (preview) についての情報保護サポート](mip-dbcs-relnotes.md)」を参照してください。

## <a name="for-further-information"></a>詳しくは、以下をご覧ください。
- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
- [カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)
- [PowerShell でカスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->