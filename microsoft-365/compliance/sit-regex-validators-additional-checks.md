---
title: 機密情報の種類 REGEX 検証ツールと追加チェック
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: sentisitve 情報の種類で REGEX 検証ツールと追加チェックを使用する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 615d4757be16b3171005105aea8148536e6f3015
ms.sourcegitcommit: bb493f12701f6d6ee7d5e64b541adb87470bc7bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2022
ms.locfileid: "62902681"
---
# <a name="sensitive-information-type-regex-validators-and-additional-check"></a>機密情報の種類 REGEX 検証ツールと追加チェック

> [!IMPORTANT]
> Microsoft カスタマー サービス/サポートでは、カスタム分類または正規表現パターンの作成をサポートしていません。 サポート エンジニアは、たとえば、テスト目的のサンプルの正規表現パターンを提供したり、期待通りにトリガーされない既存の正規表現パターンのトラブルシューティングをサポートしたりなど、機能に対する限定的なサポートを提供しますが、カスタムのコンテンツ一致の開発でユーザーの要件を満たしたり、義務を果たしたりすることを確約するわけではありません。

## <a name="sensitive-information-type-regular-expression-validators"></a>機密情報の種類の正規表現検証ツール

### <a name="checksum-validator"></a>チェックサム検証ツール

正規表現の数字にチェックサムを実行する必要がある場合は、チェックサム検証ツール *を使用できます*。 たとえば、最後の数字が mod 9 計算を使用して検証されるチェックサム桁である 8 桁のライセンス番号に対して SIT を作成する必要があるとします。 チェックサム アルゴリズムは次のように設定しました。

```console
Sum = digit 1 * Weight 1 + digit 2 * weight 2 + digit 3 * weight 3 + digit 4 * weight 4 + digit 5 * weight 5 + digit 6 * weight 6 + digit 7 * weight 7 + digit 8 * weight 8
Mod value = Sum % 9
If Mod value == digit 8
    Account number is valid
If Mod value != digit 8
    Account number is invalid
```

1. 次の正規表現を使用してプライマリ要素を定義します。

   ```console
   \d{8}
   ```

2. 次に、チェックサム検証ツールを追加します。

3. 重み値をコンマで区切って追加し、チェック桁の位置と Mod 値を追加します。 Modulo 操作の詳細については、「Modulo 操作 [」を参照してください](https://en.wikipedia.org/wiki/Modulo_operation)。

   > [!NOTE]
   > チェック桁がチェックサム計算の一部ではない場合は、チェック桁の重みとして 0 を使用します。 たとえば、上記の場合、チェック桁を使用してチェック桁を計算しない場合、重み 8 は 0 に等しくなります。

   :::image type="content" alt-text="構成済みのチェックサム検証ツールのスクリーンショット。" source="../media/checksum-validator.png" lightbox="../media/checksum-validator.png":::

### <a name="date-validator"></a>日付検証

正規表現に埋め込まれた日付値が、作成する新しいパターンの一部である場合は、日付検証ツールを使用して、条件を満たした日付をテストできます。 たとえば、9 桁の従業員 ID 番号の SIT を作成するとします。 最初の 6 桁は DDMMYY 形式の採用日であり、最後の 3 桁はランダムに生成された数値です。 最初の 6 桁の数字が正しい形式で表示されていることを検証します。

1. 次の正規表現を使用してプライマリ要素を定義します。

   ```console
   \d{9}
   ```

2. 次に、日付検証機能を追加します。

3. 日付形式と開始オフセットを選択します。 日付文字列は最初の 6 桁の数字で、オフセットは .`0`

   :::image type="content" alt-text="構成済みの日付検証ツールのスクリーンショット。" source="../media/date-validator.png" lightbox="../media/date-validator.png":::

### <a name="functional-processors-as-validators"></a>バリデーターとしての機能プロセッサ

関数プロセッサは、最も一般的に使用される一部の SIT に対してバリデーターとして使用できます。 これにより、独自の正規表現を定義しながら、SIT で必要な追加のチェックに合格することができます。 たとえば、Func_India_Aadharによって定義されたカスタム正規表現が、インドの Aadhar カードに必要な検証ロジックを渡す必要があります。 検証機能として使用できる DLP 関数の詳細については、「機密情報の [種類の関数」を参照してください](sit-functions.md)。 

### <a name="luhn-check-validator"></a>Luhn check validator

Luhn アルゴリズムを渡す正規表現を含むカスタムの機密情報の種類がある場合は、Luhn チェック検証ツール [を使用できます](https://en.wikipedia.org/wiki/Luhn_algorithm)。

## <a name="sensitive-information-type-additional-checks"></a>機密情報の種類の追加チェック

利用可能な追加のチェックの定義と例を次に示します。

**特定の一致の除外**: このチェックでは、編集しているパターンの一致を検出するときに除外するキーワードを定義できます。 たとえば、有効な数値と一致しないので、'4111111111111111' などのテスト用クレジット カード番号を除外することができます。

**文字** で始まる または始まらない: このチェック ボックスを使用すると、一致する項目で始まる必要がある文字または一致する項目で始まってはならない文字を定義できます。 たとえば、41、42、または 43 で始まるクレジット カード番号のみを検出する場合のようにパターンで 検出する場合は、[**最初は** ] を選び、一覧に 41、42、43 をコンマで区切って追加します。 

**文字** で終わるまたは終わらない:このチェックボックスを使用すると、一致する項目が終わる必要がある文字または一致する項目が終わってはならない文字を定義できます。 たとえば、従業員 ID の番号が 0 または 1 で終わる場合は、[**最後は** ではない] を選択して、一覧に 0 と 1 をコンマで区切って追加します。

**重複する文字を除外**: このチェック ボックスをオンにした場合、すべての桁が同一の一致を無視できます。 たとえば、6 桁の従業員 ID 番号ですべての数字が同じ数字になってはいけない場合 **重複する文字を除外** を選択して、111111、222222、333333、444444、555555、666666、777777、888888、999999、および 000000 を従業員 ID の有効な一致のリストから除外します。

**プレフィックスを含める、または除外する**: このチェックでは、一致するエンティティの直前に存在する必要があるキーワードまたは存在してはいけないキーワードを定義できます。 選択内容に応じて、ここに含まれるプレフィックスを前に持つ、一致または一致しないエンティティになります。 たとえば、プレフィックス **GUID:** を **除外** する場合、**GUID:** を頭に持つエンティティは、一致とは見なされません。

**サフィックスを含める、または除外する**: このチェックでは、一致するエンティティの直後に存在する必要があるキーワードまたは存在してはいけないキーワードを定義できます。 選択内容に応じて、ここに含まれるサフィックスを最後に持つ、一致または一致しないエンティティになります。 たとえば、サフィックス **:GUID** を **除外** する場合、**:GUID** が後に続くテキストは一致としません。
