---
title: 保持ラベルを自動的に適用してコンテンツを保持または削除する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 必要なものを保持し、必要でないものを削除するためにラベルを自動的に適用できるように、保持ラベルと自動ラベル付けポリシーを作成します。
ms.openlocfilehash: a79e7a96cc02957b0bac4dba31b24c5727f0483b
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751182"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a>保持ラベルを自動的に適用してコンテンツを保持または削除する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

> [!NOTE]
> このシナリオは、[規制レコード](records-management.md#records)についてはサポートしていません。

[保持ラベル](retention.md)の最も強力な機能の 1 つは、指定した条件に一致したコンテンツに自動的にラベルを適用することです。 この場合、組織内のユーザーが保持ラベルを適用する必要はありません。 Microsoft 365 が行います。
  
自動適用アイテム保持ラベルが強力な機能である理由は次のとおりです。
  
- ユーザーのトレーニングは、一部の分類方法についてのみ必要。
    
- ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。
    
- ユーザーはデータ ガバナンス ポリシーについて把握する必要がなくなるので、仕事に集中できる。
    
コンテンツに機密情報、キーワード、検索可能なプロパティ、または[トレーニング可能な分類子](classifier-get-started-with.md)のマッチが含まれている場合、保持ラベルをコンテンツに自動的に適用できます。

> [!TIP]
> プレビューでは、検索可能なプロパティを使用して [Teams 会議のレコーディング](#microsoft-teams-meeting-recordings)を特定できるようになりました。

保持ラベルを自動的に適用するプロセスは、次の条件に基づいています。

![自動適用ラベルの役割とタスクの図](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

次の手順を 2 つの管理手順に使用します。

> [!NOTE]
> 自動ポリシーで、保持ラベルを自動的に適用するための条件によりサービス側でのラベル付けを使用します。 次の操作を行うときにラベル ポリシーを使用して保持ラベルを自動的に適用することもできます。 
>
> - SharePoint Syntex のドキュメント理解モデルに保持ラベルを適用する
> - SharePoint と Outlook の既定の保持ラベルを適用する
>- Outlook ルールを使用してメールに保持ラベルを適用する
>
> これらのシナリオについては、[アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)を参照してください。

## <a name="before-you-begin"></a>はじめに

組織のグローバル管理者には、保持ラベルとそれらのポリシーを作成および編集できる完全な権限があります。 グローバル管理者としてサインインしていない場合は、「[アイテム保持ポリシーと保持ラベルを作成して管理するために必要なアクセス許可](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)」を参照してください。

## <a name="how-to-auto-apply-a-retention-label"></a>保持ラベルを自動適用する方法

まず、保持ラベルを作成します。 次に、そのラベルを適用する自動ポリシーを作成します。 保持ラベルを既に作成してある場合は、[自動ポリシーの作成](#step-2-create-an-auto-apply-policy)に進んでください。

ナビゲーション手順は、[レコード管理](records-management.md)を使用しているかどうかによって異なります。 両方のシナリオの手順を説明します。

### <a name="step-1-create-a-retention-label"></a>手順 1: 保持ラベルを作成する

1. [Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、次のいずれかの場所に移動します。
    
    - レコード管理を使用している場合:
        - [**ソリューション**] > [**レコード管理**] > [**ファイル計画**] タブ > [**+ラベルを作成**] > [**保持ラベル**]
        
    - レコード管理を使用していない場合:
       - [**ソリューション**] > [**情報ガバナンス**] > [**ラベル**] タブ > + [**ラベルを作成**]
    
    すぐにオプションが表示されませんか? 最初に [**すべて表示**] を選択します。 

2. ウィザードでプロンプトに従います。 レコード管理を使用している場合:
    
    - ファイル計画記述子については、「[Use file plan to manage retention labels (ファイル計画を使用して保持ラベルを管理する)](file-plan-manager.md)」を参照してください。
    
    - 保持ラベルを使用してレコードを宣言するには、**アイテムをレコードとしてマーク**、または **アイテムを規制レコードとしてマーク** を選択します。 詳細については、「 [保持ラベルを構成してレコードを宣言する](declare-records.md#configuring-retention-labels-to-declare-records)」を参照してください。

3. ラベルを作成し、ラベルの公開、ラベルの自動適用、またはラベルの保存のオプションが表示されたら、[**このラベルを特定の種類のコンテンツに自動適用する**] を選択してから、[**完了**] を選択すると、次の手順の手順 2 に直接進む自動ラベル作成ウィザードが起動します。

既存のラベルを編集するには、そのラベルを選択してから [**ラベルの編集**] オプションを選択し、手順 2 からラベルの説明や [有効な設定](#updating-retention-labels-and-their-policies)を変更するための保持の編集ウィザードを開始します。

### <a name="step-2-create-an-auto-apply-policy"></a>手順 2: 自動適用ポリシーを作成する

自動適用ポリシーを作成する場合、指定した条件に基づいてコンテンツに自動的に適用する保持ラベルを選択します。

1. [Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、次のいずれかの場所に移動します。
    
    - レコード管理を使用している場合: **情報ガバナンス**:
        - [**ソリューション**] > [**レコード管理**] > [**ラベル ポリシー**] タブ > [**自動適用ラベル**]
    
    - レコード管理を使用していない場合:
        - [**ソリューション**] > [**情報ガバナンス**] > [**ラベル ポリシー**] タブ > [**自動適用ラベル**]
    
    すぐにオプションが表示されませんか? 最初に [**すべて表示**] を選択します。 

2. 自動ラベル作成ウィザードの指示に従います。
    
    保持ラベルを自動的に適用する条件の構成については、このページの「[自動適用の保持ラベルの条件の構成](#configuring-conditions-for-auto-apply-retention-labels)」セクションをご覧ください。
    
    保持ラベルでサポートされている場所については、「[保持ラベルと場所](retention.md#retention-label-policies-and-locations)」のセクションをご覧ください。

既存の自動適用ポリシーを編集するには、ポリシーを選択して、アイテム保持ポリシーの編集ウィザードを起動します。このウィザードでは、手順 2 で選択した保持ラベルと[有効な設定](#updating-retention-labels-and-their-policies)を変更できます。

自動適用ラベル ポリシーを使用してコンテンツにラベル付けをした後で、コンテンツやポリシーを変更したり、新しい自動適用ラベル ポリシーを使用したりして、適用されているラベルを自動的に削除したり変更したりすることはできません。 詳細については、「[一度に 1 つの保持ラベルのみ](retention.md#only-one-retention-label-at-a-time)」を参照してください。

### <a name="configuring-conditions-for-auto-apply-retention-labels"></a>自動適用の保持ラベルの条件の構成

コンテンツに次の内容が含まれている場合は、保持ラベルを自動的にコンテンツに適用できます。

- [特定の種類の機密情報](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [作成したクエリに一致する特定のキーワードまたは検索可能なプロパティ](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [トレーニング可能な分類子の一致](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a>特定の種類の機密情報によるコンテンツへのラベルの自動適用

機密情報用に自動適用の保持ラベル ポリシーを作成するときに、データ損失防止 (DLP) ポリシーを作成するときと同じポリシー テンプレートの一覧が表示されます。 各テンプレートは、特定の種類の機密情報を見つけるように事前に設定されています。 たとえば、ここに示されているテンプレートは、**プライバシー** カテゴリからの U.S. ITIN、SSN、パスポート番号、および **U.S 個人を特定できる情報 (PII) データ テンプレート** を検索します。

![機密情報の種類によるポリシー テンプレート](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

機密情報の種類の詳細については、「[機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)」を参照してください。

ポリシー テンプレートを選択すると、機密情報の任意の種類を追加または削除できます。また、インスタンス数や一致精度を変更できます。 次に示すスクリーンショットの例では、保持ラベルは次の場合にのみ自動的に適用されます。
  
- 検出される機密情報の種類には、一致精度 (または信頼度) が少なくとも 75 はあります。 機密情報の種類の多くは、複数のパターンで定義されています。高い一致精度が指定されたパターンにはより多くの証拠 (キーワード、日付、アドレスなど) が見つかることが必要とされるのに対して、低い一致精度が指定されたパターンでは必要とされる証拠は少なくなります。 **最小** 一致精度が低いほど、コンテンツは条件に一致しやすくなります。

- 3 種類の機密情報のうち、1 から 9 個のインスタンスを含むコンテンツ。 **宛先** 値を削除すると、値は **任意** に変更されます。

これらのオプションの詳細については、DLP のドキュメント「[一致の難易度を上下するためにルールを調整する](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)」にある次のガイダンスを参照してください。
    
![機密情報の種類を識別するためのオプション](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)

機密情報の種類を使用して保持ラベルの自動適用を検討する場合:

- 新しいアイテムや変更されたアイテムには、自動的にラベルを付けることができます。

#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a>キーワードまたは検索可能なプロパティによるコンテンツへの自動適用ラベル

特定の単語、フレーズ、または検索可能なプロパティの値を含むクエリを使用して、コンテンツにラベルを自動で適用できます。AND、OR、NOT などの検索演算子を使用してクエリを絞り込むことができます。

![クエリ エディター](../media/new-retention-query-editor.png)

キーワード クエリ言語 (KQL) 構文の詳細については、「[キーワード クエリ言語 (KQL) 構文のリファレンス](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)」をご覧ください。

クエリ ベースの自動適用ポリシーは、電子情報開示コンテンツの検索と同じ検索インデックスを使用してコンテンツを識別します。 使用できる検索可能なプロパティの詳細については、「[キーワード クエリとコンテンツ検索の検索条件](keyword-queries-and-search-conditions.md)」を参照してください。

キーワードまたは検索可能なプロパティを使用して保持ラベルを自動適用する際の考慮事項:

- 新規、変更、および既存のアイテムには、SharePoint、OneDrive、および Exchange の自動ラベルが付けられます。

- SharePoint の場合、クロールされたプロパティとカスタム プロパティは、これらの KQL クエリではサポートされていないため、事前定義された管理プロパティのみを使用する必要があります。 ただし、既定で絞り込み条件として有効になっている管理プロパティ (RefinableDate00-19、RefinableString00-99、RefinableInt00-49、RefinableDecimals00-09、および RefinableDouble00-09) を使用して、テナント レベルでマッピングを使用できます。 詳細については、「[クロールされたプロパティと管理プロパティの概要 (SharePoint Server)](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)」を参照してください。手順については、「[新しい管理プロパティの作成](https://docs.microsoft.com/sharepoint/manage-search-schema#create-a-new-managed-property)」を参照してください。

- カスタム プロパティを絞り込み条件プロパティの 1 つにマップする場合は、24 時間待ってから、保持ラベルの KQL クエリで使用してください。

- SharePoint の管理プロパティはエイリアスを使用して名前を変更できますが、ラベルの KQL クエリにはこれらを使用しないでください。 「RefinableString01」のように、管理プロパティの実際の名前を常に指定します。

- スペースまたは特殊文字を含む値を検索するには、二重引用符 (`subject:"Financial Statements"`) で語句を囲みます。例: `" "`

- *Path* の代わりに *DocumentLink* プロパティを使用して、URL に基​​づいてアイテムを照合します。 

- 後方一致ワイルドカード検索 (`*cat` など) や部分文字列ワイルドカード検索 (`*cat*` など) はサポートされていません。 ただし、プレフィックス ワイルドカード検索 (`cat*` など) はサポートされています。

- 部分的にインデックス付けされたアイテムは、想定するアイテムにラベルを付けない、または NOT 演算子を使用するときにラベル付けから除外されると想定するアイテムにラベルを付ける責任があることに注意してください。 詳細については、「[コンテンツ検索で部分的にインデックスが作成されたアイテム](partially-indexed-items-in-content-search.md)」を参照してください。


クエリの例:

| Workload | 例 |
|:-----|:-----|
|Exchange   | `subject:"Financial Statements"` |
|Exchange   | `recipients:garthf@contoso.com` |
|SharePoint | `contenttype:document` |
|SharePoint | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:document`|
|Exchange または SharePoint | `"customer information" OR "private"`|

より複雑な例:

次の SharePoint のクエリは、Word 文書または Excel スプレッドシートが、キーワード **password**、**passwords**、または **pw** を含む場合に、それらを識別します。

```
(password OR passwords OR pw) AND (filetype:doc* OR filetype:xls*)
```

次の Exchange のクエリは、単語 **nda** またはフレーズ **秘密保持契約書** を含む Word 文書または PDF を、それらの文書がメールに添付されている場合に識別します。

```
(nda OR "non disclosure agreement") AND (attachmentnames:.doc* OR attachmentnames:.pdf)
```

次の SharePoint のクエリは、クレジット カード番号を含むドキュメントを識別します。 

```
sensitivetype:"credit card number"
```

次のクエリには、合法的なコンテンツを含むドキュメントまたはメールを識別するのに役立ついくつかの一般的なキーワードが含まれています。

```
ACP OR (Attorney Client Privilege*) OR (AC Privilege)
```

次のクエリには、人事用のドキュメントまたはメールを識別するのに役立つ一般的なキーワードが含まれています。 

```
(resume AND staff AND employee AND salary AND recruitment AND candidate)
```

この最後の例では、キーワード間に常に演算子を含めるというベスト プラクティスを使用していることに注意してください。 キーワード (または 2 つの property:value 式) 間のスペースは、AND を使用することと同じになります。 演算子を常に追加することで、このクエリの例では、キーワードを含むコンテンツではなく、これらのキーワードをすべて含むコンテンツのみを識別することが容易になります。 キーワードのいずれかを含むコンテンツを識別する場合は、AND の代わりに OR を指定します。 この例が示すように、常に演算子を指定すると、クエリを正しく解釈するのが容易になります。 

##### <a name="microsoft-teams-meeting-recordings"></a>Microsoft Teams 会議のレコーディング

> [!NOTE]
> Teams 会議のレコーディングを保持したり削除したりする機能はプレビュー段階にあり、レコーディングを OneDrive や SharePoint に保存する前には機能しません。 詳細については、「[OneDrive for Business と SharePoint または Stream を使用して会議の記録を行う](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change)」を参照してください。

ユーザーの OneDrive アカウントまたは SharePoint に保存されている Microsoft Teams 会議のレコーディングを特定するには、**キーワード クエリ エディター** で次のように指定します。

``` 
ProgID:Media AND ProgID:Meeting
```

ほとんどの場合、会議のレコーディングは OneDrive に保存されます。 ただしチャネル会議については、SharePoint に保存されます。


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a>トレーニング可能な分類子を使用して、ラベルをコンテンツに自動的に適用する

トレーニング可能な分類子のオプションを選択すると、組み込み分類子またはカスタム分類子のいずれかを選択できます。 組み込み分類子には、**履歴書**、**ソース コード**、**個人を標的にしたハラスメント**、**冒とく**、および **脅威** が含まれます。

![トレーニング可能な分類子の選択](../media/retention-label-classifers.png)

> [!CAUTION]
> 組み込みの [**不快な言葉**] は、誤検知の数が多いため、廃止予定です。 この組み込み分類子を使用しないでください。現在使用している場合は、ビジネス プロセスを移動する必要があります。 代わりに、[**個人を標的にしたハラスメント**]、[**冒涜的表現**]、および [**脅威**] の組み込み分類子を使用することをお勧めします。

このオプションを使用してラベルを自動的に適用するには、SharePoint サイトとメールボックスには少なくとも 10 MB のデータが必要です。

トレーニング可能な分類子の詳細については、「[トレーニング可能な分類子の詳細 (プレビュー)](classifier-learn-about.md)」を参照してください。

> [!TIP]
> Exchange でトレーニング可能な分類子を使用している場合は、最近リリースされた「[コンテンツ エクスプローラーで分類子を再トレーニングする方法 (プレビュー)](classifier-how-to-retrain-content-explorer.md)」を参照してください。

トレーニング可能な分類子を使用して保持ラベルの自動適用を検討する場合:

- 新規アイテムと変更されたアイテム、および過去 6 か月の既存のアイテムにはラベルを付けることができます。

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a>保持ラベルが有効になるまでの所要時間

保持ラベルを自動適用する場合、条件に一致する既存のコンテンツすべてに保持ラベルが適用されるまでに最大 7 日間かかります。
  
![自動適用ラベルが有効になるタイミングの図](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)

予期されるラベルが 7 日経っても表示されない場合は、コンプライアンス センターの **[ラベル ポリシー]** ページから選択して、自動適用ポリシーの **状態** を確認します。 **オフ (エラー)** の状態が表示され、場所の詳細に、ポリシーの展開 (SharePoint の場合) またはポリシーの再展開 (OneDrive の場合) に予想よりも時間がかかっているというメッセージが表示される場合は、[Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell コマンドを実行して、ポリシーの配布を再試行してください:

1. [セキュリティ/コンプライアンス センターの PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。

2. 次のコマンドを実行します。
    
    ``` PowerShell
    Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
   ```

## <a name="updating-retention-labels-and-their-policies"></a>保持ラベルとそのポリシーの更新

保持ラベルや自動適用ポリシーを編集すると、その保持ラベルが既にコンテンツに適用されている場合、新しく識別されるコンテンツに加えて、そのコンテンツにも更新された設定が自動的に適用されます。

ラベルやポリシーを作成して保存した後には変更できない設定があり、それらは以下のものを含みます。
- 保持ラベル名とアイテム保持ポリシー名および保持期間を除く保持設定。 ただし、アイテムにラベルが付けられた時期に基づいて保持期間が設定されている場合、保持期間を変更することはできません。
- アイテムをレコードとしてマークするオプション。

## <a name="locking-the-policy-to-prevent-changes"></a>変更を防止するためにポリシーをロックする

ポリシーをオフにしたり、ポリシーを削除したり、制限を緩和したりすることができないようにする必要がある場合は、「[保管ロックを使用して、アイテム保持ポリシーと保持ラベル ポリシーへの変更を制限する](retention-preservation-lock.md)」を参照してください。

## <a name="next-steps"></a>次の手順

[保持ラベルを使用して、SharePoint に保存されているドキュメントのライフサイクルを管理する](auto-apply-retention-labels-scenario.md)を参照してください。例として、SharePoint の管理プロパティで、自動適用ポリシー保持ラベルを使用し、保持期間を開始するために、イベントベースの保持を使用するというシナリオがあります。
