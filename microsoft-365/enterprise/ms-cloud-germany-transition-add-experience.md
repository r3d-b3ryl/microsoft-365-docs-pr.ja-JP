---
title: Microsoft クラウドの移行に関するその他の技術情報
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: '概要: 新しいドイツデータセンターリージョンの Microsoft Cloud ドイツ (Microsoft Cloud Deut上陸ランド) から Office 365 services に移行する際に、お客様が追加された情報をご利用いただけるようになります。'
ms.openlocfilehash: 1eef8be624a92bf2dcaba8f0df2147697202be3a
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560840"
---
# <a name="additional-experience-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft クラウドの移行に関するその他の技術情報 

次のセクションでは、お客様のエクスペリエンスに関する追加情報を提供します。

## <a name="services"></a>サービス

### <a name="azure-ad"></a>Azure AD

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Office 365 Services にコピーされた Microsoft Cloud Deut上陸土地の Azure AD テナント | Azure AD は、Office 365 サービスにテナントをコピーします。 テナントとユーザー識別子は保持されます。 Azure AD サービスの呼び出しは、Microsoft Cloud Deutare 陸から Office 365 services にリダイレクトされ、サービスに対して透過的です。 | すべての Office のお客様 | -一般的なデータ保護規則 (GDPR) データ主体要求 (DSRs) は、今後の要求のために Azure 管理ポータルから実行されます。 Microsoft Cloud Deut上陸土地に含まれているレガシーまたはお客様以外の診断データは、30日以上経過してから削除されます。 <br><br> -Active Directory フェデレーションサービス (AD FS) でフェデレーション認証を使用しているお客様は、移行時に社内の Active Directory を使用するすべての認証に使用される発行者 Uri を変更しないでください。 発行者 Uri を変更すると、ドメイン内のユーザーに対する認証エラーが発生します。 発行者 Uri は、AD FS で直接変更することも、 _管理対象_ から _フェデレーション_ に、またはその逆に変換することもできます。 移行された Azure AD テナントでは、フェデレーションドメインを追加、削除、または変換しないことをお勧めします。 発行者 Uri は、移行が完全に完了した後で変更できます。 <br><br> -Microsoft Authenticator を使用する多要素認証 (MFA) 要求は、テナントが Office 365 services にコピーされている間、ユーザー ObjectID (GUID) として表示されます。 この表示動作にかかわらず、MFA 要求は期待どおりに実行されます。  Office 365 サービスエンドポイントを使用してアクティブ化された Microsoft Authenticator アカウントは、ユーザープリンシパル名 (UPN) を表示します。  Microsoft Cloud Deut上陸ランドエンドポイントを使用して追加されたアカウントでは、ユーザー ObjectID が表示されますが、Microsoft Cloud deut/陸と Office 365 services の両方のエンドポイントが機能します。  |
| グローバル STS サービスを指している AuthServer のオンプレミスを確立します。 | これにより、ハイブリッドオンプレミス環境を対象とする Exchange の可用性要求に対して Microsoft Cloud Deutare 陸に移行するユーザーからの要求は、オンプレミスのサービスにアクセスするために認証されます。 同様に、オンプレミスから Office 365 services エンドポイントへの要求を認証することができます。 | ハイブリッド (社内) 展開の Exchange Online のお客様 | Azure AD の移行が完了した後、オンプレミスの Exchange (ハイブリッド) トポロジの管理者は、Office 365 サービス用の新しい認証サービスエンドポイントを追加する必要があります。 Exchange PowerShell からのこのコマンドを使用して、 `<TenantID>` 組織のテナント ID に置き換えます (Azure **Active Directory** の azure portal にあります)。 <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> このタスクを完了できないと、ハイブリッド空き時間情報の要求によって、Microsoft Cloud Deut・ランドから Office 365 サービスに移行されたメールボックスユーザーに関する情報が提供されないことがあります。  |
| Azure リソースの移行。 | Office 365 と Azure のリソース (たとえば、ネットワーク、コンピューティング、ストレージ) を使用しているお客様は、Office 365 services インスタンスへのリソースの移行を実行します。 この移行は、お客様の責任です。 メッセージセンターの投稿によって、開始が通知されます。 Office 365 サービス環境で Azure AD 組織の終了前に移行を完了する必要があります。 | Azure のお客様 | Azure 移行の場合は、「azure 移行プレイブック」、「 [Azure ドイツの移行ガイダンスの概要](https://docs.microsoft.com/azure/germany/germany-migration-main)」を参照してください。 |
|||||

<!--
[Reference: Experience][Data Protection] Experience][
[Reference: Experience][Federation] 
[Reference: Experience][MFA]  


[Reference: Experience – Post Migration][Hybrid]    
        

[Reference: Experience – During Migration] [Azure] 
-->

### <a name="exchange-online"></a>Exchange Online

**UserPhoto の設定** を使用している場合は、次のようにします。

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 新しいドイツ地域が既存の組織の設定に追加され、メールボックスが Office 365 サービスに移動されます。 | Exchange Online 構成は、移行中の組織に新しい go ローカルなドイツ地域を追加します。 この Office 365 サービス地域は既定として設定されています。これにより、内部の負荷分散サービスが、Office 365 services の適切な既定の地域にメールボックスを再配布できるようになります。 この移行では、いずれかの側 (ドイツまたは Office 365 services) のユーザーは同じ組織内にあり、いずれかの URL エンドポイントを使用できます。 |  Exchange Online | ユーザーメールボックスが移行されたが、管理者のメールボックスが移行されていない場合、またはその逆の場合、管理者は、PowerShell コマンドレット **を実行する** ことはできません。 このような状況では、管理者は、 `ConnectionUri` 次の構文を使用して、接続の設定時に追加の文字列を渡す必要があります。 <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> ここで、 `<user_email>` は、ユーザーの電子メール ID のプレースホルダーです。これは、ユーザーの写真 **Set-UserPhoto** を変更する必要があります。 |
|||||

<!--
[Reference: Experience][Exchange Online]  [if using Set-UserPhoto] 
-->  

ハイブリッドの社内展開を使用している場合は、次のようにします。

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
|メールボックスまたはオフボードのメールボックスの移動を停止または削除します。  | これにより、移動要求がエラーで失敗することがなくなります。 | ハイブリッド (社内) 展開の Exchange Online のお客様 | 必須のアクションです。 これを怠ると、サービスまたはソフトウェアクライアントの障害が発生する可能性があります。 |
|||||

<!--
[Reference: Experience][Hybrid] 
--> 


### <a name="dynamics"></a>Dynamics

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Microsoft Dynamics のリソース | Microsoft Dynamics を使用しているお客様は、Dynamics を Office 365 services インスタンスに移行するために、エンジニアリングまたは FastTrack によって実行されます。 * | Microsoft Dynamics 365 のお客様 | -移行後、管理者が組織を検証します。 <br><br> -必要に応じて、管理者がワークフローを変更します。 <br><br> -管理者は必要に応じて AdminOnly モードをクリアします。 <br><br> -必要に応じて、管理者が組織の種類を _サンドボックス_ から変更します。 <br><br> -新しい URL のエンドユーザーに、インスタンス (org) へのアクセスを通知します。 <br><br> -新しいエンドポイント URL へのすべての受信接続を更新します。 <br><br> -移行中は、ユーザーが Dynamics サービスを使用できなくなります。 <br><br> -各組織の移行後に、ユーザーは組織の状態と機能を検証する必要があります。  |
|||||

\* (i) Microsoft Dynamics 365 を使用しているお客様は、提供された移行プロセスでの定義に従って、この移行シナリオでアクションを実行する必要があります。 (ii) お客様が行動を取ることによる障害は、Microsoft が移行を完了できないことを意味します。 (iii) お客様の inaction のために Microsoft が移行を完了できない場合、2021年10月29日にお客様のサブスクリプションの有効期限が切れます。 


### <a name="power-bi"></a>Power BI

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Power BI リソースの移行 | Microsoft Power BI を使用しているお客様は、既存の PBI 移行ツールを手動で起動して Power BI を Office 365 services インスタンスに移行した後、エンジニアリングまたは FastTrack によって処理されます。\*\* | Microsoft Power BI のお客様 | -次の Power BI アイテムは移行され _ず_ 、再作成する必要があります。 <br><br> -リアルタイムデータセット (ストリーミングデータセット、プッシュデータセットなど)。 <br> -Power BI オンプレミスのデータゲートウェイの構成とデータソース。 <br> -リアルタイムデータセットの上に構築されたレポートは、移行後には使用できず、再作成する必要があります。 <br><br> -移行中は、ユーザーは Power BI サービスを使用できません。 サービスを利用できない場合は、24時間以上である必要があります。 <br><br> -移行後に Power BI サービスを使用して、データソースとオンプレミスのデータゲートウェイを再構成する必要があります。  そのようにするまで、ユーザーはこれらのデータソースを使用して、これらのデータソースに対してスケジュールされた更新や直接のクエリを実行することはできません。 <br><br> -容量とプレミアムワークスペースを移行することはできません。 お客様は移行前にすべての容量を削除して、移行後に再作成する必要があります。 ワークスペースを必要に応じて容量に戻します。  |
|||||

\*\* (i) Microsoft Power BI を使用しているお客様は、提供された移行プロセスで定義されているように、この移行シナリオでアクションを実行する必要があります。 (ii) お客様が行動を取ることによる障害は、Microsoft が移行を完了できないことを意味します。 (iii) お客様の inaction のために Microsoft が移行を完了できない場合、2021年10月29日にお客様のサブスクリプションの有効期限が切れます。 


### <a name="office-apps"></a>Office アプリ

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| クライアント、office Online の office クライアントのカットオーバー中、Azure AD は、Office 365 サービスを指すようにテナントスコープを終了します。 | この構成変更により、Office クライアントは Office 365 サービスエンドポイントを更新してポイントすることができます。 | すべての Office のお客様 | -ユーザーが所有する DNS から MSOID CName を削除します (存在する場合)。 <br><br> -Office クライアントが変更を選択できるようにするには、 _すべて_ の office アプリを閉じてから再度サインインするようにユーザーに通知します (または、クライアントを強制的に再起動し、ユーザーにサインインしてください)。 <br><br> -ユーザーやヘルプデスクスタッフには、Office バナーが表示され、カットオーバーの72時間以内に Office アプリのライセンス認証を行うよう求めるメッセージが表示されること *があり* ます。 <br><br> -個人用コンピューター上のすべての Office アプリケーションを閉じる必要があり、ユーザーはサインアウトしてから再度サインインする必要があります。 黄色のアクティブ化バーで、サインインして Office 365 サービスに対して再アクティブ化します。 <br><br> -共有マシンには、パーソナルマシンに似たアクションが必要であり、特別な手順は必要ありません。 <br><br> -モバイルデバイスでは、ユーザーはアプリからサインアウトし、それを閉じてから再度サインインする必要があります。 |
|||||

<!--
[Reference: Experience][Office Apps]
--> 

## <a name="during-migration"></a>移行中


### <a name="exchange-online"></a>Exchange Online

電子情報開示の場合:

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 移行中に、電子情報開示の検索が失敗するか、SharePoint Online、OneDrive for Business、および移行された Exchange Online の場所に対して0件の結果が返されます。 | 移行時に、顧客は [セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)( [コンテンツ検索](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)を含む) でケース、保持、検索、エクスポートを引き続き作成できます。  ただし、SharePoint Online、OneDrive for Business、および移行された Exchange Online の場所を対象とした検索では、0の結果が返されるか、エラーが生成されます。 修復については、「 _影響_ 」列を参照してください。 | 電子情報開示を使用するすべてのお客様 |  検索が0件の結果を返す場合や、移行中にエラーが返された場合は、SharePoint Online に対して次の操作を実行してください。 <br><br>  「 [Onedrive または sharepoint のファイルとフォルダーをダウンロード](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)する」の手順に従って、SharePoint Online/Onedrive for business サイトからサイトを直接ダウンロードします。 このメソッドには、サイトでの SharePoint Online 管理者権限または読み取り専用アクセス許可が必要です。 <br><br> 「 [Onedrive または sharepoint からのファイルとフォルダーのダウンロード](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)」で説明されているように、制限を超過した場合、ユーザーは [SharePoint と Teams のファイルをコンピューターに同期](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)するガイダンスに従って onedrive for business 同期クライアントを使用できます。 <br><br> -Exchange Online <br><br> - [Exchange Server のインプレース電子情報開示](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||

<!--
[Reference: Experience – During Migration][ [eDiscovery]
-->          


### <a name="sharepoint-online"></a>SharePoint Online

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| SharePoint と OneDrive は移行されます。 | このフェーズでは、SharePoint と OneDrive を Microsoft Cloud Deut上陸ランドから Office 365 サービスに移行します。 既存の Microsoft Cloud Deut陸の Url は保持され `contoso.sharepoint.de` ます ()。 Microsoft Cloud Deut上陸陸または Office 365 サービスによって発行されるトークンは、移行中に有効です。 | SharePoint のお客様 | Inflight SharePoint 2013 ワークフローは移行時に中断され、移行後に再発行する必要があります。 |
|||||

<!--
[Reference: Experience – During Migration][ [SPO]
-->  

### <a name="skype-for-business-online"></a>Skype for Business Online

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Skype for Business から Teams への移行。 | 既存の Skype for Business のお客様は、ヨーロッパの Office 365 サービスに移行され、Office 365 サービスのドイツ地域で Microsoft Teams に移行しています。 | Skype for Business のお客様 |  PowerShell は、テナントとユーザーの設定とポリシーを管理するために使用します。 PowerShell セッションに接続するときは、次のものを追加します。 <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||

<!--
[Reference: Experience – During Migration][ [SfBO]
-->  


## <a name="post-migration"></a>移行後

### <a name="azure-ad"></a>Azure AD

ハイブリッドの場合:

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Azure AD Connect を更新します。 | Azure AD へのカットオーバーが完了すると、組織は Office 365 サービスを完全に使用しており、Microsoft Cloud Deut上陸陸には接続されなくなります。 この時点で、ユーザーはデルタ同期プロセスが完了していることを確認した後、 `AzureInstance` レジストリパスで 3 (Microsoft Cloud Deut上陸陸) の文字列値を0に変更する必要があり `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` ます。 | ハイブリッド Azure AD –接続された組織 | レジストリキーの値 `AzureInstance` を変更します。 これに失敗すると、Microsoft Cloud Deut上陸陸地のエンドポイントが使用できなくなった後、オブジェクトが同期されなくなります。 |
|||||

<!--
[Reference: Experience – Post Migration][Hybrid]
--> 

フェデレーション認証の場合:

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 証明書利用者信頼を Microsoft Cloud Deutsif AD FS から削除します。 | Azure AD へのカットオーバーが完了すると、組織は Office 365 サービスを完全に使用しており、Microsoft Cloud Deut上陸陸には接続されなくなります。 この時点で、お客様は、証明書利用者信頼を Microsoft Cloud Deut上陸陸地エンドポイントに削除する必要があります。 これは、Azure AD が Id プロバイダー (IdP) として利用されている場合に、お客様のアプリケーションが Microsoft Cloud Deut上陸陸上エンドポイントをポイントしていない場合にのみ実行できます。 | フェデレーション認証組織 | なし。 |
|||||

<!--
[Reference: Experience – Post Migration][Federated]
-->             

Azure AD の場合:

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 元の要求が承認されなかった場合に移行を再度要求する必要があるのは、過去30日間以内に Azure AD グループに参加する要求です。 | エンドユーザーのお客様は、移行前に、過去30日間にこれらの要求が承認されなかった場合に、アクセスパネルを使用して Azure AD グループに参加する要求を再度送信する必要があります。 | 移行前に過去30日間に Azure AD グループの承認要求が承認されていないエンドユーザー |  エンドユーザーとして: <ol><li>[ [Access panel]](https://account.activedirectory.windowsazure.com/r#/joinGroups)に移動します。</li><li>移行前に、30日以内にメンバーシップの承認が保留されていた Azure AD グループを検索します。</li><li>Azure AD グループへの参加要求を再度行います。</li></ol> 移行後に再要求されない限り、30日未満のアクティブなグループへの参加要求は、移行を承認できません。 |
|||||

<!--
[Reference: Experience – Post Migration][Azure AD]
--> 

DNS の場合:

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Office 365 services エンドポイントの社内 DNS サービスを更新します。 | Office 365 ドイツをポイントするユーザーが管理する DNS エントリは、Office 365 サービスエンドポイントを指すように更新する必要があります。 | すべての Office のお客様 | 必須のアクションです。 これを怠ると、サービスまたはソフトウェアクライアントの障害が発生する可能性があります。 |
|||||

<!--
 [Reference: Experience – Post Migration][DNS]
-->

Office 365 services エンドポイントのサードパーティサービスの場合:

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Office 365 サービスエンドポイントのパートナーおよびサードパーティサービスを更新します。 | -Office 365 ドイツをポイントするサードパーティのサービスおよびパートナーは、Office 365 サービスエンドポイントを指すように更新する必要があります。 例: 再登録 (ベンダーとパートナーとの連携)、使用可能な場合は、gallery アプリバージョンのアプリケーション。 <br><br> -Graph API を利用するすべてのカスタムアプリケーション `graph.microsoft.de` をに接続 `graph.microsoft.com` します。 エンドポイントが変更されたその他の Api も、使用する場合は更新する必要があります。 <br><br> -サードパーティ製のすべてのエンタープライズアプリケーションを、全世界のエンドポイントにリダイレクトするように変更します。  | すべての Office のお客様 | 必須のアクションです。 これを怠ると、サービスまたはソフトウェアクライアントの障害が発生する可能性があります。 |
|||||

<!--
 [Reference: Experience – Post Migration][]
--> 

### <a name="exchange-online"></a>Exchange Online

ハイブリッド Exchange 構成を使用している場合:

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Office 365 サービスに対してハイブリッド構成ウィザード (HCW) を再実行します。 | 既存の HCW 構成は、Microsoft Cloud Deut上陸陸をサポートすることを目的としています。 Exchange サービスの移行が完了すると、オンプレミスの構成が Microsoft Cloud Deut上陸陸から分離されます。 | ハイブリッド展開を実行している Exchange Online のお客様 | -必須アクション。 これを怠ると、サービスまたはソフトウェアクライアントの障害が発生する可能性があります。 Exchange メールボックスの移行を開始する前 (5 日以上の通知がある場合) は、停止して、メールボックスのすべてのオンボード移動またはオフボード移動を削除する必要があることをクライアントに通知します。  そのようにしないと、移動要求にエラーが表示されます。 <br><br> -Exchange メールボックスの移行が完了した後、クライアントにオンボード移動とオフボード移動を再開できることを通知します。 <br> **MigrationServerAvailabiilty** を実行している PowerShell コマンドレットは、Microsoft Cloud Deut上陸ランドから Office 365 services への移行中には機能しない可能性があります。 ただし、移行が完了した後では正しく動作します。 <br><br> メールボックスが移行された後、クライアントが資格情報または承認の問題になると、ユーザーは、オンプレミスの管理者資格情報を、を実行して移行エンドポイントに再入力する `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` か、Exchange コントロールパネル (ECP) を使用して同じ設定を行うことができます。  |

<!--
[Reference: Experience – Post Migration][Hybrid]  
[Reference: Experience – Post Migration][Exchange Online]
--> 

電子情報開示の場合:

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
|  すべての SharePoint Online、OneDrive for Business、および Exchange Online の場所は、セキュリティ/コンプライアンスセンター (SCC) と共に移行されました。 | すべての電子情報開示アクティビティは、ワールドワイドテナントから実行する必要があります。 検索は100% 成功しました。  エラーやエラーが発生した場合は、通常のサポートチャネルに従う必要があります。 | 電子情報開示を使用するすべてのお客様 | なし。 |
| 移行前の手順で作成した組織全体のアイテム保持ポリシーを削除する | お客様は、お客様の移行前作業中に作成された組織全体のアイテム保持ポリシーを削除することができます。 | 移行前の手順の一部としてアイテム保持ポリシーを適用したすべてのお客様。 | なし。 |
|||||

<!--
 [Reference: Experience – Post Migration][ [eDiscovery]             

[Reference: Experience – Post Migration][ [eDiscovery]
-->             

### <a name="sharepoint-online"></a>SharePoint Online

| ステップ (s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| SharePoint 2013 ワークフローを再発行します。 | 移行前の作業では、SharePoint 2013 ワークフローの数が減少しました。 移行が完了したので、お客様はワークフローを再発行することができます。 | すべての Office のお客様 | これは必須のアクションです。 このようにしないと、ユーザーの混乱が発生し、ヘルプデスクの呼び出しにつながる可能性があります。 |
| Outlook でアイテムを共有する | Outlook を使用したアイテムの共有は、テナントのカットオーバー後には機能しなくなりました。 | SharePoint Online と OneDrive for Business | -SharePoint Online と OneDrive for Business では、Outlook を使用してアイテムを共有できます。 Outlook ボタンを押すと、共有可能なリンクが作成され、Outlook Web App で新しいメッセージにプッシュされます。 <br><br> -テナントのカットオーバー後は、この共有方法は機能しません。 これは既知の問題であると認識しています。 ただし、この Outlook 機能は廃止のパスにあるため、この問題を解決するには廃止がロールアウトされるまで計画されません。 |

<!--
 [Reference: Experience – Post Migration][ [SPO]
-->

## <a name="next-step"></a>次のステップ

[移行フェーズのアクションと影響について理解する](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>詳細情報

はじめに:

- [新しいドイツ語のデータセンターリージョンの Microsoft Cloud Deutランドから Office 365 サービスへの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中の顧客の利便性](ms-cloud-germany-transition-experience.md)

遷移を移動します。

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [その他の準備作業](ms-cloud-germany-transition-add-pre-work.md)
- [サービス](ms-cloud-germany-transition-add-general.md)、[デバイス](ms-cloud-germany-transition-add-devices.md)、[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、 [AD FS](ms-cloud-germany-transition-add-adfs.md)の追加情報。

クラウドアプリ:

- [Dynamics 365 移行プログラム情報](https://aka.ms/d365ceoptin)
- [Power BI 移行プログラム情報](https://aka.ms/pbioptin)
- [Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)
