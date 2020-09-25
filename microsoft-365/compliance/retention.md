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
search.appverid:
- MOE150
- MET150
description: 必要なコンテンツを保持し不要なコンテンツを削除するのに役立つ、アイテム保持ポリシーと保持ラベルについて説明します。
ms.openlocfilehash: d8b9ff7bea32f489a5cce5f64626908e8ec56fa1
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197340"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベルの詳細

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

ほとんどの組織では、電子メール、ドキュメント、インスタント メッセージなどのデータの量と複雑さが日々増しています。次の必要性から、これらの情報を効果的に管理することが重要です。
  
- **最小限の期間コンテンツを保持することを要求する業界の規制や内部ポリシーを積極的に遵守する**: たとえば、米国企業改革法により、特定の種類のコンテンツを 7 年間保持することが求められる場合があります。 

- **訴訟やセキュリティ違反が発生した場合にリスクを軽減する**: このために、保持する必要がなくなった古いコンテンツは完全に削除します。 
    
- **組織内での効率的な知識の共有と迅速な対応に役立てる**: このために、ユーザーは現時点で関連性のあるコンテンツのみを対象に作業するようにします。 
    
保持設定を構成することは、これらすべての目標を実現するのに役立ちます。 コンテンツの管理には、一般的に次の 2 つのアクションが必要です。
  
- **コンテンツの保持**: 保持期間が満了するまではコンテンツの完全な削除ができないようにします。 
    
- **コンテンツの削除**: 保持期間の満了時点でコンテンツを完全に削除します。 
    

これら 2 つの保持アクションを使用して、次の結果が得られるように保持設定を構成できます。

- 保持のみ: コンテンツを無期限または指定した期間保持します。
- 削除のみ: 指定した期間の後にコンテンツを削除します。
- 保持してから削除: コンテンツを指定した期間保持してから削除します。

これらの保持設定は所定の場所にあるコンテンツに作用し、コンプライアンス上の理由でコンテンツを保持する必要がある場合でも、追加のストレージを作成して構成するための追加のオーバーヘッドを節約できます。 また、このデータをコピーして同期するために、カスタマイズしたプロセスを実装する必要もありません。

## <a name="how-retention-settings-work-with-content-in-place"></a>保持設定が所定の場所にあるコンテンツに作用するしくみ

コンテンツに保持設定が割り当てられるとき、そのコンテンツは元の場所にそのまま残ります。 ユーザーは何事もなかったかのように、ドキュメントやメールで作業を続けることができます。 アイテム保持ポリシーに含まれているコンテンツをユーザーが編集または削除すると、そのコンテンツのコピーが、保持設定を適用した時点の状態で自動的に保持されます。
  
- SharePoint および OneDrive サイトの場合: コピーは、**アイテム保管**ライブラリに保持されます。

- Exchange メールボックスの場合: コピーは、**[回復可能なアイテム]** フォルダーに保持されます。 

- TeamsとYammerのメッセージ： **SubstrateHolds**という名前の隠しフォルダーに Exchange**回復可能アイテム**フォルダー内のサブフォルダーとして保存されます。

> [!NOTE]
> アイテム保管ライブラリは、サイトのストレージ クォータから除外されていないストレージを消費します。 SharePoint グループや Microsoft 365 グループに対して保持設定を使用する場合は、ストレージを増やすことが必要な場合があります。
> 
セキュリティで保護されているこれらの場所や保持されているコンテンツは、ほとんどのユーザーには表示されません。 ほとんどの場合、ユーザーは自分が作業しているコンテンツが保持設定の対象であることを知る必要さえありません。

保持設定がさまざまなワークロードに対してどのように機能するかの詳細については、次の記事を参照してください。

- [SharePoint と OneDrive の保持の詳細](retention-policies-sharepoint.md)
- [Microsoft Teams の保持の詳細](retention-policies-teams.md)
- [Yammerの保持の詳細](retention-policies-yammer.md)
- [Exchange の保持の詳細](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベル

保持設定をコンテンツに割り当てる場合、アイテム保持ポリシーと保持ラベルの両方を使用できます。 

サイト レベルやメールボックス レベルで同一の保持設定を割り当てるには、アイテム保持ポリシーを使用します。一方、アイテム レベル (フォルダー、ドキュメント、メール) で保持設定を割り当てるには、保持ラベルを使用します。

たとえば、SharePoint サイト内のすべてのドキュメントを 5 年間保持する必要がある場合は、同じ保持ラベルをサイト内のすべてのドキュメントに適用するよりも、アイテム保持ポリシーを使用する方が効率的です。 一方、サイト内の一部のドキュメントは 5 年間保持し、一部は 10 年間保持する必要がある場合、アイテム保持ポリシーではこれを行うことができません。 アイテム レベルで保持設定を指定する必要がある場合は、保持ラベルを使用します。 

アイテム保持ポリシーとは異なり、保持ラベルによる保持設定は、コンテンツが別の Microsoft 365 の場所にコピーまたは移動された場合でも、コンテンツと共に維持されます。 また、保持ラベルには、アイテム保持ポリシーではサポートされていない次の機能があります。 
 
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
    
ポリシーは、すべてのコンテンツに適用することも、キーワードや[機密情報の種類](sensitive-information-type-entity-definitions.md)を含むコンテンツなど、特定の条件を満たすコンテンツに適用することもできます。

#### <a name="use-preservation-lock-to-comply-with-regulatory-requirements"></a>[保持ロック] を使用して規制要件に準拠する

一部の組織は、米国証券取引委員会 (SEC) 規則 17a-4 など、規制機関によって定義された規則に準拠する必要があります。その場合、アイテム保持ポリシーをオンにした後、それをオフにしたり、制限を緩和したりすることはできないという要求があります。 

保管ロックを使用すると、アイテム保持ポリシーがロックされ、管理者を含むいかなるユーザーも、ポリシーをオフにすることや削除すること、またその制限を緩和することができなくなるため、組織はこのような規制要件を確実に満たすことができます。
  
保持ポリシーがロックされている場合:

- だれもオフにすることはできません。
- 場所は追加できますが、削除できません
- ポリシーの対象となるコンテンツは、保持期間中は変更または削除できません
- 保持期間を延長することはできますが、短縮することはできません

要約すると、ロックされたアイテム保持ポリシーを増やしたり延長したりすることは可能ですが、減らしたり、オフにしたりすることはできません。
  
> [!IMPORTANT]
> アイテム保持ポリシーをロックする前に、その影響を理解し、組織が規制要件を満たす必要があるかどうかを確認することは非常に重要です。 保管ロックを適用すると、管理者はアイテム保持ポリシーを無効にすることも削除することもできなくなります。

アイテム保持ポリシーを作成した後に、PowerShell を使用して保持ロックを適用します。 手順は、「[アイテム保持ポリシーを作成して構成する](create-retention-policies.md)」に含まれています。

#### <a name="releasing-a-retention-policy"></a>アイテム保持ポリシーを解除する

アイテム保持ポリシーに保持ロックがない場合、アイテム保持ポリシーをいつでもオフにしたり削除したりできます。 

この操作を行うと、[アイテム保管ライブラリ] で保持されている SharePoint や OneDrive のコンテンツは、すぐには完全に削除されません。 代わりに、不注意によるデータの損失を防ぐために、30 日間の猶予期間があります。そのポリシーのコンテンツの有効期限は、[アイテム保管ライブラリ] には表示されず、必要に応じてコンテンツを復元できます。 また、猶予期間中はこのコンテンツを手動で削除することはできません。

猶予期間中にアイテム保持ポリシーをもう一度有効にすることができます。そのポリシーのコンテンツは削除されません。

この SharePoint と OneDrive の 30 日の猶予期間は、Exchange の 30 日の保留期間に対応しています。 詳しくは、[メールボックスの管理についての詳細](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold) をご覧ください。。

### <a name="retention-labels"></a>保持ラベル

保持ラベルは、異なる保持設定を必要とするさまざまな種類のコンテンツに対して使用できます。 例:
  
- 最低限の期間、保持する必要のある納税申告書。 
    
- 特定の期間が経過した後、完全に削除する必要があるプレス資料。 
    
- 特定の期間保持した後に完全に削除する必要がある競合企業のリサーチ。 
    
- 編集も削除もできないように、レコードとしてマークする必要がある就労ビザ。 
    
いずれの場合も、保持ラベルを使用すると、アイテム レベル (ドキュメントやメール) でガバナンス制御用の保持設定を適用できます。
  
保持ラベルを使用すると、次のことができます。
  
- **組織のユーザーが保持ラベルを手動で適用できるようにする**。ユーザーが保持ラベルを手動で適用できるのは、Outlook および Outlook on the web、OneDrive、SharePoint​​、Microsoft 365 グループ内のコンテンツです。 多くの場合、ユーザーは自分が操作するコンテンツの種類を最もよく知っているので、コンテンツを分類して適切な保持設定を適用できます。 
    
- コンテンツに次のものが含まれている場合など、特定の条件に一致するときには、**保持ラベルをコンテンツに自動的に適用**できます。 
    - 特定の種類の機密情報。
    - 作成したクエリに一致する特定のキーワード。
    - トレーニング可能な分類子のパターン マッチ。

- **コンテンツにラベルが付けられた時点から保持期間を開始する**。SharePoint サイトや OneDrive アカウントのドキュメント、および予定表アイテム以外のメール アイテムに対してこの操作を行えます。 この構成の保持ラベルを予定表アイテムに適用すると、保持期間はアイテムが送信された時点から開始されます。

- 従業員の退職、契約の期限切れなど、**イベントの発生時に保持期間を開始する**。

- SharePoint の**ドキュメント ライブラリ、フォルダー、またはドキュメント セットに既定の保持ラベルを適用**することにより、この場所に保存するすべてのドキュメントに既定の保持ラベルが継承されるようになります。

さらに、保持ラベルは、Microsoft 365 アプリとサービス全体でのメールとドキュメントの[レコード管理](records-management.md)をサポートします。 保持ラベルを使用して、アイテムをレコードとしてマークできます。 この問題が発生し、コンテンツが Microsoft 365 に残っている場合は、このラベルで規制上の理由から必要になることがあるコンテンツがさらに制限されます。 詳細については、「[許可またはブロックするアクションの制限を比較する](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)」を参照してください。

保持ラベルは、[秘密度ラベル](sensitivity-labels.md)とは異なり、コンテンツが Microsoft 365 以外の場所に移動した場合は保持されません。

テナントでサポートされる保持ラベルの数に制限はありません。 ただし、10,000 はテナントでサポートされるポリシーの最大数であり、これらには、ラベルを適用するポリシー (保持ラベル ポリシーと自動適用アイテム保持ポリシー) とアイテム保持ポリシーが含まれます。

#### <a name="classifying-content-without-applying-any-actions"></a>アクションを適用しないでコンテンツを分類する

保持ラベルの主な目的はコンテンツを保持または削除することですが、保持やその他のアクションを有効にしないで保持ラベルを使用することもできます。 この場合、テキスト ラベルとしてのみ保持ラベルを使用し、他のアクションは適用しません。
  
たとえば、アクションを含まない "後で確認" という名前の保持ラベルを作成して適用し、後からそのコンテンツを見つけるためにそのラベルを使用できます。
  
![分類専用のラベル設定](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>DLP ポリシーで保持ラベルを条件として使用する

SharePoint のドキュメントのデータ損失防止 (DLP) ポリシーの条件として、保持ラベルを指定することができます。 たとえば、指定された保持ラベルがドキュメントに適用されている場合はそのドキュメントが組織外に共有されないように、DLP ポリシーを構成できます。

詳細については、「[DLP ポリシーでの条件としての保持ラベルの使用](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)」を参照してください。

#### <a name="retention-labels-and-policies-that-apply-them"></a>保持ラベルと保持ラベルを適用するポリシー

保持ラベルは、独立した再利用可能な文書パーツです。 保持ラベル ポリシーの主な目的は、保持ラベルのセットをグループ化して、ラベルを表示する場所を特定することです。 そうすることにより、管理者とユーザーはラベルをそれらの場所のコンテンツに適用できます。
  
![ラベル、ラベル ポリシー、および場所の図](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
保持ラベルを発行すると、それらは保持ラベル ポリシーに含まれます。このポリシーを使用することで、管理者やユーザーは次の中から選択して保持ラベルを使用できます。

- 1 つの保持ラベルを複数の保持ラベル ポリシーに含めることができます。

- 保持ラベル ポリシーは保持ラベルを発行する場所を指定します。

- 1 つの場所を複数の保持ラベル ポリシーに含めることもできます。

保持ラベル ポリシーに加えて、1 つ以上の自動適用ポリシーを作成して、それぞれに保持ラベルを 1 つ指定することもできます。 このポリシーを使うと、ポリシーで指定した条件が満たされた場合に、保持ラベルが自動的に適用されます。 

#### <a name="retention-label-policies-and-locations"></a>保持ラベルのポリシーと場所

保持ラベルの内容に応じて、多様な種類の保持ラベルをさまざまな場所に発行できます。
  
| 保持ラベルの種類 | ラベル ポリシーの適用先 |
|:-----|:-----|
|管理者とエンド ユーザーに発行されたラベル  <br/> |Exchange、SharePoint、OneDrive、Microsoft 365 グループ  <br/> |
|機密情報の種類またはトレーニング可能な分類子に基づいて自動適用されたラベル  <br/> |Exchange (すべてのメールボックスのみ)、SharePoint、OneDrive  <br/> |
|クエリに基づいて自動適用されたラベル  <br/> |Exchange、SharePoint、OneDrive、Microsoft 365 グループ  <br/> |
   
Exchange の自動適用保持ラベルは、新しく送信されたメッセージ (転送中のデータ) のみに適用され、現在メールボックスにあるすべてのアイテム (保存データ) には適用されません。 また、機密情報の種類やトレーニング可能な分類子の自動適用保持ラベルはすべてのメールボックスのみに適用でき、特定のメールボックスを選択することはできません。
  
Exchange パブリックフォルダー、Skype、Teams、Yammer メッセージは保持ラベルをサポートしていません。 これらの場所のコンテンツを保持または削除するには、代わりにアイテム保持ポリシーを使用します。

#### <a name="only-one-retention-label-at-a-time"></a>一度に 1 つの保持ラベルのみ

メールやドキュメントに一度に割り当てられる保持ラベルは 1 つのみです。
  
- 管理者やエンド ユーザーが手動で割り当てた保持ラベルの場合、ユーザーは割り当てられている保持ラベルを削除または変更できます。
    
- コンテンツに自動適用ラベルが割り当てられている場合は、このラベルを発行済みの保持ラベルで置き換えることができます。
    
- コンテンツに発行済みの保持ラベルが割り当てられている場合は、このラベルを自動適用ラベルで置き換えることはできません。
    
- 自動適用ラベルを割り当てるルールが複数あり、コンテンツが複数のルールの条件を満たしている場合、最も古いルールの保持ラベルが割り当てられます。
    
保持ラベルが別の保持ラベルではなくどのように適用されるかを理解するには、ラベルを明示的に割り当てることと、ラベルを暗黙的に割り当てることの違いを理解することが役立ちます。

- ラベル ポリシーから適用された保持ラベルは明示的に割り当てられる
- 自動適用ポリシーから自動的に適用された保持ラベルは、暗黙的に割り当てられる

明示的に割り当てられた保持ラベルは、暗黙的に割り当てられた保持ラベルよりも優先されます。 詳細については、このページの「[保持の原則または優先順位](retention.md#the-principles-of-retention-or-what-takes-precedence)」のセクションを参照してください。

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

コンテンツ検索を作成するとき、**保持 ラベル**の条件を選択し、完全な保持ラベル名を入力するか、ラベル名の一部を入力してワイルドカードを使用します。 詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。
  
![保持ラベルの条件](../media/retention-label-condition.png)


## <a name="compare-capabilities-for-retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベルの機能比較

次の表は、アイテム保持ポリシーと保持ラベルのどちらを使用するかを、機能に基づいて決定するのに役立ちます。

|機能|アイテム保持ポリシー |保持ラベル|
|:-----|:-----|:-----|:-----|
|保持してから削除、保持のみ、削除のみを指定できる保持設定 |はい |はい |
|サポートされるワークロード: <br />- Exchange <br />- SharePoint <br />- OneDrive <br />- Microsoft 365 グループ <br />- Skype for Business <br />- Teams<br />- Yammer|<br /> はい <br /> はい <br /> はい <br /> はい <br /> はい <br /> はい | <br /> はい (パブリック フォルダーを除く) <br /> はい <br /> はい <br /> はい <br /> いいえ <br /> いいえ <br /> いいえ |
|保持の自動適用 | はい | はい |
|条件に基づいて適用される保持 <br /> - 機密情報の種類、KQL クエリ、トレーニング可能な分類子| 不要 | はい |
|保持の手動適用 | いいえ | はい |
|エンド ユーザー向け UI の存在 | いいえ | はい |
|コンテンツが移動された場合の保持 | いいえ | はい (Microsoft 365 内) |
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
    
    1. Exchange メールや OneDrive ドキュメントなど、ユーザーが保持設定を含む保持ラベルをアイテムに手動で割り当てた場合は、サイト レベルまたはメールボックス レベルで割り当てられているアイテム保持ポリシーや、ドキュメント ライブラリに割り当てられている既定の保持ラベルよりも、手動で割り当てたラベルが優先されます。 たとえば、明示的な保持ラベルでは 10 年間コンテンツを保持するように構成され、サイトに割り当てられているアイテム保持ポリシーでは 5 年間のみコンテンツを保持するように構成されている場合、明示的な保持ラベルが優先されます。 自動適用の保持ラベルは、Microsoft 365 によって自動的に適用されるため、明示的ではなく、暗黙的とされます。
    
    2. アイテム保持ポリシーに特定のユーザーのメールボックスまたは OneDrive のアカウントなどの特定の場所が含まれている場合、そのアイテム保持ポリシーは、すべてのユーザーのメールボックスまたは OneDrive のアカウントに適用されるが、そのユーザーのメールボックスを特に含まない別の保持ポリシーよりも優先されます。
    
4. **最短の削除期間が優先されます。** 同様に、保持期間なしでコンテンツを削除する複数の保持設定が指定されている場合、そのコンテンツは最短保持期間の終了時に削除されます。 

最後に、アイテム保持ポリシーや保持ラベルでは、電子情報開示のために保持しているコンテンツを完全に削除することはできません。 電子情報開示のための保持を解除すると、コンテンツは再びそのワークロードに対するセキュリティで保護された場所のクリーンアップ プロセスの対象になります。

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

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a>以前の機能の代わりにアイテム保持ポリシーと保持ラベルを使用する

情報ガバナンスを目的として、Microsoft 365 のコンテンツをプロアクティブに保持または削除する必要がある場合は、次に示す以前の機能の代わりにアイテム保持ポリシーと保持ラベルを使用することをお勧めします。 
  
これらの以前の機能を現在使用している場合、それらもアイテム保持ポリシーおよび保持ラベルと並行して機能し続けます。 ただし、今後はアイテム保持ポリシーと保持ラベルを使用することをお勧めします。 それらは、Microsoft 365 全体でコンテンツの保持と削除の両方を集中管理する単一のメカニズムを提供します。

**Exchange Online の古い機能:**

- [インプレース ホールドと訴訟ホールド](https://go.microsoft.com/fwlink/?linkid=846124) (電子情報開示の保留リスト) 

- [Exchange Online メールボックスに適用されている保留の種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- [メッセージング レコード管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) とも呼ばれる、[保持タグおよびアイテム保持ポリシー](https://go.microsoft.com/fwlink/?linkid=846125) (削除のみ)
    
「[従来の電子情報開示ツールの廃止](legacy-ediscovery-retirement.md)」も参照してください。


**SharePoint と OneDrive の古い機能:**

- [電子情報開示センターでのコンテンツのケースへの追加とソースの保留リストへの配置](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (電子情報開示の保留リスト) 
    
- [ドキュメント削除ポリシーの概要](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (削除のみ)
    
- [インプレース レコード管理の構成](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (保持のみ) 
    
- [サイトのクローズと削除のポリシーを使用する](https://support.microsoft.com/ja-JP/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (削除のみ) 
    
- [情報管理ポリシー](intro-to-info-mgmt-policies.md) (削除のみ)
     
以前に情報ガバナンスを目的として電子情報開示の保留のいずれかを使用したことがある場合は、予防的なコンプライアンスのために、代わりにアイテム保持ポリシーを使用します。 電子情報開示は、保留リストのみに使用します。
  
### <a name="retention-policies-and-sharepoint-content-type-policies-or-information-management-policies"></a>アイテム保持ポリシーと SharePoint コンテンツ タイプ ポリシーまたは情報管理ポリシー

コンテンツ タイプ ポリシーまたは情報管理ポリシーの SharePoint サイトを構成して、リストまたはライブラリのコンテンツを保持している場合は、前者のポリシーは無視され、保持ポリシーが有効になります。 

## <a name="related-information"></a>関連情報

- [SharePoint Online の制限](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Microsoft Teams の制限事項と仕様](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [SEC Rule 17a-4 に準拠する ](use-exchange-online-to-comply-with-sec-rule-17a-4.md)

## <a name="next-steps"></a>次の手順

アイテム保持ポリシーを作成する準備ができている場合は、「[アイテム保持ポリシーを作成して構成する](create-retention-policies.md)」を参照してください。

保持ラベルを作成して適用するには:
- [アイテム保持ラベルを作成してアプリに適用する](create-apply-retention-labels.md)
- [保持ラベルをコンテンツに自動的に適用する](apply-retention-labels-automatically.md)

