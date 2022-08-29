---
title: 機密情報の種類と完全に一致するデータをテストする
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
description: サービスを構成する
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0c8e43e9d732535bc15b7c231cc7ac91dabe3898
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67359845"
---
# <a name="test-an-exact-data-match-sensitive-information-type"></a>機密情報の種類と完全に一致するデータをテストする

## <a name="applies-to"></a>適用対象

- [新しいエクスペリエンス](sit-create-edm-sit-unified-ux-workflow.md)
- [クラシック エクスペリエンス](sit-create-edm-sit-classic-ux-workflow.md)

厳密なデータ一致 (EDM) の機密情報の種類 (SIT) が作成され、機密情報テーブルのアップロードとインデックス作成が完了したことを確認してから 1 時間後に、コンプライアンス センターの [機密情報の種類] セクションのテスト関数を使用して、検出する情報が検出されたことをテストできます。
 
>[!注:] 既に作成された EDM SIT の変更は、システム全体に伝達されるまでに時間がかかる場合があります。 検出の問題のトラブルシューティングのために EDM 機密情報の種類を変更する場合は、テスト関数を使用して影響を検証する前に、これらの変更を行ってから少なくとも 1 時間待ってください。

## <a name="test-your-edm-sit-in-the-compliance-center"></a>コンプライアンス センターで EDM SIT をテストする

1. **コンプライアンス センター** > **のデータ分類** > **の機密情報の種類** を開きます。

2. 一覧から EDM SIT を選択し、ポップアップ ウィンドウで **[テスト** ] を選択します。 このオプションは、機密情報の種類にのみ存在します。
 
3. 検出するデータを含むアイテムをアップロードします。 たとえば、機密情報テーブル内の行のサブセットを含むアイテムを作成します。 スキーマで構成可能な一致機能を使用して無視された区切り記号を定義した場合は、その区切り記号の有無にかかわらず、項目に例が含まれていることを確認します。

4. ファイルのアップロードとスキャンが完了したら、EDM SIT に一致することを確認します。

5. SIT の **Test** 関数で一致が検出された場合は、トリミングや間違った抽出が行われていないことを検証します。 たとえば、検出するはずの完全な文字列の部分文字列のみを抽出したり、複数語の文字列内の最初の単語のみを選択したり、抽出に追加の記号や文字を含めたりします。 正規表現言語リファレンスについては、「 [正規表現言語 - クイック リファレンス」](/dotnet/standard/base-types/regular-expression-language-quick-reference) を参照してください。 

5. または、次の PowerShell コマンドレットを使用することもできます。

```powershell
Test-DataClassification  -ClassificationNames “[Your EDM sensitive info type]” -TexttoClassify “[your own text to scan for matches]” 
```

> [!NOTE]
 EDM の機密情報の種類、または EDM タイプの基になっているプライマリ SIT を作成または編集すると、SIT の変更後に変更されたすべての新しいコンテンツとコンテンツは、新しい定義に一致するテキストに対してクロールされますが、変更またはインデックスが再作成されるまで既存のコンテンツはクロールされません。 

SharePoint サイトまたはライブラリまたは OneDrive 内の既存のコンテンツを強制的に再クロールするには、「 [サイト、ライブラリ、またはリストのクロールとインデックスの再作成を手動で要求する](/sharepoint/crawl-site-content)」の手順に従います。

## <a name="test-your-edm-sit-with-information-protection-policies"></a>情報保護ポリシーを使用して EDM SIT をテストする

EDM SIT が使用されている場所と、運用環境での精度を確認するには、ポリシーで使用します。

1. [自動ラベル付けポリシーを](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)作成し、シミュレーションの **概要** で実行します。

1. EDM SIT をトリガーするいくつかのコンテンツと、EDM SIT をトリガーしないコンテンツを、ポリシーが監視している場所に追加します。

1. [ **確認するアイテム] タブを** 開き、一致を確認します。

1. 必要に応じてポリシーを調整します。 

テストとチューニングの結果に問題がなければ、EDM ベースのカスタム SIT は、次のような情報保護ポリシーで使用できるようになります。

- [DLP ポリシー](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy)
- [自動ラベル作成ポリシー](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [Microsoft Defender for Cloud Apps](/cloud-app-security/data-protection-policies)

## <a name="troubleshooting-tips"></a>トラブルシューティングのヒント

一致する項目が見つからない場合は、トラブルシューティングのヒントをいくつか紹介します。

|問題  |トラブルシューティングのヒント  |
|---------|---------|
|一致が見つかりません     |  「ハッシュ」で説明されているコマンドを使用して機密データが正しくアップロードされたことを確認 [し、厳密なデータ一致の機密情報の種類の機密情報ソース テーブルをアップロードします](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)|
|一致が見つかりません   | 各パターンでプライマリ要素を構成したときに使用した SIT をテストします。 これにより、SIT がアイテム内の例と一致することが確認されます。 EDM の機密情報の種類の分類要素として正しく定義されていない SIT を使用することが、EDM の検出エラーの最も一般的な原因です。         |
|EDM 型のプライマリ要素に対して選択した SIT がアイテムに一致しないか、予想よりも少ない一致が見つかりません    |  コンテンツ内の区切り記号と区切り記号がサポートされていることを確認します。 スキーマで定義されている無視された区切り記号を必ず含めます。       |
|プライマリ要素 SIT は項目内の一致を検出しますが、EDM SIT では一致しません。     | - \s などの空白区切り記号のキャプチャを開始または終了する REGEX ステートメントを確認します。 空白は、データ テーブル内のハッシュ値と一致しません。 代わりに 、\b のような単語区切り記号を使用します。 </br> - REGEX ステートメントを調べて、部分文字列だけでなく、キャプチャする文字列全体がキャプチャされていることを確認します。 たとえば、電子メール アドレス \b[a-zA-Z]{2,30}@[a-zA-Z]{2,20}.[a-zA-Z]{2,3}\b は *user@contoso.com* と正しく一致しますが、不完全な形式の *user@contoso.co.jp* のみをキャプチャします。
|プライマリ要素とセカンダリ要素が定義されていない EDM SIT は、項目を検出しますが、プライマリ要素とセカンダリ要素が必要な場合に予想よりも少ない一致を検出または検出しません。  | 2 次証拠に使用される列の値が、スペース、コンマ、またはその他の単語区切り記号を含まない 1 つの単語または文字列で構成されていない場合は、目的のパターンに従う複数単語の文字列を検出するように設計された REGEX (大文字で始まる一定の数の連続する単語など) を使用する機密情報の種類に関連付ける必要があります。 または、その列内のすべての一意の値を一覧表示するキーワード ディクショナリ。 たとえば、人の都市または居住地の追加の証拠列がある場合は、テーブルのすべての一意の都市名を含むリストを作成し、それを使用して辞書ベースの機密情報の種類を作成できます。 XML で EDM SIT 定義をエクスポートして編集することで、この SIT を EDM 機密情報の種類の対応する列の分類要素として使用します。 [ルール パッケージを手動で作成する方法に関するページを](sit-get-started-exact-data-match-create-rule-package.md#create-a-rule-package-manually)参照してください。|
|SIT テスト関数は、一致をまったく検出しません。   | 選択した SIT に、追加のキーワードまたはその他の検証の要件が含まれているかどうかを確認します。 組み込みの SIT については、「 [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md#sensitive-information-type-entity-definitions) 」を参照して、各種類の照合に必要な最小要件を確認します。        |
|テスト機能は機能しますが、DLP または自動ラベル付け規則で SharePoint または OneDrive アイテムが検出されない     | 一致するドキュメントがコンテンツ エクスプローラーに表示されるかどうかを確認します。 存在しない場合は、機密情報の種類の変更後に作成されたコンテンツのみが一致として表示されることに注意してください。 既存のアイテムを表示するには、サイトとライブラリを再クロールする必要があります。 SharePoint と OneDrive の再クロールの詳細については [、「サイト、ライブラリ、またはリストのクロールとインデックスの再作成を手動で要求](/sharepoint/crawl-site-content) する」を参照してください。        |
|複数の一致を必要とする DLP または自動ラベル付けルールがトリガーされない     |EDM 型と基本機密情報の種類の両方の近接要件が満たされていることを確認します。 たとえば、プライマリ要素とサポートキーワードの間の最大距離が 300 文字で、キーワードが長いテーブルの最初の行にのみ存在する場合、一致する値の最初の数行のみが近接要件を満たす可能性があります。 より緩やかな近接ルールをサポートするように SIT 定義を変更するか、ドキュメント オプション内の任意の場所を使用して、追加の証拠条件を指定します。         |
|EDM 型の検出が一貫性がない、または不規則である     |EDM 型のプライマリ要素のベースとして使用した機密情報の種類が、不要なコンテンツを検出していないことを確認します。 単語、任意の番号、すべてのメール アドレスなど、無関係なコンテンツと一致しすぎる SIT を使用すると、サービスが飽和状態になり、関連する一致が無視される可能性があります。 コンテンツ エクスプローラーで主な要素に使用した機密タイプと一致するコンテンツ の個数を確認します。 </br> SIT が一致するコンテンツが多すぎるかどうかを見積もるには: </br> - コンテンツ エクスプローラーのコンテンツ アイテムの数を、機密性の高い種類が作成されてからの日数で割る。 </br> - 1 日あたりの一致数が数十万または数百万の範囲にある場合、プライマリ SIT が広すぎる可能性があります。 EDM 型に対して適切な機密情報の種類を選択する際の推奨事項とベスト プラクティスについては、「 [正確なデータ一致ベース](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types) の機密情報の種類について説明します。         |
