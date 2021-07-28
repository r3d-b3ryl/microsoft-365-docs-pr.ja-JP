---
title: 完全一致スキーマと機密情報の種類ウィザードを使用する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 完全一致スキーマと機密情報の種類ウィザードrを使用する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1cbbb02528e898f775d63bf023b641bdaaeeb07e
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2021
ms.locfileid: "53543607"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>完全一致スキーマと機密情報の種類ウィザードを使用する

[完全一致 (EDM) ベースの分類を使用してカスタムの機密情報の種類を作成するには](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)、さまざまな手順が必要です。  このウィザードを使用すると、スキーマおよび機密情報の種類 (SIT) パターン (ルール パッケージ) ファイルを作成して、プロセスを簡略化できます。

このウィザードが代わりとなるのは、次のような場合です。

- [機密情報のデータベースのスキーマを定義する](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [パターンを設定する (ルール パッケージ)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

手順 [パート 1: EDM ベースの分類をセットアップする](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification)。

## <a name="pre-requisites"></a>前提条件.

1. EDM [ワーク フローの概要](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance)で、カスタムの機密情報の種類を作成する手順がわかります。

2. 「機密データをファイル形式または [.tsv 形式.csv保存する」の手順を実行します](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-or-tsv-format)。

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>完全一致スキーマと機密情報の種類パターンウィザードを使用する

1. テナントの Microsoft 365 コンプライアンス センターでは、**データの分類** > **完全一致** に移動します。 

2. **EDM スキーマを作成** を選択して、スキーマ ウィザードの構成 ポップアップを開きます。

![EDM スキーマ作成ウィザードの設定ポップアップ](../media/edm-schema-wizard-1.png)

3. 適切な **名前** と **説明** を入力します。

4. その動作 **が必要な場合は、[** すべてのスキーマ フィールドの区切り記号と句読点を無視する] を選択します。 大文字と小文字または区切り記号を無視するように EDM を構成する方法の詳細については、「完全データ一致 [(EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)ベースの分類を使用してカスタム機密情報の種類を作成する」を参照してください。

5. **スキーマ フィールド#1** 必要な値を入力し、必要に応じてフィールドを追加します。 

> [!IMPORTANT]
> 1 つ以上 5 つ以下のスキーマ フィールド を検索可能として指定する必要があります。

6. [保存] を選択します。 スキーマ一覧表が表示されます。

7. **EDM の機密情報の種類** を選択し、 **EDM の機密情報の種類を作成** して、機密情報の種類の構成ウィザードを開きます。

8. **既存のEDM スキーマを選択** を選択し、リストの手順2 から 6 で作成したスキーマを選択します。

9. **次へ** を選択し、**パターンの作成** を選択します。

10. **信頼度** および **主要要素** を選択します。  パターン構成方法の詳細については、「[コンプライアンス センターでカスタムの機密情報の種類を作成](create-a-custom-sensitive-information-type.md)」を参照してください。

11.  **主要要素の機密情報の種類** を選択し、それをに関連付けます。 利用可能な機密情報の種類の詳細については、「[機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)」を参照してください。

12. [**完了**] を選択します。

13. 目的の **信頼度と文字の間隔** を選択します。  これは、EDM の機密情報の種類の既定値となります。

13. EDM **機密情報** の種類に追加のパターンを作成する場合は、[パターンの作成] を選択します。

14. [**次へ**] を選択し、**名前** および **管理者向けの説明** を入力します。

15. レビューし、[**送信**] を選択します。

編集および削除コントロールを表示して、機密情報の種類パターンを削除または編集します。

> [!IMPORTANT]
> スキーマを削除し、それが既に EDM の機密情報の種類に関連付けられている場合は、まずEDM の機密情報の種類を削除し、その後、スキーマを削除できます。

## <a name="post-creation-steps"></a>作成後の手順

このウィザードを使用して EDM のスキーマおよびパターン (ルール パッケージ) ファイルを作成後、EDM ユーザー機密情報の種類を使用する前に、手順 [パート 2: 機密性の高いデータをハッシュおよびアップロードする](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data)の手順を実行する必要があります。

機密情報テーブルが正しくアップロードされていることを確認したら、正しく動作しているのをテストできます。

1. Open **Compliance center** Data  >  **classification** Sensitive Information  >  **Types**.
2. リストから EDM SIT を選択し、フライアウト ウィンドウ **で [テスト** ] を選択します。 
3. アップロードするデータを含むアイテムを作成します。たとえば、機密情報テーブルにデータの一部を含むアイテムを作成します。 スキーマで構成可能な一致機能を使用して、無視される区切り記号を定義した場合は、それらの区切り記号の使用と使用しない例がアイテムに含まれるか確認してください。
4. ファイルがアップロードおよびスキャンされた後、EDM SIT との一致を確認します。
5. SIT の **Test** 関数で一致が検出された場合は、その関数がトリミングされていないか、誤って抽出されていないか確認してください。 たとえば、検出するはずの文字列全体の部分文字列のみを抽出したり、複数単語の文字列の最初の単語のみを取得したり、抽出に余分な記号や文字を含めることができます。 正規表現 [言語リファレンスについては、「正規表現言語 -](/dotnet/standard/base-types/regular-expression-language-quick-reference) クイック リファレンス」を参照してください。 

### <a name="troubleshooting"></a>トラブルシューティング

一致が見つからなかった場合は、次の手順を実行します。
- [EDM](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)ツールを使用して機密データをアップロードするガイダンスで説明されているコマンドを使用して、機密データが正しくアップロードされていることを確認します。
- アイテムに入力した例が機密情報テーブルに存在し、無視された区切り記号が正しいか確認します。
- **各** パターンでプライマリ要素を構成するときに使用した SIT をテストします。 これにより、SIT がアイテムの例と一致する可能性が確認されます。 
  -  EDM 型のプライマリ要素に対して選択した SIT がアイテム内で一致を見つけなかったり、予期した数よりも少ない一致を見つけた場合は、コンテンツに存在する区切り記号と区切り記号がサポートされています。 スキーマで定義されている無視された区切り記号を必ず含める必要があります。 
  -  Test 関数 **で** コンテンツが検出されない場合は、選択した SIT に追加のキーワードまたは他の検証の要件が含まれるか確認します。 組み込みの SIT については[](sensitive-information-type-entity-definitions.md)、「機密情報の種類エンティティ定義」を参照して、各種類に一致する最小要件を確認します。
