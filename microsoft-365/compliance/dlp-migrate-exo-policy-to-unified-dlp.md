---
title: Exchange Online データ損失防止ポリシーをコンプライアンス センターへ移行する
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: オンライン データ損失防止ポリシーを計画し、Exchange DLP に移行するMicrosoft 365します。
ms.openlocfilehash: 07d0eb19155a7f91b30feb8d7938ea574b0e75f9
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2022
ms.locfileid: "62806158"
---
# <a name="migrate-exchange-online-data-loss-prevention-policies-to-compliance-center"></a>Exchange Online データ損失防止ポリシーをコンプライアンス センターへ移行する

[Exchange Onlineデータ損失防止 (DLP) ポリシーは](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)非推奨です。 [DLP を含む、](dlp-learn-about-dlp.md)より豊富Exchange Online DLP 機能は、コンプライアンス センター Microsoft 365[提供されます](https://compliance.microsoft.com/datalossprevention?viewid=policies)。 DLP ポリシー移行ウィザードを使用して、DLP ポリシーを管理Exchange Onlineコンプライアンス センターに移行するのに役立ちます。

移行ウィザードは、サーバーの DLP ポリシーの構成を読み取りExchangeコンプライアンス センターで重複するポリシーを作成します。 既定では、ウィザードはテスト モードで新しいバージョンのポリシーを作成します。そのため、アクションを適用せずに環境に与える影響を確認できます。 コンプライアンス センターのバージョンに完全に移行する準備ができたら、次の条件を **_満たす必要があります_**。

1. 管理者センター (EAC) でソース Exchangeを非アクティブ化または削除します。
1. ポリシーのコンプライアンス センター バージョンを編集し、その状態を [テスト] から [ **強制] に** 変更 **します**。 

> [!WARNING]
> コンプライアンス センターのバージョンを [ポリシーの両方を適用する] に設定する前に、EAC でソース ポリシーを削除または非アクティブ化しない場合は、両方のポリシーセットがアクションの適用を試み、重複するイベントが発生します。 **_これはサポートされていない構成です。_**


移行ウィザードでは、EXO ポリシーと関連付けられたメール フロー ルールのみを移行します。 スタンドアロン Exchangeフロー ルールは移行されません。

## <a name="migration-workflow"></a>移行ワークフロー

コンプライアンス センターの統合 DLP 管理コンソールExchange DLP ポリシーを移行するには、4 つのフェーズがあります。  

1. 移行の準備
    1. 重複する機能について、Exchange Online (EXO) DLP ポリシーとコンプライアンス センター DLP ポリシーを評価して比較します。
    1. どの EXO DLP ポリシーを現在とまったく同じ方法で移行するか決定します。ウィザードを使用して移行できます。
    1. Exchange 管理センターに統合して統合する EXO DLP ポリシーを決定し、移行ウィザードを使用してコンプライアンス センターに移行します。
1. 移行を実行する - ウィザードを使用する
1. テストと検証 - 結果を調べる
1. 移行されたポリシーをアクティブ化する

## <a name="before-you-begin"></a>開始する前に

### <a name="licensing-and-versions"></a>ライセンスとバージョン

DLP ポリシーの移行を開始する前に、サブスクリプションMicrosoft 365[アドオン](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)を確認する必要があります。 

ポリシー移行ウィザードにアクセスして使用するには、これらのサブスクリプションまたはアドオンの 1 つが必要です。

- Microsoft 365 E3
- Microsoft 365 E5
- Microsoft 365 A5 (EDU) 
- Microsoft 365 E5 コンプライアンス
- Microsoft 365 A5 コンプライアンス
- Microsoft 365 E5 の情報保護とガバナンス
- Microsoft 365 A5 の情報保護とガバナンス

DLP ライセンス要件の詳細な一覧については、「Microsoft 365コンプライアンス、データ損失防止&ライセンス ガイダンス[」を参照してください。](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)


### <a name="permissions"></a>アクセス許可

移行ウィザードの実行に使用するアカウントは、Exchange 管理コンソール DLP ページとコンプライアンス センターの統合 DLP コンソールの両方にアクセスできる必要があります。

## <a name="prepare-for-migration"></a>移行の準備

1. DLP、コンプライアンス センター DLP コンソール、または Exchange 管理センター DLP コンソールに慣れていない場合は、ポリシーの移行を試みる前に理解する必要があります。
    1. [Exchange Onlineデータ損失防止 (DLP) ポリシー](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
    1. [Microsoft 365 のエンドポイントのデータ損失防止についての詳細情報](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
    1. [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
1. 次の質問Exchangeして、DLP とコンプライアンス センター のポリシーを評価します。


|質問  |Action  | 移行手順|
|---------|---------|---------|
|ポリシーは引き続き必要ですか?    |削除しない場合は、削除または非アクティブ化する |移行しない|
|他のポリシーまたはコンプライアンス センター DLP Exchange重複していますか?     |はいの場合、重複するポリシーを統合できますか?         |- 別のポリシーと重複するExchange、Exchange 管理センターで統合 DLP ポリシーを手動で作成し、移行ウィザードを使用します。 </br> - 既存のコンプライアンス センター ポリシーと重複している場合は、既存のコンプライアンス センター ポリシーを一致する変更できます。コンプライアンス センター のExchangeしません。|
|DLP ポリシー Exchangeスコープが厳しく設定され、条件、アクション、包含、除外が定義されていますか?     |はいの場合は、ウィザードを使用して移行する場合は、後で削除するために戻ってくることを忘れないので、ポリシーをメモしてください。         | ウィザードを使用して移行する|

## <a name="migration"></a>移行

必要と互換性について、Exchangeコンプライアンス センターの DLP ポリシーを評価したら、移行ウィザードを使用できます。

1. コンプライアンス センター [DLP コンソールMicrosoft 365開](https://compliance.microsoft.com/datalossprevention?viewid=policies)きます。
2. 移行可能Exchange DLP ポリシーがある場合は、ページの上部にバナーが表示されます。
3. バナー **で [ポリシーの移行** ] を選択して、移行ウィザードを開きます。 すべての DLP Exchangeが一覧表示されます。 以前に移行したポリシーは選択できません。
4. 移行するポリシーを選択します。 それらを個別に移行するか、段階的なアプローチを使用してグループに移行するか、一度にすべて移行できます。 **[次へ]** を選択します。
5. 警告やメッセージについては、フライアウト ウィンドウを確認します。 進む前に問題を解決してください。
6. 新しいコンプライアンス センター ポリシーを作成するモードを[アクティブ]、[ **テスト**]、または [ **無効] で** 選択 **します**。  既定値は **Test です**。 **[次へ]** を選択します。
7. 必要に応じて、他の統合 DLP の場所の DLP ポリシーに基Exchangeポリシーを作成できます。 これにより、移行されたサーバー ポリシーに対して 1 つの新しい統合 DLP ポリシー Exchange、ここで選択した他の場所に対して 1 つの新しい統合 DLP ポリシーが作成されます。

> [!IMPORTANT]
> デバイス、SharePoint、OneDrive、オンプレミス、MCAS、Teams チャットメッセージやチャネル メッセージなど、他の DLP の場所でサポートされていない Exchange DLP ポリシーの条件とアクションは、追加のポリシーから削除されます。 また、他の場所に対して実行する必要がある事前作業があります。 参照:
>- [Microsoft 365 のエンドポイントのデータ損失防止についての詳細情報](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
>- [エンドポイント データ損失防止を開始する](endpoint-dlp-getting-started.md#get-started-with-endpoint-data-loss-prevention)
>- [エンドポイントのデータ損失防止の使用](endpoint-dlp-using.md#using-endpoint-data-loss-prevention)
>- [Microsoft 365 のエンドポイントのデータ損失防止について説明します](dlp-on-premises-scanner-learn.md#learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner)
>- [データ損失防止のオンプレミス スキャナーの使用を開始する](dlp-on-premises-scanner-get-started.md#get-started-with-the-data-loss-prevention-on-premises-scanner)
>- [Microsoft 365 のデータ損失防止のオンプレミス スキャナーを使用する](dlp-on-premises-scanner-use.md#use-the-microsoft-365-data-loss-prevention-on-premises-scanner)
>- [Microsoft 以外のクラウド アプリでデータ損失防止ポリシーを使用する](dlp-use-policies-non-microsoft-cloud-apps.md#use-data-loss-prevention-policies-for-non-microsoft-cloud-apps)
 
8. 移行ウィザードのセッション設定を確認します。 **[次へ]** を選択します。
9. 移行レポートを確認します。 メールフロー ルールに関連するエラー Exchange注意してください。 それらを修正し、関連付けられたポリシーを再読み込みできます。

移行されたポリシーは、コンプライアンス センター DLP コンソールの DLP ポリシーの一覧に表示されます。 

## <a name="common-errors-and-mitigation"></a>一般的なエラーと軽減策
|エラー メッセージ  |理由  | 軽減策/推奨手順|
|---------|---------|---------|
|名前を持つコンプライアンス ポリシーは `<Name of the policy>` 、シナリオに既に存在します `Dlp`。    |このポリシーの移行は以前に行われ、同じセッションで再び軽視された可能性があります。 |セッションを更新して、移行に使用できるポリシーの一覧を更新します。 以前に移行されたポリシーはすべて状態である必要 `Already migrated` があります。|
|名前を持つコンプライアンス ポリシーは `<Name of the policy>` 、シナリオに既に存在します `Hold`。     |同じ名前のアイテム保持ポリシーが同じテナントに存在します。       |- EAC の DLP ポリシーの名前を別の名前に変更します。 </br> - 影響を受け取ったポリシーの移行を再試行します。 |
|`DLP-group@contoso.com` 配布グループまたはメールが有効なセキュリティ グループなので、Shared By 条件の値として使用することはできません。 特定のグループのメンバーによるアクティビティを検出するには、述語のメンバーによる共有を使用します。     |トランスポート ルールを使用すると、グループを `sender is` 条件で使用できますが、統合 DLP では使用できません。         | トランスポート ルールを更新して、条件からすべてのグループ `sender is` メール アドレスを削除し、必要に応じてグループを条件 `sender is a member of` に追加します。 影響を受け取ったポリシーの移行を再試行する|
|受信者が見つからな`DLP-group@contoso.com` 新しく作成した場合は、しばらくしてから操作を再試行してください。 削除または有効期限が切れた場合は、有効な値でリセットし、もう一度やり直してください。     |条件で使用されているグループ アドレスの有効期限が`sender is a member of``recipient is a member of`切れているか無効である可能性があります。         | - 管理センターのトランスポート ルール内のすべての無効なグループ電子メール アドレスを削除Exchangeします。 </br> - 影響を受け取ったポリシーの移行を再試行します。|
|述語で指定する値 `FromMemberOf` は、メールが有効なセキュリティ グループである必要があります。     |トランスポート ルールを使用すると、個々のユーザー `sender is a member of` を条件で使用できますが、統合 DLP では使用できません。         | - トランスポート ルールを更新して、個々の `sender is a member of` ユーザー電子メール アドレスを条件から削除し、必要に応じてユーザーを `sender is` 条件に追加します。 </br> - 影響を受け取ったポリシーの移行を再試行します。|
|述語で指定する値 `SentToMemberOf` は、メールが有効なセキュリティ グループである必要があります。    |トランスポート ルールを使用すると、個々のユーザーを `recipient is a member of` 条件の下で使用できますが、統合 DLP では使用できません。         | - トランスポート ルールを更新して、個々の `recipient is a member of` ユーザー電子メール アドレスを条件から削除し、必要に応じてユーザーを `recipient is` 条件に追加します。 </br> - 影響を受け取ったポリシーの移行を再試行します。|
|パラメーターの使用`<Name of condition>`は、パラメーターの使用Exchange。 このパラメーターを削除するか、この場所Exchangeします。         | 同じ名前の別のポリシーがコンプライアンス センターに存在し、前述の条件がサポートされていない SPO/ODB/Teams などの他の場所に存在する可能性があります。 | 管理センターで DLP ポリシー Exchange変更し、移行を再試行します。|

## <a name="testing-and-validation---prateek-and-aakash-to-provide-a-list-of-supported-predicates-and-known-issues-before-publishing--"></a>テストと検証 <!--PRATEEK AND AAKASH TO PROVIDE A LIST OF SUPPORTED PREDICATES AND KNOWN ISSUES BEFORE PUBLISHING-->

ポリシーをテストして確認します。

1. DLP ポリシー [のテスト手順に従](create-test-tune-dlp-policy.md#test-a-dlp-policy) います。
2. アクティビティ エクスプローラーでポリシーによって作成されたイベント [を確認します](data-classification-activity-explorer.md)。

## <a name="review-the-policy-matches-between-exchange-admin-center-dlp-and-microsoft-365-unified-dlp"></a>管理センター DLP と統合 DLP Exchangeポリシーの一致Microsoft 365確認する

移行されたポリシーが期待どおりに動作することを確認するには、両方の管理センターからレポートをエクスポートし、ポリシーの一致の比較を行います。

1. [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) に接続する
2. [EAC DLP レポートをエクスポートします](/powershell/module/exchange/get-maildetaildlppolicyreport)。 このコマンドレットをコピーして、適切な値を挿入できます。

```powershell
Get-MailDetailDlpPolicyReport -StartDate <dd/mm/yyyy -EndDate <dd/mm/yyyy> -PageSize 5000 | select Date, MessageId, DlpPolicy, TransportRule -Unique | Export-CSV <"C:\path\filename.csv"> 
```

3. 統合 [DLP レポートをエクスポートします](/powershell/module/exchange/get-dlpdetailreport)。 このコマンドレットをコピーして、適切な値を挿入できます。

```powershell
Get-DlpDetailReport -StartDate <dd/mm/yyyy> -EndDate <dd/mm/yyyy> -PageSize 5000 | select Date, Location, DlpCompliancePolicy, DlpComplianceRule -Unique | Export-CSV <"C:\path\filename.csv">  
```

## <a name="activate-your-migrated-policies"></a>移行されたポリシーをアクティブ化する

移行したポリシーの機能に満足したら、ポリシーを [強制] に設定 **できます**。

1. 管理センター DLP コンソールExchange開きます。
2. ソース ポリシーを非アクティブ化または削除します。
3. [コンプライアンス Microsoft 365 DLP [コンソールを](https://compliance.microsoft.com/datalossprevention?viewid=policies)開き、アクティブにするポリシーを選択して編集します。
4. 状態を [オン] **に変更します**。

## <a name="related-articles"></a>関連記事

- [Exchange Onlineデータ損失防止 (DLP) ポリシー](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
- [データ損失防止について](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [Activity Explorer を使い始める](data-classification-activity-explorer.md)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [テンプレートから DLP ポリシーを作成する](create-a-dlp-policy-from-a-template.md)
- [Exchange Onlineデータ損失防止 (DLP) ポリシー](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
