---
title: Microsoft Cloud Deutschland からの移行の移行後のアクティビティ
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '概要: Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター地域の Office 365 サービスに移行した後の移行後のアクティビティ。'
ms.openlocfilehash: 745589c1c997540094fc4a770e437de89015f88a
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591758"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft Cloud Deutschland からの移行の移行後のアクティビティ

次のセクションでは、Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター地域の Office 365 サービスに移行した後、複数のサービスの移行後のアクティビティを提供します。

## <a name="azure-ad"></a>Azure AD

### <a name="azure-ad-connect"></a>Azure AD Connect
**適用対象:** すべてのお客様が Azure AD接続と ID を同期する

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| Azure AD接続を更新します。 | Azure AD への切り上げが完了すると、組織は Office 365 サービスを完全に使用し、Microsoft Cloud Deutschland に接続されなくなりました。 この時点で、お客様はデルタ同期プロセスが完了した後、レジストリ パスの文字列値を `AzureInstance` 3 (Microsoft Cloud Deutschland) から 0 に変更する必要があります `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` 。 | レジストリ キーの `AzureInstance` 値を変更します。 そうしない場合、Microsoft Cloud Deutschland エンドポイントが使用できなくなった後、オブジェクトが同期されません。 |
|||||

### <a name="azure-ad-federated-authentication-with-ad-fs"></a>Azure AD FS とのフェデレーションAD認証
**適用対象:** FS とのフェデレーション認証を使用AD顧客

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| Microsoft Cloud Deutschland および FS から証明書利用者の信頼AD削除します。 | Azure AD へのカットオーバーが完了すると、組織は Office 365 サービスを完全に使用し、Microsoft Cloud Deutschland に接続されなくなりました。 この時点で、顧客は Microsoft Cloud Deutschland エンドポイントに対する証明書利用者の信頼を削除する必要があります。 これは、Azure AD が ID プロバイダー (IdP) として活用されている場合にのみ、お客様のアプリケーションが Microsoft Cloud Deutschland エンドポイントをポイントしない場合にのみ実行できます。 | フェデレーション認証組織 | なし。 |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a>グループの承認
**適用対象:** 移行前の過去 30 日間に Azure AD承認要求が承認されなかったエンド ユーザー 

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| 移行前の過去 30 日間に Azure AD グループに参加する要求は、元の要求が承認されなかった場合は、再度要求する必要があります。 | 移行前の過去 30 日間にこれらの要求が承認されなかった場合、エンドユーザーのお客様は Access パネルを使用して Azure AD グループに再度参加する要求を送信する必要があります。 |  エンド ユーザーとして次の情報を使用します。 <ol><li>[アクセス] [パネルに移動します](https://account.activedirectory.windowsazure.com/r#/joinGroups)。</li><li>移行前 30 ADの間にメンバーシップの承認が保留された Azure ユーザー グループを検索します。</li><li>Azure ADへの参加を要求します。</li></ol> 移行の 30 日未満前にアクティブなグループに参加する要求は、移行後に再度要求されていない限り、承認できません。 |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
## <a name="custom-dns-updates"></a>カスタム DNS 更新プログラム
**適用対象:**  自分の DNS ゾーンを管理しているすべての顧客

| Step(s) | 説明 | 影響 |
|:------|:-------|:-------|
| 365 サービス エンドポイントのOffice DNS サービスを更新します。 | Microsoft Cloud Deutschland を指す顧客管理 DNS エントリを更新して、Office 365 グローバル サービス エンドポイントをポイントする必要があります。 | サービスまたはソフトウェア クライアントの障害が発生する可能性があります。 |
||||

## <a name="third-party-services"></a>サード パーティのサービス
**適用対象:** 365 サービス エンドポイントでサード パーティOfficeを使用しているお客様

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| 365 サービス エンドポイントのパートナーとOfficeサービスを更新します。 | <ul><li>Office 365 ドイツを指すサード パーティのサービスとパートナーは、Office 365 サービス エンドポイントをポイントするために更新する必要があります。 例: 利用可能な場合は、ベンダーやパートナーと連携して、ギャラリー アプリのバージョンのアプリケーションを再登録します。 </li><li>Graph API を利用するカスタム アプリケーションのポイントを指定 `graph.microsoft.de` します `graph.microsoft.com` 。 エンドポイントが変更された他の API も、活用する場合は更新する必要があります。 </li><li>すべてのファースト パーティ以外のエンタープライズ アプリケーションを変更して、世界中のエンドポイントにリダイレクトします。 </li></ul>| 必須のアクション。 サービスまたはソフトウェア クライアントの障害が発生する可能性があります。 |
||||

## <a name="sharepoint-online"></a>SharePoint Online
**適用対象**: SharePoint 2013 ワークフローを使用しているお客様

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| SharePoint 2013 ワークフローを再発行します。 | 移行前の作業では、SharePoint 2013 ワークフローの数を減らしました。 移行が完了すると、顧客はワークフローを再発行できます。 | これは必須のアクションです。 そうしない場合は、ユーザーの混乱やヘルプ デスクの呼び出しが発生する可能性があります。 |
| Outlook 経由でアイテムを共有する | SharePoint Online と OneDrive for Business のアイテムを Outlook 経由で共有すると、テナントの切り替え後に機能しなくなりました。 |<ul><li>SharePoint Online および OneDrive for Business では、Outlook 経由でアイテムを共有できます。 Outlook ボタンを押すと、共有可能なリンクが作成され、新しいメッセージにプッシュOutlook Web App。</li><li>テナントの切り替え後、この共有方法は機能しません。 これは既知の問題だと認識しています。 ただし、この Outlook 機能は廃止の道にあるので、廃止が展開されるまで問題の修正は計画されていません。 </li></ul>|
||||

## <a name="exchange-online"></a>Exchange Online
**適用対象**: ハイブリッド Exchange 構成を使用しているお客様

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| ハイブリッド構成ウィザード (HCW) を 365 サービスOffice再実行します。 | 既存の HCW 構成は、Microsoft Cloud Deutschland をサポートすることを意図しています。 Exchange サービスの移行が完了すると、Microsoft Cloud Deutschland からオンプレミス構成を切り離します。 |<ul><li>必須のアクション。 サービスまたはソフトウェア クライアントの障害が発生する可能性があります。 Exchange メールボックスの移行が開始する前に (5 日以上の通知を含む)、メールボックスのオンボーディングまたはオフボードの移動を停止して削除する必要があるクライアントに通知します。  表示しない場合は、移動要求にエラーが表示されます。 </li><li>Exchange メールボックスの移行が完了したら、オンボーディングとオフボードの移動を再開できるクライアントに通知します。 <br> Microsoft Cloud Deutschland から 365 サービスへの Exchange の移行中に、PowerShell コマンドレットである **Test-MigrationServerAvailabiilty** を実行すると、Office 365 サービスが動作しない可能性があります。 ただし、移行が完了すると正しく動作します。 </li><li>メールボックスの移行後にクライアントが資格情報または承認に関する問題にぶつかった場合、ユーザーは Exchange コントロール パネル (ECP) を使用して、移行エンドポイントでオンプレミスの管理者資格情報を再入力できます。 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` </li></ul>|
