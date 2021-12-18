---
title: 攻撃シミュレーション トレーニングのエンド ユーザー通知
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、計画 2 の Microsoft Defender で攻撃シミュレーション トレーニング用のエンド ユーザー通知メール メッセージを作成Office 365できます。
ms.technology: mdo
ms.openlocfilehash: bddd0b587e8fbf3007009a070cbd3e7616faac04
ms.sourcegitcommit: 282f3a58b8e11615b3e53328e6b89a6ac52008e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2021
ms.locfileid: "61561104"
---
# <a name="end-user-notifications-for-attack-simulation-training"></a>攻撃シミュレーション トレーニングのエンド ユーザー通知

Microsoft 365 E5 または Microsoft Defender for Office 365 プラン 2 の攻撃シミュレーション トレーニングでは、エンド ユーザーの通知は、ユーザーに送信される電子メール メッセージで、次の 2 つの基本的な種類の通知があります。

- **シミュレーション通知**: これらのメッセージは、ユーザーがトレーニングに登録されている場合や、必要なトレーニングのリマインダーとして送信されます。
- **肯定的な強化通知**: ユーザーがシミュレートされたフィッシング メッセージを報告すると、これらのメッセージが送信されます。

使用可能なエンド ユーザー通知を表示するには、Microsoft 365 Defender ポータルを開き、[電子メール & 攻撃シミュレーション トレーニング エンド ユーザー通知] タブ <https://security.microsoft.com>  \>  \> **に移動** します。[エンド ユーザー通知] タブ **に直接移動** するには、 を使用します <https://security.microsoft.com/attacksimulator?viewid=endUserNotification> 。

[ **エンド ユーザー通知] タブには** 、次の 2 つのタブがあります。

- **グローバル通知**: 組み込み通知と変更不可の通知が含まれる。
- **テナント通知**: 作成したカスタム通知が含まれる。

通知ごとに次の情報が表示されます。

- **通知**: 通知の名前。
- **言語**: 通知に複数の翻訳が含まれている場合、最初の 2 つの言語が直接表示されます。 残りの言語を表示するには、数値アイコン (たとえば **、+10) の上にマウス ポインターを置きます**。
- **種類**: 値は、シミュレーション **通知または正の****配筋通知です**。
- **ソース**: 組み込みの通知の場合、値はグローバル **です**。 カスタム通知の場合、値は **Tenant です**。
- **状態**
- **リンクされたシミュレーション**
- **作成者**: 組み込みの通知の場合、値は **Microsoft です**。 カスタム通知の場合、値は通知を作成したユーザーの UPN です。
- **作成日時**
- **変更者**
- **最終変更時刻**

一覧で通知を見つけるには、[検索] アイコン ![ を使用します。](../../media/m365-cc-sc-search-icon.png) **通知** の名前を検索する検索ボックス。

通知を種類別にグループ化するには、[グループ] アイコン ![ をクリックします。](../../media/m365-cc-sc-group-icon.png) **グループ化** し、[通知の **種類] を選択します**。 通知のグループを解除するには、[なし] を **選択します**。

[テナント通知 **] タブでのみ** 、[フィルター] アイコン ![ をクリックします。](../../media/m365-cc-sc-filter-icon.png) をクリックして、1 つ以上の言語で通知をフィルター処理します。

表示される 1 つ以上の列を削除するには、[列のカスタマイズ ![ ] アイコンをクリックします。](../../media/m365-cc-sc-customize-icon.png) **列をカスタマイズします**。

一覧から通知を選択すると、詳細フライアウトが表示され、次の情報が表示されます。

- **[プレビュー** ] タブ: 通知メッセージを表示します。 異なる言語でメッセージを表示するには、[言語の選択 **] ボックスを使用** します。
- **[詳細** ] タブ: 通知の詳細を表示します。
  - **通知の説明**
  - **ソース**: 組み込みの通知の場合、値はグローバル **です**。 カスタム通知の場合、値は **Tenant です**。
  - **通知の種類**
  - **変更者**
  - **最終更新日時**

## <a name="create-end-user-notifications"></a>エンド ユーザー通知の作成

[テナント通知 **] タブで** 、[新しいアイコンの作成 ![ ] をクリックできます。](../../media/m365-cc-sc-create-icon.png) **新しいエンド** ユーザー通知ウィザードを開始するには、新規を作成します。

1. [詳細の **定義] ページ** **で、次の設定を構成します。
   - **[通知の種類を選択****]: 正の配筋通知または****シミュレーション通知を** 使用できます。
   - **名前**: 一意の名前を入力します。
   - **説明**: オプションの説明を入力します。

   完了したら、**[次へ]** をクリックします。

2. [コンテンツ **の定義] ページ** で使用できる唯一の設定は、[ビジネス言語でコンテンツを追加 **] ボタン** です。 クリックすると、次の設定を含 **む** 既定の言語の [コンテンツの追加] フライアウトが表示されます。
   - **表示名から**
   - **メール アドレスから**
   - **メールの言語を選択します**。一覧から言語を選択します。
   - **これを既定の** 言語としてマークします。これは通知の最初の言語と唯一の言語なので、この値が選択され、変更できない場合があります。
   - **件名**: 既定値は、フィッシング **の報告に感謝** しますが、変更できます。
   - **メールのインポート**: 必要に応じてこのボタンをクリックし、[ファイルの選択] をクリックして、既存のプレーン テキスト メッセージ ファイルをインポートできます。
   - メール コンテンツ領域: 次の 2 つのタブを使用できます。
     - **[** テキスト] タブ: リッチ テキスト エディターを使用して通知メールを作成できます。 一般的なフォントと書式設定の設定に加えて、次の設定を使用できます。
       - **動的タグ**: 次のタグから選択します。
         - **名を挿入する**
         - **最後の名前を挿入する**
         - **UPN の挿入**
         - **メール アドレスの挿入**
         - **ペイロードの挿入**
     - **[コード** ] タブ: HTML コードを直接表示および変更できます。

   結果をプレビューするには、ページの上部にある **[メール** のプレビュー] ボタンをクリックします。

   完了したら、**[保存]** をクリックします。

   [コンテンツの定義] ページ **に戻り** 、作成した通知が次の情報で要約されます。

   - **Language**
   - **件名**
   - **カテゴリ**
   - **アクション**: 次のアイコンを使用できます。
     - ![[編集] アイコン。](../../media/m365-cc-sc-edit-icon.png) **Edit**
     - ![[表示] アイコン。](../../media/m365-cc-sc-view-icon.png) **表示**
     - ![[削除] アイコン。](../../media/m365-cc-sc-delete-icon.png) **削除**: 通知の言語バージョンのみがある場合は、その通知を削除できます。

   別の言語で通知のバージョンを追加するには、[翻訳の追加] ![ アイコンをクリックします ](../../media/m365-cc-sc-create-icon.png) 。 表示される **[翻訳の追加**] フライアウトでは、前に説明した既定の言語の [コンテンツの追加] フライアウトと同じ設定を使用できます。 唯一の違いは、[追加の翻訳 **で既定の** 言語としてマークする] を選択できる点です。

   完了したら、[保存] を **クリックします。**

   この手順を何度でも繰り返して、サポートされている 12 の言語で翻訳されたバージョンの通知を作成できます。

   完了したら、[次へ] を **クリックします。**

3. [通知 **の確認]** ページで、通知の詳細を確認できます。

   各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。

   完了したら、**[送信]** をクリックします。

   [新しい **シミュレーション通知の作成** ] ページで、リンクを使用して、新しい通知の作成、シミュレーションの起動、すべての通知の表示を行えます。

   完了したら、[**完了**] をクリックします。

[テナント通知 **] タブに** 戻り、作成した通知が一覧になります。

通知を選択すると、次の追加オプションを使用できます。

作成した通知が [正の配筋通知の選択] リストに表示される [正の配筋通知] ページ **に戻** ります。

- 通知を変更したり、翻訳を追加したりするには、通知を選択し、[編集] アイコン ![ をクリックします。](../../media/m365-cc-sc-edit-icon.png) **通知を編集** して、前述のように通知ウィザードを開始します (ほとんどの値が既に入力されています)。 12 のサポートされている言語の翻訳が通知に既に存在する場合は、それ以上の翻訳を追加できます。

- 通知のコピーを作成するには、通知を選択して、 ![コピー アイコンを作成します。](../../media/m365-cc-sc-copy-icon.png).

- 通知を削除するには、通知を選択して、 ![[削除] アイコン。](../../media/m365-cc-sc-delete-icon.png).

## <a name="related-links"></a>関連リンク

[攻撃シミュレーション トレーニングの使用を開始する](attack-simulation-training-get-started.md)

[フィッシング攻撃シミュレーションの作成](attack-simulation-training.md)

[攻撃シミュレーション トレーニングのシミュレーションの自動化](attack-simulation-training-simulation-automations.md)