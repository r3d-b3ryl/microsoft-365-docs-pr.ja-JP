---
title: 完全一致スキーマと機密情報の種類ウィザードを使用する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 完全一致スキーマと機密情報の種類ウィザードrを使用する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2081de887e09794350222dac3527bb3ff932837a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699160"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>完全一致スキーマと機密情報の種類ウィザードを使用する

[完全一致 (EDM) ベースの分類を使用してカスタムの機密情報の種類を作成するには](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)、さまざまな手順が必要です。  このウィザードを使用すると、スキーマと機密情報の種類パターン (ルール パッケージ) ファイルを作成して、プロセスを簡素化できます。

> [!NOTE]
> 完全一致スキーマと機密情報の種類ウィザードは、World Wide クラウドと GCC クラウドでのみ使用できます。

このウィザードが代わりとなるのは、次のような場合です。

- [機密情報のデータベースのスキーマを定義する](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [パターンを設定する (ルール パッケージ)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

手順 [パート 1: EDM ベースの分類をセットアップする](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification)。

## <a name="pre-requisites"></a>前提条件.

1. EDM [ワーク フローの概要](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance)で、カスタムの機密情報の種類を作成する手順がわかります。

2. [機密データを .csv 形式で保存](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) セクションの手順を実行します。

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>完全一致スキーマと機密情報の種類パターンウィザードを使用する

1. テナントの Microsoft 365 コンプライアンス センターでは、**データの分類** > **完全一致** に移動します。 

2. **EDM スキーマを作成** を選択して、スキーマ ウィザードの構成 ポップアップを開きます。

![EDM スキーマ作成ウィザードの設定ポップアップ](../media/edm-schema-wizard-1.png)

3. 適切な **名前** と **説明** を入力します。

4. この動作が必要な場合は、**すべてのスキーマ フィールドの区切り文字と句読点を無視する** を選択します。 EDM 構成方法の詳細については、「[ 完全一致 (EDM) ベースの分類をを使用してカスタムの機密情報の種類を作成する](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)」を参照してください。

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

13. EDM の機密情報の種類の追加のパターンを作成する場合は、 **パターンの作成** 選択します。

14. [**次へ**] を選択し、**名前** および **管理者向けの説明** を入力します。

15. レビューし、[**送信**] を選択します。

編集および削除コントロールを表示して、機密情報の種類パターンを削除または編集します。

> [!IMPORTANT]
> スキーマを削除し、それが既に EDM の機密情報の種類に関連付けられている場合は、まずEDM の機密情報の種類を削除し、その後、スキーマを削除できます。

## <a name="post-steps"></a>ステップを投稿する

このウィザードを使用して EDM のスキーマおよびパターン (ルール パッケージ) ファイルを作成後、EDM ユーザー機密情報の種類を使用する前に、手順 [パート 2: 機密性の高いデータをハッシュおよびアップロードする](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data)の手順を実行する必要があります。