---
title: 機密情報の種類に関する詳細情報
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
ms.openlocfilehash: 90b545f60c68ac6b76509e14daf1258df66e1c63
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741534"
---
# <a name="learn-about-sensitive-information-types"></a>機密情報の種類に関する詳細情報

組織の管理下にある機密性の高いアイテムを識別および分類する方法は、情報保護の分野の最初の [ステップです](protect-information.md)。  Microsoft 365 には、分類できるアイテムを識別する 3 つの方法があります。

- ユーザーが手動で行う
- 機密情報の種類などの自動パターン認識
- [機械学習](classifier-learn-about.md)

機密情報の種類は、パターン ベースの分類子です。 機密アイテムを識別するために、社会保障、クレジット カード、銀行口座番号などの機密情報を検出する場合は、「機密情報の種類エンティティ定義」 [を参照してください。](sensitive-information-type-entity-definitions.md)

## <a name="sensitive-information-types-are-used-in"></a>機密情報の種類は、

- [データ損失防止ポリシー](data-loss-prevention-policies.md) 
- [機密ラベル](sensitivity-labels.md)
- [保持ラベル](retention.md)
- [通信コンプライアンス](communication-compliance.md)
- [自動ラベル付けポリシー](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a>機密情報の種類の基本的な部分

すべての機密情報の種類エンティティは、次のフィールドで定義されます。

- name: 機密情報の種類の参照方法
- description: 機密情報の種類が何を探しているのかを説明します。
- pattern: パターンは、機密情報の種類が検出する情報を定義します。 このコンポーネントは、次のコンポーネントで構成されます。
    - Primary 要素 – 機密情報の種類が探している主な要素。 これは、チェックサム検証 **、** キーワード リスト、キーワード 辞書、または関数を含む正規表現と指定 **できます**。
    - サポート要素 – 一致の信頼度を高めるのに役立つ証拠として機能する要素。 たとえば、SSN 番号の近接にあるキーワード "SSN" です。 これは、チェックサム検証、キーワード リスト、キーワード 辞書の付いた正規表現と指定できます。
    - 信頼度レベル - 信頼度レベル (高、中、低) は、主要素と共に検出された証拠の量を反映します。 アイテムに含まれる証拠が多いほど、一致するアイテムに探している機密情報が含まれているという信頼性が高くなります。
    - 近接 – プライマリ要素とサポート要素の間の文字数

![補強証拠と近接ウィンドウの図](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

このビデオの信頼度の詳細


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a>機密情報の種類の例


## <a name="argentina-national-identity-dni-number"></a>アルゼンチンの国民 ID (DNI) 番号

### <a name="format"></a>フォーマット

ピリオドで区切られた 8 桁の数字

### <a name="pattern"></a>パターン

8 桁の数字:
- 2 桁
- ピリオド
- 3 桁の数字
- ピリオド
- 3 桁の数字

### <a name="checksum"></a>チェックサム

いいえ

### <a name="definition"></a>定義

DLP ポリシーは、次の 300 文字に近い場合に、この種類の機密情報が検出されたという中程度の信頼性を持っています。
- 正規表現は、Regex_argentina_national_id一致するコンテンツを検索します。
- このページのKeyword_argentina_national_idが見つかりました。

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
- ID 国の ID カード 
- DNI 
- NIC の国民登録 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 

### <a name="more-on-confidence-levels"></a>信頼度の詳細

機密情報の種類のエンティティ定義では、信頼度 **は** 、主要素に加えて検出される証拠の量を反映します。 アイテムに含まれる証拠が多いほど、一致するアイテムに探している機密情報が含まれているという信頼性が高くなります。 たとえば、信頼度が高い一致には、主要要素の近接性に関するより多くの証拠が含まれるのに対し、信頼度が低い一致には、近接する証拠はほとんど含めず、サポート証拠もほとんど含めずになります。 

高信頼度は、最も少ない誤検知を返しますが、より多くの誤検知が発生する可能性があります。 低または中程度の信頼度は、より多くの誤検知を返しますが、偽陰性を返す値は少なから 0 です。

- **低信頼** 度 : 値が 65 の場合、一致するアイテムには最も少ない偽陰性が含まれますが、最も誤検知が発生します。 低信頼度は、すべての低、中、および高信頼度の一致を返します。
- **中程度の** 信頼度 : 値が 75 の場合、一致するアイテムには平均的な量の誤検知と偽陰性が含まれます。 中程度の信頼度は、すべての中程度と高信頼度の一致を返します。  
- **高信頼**: 値が 85 の場合、一致するアイテムには、最も少ない誤検知が含まれますが、最も誤った負の値が含まれます。 高信頼は、高信頼度の一致のみを返します。  

高信頼度レベルのパターンは、5 ~ 10 と低い信頼度パターンと、20 以上の高信頼度パターンを使用する必要があります。

> [!NOTE]
> 数値ベースの信頼レベル (精度も知っている) を使用して定義されている既存のポリシーまたはカスタム機密情報の種類 (SIT) がある場合は、3 つの個別の信頼レベルに自動的にマップされます。セキュリティ @ コンプライアンス センター UI 全体で、低信頼性、中程度の信頼、および高い信頼性。
> - 76 ~ 100 の信頼レベルを持つ最小精度またはカスタムの SIT パターンを持つすべてのポリシーは、高信頼度にマップされます。 
> - 66 ~ 75 の信頼レベルを持つ最小精度またはカスタムの SIT パターンを持つすべてのポリシーは、中程度の信頼度にマップされます。
> - 信頼度レベルが 65 以下の最小精度またはカスタムの SIT パターンを持つすべてのポリシーは、低信頼度にマップされます。 
## <a name="creating-custom-sensitive-information-types"></a>カスタムの機密情報の種類を作成する

次のオプションを使用して、セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成できます。

- **UI を使用する** セキュリティ/コンプライアンス センターの UI を使用して、カスタムの機密情報の種類を設定します。 この方法では、正規表現、キーワード、キーワード辞書を使用することができます。 詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」を参照してください。

- **EDM を使用する** データ一致 (EDM) に基づく分類によって、カスタム機密情報の種類を設定します。 この方法では、定期的に更新できる安全なデータベースを使用して、動的な機密情報の種類を作成することができます。 詳細については、「[Exact Data Match に基づく分類で、カスタムの機密情報の種類を作成する](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)」を参照してください。

- **PowerShell を使用する** PowerShell を使用して、カスタムの機密情報の種類を設定します。 この方法は、UI を使用する場合よりも複雑ですが、より多くの構成オプションがあります。 詳細については、「[セキュリティ/コンプライアンス センターの PowerShell でカスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)」を参照してください。



> [!NOTE]
> Microsoft 365 サービスのデータ損失防止、Microsoft 365 サービスの Microsoft Information Protection、コミュニケーション コンプライアンス、情報ガバナンス、およびレコード管理内で、信頼性レベルの向上がすぐに使用できます。

> Microsoft 365 の情報保護は、次のような場合に2バイト文字セットの言語をpreviewでサポートしています。
> - 中国語 (簡体字)
> - 中国語 (繁体字)
> - 韓国語
> - 日本語

>このサポートは、機密情報の種類で使用できます。 詳細については、「[2バイト文字セットのリリースノート (preview) についての情報保護サポート](mip-dbcs-relnotes.md)」を参照してください。

## <a name="for-further-information"></a>詳細については、次の情報を参照してください。
- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
- [カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)
- [PowerShell でカスタム機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
