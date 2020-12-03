---
title: コンテンツを自動的に保持または削除するアイテム保持ポリシーと保持ラベルの詳細
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
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 必要なコンテンツを保持し不要なコンテンツを削除するのに役立つ、アイテム保持ポリシーと保持ラベルについて説明します。
ms.openlocfilehash: e2833d966fb8a1fcc15cbeb02b781d9c0325b9c1
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519378"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベルの詳細

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

ほとんどの組織では、電子メール、ドキュメント、インスタント メッセージなどのデータの量と複雑さが日々増しています。次の必要性から、これらの情報を効果的に管理することが重要です。
  
- **最小限の期間コンテンツを保持することを要求する業界の規制や内部ポリシーを積極的に遵守する**: たとえば、米国企業改革法により、特定の種類のコンテンツを 7 年間保持することが求められる場合があります。 

- **訴訟やセキュリティ違反が発生した場合にリスクを軽減する**: このために、保持する必要がなくなった古いコンテンツは完全に削除します。 
    
- **組織内での効率的な知識の共有と迅速な対応に役立てる**: このために、ユーザーは現時点で関連性のあるコンテンツのみを対象に作業するようにします。 
    
構成する保持設定は、これらすべての目標を達成するのに役立ちます。一般に、コンテンツの管理に求められる操作は次の 2 つです。
  
- **コンテンツの保持**: 保持期間が満了するまではコンテンツの完全な削除ができないようにします。 
    
- **コンテンツの削除**: 保持期間の満了時点でコンテンツを完全に削除します。 
    

これら 2 つの保持アクションを使用して、次の結果が得られるように保持設定を構成できます。

- 保持のみ: コンテンツを無期限または指定した期間保持します。
- 削除のみ: 指定した期間の後にコンテンツを削除します。
- 保持してから削除: 指定した期間、コンテンツを保持してから削除します。

これらの保持設定は所定の場所にあるコンテンツに作用し、コンプライアンス上の理由でコンテンツを保持する必要がある場合でも、追加のストレージを作成して構成するための追加のオーバーヘッドを節約できます。また、このデータをコピーして同期するために、カスタマイズしたプロセスを実装する必要もありません。

## <a name="how-retention-settings-work-with-content-in-place"></a>保持設定が所定の場所にあるコンテンツに作用するしくみ

コンテンツに保持設定が割り当てられるとき、そのコンテンツは元の場所にそのまま残ります。このため、ユーザーは何事もなかったかのように、ドキュメントやメールで作業を続けることができます。ただし、アイテム保持ポリシーに含まれているコンテンツをユーザーが編集または削除すると、そのコンテンツのコピーが自動的に保持されます。
  
- SharePoint および OneDrive サイトの場合: コピーは、**アイテム保管** ライブラリに保持されます。

- Exchange メールボックスの場合: コピーは、**[回復可能なアイテム]** フォルダーに保持されます。 

- Teams と Yammer のメッセージの場合: **SubstrateHolds** という名前の隠しフォルダーに Exchange の **[回復可能なアイテム]** フォルダー内のサブフォルダーとして保持されます。

> [!NOTE]
> アイテム保管ライブラリは、サイトのストレージ クォータから除外されていないストレージを消費します。SharePoint グループや Microsoft 365 グループに対して保持設定を使用する場合は、ストレージを増やすことが必要な場合があります。
> 
これらの安全な場所や保持されたコンテンツは、ほとんどのユーザーに表示されることはありません。ほとんどの場合、ユーザーは自分のコンテンツが保持設定の対象であることを知る必要さえありません。

保持設定がさまざまなワークロードに対してどのように機能するかの詳細については、次の記事を参照してください。

- [SharePoint と OneDrive の保持の詳細](retention-policies-sharepoint.md)
- [Microsoft Teams の保持の詳細](retention-policies-teams.md)
- [Yammerの保持の詳細](retention-policies-yammer.md)
- [Exchange の保持の詳細](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベル

アイテム保持ポリシーと保持ラベルの両方を使用して、保持設定をコンテンツに割り当てることができます。 

サイト レベルやメールボックス レベルで同一の保持設定を割り当てるには、アイテム保持ポリシーを使用します。一方、アイテム レベル (フォルダー、ドキュメント、メール) で保持設定を割り当てるには、保持ラベルを使用します。

たとえば、SharePoint サイト内のすべてのドキュメントを 5 年間保持する必要がある場合は、同じ保持ラベルをサイト内のすべてのドキュメントに適用するよりも、アイテム保持ポリシーを使用する方が効率的です。一方、サイト内の一部のドキュメントは 5 年間保持し、一部は 10 年間保持する必要がある場合、アイテム保持ポリシーではこれを行うことができません。アイテム レベルで保持設定を指定する必要がある場合は、保持ラベルを使用します。 

アイテム保持ポリシーとは異なり、保持ラベルによる保持設定は、コンテンツが Microsoft 365 テナントの別の場所に移動された場合でもコンテンツに適用されたままになります。また、保持ラベルには、アイテム保持ポリシーではサポートされていない次の機能があります。 
 
- コンテンツの保持期間や最終更新日以外に、コンテンツにラベルが付けられた時点やイベントに基づいて保持期間を開始するオプション。

- [トレーニング可能な分類子](classifier-learn-about.md)を使用して、ラベル付けするコンテンツを識別する。

- SharePoint ドキュメントに既定のラベルを適用する。

- コンテンツを完全に削除する前にコンテンツを確認する[廃棄確認](disposition-reviews.md) のサポート。

- ラベル設定の一部として、コンテンツを [[レコード]](records-management.md#records) としてマークし、保持期間の終了時にコンテンツが削除されるときに [廃棄の証明](disposition.md#disposition-of-records) を常に取得する。

### <a name="retention-policies"></a>アイテム保持ポリシー

アイテム保持ポリシーは、次の場所に適用できます。
- Exchange メール
- SharePoint サイト
- OneDrive アカウント
- Microsoft 365 グループ
- Skype for Business
- Exchange パブリック フォルダー
- チームのチャネル メッセージ
- Teams のチャット
- Yammer コミュニティのメッセージ
- Yammer の個人用メッセージ

複数の場所にも特定の場所やユーザーにも、1 つのポリシーを非常に効率的に適用できます。

保持期間の開始時に、コンテンツがいつ作成されたか、またはファイルと、コンテンツが最後に変更された SharePoint、OneDrive、Microsoft 365 グループの場所でのみサポートされるかを選択することができます。

アイテムは、アイテム保持ポリシーで指定されたコンテナーからアイテム保持設定を継承します。ポリシーがコンテンツを保持するように構成されているときに、それらがそのコンテナーの外部に移動された場合、そのアイテムのコピーがワークロードのセキュリティで保護された場所に保持されます。ただし、保持設定は、コンテンツとともに新しい場所に移動することはありません。必要な場合は、アイテム保持ポリシーの代わりに保持ラベルを使用します。

### <a name="retention-labels"></a>保持ラベル

保持ラベルは、異なる保持設定を必要とするさまざまな種類のコンテンツに対して使用できます。例:
  
- 最低限の期間、保持する必要のある納税申告書。 
    
- 特定の期間が経過した後、完全に削除する必要があるプレス資料。 
    
- 特定の期間保持した後に完全に削除する必要がある競合企業のリサーチ。 
    
- 編集も削除もできないように、レコードとしてマークする必要がある就労ビザ。 
    
いずれの場合も、保持ラベルを使用すると、アイテム レベル (ドキュメントやメール) でガバナンス制御用の保持設定を適用できます。
  
保持ラベルを使用すると、次のことができます。
  
- Outlook、Outlook on the web、OneDrive、SharePoint、Microsoft 365 グループのコンテンツに、**組織内のユーザーが保持ラベルを手動で適用** できるようにします。多くの場合、コンテンツの種類を最も良く理解しているのはそれを扱っているユーザーです。そこでユーザーにコンテンツを分類し、適切なアイテム保持設定を適用してもらいます。 
    
- コンテンツに次のものが含まれている場合など、特定の条件に一致するときには、**保持ラベルをコンテンツに自動的に適用** できます。 
    - 特定の種類の機密情報。
    - 作成したクエリに一致する特定のキーワード。
    - トレーニング可能な分類子のパターン マッチ。

- **コンテンツにラベルが付けられた時点から保持期間を開始する** SharePoint サイトや OneDrive アカウントのドキュメント、および予定表アイテム以外のメール アイテムに対してこの操作を行えます。この構成の保持ラベルを予定表アイテムに適用すると、保持期間はアイテムが送信された時点から開始されます。

- 従業員の退職や契約の期限切れなど、**イベントの発生時に保持期間を開始する**。

- SharePoint の **ドキュメント ライブラリ、フォルダー、またはドキュメント セットに既定の保持ラベルを適用** することにより、この場所に保存するすべてのドキュメントに既定の保持ラベルが継承されるようになります。

さらに、保持ラベルは、Microsoft 365 アプリとサービス全体でのメールとドキュメントの[レコード管理](records-management.md)をサポートします。保持ラベルを使用して、アイテムをレコードとしてマークできます。この問題が発生し、コンテンツが Microsoft 365 に残っている場合は、このラベルで規制上の理由から必要になる可能性があるコンテンツがさらに制限されます。詳細については、「[許可またはブロックされているアクションの制限を比較する](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)」を参照してください。

保持ラベルは、[秘密度ラベル](sensitivity-labels.md)とは異なり、コンテンツが Microsoft 365 以外の場所に移動した場合は保持されません。

テナントでサポートされる保持ラベルの数に制限はありません。ただし、10,000 がテナントでサポートされるポリシーの最大数であり、これらには、ラベルを適用するポリシー (保持ラベル ポリシーと自動適用アイテム保持ポリシー) とアイテム保持ポリシーが含まれます。

#### <a name="classifying-content-without-applying-any-actions"></a>アクションを適用しないでコンテンツを分類する

保持ラベルの主な目的はコンテンツを保持または削除することですが、保持やその他のアクションを有効にしないで保持ラベルを使用することもできます。この場合、テキスト ラベルとしてのみ保持ラベルを使用し、他のアクションは適用しません。
  
たとえば、アクションを含まない "後で確認" という名前の保持ラベルを作成して適用し、後からそのコンテンツを見つけるためにそのラベルを使用できます。
  
![分類専用のラベル設定](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>DLP ポリシーで保持ラベルを条件として使用する

SharePoint のドキュメントのデータ損失防止 (DLP) ポリシーの条件として、保持ラベルを指定することができます。たとえば、指定された保持ラベルがドキュメントに適用されている場合はそのドキュメントが組織外に共有されないように、DLP ポリシーを構成できます。

詳細については、「[DLP ポリシーでの条件としての保持ラベルの使用](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)」を参照してください。

#### <a name="retention-labels-and-policies-that-apply-them"></a>保持ラベルと保持ラベルを適用するポリシー

保持ラベルは、独立した、再利用可能な文書パーツです。ラベル ポリシーの主な目的は、保持ラベルのセットをグループ化し、それらのラベルを表示する場所を指定することです。そうすることにより、管理者とユーザーはラベルをそれらの場所のコンテンツに適用できます。
  
![ラベル、ラベル ポリシー、および場所の図](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
保持ラベルを発行すると、それらは保持ラベル ポリシーに含まれます。このポリシーを使用することで、管理者やユーザーは次の中から選択して保持ラベルを使用できます。

- 1 つの保持ラベルを複数の保持ラベル ポリシーに含めることができます。

- 保持ラベル ポリシーは保持ラベルを発行する場所を指定します。

- 1 つの場所を複数の保持ラベル ポリシーに含めることもできます。

保持ラベル ポリシーに加えて、1 つ以上の自動適用ポリシーを作成して、それぞれに保持ラベルを 1 つ指定することもできます。このポリシーを使うと、ポリシーで指定した条件が満たされた場合に、保持ラベルが自動的に適用されます。 

#### <a name="retention-label-policies-and-locations"></a>保持ラベルのポリシーと場所

保持ラベルの内容に応じて、多様な種類の保持ラベルをさまざまな場所に発行できます。
  
| 保持ラベルの種類 | ラベル ポリシーの適用先 |
|:-----|:-----|
|管理者とエンド ユーザーに発行されたラベル  <br/> |Exchange、SharePoint、OneDrive、Microsoft 365 グループ  <br/> |
|機密情報の種類またはトレーニング可能な分類子に基づいて自動適用されたラベル  <br/> |Exchange (すべてのメールボックスのみ)、SharePoint、OneDrive  <br/> |
|クエリに基づいて自動適用されたラベル  <br/> |Exchange、SharePoint、OneDrive、Microsoft 365 グループ  <br/> |
   
Exchange では、自動適用の保持ラベルは、新しく送信されたメッセージ (送信中のデータ) にのみ適用され、現在メールボックスにあるすべてのアイテム (保存データ) には適用されません。また、機密情報の種類やトレーニング可能な分類子向けの自動適用の保持ラベルは、すべてのメールボックスにのみ適用されます。ただし、特定のメールボックスを選択することはできません。
  
Exchange パブリックフォルダー、Skype、Teams、Yammer メッセージは保持ラベルをサポートしていません。これらの場所のコンテンツを保持または削除するには、代わりにアイテム保持ポリシーを使用します。

#### <a name="only-one-retention-label-at-a-time"></a>一度に 1 つの保持ラベルのみ

メールやドキュメントに一度に適用できる保持ラベルは、1 つのみです。 保持ラベルは、エンド ユーザーや管理者が[手動](create-apply-retention-labels.md#manually-apply-retention-labels)で適用することも、次のいずれかの方法を使用して自動で適用することもできます。

- [自動適用ラベル ポリシー](apply-retention-labels-automatically.md)
- [SharePoint Syntex のドキュメント理解モデル](https://docs.microsoft.com/microsoft-365/contentunderstanding/apply-a-retention-label-to-a-model)
- [Outlook](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder) または [SharePoint の既定のラベル](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)
- [Outlook のルール](create-apply-retention-labels.md#automatically-applying-a-retention-label-to-email-by-using-rules)

標準的な保持ラベルの場合 (アイテムを[レコードや規制レコード](records-management.md#records)としてマークしません)。

- 管理者とエンド ユーザーは、コンテンツに適用されている既存の保持ラベルを手動で変更または削除できます。 

- コンテンツに既に保持ラベルが適用されている場合、既存のラベルが自動的に削除されたり、別の保持ラベルに置き換えられたりすることはありません。ただし、例外が 1 つあり、既存のラベルが既定のラベルとして適用されている場合です。
    
    既定のラベルを使用して適用した場合のラベルの動作については、以下を参照してください。
    - SharePoint の既定のラベル: [SharePoint の既定のラベルを使用した場合のラベルの動作](create-apply-retention-labels.md#label-behavior-when-you-use-a-default-label-for-sharepoint)
    - Outlook の既定のラベル: [Outlook フォルダーに既定の保持ラベルを適用する](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)

- 保持ラベルを適用できる自動適用ラベル ポリシーが複数あり、コンテンツが複数のポリシーの条件を満たしている場合、(作成日を基準にして) 最も古い自動適用ラベル ポリシーの保持ラベルが適用されます。

保持ラベルがアイテムをレコードまたは規制レコードとしてマークしている場合、これらのラベルが自動的に変更されることはありません。 コンテナーの管理者のみが、アイテムをレコードとしてマークする保持ラベルを手動で変更または削除することができますが、規制レコードについてはできません。 詳細については、「[許可またはブロックされているアクションの制限を比較する](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)」を参照してください。

#### <a name="monitoring-retention-labels"></a>保持ラベルの監視

Microsoft 365 コンプライアンス センターから、**データ分類** > **概要** を使用して、保持ラベルがテナントでどのように使用されているかを監視し、ラベル付きアイテムの場所を特定します。 重要な前提条件を含む詳細については、「[データを理解する - データ分類の概要](data-classification-overview.md)」を参照してください。

詳細については、[コンテンツ エクスプローラー](data-classification-content-explorer.md) と [アクティビティ エクスプローラー](data-classification-activity-explorer.md) を使用します。

> [!TIP]
>トレーニング可能な分類子や機密情報タイプなど、他のデータ分類インサイトのいくつかを使用することを検討して、レコードとして保持または削除する必要がある、またはレコードとして管理する必要があるコンテンツを特定できるようにします。

Office 365 セキュリティ/コンプライアンス センターには、**情報ガバナンス** > **ダッシュボード** の保持ラベルと同等の概要情報と、**情報ガバナンス** > **ラベル アクティビティ エクスプローラー** の詳細情報があります。 この古い管理センターから保持ラベルを監視する方法の詳細については、次のドキュメントを参照してください:
- [データ ガバナンスのレポートを表示する](view-the-data-governance-reports.md)
- [ラベル分析によるラベル使用状況を表示する](label-analytics.md)
- [ドキュメントのラベルのアクティビティを表示する](view-label-activity-for-documents.md)

#### <a name="using-content-search-to-find-all-content-with-a-specific-retention-label"></a>コンテンツ検索を使用した特定の保持ラベルを持つすべてのコンテンツの検索

保持ラベルがユーザーによって、または自動適用されてコンテンツに適用された後、コンテンツ検索を使用して、特定の保持ラベルが適用されているすべてのアイテムを検索できます。

コンテンツ検索を作成するとき、**保持 ラベル** の条件を選択し、完全な保持ラベル名を入力するか、ラベル名の一部を入力してワイルドカードを使用します。 詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。
  
![保持ラベルの条件](../media/retention-label-condition.png)


## <a name="compare-capabilities-for-retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベルの機能比較

次の表は、アイテム保持ポリシーと保持ラベルのどちらを使用するかを、機能に基づいて決定するのに役立ちます。

|機能|アイテム保持ポリシー |保持ラベル|
|:-----|:-----|:-----|:-----|
|保持してから削除、保持のみ、削除のみを指定できる保持設定 |はい |はい |
|サポートされるワークロード: <br />- Exchange <br />- SharePoint <br />- OneDrive <br />- Microsoft 365 グループ <br />- Skype for Business <br />- Teams<br />- Yammer|<br /> はい <br /> はい <br /> はい <br /> はい <br /> はい <br /> はい <br /> はい | <br /> はい (パブリック フォルダーを除く) <br /> はい <br /> はい <br /> はい <br /> いいえ <br /> いいえ <br /> いいえ |
|保持の自動適用 | はい | はい |
|条件に基づいて適用される保持 <br /> - 機密情報の種類、KQL クエリ、トレーニング可能な分類子| 不要 | はい |
|保持の手動適用 | いいえ | はい |
|エンド ユーザー向け UI の存在 | いいえ | はい |
|コンテンツが移動された場合の保持 | いいえ | はい (Microsoft 365 テナント内で) |
|レコードとしてアイテムを宣言| 不要 | はい |
|ラベル作成時またはイベント発生時に保持期間を開始 | 不要 | はい |
|処理確認 | いいえ| はい |
|廃棄の証明 (最大 7 年間) | いいえ |はい (アイテムがレコードとして宣言されている場合)|
|管理者アクティビティを監査する| はい | はい|
|保持対象のアイテムの特定 <br /> - コンテンツ検索 <br /> - データ分類ページ、コンテンツ エクスプローラー、アクティビティ エクスプローラー | <br /> 不要 <br /> いいえ | <br /> はい <br /> はい|

アイテム保持ポリシーと保持ラベルの両方を補完的な保持方法として使用することができます。 例:

1. 最終更新日から 5 年後にコンテンツを自動的に削除するアイテム保持ポリシーを作成して構成し、すべての OneDrive アカウントにそのポリシーを適用します。

2. コンテンツを無期限に保持する保持ラベルを作成して構成し、すべての OneDrive アカウントに対して発行するラベル ポリシーにこのラベルを追加します。 5 年間更新されない場合でも自動削除されないようにする必要のある特定のドキュメントに対して、このラベルを手動で適用する方法をユーザーに説明します。

アイテム保持ポリシーと保持ラベルを組み合わせて使用する方法、および組み合わせて使用した場合の結果の確認方法の詳細については、保持の原則と優先順位について説明している次のセクションを参照してください。

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>保持の原則と優先順位

コンテンツにアイテム保持ポリシーや保持ラベルがいくつか適用されており、それぞれのポリシーやラベルに異なるアクション (保持、削除、保持してから削除) や保持期間が指定されている場合があります。 優先順位 

大まかに言えば、保持は削除より常に優先され、最長の保持期間が優先されます。 

とはいえ、組み合わせて使用する場合は他にも決定要因があります。結果を理解するため、次のフロー図を使用して説明します。この図の各レベルは、優先順位に従って上から下に配列されており、上位のレベルで結果が決定する場合は次のレベルには進みません。 そのレベルのルールで結果が決定しない場合のみ、フロー図の下位のレベルに進み、その保持設定の優先順位で結果を判断します。

![保持の原則の図](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
4 つのレベルについて説明します。
  
1. **削除よりも保持が優先されます。** 3 年後に Exchange メールを削除するように構成されているアイテム保持ポリシーがあり、加えて 5 年間 Exchange メールを保持してから削除するように構成されている別のアイテム保持ポリシーもあるとします。 作成後 3 年に達するコンテンツはすべて削除され、ユーザーのビューから非表示になりますが、コンテンツが完全に削除される 5 年に達するまで、[回復可能なアイテム] フォルダーに保持されます。 
2. **最長の保持期間が優先されます。** 期間の異なる複数の保持設定がコンテンツに対して指定されている場合、そのコンテンツは最長の保持期間が終了するまで保持されます。
    
3. **明示的に含める方が、暗黙的に含めるよりも優先されます。** これは、次のことを意味します。 
    
    1. Exchange メールや OneDrive ドキュメントなど、ユーザーが保持設定を含む保持ラベルをアイテムに手動で割り当てた場合は、サイト レベルまたはメールボックス レベルで割り当てられているアイテム保持ポリシーや、ドキュメント ライブラリに割り当てられている既定の保持ラベルよりも、手動で割り当てたラベルが優先されます。 たとえば、明示的な保持ラベルでは 10 年間コンテンツを保持するように構成され、サイトに割り当てられているアイテム保持ポリシーでは 5 年間のみコンテンツを保持するように構成されている場合、明示的な保持ラベルが優先されます。
    
    2. アイテム保持ポリシーに特定のユーザーのメールボックスまたは OneDrive のアカウントなどの特定の場所が含まれている場合、そのアイテム保持ポリシーは、すべてのユーザーのメールボックスまたは OneDrive のアカウントに適用されるが、そのユーザーのメールボックスを特に含まない別の保持ポリシーよりも優先されます。
    
4. **最短の削除期間が優先されます。** 同様に、保持期間なしでコンテンツを削除する複数の保持設定が指定されている場合、そのコンテンツは最短保持期間の終了時に削除されます。 

最後に、アイテム保持ポリシーや保持ラベルでは、電子情報開示のために保持しているコンテンツを完全に削除することはできません。 電子情報開示のための保持を解除すると、コンテンツは再びそのワークロードに対するセキュリティで保護された場所のクリーンアップ プロセスの対象になります。

## <a name="use-preservation-lock-to-restrict-changes-to-policies"></a>保管ロックを使用してポリシーへの変更を制限する

一部の組織は、米国証券取引委員会 (SEC) 規則 17a-4 など、規制機関によって定義された規則に準拠する必要があります。その場合、保持ポリシーをオンにした後、それをオフにしたり、制限を緩和したりすることはできません。 

保管ロックを使用すると、アイテム保持ポリシーまたは保持ラベル ポリシーがロックされ、管理者を含むいかなるユーザーも、ポリシーをオフにしたり、削除、またはその制限を緩和したりすることができなくなるため、組織はこのような規制要件を確実に満たすことができます。
  
アイテム保持ポリシーまたは保持ラベル ポリシーを作成した後に、PowerShell を使用して保管ロックを適用します。 詳細と手順については、「[保管ロックを使用して、アイテム保持ポリシーと保持ラベル ポリシーへの変更を制限する](retention-preservation-lock.md)」を参照してください。

## <a name="releasing-a-policy-for-retention"></a>保持に関するポリシーを解放する

保管ロックが適用されていない保持に関するポリシーの場合は、いつでもポリシーを削除できます。それにより、以前に適用された保持設定は事実上無効になります。 ポリシーを維持して、場所の状態をオフに変更することもできます。
 
これらの操作のいずれかを実行しても、[アイテム保管ライブラリ] に保持されている SharePoint や OneDrive のコンテンツについては、直ちに完全に削除されることはありません。 代わりに、不注意によるデータの損失を防ぐために、30 日間の猶予期間があります。そのポリシーのコンテンツの有効期限は、[アイテム保管ライブラリ] には表示されず、必要に応じてコンテンツを復元できます。 また、猶予期間中はこのコンテンツを手動で削除することはできません。

猶予期間中に場所の状態をオンに戻すことができ、そのポリシーのコンテンツは削除されません。

この SharePoint と OneDrive の 30 日の猶予期間は、Exchange の 30 日の保留期間に対応しています。 詳しくは、[メールボックスの管理についての詳細](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold) をご覧ください。。

## <a name="auditing-retention-configuration"></a>アイテム保持構成の監査

[監査が有効になっている](turn-audit-log-search-on-or-off.md) 場合、アイテム保持ポリシーと保持ラベルの管理者アクションは監査ログに保存されます。 たとえば、アイテム保持ポリシーまたはラベルを作成、構成、または削除すると、監査イベントが作成されます。 完全なリストについては、「[アイテム保持ポリシーと保持ラベルのアクティビティ](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)」を参照してください。

## <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベルの PowerShell コマンドレット

保持コマンドレットを使用するには、最初に [Office 365 セキュリティ/コンプライアンス センターの PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) に接続する必要があります。 次に、次のいずれかのコマンドレットを使用します。

- [Get-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)

- [New-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)

- [Remove-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)

- [Set-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)

- [Enable-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)

- [Get-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)

- [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)

- [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)

- [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)

- [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)

- [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)

- [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)

- [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)

- [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)

## <a name="when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds"></a>アイテム保持ポリシーと保持ラベルまたは電子情報開示用の保留を使用する場合

保持の設定と[電子情報開示ケースを使用して作成した保留](create-ediscovery-holds.md)は、両方ともデータが完全に削除されるのを防ぐことができますが、さまざまなシナリオに対応できるように設計されています。 違いを理解し、どちらを使用するかを決定するために、以下のガイダンスをご利用ください。

- アイテム保持ポリシーや保持ラベルで指定する保持の設定は、コンプライアンス要件に合わせてデータを保持または削除する長期的な情報ガバナンス戦略のために設計されています。 その範囲は通常、個々のユーザーよりも場所やコンテンツに焦点を合わせた幅広いものとなっています。 保持期間の開始日と終了日は構成可能で、追加の管理者が介入することなくコンテンツを自動的に削除できるオプションがあります。

- 電子情報開示 (コア電子情報開示または Advanced eDiscovery ケース) のための保留は、法的な調査のためにデータを保存する限られた期間のために設計されています。 範囲については、特定のユーザーが所有するコンテンツに限定されます。 保持期間の開始日と終了日は構成できませんが、個々の管理者の操作に依存し、保留が解除されたときにコンテンツを自動的に削除するオプションはありません。

保持と保留を比較するための概要

|考慮事項|保持 |電子情報開示の保留|
|:-----|:-----|:-----|:-----|
|ビジネス ニーズ: |コンプライアンス |法務 |
|時間の範囲: |長期 |短期 |
|フォーカス: |広範囲、コンテンツベース |限定的、ユーザーベース |
|開始日と終了日の構成が可能: |必要 |いいえ |
|コンテンツの削除 |はい (オプション) |いいえ |
|管理費: |低い |高い |

コンテンツが保持の設定と電子情報開示の保留の両方の対象になっている場合、電子情報開示の保留のためのコンテンツの保存が常に優先されます。 このように、管理者が手動で保留を解除するまでデータは保持されるため、[保持の原則](#the-principles-of-retention-or-what-takes-precedence)は電子情報開示の保留にまで拡張されます。 ただし、このような優先順位があるにもかかわらず、長期的な情報ガバナンスのために電子情報開示の保留を使用することはできません。 データの自動削除について心配がある場合は、アイテムを無期限に保持するように保持の設定を構成したり、保持ラベルを用いて[処理確認](disposition.md#disposition-reviews)を使用したりすることができます。

古い電子情報開示ツールを使用してデータを保存している場合は、以下のリソースを参照してください。

- Exchange: 
    - [インプレース保持と訴訟ホールド](https://go.microsoft.com/fwlink/?linkid=846124)
    - [Exchange Online メールボックスに適用されている保留の種類を特定する方法](https://docs.microsoft.com/microsoft-365/compliance/identify-a-hold-on-an-exchange-online-mailbox)

- SharePoint と OneDrive 
    - [電子情報開示センターでのコンテンツのケースへの追加とソースの保留リストへの配置](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center)

- [従来の電子情報開示ツールの廃止](legacy-ediscovery-retirement.md)

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a>以前の機能の代わりにアイテム保持ポリシーと保持ラベルを使用する

情報ガバナンスを目的として、Microsoft 365 のコンテンツをプロアクティブに保持または削除する必要がある場合は、次に示す以前の機能の代わりにアイテム保持ポリシーと保持ラベルを使用することをお勧めします。

これらの以前の機能を現在使用している場合、それらもアイテム保持ポリシーおよび保持ラベルと並行して機能し続けます。 ただし、今後はアイテム保持ポリシーと保持ラベルを使用することをお勧めします。 それらは、Microsoft 365 全体でコンテンツの保持と削除の両方を集中管理する単一のメカニズムを提供します。

**Exchange Online の古い機能:**

- [メッセージング レコード管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) とも呼ばれる、[保持タグおよびアイテム保持ポリシー](https://go.microsoft.com/fwlink/?linkid=846125) (削除のみ)

**SharePoint と OneDrive の古い機能:**

- [ドキュメント削除ポリシーの概要](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (削除のみ)
    
- [インプレース レコード管理の構成](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (保持のみ) 
    
- [サイトのクローズと削除のポリシーを使用する](https://support.microsoft.com/ja-JP/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (削除のみ) 
    
- [情報管理ポリシー](intro-to-info-mgmt-policies.md) (削除のみ)
     
コンテンツ タイプ ポリシーまたは情報管理ポリシーの SharePoint サイトを構成して、リストまたはライブラリのコンテンツを保持している場合は、前者のポリシーは無視され、保持ポリシーが有効になります。 

## <a name="related-information"></a>関連情報

- [SharePoint Online の制限](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Microsoft Teams の制限事項と仕様](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [情報ガバナンスおよびレコード管理の規制要件を満たすために役立つリソース](retention-regulatory-requirements.md)

## <a name="next-steps"></a>次の手順

アイテム保持ポリシーを作成する準備ができている場合は、「[アイテム保持ポリシーを作成して構成する](create-retention-policies.md)」を参照してください。

保持ラベルを作成して適用するには:
- [アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)
- [保持ラベルをコンテンツに自動的に適用する](apply-retention-labels-automatically.md)

