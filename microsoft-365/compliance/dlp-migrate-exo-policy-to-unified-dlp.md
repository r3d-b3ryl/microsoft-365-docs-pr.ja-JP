---
title: Exchange Online DLP ポリシーをコンプライアンス センターに移行する
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
description: Exchange Online データ損失防止ポリシーを計画し、DLP に移行する方法について説明します。
ms.openlocfilehash: 371dfafbbf6acf31587b0786a5b5594fb83571d9
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66638281"
---
# <a name="migrate-exchange-online-data-loss-prevention-policies-to-microsoft-purview-compliance-portal"></a>Exchange Onlineデータ損失防止ポリシーをMicrosoft Purview コンプライアンス ポータルに移行する

[Exchange Onlineデータ損失防止 (DLP) ポリシー](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)は非推奨になっています。 Microsoft Purview コンプライアンス ポータルでは、Exchange Online DLP を含む[、より豊富な DLP 機能](dlp-learn-about-dlp.md)[が提供](https://compliance.microsoft.com/datalossprevention?viewid=policies)されます。 DLP ポリシー移行ウィザードを使用すると、Exchange Online DLP ポリシーをコンプライアンス センターに持ち込んで管理することができます。

移行ウィザードは、Exchange で DLP ポリシーの構成を読み取り、コンプライアンス センターで重複するポリシーを作成することで機能します。 既定では、ウィザードによって新しいバージョンのポリシーが **テスト** モードで作成されるため、アクションを強制することなく、環境に与える影響を確認できます。 コンプライアンス センターのバージョンに完全に移行する準備ができたら、次の **_操作を行う必要があります_**。

1. Exchange 管理 センター (EAC) でソース ポリシーを非アクティブ化または削除します。
1. ポリシーのコンプライアンス センター バージョンを編集し、その状態を **テスト** から強制に変更 **します**。

> [!WARNING]
> コンプライアンス センターのバージョンを [両方のポリシーの **適用]** に設定する前に EAC でソース ポリシーを削除または非アクティブ化しない場合は、アクションの適用が試行され、重複するイベントが発生します。 **_これはサポートされていない構成です。_**

移行ウィザードでは、EXO ポリシーと関連するメール フロー ルールのみが移行されます。 スタンドアロン Exchange メール フロー ルールは移行されません。

## <a name="migration-workflow"></a>移行ワークフロー

Exchange からコンプライアンス センターの統合 DLP 管理コンソールに DLP ポリシーを移行するには、4 つのフェーズがあります。

1. 移行の準備
    1. Exchange Online (EXO) DLP ポリシーとコンプライアンス センター DLP ポリシーを評価して比較し、重複する機能を実現します。
    1. どの EXO DLP ポリシーをそのまま引き継ぐかを決定します。ウィザードを使用してこれらを移行できます。
    1. Exchange 管理センターで統合して統合する EXO DLP ポリシーを決定し、移行ウィザードを使用してコンプライアンス センターに移行します。
1. 移行を実行する - ウィザードを使用する
1. テストと検証 - 結果を調べる
1. 移行されたポリシーをアクティブ化する

## <a name="before-you-begin"></a>はじめに

### <a name="licensing-and-versions"></a>ライセンスとバージョン

DLP ポリシーの移行を開始する前に、 [Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) とアドオンを確認する必要があります。

ポリシー移行ウィザードにアクセスして使用するには、次のいずれかのサブスクリプションまたはアドオンが必要です。

- Microsoft 365 E3
- Microsoft 365 E5
- Microsoft 365 A5 (EDU) 
- Microsoft 365 E5 コンプライアンス
- Microsoft 365 A5 コンプライアンス
- Microsoft 365 E5 の情報保護とガバナンス
- Microsoft 365 A5 の情報保護とガバナンス

DLP ライセンス要件の詳細な一覧については、[セキュリティ & コンプライアンス、データ損失防止に関する Microsoft 365 ライセンスガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)を参照してください。

### <a name="permissions"></a>アクセス許可

移行ウィザードの実行に使用するアカウントは、Exchange 管理 コンソール DLP ページとコンプライアンス センターの統合 DLP コンソールの両方にアクセスできる必要があります。

## <a name="prepare-for-migration"></a>移行の準備

1. DLP、コンプライアンス センター DLP コンソール、または Exchange 管理 センター DLP コンソールに慣れていない場合は、ポリシーの移行を試みる前に理解しておく必要があります。
    1. [Exchange Onlineデータ損失防止 (DLP) ポリシー](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
    1. [エンドポイント データ損失防止について](endpoint-dlp-learn-about.md)
    1. [DLP ポリシーを作成、テスト、チューニングする](create-test-tune-dlp-policy.md)
1. 次の質問をして、Exchange DLP とコンプライアンス センターのポリシーを評価します。

|質問|Action|移行手順|
|---|---|---|
|ポリシーは引き続き必要ですか?|削除しない場合は、削除または非アクティブ化します。|移行しない|
|他の Exchange またはコンプライアンス センターの DLP ポリシーと重複していますか?|はいの場合は、重複するポリシーを統合できますか?|- 別の Exchange ポリシーと重複している場合は、Exchange 管理 センターで統合 DLP ポリシーを手動で作成し、移行ウィザードを使用します。 </br> - 既存のコンプライアンス センター ポリシーと重複している場合は、既存のコンプライアンス センター ポリシーを一致するように変更できます。Exchange バージョンを移行しないでください|
|Exchange DLP ポリシーの範囲は厳密であり、条件、アクション、包含、除外が明確に定義されていますか?|はい場合は、ウィザードを使用して移行することをお勧めします。ポリシーをメモして、後で削除することを忘れないでください|ウィザードを使用して移行する|

## <a name="migration"></a>移行

必要と互換性について Exchange およびコンプライアンス センターのすべての DLP ポリシーを評価したら、移行ウィザードを使用できます。

1. [Microsoft Purview コンプライアンス ポータル](https://compliance.microsoft.com/datalossprevention?viewid=policies) DLP コンソールを開きます。
2. 移行できる Exchange DLP ポリシーがある場合は、ページの上部にバナーが表示されます。
3. バナーで [ **ポリシーの移行** ] を選択して、移行ウィザードを開きます。 すべての Exchange DLP ポリシーが一覧表示されます。 以前に移行したポリシーは選択できません。
4. 移行するポリシーを選択します。 それらを個別に、または段階的なアプローチを使用してグループで移行することも、一度にすべて移行することもできます。 **[次へ]** を選択します。
5. ポップアップ ウィンドウで警告またはメッセージを確認します。 続行する前に問題を解決します。
6. 新しいコンプライアンス センター ポリシーを作成するモードを、 **アクティブ**、 **テスト**、または **無効に選択します**。  既定値は **[テスト]** です。 **[次へ]** を選択します。
7. 必要に応じて、他の統合 DLP の場所の Exchange DLP ポリシーに基づくポリシーをさらに作成できます。 これにより、移行された Exchange ポリシーに対する 1 つの新しい統合 DLP ポリシーと、ここで選択した他の場所に対する 1 つの新しい統合 DLP ポリシーが生成されます。

> [!IMPORTANT]
> デバイス、SharePoint、OneDrive、オンプレミス、MCAS、Teams チャット、チャネル メッセージなど、他の DLP の場所でサポートされていない Exchange DLP ポリシーの条件とアクションは、追加のポリシーから削除されます。 また、他の場所に対して実行する必要がある事前作業もあります。 参照:
>- [エンドポイント データ損失防止について](endpoint-dlp-learn-about.md)
>- [エンドポイント データ損失防止を開始する](endpoint-dlp-getting-started.md)
>- [エンドポイントのデータ損失防止の使用](endpoint-dlp-using.md)
>- [データ損失防止のオンプレミス スキャナーについて説明します](dlp-on-premises-scanner-learn.md)
>- [データ損失防止のオンプレミス スキャナーの使用を開始する](dlp-on-premises-scanner-get-started.md)
>- [Microsoft Purview データ損失防止オンプレミス スキャナーを使用する](dlp-on-premises-scanner-use.md)
>- [Microsoft 以外のクラウド アプリにデータ損失防止ポリシーを使用する](dlp-use-policies-non-microsoft-cloud-apps.md)
 
8. 移行ウィザードのセッション設定を確認します。 **[次へ]** を選択します。
9. 移行レポートを確認します。 Exchange メール フロー ルールに関連するエラーに注意してください。 それらを修正し、関連付けられているポリシーを再マッピングできます。

移行されたポリシーが、コンプライアンス センター DLP コンソールの DLP ポリシーの一覧に表示されます。

## <a name="common-errors-and-mitigation"></a>一般的なエラーと軽減策

|エラー メッセージ|理由|軽減策/推奨される手順|
|---|---|---|
|シナリオには、名前 `<Name of the policy>` を持つコンプライアンス ポリシーが既に `Dlp`存在します。|このポリシーの移行は先に行われ、同じセッションで再試行された可能性があります。|セッションを更新して、移行に使用できるポリシーの一覧を更新します。 以前に移行されたすべてのポリシーは、状態である `Already migrated` 必要があります。|
|シナリオには、名前 `<Name of the policy>` を持つコンプライアンス ポリシーが既に `Hold`存在します。|同じ名前のアイテム保持ポリシーが同じテナントに存在します。|- EAC の DLP ポリシーの名前を別の名前に変更します。 </br> - 影響を受けたポリシーの移行を再試行します。|
|`DLP-group@contoso.com` は配布グループまたはメールが有効なセキュリティ グループであるため、Shared By 条件の値として使用できません。 特定のグループのメンバーによるアクティビティを検出するには、述語のメンバーによって共有を使用します。|トランスポート ルールでは、条件でグループを `sender is` 使用できますが、統合 DLP では許可されません。|トランスポート ルールを更新して、条件からすべてのグループ電子メール アドレスを `sender is` 削除し、必要に応じてグループを条件に `sender is a member of` 追加します。 影響を受けたポリシーの移行を再試行する|
|受信者 `DLP-group@contoso.com`が見つかりませんでした。 新しく作成した場合は、しばらくしてから操作を再試行してください。 削除または期限切れの場合は、有効な値を使用してリセットしてから、もう一度やり直してください。|使用されているグループ アドレス、または条件の `sender is a member of` 有効期限が切れているか `recipient is a member of` 無効である可能性があります。|- Exchange 管理センターのトランスポート ルール内のすべての無効なグループ電子メール アドレスを削除または置換します。 </br> - 影響を受けたポリシーの移行を再試行します。|
|述語で `FromMemberOf` 指定する値は、メールが有効なセキュリティ グループである必要があります。|トランスポート ルールを使用すると、個々のユーザーを `sender is a member of` 条件で使用できますが、統合 DLP では許可されません。|- トランスポート ルールを更新して、条件から `sender is a member of` 個々のユーザーの電子メール アドレスをすべて削除し、必要に応じてユーザーを条件に `sender is` 追加します。 </br> - 影響を受けたポリシーの移行を再試行します。|
|述語で `SentToMemberOf` 指定する値は、メールが有効なセキュリティ グループである必要があります。|トランスポート ルールを使用すると、個々のユーザーを条件下で `recipient is a member of` 使用できますが、統合 DLP では許可されません。|- トランスポート ルールを更新して、条件から `recipient is a member of` 個々のユーザーの電子メール アドレスをすべて削除し、必要に応じてユーザーを条件に `recipient is` 追加します。 </br> - 影響を受けたポリシーの移行を再試行します。|
|このパラメーターの `<Name of condition>` 使用は、Exchange でのみサポートされています。 このパラメーターを削除するか、Exchange の場所のみを有効にします。|同じ名前の別のポリシーがコンプライアンス センターに存在し、前述の条件がサポートされていない SPO/ODB/Teams などの他の場所に存在する可能性があります。|Exchange 管理センターで DLP ポリシーの名前を変更し、移行を再試行します。|

## <a name="testing-and-validation---prateek-and-aakash-to-provide-a-list-of-supported-predicates-and-known-issues-before-publishing--"></a>テストと検証 <!--PRATEEK AND AAKASH TO PROVIDE A LIST OF SUPPORTED PREDICATES AND KNOWN ISSUES BEFORE PUBLISHING-->

ポリシーをテストして確認します。

1. [DLP ポリシーのテスト手順に](create-test-tune-dlp-policy.md#test-a-dlp-policy)従います。
2. [アクティビティ エクスプローラー](data-classification-activity-explorer.md)でポリシーによって作成されたイベントを確認します。

## <a name="review-the-policy-matches-between-exchange-admin-center-dlp-and-microsoft-purview-unified-dlp"></a>Exchange 管理 センター DLP と Microsoft Purview Unified DLP のポリシー一致を確認する

移行されたポリシーが期待どおりに動作するようにするには、両方の管理センターからレポートをエクスポートし、ポリシー一致の比較を行うことができます。

1. [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) に接続する
2. [EAC DLP レポート](/powershell/module/exchange/get-maildetaildlppolicyreport)をエクスポートします。 このコマンドレットをコピーし、適切な値を挿入できます。

   ```powershell
   Get-MailDetailDlpPolicyReport -StartDate <dd/mm/yyyy -EndDate <dd/mm/yyyy> -PageSize 5000 | select Date, MessageId, DlpPolicy, TransportRule -Unique | Export-CSV <"C:\path\filename.csv">
   ```

3. [統合 DLP レポート](/powershell/module/exchange/get-dlpdetailreport)をエクスポートします。 このコマンドレットをコピーし、適切な値を挿入できます。

   ```powershell
   Get-DlpDetailReport -StartDate <dd/mm/yyyy> -EndDate <dd/mm/yyyy> -PageSize 5000 | select Date, Location, DlpCompliancePolicy, DlpComplianceRule -Unique | Export-CSV <"C:\path\filename.csv">
   ```

## <a name="activate-your-migrated-policies"></a>移行したポリシーをアクティブ化する

移行したポリシーの機能に問題がなければ、それらを **[適用]** に設定できます。

1. Exchange 管理 センター DLP コンソールを開きます。
2. ソース ポリシーを非アクティブ化または削除します。
3. [Microsoft Purview コンプライアンス ポータル](https://compliance.microsoft.com/datalossprevention?viewid=policies) DLP コンソールを開き、アクティブにして編集するポリシーを選択します。
4. 状態を **[オン]** に変更します。

## <a name="related-articles"></a>関連記事

- [Exchange Onlineデータ損失防止 (DLP) ポリシー](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
- [データ損失防止について](dlp-learn-about-dlp.md)
- [Activity Explorer を使い始める](data-classification-activity-explorer.md)
- [DLP ポリシーを作成、テスト、チューニングする](create-test-tune-dlp-policy.md)
- [テンプレートからの DLP ポリシーの作成](create-a-dlp-policy-from-a-template.md)
- [Exchange Onlineデータ損失防止 (DLP) ポリシー](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
