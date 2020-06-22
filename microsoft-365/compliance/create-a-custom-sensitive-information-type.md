---
title: セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/17/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: セキュリティ/コンプライアンス センターのグラフィカル ユーザー インターフェイスで DLP のカスタム機密情報の種類を作成、変更、削除、およびテストする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f702582a0e2c53b0846cd0586295d9bbea657e3c
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818066"
---
<!-- rename md file to match the display name -->
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する

セキュリティ/コンプライアンス センターで[カスタムの機密情報の種類](custom-sensitive-info-types.md)を作成するために、この記事をお読みください(「[https://protection.office.com](https://protection.office.com)」)。 この方法を使用して作成されるカスタムの機密情報の種類は、`Microsoft.SCCManaged.CustomRulePack`という名前のルール パッケージに追加されます。

PowerShell および Exact Data Match の機能を使用して、カスタムの機密情報の種類を作成することもできます。 これらの方法の詳細については、次を参照してください。
- [セキュリティ/コンプライアンス センター PowerShell でカスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Exact Data Match (EMD) を使用して、DPL 向けのカスタムの機密情報の種類を作成する](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

## <a name="before-you-begin"></a>はじめに

> [!NOTE]
> UI を使用してカスタムの機密情報の種類を作成、テスト、展開するには、グローバル管理者またはコンプライアンス管理者のアクセス許可が必要です。 Office 365 で「[管理者ロールについて](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide)」を参照してください。

- 組織には、データ損失防止 (DLP) を含む Office 365 Enterprise などのサブスクリプションが必要です。 [メッセージング ポリシーとコンプライアンス サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)を参照してください。 

- Custom sensitive information types require familiarity with regular expressions (RegEx). For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).

  Microsoft カスタマー サービス/サポートでは、カスタム分類または正規表現パターンの作成をサポートしていません。 サポート エンジニアは、たとえば、テスト目的のサンプルの正規表現パターンを提供したり、期待通りにトリガーされない既存の正規表現パターンのトラブルシューティングをサポートしたりなど、機能に対する限定的なサポートを提供しますが、カスタムのコンテンツ一致の開発でユーザーの要件を満たしたり、義務を果たしたりすることを確約するわけではありません。

- DLP では、検索クローラーを使用して、SharePoint Online および OneDrive for Business のサイトの機密情報を特定して分類します。 既存のコンテンツで新しいカスタムの機密情報の種類を特定するには、そのコンテンツを再クロールする必要があります。 コンテンツは、スケジュールに基づいてクロールされますが、サイト コレクション、リスト、またはライブラリのコンテンツを手動で再クロールすることができます。 詳細については、「[サイト、ライブラリ、またはリストのクロールおよび再インデックスの手動要求](https://docs.microsoft.com/sharepoint/crawl-site-content)」を参照してください。

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成する

セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して **[作成]** をクリックします。

各設定については説明するまでもありませんが、ウィザードの関連ページには説明が記載されています。

- **[名前]**

- **[説明]**

- **[近接性]**

- **[信頼度]**

- **[プライマリ パターン要素]** (キーワード、正規表現、またはディクショナリ)

- オプションの **[補強パターン要素]** (キーワード、正規表現、またはディクショナリ) および対応する **[最小コスト]** 値。

Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge". To create this custom sensitive information type, do the following steps:

1. セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して **[作成]** をクリックします。

    ![機密情報の種類と [作成] ボタンの場所](../media/scc-cust-sens-info-type-new.png)

2. **[名前と説明の選択]** ページが開いたら、次の値を入力します。

  - **[名前]**: 従業員 ID。

  - **[説明]**: 9 桁の Contoso 従業員 ID 番号を検出します。

    ![名前と説明のページ](../media/scc-cust-sens-info-type-new-name-desc.png)

    完了したら、**[次へ]** をクリックします。

3. **[一致の要件]** ページが開いたら、**[要素の追加]** をクリックして、次の設定を構成します。

    - **次を含むコンテンツを検出する**:
 
      a. Click **Any of these** and select **Regular expression**.

      b. In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).
  
    - **[補強要素]**: **[補強要素の追加]** をクリックして、**[このキーワード リストを含める]** を選択します。

    - **[このキーワード リストを含める]** 領域が表示されたら、次の設定を構成します。

      - **[キーワード リスト]**: 次の値を入力します: 従業員、ID、社員証。

      - **[最低数]**: 既定値 1 のままにします。

    - 既定の **[信頼度]** 値 60 のままにします。 

    - 既定の **[文字の近接]** 値 300 のままにします。

    ![[一致の要件] ページ](../media/scc-cust-sens-info-type-new-reqs.png)

    完了したら、**[次へ]** をクリックします。

4. **[確認と最終処理]** ページが開いたら、設定を確認して **[完了]** をクリックします。

    ![[確認と最終処理] ページ](../media/scc-cust-sens-info-type-new-review.png)

5. The next page encourages you to test the new custom sensitive information type by clicking **Yes**. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). To test the rule later, click **No**.

    ![推奨をテストするページ](../media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

新しい機密情報の種類が正常に作成されたことを確認するには、次に示す手順のいずれかを実行します。

  - **[分類]** \> **[機密情報の種類]** に移動して、新しいカスタムの機密情報の種類が一覧に表示されていることを確認します。

  - Test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を変更する

**注**:
<!-- check to see if this note contradicts the guidance in "customize a built in sensitive information type customize-a-built-in-sensitive-information-type it sure seems like it does-->
- You can only modify custom sensitive information types; you can't modify built-in sensitive information types. But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types. For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).

- You can only modify custom sensitive information types that you created in the UI. If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.

セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して、変更するカスタムの機密情報の種類を選択し、[**編集**] をクリックします。

  ![機密情報の種類と [編集] ボタンの場所](../media/scc-cust-sens-info-type-edit.png)

The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center. For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

機密情報の種類が正常に変更されたことを確認するには、次に示す手順のいずれかを実行します。

  - **[分類]** \> **[機密情報の種類]** に移動して、変更したカスタムの機密情報の種類のプロパティを確認します。 

  - Test the modified custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を削除する 

**注**:

- カスタムの機密情報の種類のみを削除できます。組み込みの機密情報の種類は削除できません。

- カスタムの機密情報の種類を削除する前に、その機密情報の種類を参照している DLP ポリシーまたは Exchange メール フロー ルール (別名: トランスポート ルール) がないことを確認してください。

1. セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動して、削除するカスタムの機密情報の種類を 1 つ以上選択します。

2. ポップアップが開いたら、**[削除]** (複数選択した場合は **[機密情報の種類の削除]**) をクリックします。

    ![機密情報の種類と [削除] ボタンの場所](../media/scc-cust-sens-info-type-delete.png)

3. 警告メッセージが表示されたら、**[はい]** をクリックします。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

カスタムの機密情報の種類が正常に削除されたことを確認するには、**[分類]** \> **[機密情報の種類]** に移動して、そのカスタムの機密情報の種類が一覧に表示されていないことを確認します。

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターでカスタムの機密情報の種類をテストする

1. セキュリティ/コンプライアンス センターで、**[分類]** \> **[機密情報の種類]** に移動します。

2. Select one or more custom sensitive information types to test. In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).

    ![機密情報の種類と [種類のテスト] ボタンの場所](../media/scc-cust-sens-info-type-test.png)

3. [**テストの対象ファイルのアップロード**] ページが開いたら、ファイルをドラッグ アンド ドロップするか、または [**参照**] をクリックしてファイルを選択し、テストの対象ドキュメントをアップロードします。

    ![[テストの対象ファイルのアップロード] ページ](../media/scc-cust-sens-info-type-test-upload.png)

4. **[テスト]** ボタンをクリックして、ファイル内のパターン マッチについてドキュメントをテストします。

5. [**照合結果**] ページで、[**完了**] をクリックします。

    ![照合結果](../media/scc-cust-sens-info-type-test-results.png)
