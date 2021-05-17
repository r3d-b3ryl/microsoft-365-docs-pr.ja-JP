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
description: '概要: 移行後のアクティビティは、Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツのデータセンター地域Office 365サービスに移行した後です。'
ms.openlocfilehash: ee8dedf7ffaf6bfc4246b1a8cc2522c15d763cd1
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899366"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft Cloud Deutschland からの移行の移行後のアクティビティ

次のセクションでは、Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター地域の Office 365 サービスに移行した後、複数のサービスの移行後のアクティビティを提供します。

## <a name="azure-ad"></a>Azure AD
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a>Azure AD FS とのフェデレーションAD認証
**適用対象:** FS とのフェデレーション認証を使用AD顧客

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| Microsoft Cloud Deutschland および FS から証明書利用者の信頼AD削除します。 | Azure への切りADが完了すると、組織は Office 365 サービスを完全に使用し、Microsoft Cloud Deutschland に接続されなくなりました。 この時点で、顧客は Microsoft Cloud Deutschland エンドポイントに対する証明書利用者の信頼を削除する必要があります。 これは、Azure AD が ID プロバイダー (IdP) として活用されている場合にのみ、お客様のアプリケーションが Microsoft Cloud Deutschland エンドポイントをポイントしない場合にのみ実行できます。 | フェデレーション認証組織 | なし。 |
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
| サービス エンドポイントのオンプレミス DNS サービスOffice 365更新します。 | Microsoft Cloud Deutschland を指す顧客管理 DNS エントリは、グローバル サービス エンドポイントをポイントOffice 365更新する必要があります。 | サービスまたはソフトウェア クライアントの障害が発生する可能性があります。 |
||||

## <a name="third-party-services"></a>サード パーティのサービス
**適用対象:** サービス エンドポイントにサードパーティ サービスを使用Office 365顧客

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| パートナーとサード パーティのサービスを、Office 365エンドポイントに更新します。 | <ul><li>ドイツを指すサードパーティのサービスOffice 365パートナーは、サービス エンドポイントをポイントOffice 365する必要があります。 例: 利用可能な場合は、ベンダーやパートナーと連携して、ギャラリー アプリのバージョンのアプリケーションを再登録します。 </li><li>API を利用するカスタム アプリケーションGraphをポイント `graph.microsoft.de` します `graph.microsoft.com` 。 エンドポイントが変更された他の API も、活用する場合は更新する必要があります。 </li><li>すべてのファースト パーティ以外のエンタープライズ アプリケーションを変更して、世界中のエンドポイントにリダイレクトします。 </li></ul>| 必須のアクション。 サービスまたはソフトウェア クライアントの障害が発生する可能性があります。 |
||||

## <a name="sharepoint-online"></a>SharePoint Online
**適用対象**: 2013 ワークフロー SharePoint使用しているお客様

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| 2013 SharePointを再発行します。 | 移行前の作業では、2013 年のワークフロー SharePoint減らしました。 移行が完了すると、顧客はワークフローを再発行できます。 | これは必須のアクションです。 そうしない場合は、ユーザーの混乱やヘルプ デスクの呼び出しが発生する可能性があります。 |
| アイテムを共有するには、Outlook | テナントの切りSharePoint後 OneDrive for Business、SharePoint経由Outlookアイテムの共有が機能しなくなりました。 |<ul><li>[SharePoint]および [OneDrive for Business] では、アイテムを [オンライン] または [Outlook] で共有Outlook。 [リンク] ボタンOutlookすると、共有可能なリンクが作成され、新しいメッセージにプッシュOutlook Web App。</li><li>テナントの切り替え後、この共有方法は機能しません。 これは既知の問題だと認識しています。 ただし、このOutlook機能は廃止の道にあるので、廃止が展開されるまで問題の修正は計画されていません。 </li></ul>|
||||

## <a name="exchange-online"></a>Exchange Online
**適用対象**: ハイブリッド 構成を使用しているExchangeします。

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| ハイブリッド構成ウィザード (HCW) を実行し、Office 365します。 | 既存の HCW 構成は、Microsoft Cloud Deutschland をサポートすることを意図しています。 サービスの移行Exchange、Microsoft Cloud Deutschland からオンプレミス構成を切り離します。 |<ul><li>必須のアクション。 サービスまたはソフトウェア クライアントの障害が発生する可能性があります。 メールボックスExchange移行を開始する前に (5 日以上の通知を含む)、メールボックスのオンボーディングまたはオフボードの移動を停止して削除する必要があるクライアントに通知します。  表示しない場合は、移動要求にエラーが表示されます。 </li><li>メールボックスExchangeが完了したら、オンボーディングとオフボードの移動を再開できるクライアントに通知します。 <br> Microsoft Cloud Deutschland から Office 365 サービスへの Exchange の移行中に、PowerShell コマンドレットである **Test-MigrationServerAvailabiilty** を実行すると、動作しない可能性があります。 ただし、移行が完了すると正しく動作します。 </li><li>クライアントがメールボックスの移行後に資格情報または承認に関する問題にぶつかった場合、ユーザーは、Exchange コントロール パネル (ECP) を使用して、移行エンドポイントでオンプレミスの管理者資格情報を再入力できます。 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` </li></ul>|
