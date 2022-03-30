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
description: サービスの構成
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d0870cda205168e73d40adef7cdab333c7f0abdf
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63679942"
---
# <a name="test-an-exact-data-match-sensitive-information-type"></a>機密情報の種類と完全に一致するデータをテストする

正確なデータ一致 (EDM) 機密情報の種類 (SIT) が作成され、機密情報テーブルのアップロードとインデックス作成が完了した確認の 1 時間後に、コンプライアンス センターの [機密情報の種類] セクションでテスト関数を使用して検出する情報が検出されたことをテストできます。
 
>[!注:] 既に作成された EDM SIT の変更は、システム全体に伝達するために時間がかかる場合があります。 検出の問題のトラブルシューティングのために EDM 機密情報の種類を変更する場合は、テスト関数を使用して影響を検証する前に、これらの変更を行った後、少なくとも 1 時間待ちます。

## <a name="test-your-edm-sit-in-the-compliance-center"></a>コンプライアンス センターで EDM SIT をテストする

1. [ **コンプライアンス センター** > **] [データの分類** > **] を開きます。[セキュリティ情報の種類] をクリックします**。

2. リストから EDM SIT を選択し、フライアウト ウィンドウ **で [テスト** ] を選択します。 このオプションは、機密情報の種類の下にのみ表示されます。
 
3. アップロードするデータを含むアイテムを選択します。 たとえば、機密情報テーブル内の行のサブセットを含むアイテムを作成します。 スキーマで構成可能な一致機能を使用して、無視される区切り記号を定義した場合は、それらの区切り記号の使用と使用しない例がアイテムに含まれるか確認してください。

4. ファイルがアップロードおよびスキャンされた後、EDM SIT との一致を確認します。

5. SIT の **Test** 関数で一致が検出された場合は、その関数がトリミングされていないか、正しく抽出されていないか検証します。 たとえば、検出するはずの文字列全体の部分文字列のみを抽出したり、複数単語の文字列の最初の単語のみを取得したり、抽出に余分な記号や文字を含めることができます。 正規表現 [言語リファレンスについては、「正規表現言語 -](/dotnet/standard/base-types/regular-expression-language-quick-reference) クイック リファレンス」を参照してください。 

5. または、次の PowerShell コマンドレットを使用できます。

```powershell
Test-DataClassification  -ClassificationNames “[Your EDM sensitive info type]” -TexttoClassify “[your own text to scan for matches]” 
```

> [!NOTE]
 EDM 機密情報の種類を作成または編集する場合、または EDM の種類が基になるプライマリ SIT の場合、変更後に変更された新しいコンテンツとコンテンツはすべて、新しい定義に一致するテキストに対してクロールされますが、既存のコンテンツは変更またはインデックスの再作成までクロールされません。 

SharePoint サイトまたはライブラリまたは OneDrive の既存のコンテンツを強制的に再クロールするには、「サイト、ライブラリ、またはリストのクロールとインデックスの再作成を手動[](/sharepoint/crawl-site-content)で要求する」の手順に従います。

## <a name="test-your-edm-sit-in-mip-policies"></a>MIP ポリシーで EDM SIT をテストする

ポリシーで使用することで、EDM SIT が使用されている場所と実稼働環境での精度を確認できます。

1. 自動ラベル [付けポリシーを作成し、](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) シミュレーションの概要で **実行します**。

1. EDM SIT をトリガーするコンテンツと、EDM SIT をトリガーしないコンテンツを、ポリシーが監視している場所に追加します。

1. [確認する **アイテム] タブを開** き、一致を確認します。

1. 必要に応じてポリシーを調整します。 

テストとチューニングの結果に満足したら、EDM ベースのカスタム SIT は、次のような情報保護ポリシーで使用できます。

- [DLP ポリシー](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy)
- [自動ラベル作成ポリシー](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [Microsoft Defender for Cloud Apps](/cloud-app-security/data-protection-policies)

## <a name="troubleshooting-tips"></a>トラブルシューティングのヒント

一致が見つからなかった場合は、トラブルシューティングのヒントを次に示します。


|問題  |トラブルシューティングのヒント  |
|---------|---------|
|一致が見つかりません     |  ハッシュで説明されているコマンドを使用して機密データが正しくアップロードされていることを確認し、機密情報の種類に一致する正確なデータの機密情報ソース テーブル[をアップロードします](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types)。|
|一致が見つかりません   | 各パターンでプライマリ要素を構成するときに使用した SIT をテストします。 これにより、SIT がアイテムの例と一致する可能性が確認されます。 EDM 機密情報の種類の分類要素として正しく定義されていない SIT を使用すると、EDM での検出エラーの最も一般的な原因となります。         |
|EDM 型のプライマリ要素に対して選択した SIT がアイテムに一致しないか、予想より少ない一致を見つける    |  コンテンツ内の区切り記号と区切り記号がサポートされているのを確認します。 スキーマで定義されている無視された区切り記号を必ず含める必要があります。       |
|プライマリ要素 SIT はアイテム内の一致を見つけるが、EDM SIT は一致しない。     | - /s など、キャプチャする空白の区切り文字を開始または終了するための REGEX ステートメントを確認します。 空白は、データ テーブルのハッシュ値と一致しません。 代わりに/b のような単語区切り記号を使用します。 </br> - REGEX ステートメントを確認して、サブ文字列ではなく、キャプチャする文字列全体をキャプチャします。 たとえば、電子メール アドレスのこのパターン [a-zA-Z]{30}@[a-zA-Z]{20}.[a-zA-Z] は{2,3}*、user@contoso.com と* *user@contoso.co.jp。*  |
|プライマリ要素とセカンダリ要素が定義されていない EDM SIT は、アイテムを検出しますが、プライマリ要素とセカンダリ要素が必要な場合は、検出しないか、予想よりも少ない値を検出します。  | 二次証拠の値が、スペースを含む 1 つの単語または文字列で構成されているか、複数単語の文字列を検出する REGEX ステートメントを使用してください。 たとえば、\b[A-Z][a-z]{1,25}([ -][A-Z][a-z]){1,25}{0,4}\b は、大文字で始まる 1 ~ 5 つの連続する単語のシーケンスに一致します。 この SIT は、EDM 機密情報タイプ XML の追加証拠条件の分類要素として使用します。 「ルール [パッケージを手動で作成する」を参照してください。](sit-get-started-exact-data-match-create-rule-package.md#create-a-rule-package-manually)|
|SIT テスト関数は一致を検出しません。   | 選択した SIT に追加のキーワードまたは他の検証の要件が含まれるか確認します。 組み込みの SIT については、「機密情報[](sensitive-information-type-entity-definitions.md#sensitive-information-type-entity-definitions)の種類エンティティ定義」を参照して、各種類に一致する最小要件を確認します。        |
|テスト機能は機能しますがSharePointまたはOneDriveアイテムが DLP または自動ラベル付けルールで検出されない     | 一致するドキュメントがコンテンツ エクスプローラーに表示されるのを確認します。 機密情報の種類が変更された後に作成されたコンテンツだけが一致として表示されます。 既存のアイテムを表示するには、サイトとライブラリを再クロールする必要があります。 詳細[については、「サイト、ライブラリ、](/sharepoint/crawl-site-content)またはリストのクロールとインデックスの再作成を手動で要求する」を参照SharePointおよびOneDrive。        |
|複数の一致を必要とする DLP または自動ラベル付けルールはトリガーしない     |EDM の種類と基本機密情報の種類の両方の近接要件が満たされていないことを確認します。 たとえば、プライマリ要素とサポート キーワードの間の最大距離が 300 文字ですが、キーワードが長いテーブルの最初の行にのみ存在する場合、一致する値の最初の数行だけが近接要件を満たす可能性があります。 SIT 定義を変更して、より緩和された近接ルールをサポートするか、追加の証拠条件にドキュメント オプションの任意の場所を使用します。         |
|EDM 型の検出が一貫性がない、または不安定     |EDM タイプのプライマリ要素のベースとして使用した機密情報の種類が、不要なコンテンツを検出されていないことを確認します。 関連のないコンテンツ (単語、任意の番号、すべての電子メール アドレスなど) に一致しすぎる SIT を使用すると、サービスが関連する一致を飽和状態にし、無視する可能性があります。 コンテンツ エクスプローラーの主な要素に使用した機密性の高い種類に一致するコンテンツピースの数を確認します。 </br> SIT が一致しすぎのコンテンツを推定するには、次の方法を実行します。 </br> - コンテンツ エクスプローラー内のコンテンツ アイテムの数を、機密性の高い種類が作成された日数で割る。 </br> - 1 日あたりの一致数が数十万または数百万の範囲にある場合、プライマリ SIT が広すぎる可能性があります。 EDM [型に適切](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types) な機密情報の種類を選択する際の推奨事項とベスト プラクティスについては、「完全なデータ一致ベースの機密情報の種類について」を参照してください。         |